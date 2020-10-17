---
title: Lync Server 2013：在跨界环境中配置 Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Microsoft Lync Server 2013 in a cross-premises environment
ms:assetid: 700639ec-5264-4449-a8a6-d7386fad8719
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204990(v=OCS.15)
ms:contentKeyID: 48184449
ms.date: 02/21/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f6399185e045afb56231550abc33ab514db0d04
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517379"
---
# <a name="configuring-microsoft-lync-server-2013-in-a-cross-premises-environment"></a>在跨界环境中配置 Microsoft Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2017-02-21_

在跨内部部署配置中，某些用户驻留在 Microsoft Lync Server 2013 的本地安装中，而其他用户托管在 Microsoft 365 或 Office 365 版本的 Lync Server 上。 为了在跨界环境中配置服务器到服务器的身份验证，您必须首先将 Lync Server 2013 的本地安装配置为信任 Microsoft 365 授权服务器。 此过程的初始步骤可通过运行以下 Lync Server 命令行管理程序脚本执行：

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

脚本完成后，您必须配置 Lync Server 2013 与授权服务器之间的信任关系，以及 Exchange 2013 和授权服务器之间的第二个信任关系。 只能通过 Microsoft Online Services cmdlet 做到这一点。

<div>


> [!NOTE]  
> 如果您尚未安装 Microsoft Online Services cmdlet，则您需要先完成两项操作，然后再继续。 首先，下载并安装 64 位版本的 Microsoft Online Services 登录助手。 安装完成后，下载并安装适用于 Windows PowerShell 的64位版本的 Microsoft Online Services 模块。 可以在 Microsoft 365 或 Office 365 网站上找到有关安装和使用 Microsoft Online Services 模块的详细信息。 这些说明还将告诉你如何在 Microsoft 365 或 Office 36 与 Active Directory 之间配置单一登录、联合和同步。<BR>如果尚未安装这些 cmdlet，则脚本将失败，因为 Get-CsTenant cmdlet 将不可用。



</div>

配置 Microsoft 365 并在为 Lync Server 2013 和 Exchange 2013 创建 Microsoft 365 或 Office 365 服务主体之后，您需要使用这些服务主体注册您的凭据。 为此，您必须先获取另存为 .CER 文件的 X.509 Base64。 此证书将应用于 Microsoft 365 或 Office 365 服务主体。

获取 x.509 证书后，启动 Microsoft Online Services 模块 (依次单击 " **开始**"、" **所有程序**"、" **microsoft Online Services**" 和 " **Windows PowerShell) 的 microsoft online services 模块** "。 在服务模块打开后，键入以下命令以导入包含可用于管理服务主体的 cmdlet 的 Microsoft Online Windows PowerShell 模块：

    Import-Module MSOnlineExtended

导入该模块后，键入以下命令，然后按 ENTER 键以连接到 Microsoft 365：

    Connect-MsolService

按 Enter 后，随即出现一个凭据对话框。 在对话框中输入 Microsoft 365 或 Office 365 用户名和密码，然后单击 "确定"。

一旦连接到 Microsoft 365，您就可以运行以下命令来返回有关您的服务主体的信息：

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

下一步是导入、编码和分配 X.509 证书。 若要导入和编码证书，请使用以下 Windows PowerShell 命令，确保指定了的完整文件路径。CER 文件调用 Import 方法时：

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

在导入并编码证书后，您可以将证书分配给 Microsoft 365 服务主体。 为此，请先使用 Get-MsolServicePrincipal 检索针对 Lync Server 和 Microsoft Exchange 服务主体的 AppPrincipalId 属性的值；AppPrincipalId 属性的值将用于标识分配了证书的服务主体。 使用 Lync Server 2013 的 AppPrincipalId 属性值，使用以下命令将证书分配给 Microsoft 365 版本的 Lync Server ("起始日期" 和 "结束时间" 属性应对应于证书) 的有效期：

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

然后，您应该重复该命令，这次使用的是 Exchange 2013 的 AppPrincipalId 属性值。

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

除了分配证书之外，还必须通过为本地版本的 Lync Server 2013 添加服务器主体名称，从而为 Exchange Online 配置 Microsoft 365 服务主体。 可通过在 Microsoft Online Services PowerShell 会话中运行以下四行来实现此目的：

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

</div>

<span> </span>

</div>

</div>

</div>

