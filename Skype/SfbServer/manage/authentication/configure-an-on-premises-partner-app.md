---
title: 配置内部部署合作伙伴应用程序的 Skype 业务服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: 摘要： 配置内部部署合作伙伴应用程序的 Skype 业务服务器。
ms.openlocfilehash: a13157d590d6cdd067ed2a0a717fd744adb9de4f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913375"
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server"></a>配置内部部署合作伙伴应用程序的 Skype 业务服务器
 
**摘要：** 为业务服务器的 Skype 配置内部部署合作伙伴应用程序。
  
分配 OAuthTokenIssuer 证书后，您必须然后配置您 Skype Business Server 合作伙伴应用程序。 （即将要讨论的过程同时配置 Microsoft Exchange Server 2013 和 SharePoint 作为合作伙伴应用程序，它是可选。）若要配置内部部署合作伙伴应用程序，您必须首先复制以下 Windows PowerShell 脚本并粘贴到记事本 （或任何其他文本编辑器） 的代码：
  
```
if ((Get-CsPartnerApplication -ErrorAction SilentlyContinue) -ne $Null)
   {
       Remove-CsPartnerApplication app
   }

$exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue
        
if ($exch -eq $null)
   {
      New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
    }
else
    {
       if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
          {
             Remove-CsPartnerApplication microsoft.exchange
New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
           }
        else
           {
             Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full 
           }
     }

$shp = Get-CsPartnerApplication microsoft.sharepoint -ErrorAction SilentlyContinue
        
if ($shp -eq $null)
   {
      New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx -ApplicationTrustLevel Full 
    }
else
    {
       if ($shp.ApplicationIdentifier -ne "00000003-0000-0ff1-ce00-000000000000")
          {
             Remove-CsPartnerApplication microsoft.sharepoint
  
             New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl https://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 -ApplicationTrustLevel Full 
           }
        else
           {
             Set-CsPartnerApplication -Identity microsoft.sharepoint -ApplicationTrustLevel Full 
            }
   }

Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

复制代码后，使用文件扩展名 .PS1（例如，C:\Scripts\ServerToServerAuth.ps1）保存脚本。 请注意，在运行此脚本之前，您必须替换的元数据 Urlhttps://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1和http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1与分别使用您的 Exchange 2013 和 SharePoint 服务器的元数据 Url。 在您如何识别各自的产品的元数据 URL，请参阅 Exchange 2013 和 SharePoint 产品文档的信息。
  
如果查看脚本的最后一行，您将发现 Set-CsOAuthConfiguration cmdlet 是使用以下语法调用的：
  
```
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

由于调用 Set-CsOAuthConfiguration 时未使用 Realm 参数，因此会将领域自动设置为您组织的完全限定域名 (FQDN)（例如，litwareinc.com）。如果领域名称与组织名称不同，则应包括领域名称，如下所示：
  
```
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

这些更改后可以执行脚本，并通过运行 Business Server Management Shell 脚本文件从 Skype 配置合作伙伴应用程序，为 Exchange 2013 和 SharePoint。 例如：
  
```
C:\Scripts\ServerToServerAuth.ps1
```

请注意，即使您没有这两个 Exchange 2013 和 SharePoint Server 安装，您可以运行此脚本:，不会出现问题如果您说，将 SharePoint Server 配置为合作伙伴应用程序，即使您没有安装 SharePoint Server。
  
运行此脚本时，您可能会收到与以下内容类似的错误消息：
  
```
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

此错误消息通常指示以下两种情况之一：1) 在脚本中指定的某个 URL 无效（即，某个元数据 URL 不是实际的元数据 URL）；2) 无法联系某个元数据 URL。如果出现此情况，请验证 URL 是否正确且可访问，然后重新运行此脚本。
  
创建合作伙伴应用程序的 Skype 业务服务器后，您必须然后配置业务合作伙伴应用程序的 Exchange 2013 服务器的 Skype。 您可以通过运行该脚本 Configure-EnterprisePartnerApplication.ps1; 配置 Exchange 2013 的合作伙伴应用程序您需要执行所有是指定的元数据 URL 的 Skype 业务服务器并指示 Skype 业务服务器是新合作伙伴应用程序。 
  
若要配置 Skype 业务服务器的合作伙伴应用程序 exchange，打开 Exchange Management Shell 并运行类似如下的命令
  
```
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


