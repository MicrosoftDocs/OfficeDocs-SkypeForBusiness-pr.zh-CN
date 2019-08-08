---
title: 将 StaffHub 团队迁移到 Microsoft Teams 中的排班
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何移动 Microsoft StaffHub 团队并将数据安排到 Microsoft 团队中的倒班。
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: cef8c6fbfd5ed0b19d6762b7508b311413d11066
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233279"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="a0392-103">将 Microsoft StaffHub 团队移动到 Microsoft 团队中的倒班</span><span class="sxs-lookup"><span data-stu-id="a0392-103">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a0392-104">2019年10月1日生效, Microsoft StaffHub 将停用。</span><span class="sxs-lookup"><span data-stu-id="a0392-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="a0392-105">我们正在将 StaffHub 功能构建到 Microsoft 团队中。</span><span class="sxs-lookup"><span data-stu-id="a0392-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="a0392-106">今天, 团队包括 "倒班" 应用, 用于计划管理, 而其他功能将随着时间的推移而推出。</span><span class="sxs-lookup"><span data-stu-id="a0392-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="a0392-107">StaffHub 将停止为2019年10月1日的所有用户工作。</span><span class="sxs-lookup"><span data-stu-id="a0392-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="a0392-108">任何试图打开 StaffHub 的人都将显示一条消息, 指导他们下载团队。</span><span class="sxs-lookup"><span data-stu-id="a0392-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="a0392-109">若要了解详细信息, 请参阅[Microsoft StaffHub 已停用](microsoft-staffhub-to-be-retired.md)。</span><span class="sxs-lookup"><span data-stu-id="a0392-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

<span data-ttu-id="a0392-110">团队中的倒班应用提供了一种简单的方法来管理计划, 以及每天发生的班次交换和取消的持续流。</span><span class="sxs-lookup"><span data-stu-id="a0392-110">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="a0392-111">团队成员可以直接在应用和其设备上访问其计划和转移信息, 以设置其首选项、管理其计划和请求超时。</span><span class="sxs-lookup"><span data-stu-id="a0392-111">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="a0392-112">本文将向你介绍如何移动组织的 StaffHub 团队并将数据安排到团队中的倒班。</span><span class="sxs-lookup"><span data-stu-id="a0392-112">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="a0392-113">它包括:</span><span class="sxs-lookup"><span data-stu-id="a0392-113">It covers:</span></span>

