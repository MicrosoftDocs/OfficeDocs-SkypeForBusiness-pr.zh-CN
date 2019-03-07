---
title: 欢迎使用 Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.date: 01/28/2019
ms.reviewer: LolaJ
description: 找到在组织中部署 Microsoft Teams 的正确途径。 了解 Teams 基础结构以及如何与 Office 365 配合使用。
localization_priority: Priority
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7ee4cba00f20eb53630845f1956d88d47e333084
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2019
ms.locfileid: "30458865"
---
# <a name="welcome-to-microsoft-teams"></a><span data-ttu-id="b121f-104">欢迎使用 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b121f-104">Welcome to Microsoft Teams</span></span>
<span data-ttu-id="b121f-105">如果你是贵组织的 Microsoft Teams 管理员，本文正适合你。</span><span class="sxs-lookup"><span data-stu-id="b121f-105">If you're the admin for Microsoft Teams in your organization, you're in the right place.</span></span> <span data-ttu-id="b121f-106">如果你已准备好开始使用 Teams，请首先参阅[如何部署 Teams](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="b121f-106">When you're ready to get going with Teams, start with [How to roll out Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="b121f-107">如果你未使用过 Teams，并且想要了解详细信息，请继续阅读。</span><span class="sxs-lookup"><span data-stu-id="b121f-107">If you're new to Teams and want to learn more, read on.</span></span>

## <a name="overview-of-teams"></a><span data-ttu-id="b121f-108">Teams 概述</span><span class="sxs-lookup"><span data-stu-id="b121f-108">Overview of Teams</span></span>

<span data-ttu-id="b121f-109">如果你未使用过 Teams，请观看此短视频：[欢迎使用 Teams](https://youtu.be/s3aQV3T0D6c)。</span><span class="sxs-lookup"><span data-stu-id="b121f-109">If you're new to Teams, watch this short video, [Welcome to Teams](https://youtu.be/s3aQV3T0D6c).</span></span> <span data-ttu-id="b121f-110">Teams 基于 Office 365 组、Office Graph 以及与 Office 365 其余产品相同的企业级安全性、合规性和可管理性构建而成。</span><span class="sxs-lookup"><span data-stu-id="b121f-110">Teams is built on Office 365 groups, Office Graph, and the same enterprise-level security, compliance, and manageability as the rest of Office 365.</span></span> <span data-ttu-id="b121f-111">Teams 利用 Azure Active Directory (Azure AD) 中存储的身份。</span><span class="sxs-lookup"><span data-stu-id="b121f-111">Teams leverages identities stored in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="b121f-112">创建团队时，将会创建以下各项：</span><span class="sxs-lookup"><span data-stu-id="b121f-112">When you create a team, here's what gets created:</span></span>
- <span data-ttu-id="b121f-113">新 [Office 365 组](office-365-groups.md)</span><span class="sxs-lookup"><span data-stu-id="b121f-113">A new [Office 365 group](office-365-groups.md)</span></span>
- <span data-ttu-id="b121f-114">用于存储团队文件的 [SharePoint Online](sharepoint-onedrive-interact.md) 站点和文档库</span><span class="sxs-lookup"><span data-stu-id="b121f-114">A [SharePoint Online](sharepoint-onedrive-interact.md) site and document library to store team files</span></span>
- <span data-ttu-id="b121f-115">[Exchange Online](exchange-teams-interact.md) 共享邮箱和日历</span><span class="sxs-lookup"><span data-stu-id="b121f-115">An [Exchange Online](exchange-teams-interact.md) shared mailbox and calendar</span></span>
- <span data-ttu-id="b121f-116">OneNote 笔记本</span><span class="sxs-lookup"><span data-stu-id="b121f-116">A OneNote notebook</span></span>
- <span data-ttu-id="b121f-117">与其他 Office 365 应用（例如 Planner 和 Power BI）的关联</span><span class="sxs-lookup"><span data-stu-id="b121f-117">Ties into other Office 365 apps such as Planner and Power BI</span></span>

<span data-ttu-id="b121f-118">从现有组创建团队时，该组的成员身份、站点、邮箱和笔记本将在 Teams 中出现。</span><span class="sxs-lookup"><span data-stu-id="b121f-118">When you create a team from an existing group, that group's membership, site, mailbox, and notebook are surfaced in Teams.</span></span> <span data-ttu-id="b121f-119">不要错误新的[组织范围的团队](create-an-org-wide-team.md)，这是一种特殊类型的团队，它将组织中所有用户包含进来，并在用户加入和离开组织时在 Active Directory 中更新成员身份。</span><span class="sxs-lookup"><span data-stu-id="b121f-119">Don't miss the new [org-wide team](create-an-org-wide-team.md), a special type of team that pulls in every user in your organization and keeps membership up to date with Active Directory as users join and leave the organization.</span></span> 

<span data-ttu-id="b121f-120">若要自定义和扩展 Teams，请通过[应用、聊天机器人和连接器](deploy-apps-microsoft-teams-landing-page.md)添加第三方应用。</span><span class="sxs-lookup"><span data-stu-id="b121f-120">To customize and extend Teams, add third-party apps through [apps, bots, & connectors](deploy-apps-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="b121f-121">在 Teams 中，你可以将组织外部的人员包含进来，方法是[将其以来宾身份添加](guest-access.md)到团队或频道中。</span><span class="sxs-lookup"><span data-stu-id="b121f-121">With Teams, you can include people from outside your organization by [adding them as a guest](guest-access.md) to a team or channel.</span></span> <span data-ttu-id="b121f-122">作为 Office 365 的一部分，Teams 提供了强大的[开发平台](https://docs.microsoft.com/en-us/microsoftteams/platform)，以便你可以构建组织所需的团队合作中心。</span><span class="sxs-lookup"><span data-stu-id="b121f-122">As part of Office 365, Teams offers a robust [development platform](https://docs.microsoft.com/en-us/microsoftteams/platform) so you can build the teamwork hub you need for your organization.</span></span> 

![Teams 桌面应用和移动应用](media/teams-overview-hub.png)


## <a name="managing-teams"></a><span data-ttu-id="b121f-124">管理团队</span><span class="sxs-lookup"><span data-stu-id="b121f-124">Managing Teams</span></span>

<span data-ttu-id="b121f-125">作为管理员，你将通过 Microsoft Teams 管理中心来管理团队。</span><span class="sxs-lookup"><span data-stu-id="b121f-125">As the admin, you'll manage Teams through the Microsoft Teams admin center.</span></span> <span data-ttu-id="b121f-126">若要了解详细信息：</span><span class="sxs-lookup"><span data-stu-id="b121f-126">To learn more:</span></span>
- [<span data-ttu-id="b121f-127">在 Microsoft Teams 管理中心中管理团队</span><span class="sxs-lookup"><span data-stu-id="b121f-127">Manage Teams in the Microsoft Teams admin center</span></span>](manage-teams-skypeforbusiness-admin-center.md)
- [<span data-ttu-id="b121f-128">在过渡到全新的 Microsoft Teams 管理中心期间管理团队</span><span class="sxs-lookup"><span data-stu-id="b121f-128">Manage Teams during the transition to the new Microsoft Teams admin center</span></span>](manage-teams-in-modern-portal.md)


<span data-ttu-id="b121f-129">要时刻了解贵组织中的 Teams 及所有其他 Office 365 产品和服务的新动向，请务必检查[消息中心](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter)和 [Teams 路线图](https://www.microsoft.com/microsoft-365/roadmap?rtc=1%26filters=Microsoft%20Teams%26searchterms=microsoft%2Cteams)。</span><span class="sxs-lookup"><span data-stu-id="b121f-129">To stay on top of what’s coming for Teams and all other Office 365 products and services in your organization, be sure to check [Message center](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) and the [Teams roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=1%26filters=Microsoft%20Teams%26searchterms=microsoft%2Cteams).</span></span> <span data-ttu-id="b121f-130">你将获取有关新功能和更新功能、规划更改以及一些问题的公告，以帮助你及时了解情况并做好准备。</span><span class="sxs-lookup"><span data-stu-id="b121f-130">You’ll get announcements about new and updated features, planned changes, and issues to help keep you informed and prepared.</span></span> 

## <a name="upgrade-from-skype-for-business-to-teams"></a><span data-ttu-id="b121f-131">从 Skype for Business 升级到 Teams</span><span class="sxs-lookup"><span data-stu-id="b121f-131">Upgrade from Skype for Business to Teams</span></span>
<span data-ttu-id="b121f-132">Teams 是 Office 365 中的主要智能通信客户端，将逐渐取代 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="b121f-132">Teams is the primary client for intelligent communications in Office 365, eventually replacing Skype for Business Online.</span></span> <span data-ttu-id="b121f-133">要了解有关要添加到 Teams 的新功能的详细信息，请参阅 [Microsoft 365 路线图](http://aka.ms/O365Roadmap)。</span><span class="sxs-lookup"><span data-stu-id="b121f-133">To learn more about the new features coming to Teams, see the [Microsoft 365 Roadmap](http://aka.ms/O365Roadmap).</span></span> <span data-ttu-id="b121f-134">为了补充持久聊天和消息传递功能，Teams 通过内置的完全集成的语音和视频功能提供全面的会议和通话体验。</span><span class="sxs-lookup"><span data-stu-id="b121f-134">To complement persistent chat and messaging capabilities, Teams offers a comprehensive meeting and calling experience, with built-in, fully integrated voice and video.</span></span> <span data-ttu-id="b121f-135">请查看 Microsoft Teams 博客中的 [Teams 现在是完整的会议和通话解决方案](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-is-now-a-complete-meeting-and-calling-solution/ba-p/236042)。</span><span class="sxs-lookup"><span data-stu-id="b121f-135">Check out [Teams is now a complete meeting and calling solution](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-is-now-a-complete-meeting-and-calling-solution/ba-p/236042) in the Microsoft Teams Blog.</span></span>

<span data-ttu-id="b121f-136">如果你正在运行 Skype for Business 并准备升级到 Teams，或者你正在同时运行 Skype for Business 和 Teams 并准备完全转为运行 Teams，我们提供了工具、提示和指导，以帮助你成功完成过渡。</span><span class="sxs-lookup"><span data-stu-id="b121f-136">If you’re running Skype for Business and are ready to upgrade to Teams, or if you’re running Skype for Business and Teams side-by-side and are ready to fully move to Teams, we have the tools, tips, and guidance to help make your transition successful.</span></span> <span data-ttu-id="b121f-137">若要了解详细信息，请参阅[升级到 Teams](journey-skypeforbusiness-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="b121f-137">To learn more, see [Upgrade to Teams](journey-skypeforbusiness-teams.md).</span></span>

## <a name="teamwork-and-office-365"></a><span data-ttu-id="b121f-138">团队合作和 Office 365</span><span class="sxs-lookup"><span data-stu-id="b121f-138">Teamwork and Office 365</span></span>
<span data-ttu-id="b121f-139">每个团队各不相同，因此不存在适用于所有团队的通用协作方法。</span><span class="sxs-lookup"><span data-stu-id="b121f-139">Every team is different; there’s no one-size-fits-all approach to collaboration.</span></span> <span data-ttu-id="b121f-140">Office 365 旨在满足每个团队的独特需求，从而使大家能够通过专用的集成应用进行交流、协作以及取得更大的成就。</span><span class="sxs-lookup"><span data-stu-id="b121f-140">Office 365 is designed to meet the unique needs of every team, empowering people to communicate, collaborate, and achieve more with purpose-built, integrated applications.</span></span> 

<span data-ttu-id="b121f-141">在决定要使用的 Office 365 应用和服务时，应考虑贵组织的工作内容以及你的团队需要采用的对话类型。</span><span class="sxs-lookup"><span data-stu-id="b121f-141">When deciding which Office 365 apps and services to use, think about the work your organization does and the types of conversations your teams need to have.</span></span> 

- <span data-ttu-id="b121f-142">作为团队合作的中心，组织内外的人员可在 **Teams** 中主动联系和协作来完成工作。</span><span class="sxs-lookup"><span data-stu-id="b121f-142">**Teams**, as the hub for teamwork, is where people - including people outside your organization - can actively connect and collaborate in real time to get things done.</span></span> <span data-ttu-id="b121f-143">无论是共同创作文档、举行会议还是在其他应用和服务中合作，都可以在开展工作的地方进行对话。</span><span class="sxs-lookup"><span data-stu-id="b121f-143">Have a conversation right where the work is happening, whether coauthoring a document, having a meeting, or working together in other apps and services.</span></span> <span data-ttu-id="b121f-144">在 Teams 中，可以进行非正式聊天、快速对项目进行重复操作、处理团队文件以及对共享的可交付结果进行协作。</span><span class="sxs-lookup"><span data-stu-id="b121f-144">Teams is the place to have informal chats, iterate quickly on a project, work with team files, and collaborate on shared deliverables.</span></span> 

- <span data-ttu-id="b121f-145">**Outlook** 用于以熟悉的电子邮件环境和更加正式的结构化方式或在需要进行有目标的直接通信时进行协作。</span><span class="sxs-lookup"><span data-stu-id="b121f-145">**Outlook** for collaborating in the familiar environment of email and in a more formal, structured manner or when targeted and direct communication is required.</span></span> 

- <span data-ttu-id="b121f-146">**SharePoint** 用于网站和门户、智能内容服务、业务流程自动化和企业搜索。</span><span class="sxs-lookup"><span data-stu-id="b121f-146">**SharePoint** for sites, portals, intelligent content services, business process automation, and enterprise search.</span></span> <span data-ttu-id="b121f-147">SharePoint 将内容保留在团队合作的中心位置，从而使所有类型的内容可在团队之间轻松共享和访问。</span><span class="sxs-lookup"><span data-stu-id="b121f-147">SharePoint keeps content at the center of teamwork, making all types of content easily shareable and accessible across teams.</span></span> <span data-ttu-id="b121f-148">通过与 Outlook、Yammer 和 Teams 紧密集成，可在对话体验中实现无缝内容协作。</span><span class="sxs-lookup"><span data-stu-id="b121f-148">Tight integration with Outlook, Yammer, and Teams enables seamless content collaboration across conversation experiences.</span></span>

- <span data-ttu-id="b121f-149">**OneDrive for Business** 用于存储文件以及与用户邀请的人员共享这些文件。</span><span class="sxs-lookup"><span data-stu-id="b121f-149">**OneDrive for Business** for storing files and sharing them with people that a user invites.</span></span> <span data-ttu-id="b121f-150">用户保存到 OneDrive for Business 的内容在本人与其他人共享之前一直是私人的，因此 OneDrive for Business 非常适合存储不打算共享或未准备好共享的个人文档和草稿文档。</span><span class="sxs-lookup"><span data-stu-id="b121f-150">Content that a user saves to OneDrive for Business is private until the user shares it with others, making it the best option for storing personal and draft documents that are not intended to be shared or not ready to be shared.</span></span>

- <span data-ttu-id="b121f-151">**Yammer** 用于整个组织中的人员进行联系。</span><span class="sxs-lookup"><span data-stu-id="b121f-151">**Yammer** to connect people across the organization.</span></span> <span data-ttu-id="b121f-152">可推动公司范围的计划、共享最佳做法以及就共同的兴趣、领域或做法主题进行交流。</span><span class="sxs-lookup"><span data-stu-id="b121f-152">Drive company-wide initiatives, share best practices, and build communities around common topics of interest or areas or practice.</span></span> <span data-ttu-id="b121f-153">可汇聚众人的想法来提倡整个公司的人员进行开放式讨论。</span><span class="sxs-lookup"><span data-stu-id="b121f-153">Crowdsource ideas to foster open discussions with people across the company.</span></span>

- <span data-ttu-id="b121f-154">**Office 应用**是大家都知道并经常使用的所有熟悉的工具，包括 Word、Excel、PowerPoint 和 OneNote。</span><span class="sxs-lookup"><span data-stu-id="b121f-154">**Office apps** are all the familiar tools that people know and use regularly, including Word, Excel, PowerPoint, and OneNote.</span></span> 

## <a name="teams-known-issues"></a><span data-ttu-id="b121f-155">Teams 已知问题</span><span class="sxs-lookup"><span data-stu-id="b121f-155">Teams known issues</span></span>

<span data-ttu-id="b121f-156">请参阅 [Microsoft Teams 的已知问题](Known-issues.md)</span><span class="sxs-lookup"><span data-stu-id="b121f-156">See [Known issues for Microsoft Teams](Known-issues.md).</span></span>

## <a name="teams-client-release-notes"></a><span data-ttu-id="b121f-157">Teams 客户端发行说明</span><span class="sxs-lookup"><span data-stu-id="b121f-157">Teams client release notes</span></span>

<span data-ttu-id="b121f-158">请参阅 [Microsoft Teams 中的新增功能](https://support.office.com/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de)</span><span class="sxs-lookup"><span data-stu-id="b121f-158">See [What's new in Microsoft Teams](https://support.office.com/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de).</span></span>

