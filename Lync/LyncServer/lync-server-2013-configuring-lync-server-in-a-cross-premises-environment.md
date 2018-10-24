---
title: 在交叉部署环境中配置 Microsoft Lync Server 2013
TOCTitle: 在交叉部署环境中配置 Microsoft Lync Server 2013
ms:assetid: 700639ec-5264-4449-a8a6-d7386fad8719
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204990(v=OCS.15)
ms:contentKeyID: 49313204
ms.date: 02/21/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在交叉部署环境中配置 Microsoft Lync Server 2013

 

_**上一次修改主题：** 2017-02-21_

在交叉配置中，您的一些用户驻留在 Microsoft Lync Server 2013 的本地安装中，而其他用户驻留在 Office 365 版本的 Lync Server 中。若要在交叉环境中配置服务器间身份验证，您必须先将 Lync Server 2013 的本地安装配置为信任 Office 365 授权服务器。此过程的初始步骤可通过运行以下 Lync Server 命令行管理程序脚本执行：

    $TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
    
    $sts = Get-CsOAuthServer microsoft.sts -ErrorAction SilentlyContinue
            
       if ($sts -eq $null)
          {
             New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
          }
       else
          {
             if ($sts.MetadataUrl -ne  "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1")
                {
                   Remove-CsOAuthServer microsoft.sts
                   New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
                }
            }
    
    $exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue
            
    if ($exch -eq $null)
       {
          New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer
        }
    else
        {
           if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
              {
                 Remove-CsPartnerApplication microsoft.exchange
                 New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer 
              }
           else
              {
                 Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full -UseOAuthServer
              }
       }
    
    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

请记住，租户的领域名称通常与组织名称不同；实际上，领域名称几乎始终与租户 ID 相同。为此，脚本中的第一行用于返回指定租户（此示例中为 fabrikam.com）的 TenantId 属性的值，然后将该名称分配给变量 $TenantId：

    $TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId

脚本完成后，您必须在 Lync Server 2013 和授权服务器之间配置一层信任关系，并在 Exchange 2013 和授权服务器之间配置另一层信任关系。只能通过 Microsoft Online Services cmdlet 做到这一点。

> [!NOTE]  
> 如果您尚未安装 Microsoft Online Services cmdlet，则您需要先完成两项操作，然后再继续。首先，下载并安装 64 位版本的 Microsoft Online Services 登录助手。完成此安装后，再下载并安装 64 位版本的用于 Windows PowerShell 的 Microsoft Online Services 模块。可在 Office 365 网站上找到有关安装并使用 Microsoft Online Services 模块的详细信息。这些说明将告知您如何配置单一登录、联盟以及 Office 365 与 Active Directory 之间的同步。<br />
如果您未安装这些 cmdlet，您的脚本将失败，因为 Get-CsTenant cmdlet 不可用。



在配置 Office 365 并创建针对 Lync Server 2013 和 Exchange 2013 的 Office 365 服务主体后，您需要将您的凭据注册到这些服务主体中。为此，您必须先获取另存为 .CER 文件的 X.509 Base64。然后，将此证书应用于 Office 365 服务主体。

在获得 X.509 证书后，启动 Microsoft Online Services 模块（依次单击“开始”、“所有程序”、“Microsoft Online Services”和“用于 Windows PowerShell 的 Microsoft Online Services 模块”）。打开该服务模块后，键入以下命令导入包括可用于管理服务主体的 cmdlet 的 Microsoft Online Windows PowerShell 模块：

    Import-Module MSOnlineExtended

导入该模块后，键入以下命令并按 Enter 以连接到 Office 365：

    Connect-MsolService

按 Enter 后，随即出现一个凭据对话框。在该对话框中输入您的 Office 365 用户名和密码，然后单击“确定”。

连接到 Office 365 后，您便能运行以下命令来返回有关您的服务主体的信息：

    Get-MsolServicePrincipal

您应获得与以下信息类似的所有服务主体的相关信息：

    ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
    AccountEnabled       : True
    Addresses            : {}
    AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
    DisplayName          : Microsoft Lync Server
    ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
    ServicePrincipalName : LyncServer/litwareinc.com
    TrustedForDelegation : True

下一步是导入、编码和分配 X.509 证书。若要导入和编码证书，请使用以下 Windows PowerShell 命令，并确保在调用 Import 方法时指定 .CER 文件的完整文件路径：

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

在导入并编码证书后，您可以将证书分配给您的 Office 365 服务主体。为此，请先使用 Get-MsolServicePrincipal 检索针对 Lync Server 和 Microsoft Exchange 服务主体的 AppPrincipalId 属性的值；AppPrincipalId 属性的值将用于标识分配了证书的服务主体。获得 Lync Server 2013 的 AppPrincipalId 属性值后，可使用以下命令将证书分配给 Office 365 版本的 Lync Server（StartDate 和 EndDate 属性应对应于证书的有效期）：

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

然后，您应重复该命令，此时使用的是 Exchange 2013 的 AppPrincipalId 属性值。

如果您稍后需要删除该证书，可通过先检索证书的 KeyId 来执行此操作：

    Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000

此命令将返回与以下内容类似的数据：

    Type      : Asymmetric
    Value     : 
    KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
    StartDate : 6/1/2012 8:00:00 AM
    EndDate   : 5/31/2013 8:00:00 AM
    Usage     : Verify

然后，您可以使用与以下内容类似的命令删除该证书：

    Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0

除了分配证书以外，您还必须配置 Exchange Online 服务主体，并将本地版本的 Lync Server 2013 配置为 Office 365 服务主体。可通过执行下面两条命令达到此目的：

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

