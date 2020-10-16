---
title: Microsoft Teams 中的数据位置
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: anach, kehardy
description: 在本文中，你将了解这些数据在 Microsoft Teams 中的地理位置。
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
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121682"
---
# <a name="location-of-data-in-microsoft-teams"></a><span data-ttu-id="d4546-103">Microsoft Teams 中的数据位置</span><span class="sxs-lookup"><span data-stu-id="d4546-103">Location of data in Microsoft Teams</span></span>

<span data-ttu-id="d4546-104">Teams 中的数据位于与 Microsoft 365 或 Office 365 组织关联的地理区域中。</span><span class="sxs-lookup"><span data-stu-id="d4546-104">Data in Teams resides in the geographic region associated with your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="d4546-105">目前，Teams 支持澳大利亚、加拿大、法国、德国、印度、日本、南非、韩国、瑞士（包括列支敦士登）、阿拉伯联合酋长国、英国、美洲、亚太地区和欧洲、中东和非洲地区。</span><span class="sxs-lookup"><span data-stu-id="d4546-105">Currently, Teams supports the Australia, Canada, France, Germany, India, Japan, South Africa, South Korea, Switzerland (which includes Liechtenstein), the United Arab Emirates, United Kingdom, Americas, APAC, and EMEA regions.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="d4546-106">Teams 目前只为新租户提供澳大利亚、加拿大、法国、德国、印度、日本、阿拉伯联合酋长国、英国、韩国、南非和瑞士（包括列支敦士登）的数据驻留。</span><span class="sxs-lookup"><span data-stu-id="d4546-106">Teams currently offers data residency in Australia, Canada, France, Germany, India, Japan, the United Arab Emirates, United Kingdom, South Korea, South Africa, and Switzerland (which includes Liechtenstein) for new tenants only.</span></span>
> <span data-ttu-id="d4546-107">新的租户被定义为任何未从租户中的单个用户登录 Teams 的租户。</span><span class="sxs-lookup"><span data-stu-id="d4546-107">A new tenant is defined as any tenant that hasn’t had a single user from the tenant sign in to Teams.</span></span> <span data-ttu-id="d4546-108">来自澳大利亚、印度、日本和韩国的现有租户将继续将其 Teams 数据存储在亚太地区。</span><span class="sxs-lookup"><span data-stu-id="d4546-108">Existing tenants from Australia, India, Japan, and South Korea will continue to have their Teams data stored in the APAC region.</span></span> <span data-ttu-id="d4546-109">加拿大的现有租户将继续将其数据存储在美国。</span><span class="sxs-lookup"><span data-stu-id="d4546-109">Existing tenants in Canada will continue to have their data stored in the Americas.</span></span> <span data-ttu-id="d4546-110">法国、德国、列支敦士登、阿拉伯联合酋长国、英国、南非和瑞士的现有租户的数据将存储在欧洲、中东和非洲 (EMEA) 地区。</span><span class="sxs-lookup"><span data-stu-id="d4546-110">Existing tenants in France, Germany, Liechtenstein, the United Arab Emirates, the United Kingdom, South Africa, and Switzerland will have their data stored in the EMEA region.</span></span>

## <a name="where-your-teams-data-is-stored"></a><span data-ttu-id="d4546-111">你的 Teams 数据的存储位置</span><span class="sxs-lookup"><span data-stu-id="d4546-111">Where your Teams data is stored</span></span>

