---
title: 面向 IT 专业人员的 Microsoft 教育版管理 FAQ - Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 08/10/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 使用团队的 Microsoft 教育组管理员从常见问题的答案。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 425dc91384dd97af1b61ab6c0a19d003e20330be
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33401596"
---
# <a name="microsoft-education-governance-faq-for-admins"></a><span data-ttu-id="4e2dd-103">面向管理员的 Microsoft 教育版管理常见问题解答</span><span class="sxs-lookup"><span data-stu-id="4e2dd-103">Microsoft Education governance FAQ for admins</span></span>

> [!Tip]
> <span data-ttu-id="4e2dd-104">观看下面的会话，若要了解有关 Microsoft 团队中的管理的详细信息：[监管、 管理和生命周期中的 Microsoft 团队](https://aka.ms/teams-governance)</span><span class="sxs-lookup"><span data-stu-id="4e2dd-104">Watch the following session to learn about more about management in Microsoft Teams: [Governance, management and lifecycle in Microsoft Teams](https://aka.ms/teams-governance)</span></span>

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a><span data-ttu-id="4e2dd-105">如何控制团队创建？</span><span class="sxs-lookup"><span data-stu-id="4e2dd-105">How do I control team creation?</span></span> <span data-ttu-id="4e2dd-106">我担心学生打算创建不正确的团队。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-106">I'm worried students are going to create inappropriate teams.</span></span>

<span data-ttu-id="4e2dd-107">若要避免不正确或令人误解的名称，或只是为了提供更多结构如何命名团队，您可以使用 Office 365 组命名策略 （当前中预览）：</span><span class="sxs-lookup"><span data-stu-id="4e2dd-107">To avoid inappropriate or misleading names, or just to provide more structure for how teams are named, you can use the Office 365 Groups naming policy (currently in preview):</span></span>

-   <span data-ttu-id="4e2dd-108">**前缀后缀命名策略**您可以使用前缀或后缀定义命名约定的团队 （组），例如， **GRP_US_My Group_Engineering**。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-108">**Prefix-Suffix naming policy** You can use prefixes or suffixes to define the naming convention of teams (groups), for example, **GRP_US_My Group_Engineering**.</span></span> <span data-ttu-id="4e2dd-109">可以固定前缀和后缀，字符串或用户属性 （如 **[部门]**） 添加到基于该团队创建用户的名称。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-109">The prefixes and suffixes can be fixed strings or user attributes (such as **[Department]**) that are added to the name based on the user who’s creating the team.</span></span>
-   <span data-ttu-id="4e2dd-110">**自定义阻止单词**您可以上载一套字词，阻止特定的组织中的用户使用他们创建的工作组的名称中。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-110">**Custom Blocked Words** You can upload a set of words that users in a specific organization are blocked from using in names of teams they create.</span></span> <span data-ttu-id="4e2dd-111">例如，可以阻止条款**CEO**、**工资**和**HR**在它们不应用于的组的工作组名称中使用。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-111">For example, you can block the terms **CEO**, **Payroll**, and **HR** from being used in team names for groups they don’t apply to.</span></span>
-   <span data-ttu-id="4e2dd-112">**分类**您可以创建您的组织中的用户创建 Office 365 组时可以设置的分类。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-112">**Classification** You can create classifications that the users in your organization can set when they create an Office 365 group.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="4e2dd-113">使用 Office 365 组命名策略将 Azure Active Directory Premium P1 许可证或 Azure AD 基本 EDU 许可证需要为每个唯一用户的一个或多个 Office 365 组的成员。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-113">Using the Office 365 Groups Naming Policy requires Azure Active Directory Premium P1 licenses or Azure AD Basic EDU licenses for each unique user that is a member of one or more Office 365 groups.</span></span>

<span data-ttu-id="4e2dd-114">有关详细说明，请参阅[Office 组命名策略](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-114">For detailed instructions, see [Office groups naming policy](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>

> [!Note]
> <span data-ttu-id="4e2dd-115">如果团队通过使用从其他系统 （例如，学校数据同步） 输入自动创建，请验证输入的数据符合命名策略已配置;如果它不，团队创建将失败。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-115">If teams are created automatically by using the input from another system (for example, School Data Sync), verify that the input data complies with the naming policy you’ve configured; if it doesn’t, team creation will fail.</span></span>

## <a name="can-i-see-who-created-a-team"></a><span data-ttu-id="4e2dd-116">可以查看工作组的创建者？</span><span class="sxs-lookup"><span data-stu-id="4e2dd-116">Can I see who created a team?</span></span>

<span data-ttu-id="4e2dd-117">若要了解特定的团队的创建者，请参阅[Search 中的 Microsoft 团队的事件的审核日志](audit-log-events.md)。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-117">To find out who created a specific team, see [Search the audit log for events in Microsoft Teams](audit-log-events.md).</span></span>

## <a name="can-i-control-who-can-create-teams"></a><span data-ttu-id="4e2dd-118">可以控制谁可以创建团队？</span><span class="sxs-lookup"><span data-stu-id="4e2dd-118">Can I control who can create teams?</span></span>

<span data-ttu-id="4e2dd-119">一般情况下，我们建议不要使任何人创建团队。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-119">In general, we recommend against preventing anyone from creating teams.</span></span> <span data-ttu-id="4e2dd-120">所有人都可以创建团队，团队更容易被广泛采用。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-120">If everyone can create teams, Teams is more likely to be widely adopted.</span></span> <span data-ttu-id="4e2dd-121">教师、 教师或学生可以使用团队创建研究组或感兴趣的组。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-121">Faculty, teachers, or students can  use Teams to create study groups or special interest groups.</span></span> <span data-ttu-id="4e2dd-122">这将帮助团队内部和外部课堂接受。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-122">This will help Teams be accepted inside and outside of the classroom.</span></span>

<span data-ttu-id="4e2dd-123">我们的经验，用户教育有助于确保负责团队使用率。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-123">In our experience, user education helps ensure responsible Teams usage.</span></span> <span data-ttu-id="4e2dd-124">只要用户了解创建团队不匿名，他们了解不小心创建它们的含义，并倾向于不愿意滥用工具。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-124">As soon as users understand that creating teams isn’t anonymous, they understand the implications of carelessly creating them and tend to shy away from misusing the tool.</span></span>

<span data-ttu-id="4e2dd-125">如果您确实要控制可以创建团队，请参阅[的 Manage 可以创建 Office 365 组](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-125">If you’re sure you want to control who can create teams, see [Manage who can create Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a><span data-ttu-id="4e2dd-126">如何自动创建每个课程的团队期末或一个季度的开头？</span><span class="sxs-lookup"><span data-stu-id="4e2dd-126">How do I automatically create a team for each course at the beginning of the semester or quarter?</span></span>

<span data-ttu-id="4e2dd-127">在每个期末或一个季度开始时，您将需要大量新团队。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-127">At the start of each semester or quarter, you’ll need a number of new teams.</span></span> <span data-ttu-id="4e2dd-128">可能有意义才能自动化的方法，以自动创建这些团队，其中填充正确的用户，并设置正确的权限：</span><span class="sxs-lookup"><span data-stu-id="4e2dd-128">It might make sense to take an automated approach to create these teams automatically, populate them with the right users, and set the right permissions:</span></span>

-   <span data-ttu-id="4e2dd-129">学校数据同步可以为 Exchange Online 和 SharePoint Online 的 Microsoft 团队和 OneNote 类笔记本的类团队、 用于教育和 rostering Intune 和单一登录 (SSO) 集成的许多其他学校组创建 Office 365 组第三方应用程序。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-129">School Data Sync can create Office 365 Groups for Exchange Online and SharePoint Online, class teams for Microsoft Teams and OneNote Class notebooks, school groups for Intune for Education, and rostering and single sign-on (SSO) integration for many other third-party applications.</span></span> <span data-ttu-id="4e2dd-130">有关详细信息[学校数据同步的概述](https://docs.microsoft.com/schooldatasync/overview-of-school-data-sync)。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-130">Learn more at [Overview of School Data Sync](https://docs.microsoft.com/schooldatasync/overview-of-school-data-sync).</span></span>
-   <span data-ttu-id="4e2dd-131">使用 PowerShell，您可以创建工作组和通道，并配置设置自动。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-131">With PowerShell, you can create teams and channels, and configure settings automatically.</span></span> <span data-ttu-id="4e2dd-132">有关详细信息，请参阅[Microsoft 团队 PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-132">See [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
-   <span data-ttu-id="4e2dd-133">可以使用 Microsoft Graph API （当前 beta) 中创建、 配置、 复制，并存档团队。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-133">You can use the Microsoft Graph API (currently in beta) to create, configure, clone, and archive teams.</span></span> <span data-ttu-id="4e2dd-134">有关详细信息，请参阅[使用 Microsoft Graph API 以使用 Microsoft 团队](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-134">See [Use the Microsoft Graph API to work with Microsoft Teams](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) for more information.</span></span>

> [!TIP]
> <span data-ttu-id="4e2dd-135">学校数据同步创建每个类同步，并[使隐藏的组成员身份](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945)的 Office 365 的组，以便仅教师和学生类中的可以看到该类的成员。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-135">School Data Sync creates an Office 365 group for each class synced and [enables hidden group membership](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) so only teachers and students within the class can see the members of that class.</span></span> <span data-ttu-id="4e2dd-136">如果使用不同的过程创建类组使用新建 UnifiedGroup cmdlet 的 HiddenGroupMembershipEnabled 参数以满足隐私要求相同。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-136">If using a different process to create class groups use the HiddenGroupMembershipEnabled parameter of the New-UnifiedGroup cmdlet to meet the same privacy requirements.</span></span>

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a><span data-ttu-id="4e2dd-137">我该如何处理与团队期末或一个季度结束时？</span><span class="sxs-lookup"><span data-stu-id="4e2dd-137">How do I deal with teams when the semester or quarter ends?</span></span>

<span data-ttu-id="4e2dd-138">我们建议您首先考虑有关您希望如何处理团队数据时学校期末或一个季度通过： 是否将其删除或使其可以学生的即使它们完成本课程。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-138">We recommend that you first think about how you want to handle Teams data when the school semester or quarter is over: whether to delete it or keep it available for students even after they’ve completed the course.</span></span> <span data-ttu-id="4e2dd-139">您需要学校日历请记住，因此您设置的任何策略与假日不会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-139">You’ll want to keep the school calendar in mind so any policies you set don’t conflict with holidays.</span></span> <span data-ttu-id="4e2dd-140">您可以使用以下工具来实现您的策略：</span><span class="sxs-lookup"><span data-stu-id="4e2dd-140">You can use the following tools to implement your strategy:</span></span>

-   <span data-ttu-id="4e2dd-141">**保留策略：** 用于删除早于指定以确保旧数据已从 （对于所有或某些用户） 的聊天和频道期限的所有数据。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-141">**Retention policy:** Use this to delete all data older than an age you specify to make sure that old data is removed from chats (for all or some users) and channels.</span></span> <span data-ttu-id="4e2dd-142">您还可以配置团队保留内容，因此不能删除它。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-142">You can also configure Teams to retain content so it can’t be deleted.</span></span> <span data-ttu-id="4e2dd-143">有关详细信息，请参阅[Microsoft 团队的保留策略](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011)。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-143">For more information, see [Retention policies for Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011).</span></span>
-   <span data-ttu-id="4e2dd-144">**到期策略：** 配置团队某些天后过期。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-144">**Expiry policy:** Configure teams to expire after a certain number of days.</span></span> <span data-ttu-id="4e2dd-145">到期日期之前的 30 天，其团队需要更新，否则它将被删除 （虽然其他 30 天，管理员可以恢复已删除的工作组） 通知的工作组的所有所有者。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-145">Thirty days before expiration, all owners of a team are notified that their team needs to be renewed, otherwise it will be deleted (though an administrator can recover deleted teams for an additional 30 days).</span></span> <span data-ttu-id="4e2dd-146">此设置是以确保未使用的团队 sunsetted 非常有用。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-146">This setting is very useful for making sure unused teams are sunsetted.</span></span> <span data-ttu-id="4e2dd-147">了解更多信息，请访问[Office 365 组过期策略](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733)。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-147">Learn more at [Office 365 Group Expiration Policy](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733).</span></span>

-   <span data-ttu-id="4e2dd-148">**存档团队：** 此设置将团队置于只读模式。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-148">**Archive team:** This setting puts teams into read-only mode.</span></span> <span data-ttu-id="4e2dd-149">它们可以仍浏览和搜索，但没有人可以添加任何新文章。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-149">They can still be browsed and searched, but no one can add any new posts.</span></span> <span data-ttu-id="4e2dd-150">[存档或还原团队](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)介绍如何团队所有者可以存档团队;团队所有者还可以使用[图形 API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)存档或还原团队。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-150">[Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) describes how team owners can archive a team; Team owners can also use the [Graph API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) to archive or restore a team.</span></span>
 
> [!IMPORTANT]
> <span data-ttu-id="4e2dd-151">使用 Office 365 组过期策略要求为每个唯一用户的一个或多个 Office 365 组的成员的 Azure Active Directory Premium P1 许可证。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-151">Using the Office 365 Groups Expiration Policy requires Azure Active Directory Premium P1 licenses for each unique user that is a member of one or more Office 365 groups.</span></span>

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a><span data-ttu-id="4e2dd-152">是否有我教职员工创建团队时要使用的工作组模板？</span><span class="sxs-lookup"><span data-stu-id="4e2dd-152">Are there team templates for my faculty members to use when creating a team?</span></span>

<span data-ttu-id="4e2dd-153">是。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-153">Yes.</span></span> <span data-ttu-id="4e2dd-154">创建一个新的团队时，用户可以选择**从现有模板创建团队**和团队所有者还可以使用[图形 API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)从可用的模板创建新的团队。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-154">Users can select **Create Team from existing template** when creating a new team, and Teams owners can also use the [Graph API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) to create a new team from the available templates.</span></span>

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a><span data-ttu-id="4e2dd-155">通过 PowerShell 或图形可以自动哪些任务？</span><span class="sxs-lookup"><span data-stu-id="4e2dd-155">What tasks can I automate via PowerShell or Graph?</span></span>

<span data-ttu-id="4e2dd-156">[Microsoft Graph API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4e2dd-156">The [Microsoft Graph API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) can do the following:</span></span>

-   <span data-ttu-id="4e2dd-157">创建工作组。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-157">Create a team.</span></span>
-   <span data-ttu-id="4e2dd-158">添加成员和所有者。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-158">Add members and owners.</span></span>
-   <span data-ttu-id="4e2dd-159">添加通道。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-159">Add channels.</span></span>
-   <span data-ttu-id="4e2dd-160">添加应用程序。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-160">Add apps.</span></span>
-   <span data-ttu-id="4e2dd-161">快捷方式通过克隆现有这些步骤团队，并太获取其选项卡。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-161">Shortcut those steps by cloning an existing team, and get its tabs too.</span></span>
-   <span data-ttu-id="4e2dd-162">向您刚创建的团队为用户提供一个链接。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-162">Give the user a link to the team you just created.</span></span>
-   <span data-ttu-id="4e2dd-163">当不再需要删除成员、 所有者、 通道和应用程序。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-163">Remove members, owners, channels, and apps when you no longer need them.</span></span>
-   <span data-ttu-id="4e2dd-164">不再处于活动状态时存档团队。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-164">Archive the team when it's no longer active.</span></span> 
-   <span data-ttu-id="4e2dd-165">删除团队。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-165">Delete the team.</span></span>
-   <span data-ttu-id="4e2dd-166">创建通道线程</span><span class="sxs-lookup"><span data-stu-id="4e2dd-166">Create a channel thread</span></span>

<span data-ttu-id="4e2dd-167">[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4e2dd-167">[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) can do the following:</span></span>

-   <span data-ttu-id="4e2dd-168">创建工作组。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-168">Create a team.</span></span>
-   <span data-ttu-id="4e2dd-169">添加成员和所有者。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-169">Add members and owners.</span></span>
-   <span data-ttu-id="4e2dd-170">添加通道。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-170">Add channels.</span></span>
-   <span data-ttu-id="4e2dd-171">当不再需要删除成员、 所有者和通道。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-171">Remove members, owners, and channels when you no longer need them.</span></span>
-   <span data-ttu-id="4e2dd-172">删除团队。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-172">Delete the team.</span></span>

> [!TIP]
> <span data-ttu-id="4e2dd-173">图形 API 和 PowerShell cmdlet 不断地将添加功能。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-173">The Graph API and PowerShell cmdlets are constantly adding functionality.</span></span> <span data-ttu-id="4e2dd-174">请确保要检查功能增强通常[Microsoft Graph API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)和[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)文章。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-174">Make sure to check the [Microsoft Graph API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) and [PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) articles often for feature enhancements.</span></span>  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a><span data-ttu-id="4e2dd-175">可以控制我教职员工和学生有权访问哪些团队功能？</span><span class="sxs-lookup"><span data-stu-id="4e2dd-175">Can I control what Teams features my faculty and students have access to?</span></span>

<span data-ttu-id="4e2dd-176">是。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-176">Yes.</span></span> <span data-ttu-id="4e2dd-177">您可以使用策略来控制特定消息、 会议、 通话，并 live 用户有权访问事件功能。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-177">You can use policies to control specific messaging, meeting, calling, and live event features your users have access to.</span></span> <span data-ttu-id="4e2dd-178">可以使用租户范围的设置相同的设置应用于所有，或如果需要应用用户级别策略。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-178">You can use tenant-wide settings to apply the same settings to all, or apply user-level policies if required.</span></span> 

<span data-ttu-id="4e2dd-179">有关团队策略的详细信息，请参阅[管理 Microsoft 团队设置为您的组织](enable-features-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-179">For more details about Teams policies, see [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a><span data-ttu-id="4e2dd-180">可以控制哪些外部方我教职员工和学生协作？</span><span class="sxs-lookup"><span data-stu-id="4e2dd-180">Can I control what external parties my faculty and students collaborate with?</span></span>

<span data-ttu-id="4e2dd-181">您可以使用来宾访问您的租户，可用于研究协作或来宾讲座之外邀请中的用户：</span><span class="sxs-lookup"><span data-stu-id="4e2dd-181">You can use guest access to invite users from outside of your tenant, which can be useful for research collaboration or guest lectures:</span></span>

-   <span data-ttu-id="4e2dd-182">使用域添加到白名单允许或阻止来宾根据其域。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-182">Use domain whitelisting to allow or block guests based on their domain.</span></span>
-   <span data-ttu-id="4e2dd-183">关闭来宾访问打开和关闭特定的 Office 365 组和团队以控制该团队可以 （并且不能） 邀请来宾。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-183">Turn guest access on and off for particular Office 365 Groups and teams, to control which teams can (and can’t) invite guests.</span></span>
-   <span data-ttu-id="4e2dd-184">使用审核日志来查看哪些通知发送到被邀请的来宾。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-184">Use the audit log to see which alerts were sent to invited guests.</span></span>

<span data-ttu-id="4e2dd-185">有关详细信息，请参阅[Office 365 组中的来宾访问](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage)。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-185">For more information, see [Guest access in Office 365 Groups](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage).</span></span>

## <a name="what-information-can-i-review-about-existing-teams"></a><span data-ttu-id="4e2dd-186">可以查看有关现有团队哪些信息？</span><span class="sxs-lookup"><span data-stu-id="4e2dd-186">What information can I review about existing teams?</span></span>

<span data-ttu-id="4e2dd-187">您可以检查审核日志，请参阅：</span><span class="sxs-lookup"><span data-stu-id="4e2dd-187">You can check the audit logs to see:</span></span>

-   <span data-ttu-id="4e2dd-188">被邀请以来宾身份到哪个工作组。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-188">Who was invited as a guest to which team.</span></span>
-   <span data-ttu-id="4e2dd-189">哪个团队的创建者。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-189">Who created which team.</span></span>

<span data-ttu-id="4e2dd-190">有关详细信息，请参阅[Search 中的 Microsoft 团队的事件的审核日志](audit-log-events.md)。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-190">For more information, see [Search the audit log for events in Microsoft Teams](audit-log-events.md).</span></span>

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a><span data-ttu-id="4e2dd-191">团队，以便快速发展。</span><span class="sxs-lookup"><span data-stu-id="4e2dd-191">Teams evolves so quickly.</span></span> <span data-ttu-id="4e2dd-192">如何保持最新状态？</span><span class="sxs-lookup"><span data-stu-id="4e2dd-192">How can I stay up-to-date?</span></span>

<span data-ttu-id="4e2dd-193">我们建议团队获取最新的更新的以下资源：</span><span class="sxs-lookup"><span data-stu-id="4e2dd-193">We recommend the following resources to get the latest updates on Teams:</span></span>

-   [<span data-ttu-id="4e2dd-194">What's new in Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="4e2dd-194">What's new in Microsoft Teams</span></span>](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [<span data-ttu-id="4e2dd-195">Microsoft 团队博客 （英文)</span><span class="sxs-lookup"><span data-stu-id="4e2dd-195">Microsoft Teams blog</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)
