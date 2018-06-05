---
title: 在 Skype for Business Server 2015 中配置混合环境
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 摘要： 配置混合环境中业务服务器 2015 Skype。
ms.openlocfilehash: 4798839bd001e6320870d7ca97ba99108e3b32de
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19570183"
---
# <a name="configure-a-hybrid-environment-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中配置混合环境
 
**摘要：** 配置混合环境中的业务服务器 2015 Skype。
  
在混合配置中，某些用户驻留在本地安装的 Skype 的业务服务器 2015年时其他用户都驻留在 Office 365 版本的 Skype 业务服务器。 要在混合环境中配置服务器到服务器身份验证，您必须首先配置业务服务器 2015 信任 Office 365 授权服务器的 Skype 您的本地的安装。 可以通过运行以下 Skype 业务 Server 命令行管理程序脚本来执行此过程中的初始步骤：
  
```
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
  
```
$TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId
```

脚本完成后，然后必须配置的业务服务器 2015 Skype 和授权服务器之间的信任关系和 Exchange 2013 和授权服务器之间的第二个信任关系。 这只能使用 Microsoft Online Services cmdlet 来完成。
  
> [!NOTE]
> 如果你尚未安装 Microsoft Online Services cmdlet，则你需要先完成两项操作，然后再继续。 首先，下载并安装 64 位版本的 Microsoft Online Services 登录助手。 安装完成后，下载并安装 Microsoft Online Services 模块用于 Windows PowerShell 的 64 位版本。 Office 365 网站上可找到的安装和使用 Microsoft Online Services 模块的详细的信息。 这些说明将还告诉您如何配置单一登录、 联盟和 Office 365 和 Active Directory 之间的同步。 
  
如果您未安装这些 cmdlet，您的脚本将失败，因为 Get-CsTenant cmdlet 不可用。
  
配置 Office 365 后和业务服务器 2015年和 Exchange 2013，都在服务主体的 Skype 创建 Office 365 后，您将需要使用这些服务主体注册您的凭据。 为此，您必须先获取另存为 .CER 文件的 X.509 Base64。 然后，此证书都将应用于 Office 365 服务主体。
  
当获取 X.509 证书时，启动 Microsoft Online Services 模块 （单击**开始**，单击**所有程序**，都单击**Microsoft Online Services**，然后都单击**Microsoft Online Services 模块 for WindowsPowerShell**)。 服务模块打开后，键入以下内容以导入 Microsoft Online Windows PowerShell 模块包含可用于管理的服务主体的 cmdlet:
  
```
Import-Module MSOnlineExtended
```

导入该模块后，键入以下命令并按 ENTER 以连接到 Office 365:
  
```
Connect-MsolService
```

按 Enter 后，随即出现一个凭据对话框。 在对话框中，输入您的 Office 365 用户名和密码，然后单击确定。
  
只要您连接到 Office 365，您可以然后运行以下命令来返回有关您的服务主体的信息：
  
```
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

下一步是导入、编码和分配 X.509 证书。 若要导入和编码证书，请使用以下 Windows PowerShell 命令，确保指定的完整文件路径您。CER 文件导入方法致电时：
  
```
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

导入证书并将其编码后，您然后可以将证书分配给您的 Office 365 服务主体。 为此，首先使用 Get-MsolServicePrincipal 业务服务器 Skype 和 Microsoft Exchange 服务主体; 检索 AppPrincipalId 属性的值AppPrincipalId 属性的值将用于标识其分配证书的服务主体。 AppPrincipalId 属性值的 Skype 业务服务器 2015年手中，使用以下命令业务服务器的证书分配给 Skype 的 Office 365 版本：
  
```
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

您然后应重复该命令，这次使用 Exchange 2013 的 AppPrincipalId 属性值。
  
如果您稍后需要删除该证书，可通过先检索证书的 KeyId 来执行此操作：
  
```
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
  
```
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

除了分配证书，您必须配置 Exchange Online 服务主体，并将您的本地版本的 Skype 业务服务器 2015年外部 Web 服务 url 配置为 Office 365 服务主体。 可通过执行下面两条命令达到此目的。 
  
以下示例中，在 lync.contoso.com 是业务服务器池的 Skype 的外部 Web 服务 URL。 您应重复这些步骤以添加在部署中的所有外部 Web 服务 Url。
  
```
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```