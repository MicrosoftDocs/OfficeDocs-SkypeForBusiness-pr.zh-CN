---
title: 将 StaffHub 团队迁移到 Microsoft Teams 中的排班
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 3/29/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: 了解如何移动 Microsoft StaffHub 团队和安排到班次的 Microsoft 团队中的数据。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: fa224306f3d42d4746f8e8f2276b44208fc568bd
ms.sourcegitcommit: a505869a3cc2fe6fe4ee18bcbe99bf980aa91a86
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "31520213"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="525b4-103">将 Microsoft StaffHub 团队移动到引进中的 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="525b4-103">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="525b4-104">有效 2019 年 10 月 1，，Microsoft StaffHub 将要停用。</span><span class="sxs-lookup"><span data-stu-id="525b4-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="525b4-105">我们 StaffHub 功能构建到 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="525b4-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="525b4-106">如今，团队包括日程管理引进相关应用程序和其他功能将随着时间的推移推出。</span><span class="sxs-lookup"><span data-stu-id="525b4-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="525b4-107">StaffHub 上 2019 年 10 月 1，将停止的所有用户的工作。</span><span class="sxs-lookup"><span data-stu-id="525b4-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="525b4-108">尝试打开 StaffHub 的任何人都将显示一条消息，来下载团队。</span><span class="sxs-lookup"><span data-stu-id="525b4-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="525b4-109">若要了解详细信息，请参阅[Microsoft StaffHub 要停用](microsoft-staffhub-to-be-retired.md)。</span><span class="sxs-lookup"><span data-stu-id="525b4-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

