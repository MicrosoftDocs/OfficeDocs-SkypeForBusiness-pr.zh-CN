---
title: Microsoft Teams 中的数据位置
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: anach, kehardy
description: 在本文中，你将了解数据位于 Microsoft 团队中的地理位置。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c16065a864ac82cdf5f11c0d2c8254b648731cac
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121682"
---
# <a name="location-of-data-in-microsoft-teams"></a><span data-ttu-id="c1c3f-103">Microsoft Teams 中的数据位置</span><span class="sxs-lookup"><span data-stu-id="c1c3f-103">Location of data in Microsoft Teams</span></span>

<span data-ttu-id="c1c3f-104">团队中的数据位于与 Microsoft 365 或 Office 365 组织相关联的地理区域中。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-104">Data in Teams resides in the geographic region associated with your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="c1c3f-105">目前，团队支持澳大利亚、加拿大、法国、德国、印度、日本、南非、韩国、瑞士（包括列支敦士登）、阿拉伯联合酋长国、英国、美洲、APAC 和 EMEA 地区。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-105">Currently, Teams supports the Australia, Canada, France, Germany, India, Japan, South Africa, South Korea, Switzerland (which includes Liechtenstein), the United Arab Emirates, United Kingdom, Americas, APAC, and EMEA regions.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="c1c3f-106">团队目前在澳大利亚、加拿大、法国、德国、印度、日本、阿拉伯联合酋长国、英国、韩国、南非和瑞士（包括列支敦士登）中提供了新租户的数据常驻。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-106">Teams currently offers data residency in Australia, Canada, France, Germany, India, Japan, the United Arab Emirates, United Kingdom, South Korea, South Africa, and Switzerland (which includes Liechtenstein) for new tenants only.</span></span>
> <span data-ttu-id="c1c3f-107">新租户的定义是，该租户中没有任何一个用户登录过 Teams。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-107">A new tenant is defined as any tenant that hasn’t had a single user from the tenant sign in to Teams.</span></span> <span data-ttu-id="c1c3f-108">澳大利亚、印度、日本和韩国的现有租户将继续在 APAC 区域中存储其团队数据。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-108">Existing tenants from Australia, India, Japan, and South Korea will continue to have their Teams data stored in the APAC region.</span></span> <span data-ttu-id="c1c3f-109">加拿大的现有租户将继续将其数据存储在美洲。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-109">Existing tenants in Canada will continue to have their data stored in the Americas.</span></span> <span data-ttu-id="c1c3f-110">在法国、德国、列支敦士登、阿拉伯联合酋长国、英国、南非和瑞士的现有租户的数据将存储在 EMEA 地区。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-110">Existing tenants in France, Germany, Liechtenstein, the United Arab Emirates, the United Kingdom, South Africa, and Switzerland will have their data stored in the EMEA region.</span></span>

## <a name="where-your-teams-data-is-stored"></a><span data-ttu-id="c1c3f-111">存储团队数据的位置</span><span class="sxs-lookup"><span data-stu-id="c1c3f-111">Where your Teams data is stored</span></span>

