---
title: 为 Lync Server 2013 配置本地合作伙伴应用程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring an on-premises partner application for Lync Server 2013
ms:assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204975(v=OCS.15)
ms:contentKeyID: 48184412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c396415dd6bd3bda99254f30b0223f1ff672a01f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837292"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-an-on-premises-partner-application-for-microsoft-lync-server-2013"></a><span data-ttu-id="3bf9f-102">为 Microsoft Lync Server 2013 配置本地合作伙伴应用程序</span><span class="sxs-lookup"><span data-stu-id="3bf9f-102">Configuring an on-premises partner application for Microsoft Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3bf9f-103">_**主题上次修改时间:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="3bf9f-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="3bf9f-104">分配 OAuthTokenIssuer 证书后, 必须配置你的 Microsoft Lync Server 2013 合作伙伴应用程序。</span><span class="sxs-lookup"><span data-stu-id="3bf9f-104">After you have assigned the OAuthTokenIssuer certificate you must then configure your Microsoft Lync Server 2013 partner applications.</span></span> <span data-ttu-id="3bf9f-105">(讨论的过程将配置 Microsoft Exchange Server 2013 和 Microsoft SharePoint 以充当合作伙伴应用程序。)若要配置本地合作伙伴应用程序, 必须首先复制以下 Windows PowerShell 脚本, 然后将代码粘贴到记事本 (或任何其他文本编辑器) 中:</span><span class="sxs-lookup"><span data-stu-id="3bf9f-105">(The procedure about to be discussed configures both Microsoft Exchange Server 2013 and Microsoft SharePoint to act as partner applications.) To configure an on-premises partner application, you must start by copying the following Windows PowerShell script and pasting the code into Notepad (or any other text editor):</span></span>

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
      
                 New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx -ApplicationTrustLevel Full 
               }
            else
               {
                 Set-CsPartnerApplication -Identity microsoft.sharepoint -ApplicationTrustLevel Full 
                }
       }
    
    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="3bf9f-106">复制代码后, 使用将脚本保存。PS1 文件扩展名 (例如, C:\\Scripts\\ServerToServerAuth)。</span><span class="sxs-lookup"><span data-stu-id="3bf9f-106">After copying the code, save the script using a .PS1 file extension (for example, C:\\Scripts\\ServerToServerAuth.ps1).</span></span> <span data-ttu-id="3bf9f-107">请注意, 在运行此脚本之前, 必须将元数据 Url https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1替换http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx为 Exchange 2013 和 SharePoint 服务器分别使用的元数据 url。</span><span class="sxs-lookup"><span data-stu-id="3bf9f-107">Note that, before you run this script, you must replace the metadata URLs https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 and http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx with the metadata URLs used by your Exchange 2013 and SharePoint servers, respectively.</span></span> <span data-ttu-id="3bf9f-108">有关如何识别相应产品的元数据 URL 的信息, 请参阅 Exchange 2013 和 SharePoint 的产品文档。</span><span class="sxs-lookup"><span data-stu-id="3bf9f-108">See the product documentation for Exchange 2013 and SharePoint for information on how you can identify the respective product's metadata URL.</span></span>

<span data-ttu-id="3bf9f-109">如果查看脚本的最后一行，您将发现 Set-CsOAuthConfiguration cmdlet 是使用以下语法调用的：</span><span class="sxs-lookup"><span data-stu-id="3bf9f-109">If you look at the last line of the script you will notice that the Set-CsOAuthConfiguration cmdlet is called using this syntax:</span></span>

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="3bf9f-p103">由于调用 Set-CsOAuthConfiguration 时未使用 Realm 参数，因此会将领域自动设置为您组织的完全限定域名 (FQDN)（例如，litwareinc.com）。如果领域名称与组织名称不同，则应包括领域名称，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3bf9f-p103">Because the Realm parameter was not used when calling Set-CsOAuthConfiguration the realm will automatically be set to the fully qualified domain name (FQDN) of your organization (for example, litwareinc.com). If your realm name is different from your organization name then you should include the realm name, like this:</span></span>

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"

