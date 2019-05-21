---
title: 为 Skype for Business 服务器配置本地合作伙伴应用程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: '摘要: 为 Skype for Business 服务器配置本地合作伙伴应用程序。'
ms.openlocfilehash: 9cd6272b164a6c7fa42430905127b38c5acbc7be
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285517"
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server"></a>为 Skype for Business 服务器配置本地合作伙伴应用程序
 
**摘要:** 为 Skype for Business 服务器配置本地合作伙伴应用程序。
  
分配 OAuthTokenIssuer 证书后, 必须配置 Skype for Business Server 合作伙伴应用程序。 (要讨论的过程将配置 Microsoft Exchange Server 2013 和 SharePoint 以充当合作伙伴应用程序, 这是可选的。)若要配置本地合作伙伴应用程序, 必须首先复制以下 Windows PowerShell 脚本, 然后将代码粘贴到记事本 (或任何其他文本编辑器) 中:
  
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

复制代码后，使用文件扩展名 .PS1（例如，C:\Scripts\ServerToServerAuth.ps1）保存脚本。 请注意, 在运行此脚本之前, 必须将元数据 Url https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1替换http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1为 Exchange 2013 和 SharePoint 服务器分别使用的元数据 url。 有关如何识别相应产品的元数据 URL 的信息, 请参阅 Exchange 2013 和 SharePoint 的产品文档。
  
如果查看脚本的最后一行，您将发现 Set-CsOAuthConfiguration cmdlet 是使用以下语法调用的：
  
```
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

由于调用 Set-CsOAuthConfiguration 时未使用 Realm 参数，因此会将领域自动设置为您组织的完全限定域名 (FQDN)（例如，litwareinc.com）。如果领域名称与组织名称不同，则应包括领域名称，如下所示：
  
```
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

进行这些更改之后, 你可以执行该脚本, 并将 Exchange 2013 和 SharePoint 配置为合作伙伴应用程序, 方法是从 Skype for Business Server 命令行管理程序中运行脚本文件。 例如：
  
```
C:\Scripts\ServerToServerAuth.ps1
```

请注意, 即使你未安装 Exchange 2013 和 SharePoint Server, 也可以运行此脚本: 如果未安装 SharePoint Server, 则不会出现任何问题。如果你未安装 SharePoint Server, 则不会出现任何问题。
  
运行此脚本时，您可能会收到与以下内容类似的错误消息：
  
```
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

此错误消息通常指示以下两种情况之一：1) 在脚本中指定的某个 URL 无效（即，某个元数据 URL 不是实际的元数据 URL）；2) 无法联系某个元数据 URL。如果出现此情况，请验证 URL 是否正确且可访问，然后重新运行此脚本。
  
为 Skype for Business 服务器创建合作伙伴应用程序后, 必须随后将 Skype for business 服务器配置为 Exchange 2013 的合作伙伴应用程序。 你可以通过运行脚本 Configure-EnterprisePartnerApplication 为 Exchange 2013 配置合作伙伴应用程序。您只需指定 Skype for business 服务器的元数据 URL, 并指明 Skype for business 服务器是新的合作伙伴应用程序。 
  
若要将 Skype for Business 服务器配置为 Exchange 的合作伙伴应用程序, 请打开 Exchange 命令行管理程序并运行如下所示的命令
  
```
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


