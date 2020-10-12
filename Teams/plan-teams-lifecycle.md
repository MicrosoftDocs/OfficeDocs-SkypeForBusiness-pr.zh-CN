---
title: 规划生命周期管理
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 在本文中，你将了解如何进行相关规划，以便在 Teams 中实施生命周期管理功能。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 44be1d139fe37a34cad620cb449ac8bfe10eb99b
ms.sourcegitcommit: 43823358e7e1c1cece72a69a2ceb4eff86d3f927
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/10/2020
ms.locfileid: "48416925"
---
# <a name="plan-for-lifecycle-management-in-teams"></a><span data-ttu-id="2374e-103">在 Teams 中规划生命周期管理</span><span class="sxs-lookup"><span data-stu-id="2374e-103">Plan for lifecycle management in Teams</span></span>

<span data-ttu-id="2374e-p101">Teams 提供了一组丰富的工具，用于为组织实施协作生命周期管理流程。本文通过适当的问题指导 IT 专业人员确定其对生命周期管理的要求，以及用于满足这些要求的工具。</span><span class="sxs-lookup"><span data-stu-id="2374e-p101">Teams provides a rich set of tools to implement collaboration lifecycle management processes for your organization. This article guides IT pros through the right questions to determine their requirements for lifecycle management, and the tools to use to meet them.</span></span> 

<span data-ttu-id="2374e-p102">规划生命周期管理很重要，因为这意味着你要制定有效地完成工作的规划。大多数项目都会经历开始、中间和结束。Teams 也是如此，但其构建和使用方式多种多样，因此，Teams 处在生命周期的哪个阶段并不总是很明显。制定生命周期管理规划可帮助你在组织的项目经历这些阶段时对其进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="2374e-p102">Planning for lifecycle management is important, because it means you're building a plan to get your work done effectively. Most projects consist of a beginning, middle, and end. Teams do too, but they can be constructed and used in such a variety of ways that it's not always obvious which stage of their lifecycle they're in. Having a plan for lifecycle management will help you track your organization's projects as they go through these stages.</span></span>