<span data-ttu-id="3bf9f-112">进行这些更改之后, 你可以执行脚本, 并通过 Lync Server 2013 管理外壳程序从 Lync Server 中运行脚本文件, 将 Exchange 2013 和 SharePoint 配置为合作伙伴应用程序。</span><span class="sxs-lookup"><span data-stu-id="3bf9f-112">After making these changes you can then execute the script, and configure both Exchange 2013 and SharePoint as partner applications, by running the script file from within the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="3bf9f-113">例如：</span><span class="sxs-lookup"><span data-stu-id="3bf9f-113">For example:</span></span>

    C:\Scripts\ServerToServerAuth.ps1

<span data-ttu-id="3bf9f-114">请注意, 即使你未安装 Exchange 2013 和 SharePoint Server, 也可以运行此脚本: 如果未安装 SharePoint Server, 则不会出现任何问题。如果你未安装 SharePoint Server, 则不会出现任何问题。</span><span class="sxs-lookup"><span data-stu-id="3bf9f-114">Note that you can run this script even if you do not have both Exchange 2013 and SharePoint Server installed:, no problems will occur if you, say, configure SharePoint Server as a partner application even though you do not have SharePoint Server installed.</span></span>

<span data-ttu-id="3bf9f-115">运行此脚本时，您可能会收到与以下内容类似的错误消息：</span><span class="sxs-lookup"><span data-stu-id="3bf9f-115">When you run this script you might receive an error message similar to the following:</span></span>

    New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."

<span data-ttu-id="3bf9f-p105">此错误消息通常指示以下两种情况之一：1) 在脚本中指定的某个 URL 无效（即，某个元数据 URL 不是实际的元数据 URL）；2) 无法联系某个元数据 URL。如果出现此情况，请验证 URL 是否正确且可访问，然后重新运行此脚本。</span><span class="sxs-lookup"><span data-stu-id="3bf9f-p105">This error message typically means one of two things: 1) that one of the URLs specified in the script is not valid (that is, one of your metadata URLs is not an actual metadata URL); or, 2) one of the metadata URLs could not be contacted. If this happens, verify that the URLs are correct and are accessible, and the re-run the script.</span></span>

<span data-ttu-id="3bf9f-118">为 Lync Server 2013 创建合作伙伴应用程序后, 必须随后将 Lync Server 配置为 Exchange 2013 的合作伙伴应用程序。</span><span class="sxs-lookup"><span data-stu-id="3bf9f-118">After creating the partner application for Lync Server 2013 you must then configure Lync Server to be a partner application for Exchange 2013.</span></span> <span data-ttu-id="3bf9f-119">你可以通过运行脚本 Configure-EnterprisePartnerApplication 为 Exchange 2013 配置合作伙伴应用程序。您只需指定 Lync Server 的元数据 URL, 并指明 Lync 服务器是新的合作伙伴应用程序。</span><span class="sxs-lookup"><span data-stu-id="3bf9f-119">You can configure partner applications for Exchange 2013 by running the script Configure-EnterprisePartnerApplication.ps1; all you need to do is specify the metadata URL for Lync Server and indicate that Lync Server is the new partner application.</span></span>

<span data-ttu-id="3bf9f-120">若要将 Lync Server 配置为 Exchange 的合作伙伴应用程序, 请打开 Exchange 命令行管理程序并运行如下所示的命令</span><span class="sxs-lookup"><span data-stu-id="3bf9f-120">To configure Lync Server as a partner application for Exchange, open the Exchange Management Shell and run a command similar to this</span></span>

    "c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://lync.contoso.com/metadata/json/1" -ApplicationType "Lync"

</div>

<span> </span>

</div>

</div>

</div>

