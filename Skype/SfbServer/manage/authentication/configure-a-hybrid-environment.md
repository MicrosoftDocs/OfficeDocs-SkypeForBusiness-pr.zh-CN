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
description: 摘要： 在混合环境中配置业务服务器 2015年的 Skype。
ms.openlocfilehash: e31338647338854b260c9f8935cac4dde69df490
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-a-hybrid-environment-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中配置混合环境
 
**摘要：**在混合环境中配置业务服务器 2015 Skype。
  
在混合配置中，您的部分用户托管内部安装的 Skype 上的业务服务器 2015年时其他用户业务服务器托管在 Skype 的 Office 365 版本。 为了在混合环境中配置服务器到服务器的身份验证，您必须首先配置 Skype 业务服务器 2015 信任 Office 365 授权服务器用于内部部署安装。 可以通过运行下面的 Skype 业务服务器管理外壳脚本执行此过程的初始步骤：
  
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

脚本执行完毕后，您必须配置业务服务器 2015年的 Skype 和授权服务器之间的信任关系和第二个 Exchange 2013 和授权服务器之间信任关系。 这只能使用 Microsoft Online Services cmdlet 来完成。
  
> [!NOTE]
> 如果你尚未安装 Microsoft Online Services cmdlet，则你需要先完成两项操作，然后再继续。 首先，下载并安装 64 位版本的 Microsoft Online Services 登录助手。 安装完成后，下载并安装 Microsoft Online Services 模块用于 Windows PowerShell 的 64 位版本。 Office 365 网站上找不到安装并使用 Microsoft Online Services 模块的详细的信息。 这些说明将还告诉您如何配置单一登录、 联盟和 Office 365 和 Active Directory 之间的同步。 
  
如果您未安装这些 cmdlet，您的脚本将失败，因为 Get-CsTenant cmdlet 不可用。
  
您已配置了 Office 365 之后，创建之后，Office 365 的 Skype 的服务主体业务服务器 2015年和 Exchange 2013，然后需要使用这些服务主体注册您的凭据。 为此，您必须先获取另存为 .CER 文件的 X.509 Base64。 此证书将应用到 Office 365 服务主体。
  
当您获得 X.509 证书时，启动 Microsoft Online Services 模块 （单击**开始**，单击**所有程序**，都单击**Microsoft Online Services**，然后都单击**Microsoft Online Services 模块 WindowsPowerShell**)。 打开服务模块后，键入以下命令以导入包含可用于管理服务主体的 cmdlet 的 Microsoft 在线 Windows PowerShell 模块：
  
```
Import-Module MSOnlineExtended
```

导入模块之后，键入以下命令，然后才能连接到 Office 365 中按 enter 键：
  
```
Connect-MsolService
```

按 Enter 后，随即出现一个凭据对话框。 在对话框中，输入您的 Office 365 用户名和密码，然后单击确定。
  
一旦您连接到 Office 365，然后，可以运行下面的命令来返回服务主体有关的信息：
  
```
Get-MsolServicePrincipal
```

您应获得与以下信息类似的所有服务主体的相关信息：
  
```
ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
AccountEnabled       : True
Addresses            : {}
AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
DisplayName          : Skype for Business Server
ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
ServicePrincipalName : SkypeForBusinessServer/litwareinc.com
TrustedForDelegation : True
```

下一步是导入、编码和分配 X.509 证书。 导入并编码证书，请使用以下 Windows PowerShell 命令，确保指定的文件完整路径您。CER 文件调用导入方法时：
  
```
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

导入证书并将其编码后，可以再将证书分配到您的 Office 365 服务主体。 要做到这一点，首先使用 Get MsolServicePrincipal 业务服务器的 Skype 和 Microsoft Exchange 服务主体; 检索 AppPrincipalId 属性的值AppPrincipalId 属性的值将用于标识分配证书服务主体。 AppPrincipalId 属性的值为 Skype 业务服务器 2015年手中，使用下面的命令将证书给 Office 365 份 Skype 业务服务器：
  
```
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

您应该使用 AppPrincipalId 属性值交换 2013年这次重复的命令。
  
如果您稍后需要删除该证书，可通过先检索证书的 KeyId 来执行此操作：
  
```
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

此命令将返回与以下内容类似的数据：
  
```
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
```

然后，您可以使用与以下内容类似的命令删除该证书：
  
```
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

除了分配一个证书，还必须配置 Exchange 的联机服务主体和作为 Office 365 服务主体业务服务器 2015年的外部 Web 服务 Url 配置您的 Skype 的内部部署版本。 可通过执行下面两条命令达到此目的。 
  
在以下示例中，lync.contoso.com 是业务服务器池 Skype 的外部 Web 服务 URL。 应重复上述步骤以添加部署中的所有外部 Web 服务 Url。
  
```
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true

$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```