---
title: 为混合环境配置服务器Skype for Business Server身份验证
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 摘要：为混合环境配置Skype for Business Server身份验证。
ms.openlocfilehash: 1da99f335e5d26523bb29ef6e11251019e2020c8
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58587194"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>为混合环境配置Skype for Business Server身份验证。

**摘要：** 为混合环境配置Skype for Business Server身份验证。

在混合配置中，您的一些用户位于 Skype for Business Server 本地安装中，而其他用户则位于 Microsoft 365 或 Office 365 版本的 Skype for Business Server。 为了在混合环境中配置服务器到服务器身份验证，您必须先配置内部部署 Skype for Business Server信任授权服务器。 此过程的初始步骤可通过运行以下命令行管理程序脚本Skype for Business Server执行：

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

若要执行此脚本，必须已安装 Skype for Business Online PowerShell 模块，并连接到包含此模块的租户。 如果尚未安装这些 cmdlet，脚本将失败，Get-CsTenant cmdlet 不可用。 脚本完成后，您必须在 Skype for Business Server 和授权服务器之间配置信任关系，以及 Exchange 2013/2016 和授权服务器之间的第二个信任关系。 只能通过 Microsoft Online Services cmdlet 做到这一点。

> [!NOTE]
> 如果您尚未安装 Microsoft Online Services cmdlet，则需要使用 cmdlet 从 PowerShell 存储库安装 `install-module MSOnline` 它。 有关安装和使用 Microsoft Online Services 模块的详细信息，请参阅 Microsoft 365 网站。 这些说明还将告诉你如何在 active Directory 或 Microsoft 365 Office 365配置单一登录、联合和同步。 



配置 Microsoft 365 或 Office 365，为 Skype for Business Server 和 Exchange 2013 创建 Microsoft 365 或 Office 365 服务主体后，您需要向这些服务主体注册凭据。 为此，必须先获取另存为 的 X.509 Base64 证书。CER 文件。 然后，此证书将应用于 Microsoft 365 或 Office 365 服务主体。

获取 X.509 证书后，打开 PowerShell 控制台并导入包含可用于管理服务主体的 cmdlet 的 Microsoft Online Windows PowerShell 模块：

```PowerShell
Import-Module MSOnline
```

导入模块后，键入以下命令，然后按 Enter：

```PowerShell
Connect-MsolService
```

按 Enter 后，随即出现一个凭据对话框。 在Microsoft 365或Office 365输入用户名和密码，然后单击"确定"。

一旦连接到 Microsoft 365 或 Office 365，就可以运行以下命令以返回有关服务主体的信息：

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

下一步是导入、编码和分配 X.509 证书。 若要导入和编码证书，请使用以下Windows PowerShell命令，确保指定您的 完整文件路径。调用 Import 方法时 CER 文件：

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue) 
```

导入并编码证书后，可以将证书分配给您的证书Microsoft 365或Office 365服务主体。 为此，首先使用 Get-MsolServicePrincipal 检索 Skype for Business Server 和 Microsoft Exchange 服务主体的 AppPrincipalId 属性的值;AppPrincipalId 属性的值将用于标识要分配证书的服务主体。 使用 AppPrincipalId 属性值Skype for Business Server，使用以下命令将证书分配给 Skype For Business Online 版本：

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

然后，您应重复该命令，这次使用 Exchange 2013 的 AppPrincipalId 属性值。

如果您稍后需要删除该证书，例如，如果证书已过期，则可以通过先检索证书的 KeyId 来这样做：

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

除了分配证书之外，还必须配置 Exchange Online 服务主体，并将本地版本的 Skype for Business Server 外部 Web 服务 URL 配置为 Microsoft 365 或 Office 365 服务主体。 这可以通过执行以下两个命令完成。 

在下面的示例中，Pool1ExternalWebFQDN.contoso.com 池的外部 Web 服务 URL Skype for Business Server URL。 应重复这些步骤以在部署中添加所有外部 Web 服务 URL。

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
