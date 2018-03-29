---
title: 配置 Skype for Business Server 2015 的本地合作伙伴应用程序
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: 摘要： 配置内部合作伙伴应用程序的业务服务器 2015 Skype。
ms.openlocfilehash: 4a31d97f7a4c2f717084c72cbc349c4f495597ea
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server-2015"></a>配置 Skype for Business Server 2015 的本地合作伙伴应用程序
 
**摘要：**配置业务服务器 2015 Skype 的合作伙伴应用程序内部。
  
分配 OAuthTokenIssuer 证书后您必须配置您 Skype 业务服务器 2015年合作伙伴应用程序。 （将要讨论的过程同时配置 Microsoft Exchange Server 2013年和 SharePoint 作为合作伙伴的应用程序，它是可选的。）若要配置内部合作伙伴应用程序，您必须启动复制以下 Windows PowerShell 脚本并将代码粘贴到记事本 （或任何其他文本编辑器）：
  
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

复制代码后，使用文件扩展名 .PS1（例如，C:\Scripts\ServerToServerAuth.ps1）保存脚本。 请注意，在运行该脚本之前，您必须替换元数据 Url https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 ，http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1与分别交换 2013年和 SharePoint 服务器，所使用的元数据 Url。 如何标识元数据 URL 各自的产品上看到信息交换 2013年和 SharePoint 的产品文档。
  
如果查看脚本的最后一行，您将发现 Set-CsOAuthConfiguration cmdlet 是使用以下语法调用的：
  
```
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

由于调用 Set-CsOAuthConfiguration 时未使用 Realm 参数，因此会将领域自动设置为您组织的完全限定域名 (FQDN)（例如，litwareinc.com）。如果领域名称与组织名称不同，则应包括领域名称，如下所示：
  
```
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

这些更改可以执行脚本，并通过业务服务器管理外壳程序运行在 Skype 的脚本文件配置为合作伙伴应用程序，Exchange 2013 和 SharePoint 后。 例如：
  
```
C:\Scripts\ServerToServerAuth.ps1
```

请注意，您可以运行此脚本，即使没有两个 Exchange 2013 和安装 SharePoint 服务器:，不会出现问题如果您，说，作为合作伙伴的应用程序配置 SharePoint 服务器，即使您没有安装 SharePoint 服务器。
  
运行此脚本时，您可能会收到与以下内容类似的错误消息：
  
```
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

此错误消息通常指示以下两种情况之一：1) 在脚本中指定的某个 URL 无效（即，某个元数据 URL 不是实际的元数据 URL）；2) 无法联系某个元数据 URL。如果出现此情况，请验证 URL 是否正确且可访问，然后重新运行此脚本。
  
创建业务服务器 2015 Skype 的合作伙伴应用程序后您必须配置为 Exchange 2013 的合作伙伴应用程序的业务服务器的 Skype。 您可以通过运行脚本配置-EnterprisePartnerApplication.ps1; 配置 Exchange 2013 的合作伙伴应用程序您需要做的就是 Skype 业务服务器指定的元数据 URL 并指示 Skype 业务服务器是新的合作伙伴应用程序。 
  
要配置 Skype 业务服务器作为合作伙伴应用程序用于交换，打开 Exchange 管理外壳程序，然后运行与以下类似的命令
  
```
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