<span data-ttu-id="c1c3f-112">若要查看哪个区域驻留你的租户的数据，请转到[Microsoft 365 管理中心](https://portal.office.com/adminportal/home)  >  **设置**  >  **组织配置文件**。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-112">To see which region houses data for your tenant, go to the [Microsoft 365 admin center](https://portal.office.com/adminportal/home) > **Settings** > **Organization profile**.</span></span> <span data-ttu-id="c1c3f-113">向下滚动到“**数据位置**”。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-113">Scroll down to **Data location**.</span></span>

![数据位置表的屏幕截图，其中包括管理中心中的团队](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="location-of-teams-data-at-rest"></a><span data-ttu-id="c1c3f-115">工作组数据的存放位置</span><span class="sxs-lookup"><span data-stu-id="c1c3f-115">Location of Teams data at rest</span></span>

<span data-ttu-id="c1c3f-116">团队数据的存储方式会有所不同，具体取决于内容类型。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-116">Your Teams data is stored differently depending on the content type.</span></span> 

![显示团队内容类型及其在其他位置存储的位置的图表](media/location-of-data-storage-at-rest.png)

<span data-ttu-id="c1c3f-118">查看[Microsoft 团队体系结构上的 Ignite 专题讨论](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071)可进行深入讨论。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-118">Check out the [Ignite breakout session on Microsoft Teams architecture](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071) for an in-depth discussion.</span></span>

### <a name="core-teams-customer-data"></a><span data-ttu-id="c1c3f-119">核心团队客户数据</span><span class="sxs-lookup"><span data-stu-id="c1c3f-119">Core Teams customer data</span></span>

<span data-ttu-id="c1c3f-120">如果你的租户在澳大利亚、加拿大、欧盟、法国、德国、印度、日本、南非、韩国、瑞士（包括列支敦士登）、阿拉伯联合酋长国、英国或美国均已预配，Microsoft 仅在该位置内将以下客户数据存储在其余位置：</span><span class="sxs-lookup"><span data-stu-id="c1c3f-120">If your tenant is provisioned in Australia, Canada, the European Union, France, Germany, India, Japan, South Africa, South Korea, Switzerland (which includes Liechtenstein), the United Arab Emirates, the United Kingdom, or the United States, Microsoft stores the following customer data at rest only within that location:</span></span>

- <span data-ttu-id="c1c3f-121">团队聊天、团队和频道对话、图像、语音邮件和联系人</span><span class="sxs-lookup"><span data-stu-id="c1c3f-121">Teams chats, team and channel conversations, images, voicemail messages, and contacts</span></span>
- <span data-ttu-id="c1c3f-122">SharePoint Online 网站内容和该网站中存储的文件</span><span class="sxs-lookup"><span data-stu-id="c1c3f-122">SharePoint Online site content and the files stored within that site</span></span>
- <span data-ttu-id="c1c3f-123">已上载到 OneDrive for business 的文件</span><span class="sxs-lookup"><span data-stu-id="c1c3f-123">Files uploaded to OneDrive for Business</span></span>

#### <a name="chat-channel-messages-team-structure"></a><span data-ttu-id="c1c3f-124">聊天、频道消息、团队结构</span><span class="sxs-lookup"><span data-stu-id="c1c3f-124">Chat, channel messages, team structure</span></span>

<span data-ttu-id="c1c3f-125">团队中的每个团队都由 Microsoft 365 组及其 SharePoint 网站和 Exchange 邮箱进行支持。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-125">Every team in Teams is backed by a Microsoft 365 Group and its SharePoint site and Exchange mailbox.</span></span> <span data-ttu-id="c1c3f-126">私人聊天（包括群组聊天）、在频道中作为对话的一部分发送的邮件以及团队和频道的结构存储在在 Azure 中运行的聊天服务中。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-126">Private chats (including group chats), messages sent as part of a conversation in a channel, and the structure of teams and channels are stored in a chat service running in Azure.</span></span> <span data-ttu-id="c1c3f-127">数据还存储在用户和组邮箱的隐藏文件夹中，以启用信息保护功能。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-127">The data is also stored in a hidden folder in the user and group mailboxes to enable Information Protection features.</span></span>

#### <a name="voicemail-and-contacts"></a><span data-ttu-id="c1c3f-128">语音邮件和联系人</span><span class="sxs-lookup"><span data-stu-id="c1c3f-128">Voicemail and contacts</span></span>

<span data-ttu-id="c1c3f-129">语音邮件存储在 Exchange 中。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-129">Voicemails are stored in Exchange.</span></span> <span data-ttu-id="c1c3f-130">联系人存储在基于 Exchange 的云数据存储中。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-130">Contacts are stored in Exchange-based cloud data store.</span></span> <span data-ttu-id="c1c3f-131">Exchange 和基于 Exchange 的云应用商店已在每个全球数据中心 geos 提供了数据派驻服务。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-131">Exchange and the Exchange-based cloud store already provide data residency in each of the worldwide datacenter geos.</span></span> <span data-ttu-id="c1c3f-132">对于所有团队，语音邮件和联系人均存储在国内、加拿大、法国、德国、印度、日本、阿拉伯联合酋长国、英国、南非、韩国、瑞士、瑞士（包括列支敦士登）和美国。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-132">For all teams, voicemail and contacts are stored in-country for Australia, Canada, France, Germany, India, Japan, the United Arab Emirates, the United Kingdom, South Africa, South Korea, Switzerland (includes Liechtenstein), and the United States.</span></span> <span data-ttu-id="c1c3f-133">对于所有其他国家/地区，文件基于租户相关性存储在美国、欧洲或亚太地区位置。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-133">For all other countries, files are stored in the US, Europe, or Asia-Pacific location based on tenant affinity.</span></span>

#### <a name="images-and-media"></a><span data-ttu-id="c1c3f-134">图像和媒体</span><span class="sxs-lookup"><span data-stu-id="c1c3f-134">Images and media</span></span>

<span data-ttu-id="c1c3f-135">聊天中使用的媒体（除不存储的 Giphy Gif 和指向原始 Giphy 服务 URL 的引用链接，Giphy 是非 Microsoft 服务）存储在与聊天服务部署到同一位置的基于 Azure 的媒体服务中。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-135">Media used in chats (except for Giphy GIFs which aren't stored but are a reference link to the original Giphy service URL, Giphy is a non-Microsoft service) is stored in an Azure-based media service that is deployed to the same locations as the chat service.</span></span>

#### <a name="files"></a><span data-ttu-id="c1c3f-136">文件</span><span class="sxs-lookup"><span data-stu-id="c1c3f-136">Files</span></span>

<span data-ttu-id="c1c3f-137">在频道中共享的文件（包括 OneNote 和 Wiki）存储在团队的 SharePoint 网站中。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-137">Files (including OneNote and Wiki) that somebody shares in a channel are stored in the team’s SharePoint site.</span></span> <span data-ttu-id="c1c3f-138">在会议或通话期间，在私人聊天或聊天中共享的文件将上载并存储在共享该文件的用户的商业帐户中。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-138">Files shared in a private chat or a chat during a meeting or call are uploaded and stored in the OneDrive for the Business account of the user who shares the file.</span></span> <span data-ttu-id="c1c3f-139">Exchange、SharePoint 和 OneDrive 已在每个全球数据中心 geos 提供了数据派驻服务。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-139">Exchange, SharePoint and OneDrive already provide data residency in each of the worldwide datacenter geos.</span></span> <span data-ttu-id="c1c3f-140">因此，对于现有客户，所有文件、OneNote 笔记本、团队 wiki 内容和属于团队体验的邮箱已存储在基于你的租户相关性的位置。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-140">So, for existing customers, all files, OneNote notebooks, Teams wiki content, and mailboxes that are part of the Teams experience are already stored in the location based on your tenant affinity.</span></span> <span data-ttu-id="c1c3f-141">文件存储在适用于澳大利亚、加拿大、法国、德国、印度、日本、阿拉伯联合酋长国、英国、南非、韩国和瑞士（包括列支敦士登）的国家/地区。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-141">Files are stored in-country for Australia, Canada, France, Germany, India, Japan, the United Arab Emirates, the United Kingdom, South Africa, South Korea, and Switzerland (which includes Liechtenstein).</span></span> <span data-ttu-id="c1c3f-142">对于所有其他国家/地区，文件基于租户相关性存储在美国、欧洲或亚太地区位置。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-142">For all other countries, files are stored in the US, Europe, or Asia Pacific location based on tenant affinity.</span></span>

### <a name="datacenter-locations"></a><span data-ttu-id="c1c3f-143">数据中心位置</span><span class="sxs-lookup"><span data-stu-id="c1c3f-143">Datacenter locations</span></span>

<span data-ttu-id="c1c3f-144">本部分中所述的团队服务将数据存储在以下位置中的其他位置：</span><span class="sxs-lookup"><span data-stu-id="c1c3f-144">The Teams services described in this section store data at rest in the following locations:</span></span>

|<span data-ttu-id="c1c3f-145">国家或地区</span><span class="sxs-lookup"><span data-stu-id="c1c3f-145">Country or region</span></span>  |<span data-ttu-id="c1c3f-146">数据中心位置</span><span class="sxs-lookup"><span data-stu-id="c1c3f-146">Datacenter location</span></span> |
|---------|---------|
|<span data-ttu-id="c1c3f-147">澳大利亚</span><span class="sxs-lookup"><span data-stu-id="c1c3f-147">Australia</span></span>   |<span data-ttu-id="c1c3f-148">新的南威尔士和维多利亚</span><span class="sxs-lookup"><span data-stu-id="c1c3f-148">New South Wales and Victoria</span></span>         |
|<span data-ttu-id="c1c3f-149">加拿大</span><span class="sxs-lookup"><span data-stu-id="c1c3f-149">Canada</span></span>    |<span data-ttu-id="c1c3f-150">魁北克城市和多伦多</span><span class="sxs-lookup"><span data-stu-id="c1c3f-150">Quebec City and Toronto</span></span>         |
|<span data-ttu-id="c1c3f-151">法国</span><span class="sxs-lookup"><span data-stu-id="c1c3f-151">France</span></span>    |<span data-ttu-id="c1c3f-152">Marseille 和巴黎</span><span class="sxs-lookup"><span data-stu-id="c1c3f-152">Marseille and Paris</span></span>         |
|<span data-ttu-id="c1c3f-153">德国</span><span class="sxs-lookup"><span data-stu-id="c1c3f-153">Germany</span></span>    |<span data-ttu-id="c1c3f-154">柏林和法兰克福</span><span class="sxs-lookup"><span data-stu-id="c1c3f-154">Berlin and Frankfurt</span></span>      |
|<span data-ttu-id="c1c3f-155">印度</span><span class="sxs-lookup"><span data-stu-id="c1c3f-155">India</span></span>   |<span data-ttu-id="c1c3f-156">金奈和 Pune</span><span class="sxs-lookup"><span data-stu-id="c1c3f-156">Chennai and Pune</span></span>        |
|<span data-ttu-id="c1c3f-157">日本</span><span class="sxs-lookup"><span data-stu-id="c1c3f-157">Japan</span></span>    |<span data-ttu-id="c1c3f-158">东京（Saitama）和大阪</span><span class="sxs-lookup"><span data-stu-id="c1c3f-158">Tokyo (Saitama) and Osaka</span></span>         |
|<span data-ttu-id="c1c3f-159">列支敦士登</span><span class="sxs-lookup"><span data-stu-id="c1c3f-159">Liechtenstein</span></span>   |<span data-ttu-id="c1c3f-160">日内瓦和苏黎世</span><span class="sxs-lookup"><span data-stu-id="c1c3f-160">Geneva and Zurich</span></span>       |
|<span data-ttu-id="c1c3f-161">南非</span><span class="sxs-lookup"><span data-stu-id="c1c3f-161">South Africa</span></span>     |<span data-ttu-id="c1c3f-162">约翰内斯堡和佛得角</span><span class="sxs-lookup"><span data-stu-id="c1c3f-162">Johannesburg and Cape Town</span></span>         |
|<span data-ttu-id="c1c3f-163">韩国</span><span class="sxs-lookup"><span data-stu-id="c1c3f-163">South Korea</span></span>     |<span data-ttu-id="c1c3f-164">首尔和 Busan</span><span class="sxs-lookup"><span data-stu-id="c1c3f-164">Seoul and Busan</span></span>         |
|<span data-ttu-id="c1c3f-165">瑞士</span><span class="sxs-lookup"><span data-stu-id="c1c3f-165">Switzerland</span></span>    |<span data-ttu-id="c1c3f-166">日内瓦和苏黎世</span><span class="sxs-lookup"><span data-stu-id="c1c3f-166">Geneva and Zurich</span></span>       |
|<span data-ttu-id="c1c3f-167">阿拉伯联合酋长国</span><span class="sxs-lookup"><span data-stu-id="c1c3f-167">United Arab Emirates</span></span>     |<span data-ttu-id="c1c3f-168">Abu Dhabi 和迪拜</span><span class="sxs-lookup"><span data-stu-id="c1c3f-168">Abu Dhabi and Dubai</span></span>         |
|<span data-ttu-id="c1c3f-169">英国</span><span class="sxs-lookup"><span data-stu-id="c1c3f-169">United Kingdom</span></span>     | <span data-ttu-id="c1c3f-170">加和伦敦</span><span class="sxs-lookup"><span data-stu-id="c1c3f-170">Cardiff and London</span></span>        |
|<span data-ttu-id="c1c3f-171">美洲–北部和南（AMER）</span><span class="sxs-lookup"><span data-stu-id="c1c3f-171">Americas – North, and South (AMER)</span></span> |<span data-ttu-id="c1c3f-172">Bay、CA 和 Boydton、VA</span><span class="sxs-lookup"><span data-stu-id="c1c3f-172">Bay, CA and Boydton, VA</span></span>       |
|<span data-ttu-id="c1c3f-173">亚太地区（APAC）</span><span class="sxs-lookup"><span data-stu-id="c1c3f-173">Asia Pacific (APAC)</span></span>  |<span data-ttu-id="c1c3f-174">新加坡和香港特别行政区</span><span class="sxs-lookup"><span data-stu-id="c1c3f-174">Singapore and Hong Kong</span></span>        |
|<span data-ttu-id="c1c3f-175">欧洲、中东和亚洲（EMEA）</span><span class="sxs-lookup"><span data-stu-id="c1c3f-175">Europe, Middle East, and Asia (EMEA)</span></span>   |<span data-ttu-id="c1c3f-176">都柏林和阿姆斯特丹</span><span class="sxs-lookup"><span data-stu-id="c1c3f-176">Dublin and Amsterdam</span></span>        |

> [!NOTE]
> <span data-ttu-id="c1c3f-177">对于列支敦士登，数据存储在日内瓦和苏黎世的瑞士数据中心中的其他位置。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-177">For Liechtenstein, data is stored at rest in the Switzerland data centers in Geneva and Zurich.</span></span>

### <a name="data-stored-with-a-third-party-storage-provider"></a><span data-ttu-id="c1c3f-178">与第三方存储提供商存储的数据</span><span class="sxs-lookup"><span data-stu-id="c1c3f-178">Data stored with a third-party storage provider</span></span>

<span data-ttu-id="c1c3f-179">允许用户使用第三方存储提供程序存储文件的组织依赖于这些服务的存储位置，因此应单独查看这些服务的剩余数据位置。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-179">Organizations who allow users to store files with a third-party storage provider are dependent on the storage location of those services and should, therefore, review the location of data at rest for those services separately.</span></span>

- <span data-ttu-id="c1c3f-180">**选项卡**：选项卡允许用户将应用和服务中的信息固定到频道。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-180">**Tabs**: Tabs allow users to pin information from apps and services to a channel.</span></span> <span data-ttu-id="c1c3f-181">因此，它会因存储数据的选项卡的类型而异。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-181">Thus, it varies by type of the tab where the data is stored.</span></span> <span data-ttu-id="c1c3f-182">选项卡本身不存储任何数据。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-182">The tab itself doesn't store any data.</span></span> <span data-ttu-id="c1c3f-183">例如，SharePoint 选项卡将根据 SharePoint 网站集的预配位置存储数据。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-183">For example, a SharePoint tab will store data based on where the SharePoint site collection was provisioned.</span></span> <span data-ttu-id="c1c3f-184">包括来自合作伙伴的信息的选项卡将直接存储在合作伙伴使用的系统中的数据，并仅显示该数据的视图。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-184">A tab that includes information from a partner will store the data directly in the system used by the partner and only present a view of it.</span></span>
- <span data-ttu-id="c1c3f-185">**其他合作伙伴应用**： Microsoft 不会为你可能在团队体验中使用的合作伙伴提供对应用和服务的任何数据派驻支持。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-185">**Other partner apps**: Microsoft doesn't provide any data residency support for apps and services from partners that you might be using within the Teams experience.</span></span> <span data-ttu-id="c1c3f-186">直接查看这些解决方案中的信息，了解存储其数据的位置。</span><span class="sxs-lookup"><span data-stu-id="c1c3f-186">Review information from those solutions directly to learn about where their data is being stored.</span></span>

## <a name="see-also"></a><span data-ttu-id="c1c3f-187">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c1c3f-187">See also</span></span>

- [<span data-ttu-id="c1c3f-188">Microsoft 团队启动阿拉伯联合酋长国数据派驻服务</span><span class="sxs-lookup"><span data-stu-id="c1c3f-188">Microsoft Teams launches United Arab Emirates Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-United-Arab-Emirates-Data-Residency/ba-p/980330)

- [<span data-ttu-id="c1c3f-189">Microsoft 团队启动南亚韩文数据派驻服务</span><span class="sxs-lookup"><span data-stu-id="c1c3f-189">Microsoft Teams launches South Korean Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Korea-Data-Residency/ba-p/789171)

- [<span data-ttu-id="c1c3f-190">Microsoft 团队启动南非数据派驻服务</span><span class="sxs-lookup"><span data-stu-id="c1c3f-190">Microsoft Teams launches South African Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Africa-Data-Residency/ba-p/776611)

- [<span data-ttu-id="c1c3f-191">Microsoft 团队启动法国数据派驻服务</span><span class="sxs-lookup"><span data-stu-id="c1c3f-191">Microsoft Teams Launches France Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-France-Data-Residency/ba-p/364466)

- [<span data-ttu-id="c1c3f-192">Microsoft 团队启动印度数据派驻服务，即将推出其他 geos</span><span class="sxs-lookup"><span data-stu-id="c1c3f-192">Microsoft Teams launches India Data Residency, other geos coming soon</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-India-Data-Residency-other-geos-coming/ba-p/154083)

- [<span data-ttu-id="c1c3f-193">Microsoft 团队启动澳大利亚和日本数据派驻服务</span><span class="sxs-lookup"><span data-stu-id="c1c3f-193">Microsoft Teams Launches Australia and Japan Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827)

- [<span data-ttu-id="c1c3f-194">Microsoft 团队启动加拿大数据派驻、澳大利亚和日本即将推出</span><span class="sxs-lookup"><span data-stu-id="c1c3f-194">Microsoft Teams Launches Canada Data Residency, Australia and Japan coming soon</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178)
