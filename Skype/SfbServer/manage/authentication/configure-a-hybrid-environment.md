---
title: 为 Skype for business Server 混合环境配置服务器到服务器身份验证
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 摘要：为 Skype for business Server 混合环境配置服务器到服务器身份验证。
ms.openlocfilehash: 191d5d2f391df73401ff27e8c71a60624e74296c
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780731"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>为 Skype for business Server 混合环境配置服务器到服务器身份验证。

**摘要：** 为 Skype for business Server 混合环境配置服务器到服务器身份验证。

在混合配置中，您的一些用户驻留在 Skype for business Server 的本地安装中，而其他用户托管在 Office 365 版本的 Skype for business Server 中。 若要在混合环境中配置服务器到服务器身份验证，必须首先将 Skype for Business 服务器的本地安装配置为信任 Office 365 授权服务器。 此过程的初始步骤可通过运行以下 Skype for Business Server 命令行管理程序脚本执行：

```PowerShell
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
```

请记住，租户的领域名称通常与组织名称不同；实际上，领域名称几乎始终与租户 ID 相同。为此，脚本中的第一行用于返回指定租户（此示例中为 fabrikam.com）的 TenantId 属性的值，然后将该名称分配给变量 $TenantId：

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

若要执行此脚本，您必须已安装 Skype for Business Online PowerShell 模块，并使用此模块连接到你的租户。 如果尚未安装这些 cmdlet，则脚本将失败，因为 Get-cstenant cmdlet 将不可用。 脚本完成后，您必须配置 Skype for Business Server 和授权服务器之间的信任关系，以及 Exchange 2013/2016 与授权服务器之间的第二个信任关系。 只能通过 Microsoft Online Services cmdlet 做到这一点。

> [!NOTE]
> 如果尚未安装 Microsoft Online Services cmdlet，则需要使用 cmdlet `install-module MSOnline`从 PowerShell 存储库中安装它。 可在 Office 365 网站上找到有关安装并使用 Microsoft Online Services 模块的详细信息。 这些说明将告知您如何配置单一登录、联盟以及 Office 365 与 Active Directory 之间的同步。 



在配置了 Office 365 并为 Skype for business Server 和 Exchange 2013 创建了 Office 365 服务主体之后，你将需要使用这些服务主体注册你的凭据。 若要执行此操作，必须首先获取一个 x.509 Base64 证书另存为。CER 文件。 然后，将此证书应用于 Office 365 服务主体。

获取 x.509 证书后，打开 PowerShell 控制台，然后导入 Microsoft Online Windows PowerShell 模块，其中包含可用于管理服务主体的 cmdlet：

```PowerShell
Import-Module MSOnline
```

导入该模块后，键入以下命令并按 Enter 以连接到 Office 365：

```PowerShell
Connect-MsolService
```

按 Enter 后，随即出现一个凭据对话框。 在对话框中输入 Microsoft 365 或 Office 365 用户名和密码，然后单击 "确定"。

一旦连接到 Office 365，您就可以运行以下命令来返回有关您的服务主体的信息：

```PowerShell
Get-MsolServicePrincipal
```

您应获得与以下信息类似的所有服务主体的相关信息：

<pre>
ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
AccountEnabled       : True
Addresses            : {}
AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
DisplayName          : Skype for Business Server
ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
ServicePrincipalName : SkypeForBusinessServer/litwareinc.com
TrustedForDelegation : True
</pre>

下一步是导入、编码和分配 X.509 证书。 若要导入和编码证书，请使用以下 Windows PowerShell 命令，确保指定了的完整文件路径。CER 文件调用 Import 方法时：

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

在导入并编码证书后，您可以将证书分配给您的 Office 365 服务主体。 为此，请首先使用 New-msolserviceprincipal 检索 Skype for Business Server 和 Microsoft Exchange 服务主体的 AppPrincipalId 属性的值;AppPrincipalId 属性的值将用于标识为其分配证书的服务主体。 使用适用于 Skype for business Server 的 AppPrincipalId 属性值，请使用以下命令将证书分配到 Skype For Business Online 版本：

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

然后，您应该重复该命令，这次使用的是 Exchange 2013 的 AppPrincipalId 属性值。

如果您稍后需要删除该证书（例如，如果它已过期），您可以通过先检索证书的 KeyId 来执行此操作：

```PowerShell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

此命令将返回与以下内容类似的数据：

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

然后，您可以使用与以下内容类似的命令删除该证书：

```PowerShell
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

除了分配证书之外，还必须配置 Exchange Online 服务主体，并将本地版本的 Skype for Business Server 外部 Web 服务 Url 配置为 Office 365 服务主体。 为此，可以执行以下两个命令。 

在以下示例中，Pool1ExternalWebFQDN.contoso.com 是 Skype for Business Server 池的外部 Web 服务 URL。 应重复这些步骤以添加部署中的所有外部 Web 服务 Url。

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