> [!Tip]
> <span data-ttu-id="2374e-110">观看以下会话，详细了解 Microsoft Teams 中的生命周期：[Microsoft Teams 中的治理、管理和生命周期](https://aka.ms/teams-governance)</span><span class="sxs-lookup"><span data-stu-id="2374e-110">Watch the following session to learn about more about lifecycle in Microsoft Teams: [Governance, management and lifecycle in Microsoft Teams](https://aka.ms/teams-governance)</span></span>


## <a name="lifecycle-concepts"></a><span data-ttu-id="2374e-111">生命周期概念</span><span class="sxs-lookup"><span data-stu-id="2374e-111">Lifecycle concepts</span></span>

<span data-ttu-id="2374e-112">以下概念和定义都会影响你为生命周期管理做出的决策。</span><span class="sxs-lookup"><span data-stu-id="2374e-112">The following concepts and definitions all affect the decisions you make for lifecycle management.</span></span>

<span data-ttu-id="2374e-113">**Teams**</span><span class="sxs-lookup"><span data-stu-id="2374e-113">**Teams**</span></span>

<span data-ttu-id="2374e-114">_团队_是包含人员、内容和促进协作的工具的集合。</span><span class="sxs-lookup"><span data-stu-id="2374e-114">A _team_ is a collection of people, content, and tools that facilitate collaboration.</span></span> <span data-ttu-id="2374e-115">团队规定了其成员以及应用于这些成员的权限和策略。</span><span class="sxs-lookup"><span data-stu-id="2374e-115">A team defines who its members are, and the permissions and policies that apply to those members.</span></span> <span data-ttu-id="2374e-116">Teams 是基于 Microsoft 365 组进行构建的，并且对 Microsoft 365 组成员身份的更改会同步到团队。</span><span class="sxs-lookup"><span data-stu-id="2374e-116">Teams are built on Microsoft 365 Groups, and changes to Microsoft 365 group membership sync to the team.</span></span> <span data-ttu-id="2374e-117">与其他 Microsoft 365 组一样，Teams 中自动预配了一个 Exchange 邮箱、一个 SharePoint 站点、一个 OneNote 笔记本以及 Microsoft 365 或 Office 365 中的其他资源。</span><span class="sxs-lookup"><span data-stu-id="2374e-117">Like other Microsoft 365 Groups, Teams come auto-provisioned with an Exchange mailbox, a SharePoint site, a OneNote notebook, and other assets within Microsoft 365 or Office 365.</span></span> <span data-ttu-id="2374e-118">[了解有关 Microsoft 365 组的详细信息。](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)</span><span class="sxs-lookup"><span data-stu-id="2374e-118">[Learn more about Microsoft 365 Groups](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).</span></span>

<span data-ttu-id="2374e-119">**频道**</span><span class="sxs-lookup"><span data-stu-id="2374e-119">**Channels**</span></span>

<span data-ttu-id="2374e-120">频道是团队中的协作空间，在此完成实际工作。</span><span class="sxs-lookup"><span data-stu-id="2374e-120">Channels are the collaboration spaces within a team where the actual work is done.</span></span> <span data-ttu-id="2374e-121">每个频道均代表整个团队中一个不同的主题或工作流。</span><span class="sxs-lookup"><span data-stu-id="2374e-121">Each channel represents a different topic or workstream within the overall team.</span></span> <span data-ttu-id="2374e-122">对于每个频道，都会自动在 SharePoint 站点上创建一个文件夹以用于存储共享到相应频道的所有文件，从而方便用户查找和处理其需要的文档。</span><span class="sxs-lookup"><span data-stu-id="2374e-122">For each channel, a folder is automatically created on the SharePoint site to store all files shared to that channel, making it easy for users to find and work on the documents they care about.</span></span> <span data-ttu-id="2374e-123">也可以使用与特定工作流相关的应用程序扩展频道，例如，你可以将 Power BI 仪表板添加到某个频道以跟踪项目的某个方面的成功情况。</span><span class="sxs-lookup"><span data-stu-id="2374e-123">Channels can also be extended with apps that are relevant to the particular workstream—for example, you can add a Power BI dashboard to a channel to track the success of one aspect of your project.</span></span>

<span data-ttu-id="2374e-124">**团队访问类型**</span><span class="sxs-lookup"><span data-stu-id="2374e-124">**Team access types**</span></span>

<span data-ttu-id="2374e-125">这些类型确定哪些人可以加入团队：</span><span class="sxs-lookup"><span data-stu-id="2374e-125">These determine who can join the team:</span></span>

-   <span data-ttu-id="2374e-126">_私人_团队限于团队所有者批准的团队成员。</span><span class="sxs-lookup"><span data-stu-id="2374e-126">_Private_ teams are restricted to team members approved by the team owner(s).</span></span> <span data-ttu-id="2374e-127">这是大型组织中项目团队和虚拟团队的典型设置。</span><span class="sxs-lookup"><span data-stu-id="2374e-127">This is a typical setting for project teams and virtual teams in a large organization.</span></span>
-   <span data-ttu-id="2374e-128">_公共_团队向组织中的所有人开放，可以直接加入。</span><span class="sxs-lookup"><span data-stu-id="2374e-128">_Public_ teams are open for anyone in the organization to join directly.</span></span> <span data-ttu-id="2374e-129">要对处理不同项目的不同部门的人员都关注的主题进行协作，这很有用。</span><span class="sxs-lookup"><span data-stu-id="2374e-129">This is useful for collaboration on topics of general interest to people in different departments working on different projects.</span></span> <span data-ttu-id="2374e-130">这是适合小型组织的默认设置。</span><span class="sxs-lookup"><span data-stu-id="2374e-130">This is a good default setting for smaller organizations.</span></span>

<span data-ttu-id="2374e-131">**团队用户类型和管理员角色**</span><span class="sxs-lookup"><span data-stu-id="2374e-131">**Team user types and admin roles**</span></span> 

<span data-ttu-id="2374e-132">团队用户类型确定团队成员拥有的控制权限：</span><span class="sxs-lookup"><span data-stu-id="2374e-132">Team user types determine how much control a team member has:</span></span>

-   <span data-ttu-id="2374e-133">*团队创建者*有权在目录中创建组或团队。</span><span class="sxs-lookup"><span data-stu-id="2374e-133">*Team creator* has permissions to create a group or team in the directory.</span></span> <span data-ttu-id="2374e-134">管理员可以将此用户类型限定于一部分管理员或用户。</span><span class="sxs-lookup"><span data-stu-id="2374e-134">The admin can constrain this user type to a subset of admins or users.</span></span> <span data-ttu-id="2374e-135">有关详细信息，请参阅[管理哪些人可以创建 Microsoft 365 组](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618)。</span><span class="sxs-lookup"><span data-stu-id="2374e-135">For more information, see [Manage who can create Microsoft 365 Groups](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span> <span data-ttu-id="2374e-136">团队创建者会自动成为团队的所有者。</span><span class="sxs-lookup"><span data-stu-id="2374e-136">Team creators automatically become an owner of the team.</span></span>
-   <span data-ttu-id="2374e-137">*团队所有者*管理团队的成员身份和设置。</span><span class="sxs-lookup"><span data-stu-id="2374e-137">*Team owner* manages membership and settings for the team.</span></span> <span data-ttu-id="2374e-138">每个团队的团队所有者可以多达 100 人。</span><span class="sxs-lookup"><span data-stu-id="2374e-138">There can be as many as 100 team owners per team.</span></span>
-   <span data-ttu-id="2374e-139">*团队成员*是组织中加入团队的成员。</span><span class="sxs-lookup"><span data-stu-id="2374e-139">*Team member* is a member of your organization who participates in a team.</span></span>
-   <span data-ttu-id="2374e-140">*来宾*是组织外部的用户。</span><span class="sxs-lookup"><span data-stu-id="2374e-140">*Guest* is a user who's external to your organization.</span></span> <span data-ttu-id="2374e-141">如果组织启用了[来宾访问](guest-access.md)，则可以邀请有电子邮件地址的任何人作为来宾。</span><span class="sxs-lookup"><span data-stu-id="2374e-141">Anyone with an email address can be invited as a guest if your organization has enabled [guest access](guest-access.md).</span></span>

> [!Note]
> <span data-ttu-id="2374e-142">有关团队所有者和团队成员功能的详细信息，请参阅[在 Microsoft Teams 中分配角色和权限](assign-roles-permissions.md)一文。</span><span class="sxs-lookup"><span data-stu-id="2374e-142">You can learn more about team owner and team member capabilities in the article [Assign role and permissions in Microsoft Teams](assign-roles-permissions.md).</span></span>

<span data-ttu-id="2374e-143">团队管理员角色确定每个管理员角色拥有者可以使用的功能。</span><span class="sxs-lookup"><span data-stu-id="2374e-143">Teams admin roles determine what capabilities each admin role holder has.</span></span> <span data-ttu-id="2374e-144">下表对此进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="2374e-144">These are described in the following table.</span></span>

<table>
 <thead>
  <tr>
    <th width="0.5%"></th>
    <th width="15.5%"><span data-ttu-id="2374e-145">角色&nbsp;&nbsp;</span><span class="sxs-lookup"><span data-stu-id="2374e-145">Role&nbsp;&nbsp;</span></span></th>
    <th width="25%"><span data-ttu-id="2374e-146">说明</span><span class="sxs-lookup"><span data-stu-id="2374e-146">Description</span></span></th>
    <th width="60%"><span data-ttu-id="2374e-147">可以执行的任务（使用备注的工具）</span><span class="sxs-lookup"><span data-stu-id="2374e-147">Can do the following tasks, using tools as noted</span></span></th>
  </tr>
</thead>
<tbody>
   <tr>
    <td valign="top" colspan="2"><span data-ttu-id="2374e-148">Teams 服务管理员</span><span class="sxs-lookup"><span data-stu-id="2374e-148">Teams Service Administrator</span></span></td>
    <td valign="top"><span data-ttu-id="2374e-149">管理 Teams 服务，创建和管理 Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="2374e-149">Manage the Teams service, and create and manage Microsoft 365 Groups</span></span></td>
    <td valign="top"><span data-ttu-id="2374e-150">管理会议，包括会议策略、配置和会议网桥<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2374e-150">Manage meetings, including meeting policies, configurations, and conference bridges<sup>1</sup></span></span><br><br><span data-ttu-id="2374e-151">管理语音，包括通话策略、电话号码存量和分配、呼叫队列以及自动助理<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2374e-151">Manage voice, including calling policies, phone number inventory and assignment, call queues, and auto attendants<sup>1</sup></span></span><br><br><span data-ttu-id="2374e-152">管理消息，包括消息策略<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2374e-152">Manage messaging, including messaging policies<sup>1</sup></span></span><br><br><span data-ttu-id="2374e-153">管理组织范围的所有设置，包括联合、Teams 升级和 Teams 客户端设置<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2374e-153">Manage all org-wide settings, including federation, Teams upgrade, and Teams client settings<sup>1</sup></span></span><br><br><span data-ttu-id="2374e-154">管理组织中的团队及其关联的设置，包括成员身份<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="2374e-154">Manage the teams in the organization and their associated settings, including membership<sup>2</sup></span></span><br><br><span data-ttu-id="2374e-155">查看用户配置文件页面，以及使用高级故障排除工具集解决用户通话质量问题<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2374e-155">View the user profile page and troubleshoot user call quality problems by using advanced troubleshooting toolset<sup>3</sup></span></span></td>
</tr>
<tr>
<td valign="top" colspan="2"><span data-ttu-id="2374e-156">Teams 通信管理员</span><span class="sxs-lookup"><span data-stu-id="2374e-156">Teams Communications Administrator</span></span></td>
<td valign="top"><span data-ttu-id="2374e-157">在 Microsoft Teams 服务中管理通话和会议功能</span><span class="sxs-lookup"><span data-stu-id="2374e-157">Manage calling and meetings features within the Microsoft Teams service</span></span></td>
<td valign="top"><span data-ttu-id="2374e-158">管理会议，包括会议策略、配置和会议网桥<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2374e-158">Manage meetings, including meeting policies, configurations, and conference bridges<sup>1</sup></span></span><br><br><span data-ttu-id="2374e-159">管理语音，包括通话策略、电话号码存量和分配、呼叫队列以及自动助理<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2374e-159">Manage voice, including calling policies, phone number inventory and assignment, call queues, and auto attendants<sup>1</sup></span></span><br><br><span data-ttu-id="2374e-160">查看用户配置文件页面，以及使用高级故障排除工具集解决用户通话质量问题<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2374e-160">View user profile page and troubleshoot user call quality problems using advanced troubleshooting toolset<sup>1</sup></span></span></td>
</tr>
<tr>
<td valign="top" colspan="2"><span data-ttu-id="2374e-161">Teams 通信专家</span><span class="sxs-lookup"><span data-stu-id="2374e-161">Teams Communications Specialist</span></span></td>
<td valign="top"><span data-ttu-id="2374e-162">使用基本工具解决 Teams 中的通信问题</span><span class="sxs-lookup"><span data-stu-id="2374e-162">Troubleshoot communications issues within Teams by using basic tools</span></span></td>
<td valign="top"><span data-ttu-id="2374e-163">访问用户配置文件页面以对通话分析中的通话进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="2374e-163">Access to the user profile page for troubleshooting calls in Call Analytics.</span></span> <span data-ttu-id="2374e-164">只能查看搜索的特定用户的用户信息。<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2374e-164">Can only view user information for the specific user being searched for.<sup>3</sup></span></span></td>
</tr>
<tr>
<td valign="top" colspan="2"><span data-ttu-id="2374e-165">Teams 通信支持工程师</span><span class="sxs-lookup"><span data-stu-id="2374e-165">Teams Communications Support Engineer</span></span></td>
<td valign="top"><span data-ttu-id="2374e-166">使用高级工具解决 Teams 中的通信问题</span><span class="sxs-lookup"><span data-stu-id="2374e-166">Troubleshoot communications issues within Teams by using advanced tools</span></span></td>
<td valign="top"><span data-ttu-id="2374e-167">访问用户配置文件页面以对通话分析中的通话进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="2374e-167">Access to the user profile page for troubleshooting calls in Call Analytics.</span></span> <span data-ttu-id="2374e-168">可以查看完整的通话记录信息。<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2374e-168">Can view the full call record information.<sup>3</sup></span></span></td>
</tr>
<tr>
</tbody>
<tfoot>
<tr><td align="right"><span data-ttu-id="2374e-169"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2374e-169"><sup>1</sup></span></span></td><td colspan="3"><span data-ttu-id="2374e-170"><a href="https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell
">PowerShell—Skype for Business 模块</a>或 <a href="https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center">Microsoft Teams 管理中心</a></span><span class="sxs-lookup"><span data-stu-id="2374e-170"><a href="https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell
">PowerShell—Skype for Business module</a> or <a href="https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center">Microsoft Teams admin center</a></span></span></td></tr>
<tr><td align="right"><span data-ttu-id="2374e-171"><sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="2374e-171"><sup>2</sup></span></span></td><td colspan="3"><span data-ttu-id="2374e-172"><a href="https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3">PowerShell—Microsoft Teams 模块</a>或 <a href="https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center">Microsoft Teams 管理中心</a></span><span class="sxs-lookup"><span data-stu-id="2374e-172"><a href="https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3">PowerShell—Microsoft Teams module</a> or <a href="https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center">Microsoft Teams admin center</a></span></span></td></tr>
<tr><td align="right"><span data-ttu-id="2374e-173"><sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2374e-173"><sup>3</sup></span></span></td><td colspan="3"><span data-ttu-id="2374e-174">仅 <a href="https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center">Microsoft Teams 管理中心</a></span><span class="sxs-lookup"><span data-stu-id="2374e-174"><a href="https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center">Microsoft Teams admin center</a> only</span></span></td>
</tr>
</tfoot>
</table>


## <a name="it-decisions-to-make-before-getting-started"></a><span data-ttu-id="2374e-175">开始之前要做出的 IT 决策</span><span class="sxs-lookup"><span data-stu-id="2374e-175">IT decisions to make before getting started</span></span>

<span data-ttu-id="2374e-176">在向组织推出 Teams 之前，应实施组织决定要求的所有治理策略。</span><span class="sxs-lookup"><span data-stu-id="2374e-176">Before you roll Teams out to your organization, implement any governance policies that your organization has decided it requires.</span></span> <span data-ttu-id="2374e-177">其中可以包括命名约定、过期策略、保留策略等各项。</span><span class="sxs-lookup"><span data-stu-id="2374e-177">These can include items like naming conventions, expiration policies, retention policies, and more.</span></span> <span data-ttu-id="2374e-178">一般而言，在整个组织中扩展部署之前实施这些要求要容易得多。</span><span class="sxs-lookup"><span data-stu-id="2374e-178">Generally speaking, it's much easier to implement these requirements prior to scaling your deployment across your organization.</span></span>

<span data-ttu-id="2374e-179">有关详细信息，请参阅[在 Teams 中规划治理](plan-teams-governance.md)。</span><span class="sxs-lookup"><span data-stu-id="2374e-179">For more information, see [Plan for governance in Teams](plan-teams-governance.md).</span></span>

## <a name="teams-lifecycle-stages"></a><span data-ttu-id="2374e-180">Teams 生命周期阶段</span><span class="sxs-lookup"><span data-stu-id="2374e-180">Teams lifecycle stages</span></span>

<span data-ttu-id="2374e-181">一般而言，团队会有与项目一致或实现某个目标的目的。</span><span class="sxs-lookup"><span data-stu-id="2374e-181">Generally speaking, a team has a purpose that's aligned with a project or accomplishing a goal.</span></span> <span data-ttu-id="2374e-182">即使团队是基于某个共同的兴趣而建的，团队成员身份也可能会随着时间而变化，并且讨论内容可能也会变得过时 - 只是在不同的团队中以稍微不同的方式同样出现。</span><span class="sxs-lookup"><span data-stu-id="2374e-182">Even if a team was formed based on a shared interest, the team membership will probably change over time and the discussion might grow stale—only to surface again in a slightly different way in a different team.</span></span>

<span data-ttu-id="2374e-183">每个团队都会经历开始（创建团队和设置频道）、中间（使用团队，进行协作以符合工作流的节奏）以及（有时）结束（团队实现其目的，到达其有效期限终点）。</span><span class="sxs-lookup"><span data-stu-id="2374e-183">Each team has a beginning, when the team is created and the channels are set up; a middle, when the team is used and collaboration occurs to match the rhythm of the workflow; and—sometimes—an end, when the team has completed its purpose and reached the end of its useful life.</span></span> 

<span data-ttu-id="2374e-184">有关详细信息，请参见[在 Microsoft Teams 管理中心中管理团队](manage-teams-in-modern-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="2374e-184">For more information, see [Manage teams in the Microsoft Teams admin center](manage-teams-in-modern-portal.md).</span></span>

### <a name="stage-1-beginning"></a><span data-ttu-id="2374e-185">第 1 阶段：开始</span><span class="sxs-lookup"><span data-stu-id="2374e-185">Stage 1: Beginning</span></span>

#### <a name="create-the-team"></a><span data-ttu-id="2374e-186">创建团队</span><span class="sxs-lookup"><span data-stu-id="2374e-186">Create the team</span></span>

<span data-ttu-id="2374e-187">第一步是定义团队的目标（可以是业务流程、组织结构或项目，或者只是创建一个开放的非结构化协作中心）。</span><span class="sxs-lookup"><span data-stu-id="2374e-187">The first step is to define the goal of the team (which can range from business processes to org structure to projects, or simply creating an open, unstructured collaboration hub).</span></span> <span data-ttu-id="2374e-188">定义团队目标的同时要确定合适的人员。</span><span class="sxs-lookup"><span data-stu-id="2374e-188">Defining the team goal goes hand in hand with identifying the right people.</span></span> <span data-ttu-id="2374e-189">在切实可行的范围内，建议力求包含广泛的成员身份来培养开放性的协作。</span><span class="sxs-lookup"><span data-stu-id="2374e-189">As far as practicable, it's a good idea to foster open collaboration by aiming for broad membership.</span></span> 

<span data-ttu-id="2374e-190">团队所有者邀请团队成员、设置团队图片和说明，并可以为各个成员设置权限。</span><span class="sxs-lookup"><span data-stu-id="2374e-190">Team owners invite team members, set the team picture and description, and can set permissions for individual members.</span></span> 

> [!Tip]
>  <span data-ttu-id="2374e-191">最好是至少确定两名团队所有者，以便考虑到缺席或重新分配的情况。</span><span class="sxs-lookup"><span data-stu-id="2374e-191">It's optimal to identify at least two team owners, to account for absence or reassignment.</span></span>

#### <a name="team-origins"></a><span data-ttu-id="2374e-192">团队起源</span><span class="sxs-lookup"><span data-stu-id="2374e-192">Team origins</span></span>

<span data-ttu-id="2374e-193">可以采用各种方法创建团队，其中包括：</span><span class="sxs-lookup"><span data-stu-id="2374e-193">Teams can originate from a variety of methods, including:</span></span>

-   <span data-ttu-id="2374e-194">从头开始创建团队。</span><span class="sxs-lookup"><span data-stu-id="2374e-194">Create the team from scratch.</span></span> <span data-ttu-id="2374e-195">通过使用各个电子邮件别名或用户名添加成员，或者扩展通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="2374e-195">Add members by using individual email aliases or usernames, or expand a distribution list.</span></span>
-   <span data-ttu-id="2374e-196">基于某个现有团队创建团队，并将其频道配置和任何应用配置用作模板。</span><span class="sxs-lookup"><span data-stu-id="2374e-196">Create the team from an existing team, and use its channel configuration and any app configuration as a template.</span></span> <span data-ttu-id="2374e-197">你也可以选择使用其成员身份列表。</span><span class="sxs-lookup"><span data-stu-id="2374e-197">You can optionally also use its membership list.</span></span>
-   <span data-ttu-id="2374e-198">将某个团队添加到某个现有 Microsoft 365 组，这还会为该团队提供访问其邮箱和 SharePoint 站点的权限。</span><span class="sxs-lookup"><span data-stu-id="2374e-198">Add a team to an existing Microsoft 365 group, which also gives the team access to its mailbox and SharePoint site.</span></span>
-   <span data-ttu-id="2374e-199">使用 Microsoft Graph Teams API 或 PowerShell cmdlet 创建团队。</span><span class="sxs-lookup"><span data-stu-id="2374e-199">Use the Microsoft Graph Teams APIs or PowerShell cmdlets to create teams.</span></span> <span data-ttu-id="2374e-200">这些 API 可以根据全球通讯簿属性（例如，区域或部门）或业务流程（例如，客户端参与或教室名册）以编程方式创建团队。</span><span class="sxs-lookup"><span data-stu-id="2374e-200">The APIs can programmatically create teams based on Global Address Book attributes (such as region or department) or business processes (client engagements or classroom rosters, for example).</span></span>

<span data-ttu-id="2374e-201">可访问以下链接获取有关组织团队的详细信息：</span><span class="sxs-lookup"><span data-stu-id="2374e-201">Use these links to get more information about organizing your teams:</span></span>

-   [<span data-ttu-id="2374e-202">在 Teams 中组织团队的最佳做法</span><span class="sxs-lookup"><span data-stu-id="2374e-202">Best practices for organizing teams in Teams</span></span>](best-practices-organizing.md)
-   [<span data-ttu-id="2374e-203">部署聊天、团队、频道和应用</span><span class="sxs-lookup"><span data-stu-id="2374e-203">Deploy chat, teams, channels, & apps</span></span>](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
-   [<span data-ttu-id="2374e-204">部署会议</span><span class="sxs-lookup"><span data-stu-id="2374e-204">Deploy meetings & conferencing</span></span>](deploy-meetings-microsoft-teams-landing-page.md)
-   [<span data-ttu-id="2374e-205">部署云语音</span><span class="sxs-lookup"><span data-stu-id="2374e-205">Deploy cloud voice</span></span>](cloud-voice-landing-page.md)


|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="2374e-207">决策点</span><span class="sxs-lookup"><span data-stu-id="2374e-207">Decision points</span></span>|<ul><li><span data-ttu-id="2374e-208">团队的目的是什么？</span><span class="sxs-lookup"><span data-stu-id="2374e-208">What's the purpose of the team?</span></span></li><li><span data-ttu-id="2374e-209">哪些人属于团队？</span><span class="sxs-lookup"><span data-stu-id="2374e-209">Who belongs on the team?</span></span></li><li><span data-ttu-id="2374e-210">团队是私人团队还是公共团队？</span><span class="sxs-lookup"><span data-stu-id="2374e-210">Will the team be private or public?</span></span></li><li><span data-ttu-id="2374e-211">新成员是否可以添加自己，或由团队所有者添加新成员？</span><span class="sxs-lookup"><span data-stu-id="2374e-211">Can new members add themselves or do team owners add them?</span></span></li><li><span data-ttu-id="2374e-212">哪些人有权创建频道或添加选项卡、聊天机器人和连接器？</span><span class="sxs-lookup"><span data-stu-id="2374e-212">Who will have permissions to create channels or add tabs, bots, and connectors?</span></span></li></ul> |
| ![描述后续步骤的图标](media/audio_conferencing_image9.png)<br/><span data-ttu-id="2374e-214">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2374e-214">Next steps</span></span>|<ul><li><span data-ttu-id="2374e-215">创建团队。</span><span class="sxs-lookup"><span data-stu-id="2374e-215">Create the team.</span></span></li><li><span data-ttu-id="2374e-216">规划频道。</span><span class="sxs-lookup"><span data-stu-id="2374e-216">Plan for channels.</span></span></li></ul>|


#### <a name="set-up-channels"></a><span data-ttu-id="2374e-217">设置频道</span><span class="sxs-lookup"><span data-stu-id="2374e-217">Set up channels</span></span>

<span data-ttu-id="2374e-218">任何团队所有者或有相应权限的成员都可以在团队中创建频道。</span><span class="sxs-lookup"><span data-stu-id="2374e-218">Any team owner or member with appropriate permissions can create channels in a team.</span></span> <span data-ttu-id="2374e-219">考虑每个频道的目标（其中包括围绕项目展开的协作、主题讨论内容或共同兴趣的各方面）这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="2374e-219">It's important to consider the goal of each channel—options include collaboration around projects, discussions of topics, or areas of common interest.</span></span> <span data-ttu-id="2374e-220">默认情况下，每个团队都包括一个常规频道；大多数团队需要更多频道，成员将会创建额外的频道。</span><span class="sxs-lookup"><span data-stu-id="2374e-220">By default, every team includes a General channel; most teams need more than this, and members will create additional channels.</span></span> <span data-ttu-id="2374e-221">可能会出现这些情况：随着新主题或项目的出现，频道集将会随之逐渐增加，讨论内容可能会超出其开始的频道的范围。</span><span class="sxs-lookup"><span data-stu-id="2374e-221">It's likely that the set of channels will grow organically as new topics or projects arise, and discussions might outgrow the channel they began in.</span></span>

<span data-ttu-id="2374e-222">为了引起大家的兴趣，频道所有者可以发布欢迎消息、将相关文档上载到“**文件**”选项卡，或者向频道添加选项卡或连接器。</span><span class="sxs-lookup"><span data-stu-id="2374e-222">To spark interest, the channel owner can post a welcome message, upload relevant documents to the **Files** tab, or add tabs or connectors to the channel.</span></span> <span data-ttu-id="2374e-223">所有者也可设置频道说明，并可以“自动收藏”重要频道，以便默认为所有团队成员列出这些频道。</span><span class="sxs-lookup"><span data-stu-id="2374e-223">The owner also sets the channel description, and can "auto-favorite" important channels so they're listed by default for all team members.</span></span>

<span data-ttu-id="2374e-224">在创建频道名称之前，请先考虑频道名称，因为在团队中重命名频道不会重命名 SharePoint 文档库中的相应文件夹，这可能导致最终用户混淆。</span><span class="sxs-lookup"><span data-stu-id="2374e-224">Consider channel names before creating them as renaming a channel in the team will not rename the corresponding folder in the SharePoint document library which can lead to end-user confusion.</span></span> 

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="2374e-226">决策点</span><span class="sxs-lookup"><span data-stu-id="2374e-226">Decision points</span></span>|<ul><li><span data-ttu-id="2374e-227">哪些初始频道将会添加到团队？</span><span class="sxs-lookup"><span data-stu-id="2374e-227">What initial channels will be added to the team?</span></span></li><li><span data-ttu-id="2374e-228">将会提供哪些有关添加新频道的指导（如果有）？</span><span class="sxs-lookup"><span data-stu-id="2374e-228">What guidance, if any, will be provided for adding new channels?</span></span> <span data-ttu-id="2374e-229">（它们将按项目、按主题或按其他内容进行设置？）</span><span class="sxs-lookup"><span data-stu-id="2374e-229">(Will they be set up by project, by topic, or ...?)</span></span></li></ul> |
| ![描述后续步骤的图标](media/audio_conferencing_image9.png)<br/><span data-ttu-id="2374e-231">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2374e-231">Next steps</span></span>|<ul><li><span data-ttu-id="2374e-232">创建初始频道</span><span class="sxs-lookup"><span data-stu-id="2374e-232">Create initial channels.</span></span></li><li><span data-ttu-id="2374e-233">发布欢迎消息。</span><span class="sxs-lookup"><span data-stu-id="2374e-233">Post a welcome message.</span></span></li><li><span data-ttu-id="2374e-234">开始协作。</span><span class="sxs-lookup"><span data-stu-id="2374e-234">Start collaborating.</span></span></li></ul>|

### <a name="stage-2-middle"></a><span data-ttu-id="2374e-235">第 2 阶段：中间</span><span class="sxs-lookup"><span data-stu-id="2374e-235">Stage 2: Middle</span></span>

<span data-ttu-id="2374e-236">随着团队合作的开始，团队成员身份和频道层次结构可能会开始发展变化。</span><span class="sxs-lookup"><span data-stu-id="2374e-236">As the teamwork begins, the team membership probably begins to evolve, along with the channel hierarchy.</span></span> <span data-ttu-id="2374e-237">除非需要严格控制和锁定团队，否则，建议鼓励进行探索，即使这会导致终结也是如此。</span><span class="sxs-lookup"><span data-stu-id="2374e-237">Unless the team needs to be strictly controlled and locked down, it's a good idea to encourage exploration even if it leads to dead ends.</span></span> <span data-ttu-id="2374e-238">随着用户越来越适应，他们可以尝试使用 \@团队提及功能、将频道标记为收藏项以及使用“常规”频道以习惯使用发布功能。</span><span class="sxs-lookup"><span data-stu-id="2374e-238">As users get more comfortable, they can experiment with \@team mentions, marking channels as favorite, and using the General channel to get comfortable with posting.</span></span> <span data-ttu-id="2374e-239">每个团队都不同；可通过使用来引导设计的发展变化。</span><span class="sxs-lookup"><span data-stu-id="2374e-239">Each team is different; let usage guide the evolution of the design.</span></span> <span data-ttu-id="2374e-240">可通过 Teams 报告功能来监控团队的使用情况和运行状况。</span><span class="sxs-lookup"><span data-stu-id="2374e-240">Monitor the usage and health of the team via Teams reporting capabilities.</span></span>

<span data-ttu-id="2374e-241">随着在 Teams 中启动和持续进行关键的组通信，信任、宽容和协作精神会随之逐渐增强。</span><span class="sxs-lookup"><span data-stu-id="2374e-241">Trust, tolerance, and a spirit of collaboration grow organically as key group communications are initiated and sustained in Teams.</span></span> <span data-ttu-id="2374e-242">团队成员会发现组对话优于一对一聊天的实用性。</span><span class="sxs-lookup"><span data-stu-id="2374e-242">Team members see the usefulness of group conversations over one-on-one chats.</span></span> <span data-ttu-id="2374e-243">各个团队都倾向于借助 Giphy 和贴纸等有趣的功能发展自己的个性。</span><span class="sxs-lookup"><span data-stu-id="2374e-243">Individual teams tend to develop their own personality, aided by fun features like Giphys and stickers.</span></span> <span data-ttu-id="2374e-244">同时，任何时候发生恶劣或粗鲁行为，务必要进行阻止。</span><span class="sxs-lookup"><span data-stu-id="2374e-244">At the same time, it's important that rogue or rude behavior be discouraged any time it occurs.</span></span>

<span data-ttu-id="2374e-245">由于团队是有活力的机体，偶尔需要对其进行检查和照顾。</span><span class="sxs-lookup"><span data-stu-id="2374e-245">Because teams are living organisms, they occasionally need to be checked on and cared for.</span></span> <span data-ttu-id="2374e-246">下面提供了一些最佳做法：</span><span class="sxs-lookup"><span data-stu-id="2374e-246">These are some best practices:</span></span>

- <span data-ttu-id="2374e-247">在其开始衰落时安排支持者维持其使用，以及发现并传播有创意的新行为。</span><span class="sxs-lookup"><span data-stu-id="2374e-247">Use champions to sustain usage if it starts to drop, and also to discover and propagate creative new behaviors.</span></span> 
- <span data-ttu-id="2374e-248">妥善地管理来宾，确保来宾的访问在业务需求终止时终止。</span><span class="sxs-lookup"><span data-stu-id="2374e-248">Manage guests judiciously, making sure their access ends when the business need ends.</span></span>
- <span data-ttu-id="2374e-249">鼓励成员使用线程化对话和主题行，以通过滚动频道来提高可见性和关注度。</span><span class="sxs-lookup"><span data-stu-id="2374e-249">Encourage members to use threaded conversations with subject lines to improve visibility and attention with scrolling through a channel.</span></span>
- <span data-ttu-id="2374e-250">允许频道随着业务需求而发展变化，根据需要添加新频道，允许旧频道停止使用（或者，如果这些频道包含敏感或临时性数据，根据你的保留要求，考虑将其存档或删除）。</span><span class="sxs-lookup"><span data-stu-id="2374e-250">Let channels evolve with business needs, adding new ones as necessary and allowing old ones to fade (or consider archiving or deleting them if they contain sensitive or ephemeral data, based on your retention requirements).</span></span>
- <span data-ttu-id="2374e-251">随着组扩大或出现基于兴趣的领域时，创建新团队。</span><span class="sxs-lookup"><span data-stu-id="2374e-251">Carve out new teams as larger groups or interest-based areas emerge.</span></span>
- <span data-ttu-id="2374e-252">尝试使用不同的频道协作，例如，频道会议或围绕文档展开的选项卡对话。</span><span class="sxs-lookup"><span data-stu-id="2374e-252">Try different channel collaborations, such as channel meetings or tab conversations around documents.</span></span>
- <span data-ttu-id="2374e-253">使用 Microsoft Teams 移动应用来提高参与度。</span><span class="sxs-lookup"><span data-stu-id="2374e-253">Use the Microsoft Teams mobile app to increase engagement.</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="2374e-255">决策点</span><span class="sxs-lookup"><span data-stu-id="2374e-255">Decision points</span></span>|<ul><li><span data-ttu-id="2374e-256">将由谁监控使用情况以发现问题？</span><span class="sxs-lookup"><span data-stu-id="2374e-256">Who will monitor usage to identify problems?</span></span></li><li><span data-ttu-id="2374e-257">将使用哪些指标来确定团队运行是否正常？</span><span class="sxs-lookup"><span data-stu-id="2374e-257">What metrics will be used to determine whether a team is healthy?</span></span></li><li><span data-ttu-id="2374e-258">确定已达到其有效期限终点的任何团队。</span><span class="sxs-lookup"><span data-stu-id="2374e-258">Identify any teams that have reached the end of their useful life.</span></span></li><li><span data-ttu-id="2374e-259">确定仍在用于某个目的但需要增强活力的不正常团队。</span><span class="sxs-lookup"><span data-stu-id="2374e-259">Identify unhealthy teams that still serve a purpose but need revitalizing.</span></span></li></ul> |
| ![描述后续步骤的图标](media/audio_conferencing_image9.png)<br/><span data-ttu-id="2374e-261">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2374e-261">Next step</span></span>|<ul><li><span data-ttu-id="2374e-262">实施流程以监控各个团队运行状况。</span><span class="sxs-lookup"><span data-stu-id="2374e-262">Implement a process to monitor individual team health.</span></span></li></ul>|

### <a name="stage-3-end"></a><span data-ttu-id="2374e-263">第 3 阶段：结束</span><span class="sxs-lookup"><span data-stu-id="2374e-263">Stage 3: End</span></span>

<span data-ttu-id="2374e-264">当团队的工作完成时，务必要正式确认其已结束。</span><span class="sxs-lookup"><span data-stu-id="2374e-264">When the work of a team has run its course, it's important to formally acknowledge that it's over.</span></span> <span data-ttu-id="2374e-265">这是向团队成员告知结束，此外，也防止任何人访问已过时的陈旧信息。</span><span class="sxs-lookup"><span data-stu-id="2374e-265">This gives team members a sense of closure and also prevents anyone from accessing outdated, stale information.</span></span> <span data-ttu-id="2374e-266">你可以使用团队本身完成结束事项，例如，事后剖析和执行摘要。</span><span class="sxs-lookup"><span data-stu-id="2374e-266">You can use the team itself to conduct closure rituals like postmortems and executive summaries.</span></span>

<span data-ttu-id="2374e-267">你可以删除你知道不需要的团队（例如，只是为了测试而创建的团队，或包含敏感数据的团队）。</span><span class="sxs-lookup"><span data-stu-id="2374e-267">You can delete teams that you know you don't need (for example, a team created purely for testing or a team that contains sensitive data).</span></span> <span data-ttu-id="2374e-268">团队实际上是通过“软删除”进行删除的，IT 最长可以在 21 天内将其恢复（Microsoft 365 组是 30 天）。</span><span class="sxs-lookup"><span data-stu-id="2374e-268">Teams are actually deleted with a "soft delete" that IT can reverse for up to 21 days (30 days for Microsoft 365 Groups).</span></span> <span data-ttu-id="2374e-269">删除团队不会影响按照合规性策略保留的任何聊天或内容。</span><span class="sxs-lookup"><span data-stu-id="2374e-269">Deleting teams doesn't affect any chats or content that were retained in accordance with compliance policies.</span></span> <span data-ttu-id="2374e-270">频道也具有“软删除”，并且可在删除后的最长 21 天内恢复。</span><span class="sxs-lookup"><span data-stu-id="2374e-270">Channels also have a "soft delete" and can be reversed for up to 21 days after deletion.</span></span> <span data-ttu-id="2374e-271">删除频道不会从 SharePoint 文档库中删除文件夹或其内容。</span><span class="sxs-lookup"><span data-stu-id="2374e-271">Deleting a channel will not delete the folder or its contents from the SharePoint document library.</span></span>

<span data-ttu-id="2374e-272">你还可以使用过期和保留策略以及存档功能来减少公开不再使用或其所有者已离开组织的团队。</span><span class="sxs-lookup"><span data-stu-id="2374e-272">You can also use expiration and retention policies in addition to archiving capabilities to reduce exposure from teams that aren't active any longer or whose owners have left the organization.</span></span>

<span data-ttu-id="2374e-273">应用于 Teams 或相关服务（如 SharePoint）的保留策略可能会禁止删除团队。</span><span class="sxs-lookup"><span data-stu-id="2374e-273">Retention policies applied to Teams or associated services such as SharePoint may prohibit the deletion of teams.</span></span> <span data-ttu-id="2374e-274">此外，请考虑团队中的内容通常不仅仅是 SharePoint 文档库中的文件；它是对话、Planner 版块、Wiki、表单结果、录制的会议、OneNote 笔记本以及其他各种内容。</span><span class="sxs-lookup"><span data-stu-id="2374e-274">Additionally, consider that content in a team is often more than just files in the SharePoint document library; it is conversations, Planner boards, wikis, Forms results, recorded meetings, OneNote notebooks, and various others.</span></span>

<span data-ttu-id="2374e-275">有关设置过期和保留策略的信息，请参阅 [Microsoft Teams 中的安全性和合规性概述](security-compliance-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="2374e-275">For information about setting up expiration and retention policies, see [Overview of security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/><span data-ttu-id="2374e-277">决策点</span><span class="sxs-lookup"><span data-stu-id="2374e-277">Decision points</span></span>|<ul><li><span data-ttu-id="2374e-278">定义团队到达其期限终点时的情况。</span><span class="sxs-lookup"><span data-stu-id="2374e-278">Define what the end of a team's life looks like.</span></span></li><li><span data-ttu-id="2374e-279">决定是否使团队的内容保留可用，以及保留多长时间。</span><span class="sxs-lookup"><span data-stu-id="2374e-279">Decide whether to keep the content of a team available, and for how long.</span></span></li></ul> |
| ![描述后续步骤的图标](media/audio_conferencing_image9.png)<br/><span data-ttu-id="2374e-281">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2374e-281">Next steps</span></span>|<ul><li><span data-ttu-id="2374e-282">记录最佳做法以及经验与教训。</span><span class="sxs-lookup"><span data-stu-id="2374e-282">Document best practices and lessons learned.</span></span></li><li><span data-ttu-id="2374e-283">存档数据（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="2374e-283">Archive data, if necessary.</span></span></li></ul>|

## <a name="related-topics"></a><span data-ttu-id="2374e-284">相关主题</span><span class="sxs-lookup"><span data-stu-id="2374e-284">Related topics</span></span>

[<span data-ttu-id="2374e-285">Teams 的管控快速入门</span><span class="sxs-lookup"><span data-stu-id="2374e-285">Governance quick start for Teams</span></span>](teams-adoption-governance-quick-start.md)