> <span data-ttu-id="525b4-110">本文中讨论的功能不起作用尚未释放。</span><span class="sxs-lookup"><span data-stu-id="525b4-110">The capability discussed in this article hasn't yet been released.</span></span> <span data-ttu-id="525b4-111">它已公布，并且即将提供，达到年 4 月 2019年的末尾。</span><span class="sxs-lookup"><span data-stu-id="525b4-111">It's been announced, and is coming soon, towards the end of April 2019.</span></span> <span data-ttu-id="525b4-112">如果您是管理员，您可以了解时这将会出现在邮件中心 （在[Microsoft 365 管理中心](https://portal.office.com/adminportal/home)）。</span><span class="sxs-lookup"><span data-stu-id="525b4-112">If you're an admin, you can find out when this will be available in the Message Center (in the [Microsoft 365 admin center](https://portal.office.com/adminportal/home)).</span></span>

<span data-ttu-id="525b4-113">团队中的班次应用程序提供管理计划和常量流 shift 交换和取消通知发生在每天的简单方法。</span><span class="sxs-lookup"><span data-stu-id="525b4-113">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="525b4-114">团队成员可以访问其日程安排和班次信息直接应用程序中以及跨其设备设置其首选项，管理其日程安排，关闭请求的时间。</span><span class="sxs-lookup"><span data-stu-id="525b4-114">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="525b4-115">本文将指导您完成如何移动贵组织的 StaffHub 团队和安排到引进团队中的数据。</span><span class="sxs-lookup"><span data-stu-id="525b4-115">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="525b4-116">无论您是具有一个或两个 StaffHub 团队的小型企业或大型企业与数百个 StaffHub 团队，在此可以找到您需要帮助团队对成功进行转换的管理指南。</span><span class="sxs-lookup"><span data-stu-id="525b4-116">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="525b4-117">您必须是全局管理员才能执行本文中的步骤。</span><span class="sxs-lookup"><span data-stu-id="525b4-117">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="525b4-118">如果您尚未这样做，必须通过[StaffHub 退休常见问题](microsoft-staffhub-to-be-retired.md)查看获取您可能遇到的任何问题的解答。</span><span class="sxs-lookup"><span data-stu-id="525b4-118">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span> 

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="525b4-119">您需要了解的有关移动到团队</span><span class="sxs-lookup"><span data-stu-id="525b4-119">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="525b4-120">何时将移动到团队</span><span class="sxs-lookup"><span data-stu-id="525b4-120">When to move to Teams</span></span>

<span data-ttu-id="525b4-121">有效 2019 年 10 月 1，，StaffHub 将要停用。</span><span class="sxs-lookup"><span data-stu-id="525b4-121">Effective October 1, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="525b4-122">我们建议您开始立即使用团队并开始转换贵组织的团队和 StaffHub 用户。</span><span class="sxs-lookup"><span data-stu-id="525b4-122">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="525b4-123">与计划管理正在 StaffHub 中的最常用的功能，我们建议您使用引进应用程序在工作组中向前移动。</span><span class="sxs-lookup"><span data-stu-id="525b4-123">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="525b4-124">什么被移动到团队</span><span class="sxs-lookup"><span data-stu-id="525b4-124">What is moved to Teams</span></span>

<span data-ttu-id="525b4-125">用户的详细信息、 日程安排信息和聊天和文件数据转为团队。</span><span class="sxs-lookup"><span data-stu-id="525b4-125">User details, schedule information, and chat and file data are transitioned to Teams.</span></span> <span data-ttu-id="525b4-126">这包括团队成员资格、 工作组计划，和聊天室和最近 90 天的文件。</span><span class="sxs-lookup"><span data-stu-id="525b4-126">This includes team membership, team schedules, and chats and files from the last 90 days.</span></span>

<span data-ttu-id="525b4-127">每个 StaffHub 团队需要相应的 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="525b4-127">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="525b4-128">如果 StaffHub 团队没有与其关联的 Office 365 组，将自动为您支持转换创建一个。</span><span class="sxs-lookup"><span data-stu-id="525b4-128">If a StaffHub team doesn't have an Office 365 Group associated with it, one is automatically created for you to support the transition.</span></span> <span data-ttu-id="525b4-129">给定团队和组命名团队和 StaffHub 之间的差异，可能会看到团队中的不同的工作组名称。</span><span class="sxs-lookup"><span data-stu-id="525b4-129">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span>

<span data-ttu-id="525b4-130">如转换团队从 StaffHub 团队，用户在 StaffHub 中将不再有权访问其日程安排和重定向到团队中的变化。</span><span class="sxs-lookup"><span data-stu-id="525b4-130">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="525b4-131">我们建议您在整个组织大程度地减少中断并鼓励用户采用和研究团队通信此更改。</span><span class="sxs-lookup"><span data-stu-id="525b4-131">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span>

## <a name="prepare"></a><span data-ttu-id="525b4-132">准备</span><span class="sxs-lookup"><span data-stu-id="525b4-132">Prepare</span></span>

<span data-ttu-id="525b4-133">下面是如何准备要移到团队。</span><span class="sxs-lookup"><span data-stu-id="525b4-133">Here's how to prepare for the move to Teams.</span></span>

### <a name="assign-teams-licenses"></a><span data-ttu-id="525b4-134">分配 Teams 许可证</span><span class="sxs-lookup"><span data-stu-id="525b4-134">Assign Teams licenses</span></span>

<span data-ttu-id="525b4-135">每个用户必须具有活动的 Microsoft 365 或 Office 365 许可证从[合格的计划](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in)，并且必须分配团队许可证。</span><span class="sxs-lookup"><span data-stu-id="525b4-135">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan ](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="525b4-136">向用户分配的工作组许可证，这些访问团队。</span><span class="sxs-lookup"><span data-stu-id="525b4-136">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="525b4-137">管理 Microsoft 365 管理中心中的团队许可证。</span><span class="sxs-lookup"><span data-stu-id="525b4-137">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="525b4-138">若要了解详细信息，请参阅[管理用户对团队的访问权限](../../user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="525b4-138">To learn more, see [Manage user access to Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="525b4-139">如果您的组织使用 Skype for Business 并且您并不准备要迁移到团队的所有用户，可以将团队启用然后，可以运行旁 for Business 的 Skype 团队您 Firstline 工作者。</span><span class="sxs-lookup"><span data-stu-id="525b4-139">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="525b4-140">在此共存模式，调用*群岛*，每个客户端应用程序运行作为单独的解决方案。</span><span class="sxs-lookup"><span data-stu-id="525b4-140">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="525b4-141">若要了解详细信息，请参阅[了解团队和 Skype 的业务共存及互操作性](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md)。</span><span class="sxs-lookup"><span data-stu-id="525b4-141">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a><span data-ttu-id="525b4-142">设置的 Azure AD 中未标识 StaffHub 用户帐户</span><span class="sxs-lookup"><span data-stu-id="525b4-142">Provision accounts for StaffHub users who don't have an identity in Azure AD</span></span>

<span data-ttu-id="525b4-143">每个管理器和团队成员必须在 Azure Active Directory (Azure AD) 中具有标识。</span><span class="sxs-lookup"><span data-stu-id="525b4-143">Each manager and team member must have an identity in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="525b4-144">如果用户在 Azure AD 中没有 identity，这些设置的帐户。</span><span class="sxs-lookup"><span data-stu-id="525b4-144">If a user doesn't already have an identity in Azure AD, provision an account for them.</span></span> <span data-ttu-id="525b4-145">方法如下。</span><span class="sxs-lookup"><span data-stu-id="525b4-145">Here's how.</span></span>

- <span data-ttu-id="525b4-146">StaffHub 团队所有者和管理员可以将转换的虚拟或非活动帐户，并将其链接到 StaffHub 中的已设置帐户更改为有效的 UPN StaffHub 工作组设置页上的用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="525b4-146">StaffHub team owners and managers can convert a dummy or inactive account and link it to a provisioned account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="525b4-147">管理员可以运行[添加 StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps)并通过使用 UPN 备份[删除 StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) cmdlet 从 StaffHub 团队中移除的非设置的帐户和添加的帐户。</span><span class="sxs-lookup"><span data-stu-id="525b4-147">Admins can run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) and [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) cmdlets to remove a non-provisioned account from a StaffHub team and add the account back by using the UPN.</span></span>

### <a name="install-the-staffhub-powershell-module"></a><span data-ttu-id="525b4-148">安装 StaffHub PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="525b4-148">Install the StaffHub PowerShell module</span></span>

<span data-ttu-id="525b4-149">如果尚未[安装 StaffHub PowerShell 模块](install-the-staffhub-powershell-module.md)。</span><span class="sxs-lookup"><span data-stu-id="525b4-149">If you haven't already, [install the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span>

<span data-ttu-id="525b4-150">当移动 StaffHub 团队，先决条件检查的移动请求。</span><span class="sxs-lookup"><span data-stu-id="525b4-150">When you move a StaffHub team, the move request checks for prerequisites.</span></span> <span data-ttu-id="525b4-151">下面是移动请求可能无法的原因：</span><span class="sxs-lookup"><span data-stu-id="525b4-151">Here's reasons why a move request may fail:</span></span>

- <span data-ttu-id="525b4-152">已登录的用户不是全局管理员</span><span class="sxs-lookup"><span data-stu-id="525b4-152">The signed-in user is not a global admin</span></span>
- <span data-ttu-id="525b4-153">团队禁用租户中的所有用户</span><span class="sxs-lookup"><span data-stu-id="525b4-153">Teams is disabled for all users in the tenant</span></span>
- <span data-ttu-id="525b4-154">租户中禁用了组创建 office 365</span><span class="sxs-lookup"><span data-stu-id="525b4-154">Office 365 Groups creation is disabled in the tenant</span></span>
- <span data-ttu-id="525b4-155">StaffHub 团队 Id 无效或不包含任何成员</span><span class="sxs-lookup"><span data-stu-id="525b4-155">The StaffHub teamId is not valid or has no members</span></span>
- <span data-ttu-id="525b4-156">StaffHub 团队包括未链接到的 Azure AD 帐户的成员</span><span class="sxs-lookup"><span data-stu-id="525b4-156">The StaffHub team includes members that aren't linked to an Azure AD account</span></span>  

## <a name="run-a-pilot"></a><span data-ttu-id="525b4-157">试运行</span><span class="sxs-lookup"><span data-stu-id="525b4-157">Run a pilot</span></span>

<span data-ttu-id="525b4-158">我们建议您通过移动两个或三个 StaffHub 团队的一组选定的前期应用启动。</span><span class="sxs-lookup"><span data-stu-id="525b4-158">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="525b4-159">运行试验可帮助您优化您转换的计划，并确保您准备要迁移到团队贵组织的所有 StaffHub 小组。</span><span class="sxs-lookup"><span data-stu-id="525b4-159">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="525b4-160">它还标识拥护者可帮助您的组织内的推动采纳率。</span><span class="sxs-lookup"><span data-stu-id="525b4-160">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="525b4-161">如果您是小型企业用户不需要的阶段性的方法，此部分中的步骤可能只需向工作组从 StaffHub 进行切换。</span><span class="sxs-lookup"><span data-stu-id="525b4-161">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="525b4-162">确定试点团队</span><span class="sxs-lookup"><span data-stu-id="525b4-162">Identify pilot teams</span></span>

<span data-ttu-id="525b4-163">到达标识两个或三个试点团队。</span><span class="sxs-lookup"><span data-stu-id="525b4-163">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="525b4-164">所有团队成员应都提交到使用团队中引进管理其日程安排和通信和相互协作。</span><span class="sxs-lookup"><span data-stu-id="525b4-164">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="525b4-165">确定团队拥护者</span><span class="sxs-lookup"><span data-stu-id="525b4-165">Identify team champions</span></span>

<span data-ttu-id="525b4-166">跨试点团队确定拥护者和登记它们可帮助宣传引进。</span><span class="sxs-lookup"><span data-stu-id="525b4-166">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="525b4-167">团队拥护者是有关用途，热心共享他们自己的经验教训到团队成员提供支持和指导。</span><span class="sxs-lookup"><span data-stu-id="525b4-167">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="525b4-168">团队拥护者可以是团队所有者或管理员。</span><span class="sxs-lookup"><span data-stu-id="525b4-168">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="525b4-169">工作组成员都设置按专用时间让每个人都[获取团队客户端](../../get-clients.md)，登录到团队和签出其日程安排中引进，并启动彼此聊天，应确保团队拥护者。</span><span class="sxs-lookup"><span data-stu-id="525b4-169">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="525b4-170">用户已熟悉 StaffHub 将启动并正在运行快速引进中。</span><span class="sxs-lookup"><span data-stu-id="525b4-170">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="525b4-171">您还可以指向其[引进](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)帮助以获取其他帮助。</span><span class="sxs-lookup"><span data-stu-id="525b4-171">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team-coming-soon"></a><span data-ttu-id="525b4-172">移动 StaffHub 团队 （即将推出）</span><span class="sxs-lookup"><span data-stu-id="525b4-172">Move a StaffHub team (coming soon)</span></span>

<span data-ttu-id="525b4-173">使用以下步骤一次移动一个 StaffHub 团队。</span><span class="sxs-lookup"><span data-stu-id="525b4-173">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="525b4-174">我们建议您的试点工作组此方法。</span><span class="sxs-lookup"><span data-stu-id="525b4-174">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="525b4-175">更高版本，当您准备要迁移贵组织的所有 StaffHub 团队，请参阅[移动 StaffHub 团队](#move-your-staffhub-teams-coming-soon)有关的操作步骤一次移动多个团队。</span><span class="sxs-lookup"><span data-stu-id="525b4-175">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams-coming-soon) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="525b4-176">运行以下命令以移动 StaffHub 团队。</span><span class="sxs-lookup"><span data-stu-id="525b4-176">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -Identity <String>
```

<span data-ttu-id="525b4-177">下面是一个示例获取提交一个请求将 StaffHub 团队移动到团队时的响应。</span><span class="sxs-lookup"><span data-stu-id="525b4-177">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
    jobId   teamId                                      teamAlreadyInMicrosofteams  
    -----   ------                                      ------------          
        1   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   True
```

<span data-ttu-id="525b4-178">要检查的移动请求的状态，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="525b4-178">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <Int32>
```

<span data-ttu-id="525b4-179">下面是一个示例获取移动时的响应。</span><span class="sxs-lookup"><span data-stu-id="525b4-179">Here's an example of the response you get when a move is in progress.</span></span>

```
    jobId   status       teamId                                     isO365GroupCreated  Error
    -----   ------       ------                                     ------------------  -----    
        1   InProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  True                None
```

## <a name="make-the-transition-from-staffhub-to-teams"></a><span data-ttu-id="525b4-180">向工作组从 StaffHub 进行转换</span><span class="sxs-lookup"><span data-stu-id="525b4-180">Make the transition from StaffHub to Teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="525b4-181">认知度</span><span class="sxs-lookup"><span data-stu-id="525b4-181">Raise awareness</span></span>

<span data-ttu-id="525b4-182">在您准备好超越您的试点工作组并将您的组织 StaffHub 团队移至团队非常重要首先在组织间通信更改。</span><span class="sxs-lookup"><span data-stu-id="525b4-182">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="525b4-183">分布有关引进并切换到团队认知度，生成兴奋，并决定采用的单词。</span><span class="sxs-lookup"><span data-stu-id="525b4-183">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams-coming-soon"></a><span data-ttu-id="525b4-184">移动 StaffHub 团队 （即将推出）</span><span class="sxs-lookup"><span data-stu-id="525b4-184">Move your StaffHub teams (coming soon)</span></span>

<span data-ttu-id="525b4-185">使用以下步骤来批量移动 StaffHub 团队。</span><span class="sxs-lookup"><span data-stu-id="525b4-185">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="525b4-186">您可以选择移动贵组织的所有 StaffHub 小组或移动特定 StaffHub 团队。</span><span class="sxs-lookup"><span data-stu-id="525b4-186">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="525b4-187">如果您想要移动 StaffHub 团队需要一次，请参阅[移动 StaffHub 团队](#move-a-staffhub-team-coming-soon)。</span><span class="sxs-lookup"><span data-stu-id="525b4-187">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team-coming-soon).</span></span>

#### <a name="move-all-staffhub-teams-coming-soon"></a><span data-ttu-id="525b4-188">移动所有 StaffHub 团队 （即将推出）</span><span class="sxs-lookup"><span data-stu-id="525b4-188">Move all StaffHub teams (coming soon)</span></span>

<span data-ttu-id="525b4-189">运行以下命令以获取您的组织中的所有 StaffHub 团队的列表。</span><span class="sxs-lookup"><span data-stu-id="525b4-189">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant
```

<span data-ttu-id="525b4-190">然后，运行以下命令以移动所有团队。</span><span class="sxs-lookup"><span data-stu-id="525b4-190">Then, run the following to move all teams.</span></span>

```
$StaffHubTeams | foreach {Move-StaffHubTeam -Identity {$_.Id}}
```

<span data-ttu-id="525b4-191">下面是响应的一个示例。</span><span class="sxs-lookup"><span data-stu-id="525b4-191">Here's an example of the response.</span></span>

```
    jobId   teamId                                      teamAlreadyInMicrosofteams  
    -----   ------                                      ------------          
        1   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   True
        2   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   False
```

#### <a name="move-specific-staffhub-teams-coming-soon"></a><span data-ttu-id="525b4-192">移动特定 StaffHub 团队 （即将推出）</span><span class="sxs-lookup"><span data-stu-id="525b4-192">Move specific StaffHub teams (coming soon)</span></span>

<span data-ttu-id="525b4-193">运行以下命令以获取您的组织中的所有 StaffHub 团队的列表。</span><span class="sxs-lookup"><span data-stu-id="525b4-193">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant
```

<span data-ttu-id="525b4-194">创建一个以逗号分隔值 (CSV) 文件并添加您要移动的团队的 Id。</span><span class="sxs-lookup"><span data-stu-id="525b4-194">Create a comma-separated values (CSV) file and add the IDs of the teams you want to move.</span></span>
<span data-ttu-id="525b4-195">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="525b4-195">Here's an example.</span></span>

|<span data-ttu-id="525b4-196">Id</span><span class="sxs-lookup"><span data-stu-id="525b4-196">Id</span></span>  |
|---------|
|<span data-ttu-id="525b4-197">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="525b4-197">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="525b4-198">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="525b4-198">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="525b4-199">TEAM_b42d0fa2-0 fc 9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="525b4-199">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="525b4-200">TEAM_b42d0fa2-0 fc 9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="525b4-200">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="525b4-201">然后，运行以下命令以移动 CSV 文件中指定的团队。</span><span class="sxs-lookup"><span data-stu-id="525b4-201">Then, run the following to move the teams you specified in the CSV file.</span></span>

```
Import-Csv .\teams.txt | foreach {Move-StaffHubTeam -Identity {$_.Id}}
```

## <a name="monitor-teams-usage"></a><span data-ttu-id="525b4-202">监视团队使用率</span><span class="sxs-lookup"><span data-stu-id="525b4-202">Monitor Teams usage</span></span>

<span data-ttu-id="525b4-203">使用率报告可帮助您更好地了解使用模式并为您在何处针对性，培训和通信在整个组织提供见解。</span><span class="sxs-lookup"><span data-stu-id="525b4-203">Usage reports can help you better understand usage patterns and give you insights on where to prioritize training and communication efforts across your organization.</span></span> <span data-ttu-id="525b4-204">由于引进团队中的应用程序，您可以查看使用率通过团队报告。</span><span class="sxs-lookup"><span data-stu-id="525b4-204">Because Shifts is an app in Teams, you can view usage through Teams reports.</span></span> <span data-ttu-id="525b4-205">有关详细信息，请参阅[团队报告在管理中心中的 Microsoft 团队](../../teams-analytics-and-reports/teams-reporting-reference.md)和[Microsoft 365 管理中心中的团队活动报告](../../teams-activity-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="525b4-205">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="525b4-206">相关主题</span><span class="sxs-lookup"><span data-stu-id="525b4-206">Related topics</span></span>
- [<span data-ttu-id="525b4-207">Microsoft StaffHub 将停用</span><span class="sxs-lookup"><span data-stu-id="525b4-207">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="525b4-208">在 Microsoft Teams 中为组织管理 Shifts 应用</span><span class="sxs-lookup"><span data-stu-id="525b4-208">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="525b4-209">StaffHub PowerShell 参考</span><span class="sxs-lookup"><span data-stu-id="525b4-209">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
