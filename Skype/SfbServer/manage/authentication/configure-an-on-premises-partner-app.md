---
title: 为部署环境配置本地合作伙伴Skype for Business Server
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
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: 摘要：为本地合作伙伴应用程序配置Skype for Business Server。
ms.openlocfilehash: d0907d73d6a23c0a5b9a1f1725503b72c5bce993
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012616"
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server"></a>为部署环境配置本地合作伙伴Skype for Business Server
 
**摘要：** 为本地合作伙伴应用程序配置Skype for Business Server。
  
分配 OAuthTokenIssuer 证书后，您必须配置您的Skype for Business Server应用程序。  (即将讨论的过程将 Microsoft Exchange Server 2013 和 SharePoint 配置为充当合作伙伴应用程序（可选）。) 若要配置本地合作伙伴应用程序，首先必须复制以下 Windows PowerShell 脚本，将代码粘贴到 记事本 (或任何其他文本编辑器) ：
  
```PowerShell
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

复制代码后，使用文件扩展名 .PS1（例如，C:\Scripts\ServerToServerAuth.ps1）保存脚本。 请注意，在运行此脚本之前，您必须分别将元数据 URL 和 `https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1` `http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1` Exchange 2013 和 SharePoint 使用的元数据 URL。 请参阅 Exchange 2013 和 SharePoint 产品文档，了解如何标识各自的产品的元数据 URL。
  
如果查看脚本的最后一行，您将发现 Set-CsOAuthConfiguration cmdlet 是使用以下语法调用的：
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

由于调用 Set-CsOAuthConfiguration 时未使用 Realm 参数，因此会将领域自动设置为您组织的完全限定域名 (FQDN)（例如，litwareinc.com）。如果领域名称与组织名称不同，则应包括领域名称，如下所示：
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

进行这些更改后，可以通过从 Skype for Business Server 命令行管理程序中运行脚本文件来执行脚本，然后将 Exchange 2013 和 SharePoint 配置为合作伙伴应用程序。 例如：
  
```PowerShell
C:\Scripts\ServerToServerAuth.ps1
```

请注意，即使未同时安装 Exchange 2013 和 SharePoint Server：，也可以运行此脚本，如果您将 SharePoint Server 配置为合作伙伴应用程序，则不会发生任何问题，即使未安装 SharePoint Server。
  
运行此脚本时，您可能会收到与以下内容类似的错误消息：
  
```PowerShell
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

此错误消息通常指示以下两种情况之一：1) 在脚本中指定的某个 URL 无效（即，某个元数据 URL 不是实际的元数据 URL）；2) 无法联系某个元数据 URL。如果出现此情况，请验证 URL 是否正确且可访问，然后重新运行此脚本。
  
为 Skype for Business Server 创建合作伙伴应用程序后Skype for Business Server必须配置为 Exchange 2013 的合作伙伴应用程序。 可以通过运行脚本代码为 Exchange 2013 配置Configure-EnterprisePartnerApplication.ps1;你只需指定应用程序的元数据 URL Skype for Business Server并指示Skype for Business Server是新的合作伙伴应用程序。 
  
若要将 Skype for Business Server 配置为 Exchange 的合作伙伴应用程序，请打开 Exchange 命令行管理程序并运行类似如下的命令
  
```PowerShell
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


