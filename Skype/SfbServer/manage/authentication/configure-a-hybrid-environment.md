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
ms.openlocfilehash: ed82e72c04d6fca0702a37819778d880b45ef617
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818834"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>为 Skype for business Server 混合环境配置服务器到服务器身份验证。

**摘要：** 为 Skype for business Server 混合环境配置服务器到服务器身份验证。

在混合配置中，你的某些用户驻留在本地安装 Skype for Business 服务器，而其他用户托管在 Office 365 版本的 Skype for Business 服务器上。 为了在混合环境中配置服务器到服务器的身份验证，必须首先配置 Skype for Business 服务器的本地安装，以信任 Office 365 授权服务器。 通过运行以下 Skype for Business Server Management Shell 脚本，可以执行此过程中的初始步骤：

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

若要执行此脚本，你必须已安装 Skype for Business Online PowerShell 模块并使用此模块连接到你的租户。 如果您未安装这些 cmdlet，您的脚本将失败，因为 Get-CsTenant cmdlet 不可用。 脚本完成后，必须配置 Skype for Business 服务器与授权服务器之间的信任关系，以及 Exchange 2013/2016 和授权服务器之间的第二个信任关系。 这只能使用 Microsoft Online Services cmdlet 来完成。

> [!NOTE]
> 如果尚未安装 Microsoft Online Services cmdlet，你将需要使用 cmdlet `install-module MSOnline`从 PowerShell 存储库中安装它。 可在 Office 365 网站上找到有关安装和使用 Microsoft Online Services 模块的详细信息。 这些说明还将告诉你如何在 Office 365 和 Active Directory 之间配置单一登录、联盟和同步。 



配置 Office 365 后，在为 Skype for business Server 和 Exchange 2013 创建 Office 365 服务主体之后，你将需要向这些服务主体注册你的凭据。 为此，必须首先获取一个 x.509 Base64 证书，另存为。CER 文件。 此证书将应用于 Office 365 服务主体。

获取 x.509 证书后，打开 PowerShell 控制台并导入包含可用于管理服务主体的 cmdlet 的 Microsoft Online Windows PowerShell 模块：

```PowerShell
Import-Module MSOnline
```

导入模块后，键入以下命令，然后按 ENTER 以连接到 Office 365：

```PowerShell
Connect-MsolService
```

按 Enter 后，随即出现一个凭据对话框。 在对话框中输入 Office 365 的用户名和密码，然后单击 "确定"。

连接到 Office 365 后，你可以立即运行以下命令以返回有关你的服务主体的信息：

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

下一步是导入、编码和分配 X.509 证书。 若要导入和编码证书，请使用以下 Windows PowerShell 命令，确保为你指定完整的文件路径。在调用 Import 方法时的 CER 文件：

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

在证书导入和编码后，你可以将证书分配给你的 Office 365 服务主体。 若要执行此操作，请首先使用 MsolServicePrincipal 检索 Skype for business 服务器和 Microsoft Exchange 服务主体的 AppPrincipalId 属性的值;AppPrincipalId 属性的值将用于标识分配了证书的服务主体。 使用 Skype for business 服务器的 AppPrincipalId 属性值，使用以下命令将证书分配到 Skype For business Online 版本：

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

然后，你应该使用 Exchange 2013 的 AppPrincipalId 属性值，重复该命令。

如果您以后需要删除该证书（例如，它已过期），您可以通过首先检索证书的 KeyId 来执行此操作：

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

除了分配证书之外，还必须配置 Exchange Online 服务主体，并将本地版本的 Skype for Business 服务器外部 Web 服务 Url 配置为 Office 365 服务主体。 可通过执行下面两条命令达到此目的。 

在以下示例中，Pool1ExternalWebFQDN.contoso.com 是 Skype for business 服务器池的外部 Web 服务 URL。 应重复这些步骤来添加部署中的所有外部 Web 服务 Url。

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
