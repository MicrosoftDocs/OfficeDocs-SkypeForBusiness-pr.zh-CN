---
title: 欢迎使用 Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.date: 06/18/2019
ms.reviewer: LolaJ
description: 找到在组织中部署 Microsoft Teams 的正确途径。 了解 Teams 基础结构以及如何与 Office 365 配合使用。
localization_priority: Priority
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 84d23efc8cbec7435b4b9677bf9c6321ade4fb3d
ms.sourcegitcommit: 35930c6f634623983aefeed104bc6c66a8aab174
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2019
ms.locfileid: "34957473"
---
# <a name="welcome-to-microsoft-teams"></a><span data-ttu-id="425cd-104">欢迎使用 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="425cd-104">Welcome to Microsoft Teams</span></span>
<span data-ttu-id="425cd-105">如果你是贵组织的 Microsoft Teams 管理员，本文正适合你。</span><span class="sxs-lookup"><span data-stu-id="425cd-105">If you're the admin for Microsoft Teams in your organization, you're in the right place.</span></span> <span data-ttu-id="425cd-106">如果你已准备好开始使用 Teams，请首先参阅[如何部署 Teams](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="425cd-106">When you're ready to get going with Teams, start with [How to roll out Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="425cd-107">如果你未使用过 Teams，并且想要了解详细信息，请继续阅读。</span><span class="sxs-lookup"><span data-stu-id="425cd-107">If you're new to Teams and want to learn more, read on.</span></span> <span data-ttu-id="425cd-108">观看此短视频：[欢迎使用 Teams](https://youtu.be/s3aQV3T0D6c)。</span><span class="sxs-lookup"><span data-stu-id="425cd-108">Check out this short video, [Welcome to Teams](https://youtu.be/s3aQV3T0D6c).</span></span> 

<span data-ttu-id="425cd-109">如果你要查找最终用户 Teams 帮助，请单击应用左侧的“**帮助**”，或转到 [Microsoft Teams 帮助中心](https://support.office.com/teams)。</span><span class="sxs-lookup"><span data-stu-id="425cd-109">If you're looking for end user Teams Help, click **Help** on the left side of the app, or go to the [Microsoft Teams help center](https://support.office.com/teams).</span></span> <span data-ttu-id="425cd-110">有关培训，请访问 [Microsoft Teams 培训](training-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="425cd-110">For training, go to [Microsoft Teams Training](training-microsoft-teams-landing-page.md).</span></span> 

## <a name="teams-architecture"></a><span data-ttu-id="425cd-111">Teams 体系结构</span><span class="sxs-lookup"><span data-stu-id="425cd-111">Teams architecture</span></span>

<span data-ttu-id="425cd-112">Teams 基于 Office 365 组、Microsoft Graph 以及与其余 Office 365 产品相同的企业级安全性、合规性和可管理性构建而成。</span><span class="sxs-lookup"><span data-stu-id="425cd-112">Teams is built on Office 365 groups, Office Graph, and the same enterprise-level security, compliance, and manageability as the rest of Office 365.</span></span> <span data-ttu-id="425cd-113">Teams 利用 Azure Active Directory (Azure AD) 中存储的身份。</span><span class="sxs-lookup"><span data-stu-id="425cd-113">Teams leverages identities stored in Azure Active Directory (Azure AD).</span></span> 

<span data-ttu-id="425cd-114">若要了解 Teams 在 Microsoft 365 中的位置，请查看此体系结构海报：[作为 Microsoft 365 一部分的 Teams](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)</span><span class="sxs-lookup"><span data-stu-id="425cd-114">To see where Teams fits in the context of Microsoft 365, check out this architecture poster: [Teams as part of Microsoft 365](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)</span></span>

<span data-ttu-id="425cd-115">[![Teams 逻辑体系结构海报缩略图](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-teams-logical-architecture-thumb.png)](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-teams-logical-architecture.pdf)</span><span class="sxs-lookup"><span data-stu-id="425cd-115">[![Thumb image for Teams logical architecture poster](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-teams-logical-architecture-thumb.png)](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-teams-logical-architecture.pdf)</span></span>         



<span data-ttu-id="425cd-116">创建团队时，将会创建以下各项：</span><span class="sxs-lookup"><span data-stu-id="425cd-116">When you create a team, here's what gets created:</span></span>
- <span data-ttu-id="425cd-117">新 [Office 365 组](office-365-groups.md)</span><span class="sxs-lookup"><span data-stu-id="425cd-117">A new [Office 365 group](office-365-groups.md)</span></span>
- <span data-ttu-id="425cd-118">用于存储团队文件的 [SharePoint Online](sharepoint-onedrive-interact.md) 站点和文档库</span><span class="sxs-lookup"><span data-stu-id="425cd-118">A [SharePoint Online](sharepoint-onedrive-interact.md) site and document library to store team files</span></span>
- <span data-ttu-id="425cd-119">[Exchange Online](exchange-teams-interact.md) 共享邮箱和日历</span><span class="sxs-lookup"><span data-stu-id="425cd-119">An [Exchange Online](exchange-teams-interact.md) shared mailbox and calendar</span></span>
- <span data-ttu-id="425cd-120">OneNote 笔记本</span><span class="sxs-lookup"><span data-stu-id="425cd-120">A OneNote notebook</span></span>
- <span data-ttu-id="425cd-121">与其他 Office 365 应用（例如 Planner 和 Power BI）的关联</span><span class="sxs-lookup"><span data-stu-id="425cd-121">Ties into other Office 365 apps such as Planner and Power BI</span></span>

<span data-ttu-id="425cd-122">从现有组创建团队时，该组的成员身份、站点、邮箱和笔记本将在 Teams 中出现。</span><span class="sxs-lookup"><span data-stu-id="425cd-122">When you create a team from an existing group, that group's membership, site, mailbox, and notebook are surfaced in Teams.</span></span> <span data-ttu-id="425cd-123">要了解详细信息，请查看此海报：[面向 IT 架构师的 Microsoft 365 中的组](teams-architecture-solutions-posters.md#groups-in-microsoft-365)</span><span class="sxs-lookup"><span data-stu-id="425cd-123">To learn more, check out this poster: [Groups in Microsoft 365 for IT Architects](teams-architecture-solutions-posters.md#groups-in-microsoft-365)</span></span>

<span data-ttu-id="425cd-124">[![组信息图的缩略图](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.pdf)</span><span class="sxs-lookup"><span data-stu-id="425cd-124">[![Thumb image for groups infographic](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.pdf)</span></span>

<span data-ttu-id="425cd-125">若要自定义和扩展 Teams，请通过[应用、聊天机器人和连接器](deploy-apps-microsoft-teams-landing-page.md)添加第三方应用。</span><span class="sxs-lookup"><span data-stu-id="425cd-125">To customize and extend Teams, add third-party apps through [apps, bots, & connectors](deploy-apps-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="425cd-126">在 Teams 中，你可以将组织外部的人员包含进来，方法是[将其以来宾身份添加](guest-access.md)到团队或频道中。</span><span class="sxs-lookup"><span data-stu-id="425cd-126">With Teams, you can include people from outside your organization by [adding them as a guest](guest-access.md) to a team or channel.</span></span> <span data-ttu-id="425cd-127">作为 Office 365 的一部分，Teams 提供了强大的[开发平台](https://docs.microsoft.com/microsoftteams/platform)，以便你可以构建组织所需的团队合作中心。</span><span class="sxs-lookup"><span data-stu-id="425cd-127">As part of Office 365, Teams offers a robust [development platform](https://docs.microsoft.com/microsoftteams/platform) so you can build the teamwork hub you need for your organization.</span></span> 

> [!TIP]
> <span data-ttu-id="425cd-128">如需深入了解 Teams 体系结构，请观看 [Teams Platform Academy](https://aka.ms/TeamsPlatformAcademy) 中的视频。</span><span class="sxs-lookup"><span data-stu-id="425cd-128">For a deep dive into Teams architecture, watch the videos on the [Teams Platform Academy](https://aka.ms/TeamsPlatformAcademy).</span></span>


## <a name="managing-teams"></a><span data-ttu-id="425cd-129">管理团队</span><span class="sxs-lookup"><span data-stu-id="425cd-129">Managing Teams</span></span>

<span data-ttu-id="425cd-130">作为管理员，你将通过 Microsoft Teams 管理中心来管理团队。</span><span class="sxs-lookup"><span data-stu-id="425cd-130">As the admin, you'll manage Teams through the Microsoft Teams admin center.</span></span> <span data-ttu-id="425cd-131">若要了解详细信息：</span><span class="sxs-lookup"><span data-stu-id="425cd-131">To learn more:</span></span>
- [<span data-ttu-id="425cd-132">使用 Teams 管理员角色管理 Teams</span><span class="sxs-lookup"><span data-stu-id="425cd-132">Use Teams admin roles to manage Teams</span></span>](using-admin-roles.md)
- [<span data-ttu-id="425cd-133">在 Teams 管理中心中管理 Teams</span><span class="sxs-lookup"><span data-stu-id="425cd-133">Manage Teams in the Microsoft Teams admin center</span></span>](manage-teams-skypeforbusiness-admin-center.md)
- [<span data-ttu-id="425cd-134">在过渡到全新的 Teams 管理中心期间管理 Teams</span><span class="sxs-lookup"><span data-stu-id="425cd-134">Manage Teams during the transition to the new Microsoft Teams admin center</span></span>](manage-teams-in-modern-portal.md)
- [<span data-ttu-id="425cd-135">在你的 Office 365 组织中管理 Teams 功能</span><span class="sxs-lookup"><span data-stu-id="425cd-135">Manage Teams features in your Office 365 organization</span></span>](enable-features-office-365.md)

<span data-ttu-id="425cd-136">要时刻了解贵组织中的 Teams 及所有其他 Office 365 产品和服务的新动向，请务必检查[消息中心](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter)和 [Teams 路线图](https://www.microsoft.com/microsoft-365/roadmap?rtc=1%26filters=Microsoft%20Teams%26searchterms=microsoft%2Cteams)。</span><span class="sxs-lookup"><span data-stu-id="425cd-136">To stay on top of what’s coming for Teams and all other Office 365 products and services in your organization, be sure to check [Message center](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) and the [Teams roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=1%26filters=Microsoft%20Teams%26searchterms=microsoft%2Cteams).</span></span> <span data-ttu-id="425cd-137">你将获取有关新功能和更新功能、规划更改以及一些问题的公告，以帮助你及时了解情况并做好准备。</span><span class="sxs-lookup"><span data-stu-id="425cd-137">You’ll get announcements about new and updated features, planned changes, and issues to help keep you informed and prepared.</span></span> 

## <a name="upgrade-from-skype-for-business-to-teams"></a><span data-ttu-id="425cd-138">从 Skype for Business 升级到 Teams</span><span class="sxs-lookup"><span data-stu-id="425cd-138">Upgrade from Skype for Business to Teams</span></span>
<span data-ttu-id="425cd-139">Teams 是 Office 365 中的主要智能通信客户端，将逐渐取代 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="425cd-139">Teams is the primary client for intelligent communications in Office 365, eventually replacing Skype for Business Online.</span></span> <span data-ttu-id="425cd-140">若要了解要添加到 Teams 的新功能，请参阅 [Microsoft 365 路线图](http://aka.ms/O365Roadmap)。</span><span class="sxs-lookup"><span data-stu-id="425cd-140">To stay on top of new features coming to Teams, see the [Microsoft 365 Roadmap](http://aka.ms/O365Roadmap).</span></span> <span data-ttu-id="425cd-141">为了补充持久聊天和消息传递功能，Teams 通过完全集成的内置语音和视频功能提供全面的会议和通话体验。</span><span class="sxs-lookup"><span data-stu-id="425cd-141">To complement persistent chat and messaging capabilities, Teams offers a comprehensive meeting and calling experience, with built-in, fully integrated voice and video.</span></span> <span data-ttu-id="425cd-142">请查看 Microsoft Teams 博客中的 [Teams 现在是完整的会议和通话解决方案](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-is-now-a-complete-meeting-and-calling-solution/ba-p/236042)。</span><span class="sxs-lookup"><span data-stu-id="425cd-142">Check out [Teams is now a complete meeting and calling solution](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-is-now-a-complete-meeting-and-calling-solution/ba-p/236042) in the Microsoft Teams Blog.</span></span>

<span data-ttu-id="425cd-143">如果你正在运行 Skype for Business 并准备升级到 Teams，或者你正在同时运行 Skype for Business 和 Teams 并准备完全转为运行 Teams，我们提供了工具、提示和指导，以帮助你成功完成过渡。</span><span class="sxs-lookup"><span data-stu-id="425cd-143">If you’re running Skype for Business and are ready to upgrade to Teams, or if you’re running Skype for Business and Teams side-by-side and are ready to fully move to Teams, we have the tools, tips, and guidance to help make your transition successful.</span></span> <span data-ttu-id="425cd-144">若要了解详细信息，请参阅[升级到 Teams](journey-skypeforbusiness-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="425cd-144">To learn more, see [Upgrade to Teams](journey-skypeforbusiness-teams.md).</span></span>

## <a name="teamwork-and-office-365"></a><span data-ttu-id="425cd-145">团队合作和 Office 365</span><span class="sxs-lookup"><span data-stu-id="425cd-145">Teamwork and Office 365</span></span>
<span data-ttu-id="425cd-146">每个团队各不相同，因此不存在适用于所有团队的通用协作方法。</span><span class="sxs-lookup"><span data-stu-id="425cd-146">Every team is different; there’s no one-size-fits-all approach to collaboration.</span></span> <span data-ttu-id="425cd-147">Office 365 旨在满足每个团队的独特需求，从而使大家能够通过专用的集成应用进行交流、协作以及取得更大的成就。</span><span class="sxs-lookup"><span data-stu-id="425cd-147">Office 365 is designed to meet the unique needs of every team, empowering people to communicate, collaborate, and achieve more with purpose-built, integrated applications.</span></span> 

<span data-ttu-id="425cd-148">在决定要使用的 Office 365 应用和服务时，应考虑贵组织的工作内容以及你的团队需要采用的对话类型。</span><span class="sxs-lookup"><span data-stu-id="425cd-148">When deciding which Office 365 apps and services to use, think about the work your organization does and the types of conversations your teams need to have.</span></span> 

- <span data-ttu-id="425cd-149">作为团队合作的中心，组织内外的人员可在 **Teams** 中主动联系和协作来完成工作。</span><span class="sxs-lookup"><span data-stu-id="425cd-149">**Teams**, as the hub for teamwork, is where people - including people outside your organization - can actively connect and collaborate in real time to get things done.</span></span> <span data-ttu-id="425cd-150">无论是共同创作文档、举行会议还是在其他应用和服务中合作，都可以在开展工作的地方进行对话。</span><span class="sxs-lookup"><span data-stu-id="425cd-150">Have a conversation right where the work is happening, whether coauthoring a document, having a meeting, or working together in other apps and services.</span></span> <span data-ttu-id="425cd-151">在 Teams 中，可以进行非正式聊天、快速对项目进行重复操作、处理团队文件以及对共享的可交付结果进行协作。</span><span class="sxs-lookup"><span data-stu-id="425cd-151">Teams is the place to have informal chats, iterate quickly on a project, work with team files, and collaborate on shared deliverables.</span></span> 

- <span data-ttu-id="425cd-152">**Outlook** 用于以熟悉的电子邮件环境和更加正式的结构化方式或在需要进行有目标的直接通信时进行协作。</span><span class="sxs-lookup"><span data-stu-id="425cd-152">**Outlook** for collaborating in the familiar environment of email and in a more formal, structured manner or when targeted and direct communication is required.</span></span> 

- <span data-ttu-id="425cd-153">**SharePoint** 用于网站和门户、智能内容服务、业务流程自动化和企业搜索。</span><span class="sxs-lookup"><span data-stu-id="425cd-153">**SharePoint** for sites, portals, intelligent content services, business process automation, and enterprise search.</span></span> <span data-ttu-id="425cd-154">SharePoint 将内容保留在团队合作的中心位置，从而使所有类型的内容可在团队之间轻松共享和访问。</span><span class="sxs-lookup"><span data-stu-id="425cd-154">SharePoint keeps content at the center of teamwork, making all types of content easily shareable and accessible across teams.</span></span> <span data-ttu-id="425cd-155">通过与 Outlook、Yammer 和 Teams 紧密集成，可在对话体验中实现无缝内容协作。</span><span class="sxs-lookup"><span data-stu-id="425cd-155">Tight integration with Outlook, Yammer, and Teams enables seamless content collaboration across conversation experiences.</span></span>

- <span data-ttu-id="425cd-156">**OneDrive for Business** 用于存储文件以及与用户邀请的人员共享这些文件。</span><span class="sxs-lookup"><span data-stu-id="425cd-156">**OneDrive for Business** for storing files and sharing them with people that a user invites.</span></span> <span data-ttu-id="425cd-157">用户保存到 OneDrive for Business 的内容在本人与其他人共享之前一直是私人的，因此 OneDrive for Business 非常适合存储不打算共享或未准备好共享的个人文档和草稿文档。</span><span class="sxs-lookup"><span data-stu-id="425cd-157">Content that a user saves to OneDrive for Business is private until the user shares it with others, making it the best option for storing personal and draft documents that are not intended to be shared or not ready to be shared.</span></span>

- <span data-ttu-id="425cd-158">**Yammer** 用于整个组织中的人员进行联系。</span><span class="sxs-lookup"><span data-stu-id="425cd-158">**Yammer** to connect people across the organization.</span></span> <span data-ttu-id="425cd-159">可推动公司范围的计划、共享最佳做法以及就共同的兴趣、领域或做法主题进行交流。</span><span class="sxs-lookup"><span data-stu-id="425cd-159">Drive company-wide initiatives, share best practices, and build communities around common topics of interest or areas or practice.</span></span> <span data-ttu-id="425cd-160">可汇聚众人的想法来提倡整个公司的人员进行开放式讨论。</span><span class="sxs-lookup"><span data-stu-id="425cd-160">Crowdsource ideas to foster open discussions with people across the company.</span></span>

- <span data-ttu-id="425cd-161">**Office 应用**是大家都知道并经常使用的所有熟悉的工具，包括 Word、Excel、PowerPoint 和 OneNote。</span><span class="sxs-lookup"><span data-stu-id="425cd-161">**Office apps** are all the familiar tools that people know and use regularly, including Word, Excel, PowerPoint, and OneNote.</span></span> 

## <a name="teams-content-updates"></a><span data-ttu-id="425cd-162">Teams 内容更新</span><span class="sxs-lookup"><span data-stu-id="425cd-162">Teams content updates</span></span>

<span data-ttu-id="425cd-163">查看[每周更新的 Teams 主题列表](teams-updates.md)。</span><span class="sxs-lookup"><span data-stu-id="425cd-163">See a [weekly list of Teams topics that have been updated](teams-updates.md).</span></span>

## <a name="teams-known-issues"></a><span data-ttu-id="425cd-164">Teams 已知问题</span><span class="sxs-lookup"><span data-stu-id="425cd-164">Teams known issues</span></span>

<span data-ttu-id="425cd-165">请参阅 [Teams 的已知问题](Known-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="425cd-165">See [Known issues for Microsoft Teams](Known-issues.md).</span></span>

## <a name="teams-client-release-notes"></a><span data-ttu-id="425cd-166">Teams 客户端发行说明</span><span class="sxs-lookup"><span data-stu-id="425cd-166">Teams client release notes</span></span>

<span data-ttu-id="425cd-167">请参阅 [Teams 中的新增功能](https://support.office.com/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de)。</span><span class="sxs-lookup"><span data-stu-id="425cd-167">See [What's new in Microsoft Teams](https://support.office.com/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de).</span></span>

