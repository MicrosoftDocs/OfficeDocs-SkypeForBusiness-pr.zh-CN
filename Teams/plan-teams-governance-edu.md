---
title: 面向 IT 专业人员的 Microsoft 教育版管理 FAQ - Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 对使用团队的 Microsoft 教育组的管理员提出的常见问题的解答。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b1bfa8f141f7aa8ce8dd258610ff8b510ff66aac
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237647"
---
# <a name="microsoft-education-governance-faq-for-admins"></a><span data-ttu-id="b4931-103">面向管理员的 Microsoft 教育版管理常见问题解答</span><span class="sxs-lookup"><span data-stu-id="b4931-103">Microsoft Education governance FAQ for admins</span></span>

> [!Tip]
> <span data-ttu-id="b4931-104">观看以下会话以了解有关 Microsoft 团队中的管理的详细信息: [Microsoft 团队中的管理、管理和生命周期](https://aka.ms/teams-governance)</span><span class="sxs-lookup"><span data-stu-id="b4931-104">Watch the following session to learn about more about management in Microsoft Teams: [Governance, management and lifecycle in Microsoft Teams](https://aka.ms/teams-governance)</span></span>

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a><span data-ttu-id="b4931-105">如何控制团队创建？</span><span class="sxs-lookup"><span data-stu-id="b4931-105">How do I control team creation?</span></span> <span data-ttu-id="b4931-106">我担心学生将创建不恰当的团队。</span><span class="sxs-lookup"><span data-stu-id="b4931-106">I'm worried students are going to create inappropriate teams.</span></span>

<span data-ttu-id="b4931-107">为避免使用不适当或误导的名称, 或者只是为团队命名方式提供更多的结构, 您可以使用 Office 365 组命名策略 (当前在预览中):</span><span class="sxs-lookup"><span data-stu-id="b4931-107">To avoid inappropriate or misleading names, or just to provide more structure for how teams are named, you can use the Office 365 Groups naming policy (currently in preview):</span></span>

-   <span data-ttu-id="b4931-108">**前缀-后缀命名策略**可以使用前缀或后缀定义团队 (组) 的命名约定, 例如, **GRP_US_My Group_Engineering**。</span><span class="sxs-lookup"><span data-stu-id="b4931-108">**Prefix-Suffix naming policy** You can use prefixes or suffixes to define the naming convention of teams (groups), for example, **GRP_US_My Group_Engineering**.</span></span> <span data-ttu-id="b4931-109">前缀和后缀可以是固定字符串或用户属性 (如 **[部门]**), 这些属性根据创建团队的用户添加到名称。</span><span class="sxs-lookup"><span data-stu-id="b4931-109">The prefixes and suffixes can be fixed strings or user attributes (such as **[Department]**) that are added to the name based on the user who’s creating the team.</span></span>
-   <span data-ttu-id="b4931-110">**自定义阻止的字词**你可以上载特定组织中的用户在其创建的团队名称中阻止使用的一组字词。</span><span class="sxs-lookup"><span data-stu-id="b4931-110">**Custom Blocked Words** You can upload a set of words that users in a specific organization are blocked from using in names of teams they create.</span></span> <span data-ttu-id="b4931-111">例如, 您可以阻止术语 " **CEO**"、"**工资单**" 和 "**人力资源**" 在不适用的组的团队名称中使用。</span><span class="sxs-lookup"><span data-stu-id="b4931-111">For example, you can block the terms **CEO**, **Payroll**, and **HR** from being used in team names for groups they don’t apply to.</span></span>
-   <span data-ttu-id="b4931-112">**分类**你可以创建你的组织中的用户在创建 Office 365 组时可以设置的分类。</span><span class="sxs-lookup"><span data-stu-id="b4931-112">**Classification** You can create classifications that the users in your organization can set when they create an Office 365 group.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="b4931-113">使用 Office 365 组命名策略要求属于一个或多个 Office 365 组成员的每个唯一用户的 Azure Active Directory Premium P1 许可证或 Azure AD 基本教育机构许可证。</span><span class="sxs-lookup"><span data-stu-id="b4931-113">Using the Office 365 Groups Naming Policy requires Azure Active Directory Premium P1 licenses or Azure AD Basic EDU licenses for each unique user that is a member of one or more Office 365 groups.</span></span>

<span data-ttu-id="b4931-114">有关详细说明, 请参阅[Office 组命名策略](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。</span><span class="sxs-lookup"><span data-stu-id="b4931-114">For detailed instructions, see [Office groups naming policy](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>

> [!Note]
> <span data-ttu-id="b4931-115">如果团队是使用来自其他系统 (如学校数据同步) 的输入自动创建的, 请验证输入数据是否符合您配置的命名策略;如果不是, 团队创建将失败。</span><span class="sxs-lookup"><span data-stu-id="b4931-115">If teams are created automatically by using the input from another system (for example, School Data Sync), verify that the input data complies with the naming policy you’ve configured; if it doesn’t, team creation will fail.</span></span>

## <a name="can-i-see-who-created-a-team"></a><span data-ttu-id="b4931-116">是否可以查看团队的创建者？</span><span class="sxs-lookup"><span data-stu-id="b4931-116">Can I see who created a team?</span></span>

<span data-ttu-id="b4931-117">若要了解创建特定团队的人员, 请参阅[在 Microsoft 团队中搜索事件的审核日志](audit-log-events.md)。</span><span class="sxs-lookup"><span data-stu-id="b4931-117">To find out who created a specific team, see [Search the audit log for events in Microsoft Teams](audit-log-events.md).</span></span>

## <a name="can-i-control-who-can-create-teams"></a><span data-ttu-id="b4931-118">是否可以控制哪些人可以创建团队？</span><span class="sxs-lookup"><span data-stu-id="b4931-118">Can I control who can create teams?</span></span>

<span data-ttu-id="b4931-119">一般情况下, 建议不要阻止任何人创建团队。</span><span class="sxs-lookup"><span data-stu-id="b4931-119">In general, we recommend against preventing anyone from creating teams.</span></span> <span data-ttu-id="b4931-120">如果每个人都可以创建团队, 则团队更有可能被广泛采纳。</span><span class="sxs-lookup"><span data-stu-id="b4931-120">If everyone can create teams, Teams is more likely to be widely adopted.</span></span> <span data-ttu-id="b4931-121">教职员工、教师或学生可以使用团队创建研究组或特殊兴趣组。</span><span class="sxs-lookup"><span data-stu-id="b4931-121">Faculty, teachers, or students can  use Teams to create study groups or special interest groups.</span></span> <span data-ttu-id="b4931-122">这将帮助在课堂内部和外部接受团队。</span><span class="sxs-lookup"><span data-stu-id="b4931-122">This will help Teams be accepted inside and outside of the classroom.</span></span>

<span data-ttu-id="b4931-123">在我们的经验中, 用户教育有助于确保负责人的使用。</span><span class="sxs-lookup"><span data-stu-id="b4931-123">In our experience, user education helps ensure responsible Teams usage.</span></span> <span data-ttu-id="b4931-124">一旦用户知道创建团队不是匿名的, 他们就会理解 carelessly 创建它们的含义, 并倾向于 shy 退出该工具。</span><span class="sxs-lookup"><span data-stu-id="b4931-124">As soon as users understand that creating teams isn’t anonymous, they understand the implications of carelessly creating them and tend to shy away from misusing the tool.</span></span>

<span data-ttu-id="b4931-125">如果您确定要控制哪些人可以创建团队, 请参阅[管理可创建 Office 365 组的人员](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)。</span><span class="sxs-lookup"><span data-stu-id="b4931-125">If you’re sure you want to control who can create teams, see [Manage who can create Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a><span data-ttu-id="b4931-126">如何在学期或季度的开始期间自动为每个课程创建团队？</span><span class="sxs-lookup"><span data-stu-id="b4931-126">How do I automatically create a team for each course at the beginning of the semester or quarter?</span></span>

<span data-ttu-id="b4931-127">在每个学期或季度开始时, 您将需要许多新团队。</span><span class="sxs-lookup"><span data-stu-id="b4931-127">At the start of each semester or quarter, you’ll need a number of new teams.</span></span> <span data-ttu-id="b4931-128">使用自动化方法自动创建这些团队、使用适当的用户填充它们以及设置正确的权限, 这可能会有意义:</span><span class="sxs-lookup"><span data-stu-id="b4931-128">It might make sense to take an automated approach to create these teams automatically, populate them with the right users, and set the right permissions:</span></span>

-   <span data-ttu-id="b4931-129">学校数据同步可为 Exchange Online 和 SharePoint Online 创建 Office 365 组、Microsoft 团队的课堂团队和 OneNote 课堂笔记本、用于 Intune 教育的学校组以及 rostering 和单一登录 (SSO) 集成第三方应用程序。</span><span class="sxs-lookup"><span data-stu-id="b4931-129">School Data Sync can create Office 365 Groups for Exchange Online and SharePoint Online, class teams for Microsoft Teams and OneNote Class notebooks, school groups for Intune for Education, and rostering and single sign-on (SSO) integration for many other third-party applications.</span></span> <span data-ttu-id="b4931-130">了解有关[学校数据同步的概览的](https://docs.microsoft.com/schooldatasync/overview-of-school-data-sync)详细信息。</span><span class="sxs-lookup"><span data-stu-id="b4931-130">Learn more at [Overview of School Data Sync](https://docs.microsoft.com/schooldatasync/overview-of-school-data-sync).</span></span>
-   <span data-ttu-id="b4931-131">通过 PowerShell, 你可以创建团队和频道, 并自动配置设置。</span><span class="sxs-lookup"><span data-stu-id="b4931-131">With PowerShell, you can create teams and channels, and configure settings automatically.</span></span> <span data-ttu-id="b4931-132">有关详细信息, 请参阅[Microsoft 团队 PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 。</span><span class="sxs-lookup"><span data-stu-id="b4931-132">See [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
-   <span data-ttu-id="b4931-133">你可以使用 Microsoft Graph API (当前在 beta 中) 来创建、配置、克隆和存档团队。</span><span class="sxs-lookup"><span data-stu-id="b4931-133">You can use the Microsoft Graph API (currently in beta) to create, configure, clone, and archive teams.</span></span> <span data-ttu-id="b4931-134">有关详细信息, 请参阅[使用 Microsoft GRAPH API 处理 Microsoft 团队](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)。</span><span class="sxs-lookup"><span data-stu-id="b4931-134">See [Use the Microsoft Graph API to work with Microsoft Teams](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) for more information.</span></span>

> [!TIP]
> <span data-ttu-id="b4931-135">学校数据同步为每个已同步的类创建 Office 365 组, 并[启用隐藏的组成员身份](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945), 以便只有课堂中的教师和学生才能看到该类的成员。</span><span class="sxs-lookup"><span data-stu-id="b4931-135">School Data Sync creates an Office 365 group for each class synced and [enables hidden group membership](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) so only teachers and students within the class can see the members of that class.</span></span> <span data-ttu-id="b4931-136">如果使用不同的进程创建类组, 请使用 UnifiedGroup cmdlet 的 HiddenGroupMembershipEnabled 参数来满足相同的隐私要求。</span><span class="sxs-lookup"><span data-stu-id="b4931-136">If using a different process to create class groups use the HiddenGroupMembershipEnabled parameter of the New-UnifiedGroup cmdlet to meet the same privacy requirements.</span></span>

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a><span data-ttu-id="b4931-137">在学期或季度结束时如何处理团队？</span><span class="sxs-lookup"><span data-stu-id="b4931-137">How do I deal with teams when the semester or quarter ends?</span></span>

<span data-ttu-id="b4931-138">我们建议您首先考虑在学校半学期或季度结束时如何处理团队数据: 是删除它还是让学生在完成课程后仍可供学生使用。</span><span class="sxs-lookup"><span data-stu-id="b4931-138">We recommend that you first think about how you want to handle Teams data when the school semester or quarter is over: whether to delete it or keep it available for students even after they’ve completed the course.</span></span> <span data-ttu-id="b4931-139">您需要记住学校日历, 以便您设置的任何策略不会与假日冲突。</span><span class="sxs-lookup"><span data-stu-id="b4931-139">You’ll want to keep the school calendar in mind so any policies you set don’t conflict with holidays.</span></span> <span data-ttu-id="b4931-140">你可以使用以下工具实现你的策略:</span><span class="sxs-lookup"><span data-stu-id="b4931-140">You can use the following tools to implement your strategy:</span></span>

-   <span data-ttu-id="b4931-141">**保留策略:** 使用此功能可删除早于指定时期的所有数据, 以确保从聊天中删除旧数据 (适用于所有或部分用户) 和频道。</span><span class="sxs-lookup"><span data-stu-id="b4931-141">**Retention policy:** Use this to delete all data older than an age you specify to make sure that old data is removed from chats (for all or some users) and channels.</span></span> <span data-ttu-id="b4931-142">您还可以将团队配置为保留内容, 使其无法删除。</span><span class="sxs-lookup"><span data-stu-id="b4931-142">You can also configure Teams to retain content so it can’t be deleted.</span></span> <span data-ttu-id="b4931-143">有关详细信息, 请参阅[Microsoft 团队的保留策略](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011)。</span><span class="sxs-lookup"><span data-stu-id="b4931-143">For more information, see [Retention policies for Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011).</span></span>
-   <span data-ttu-id="b4931-144">**过期策略:** 将团队配置为在特定天数后过期。</span><span class="sxs-lookup"><span data-stu-id="b4931-144">**Expiry policy:** Configure teams to expire after a certain number of days.</span></span> <span data-ttu-id="b4931-145">过期之前的三十天, 将通知团队的所有所有者需要续订其团队, 否则将被删除 (尽管管理员可以恢复已删除的团队还需30天)。</span><span class="sxs-lookup"><span data-stu-id="b4931-145">Thirty days before expiration, all owners of a team are notified that their team needs to be renewed, otherwise it will be deleted (though an administrator can recover deleted teams for an additional 30 days).</span></span> <span data-ttu-id="b4931-146">此设置对于确保未使用的团队 sunsetted 非常有用。</span><span class="sxs-lookup"><span data-stu-id="b4931-146">This setting is very useful for making sure unused teams are sunsetted.</span></span> <span data-ttu-id="b4931-147">有关详细信息, 请参阅[Office 365 组过期策略](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733)。</span><span class="sxs-lookup"><span data-stu-id="b4931-147">Learn more at [Office 365 Group Expiration Policy](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733).</span></span>

-   <span data-ttu-id="b4931-148">**存档团队:** 此设置将团队置于只读模式。</span><span class="sxs-lookup"><span data-stu-id="b4931-148">**Archive team:** This setting puts teams into read-only mode.</span></span> <span data-ttu-id="b4931-149">它们仍然可以被浏览和搜索, 但没有人可以添加任何新帖子。</span><span class="sxs-lookup"><span data-stu-id="b4931-149">They can still be browsed and searched, but no one can add any new posts.</span></span> <span data-ttu-id="b4931-150">[存档或还原团队](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)介绍团队所有者如何存档团队。团队所有者还可以使用[GRAPH API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)来存档或还原团队。</span><span class="sxs-lookup"><span data-stu-id="b4931-150">[Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) describes how team owners can archive a team; Team owners can also use the [Graph API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) to archive or restore a team.</span></span>
 
> [!IMPORTANT]
> <span data-ttu-id="b4931-151">使用 Office 365 组过期策略要求属于一个或多个 Office 365 组成员的每个唯一用户的 Azure Active Directory Premium P1 许可证。</span><span class="sxs-lookup"><span data-stu-id="b4931-151">Using the Office 365 Groups Expiration Policy requires Azure Active Directory Premium P1 licenses for each unique user that is a member of one or more Office 365 groups.</span></span>

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a><span data-ttu-id="b4931-152">我的教职员是否有团队模板可供我创建团队时使用？</span><span class="sxs-lookup"><span data-stu-id="b4931-152">Are there team templates for my faculty members to use when creating a team?</span></span>

<span data-ttu-id="b4931-153">是。</span><span class="sxs-lookup"><span data-stu-id="b4931-153">Yes.</span></span> <span data-ttu-id="b4931-154">创建新团队时, 用户可以**从现有模板中选择 "创建团队**", 团队所有者还可以使用[图形 API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)从可用模板创建新团队。</span><span class="sxs-lookup"><span data-stu-id="b4931-154">Users can select **Create Team from existing template** when creating a new team, and Teams owners can also use the [Graph API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) to create a new team from the available templates.</span></span>

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a><span data-ttu-id="b4931-155">我可以通过 PowerShell 或图形自动执行哪些任务？</span><span class="sxs-lookup"><span data-stu-id="b4931-155">What tasks can I automate via PowerShell or Graph?</span></span>

<span data-ttu-id="b4931-156">[Microsoft GRAPH API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)可以执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="b4931-156">The [Microsoft Graph API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) can do the following:</span></span>

-   <span data-ttu-id="b4931-157">创建团队。</span><span class="sxs-lookup"><span data-stu-id="b4931-157">Create a team.</span></span>
-   <span data-ttu-id="b4931-158">添加成员和所有者。</span><span class="sxs-lookup"><span data-stu-id="b4931-158">Add members and owners.</span></span>
-   <span data-ttu-id="b4931-159">添加频道。</span><span class="sxs-lookup"><span data-stu-id="b4931-159">Add channels.</span></span>
-   <span data-ttu-id="b4931-160">添加应用程序。</span><span class="sxs-lookup"><span data-stu-id="b4931-160">Add apps.</span></span>
-   <span data-ttu-id="b4931-161">通过克隆现有团队和获取其选项卡来为这些步骤提供快捷方式。</span><span class="sxs-lookup"><span data-stu-id="b4931-161">Shortcut those steps by cloning an existing team, and get its tabs too.</span></span>
-   <span data-ttu-id="b4931-162">向用户提供您刚创建的团队的链接。</span><span class="sxs-lookup"><span data-stu-id="b4931-162">Give the user a link to the team you just created.</span></span>
-   <span data-ttu-id="b4931-163">当不再需要成员、所有者、频道和应用时, 可将其删除。</span><span class="sxs-lookup"><span data-stu-id="b4931-163">Remove members, owners, channels, and apps when you no longer need them.</span></span>
-   <span data-ttu-id="b4931-164">如果团队不再处于活动状态, 则将其存档。</span><span class="sxs-lookup"><span data-stu-id="b4931-164">Archive the team when it's no longer active.</span></span> 
-   <span data-ttu-id="b4931-165">删除团队。</span><span class="sxs-lookup"><span data-stu-id="b4931-165">Delete the team.</span></span>
-   <span data-ttu-id="b4931-166">创建通道线程</span><span class="sxs-lookup"><span data-stu-id="b4931-166">Create a channel thread</span></span>

<span data-ttu-id="b4931-167">[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)可以执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="b4931-167">[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) can do the following:</span></span>

-   <span data-ttu-id="b4931-168">创建团队。</span><span class="sxs-lookup"><span data-stu-id="b4931-168">Create a team.</span></span>
-   <span data-ttu-id="b4931-169">添加成员和所有者。</span><span class="sxs-lookup"><span data-stu-id="b4931-169">Add members and owners.</span></span>
-   <span data-ttu-id="b4931-170">添加频道。</span><span class="sxs-lookup"><span data-stu-id="b4931-170">Add channels.</span></span>
-   <span data-ttu-id="b4931-171">当不再需要成员、所有者和频道时, 可将其删除。</span><span class="sxs-lookup"><span data-stu-id="b4931-171">Remove members, owners, and channels when you no longer need them.</span></span>
-   <span data-ttu-id="b4931-172">删除团队。</span><span class="sxs-lookup"><span data-stu-id="b4931-172">Delete the team.</span></span>

> [!TIP]
> <span data-ttu-id="b4931-173">Graph API 和 PowerShell cmdlet 不断添加功能。</span><span class="sxs-lookup"><span data-stu-id="b4931-173">The Graph API and PowerShell cmdlets are constantly adding functionality.</span></span> <span data-ttu-id="b4931-174">请确保经常查看[Microsoft GRAPH API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)和[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)文章以获取功能增强。</span><span class="sxs-lookup"><span data-stu-id="b4931-174">Make sure to check the [Microsoft Graph API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) and [PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) articles often for feature enhancements.</span></span>  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a><span data-ttu-id="b4931-175">我是否可以控制我的教职员和学生可以访问的团队功能？</span><span class="sxs-lookup"><span data-stu-id="b4931-175">Can I control what Teams features my faculty and students have access to?</span></span>

<span data-ttu-id="b4931-176">是。</span><span class="sxs-lookup"><span data-stu-id="b4931-176">Yes.</span></span> <span data-ttu-id="b4931-177">你可以使用策略控制你的用户有权访问的特定消息、会议、调用和实时事件功能。</span><span class="sxs-lookup"><span data-stu-id="b4931-177">You can use policies to control specific messaging, meeting, calling, and live event features your users have access to.</span></span> <span data-ttu-id="b4931-178">你可以使用租户范围的设置将相同设置应用于所有设置, 或者根据需要应用用户级别策略。</span><span class="sxs-lookup"><span data-stu-id="b4931-178">You can use tenant-wide settings to apply the same settings to all, or apply user-level policies if required.</span></span> 

<span data-ttu-id="b4931-179">有关团队策略的更多详细信息, 请参阅[管理你的组织的 Microsoft 团队设置](enable-features-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="b4931-179">For more details about Teams policies, see [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a><span data-ttu-id="b4931-180">是否可以控制教职员工和学生协作的外部团体？</span><span class="sxs-lookup"><span data-stu-id="b4931-180">Can I control what external parties my faculty and students collaborate with?</span></span>

<span data-ttu-id="b4931-181">可以使用来宾访问邀请来自租户外部的用户, 这对于研究协作或来宾讲座非常有用:</span><span class="sxs-lookup"><span data-stu-id="b4931-181">You can use guest access to invite users from outside of your tenant, which can be useful for research collaboration or guest lectures:</span></span>

-   <span data-ttu-id="b4931-182">使用域 whitelisting 根据其域允许或阻止来宾。</span><span class="sxs-lookup"><span data-stu-id="b4931-182">Use domain whitelisting to allow or block guests based on their domain.</span></span>
-   <span data-ttu-id="b4931-183">为特定的 Office 365 组和团队打开和关闭来宾访问权限, 以控制哪些团队可以 (且无法) 邀请来宾。</span><span class="sxs-lookup"><span data-stu-id="b4931-183">Turn guest access on and off for particular Office 365 Groups and teams, to control which teams can (and can’t) invite guests.</span></span>
-   <span data-ttu-id="b4931-184">使用审核日志查看向受邀请的来宾发送了哪些警报。</span><span class="sxs-lookup"><span data-stu-id="b4931-184">Use the audit log to see which alerts were sent to invited guests.</span></span>

<span data-ttu-id="b4931-185">有关详细信息, 请参阅[Office 365 组中的来宾访问](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage)。</span><span class="sxs-lookup"><span data-stu-id="b4931-185">For more information, see [Guest access in Office 365 Groups](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage).</span></span>

## <a name="what-information-can-i-review-about-existing-teams"></a><span data-ttu-id="b4931-186">我可以查看有关现有团队的哪些信息？</span><span class="sxs-lookup"><span data-stu-id="b4931-186">What information can I review about existing teams?</span></span>

<span data-ttu-id="b4931-187">你可以查看审核日志以查看:</span><span class="sxs-lookup"><span data-stu-id="b4931-187">You can check the audit logs to see:</span></span>

-   <span data-ttu-id="b4931-188">被邀请成为哪个团队的来宾。</span><span class="sxs-lookup"><span data-stu-id="b4931-188">Who was invited as a guest to which team.</span></span>
-   <span data-ttu-id="b4931-189">创建了哪个团队。</span><span class="sxs-lookup"><span data-stu-id="b4931-189">Who created which team.</span></span>

<span data-ttu-id="b4931-190">有关详细信息, 请参阅[在 Microsoft 团队中搜索事件的审核日志](audit-log-events.md)。</span><span class="sxs-lookup"><span data-stu-id="b4931-190">For more information, see [Search the audit log for events in Microsoft Teams](audit-log-events.md).</span></span>

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a><span data-ttu-id="b4931-191">团队快速演变。</span><span class="sxs-lookup"><span data-stu-id="b4931-191">Teams evolves so quickly.</span></span> <span data-ttu-id="b4931-192">如何保持最新状态？</span><span class="sxs-lookup"><span data-stu-id="b4931-192">How can I stay up-to-date?</span></span>

<span data-ttu-id="b4931-193">我们建议使用以下资源来获取团队的最新更新:</span><span class="sxs-lookup"><span data-stu-id="b4931-193">We recommend the following resources to get the latest updates on Teams:</span></span>

-   [<span data-ttu-id="b4931-194">Microsoft 团队中的新增功能</span><span class="sxs-lookup"><span data-stu-id="b4931-194">What's new in Microsoft Teams</span></span>](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [<span data-ttu-id="b4931-195">Microsoft 团队博客</span><span class="sxs-lookup"><span data-stu-id="b4931-195">Microsoft Teams blog</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)