<span data-ttu-id="d4546-112">要查看哪些区域托管你的租户数据，请转到 [Microsoft 365 管理中心](https://portal.office.com/adminportal/home) > “**设置**” > “**组织配置文件**”。</span><span class="sxs-lookup"><span data-stu-id="d4546-112">To see which region houses data for your tenant, go to the [Microsoft 365 admin center](https://portal.office.com/adminportal/home) > **Settings** > **Organization profile**.</span></span> <span data-ttu-id="d4546-113">向下滚动到**数据位置**。</span><span class="sxs-lookup"><span data-stu-id="d4546-113">Scroll down to **Data location**.</span></span>

![包含管理中心中的 Teams 的数据位置表的屏幕截图](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="location-of-teams-data-at-rest"></a><span data-ttu-id="d4546-115">Teams 静态数据的位置</span><span class="sxs-lookup"><span data-stu-id="d4546-115">Location of Teams data at rest</span></span>

<span data-ttu-id="d4546-116">Teams 数据的存储方式将有所不同，具体取决于内容类型。</span><span class="sxs-lookup"><span data-stu-id="d4546-116">Your Teams data is stored differently depending on the content type.</span></span> 

![显示 Teams 内容类型及其静态存储位置的图表](media/location-of-data-storage-at-rest.png)

<span data-ttu-id="d4546-118">查看有关 [Microsoft Teams 体系结构的 Ignite 分组讨论](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071)，以进行深入讨论。</span><span class="sxs-lookup"><span data-stu-id="d4546-118">Check out the [Ignite breakout session on Microsoft Teams architecture](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071) for an in-depth discussion.</span></span>

### <a name="core-teams-customer-data"></a><span data-ttu-id="d4546-119">核心 Teams 客户数据</span><span class="sxs-lookup"><span data-stu-id="d4546-119">Core Teams customer data</span></span>

<span data-ttu-id="d4546-120">如果您的租户位于澳大利亚、加拿大、欧盟、法国、德国、印度、日本、南非、韩国、瑞士（包括列支敦士登）、阿拉伯联合酋长国、英国或美国，则 Microsoft 仅在该位置存储以下客户数据：</span><span class="sxs-lookup"><span data-stu-id="d4546-120">If your tenant is provisioned in Australia, Canada, the European Union, France, Germany, India, Japan, South Africa, South Korea, Switzerland (which includes Liechtenstein), the United Arab Emirates, the United Kingdom, or the United States, Microsoft stores the following customer data at rest only within that location:</span></span>

- <span data-ttu-id="d4546-121">Teams 聊天、团队和频道对话、图像、语音邮件和联系人</span><span class="sxs-lookup"><span data-stu-id="d4546-121">Teams chats, team and channel conversations, images, voicemail messages, and contacts</span></span>
- <span data-ttu-id="d4546-122">SharePoint Online 网站内容和存储在该网站中的文件</span><span class="sxs-lookup"><span data-stu-id="d4546-122">SharePoint Online site content and the files stored within that site</span></span>
- <span data-ttu-id="d4546-123">上传到 OneDrive for Business 的文件</span><span class="sxs-lookup"><span data-stu-id="d4546-123">Files uploaded to OneDrive for Business</span></span>

#### <a name="chat-channel-messages-team-structure"></a><span data-ttu-id="d4546-124">聊天，频道消息，团队结构</span><span class="sxs-lookup"><span data-stu-id="d4546-124">Chat, channel messages, team structure</span></span>

<span data-ttu-id="d4546-125">Teams 中的每个团队都由 Microsoft 365 组及其 SharePoint 站点和 Exchange 邮箱支持。</span><span class="sxs-lookup"><span data-stu-id="d4546-125">Every team in Teams is backed by a Microsoft 365 Group and its SharePoint site and Exchange mailbox.</span></span> <span data-ttu-id="d4546-126">私密聊天（包括群组聊天）、在频道中作为会话一部分发送的消息以及团队和频道的结构都存储在运行于 Azure 的聊天服务中。</span><span class="sxs-lookup"><span data-stu-id="d4546-126">Private chats (including group chats), messages sent as part of a conversation in a channel, and the structure of teams and channels are stored in a chat service running in Azure.</span></span> <span data-ttu-id="d4546-127">数据还存储在用户和组邮箱中的隐藏文件夹中，以启用信息保护功能。</span><span class="sxs-lookup"><span data-stu-id="d4546-127">The data is also stored in a hidden folder in the user and group mailboxes to enable Information Protection features.</span></span>

#### <a name="voicemail-and-contacts"></a><span data-ttu-id="d4546-128">语音邮件和联系人</span><span class="sxs-lookup"><span data-stu-id="d4546-128">Voicemail and contacts</span></span>

<span data-ttu-id="d4546-129">语音邮件存储在 Exchange 中。</span><span class="sxs-lookup"><span data-stu-id="d4546-129">Voicemails are stored in Exchange.</span></span> <span data-ttu-id="d4546-130">联系人存储在基于 Exchange 的云数据存储中。</span><span class="sxs-lookup"><span data-stu-id="d4546-130">Contacts are stored in Exchange-based cloud data store.</span></span> <span data-ttu-id="d4546-131">Exchange 和基于 Exchange 的云存储已在全球每个数据中心地理位置提供数据驻留。</span><span class="sxs-lookup"><span data-stu-id="d4546-131">Exchange and the Exchange-based cloud store already provide data residency in each of the worldwide datacenter geos.</span></span> <span data-ttu-id="d4546-132">对于所有团队，语音信箱和联系人存储在澳大利亚、加拿大、法国、德国、印度、日本、阿拉伯联合酋长国、英国、南非、韩国、瑞士（包括列支敦士登）和美国的国家/地区。</span><span class="sxs-lookup"><span data-stu-id="d4546-132">For all teams, voicemail and contacts are stored in-country for Australia, Canada, France, Germany, India, Japan, the United Arab Emirates, the United Kingdom, South Africa, South Korea, Switzerland (includes Liechtenstein), and the United States.</span></span> <span data-ttu-id="d4546-133">对于所有其他国家/地区，基于租户相关性，文件存储在美国、欧洲或亚太地区。</span><span class="sxs-lookup"><span data-stu-id="d4546-133">For all other countries, files are stored in the US, Europe, or Asia-Pacific location based on tenant affinity.</span></span>

#### <a name="images-and-media"></a><span data-ttu-id="d4546-134">图像和媒体</span><span class="sxs-lookup"><span data-stu-id="d4546-134">Images and media</span></span>

<span data-ttu-id="d4546-135">聊天中使用的媒体（Giphy GIF 除外，它没有被存储，但是指向原始 Giphy 服务 URL 的引用链接，Giphy 是非 Microsoft 服务）存储在基于 Azure 的媒体服务中，该服务部署到与聊天服务相同的位置。</span><span class="sxs-lookup"><span data-stu-id="d4546-135">Media used in chats (except for Giphy GIFs which aren't stored but are a reference link to the original Giphy service URL, Giphy is a non-Microsoft service) is stored in an Azure-based media service that is deployed to the same locations as the chat service.</span></span>

#### <a name="files"></a><span data-ttu-id="d4546-136">文件</span><span class="sxs-lookup"><span data-stu-id="d4546-136">Files</span></span>

<span data-ttu-id="d4546-137">频道中共享的文件（包括 OneNote 和 Wiki ）存储在团队的 SharePoint 站点中。</span><span class="sxs-lookup"><span data-stu-id="d4546-137">Files (including OneNote and Wiki) that somebody shares in a channel are stored in the team’s SharePoint site.</span></span> <span data-ttu-id="d4546-138">在私密聊天、会议或通话期间的聊天中共享的文件将上载并存储在 OneDrive 中，供共享该文件的用户的业务帐户使用。</span><span class="sxs-lookup"><span data-stu-id="d4546-138">Files shared in a private chat or a chat during a meeting or call are uploaded and stored in the OneDrive for the Business account of the user who shares the file.</span></span> <span data-ttu-id="d4546-139">Exchange、SharePoint 和 OneDrive 已经在全球每个数据中心地理位置提供数据驻留。</span><span class="sxs-lookup"><span data-stu-id="d4546-139">Exchange, SharePoint and OneDrive already provide data residency in each of the worldwide datacenter geos.</span></span> <span data-ttu-id="d4546-140">因此，对于现有客户，作为 Teams 体验一部分的所有文件、OneNote 笔记本、Team wiki 内容和邮箱都已根据您的租户相关性存储在该位置。</span><span class="sxs-lookup"><span data-stu-id="d4546-140">So, for existing customers, all files, OneNote notebooks, Teams wiki content, and mailboxes that are part of the Teams experience are already stored in the location based on your tenant affinity.</span></span> <span data-ttu-id="d4546-141">文件存储在澳大利亚、加拿大、法国、德国、印度、日本、阿拉伯联合酋长国、英国、南非、韩国和瑞士（包括列支敦士登）的国家/地区。</span><span class="sxs-lookup"><span data-stu-id="d4546-141">Files are stored in-country for Australia, Canada, France, Germany, India, Japan, the United Arab Emirates, the United Kingdom, South Africa, South Korea, and Switzerland (which includes Liechtenstein).</span></span> <span data-ttu-id="d4546-142">对于所有其他国家/地区，基于租户相关性，文件存储在美国、欧洲或亚太地区。</span><span class="sxs-lookup"><span data-stu-id="d4546-142">For all other countries, files are stored in the US, Europe, or Asia Pacific location based on tenant affinity.</span></span>

### <a name="datacenter-locations"></a><span data-ttu-id="d4546-143">数据中心位置</span><span class="sxs-lookup"><span data-stu-id="d4546-143">Datacenter locations</span></span>

<span data-ttu-id="d4546-144">本节中描述的 Teams 服务将静态数据存储在以下位置：</span><span class="sxs-lookup"><span data-stu-id="d4546-144">The Teams services described in this section store data at rest in the following locations:</span></span>

|<span data-ttu-id="d4546-145">国家或地区</span><span class="sxs-lookup"><span data-stu-id="d4546-145">Country or region</span></span>  |<span data-ttu-id="d4546-146">数据中心位置</span><span class="sxs-lookup"><span data-stu-id="d4546-146">Datacenter location</span></span> |
|---------|---------|
|<span data-ttu-id="d4546-147">澳大利亚</span><span class="sxs-lookup"><span data-stu-id="d4546-147">Australia</span></span>   |<span data-ttu-id="d4546-148">新南威尔士州和维多利亚</span><span class="sxs-lookup"><span data-stu-id="d4546-148">New South Wales and Victoria</span></span>         |
|<span data-ttu-id="d4546-149">加拿大</span><span class="sxs-lookup"><span data-stu-id="d4546-149">Canada</span></span>    |<span data-ttu-id="d4546-150">魁北克市和多伦多</span><span class="sxs-lookup"><span data-stu-id="d4546-150">Quebec City and Toronto</span></span>         |
|<span data-ttu-id="d4546-151">法国</span><span class="sxs-lookup"><span data-stu-id="d4546-151">France</span></span>    |<span data-ttu-id="d4546-152">马赛和巴黎</span><span class="sxs-lookup"><span data-stu-id="d4546-152">Marseille and Paris</span></span>         |
|<span data-ttu-id="d4546-153">德国</span><span class="sxs-lookup"><span data-stu-id="d4546-153">Germany</span></span>    |<span data-ttu-id="d4546-154">柏林和法兰克福</span><span class="sxs-lookup"><span data-stu-id="d4546-154">Berlin and Frankfurt</span></span>      |
|<span data-ttu-id="d4546-155">印度</span><span class="sxs-lookup"><span data-stu-id="d4546-155">India</span></span>   |<span data-ttu-id="d4546-156">金奈和普纳</span><span class="sxs-lookup"><span data-stu-id="d4546-156">Chennai and Pune</span></span>        |
|<span data-ttu-id="d4546-157">日本</span><span class="sxs-lookup"><span data-stu-id="d4546-157">Japan</span></span>    |<span data-ttu-id="d4546-158">东京（埼玉）和大阪</span><span class="sxs-lookup"><span data-stu-id="d4546-158">Tokyo (Saitama) and Osaka</span></span>         |
|<span data-ttu-id="d4546-159">列支敦士登</span><span class="sxs-lookup"><span data-stu-id="d4546-159">Liechtenstein</span></span>   |<span data-ttu-id="d4546-160">日内瓦和苏黎世</span><span class="sxs-lookup"><span data-stu-id="d4546-160">Geneva and Zurich</span></span>       |
|<span data-ttu-id="d4546-161">南非</span><span class="sxs-lookup"><span data-stu-id="d4546-161">South Africa</span></span>     |<span data-ttu-id="d4546-162">约翰内斯堡和开普敦</span><span class="sxs-lookup"><span data-stu-id="d4546-162">Johannesburg and Cape Town</span></span>         |
|<span data-ttu-id="d4546-163">韩国</span><span class="sxs-lookup"><span data-stu-id="d4546-163">South Korea</span></span>     |<span data-ttu-id="d4546-164">首尔和釜山</span><span class="sxs-lookup"><span data-stu-id="d4546-164">Seoul and Busan</span></span>         |
|<span data-ttu-id="d4546-165">瑞士</span><span class="sxs-lookup"><span data-stu-id="d4546-165">Switzerland</span></span>    |<span data-ttu-id="d4546-166">日内瓦和苏黎世</span><span class="sxs-lookup"><span data-stu-id="d4546-166">Geneva and Zurich</span></span>       |
|<span data-ttu-id="d4546-167">阿拉伯联合酋长国</span><span class="sxs-lookup"><span data-stu-id="d4546-167">United Arab Emirates</span></span>     |<span data-ttu-id="d4546-168">阿布扎比和迪拜</span><span class="sxs-lookup"><span data-stu-id="d4546-168">Abu Dhabi and Dubai</span></span>         |
|<span data-ttu-id="d4546-169">英国</span><span class="sxs-lookup"><span data-stu-id="d4546-169">United Kingdom</span></span>     | <span data-ttu-id="d4546-170">加的夫和伦敦</span><span class="sxs-lookup"><span data-stu-id="d4546-170">Cardiff and London</span></span>        |
|<span data-ttu-id="d4546-171">美洲 - 北美洲和南美洲 (AMER)</span><span class="sxs-lookup"><span data-stu-id="d4546-171">Americas – North, and South (AMER)</span></span> |<span data-ttu-id="d4546-172">加州湾和弗吉尼亚州博伊顿</span><span class="sxs-lookup"><span data-stu-id="d4546-172">Bay, CA and Boydton, VA</span></span>       |
|<span data-ttu-id="d4546-173">亚太地区 (APAC)</span><span class="sxs-lookup"><span data-stu-id="d4546-173">Asia Pacific (APAC)</span></span>  |<span data-ttu-id="d4546-174">新加坡和香港特别行政区</span><span class="sxs-lookup"><span data-stu-id="d4546-174">Singapore and Hong Kong</span></span>        |
|<span data-ttu-id="d4546-175">欧洲、中东和亚洲 (EMEA)</span><span class="sxs-lookup"><span data-stu-id="d4546-175">Europe, Middle East, and Asia (EMEA)</span></span>   |<span data-ttu-id="d4546-176">都柏林和阿姆斯特丹</span><span class="sxs-lookup"><span data-stu-id="d4546-176">Dublin and Amsterdam</span></span>        |

> [!NOTE]
> <span data-ttu-id="d4546-177">对列支敦士登来说，数据存储在日内瓦和苏黎世的瑞士数据中心。</span><span class="sxs-lookup"><span data-stu-id="d4546-177">For Liechtenstein, data is stored at rest in the Switzerland data centers in Geneva and Zurich.</span></span>

### <a name="data-stored-with-a-third-party-storage-provider"></a><span data-ttu-id="d4546-178">使用第三方存储提供商存储的数据</span><span class="sxs-lookup"><span data-stu-id="d4546-178">Data stored with a third-party storage provider</span></span>

<span data-ttu-id="d4546-179">因此，对于那些依赖于第三方存储位置的服务的用户来说，应该允许他们将这些数据存储在第三方的位置上。</span><span class="sxs-lookup"><span data-stu-id="d4546-179">Organizations who allow users to store files with a third-party storage provider are dependent on the storage location of those services and should, therefore, review the location of data at rest for those services separately.</span></span>

- <span data-ttu-id="d4546-180">**选项卡**：选项卡允许用户将应用程序和服务中的信息固定到频道。</span><span class="sxs-lookup"><span data-stu-id="d4546-180">**Tabs**: Tabs allow users to pin information from apps and services to a channel.</span></span> <span data-ttu-id="d4546-181">因此，它因存储数据的选项卡类型而异。</span><span class="sxs-lookup"><span data-stu-id="d4546-181">Thus, it varies by type of the tab where the data is stored.</span></span> <span data-ttu-id="d4546-182">该选项卡本身不存储任何数据。</span><span class="sxs-lookup"><span data-stu-id="d4546-182">The tab itself doesn't store any data.</span></span> <span data-ttu-id="d4546-183">例如，SharePoint 选项卡将根据 SharePoint 网站集的预配位置存储数据。</span><span class="sxs-lookup"><span data-stu-id="d4546-183">For example, a SharePoint tab will store data based on where the SharePoint site collection was provisioned.</span></span> <span data-ttu-id="d4546-184">包含合作伙伴信息的选项卡将直接将数据存储在合作伙伴使用的系统中，并且只显示其视图。</span><span class="sxs-lookup"><span data-stu-id="d4546-184">A tab that includes information from a partner will store the data directly in the system used by the partner and only present a view of it.</span></span>
- <span data-ttu-id="d4546-185">**其他合作伙伴应用**：对于您可能在 Teams 体验中使用的合作伙伴的应用程序和服务，Microsoft 不提供任何数据驻留支持。</span><span class="sxs-lookup"><span data-stu-id="d4546-185">**Other partner apps**: Microsoft doesn't provide any data residency support for apps and services from partners that you might be using within the Teams experience.</span></span> <span data-ttu-id="d4546-186">直接查看这些解决方案中的信息，以了解其数据的存储位置。</span><span class="sxs-lookup"><span data-stu-id="d4546-186">Review information from those solutions directly to learn about where their data is being stored.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4546-187">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d4546-187">See also</span></span>

- [<span data-ttu-id="d4546-188">Microsoft Teams 推出阿联酋数据驻留</span><span class="sxs-lookup"><span data-stu-id="d4546-188">Microsoft Teams launches United Arab Emirates Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-United-Arab-Emirates-Data-Residency/ba-p/980330)

- [<span data-ttu-id="d4546-189">Microsoft Teams 推出韩国数据驻留</span><span class="sxs-lookup"><span data-stu-id="d4546-189">Microsoft Teams launches South Korean Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Korea-Data-Residency/ba-p/789171)

- [<span data-ttu-id="d4546-190">Microsoft Teams 推出南非数据驻留</span><span class="sxs-lookup"><span data-stu-id="d4546-190">Microsoft Teams launches South African Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Africa-Data-Residency/ba-p/776611)

- [<span data-ttu-id="d4546-191">Microsoft Teams 推出法国数据驻留</span><span class="sxs-lookup"><span data-stu-id="d4546-191">Microsoft Teams Launches France Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-France-Data-Residency/ba-p/364466)

- [<span data-ttu-id="d4546-192">Microsoft Teams 推出印度数据驻留，即将推出其他地点</span><span class="sxs-lookup"><span data-stu-id="d4546-192">Microsoft Teams launches India Data Residency, other geos coming soon</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-India-Data-Residency-other-geos-coming/ba-p/154083)

- [<span data-ttu-id="d4546-193">Microsoft Teams 推出澳大利亚和日本数据驻留</span><span class="sxs-lookup"><span data-stu-id="d4546-193">Microsoft Teams Launches Australia and Japan Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827)

- [<span data-ttu-id="d4546-194">Microsoft Teams 推出加拿大的数据驻留、澳大利亚和日本即将推出</span><span class="sxs-lookup"><span data-stu-id="d4546-194">Microsoft Teams Launches Canada Data Residency, Australia and Japan coming soon</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178)
