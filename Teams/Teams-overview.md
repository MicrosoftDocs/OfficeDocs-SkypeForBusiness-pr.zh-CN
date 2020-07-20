---
title: 欢迎使用 Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: LolaJ
description: 找到在组织中部署 Microsoft Teams 的正确途径。 了解 Teams 基础结构以及如何与 Microsoft 365 或 Office 365 配合使用。
localization_priority: Priority
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.allteamsdocuments
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7220a7776acb796a4ca56ef28541fd821c0c0132
ms.sourcegitcommit: 18838ed1da69ab4668c903bfcafd4ad2fa02639d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2020
ms.locfileid: "44773307"
---
# <a name="welcome-to-microsoft-teams"></a><span data-ttu-id="afbfd-104">欢迎使用 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="afbfd-104">Welcome to Microsoft Teams</span></span>
<span data-ttu-id="afbfd-105">如果你是贵组织的 Microsoft Teams 管理员，本文正适合你。</span><span class="sxs-lookup"><span data-stu-id="afbfd-105">If you're the admin for Microsoft Teams in your organization, you're in the right place.</span></span> <span data-ttu-id="afbfd-106">如果你已准备好开始使用 Teams，请首先参阅[如何部署 Teams](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="afbfd-106">When you're ready to get going with Teams, start with [How to roll out Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="afbfd-107">如果是第一次使用 Teams 且想要了解详细信息，请观看短视频“[欢迎使用 Teams](https://www.youtube.com/embed/s3aQV3T0D6c)”（55 秒）。</span><span class="sxs-lookup"><span data-stu-id="afbfd-107">If you're new to Teams and want to learn more, check out our short [Welcome to Teams](https://www.youtube.com/embed/s3aQV3T0D6c) video (55 seconds).</span></span>

<span data-ttu-id="afbfd-108">不要错过我们的视频“欢迎使用 Teams（针对 Teams 管理员）”（3 分多钟）：</span><span class="sxs-lookup"><span data-stu-id="afbfd-108">Don't miss our Welcome to Teams for the Teams admin video (just over 3 minutes):</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vxW4]

<span data-ttu-id="afbfd-109">若要获取最终用户 Teams 帮助，请单击应用左侧的“帮助”\*\*\*\*，或转到 [Microsoft Teams 帮助中心](https://support.office.com/teams)。</span><span class="sxs-lookup"><span data-stu-id="afbfd-109">If you're looking for end user Teams Help, click **Help** on the left side of the app, or go to the [Microsoft Teams help center](https://support.office.com/teams).</span></span> <span data-ttu-id="afbfd-110">有关培训，请访问 [Microsoft Teams 培训](training-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="afbfd-110">For training, go to [Microsoft Teams Training](training-microsoft-teams-landing-page.md).</span></span> 

## <a name="teams-architecture"></a><span data-ttu-id="afbfd-111">Teams 体系结构</span><span class="sxs-lookup"><span data-stu-id="afbfd-111">Teams architecture</span></span>

<span data-ttu-id="afbfd-112">Teams 基于 Microsoft 365 组、Microsoft Graph 以及与其余 Microsoft 365 和 Office 365 产品相同的企业级安全性、合规性和可管理性构建而成。</span><span class="sxs-lookup"><span data-stu-id="afbfd-112">Teams is built on Microsoft 365 groups, Microsoft Graph, and the same enterprise-level security, compliance, and manageability as the rest of Microsoft 365 and Office 365.</span></span> <span data-ttu-id="afbfd-113">Teams 利用 Azure Active Directory (Azure AD) 中存储的身份。</span><span class="sxs-lookup"><span data-stu-id="afbfd-113">Teams leverages identities stored in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="afbfd-114">即使在你脱机或遇到网络时好时坏的情况时，Teams 也会继续工作。</span><span class="sxs-lookup"><span data-stu-id="afbfd-114">Teams keeps working even when you're offline or experiencing spotty network conditions.</span></span>

<span data-ttu-id="afbfd-115">若要了解 Teams 在 Microsoft 365 上下文中的位置，请查看以下体系结构海报：[作为 Microsoft 365 一部分的 Teams](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)</span><span class="sxs-lookup"><span data-stu-id="afbfd-115">To see where Teams fits in the context of Microsoft 365, check out this architecture poster:  [Teams as part of Microsoft 365](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)</span></span>

<span data-ttu-id="afbfd-116">创建团队时，将会创建以下各项：</span><span class="sxs-lookup"><span data-stu-id="afbfd-116">When you create a team, here's what gets created:</span></span>
- <span data-ttu-id="afbfd-117">新的 [Microsoft 365 组](office-365-groups.md)</span><span class="sxs-lookup"><span data-stu-id="afbfd-117">A new [Microsoft 365 group](office-365-groups.md)</span></span>
- <span data-ttu-id="afbfd-118">用于存储团队文件的 [SharePoint Online](sharepoint-onedrive-interact.md) 站点和文档库</span><span class="sxs-lookup"><span data-stu-id="afbfd-118">A [SharePoint Online](sharepoint-onedrive-interact.md) site and document library to store team files</span></span>
- <span data-ttu-id="afbfd-119">[Exchange Online](exchange-teams-interact.md) 共享邮箱和日历</span><span class="sxs-lookup"><span data-stu-id="afbfd-119">An [Exchange Online](exchange-teams-interact.md) shared mailbox and calendar</span></span>
- <span data-ttu-id="afbfd-120">OneNote 笔记本</span><span class="sxs-lookup"><span data-stu-id="afbfd-120">A OneNote notebook</span></span>
- <span data-ttu-id="afbfd-121">与其他 Microsoft 365 和 Office 365 应用（例如 Planner 和 Power BI）的关联</span><span class="sxs-lookup"><span data-stu-id="afbfd-121">Ties into other Microsoft 365 and Office 365 apps such as Planner and Power BI</span></span>

<span data-ttu-id="afbfd-122">从现有组创建团队时，该组的成员身份、站点、邮箱和笔记本将在 Teams 中出现。</span><span class="sxs-lookup"><span data-stu-id="afbfd-122">When you create a team from an existing group, that group's membership, site, mailbox, and notebook are surfaced in Teams.</span></span> <span data-ttu-id="afbfd-123">要了解详细信息，请查看此海报：[面向 IT 架构师的 Microsoft 365 中的组](teams-architecture-solutions-posters.md#groups-in-microsoft-365)</span><span class="sxs-lookup"><span data-stu-id="afbfd-123">To learn more, check out this poster: [Groups in Microsoft 365 for IT Architects](teams-architecture-solutions-posters.md#groups-in-microsoft-365)</span></span>

<span data-ttu-id="afbfd-124">若要自定义和扩展 Teams，请通过[应用、机器人和连接器](deploy-apps-microsoft-teams-landing-page.md)添加第三方应用。</span><span class="sxs-lookup"><span data-stu-id="afbfd-124">To customize and extend Teams, add third-party apps through [apps, bots, and connectors](deploy-apps-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="afbfd-125">在 Teams 中，你可以将组织外部的人员包含进来，方法是[将其以来宾身份添加](guest-access.md)到团队或频道中。</span><span class="sxs-lookup"><span data-stu-id="afbfd-125">With Teams, you can include people from outside your organization by [adding them as a guest](guest-access.md) to a team or channel.</span></span> <span data-ttu-id="afbfd-126">作为 Microsoft 365 和 Office 365 的一部分，Teams 提供了强大的[开发平台](https://docs.microsoft.com/microsoftteams/platform)，以便你可以构建组织所需的团队合作中心。</span><span class="sxs-lookup"><span data-stu-id="afbfd-126">As part of Microsoft 365 and Office 365, Teams offers a robust [development platform](https://docs.microsoft.com/microsoftteams/platform) so you can build the teamwork hub you need for your organization.</span></span> 

> [!TIP]
> <span data-ttu-id="afbfd-127">如需深入了解 Teams 体系结构，请观看 [Teams Platform Academy](https://aka.ms/TeamsPlatformAcademy) 中的视频。</span><span class="sxs-lookup"><span data-stu-id="afbfd-127">For a deep dive into Teams architecture, watch the videos on the [Teams Platform Academy](https://aka.ms/TeamsPlatformAcademy).</span></span>


## <a name="managing-teams"></a><span data-ttu-id="afbfd-128">管理团队</span><span class="sxs-lookup"><span data-stu-id="afbfd-128">Managing Teams</span></span>

<span data-ttu-id="afbfd-129">作为管理员，你将通过 Microsoft Teams 管理中心来管理团队。</span><span class="sxs-lookup"><span data-stu-id="afbfd-129">As the admin, you'll manage Teams through the Microsoft Teams admin center.</span></span> <span data-ttu-id="afbfd-130">要快速定位，请观看“使用 Teams 管理中心管理 Teams”视频（3:03 分钟）：</span><span class="sxs-lookup"><span data-stu-id="afbfd-130">For a quick orientation, watch the Manage Teams using the Teams admin center video (3:03 min):</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yi]

<span data-ttu-id="afbfd-131">要了解详细信息：</span><span class="sxs-lookup"><span data-stu-id="afbfd-131">To learn more:</span></span>

- [<span data-ttu-id="afbfd-132">使用 Teams 管理员角色管理 Teams</span><span class="sxs-lookup"><span data-stu-id="afbfd-132">Use Teams admin roles to manage Teams</span></span>](using-admin-roles.md)
- [<span data-ttu-id="afbfd-133">在 Teams 管理中心中管理 Teams</span><span class="sxs-lookup"><span data-stu-id="afbfd-133">Manage Teams in the Teams admin center</span></span>](manage-teams-skypeforbusiness-admin-center.md)
- [<span data-ttu-id="afbfd-134">在过渡到全新的 Teams 管理中心期间管理 Teams</span><span class="sxs-lookup"><span data-stu-id="afbfd-134">Manage Teams during the transition to the new Teams admin center</span></span>](manage-teams-in-modern-portal.md)
- [<span data-ttu-id="afbfd-135">在你的 Microsoft 365 或 Office 365 中管理 Teams 功能</span><span class="sxs-lookup"><span data-stu-id="afbfd-135">Manage Teams features in your Microsoft 365 or Office 365</span></span>](enable-features-office-365.md)

<span data-ttu-id="afbfd-136">要时刻了解贵组织中的 Teams 及所有其他 Microsoft 365 或 Office 365 产品和服务的新动向，请务必检查[消息中心](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter)和 [Teams 路线图](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams)。</span><span class="sxs-lookup"><span data-stu-id="afbfd-136">To stay on top of what's coming for Teams and all other Microsoft 365 or Office 365 products and services in your organization, be sure to check [Message center](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) and the [Teams roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams).</span></span> <span data-ttu-id="afbfd-137">你将获取有关新功能和更新功能、规划更改以及一些问题的公告，以帮助你及时了解情况并做好准备。</span><span class="sxs-lookup"><span data-stu-id="afbfd-137">You'll get announcements about new and updated features, planned changes, and issues to help keep you informed and prepared.</span></span> 

## <a name="upgrade-from-skype-for-business-to-teams"></a><span data-ttu-id="afbfd-138">从 Skype for Business 升级到 Teams</span><span class="sxs-lookup"><span data-stu-id="afbfd-138">Upgrade from Skype for Business to Teams</span></span>
<span data-ttu-id="afbfd-139">Teams 是 Microsoft 365 和 Office 365 中的主要智能通信客户端，它最终将取代 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="afbfd-139">Teams is the primary client for intelligent communications in Microsoft 365 and Office 365, and it'll eventually replace Skype for Business Online.</span></span> <span data-ttu-id="afbfd-140">若要了解要添加到 Teams 的新功能，请参阅 [Microsoft 365 路线图](https://aka.ms/O365Roadmap)。</span><span class="sxs-lookup"><span data-stu-id="afbfd-140">To stay on top of new features coming to Teams, see the [Microsoft 365 Roadmap](https://aka.ms/O365Roadmap).</span></span> <span data-ttu-id="afbfd-141">为了补充持久聊天和消息传递功能，Teams 通过完全集成的内置语音和视频功能提供全面的会议和通话体验。</span><span class="sxs-lookup"><span data-stu-id="afbfd-141">To complement persistent chat and messaging capabilities, Teams offers a comprehensive meeting and calling experience, with built in, fully integrated voice and video.</span></span> <span data-ttu-id="afbfd-142">请查看 Microsoft Teams 博客中的 [Teams 现在是完整的会议和通话解决方案](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-is-now-a-complete-meeting-and-calling-solution/ba-p/236042)。</span><span class="sxs-lookup"><span data-stu-id="afbfd-142">Check out [Teams is now a complete meeting and calling solution](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-is-now-a-complete-meeting-and-calling-solution/ba-p/236042) in the Microsoft Teams Blog.</span></span>

<span data-ttu-id="afbfd-143">如果你正在运行 Skype for Business 并准备升级到 Teams，或者你正在同时运行 Skype for Business 和 Teams 并准备完全转为运行 Teams，我们提供了工具、提示和指导，以帮助你成功完成过渡。</span><span class="sxs-lookup"><span data-stu-id="afbfd-143">If you're running Skype for Business and are ready to upgrade to Teams, or if you're running Skype for Business and Teams side-by-side and are ready to fully move to Teams, we have the tools, tips, and guidance to help make your transition successful.</span></span> <span data-ttu-id="afbfd-144">若要了解详细信息，请参阅[升级到 Teams](upgrade-start-here.md)。</span><span class="sxs-lookup"><span data-stu-id="afbfd-144">To learn more, see [Upgrade to Teams](upgrade-start-here.md).</span></span>

## <a name="teamwork"></a><span data-ttu-id="afbfd-145">团队合作</span><span class="sxs-lookup"><span data-stu-id="afbfd-145">Teamwork</span></span>
<span data-ttu-id="afbfd-146">每个团队各不相同，因此不存在适用于所有团队的通用协作方法。</span><span class="sxs-lookup"><span data-stu-id="afbfd-146">Every team is different; there's no one-size-fits-all approach to collaboration.</span></span> <span data-ttu-id="afbfd-147">Microsoft 365 和 Office 365 旨在满足每个团队的独特需求，从而使大家能够通过专用的集成应用进行交流、协作以及取得更大的成就。</span><span class="sxs-lookup"><span data-stu-id="afbfd-147">Microsoft 365 and Office 365 are designed to meet the unique needs of every team, empowering people to communicate, collaborate, and achieve more with purpose-built, integrated applications.</span></span>

<span data-ttu-id="afbfd-148">在决定要使用的 Microsoft 365 或 Office 365 应用和服务时，应考虑贵组织的工作内容以及你的团队需要采用的对话类型。</span><span class="sxs-lookup"><span data-stu-id="afbfd-148">When deciding which Microsoft 365 or Office 365 apps and services to use, think about the work your organization does and the types of conversations your teams need to have.</span></span> 

- <span data-ttu-id="afbfd-149">作为团队合作的中心，组织内外的人员可在 **Teams** 中主动联系和协作来完成工作。</span><span class="sxs-lookup"><span data-stu-id="afbfd-149">**Teams**, as the hub for teamwork, is where people - including people outside your organization - can actively connect and collaborate in real time to get things done.</span></span> <span data-ttu-id="afbfd-150">无论是共同创作文档、举行会议还是在其他应用和服务中合作，都可以在开展工作的地方进行对话。</span><span class="sxs-lookup"><span data-stu-id="afbfd-150">Have a conversation right where the work is happening, whether coauthoring a document, having a meeting, or working together in other apps and services.</span></span> <span data-ttu-id="afbfd-151">在 Teams 中，可以进行非正式聊天、快速对项目进行重复操作、处理团队文件以及对共享的可交付结果进行协作。</span><span class="sxs-lookup"><span data-stu-id="afbfd-151">Teams is the place to have informal chats, iterate quickly on a project, work with team files, and collaborate on shared deliverables.</span></span> 

- <span data-ttu-id="afbfd-152">**Outlook** 用于以熟悉的电子邮件环境和更加正式的结构化方式或在需要进行有目标的直接通信时进行协作。</span><span class="sxs-lookup"><span data-stu-id="afbfd-152">**Outlook** for collaborating in the familiar environment of email and in a more formal, structured manner or when targeted and direct communication is required.</span></span>

- <span data-ttu-id="afbfd-153">**SharePoint** 用于网站和门户、智能内容服务、业务流程自动化和企业搜索。</span><span class="sxs-lookup"><span data-stu-id="afbfd-153">**SharePoint** for sites, portals, intelligent content services, business process automation, and enterprise search.</span></span> <span data-ttu-id="afbfd-154">SharePoint 将内容保留在团队合作的中心位置，从而使所有类型的内容可在团队之间轻松共享和访问。</span><span class="sxs-lookup"><span data-stu-id="afbfd-154">SharePoint keeps content at the center of teamwork, making all types of content easily shareable and accessible across teams.</span></span> <span data-ttu-id="afbfd-155">通过与 Outlook、Yammer 和 Teams 紧密集成，可在对话体验中实现无缝内容协作。</span><span class="sxs-lookup"><span data-stu-id="afbfd-155">Tight integration with Outlook, Yammer, and Teams enables seamless content collaboration across conversation experiences.</span></span>

- <span data-ttu-id="afbfd-156">**OneDrive for Business** 用于存储文件以及与用户邀请的人员共享这些文件。</span><span class="sxs-lookup"><span data-stu-id="afbfd-156">**OneDrive for Business** for storing files and sharing them with people that a user invites.</span></span> <span data-ttu-id="afbfd-157">用户保存到 OneDrive for Business 的内容在本人与其他人共享之前一直是私人的，因此 OneDrive for Business 非常适合存储不打算共享或未准备好共享的个人文档和草稿文档。</span><span class="sxs-lookup"><span data-stu-id="afbfd-157">Content that a user saves to OneDrive for Business is private until the user shares it with others, making it the best option for storing personal and draft documents that are not intended to be shared or not ready to be shared.</span></span>

- <span data-ttu-id="afbfd-158">**Yammer** 用于整个组织中的人员进行联系。</span><span class="sxs-lookup"><span data-stu-id="afbfd-158">**Yammer** to connect people across the organization.</span></span> <span data-ttu-id="afbfd-159">可推动公司范围的计划、共享最佳做法以及就共同的兴趣、领域或做法主题进行交流。</span><span class="sxs-lookup"><span data-stu-id="afbfd-159">Drive company-wide initiatives, share best practices, and build communities around common topics of interest or areas of practice.</span></span> <span data-ttu-id="afbfd-160">可汇聚众人的想法来提倡整个公司的人员进行开放式讨论。</span><span class="sxs-lookup"><span data-stu-id="afbfd-160">Crowdsource ideas to foster open discussions with people across the company.</span></span>

- <span data-ttu-id="afbfd-161">**Office 应用**是大家都知道并经常使用的所有熟悉的工具，包括 Word、Excel、PowerPoint 和 OneNote。</span><span class="sxs-lookup"><span data-stu-id="afbfd-161">**Office apps** are all the familiar tools that people know and use regularly, including Word, Excel, PowerPoint, and OneNote.</span></span> 

## <a name="teams-content-updates"></a><span data-ttu-id="afbfd-162">Teams 内容更新</span><span class="sxs-lookup"><span data-stu-id="afbfd-162">Teams content updates</span></span>

<span data-ttu-id="afbfd-163">查看[每周更新的 Teams 主题列表](teams-updates.md)。</span><span class="sxs-lookup"><span data-stu-id="afbfd-163">See a [weekly list of Teams topics that have been updated](teams-updates.md).</span></span>

## <a name="teams-known-issues"></a><span data-ttu-id="afbfd-164">Teams 已知问题</span><span class="sxs-lookup"><span data-stu-id="afbfd-164">Teams known issues</span></span>

<span data-ttu-id="afbfd-165">请参阅 [Teams 疑难解答](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)。</span><span class="sxs-lookup"><span data-stu-id="afbfd-165">See [Teams Troubleshooting](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams).</span></span>

## <a name="teams-client-release-notes"></a><span data-ttu-id="afbfd-166">Teams 客户端发行说明</span><span class="sxs-lookup"><span data-stu-id="afbfd-166">Teams client release notes</span></span>

<span data-ttu-id="afbfd-167">请参阅 [Teams 中的新增功能](https://support.office.com/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de)。</span><span class="sxs-lookup"><span data-stu-id="afbfd-167">See [What's new in Teams](https://support.office.com/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de).</span></span>

