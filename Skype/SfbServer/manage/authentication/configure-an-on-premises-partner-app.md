---
title: 为 Skype for Business 服务器配置本地合作伙伴应用程序
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
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: 摘要：为 Skype for Business 服务器配置本地合作伙伴应用程序。
ms.openlocfilehash: 3f8aa3bfc7407ccf6409d00c540cfeab724913ab
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818824"
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server"></a><span data-ttu-id="f46ac-103">为 Skype for Business 服务器配置本地合作伙伴应用程序</span><span class="sxs-lookup"><span data-stu-id="f46ac-103">Configure an on-premises partner application for Skype for Business Server</span></span>
 
<span data-ttu-id="f46ac-104">**摘要：** 为 Skype for Business 服务器配置本地合作伙伴应用程序。</span><span class="sxs-lookup"><span data-stu-id="f46ac-104">**Summary:** Configure an on-premises partner application for Skype for Business Server.</span></span>
  
<span data-ttu-id="f46ac-105">分配 OAuthTokenIssuer 证书后，必须配置 Skype for Business Server 合作伙伴应用程序。</span><span class="sxs-lookup"><span data-stu-id="f46ac-105">After you have assigned the OAuthTokenIssuer certificate you must then configure your Skype for Business Server partner applications.</span></span> <span data-ttu-id="f46ac-106">（要讨论的过程将配置 Microsoft Exchange Server 2013 和 SharePoint 以充当合作伙伴应用程序，这是可选的。）若要配置本地合作伙伴应用程序，必须首先复制以下 Windows PowerShell 脚本，然后将代码粘贴到记事本（或任何其他文本编辑器）中：</span><span class="sxs-lookup"><span data-stu-id="f46ac-106">(The procedure about to be discussed configures both Microsoft Exchange Server 2013 and SharePoint to act as partner applications, which is optional.) To configure an on-premises partner application, you must start by copying the following Windows PowerShell script and pasting the code into Notepad (or any other text editor):</span></span>
  
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

<span data-ttu-id="f46ac-107">复制代码后，使用文件扩展名 .PS1（例如，C:\Scripts\ServerToServerAuth.ps1）保存脚本。</span><span class="sxs-lookup"><span data-stu-id="f46ac-107">After copying the code, save the script using a .PS1 file extension (for example, C:\Scripts\ServerToServerAuth.ps1).</span></span> <span data-ttu-id="f46ac-108">请注意，在运行此脚本之前，必须将元数据 Url https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1替换http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1为 Exchange 2013 和 SharePoint 服务器分别使用的元数据 url。</span><span class="sxs-lookup"><span data-stu-id="f46ac-108">Note that, before you run this script, you must replace the metadata URLs https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 and http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 with the metadata URLs used by your Exchange 2013 and SharePoint servers, respectively.</span></span> <span data-ttu-id="f46ac-109">有关如何识别相应产品的元数据 URL 的信息，请参阅 Exchange 2013 和 SharePoint 的产品文档。</span><span class="sxs-lookup"><span data-stu-id="f46ac-109">See the product documentation for Exchange 2013 and SharePoint for information on how you can identify the respective product's metadata URL.</span></span>
  
<span data-ttu-id="f46ac-110">如果查看脚本的最后一行，您将发现 Set-CsOAuthConfiguration cmdlet 是使用以下语法调用的：</span><span class="sxs-lookup"><span data-stu-id="f46ac-110">If you look at the last line of the script you will notice that the Set-CsOAuthConfiguration cmdlet is called using this syntax:</span></span>
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="f46ac-p103">由于调用 Set-CsOAuthConfiguration 时未使用 Realm 参数，因此会将领域自动设置为您组织的完全限定域名 (FQDN)（例如，litwareinc.com）。如果领域名称与组织名称不同，则应包括领域名称，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f46ac-p103">Because the Realm parameter was not used when calling Set-CsOAuthConfiguration the realm will automatically be set to the fully qualified domain name (FQDN) of your organization (for example, litwareinc.com). If your realm name is different from your organization name then you should include the realm name, like this:</span></span>
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

<span data-ttu-id="f46ac-113">进行这些更改之后，你可以执行该脚本，并将 Exchange 2013 和 SharePoint 配置为合作伙伴应用程序，方法是从 Skype for Business Server 命令行管理程序中运行脚本文件。</span><span class="sxs-lookup"><span data-stu-id="f46ac-113">After making these changes you can then execute the script, and configure both Exchange 2013 and SharePoint as partner applications, by running the script file from within the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="f46ac-114">例如：</span><span class="sxs-lookup"><span data-stu-id="f46ac-114">For example:</span></span>
  
```PowerShell
C:\Scripts\ServerToServerAuth.ps1
```

<span data-ttu-id="f46ac-115">请注意，即使你未安装 Exchange 2013 和 SharePoint Server，也可以运行此脚本：如果未安装 SharePoint Server，则不会出现任何问题。如果你未安装 SharePoint Server，则不会出现任何问题。</span><span class="sxs-lookup"><span data-stu-id="f46ac-115">Note that you can run this script even if you do not have both Exchange 2013 and SharePoint Server installed:, no problems will occur if you, say, configure SharePoint Server as a partner application even though you do not have SharePoint Server installed.</span></span>
  
<span data-ttu-id="f46ac-116">运行此脚本时，您可能会收到与以下内容类似的错误消息：</span><span class="sxs-lookup"><span data-stu-id="f46ac-116">When you run this script you might receive an error message similar to the following:</span></span>
  
```PowerShell
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

<span data-ttu-id="f46ac-p105">此错误消息通常指示以下两种情况之一：1) 在脚本中指定的某个 URL 无效（即，某个元数据 URL 不是实际的元数据 URL）；2) 无法联系某个元数据 URL。如果出现此情况，请验证 URL 是否正确且可访问，然后重新运行此脚本。</span><span class="sxs-lookup"><span data-stu-id="f46ac-p105">This error message typically means one of two things: 1) that one of the URLs specified in the script is not valid (that is, one of your metadata URLs is not an actual metadata URL); or, 2) one of the metadata URLs could not be contacted. If this happens, verify that the URLs are correct and are accessible, and the re-run the script.</span></span>
  
<span data-ttu-id="f46ac-119">为 Skype for Business 服务器创建合作伙伴应用程序后，必须随后将 Skype for business 服务器配置为 Exchange 2013 的合作伙伴应用程序。</span><span class="sxs-lookup"><span data-stu-id="f46ac-119">After creating the partner application for Skype for Business Server you must then configure Skype for Business Server to be a partner application for Exchange 2013.</span></span> <span data-ttu-id="f46ac-120">你可以通过运行脚本 Configure-EnterprisePartnerApplication 为 Exchange 2013 配置合作伙伴应用程序。您只需指定 Skype for business 服务器的元数据 URL，并指明 Skype for business 服务器是新的合作伙伴应用程序。</span><span class="sxs-lookup"><span data-stu-id="f46ac-120">You can configure partner applications for Exchange 2013 by running the script Configure-EnterprisePartnerApplication.ps1; all you need to do is specify the metadata URL for Skype for Business Server and indicate that Skype for Business Server is the new partner application.</span></span> 
  
<span data-ttu-id="f46ac-121">若要将 Skype for Business 服务器配置为 Exchange 的合作伙伴应用程序，请打开 Exchange 命令行管理程序并运行如下所示的命令</span><span class="sxs-lookup"><span data-stu-id="f46ac-121">To configure Skype for Business Server as a partner application for Exchange, open the Exchange Management Shell and run a command similar to this</span></span>
  
```PowerShell
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