- [<span data-ttu-id="a0392-114">您需要了解的有关迁移到团队的哪些信息</span><span class="sxs-lookup"><span data-stu-id="a0392-114">What you need to know about the move to Teams</span></span>](#what-you-need-to-know-about-the-move-to-teams)
- [<span data-ttu-id="a0392-115">准备</span><span class="sxs-lookup"><span data-stu-id="a0392-115">Prepare</span></span>](#prepare)
- [<span data-ttu-id="a0392-116">执行试验</span><span class="sxs-lookup"><span data-stu-id="a0392-116">Conduct a pilot</span></span>](#conduct-a-pilot) 
- [<span data-ttu-id="a0392-117">超越您的试点和移动所有 StaffHub 团队</span><span class="sxs-lookup"><span data-stu-id="a0392-117">Go beyond your pilot and move all StaffHub teams</span></span>](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [<span data-ttu-id="a0392-118">监视团队使用情况</span><span class="sxs-lookup"><span data-stu-id="a0392-118">Monitor Teams usage</span></span>](#monitor-teams-usage)
- [<span data-ttu-id="a0392-119">过程</span><span class="sxs-lookup"><span data-stu-id="a0392-119">Troubleshooting</span></span>](#troubleshooting)

<span data-ttu-id="a0392-120">无论您是拥有一个或两个 StaffHub 团队的小型企业, 还是有数百个 StaffHub 团队的大型企业, 在这里, 您将找到所需的管理员指南, 帮助您成功过渡到团队。</span><span class="sxs-lookup"><span data-stu-id="a0392-120">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="a0392-121">只有全局管理员才能执行本文中的步骤。</span><span class="sxs-lookup"><span data-stu-id="a0392-121">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="a0392-122">如果尚未执行此操作, 请查看[StaffHub 退休常见问题](microsoft-staffhub-to-be-retired.md), 获取你可能遇到的任何问题的答案。</span><span class="sxs-lookup"><span data-stu-id="a0392-122">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span>

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="a0392-123">您需要了解的有关迁移到团队的哪些信息</span><span class="sxs-lookup"><span data-stu-id="a0392-123">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="a0392-124">何时转到团队</span><span class="sxs-lookup"><span data-stu-id="a0392-124">When to move to Teams</span></span>

<span data-ttu-id="a0392-125">将在2019年10月1日生效, StaffHub 将停用。</span><span class="sxs-lookup"><span data-stu-id="a0392-125">Effective October 1, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="a0392-126">我们鼓励你立即开始使用团队, 并开始从 StaffHub 过渡你的组织的团队和用户。</span><span class="sxs-lookup"><span data-stu-id="a0392-126">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="a0392-127">在 StaffHub 中, 如果计划管理是最常用的功能, 我们建议你使用团队中的倒班应用继续。</span><span class="sxs-lookup"><span data-stu-id="a0392-127">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="a0392-128">哪些内容被移动到团队</span><span class="sxs-lookup"><span data-stu-id="a0392-128">What is moved to Teams</span></span>

<span data-ttu-id="a0392-129">移动 StaffHub 团队时, 团队成员、用户详细信息、工作组日程和聊天数据将移到团队。</span><span class="sxs-lookup"><span data-stu-id="a0392-129">When you move a StaffHub team, team membership, user details, team schedules, and chat data are moved to Teams.</span></span> <span data-ttu-id="a0392-130">移动 StaffHub 团队时, 文件不会移动。</span><span class="sxs-lookup"><span data-stu-id="a0392-130">Files aren't moved when you move a StaffHub team.</span></span> <span data-ttu-id="a0392-131">如果 StaffHub 团队包含你还想要移动到团队的文件, 请在单独的步骤中移动文件。</span><span class="sxs-lookup"><span data-stu-id="a0392-131">If a StaffHub team contains files that you also want to move to teams, you move the files in a separate step.</span></span>

<span data-ttu-id="a0392-132">每个 StaffHub 团队都需要一个相应的 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="a0392-132">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="a0392-133">如果 StaffHub 团队没有与之关联的 Office 365 组, 则会自动为您创建一个以支持切换。</span><span class="sxs-lookup"><span data-stu-id="a0392-133">If a StaffHub team doesn't have an Office 365 Group associated with it, one is automatically created for you to support the transition.</span></span> <span data-ttu-id="a0392-134">由于团队和 StaffHub 之间的团队和组命名之间的差异, 团队中可能会显示不同的团队名称。</span><span class="sxs-lookup"><span data-stu-id="a0392-134">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span>

<span data-ttu-id="a0392-135">当您将团队从 StaffHub 过渡到团队时, 用户将无法再访问其在 StaffHub 中的日程安排, 并且会被重定向到团队中的倒班。</span><span class="sxs-lookup"><span data-stu-id="a0392-135">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="a0392-136">我们建议你将此更改与你的组织进行沟通, 以最大限度地减少中断, 并鼓励用户采纳和探索团队。</span><span class="sxs-lookup"><span data-stu-id="a0392-136">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span> <span data-ttu-id="a0392-137">如果你有 Azure AD Premium, 则可以[运行报表](run-report-to-show-staffhub-usage.md)来获取组织中需要了解此更改的 StaffHub 用户的列表。</span><span class="sxs-lookup"><span data-stu-id="a0392-137">If you have Azure AD Premium, you can [run a report](run-report-to-show-staffhub-usage.md) to get a list of StaffHub users in your organization who need to know about this change.</span></span>  

<span data-ttu-id="a0392-138">将 StaffHub 团队移动到团队后, 没有回滚选项。</span><span class="sxs-lookup"><span data-stu-id="a0392-138">There's no rollback option after you move a StaffHub team to Teams.</span></span>

### <a name="user-experience-when-you-move-a-team"></a><span data-ttu-id="a0392-139">移动团队时的用户体验</span><span class="sxs-lookup"><span data-stu-id="a0392-139">User experience when you move a team</span></span>

<span data-ttu-id="a0392-140">当用户的团队从 StaffHub 切换到团队成员时, 停机时间最少 (如果有)。</span><span class="sxs-lookup"><span data-stu-id="a0392-140">There's minimal downtime (less than a second, if any at all) for users when their team is switched from StaffHub to Shifts in Teams.</span></span> <span data-ttu-id="a0392-141">用户可以继续使用 StaffHub, 直到完成到团队的移动。</span><span class="sxs-lookup"><span data-stu-id="a0392-141">Users can continue using StaffHub until the move to Teams is completed.</span></span> <span data-ttu-id="a0392-142">完成移动后, 团队成员将看到一条消息, 告知他们需要开始使用团队中的倒班访问其团队日程。</span><span class="sxs-lookup"><span data-stu-id="a0392-142">When the move is completed, team members will see a message to let them know that they need to start using Shifts in Teams to access their team schedule.</span></span> <span data-ttu-id="a0392-143">下面是用户在 StaffHub 团队移到团队后在 StaffHub 中看到的消息的示例。</span><span class="sxs-lookup"><span data-stu-id="a0392-143">Here's an example of the message that users see in StaffHub after the StaffHub team is moved to Teams.</span></span>

<span data-ttu-id="a0392-144">![用户看到的消息的示例。](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "用户在 StaffHub 团队移到团队后在 StaffHub 中看到的消息示例")</span><span class="sxs-lookup"><span data-stu-id="a0392-144">![Example of the message that users see.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Example of the message that users see in StaffHub after the StaffHub team is moved to Teams")</span></span>

## <a name="prepare"></a><span data-ttu-id="a0392-145">准备</span><span class="sxs-lookup"><span data-stu-id="a0392-145">Prepare</span></span>

<span data-ttu-id="a0392-146">下面介绍了如何准备迁移到团队。</span><span class="sxs-lookup"><span data-stu-id="a0392-146">Here's how to prepare for the move to Teams.</span></span>

### <a name="check-that-prerequisites-are-met"></a><span data-ttu-id="a0392-147">检查是否满足先决条件</span><span class="sxs-lookup"><span data-stu-id="a0392-147">Check that prerequisites are met</span></span>

<span data-ttu-id="a0392-148">将 StaffHub 团队移动到团队之前, 请确保:</span><span class="sxs-lookup"><span data-stu-id="a0392-148">Before you move a StaffHub team to Teams, make sure that:</span></span>

- <span data-ttu-id="a0392-149">登录用户是全局管理员。</span><span class="sxs-lookup"><span data-stu-id="a0392-149">The signed-in user is a global admin.</span></span>
- <span data-ttu-id="a0392-150">已为租户中的所有用户启用团队。</span><span class="sxs-lookup"><span data-stu-id="a0392-150">Teams is enabled for all users in the tenant.</span></span>
- <span data-ttu-id="a0392-151">租户中已启用 Office 365 组创建。</span><span class="sxs-lookup"><span data-stu-id="a0392-151">Office 365 Groups creation is enabled in the tenant.</span></span>
- <span data-ttu-id="a0392-152">StaffHub teamId 有效。</span><span class="sxs-lookup"><span data-stu-id="a0392-152">The StaffHub teamId is valid.</span></span>
- <span data-ttu-id="a0392-153">StaffHub 团队包含成员。</span><span class="sxs-lookup"><span data-stu-id="a0392-153">The StaffHub team contains members.</span></span>
- <span data-ttu-id="a0392-154">所有 StaffHub 团队成员均链接到 Azure AD 帐户。</span><span class="sxs-lookup"><span data-stu-id="a0392-154">All StaffHub team members are linked to an Azure AD account.</span></span>

<span data-ttu-id="a0392-155">如果不满足这些先决条件, 则移动请求将失败。</span><span class="sxs-lookup"><span data-stu-id="a0392-155">If these prerequisites aren't met, the move request will fail.</span></span>

### <a name="assign-teams-licenses"></a><span data-ttu-id="a0392-156">分配 Teams 许可证</span><span class="sxs-lookup"><span data-stu-id="a0392-156">Assign Teams licenses</span></span>

<span data-ttu-id="a0392-157">每个用户都必须具有[符合条件的计划](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in)的活动 Microsoft 365 或 Office 365 许可证, 并且必须分配有团队许可证。</span><span class="sxs-lookup"><span data-stu-id="a0392-157">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="a0392-158">为用户分配团队许可证后, 他们可以访问团队。</span><span class="sxs-lookup"><span data-stu-id="a0392-158">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="a0392-159">可在 Microsoft 365 管理中心内管理团队许可证。</span><span class="sxs-lookup"><span data-stu-id="a0392-159">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="a0392-160">若要了解详细信息, 请参阅[管理用户对团队的访问权限](../../user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="a0392-160">To learn more, see [Manage user access to Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a0392-161">如果你的组织使用 Skype for Business, 并且尚未准备好将所有用户移到团队, 你可以为你的一线工作人员启用团队, 然后将团队与 Skype for Business 一起运行。</span><span class="sxs-lookup"><span data-stu-id="a0392-161">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="a0392-162">在此共存模式 (名为 "*岛*") 中, 每个客户端应用都作为单独的解决方案运行。</span><span class="sxs-lookup"><span data-stu-id="a0392-162">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="a0392-163">若要了解详细信息, 请参阅[了解团队和 Skype for business 共存和互操作性](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md)。</span><span class="sxs-lookup"><span data-stu-id="a0392-163">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="install-the-staffhub-powershell-module"></a><span data-ttu-id="a0392-164">安装 StaffHub PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="a0392-164">Install the StaffHub PowerShell module</span></span>

<span data-ttu-id="a0392-165">如果尚未安装, 请[安装 StaffHub PowerShell 模块](install-the-staffhub-powershell-module.md)。</span><span class="sxs-lookup"><span data-stu-id="a0392-165">If you haven't already, [install the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span> 

### <a name="link-an-azure-ad-account-for-staffhub-team-members-who-dont-have-one"></a><span data-ttu-id="a0392-166">为没有联系人的 StaffHub 团队成员链接 Azure AD 帐户</span><span class="sxs-lookup"><span data-stu-id="a0392-166">Link an Azure AD account for StaffHub team members who don't have one</span></span>

<span data-ttu-id="a0392-167">每个 StaffHub 团队成员都必须链接到 Azure Active Directory (Azure AD) 帐户。</span><span class="sxs-lookup"><span data-stu-id="a0392-167">Each StaffHub team member must be linked to an Azure Active Directory (Azure AD) account.</span></span> <span data-ttu-id="a0392-168">如果以下任何情形适用, 组织中的用户将不会链接到 Azure AD 帐户:</span><span class="sxs-lookup"><span data-stu-id="a0392-168">Users in your organization won't be linked to an Azure AD account if any of the following scenarios apply:</span></span>

- <span data-ttu-id="a0392-169">团队所有者添加的用户没有 Azure AD 帐户。</span><span class="sxs-lookup"><span data-stu-id="a0392-169">A team owner added a user who doesn't have an Azure AD account.</span></span>
- <span data-ttu-id="a0392-170">团队所有者邀请用户加入 StaffHub 团队, 而该用户未接受邀请。</span><span class="sxs-lookup"><span data-stu-id="a0392-170">A team owner invited a user to a StaffHub team and that user didn't accept the invitation.</span></span>

<span data-ttu-id="a0392-171">你可以链接这些用户的 Azure AD 帐户。</span><span class="sxs-lookup"><span data-stu-id="a0392-171">You can link an Azure AD account for these users.</span></span>  <span data-ttu-id="a0392-172">方法如下。</span><span class="sxs-lookup"><span data-stu-id="a0392-172">Here's how.</span></span>

#### <a name="get-a-list-of-all-users-on-staffhub-teams-that-have-team-members-that-arent-linked-to-an-azure-ad-account"></a><span data-ttu-id="a0392-173">获取包含未链接到 Azure AD 帐户的团队成员的 StaffHub 团队中的所有用户的列表</span><span class="sxs-lookup"><span data-stu-id="a0392-173">Get a list of all users on StaffHub teams that have team members that aren't linked to an Azure AD account</span></span>

<span data-ttu-id="a0392-174">请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="a0392-174">Run the following:</span></span>
```
$StaffHubTeams = Get-StaffHubTeamsForTenant
$StaffHubTeams[0] = $StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq 'StaffHub' }
foreach($team in $StaffHubTeams[0]) {Get-StaffHubMember -TeamId $team.Id | where {$_.Email -eq $null -or $_.State -eq "Invited"}}
```

#### <a name="link-the-account"></a><span data-ttu-id="a0392-175">链接帐户</span><span class="sxs-lookup"><span data-stu-id="a0392-175">Link the account</span></span>

<span data-ttu-id="a0392-176">请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="a0392-176">Do one of the following:</span></span>

- <span data-ttu-id="a0392-177">转换和链接帐户。</span><span class="sxs-lookup"><span data-stu-id="a0392-177">Convert and link the account.</span></span>

  <span data-ttu-id="a0392-178">StaffHub 团队所有者和管理者可以转换非活动帐户并将其链接到 StaffHub 中的 Azure AD 帐户, 方法是将用户的电子邮件地址更改为 "StaffHub 团队设置" 页面上的有效 UPN。</span><span class="sxs-lookup"><span data-stu-id="a0392-178">StaffHub team owners and managers can convert an inactive account and link it to an Azure AD account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="a0392-179">删除未链接的帐户, 然后使用 UPN 重新添加帐户。</span><span class="sxs-lookup"><span data-stu-id="a0392-179">Remove the unlinked account and then re-add the account by using the UPN.</span></span>
    1. <span data-ttu-id="a0392-180">运行[StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubMember?view=staffhub-ps) cmdlet 以从 StaffHub 团队中删除未预配的帐户。</span><span class="sxs-lookup"><span data-stu-id="a0392-180">Run the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubMember?view=staffhub-ps) cmdlet to remove the non-provisioned account from the StaffHub team.</span></span>
    2. <span data-ttu-id="a0392-181">运行[StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) cmdlet, 使用 UPN 将帐户重新添加到 StaffHub 团队。</span><span class="sxs-lookup"><span data-stu-id="a0392-181">Run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) cmdlet to add the account back to the StaffHub team by using the UPN.</span></span>

- <span data-ttu-id="a0392-182">删除未链接的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="a0392-182">Remove the unlinked user account.</span></span> <span data-ttu-id="a0392-183">使用此选项将不再需要用户帐户。</span><span class="sxs-lookup"><span data-stu-id="a0392-183">Use this option the user account is no longer needed.</span></span>

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a><span data-ttu-id="a0392-184">将 FirstlineWorker 应用设置策略分配给用户</span><span class="sxs-lookup"><span data-stu-id="a0392-184">Assign the FirstlineWorker app setup policy to users</span></span>

<span data-ttu-id="a0392-185">团队包含内置的 FirstlineWorker 应用设置策略, 可用于自定义团队, 以突出显示对于组织中的一线工作人员而言最重要的应用。</span><span class="sxs-lookup"><span data-stu-id="a0392-185">Teams includes a built-in FirstlineWorker app setup policy that you can use to customize Teams to highlight the apps that are most important for the Firstline Workers in your organization.</span></span> <span data-ttu-id="a0392-186">向用户分配此策略时, 策略中的应用将固定到团队中的应用栏, 以便快速轻松地访问。</span><span class="sxs-lookup"><span data-stu-id="a0392-186">When you assign this policy to users, the apps in the policy are pinned to the app bar in Teams for quick and easy access.</span></span> <span data-ttu-id="a0392-187">添加到团队的其他应用可以通过单击 "..." 在应用栏中找到 **。** 团队桌面和 web 客户端中的更多应用, 并可通过团队移动客户端向上轻扫。</span><span class="sxs-lookup"><span data-stu-id="a0392-187">Other apps added to Teams can be found in the app bar by clicking **... More apps** in the Teams desktop and web clients and by swiping up in the Teams mobile client.</span></span> <span data-ttu-id="a0392-188">默认情况下, FirstlineWorker 应用设置策略包括活动、班次、聊天和调用应用。</span><span class="sxs-lookup"><span data-stu-id="a0392-188">By default, the FirstlineWorker app setup policy includes the Activity, Shifts, Chat, and Calling apps.</span></span>

<span data-ttu-id="a0392-189">有关如何将 FirstlineWorker 应用设置策略分配给用户的步骤, 请参阅[使用 FirstlineWorker 应用设置策略固定对团队的倒班](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams)。</span><span class="sxs-lookup"><span data-stu-id="a0392-189">For steps on how to assign the FirstlineWorker app setup policy to users, see [Use the FirstlineWorker app setup policy to pin Shifts to Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span></span> <span data-ttu-id="a0392-190">分配策略后, 可能需要长达24小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="a0392-190">After you assign a policy, it can take up to 24 hours to take effect.</span></span>

<span data-ttu-id="a0392-191">我们建议您至少一周完成此步骤, 然后再将 StaffHub 团队和用户移到团队。</span><span class="sxs-lookup"><span data-stu-id="a0392-191">We recommend you complete this step at least a week before you move your StaffHub teams and users to Teams.</span></span> <span data-ttu-id="a0392-192">当用户位于团队中时, 请确认他们可以查看和访问 "倒班" 应用。</span><span class="sxs-lookup"><span data-stu-id="a0392-192">When users are on Teams, confirm that they can see and access the Shifts app.</span></span>

<span data-ttu-id="a0392-193">你还可以创建自定义应用设置策略, 并编辑全局应用设置策略中的设置。</span><span class="sxs-lookup"><span data-stu-id="a0392-193">You can also create custom app setup policies and edit the settings in the global app setup policy.</span></span> <span data-ttu-id="a0392-194">若要了解详细信息, 请参阅[管理团队中的应用设置策略](../../teams-app-setup-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a0392-194">To learn more, check out [Manage app setup policies in Teams](../../teams-app-setup-policies.md).</span></span>

### <a name="onboard-users-to-teams"></a><span data-ttu-id="a0392-195">向团队中的用户的板载用户</span><span class="sxs-lookup"><span data-stu-id="a0392-195">Onboard users to Teams</span></span>

<span data-ttu-id="a0392-196">作为加入策略的一部分, 为用户提供培训和指导, 帮助他们熟悉团队。</span><span class="sxs-lookup"><span data-stu-id="a0392-196">As part of your onboarding strategy, provide training and guidance for users to help them get familiar with Teams.</span></span> <span data-ttu-id="a0392-197">与用户共享以下资源, 以便他们知道团队客户端、培训和支持的位置:</span><span class="sxs-lookup"><span data-stu-id="a0392-197">Share the following resources with users so they know where to get Teams clients, training, and support:</span></span>

- [<span data-ttu-id="a0392-198">Teams Web 客户端</span><span class="sxs-lookup"><span data-stu-id="a0392-198">Teams web client</span></span>](https://teams.microsoft.com)
- [<span data-ttu-id="a0392-199">桌面和移动客户端下载链接</span><span class="sxs-lookup"><span data-stu-id="a0392-199">Desktop and mobile client download links</span></span>](https://teams.microsoft.com/downloads)
- [<span data-ttu-id="a0392-200">Teams 培训视频</span><span class="sxs-lookup"><span data-stu-id="a0392-200">Teams training videos</span></span>](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [<span data-ttu-id="a0392-201">Teams 帮助文档</span><span class="sxs-lookup"><span data-stu-id="a0392-201">Teams Help documentation</span></span>](https://support.office.com/teams)

<span data-ttu-id="a0392-202">有关部署团队和推动团队采纳的指南, 请参阅[如何推广团队](../../How-to-roll-out-teams.md)和[采纳团队](../../adopt-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="a0392-202">For guidance on deploying Teams and driving Teams adoption, see [How to roll out Teams](../../How-to-roll-out-teams.md) and [Adopt Teams](../../adopt-microsoft-teams-landing-page.md).</span></span>

## <a name="conduct-a-pilot"></a><span data-ttu-id="a0392-203">执行试验</span><span class="sxs-lookup"><span data-stu-id="a0392-203">Conduct a pilot</span></span>

<span data-ttu-id="a0392-204">我们建议您首先将两个或三个 StaffHub 团队移动到一组早期采纳者。</span><span class="sxs-lookup"><span data-stu-id="a0392-204">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="a0392-205">运行试验可帮助你优化过渡计划, 并确保你已准备好将组织的所有 StaffHub 团队移动到团队。</span><span class="sxs-lookup"><span data-stu-id="a0392-205">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="a0392-206">它还标识了可帮助推动组织内采用的拥护者。</span><span class="sxs-lookup"><span data-stu-id="a0392-206">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="a0392-207">如果您是不需要分阶段方法的小型企业, 那么本部分中的步骤可能是您将从 StaffHub 切换到团队的所有步骤。</span><span class="sxs-lookup"><span data-stu-id="a0392-207">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="a0392-208">确定试生产团队</span><span class="sxs-lookup"><span data-stu-id="a0392-208">Identify pilot teams</span></span>

<span data-ttu-id="a0392-209">联系以确定两个或三个试验团队。</span><span class="sxs-lookup"><span data-stu-id="a0392-209">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="a0392-210">所有团队成员都应承诺使用团队中的倒班管理其日程并相互沟通和协作。</span><span class="sxs-lookup"><span data-stu-id="a0392-210">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="a0392-211">确定团队拥护人员</span><span class="sxs-lookup"><span data-stu-id="a0392-211">Identify team champions</span></span>

<span data-ttu-id="a0392-212">在试点团队中确定拥护人员, 并登记它们以帮助布道倒班。</span><span class="sxs-lookup"><span data-stu-id="a0392-212">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="a0392-213">团队拥护者热心他们所做的工作, 分享他们自己的发现以向团队成员提供支持和指导。</span><span class="sxs-lookup"><span data-stu-id="a0392-213">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="a0392-214">团队拥护者可以是团队所有者或经理。</span><span class="sxs-lookup"><span data-stu-id="a0392-214">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="a0392-215">团队拥护者应确保团队成员可以通过专门的时间让每个人[获得团队客户](../../get-clients.md), 登录团队并查看他们的日程安排, 并相互开始聊天。</span><span class="sxs-lookup"><span data-stu-id="a0392-215">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="a0392-216">已熟悉 StaffHub 的用户将在倒班中快速启动并运行。</span><span class="sxs-lookup"><span data-stu-id="a0392-216">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="a0392-217">你还可以指向它们以[移动帮助](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)以获取其他帮助。</span><span class="sxs-lookup"><span data-stu-id="a0392-217">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team"></a><span data-ttu-id="a0392-218">移动 StaffHub 团队</span><span class="sxs-lookup"><span data-stu-id="a0392-218">Move a StaffHub team</span></span>

<span data-ttu-id="a0392-219">使用以下步骤一次移动一个 StaffHub 团队。</span><span class="sxs-lookup"><span data-stu-id="a0392-219">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="a0392-220">我们建议你的试点团队采用此方法。</span><span class="sxs-lookup"><span data-stu-id="a0392-220">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="a0392-221">稍后, 当你准备好移动组织的所有 StaffHub 团队时, 请参阅[移动你的 StaffHub 团队](#move-your-staffhub-teams), 了解如何一次移动多个团队的步骤。</span><span class="sxs-lookup"><span data-stu-id="a0392-221">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="a0392-222">运行以下操作以移动 StaffHub 团队。</span><span class="sxs-lookup"><span data-stu-id="a0392-222">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -TeamId <String>
```
<span data-ttu-id="a0392-223">上例</span><span class="sxs-lookup"><span data-stu-id="a0392-223">Example:</span></span>

```
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="a0392-224">下面是提交请求以将 StaffHub 团队移动到团队时收到的答复的示例。</span><span class="sxs-lookup"><span data-stu-id="a0392-224">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="a0392-225">若要检查移动请求的状态, 请运行以下。</span><span class="sxs-lookup"><span data-stu-id="a0392-225">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <String>
```
<span data-ttu-id="a0392-226">上例</span><span class="sxs-lookup"><span data-stu-id="a0392-226">Example:</span></span>

```
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

<span data-ttu-id="a0392-227">下面是在移动进行过程中获取的响应的示例。</span><span class="sxs-lookup"><span data-stu-id="a0392-227">Here's an example of the response you get when a move is in progress.</span></span>

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a><span data-ttu-id="a0392-228">将文件从 StaffHub 团队移动到团队</span><span class="sxs-lookup"><span data-stu-id="a0392-228">Move files from a StaffHub team to Teams</span></span>

<span data-ttu-id="a0392-229">此步骤仅适用于你已移动到团队的 StaffHub 团队是否具有你希望还希望迁移到团队的文件。</span><span class="sxs-lookup"><span data-stu-id="a0392-229">This step only applies if the StaffHub team that you moved to Teams has files that you want to also move to Teams.</span></span> <span data-ttu-id="a0392-230">你可以直接在 SharePoint Online 或使用 PowerShell 中移动文件。</span><span class="sxs-lookup"><span data-stu-id="a0392-230">You can move files directly in SharePoint Online or by using PowerShell.</span></span>

#### <a name="in-sharepoint-online"></a><span data-ttu-id="a0392-231">在 SharePoint Online 中</span><span class="sxs-lookup"><span data-stu-id="a0392-231">In SharePoint Online</span></span>

<span data-ttu-id="a0392-232">了解[如何在 SharePoint Online 中移动文件](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30)。</span><span class="sxs-lookup"><span data-stu-id="a0392-232">See [How to move files in SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="a0392-233">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="a0392-233">Using PowerShell</span></span>

<span data-ttu-id="a0392-234">下载并安装[SharePoint Online 命令行管理](https://www.microsoft.com/download/details.aspx?id=35588)程序 (如果尚未安装)。</span><span class="sxs-lookup"><span data-stu-id="a0392-234">Download and install the [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588), if you haven't already.</span></span> <span data-ttu-id="a0392-235">它包含移动文件所需的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a0392-235">It contains the cmdlets you need to move files.</span></span>  

<span data-ttu-id="a0392-236">使用[admin.sharepoint.com](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) cmdlet 连接到 SharePoint Online 团队网站。</span><span class="sxs-lookup"><span data-stu-id="a0392-236">Use the [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) cmdlet to connect to the SharePoint Online team site.</span></span>

```
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

<span data-ttu-id="a0392-237">对于要从 StaffHub 移动到团队的每个文件, 请使用[PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) cmdlet 移动文件。</span><span class="sxs-lookup"><span data-stu-id="a0392-237">For each file that you want to move from StaffHub to Teams, use the [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) cmdlet to move the file.</span></span>

```
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

<span data-ttu-id="a0392-238">若要移动多个文件, 请循环访问这些文件, 然后在循环中运行第二个命令。</span><span class="sxs-lookup"><span data-stu-id="a0392-238">To move multiple files, loop over the files and run the second command on the loop.</span></span> <span data-ttu-id="a0392-239">如果会话保持活动状态, 则无需重复第一个命令。</span><span class="sxs-lookup"><span data-stu-id="a0392-239">You don't need to repeat the first command if the session remains active.</span></span>

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a><span data-ttu-id="a0392-240">超越您的试点和移动所有 StaffHub 团队</span><span class="sxs-lookup"><span data-stu-id="a0392-240">Go beyond your pilot and move all StaffHub teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="a0392-241">提高意识</span><span class="sxs-lookup"><span data-stu-id="a0392-241">Raise awareness</span></span>

<span data-ttu-id="a0392-242">当您准备好超越试点团队, 并将组织的 StaffHub 团队移动到团队时, 首先要在组织中传达更改, 这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="a0392-242">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="a0392-243">传播关于倒班和过渡到团队的内容, 以提高意识、产生兴奋和推动采纳。</span><span class="sxs-lookup"><span data-stu-id="a0392-243">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams"></a><span data-ttu-id="a0392-244">移动 StaffHub 团队</span><span class="sxs-lookup"><span data-stu-id="a0392-244">Move your StaffHub teams</span></span>

<span data-ttu-id="a0392-245">使用以下步骤批量移动 StaffHub 团队。</span><span class="sxs-lookup"><span data-stu-id="a0392-245">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="a0392-246">你可以选择移动组织的所有 StaffHub 团队或移动特定的 StaffHub 团队。</span><span class="sxs-lookup"><span data-stu-id="a0392-246">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="a0392-247">如果想要一次移动一个团队, 请参阅[移动 StaffHub 团队](#move-a-staffhub-team)。</span><span class="sxs-lookup"><span data-stu-id="a0392-247">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team).</span></span>

#### <a name="move-all-staffhub-teams"></a><span data-ttu-id="a0392-248">移动所有 StaffHub 团队</span><span class="sxs-lookup"><span data-stu-id="a0392-248">Move all StaffHub teams</span></span>

<span data-ttu-id="a0392-249">运行以下操作以获取组织中所有 StaffHub 团队的列表。</span><span class="sxs-lookup"><span data-stu-id="a0392-249">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant
$StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq ‘StaffHub’ }
```

<span data-ttu-id="a0392-250">然后, 运行以下操作以移动所有团队。</span><span class="sxs-lookup"><span data-stu-id="a0392-250">Then, run the following to move all teams.</span></span>

```
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

<span data-ttu-id="a0392-251">下面是该响应的一个示例。</span><span class="sxs-lookup"><span data-stu-id="a0392-251">Here's an example of the response.</span></span>

<span data-ttu-id="a0392-252">对于已迁移到团队或已存在于团队中的任何团队, 作业 Id 将为 "null", 因为不需要提交作业即可移动该团队。</span><span class="sxs-lookup"><span data-stu-id="a0392-252">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a><span data-ttu-id="a0392-253">移动特定的 StaffHub 团队</span><span class="sxs-lookup"><span data-stu-id="a0392-253">Move specific StaffHub teams</span></span>

<span data-ttu-id="a0392-254">运行以下操作以获取组织中所有 StaffHub 团队 Id 的列表。</span><span class="sxs-lookup"><span data-stu-id="a0392-254">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="a0392-255">在之前运行的`Get-StaffHubteamsForTenant` cmdlet 返回的结果中, 选择要移动的团队 id, 然后将其添加到逗号分隔值 (CSV) 文件。</span><span class="sxs-lookup"><span data-stu-id="a0392-255">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="a0392-256">下面是如何设置 CSV 文件格式的示例。</span><span class="sxs-lookup"><span data-stu-id="a0392-256">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="a0392-257">标识号</span><span class="sxs-lookup"><span data-stu-id="a0392-257">Id</span></span>  |
|---------|
|<span data-ttu-id="a0392-258">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="a0392-258">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="a0392-259">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="a0392-259">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="a0392-260">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="a0392-260">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="a0392-261">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="a0392-261">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="a0392-262">创建 CSV 文件后, 请运行以下操作以移动您在 CSV 文件中指定的团队。</span><span class="sxs-lookup"><span data-stu-id="a0392-262">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```
$StaffHubTeams = Import-Csv .\teams.csv
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a><span data-ttu-id="a0392-263">确认你的 StaffHub 团队是否已迁移到团队</span><span class="sxs-lookup"><span data-stu-id="a0392-263">Confirm that your StaffHub teams have moved to Teams</span></span>

<span data-ttu-id="a0392-264">运行以下操作, 获取组织中所有团队成员的列表。</span><span class="sxs-lookup"><span data-stu-id="a0392-264">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a><span data-ttu-id="a0392-265">将文件从 StaffHub 团队移动到团队</span><span class="sxs-lookup"><span data-stu-id="a0392-265">Move files from your StaffHub teams to Teams</span></span>

<span data-ttu-id="a0392-266">如果你移动的 StaffHub 团队包含你还想要移动到团队的文件, 请参阅[将文件从 StaffHub 团队移动到团队](#move-files-from-a-staffhub-team-to-teams)。</span><span class="sxs-lookup"><span data-stu-id="a0392-266">If the StaffHub teams that you moved contain files that you also want to move to Teams, see [Move files from a StaffHub team to Teams](#move-files-from-a-staffhub-team-to-teams).</span></span>

## <a name="monitor-teams-usage"></a><span data-ttu-id="a0392-267">监视团队使用情况</span><span class="sxs-lookup"><span data-stu-id="a0392-267">Monitor Teams usage</span></span>

<span data-ttu-id="a0392-268">使用情况报告可帮助你更好地了解使用模式, 并向你提供有关在你的组织中对培训和沟通工作进行排序的位置的见解。</span><span class="sxs-lookup"><span data-stu-id="a0392-268">Usage reports can help you better understand usage patterns and give you insights on where to prioritize training and communication efforts across your organization.</span></span> <span data-ttu-id="a0392-269">你可以运行报表, 显示总体团队使用情况、用户在团队中执行的活动类型、用户如何连接到团队等。</span><span class="sxs-lookup"><span data-stu-id="a0392-269">You can run reports that show you overall Teams usage, the types of activities that users perform in Teams, how users connect to Teams, and more.</span></span> <span data-ttu-id="a0392-270">有关详细信息, 请参阅 Microsoft[团队管理中心中的团队报告](../../teams-analytics-and-reports/teams-reporting-reference.md)和[microsoft 365 管理中心中的团队活动报表](../../teams-activity-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="a0392-270">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="a0392-271">疑难解答</span><span class="sxs-lookup"><span data-stu-id="a0392-271">Troubleshooting</span></span>

<span data-ttu-id="a0392-272">**当您尝试将文件从 StaffHub 移动到团队时, 会收到 "权限被拒绝" 错误消息。**</span><span class="sxs-lookup"><span data-stu-id="a0392-272">**When you try to move files from StaffHub to Teams, you get a "Permission denied" error message.**</span></span>

<span data-ttu-id="a0392-273">如果你尝试将文件移动到你不是其成员的专用 Office 365 组中, 可能会出现此情况。</span><span class="sxs-lookup"><span data-stu-id="a0392-273">This may occur if you're trying to move files in a private Office 365 group that you're not a member of.</span></span> <span data-ttu-id="a0392-274">如果是这种情况, 请使用[AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) cmdlet 将自己添加到 StaffHub 团队, 然后移动文件。</span><span class="sxs-lookup"><span data-stu-id="a0392-274">If this is the case, use the [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) cmdlet to add yourself to the StaffHub team, and then move the files.</span></span> <span data-ttu-id="a0392-275">移动文件后, 请使用[StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) cmdlet 将自己从团队中删除。</span><span class="sxs-lookup"><span data-stu-id="a0392-275">After you move the files, use the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) cmdlet to remove yourself from the team.</span></span> 

<span data-ttu-id="a0392-276">**当您尝试将文件从 StaffHub 移动到团队时, 将收到一条错误消息, 指出 "常规" 文件夹不存在。**</span><span class="sxs-lookup"><span data-stu-id="a0392-276">**When you try to move files from StaffHub to Teams, you get an error that says the General folder doesn't exist.**</span></span>

<span data-ttu-id="a0392-277">运行以下命令以将常规文件夹添加到 SharePoint, 然后重试:</span><span class="sxs-lookup"><span data-stu-id="a0392-277">Run the following command to add the General folder to SharePoint, and then try again:</span></span>

  ```
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a><span data-ttu-id="a0392-278">相关主题</span><span class="sxs-lookup"><span data-stu-id="a0392-278">Related topics</span></span>
- [<span data-ttu-id="a0392-279">如何部署 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a0392-279">How to roll out Microsoft Teams</span></span>](../../How-to-roll-out-teams.md)
- [<span data-ttu-id="a0392-280">Microsoft StaffHub 将停用</span><span class="sxs-lookup"><span data-stu-id="a0392-280">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="a0392-281">在 Microsoft Teams 中为组织管理 Shifts 应用</span><span class="sxs-lookup"><span data-stu-id="a0392-281">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="a0392-282">StaffHub PowerShell 参考</span><span class="sxs-lookup"><span data-stu-id="a0392-282">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
