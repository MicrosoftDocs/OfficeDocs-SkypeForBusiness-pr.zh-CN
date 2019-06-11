---
title: 'Lync Server 2013: 在跨平台环境中配置 Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Microsoft Lync Server 2013 in a cross-premises environment
ms:assetid: 700639ec-5264-4449-a8a6-d7386fad8719
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204990(v=OCS.15)
ms:contentKeyID: 48184449
ms.date: 02/21/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44a47dc3bf3c832819fe431cb0177bfc1a03f330
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-in-a-cross-premises-environment"></a>在跨平台环境中配置 Microsoft Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2017-02-21_

在跨部署配置中, 你的某些用户驻留在 Microsoft Lync Server 2013 的本地安装中, 而其他用户托管在 Office 365 版本的 Lync Server。 为了在跨平台环境中配置服务器到服务器身份验证, 必须首先配置 Lync Server 2013 的本地安装, 以信任 Office 365 授权服务器。 通过运行以下 Lync Server Management Shell 脚本, 可以执行此过程中的初始步骤:

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

在脚本完成后, 必须配置 Lync Server 2013 和授权服务器之间的信任关系, 以及 Exchange 2013 和授权服务器之间的第二个信任关系。 这只能使用 Microsoft Online Services cmdlet 来完成。

<div>


> [!NOTE]  
> 如果尚未安装 Microsoft Online Services cmdlet, 则需要执行两个操作才能继续操作。 首先，下载并安装 64 位版本的 Microsoft Online Services 登录助手。 安装完成后, 下载并安装适用于 Windows PowerShell 的 Microsoft Online Services 模块的64位版本。 可在 Office 365 网站上找到有关安装和使用 Microsoft Online Services 模块的详细信息。 这些说明还将告诉你如何在 Office 365 和 Active Directory 之间配置单一登录、联盟和同步。<BR>如果您未安装这些 cmdlet，您的脚本将失败，因为 Get-CsTenant cmdlet 不可用。



</div>

配置 Office 365 后, 在为 Lync Server 2013 和 Exchange 2013 创建 Office 365 服务主体之后, 你将需要向这些服务主体注册你的凭据。 为此，您必须先获取另存为 .CER 文件的 X.509 Base64。 此证书将应用于 Office 365 服务主体。

获取 x.509 证书后, 启动 Microsoft Online Services 模块 (单击 "**开始**", 单击 "**所有程序**", 单击 " **microsoft online 服务**", 然后单击 " **microsoft online services 模块 for Windows"PowerShell**)。 服务模块打开后, 键入以下内容以导入包含可用于管理服务主体的 cmdlet 的 Microsoft Online Windows PowerShell 模块:

    Import-Module MSOnlineExtended

导入模块后, 键入以下命令, 然后按 ENTER 以连接到 Office 365:

    Connect-MsolService

按 Enter 后，随即出现一个凭据对话框。 在对话框中输入 Office 365 的用户名和密码, 然后单击 "确定"。

连接到 Office 365 后, 你可以立即运行以下命令, 以返回有关你的服务主体的信息:

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

下一步是导入、编码和分配 X.509 证书。 若要导入和编码证书, 请使用以下 Windows PowerShell 命令, 确保为你指定完整的文件路径。在调用 Import 方法时的 CER 文件:

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

在证书导入和编码后, 你可以将证书分配给你的 Office 365 服务主体。 若要执行此操作, 请首先使用 MsolServicePrincipal 检索 Lync Server 和 Microsoft Exchange 服务主体的 AppPrincipalId 属性的值;AppPrincipalId 属性的值将用于标识分配了证书的服务主体。 使用 Lync Server 2013 的 AppPrincipalId 属性值, 使用以下命令将证书分配给 Lync Server 的 Office 365 版本 ("开始日期" 和 "结束时间" 属性应对应于证书的有效期):

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

然后, 你应该使用 Exchange 2013 的 AppPrincipalId 属性值, 重复该命令。

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

除了分配证书之外, 还必须通过为本地版本的 Lync Server 2013 添加服务器主体名称, 为 Exchange Online 配置 Office 365 服务主体。 可通过在 Microsoft Online Services PowerShell 会话中运行以下四行来执行此操作:

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

</div>

<span> </span>

</div>

</div>

</div>

