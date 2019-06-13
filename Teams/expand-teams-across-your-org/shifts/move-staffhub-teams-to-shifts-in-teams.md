---
title: 将 StaffHub 团队迁移到 Microsoft Teams 中的排班
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: 了解如何将 Microsoft StaffHub 团队和日程安排数据迁移到 Microsoft Teams 中的排班。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e2e8b0ac4f1c4eb0cce2cae97481fc428f588ec5
ms.sourcegitcommit: 8f9bf1acdcdc2104fa8c343c030d64838e2c31eb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2019
ms.locfileid: "34780806"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="466a1-103">将 Microsoft StaffHub 团队迁移到 Microsoft Teams 中的排班</span><span class="sxs-lookup"><span data-stu-id="466a1-103">Move your StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="466a1-104">自 2019 年 10 月 1 日起，Microsoft StaffHub 将停用。</span><span class="sxs-lookup"><span data-stu-id="466a1-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="466a1-105">我们正在为 Microsoft Teams 构建 StaffHub 功能。</span><span class="sxs-lookup"><span data-stu-id="466a1-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="466a1-106">如今，Teams 包含用于日程安排管理的排班应用，并且随着时间推移将推出其他功能。</span><span class="sxs-lookup"><span data-stu-id="466a1-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="466a1-107">StaffHub 将于 2019 年 10 月 1 日停止为所有用户工作。</span><span class="sxs-lookup"><span data-stu-id="466a1-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="466a1-108">尝试打开 StaffHub 的任何用户都会看到一则提示其下载 Teams 的消息。</span><span class="sxs-lookup"><span data-stu-id="466a1-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="466a1-109">若要了解详细信息，请参阅 [Microsoft StaffHub 将停用](microsoft-staffhub-to-be-retired.md)。</span><span class="sxs-lookup"><span data-stu-id="466a1-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

<span data-ttu-id="466a1-110">Teams 中的排班应用提供了一种简单的方法来管理日程安排以及每天发生的换班和班次取消的持续流程。</span><span class="sxs-lookup"><span data-stu-id="466a1-110">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="466a1-111">团队成员可以直接在该应用及其设备上访问他们的日程安排和排班信息，以便设置他们的偏好、管理日程安排和申请休假。</span><span class="sxs-lookup"><span data-stu-id="466a1-111">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="466a1-112">本文将介绍如何将组织的 StaffHub 团队和日程安排数据迁移到 Teams 中的排班。</span><span class="sxs-lookup"><span data-stu-id="466a1-112">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="466a1-113">它包含以下内容：</span><span class="sxs-lookup"><span data-stu-id="466a1-113">It covers:</span></span>

- [<span data-ttu-id="466a1-114">迁移到 Teams 的必备知识</span><span class="sxs-lookup"><span data-stu-id="466a1-114">What you need to know about the move to Teams</span></span>](#what-you-need-to-know-about-the-move-to-teams)
- [<span data-ttu-id="466a1-115">准备</span><span class="sxs-lookup"><span data-stu-id="466a1-115">Prepare Schema</span></span>](#prepare)
- [<span data-ttu-id="466a1-116">执行试点</span><span class="sxs-lookup"><span data-stu-id="466a1-116">Conduct a user pilot</span></span>](#conduct-a-pilot) 
- [<span data-ttu-id="466a1-117">超越试点并迁移所有 StaffHub 团队</span><span class="sxs-lookup"><span data-stu-id="466a1-117">Go beyond your pilot and move all StaffHub teams</span></span>](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [<span data-ttu-id="466a1-118">监视 Teams 使用情况</span><span class="sxs-lookup"><span data-stu-id="466a1-118">Monitor Teams usage</span></span>](#monitor-teams-usage)
- [<span data-ttu-id="466a1-119">疑难解答</span><span class="sxs-lookup"><span data-stu-id="466a1-119">troubleshooting</span></span>](#troubleshooting)

<span data-ttu-id="466a1-120">无论你拥有包含一个或两个 StaffHub 团队的小型企业，还是拥有包含数百个 StaffHub 团队的大型企业，你都可以在这里找到帮助你成功过渡到 Teams 所需的管理员指南。</span><span class="sxs-lookup"><span data-stu-id="466a1-120">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="466a1-121">只有全局管理员才能执行本文所述的步骤。</span><span class="sxs-lookup"><span data-stu-id="466a1-121">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="466a1-122">如果你尚未这样做，请查看 [StaffHub 停用常见问题解答](microsoft-staffhub-to-be-retired.md)，以获取你可能遇到的任何问题的答案。</span><span class="sxs-lookup"><span data-stu-id="466a1-122">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span>

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="466a1-123">迁移到 Teams 的必备知识</span><span class="sxs-lookup"><span data-stu-id="466a1-123">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="466a1-124">何时迁移到 Teams</span><span class="sxs-lookup"><span data-stu-id="466a1-124">When to move to Teams</span></span>

<span data-ttu-id="466a1-125">自 2019 年 10 月 1 日起，StaffHub 将停用。</span><span class="sxs-lookup"><span data-stu-id="466a1-125">Effective October 1, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="466a1-126">我们鼓励你立即开始使用 Teams，并开始从 StaffHub 迁移组织的团队和用户。</span><span class="sxs-lookup"><span data-stu-id="466a1-126">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="466a1-127">由于日程安排管理是 StaffHub 中的最常用功能，我们建议你使用 Teams 中的排班应用继续执行相关操作。</span><span class="sxs-lookup"><span data-stu-id="466a1-127">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="466a1-128">可将哪些内容迁移到 Teams</span><span class="sxs-lookup"><span data-stu-id="466a1-128">What is moved to Teams</span></span>

<span data-ttu-id="466a1-129">可将用户详细信息、日程安排信息以及聊天记录和文件数据迁移到 Teams。</span><span class="sxs-lookup"><span data-stu-id="466a1-129">User details, schedule information, and chat and file data are transitioned to Teams.</span></span> <span data-ttu-id="466a1-130">这包括团队成员资格、团队日程安排以及过去 90 天内的聊天记录和文件。</span><span class="sxs-lookup"><span data-stu-id="466a1-130">This includes team membership, team schedules, and chats and files from the last 90 days.</span></span>

<span data-ttu-id="466a1-131">每个 StaffHub 团队都需要一个相应的 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="466a1-131">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="466a1-132">如果 StaffHub 团队没有与之关联的 Office 365 组，则系统会自动创建一个以支持迁移。</span><span class="sxs-lookup"><span data-stu-id="466a1-132">If a StaffHub team doesn't have an Office 365 Group associated with it, one is automatically created for you to support the transition.</span></span> <span data-ttu-id="466a1-133">鉴于 Teams 与 StaffHub 之间的团队和组命名有所不同，你可能会在 Teams 中看到不同的团队名称。</span><span class="sxs-lookup"><span data-stu-id="466a1-133">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span>

<span data-ttu-id="466a1-134">将团队从 StaffHub 迁移到 Teams 时，用户将无法再访问 StaffHub 中的日程安排，并且将重定向到 Teams 中的排班应用。</span><span class="sxs-lookup"><span data-stu-id="466a1-134">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="466a1-135">我们建议你在整个组织内传达此更改，以最大限度地减少中断并鼓励用户采用和探索 Teams。</span><span class="sxs-lookup"><span data-stu-id="466a1-135">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span> <span data-ttu-id="466a1-136">如果你拥有 Azure AD Premium，则可以[运行报告](run-report-to-show-staffhub-usage.md)以获取组织内需要了解此更改的 StaffHub 用户列表。</span><span class="sxs-lookup"><span data-stu-id="466a1-136">If you have Azure AD Premium, you can [run a report](run-report-to-show-staffhub-usage.md) to get a list of StaffHub users in your organization who need to know about this change.</span></span>  

<span data-ttu-id="466a1-137">将 StaffHub 团队迁移至 Teams 后，不提供任何回滚选项。</span><span class="sxs-lookup"><span data-stu-id="466a1-137">There's no rollback option after you move a StaffHub team to Teams.</span></span>

### <a name="user-experience-when-you-move-a-team"></a><span data-ttu-id="466a1-138">迁移团队时的用户体验</span><span class="sxs-lookup"><span data-stu-id="466a1-138">User experience when you move a team</span></span>

<span data-ttu-id="466a1-139">将团队从 StaffHub 切换到 Teams 中的排班应用时，用户的停机时间很短（不到一秒钟，如果有的话）。</span><span class="sxs-lookup"><span data-stu-id="466a1-139">There's minimal downtime (less than a second, if any at all) for users when their team is switched from StaffHub to Shifts in Teams.</span></span> <span data-ttu-id="466a1-140">用户可以继续使用 StaffHub，直到完成向 Teams 的迁移为止。</span><span class="sxs-lookup"><span data-stu-id="466a1-140">Users can continue using StaffHub until the move to Teams is completed.</span></span> <span data-ttu-id="466a1-141">完成迁移后，团队成员将看到一则消息，提示他们需要开始使用 Teams 中的排班应用来访问其团队日程安排。</span><span class="sxs-lookup"><span data-stu-id="466a1-141">When the move is completed, team members will see a message to let them know that they need to start using Shifts in Teams to access their team schedule.</span></span> <span data-ttu-id="466a1-142">以下是将 StaffHub 团队迁移到 Teams 后用户将在 StaffHub 中看到的消息示例。</span><span class="sxs-lookup"><span data-stu-id="466a1-142">Here's an example of the message that users see in StaffHub after the StaffHub team is moved to Teams.</span></span>

<span data-ttu-id="466a1-143">![用户看到的消息示例。](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "将 StaffHub 团队迁移到 Teams 后用户将在 StaffHub 中看到的消息示例")</span><span class="sxs-lookup"><span data-stu-id="466a1-143">![Example of the message that users see.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Example of the message that users see in StaffHub after the StaffHub team is moved to Teams")</span></span>

## <a name="prepare"></a><span data-ttu-id="466a1-144">准备</span><span class="sxs-lookup"><span data-stu-id="466a1-144">Prepare Schema</span></span>

<span data-ttu-id="466a1-145">下文介绍了迁移到 Teams 的准备工作。</span><span class="sxs-lookup"><span data-stu-id="466a1-145">Here's how to prepare for the move to Teams.</span></span>

### <a name="check-that-prerequisites-are-met"></a><span data-ttu-id="466a1-146">检查是否满足先决条件</span><span class="sxs-lookup"><span data-stu-id="466a1-146">Ensure that deployment prerequisites are met</span></span>

<span data-ttu-id="466a1-147">将 StaffHub 团队迁移到 Teams 之前，请确保：</span><span class="sxs-lookup"><span data-stu-id="466a1-147">Before you move a StaffHub team to Teams, make sure that:</span></span>

- <span data-ttu-id="466a1-148">已登录的用户是全局管理员。</span><span class="sxs-lookup"><span data-stu-id="466a1-148">The signed-in user is a global admin.</span></span>
- <span data-ttu-id="466a1-149">已为租户中的所有用户启用 Teams。</span><span class="sxs-lookup"><span data-stu-id="466a1-149">Teams is enabled for all users in the tenant.</span></span>
- <span data-ttu-id="466a1-150">已在租户中启用 Office 365 组创建。</span><span class="sxs-lookup"><span data-stu-id="466a1-150">Office 365 Groups creation is enabled in the tenant.</span></span>
- <span data-ttu-id="466a1-151">StaffHub teamId 有效。</span><span class="sxs-lookup"><span data-stu-id="466a1-151">The StaffHub teamId is valid.</span></span>
- <span data-ttu-id="466a1-152">StaffHub 团队包含成员。</span><span class="sxs-lookup"><span data-stu-id="466a1-152">The StaffHub team contains members.</span></span> 
- <span data-ttu-id="466a1-153">所有 StaffHub 团队成员均已链接到 Azure AD 帐户。</span><span class="sxs-lookup"><span data-stu-id="466a1-153">All StaffHub team members are linked to an Azure AD account.</span></span> 

<span data-ttu-id="466a1-154">如果不满足这些先决条件，则迁移请求将失败。</span><span class="sxs-lookup"><span data-stu-id="466a1-154">If these prerequisites aren't met, the move request will fail.</span></span> 

### <a name="assign-teams-licenses"></a><span data-ttu-id="466a1-155">分配 Teams 许可证</span><span class="sxs-lookup"><span data-stu-id="466a1-155">Assign Teams licenses</span></span>

<span data-ttu-id="466a1-156">每个用户都必须已通过[符合条件的计划](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in)获得有效的 Microsoft 365 或 Office 365 许可证，并且已分配一个 Teams 许可证。</span><span class="sxs-lookup"><span data-stu-id="466a1-156">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="466a1-157">为用户分配 Teams 许可证可使他们获得 Teams 的访问权限。</span><span class="sxs-lookup"><span data-stu-id="466a1-157">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="466a1-158">你可以在 Microsoft 365 管理中心管理 Teams 许可证。</span><span class="sxs-lookup"><span data-stu-id="466a1-158">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="466a1-159">若要了解详细信息，请参阅[管理用户对 Teams 的访问权限](../../user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="466a1-159">To learn more, see [Manage user access to Microsoft Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="466a1-160">如果贵组织使用 Skype for Business，而你尚未准备好将所有用户迁移到 Teams，则可以为你的一线员工启用 Teams，随后他们可以将 Teams 与 Skype for Business 一起运行。</span><span class="sxs-lookup"><span data-stu-id="466a1-160">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="466a1-161">在这种称为“*并行*”的共存模式中，每个客户端应用都作为单独的解决方案运行。</span><span class="sxs-lookup"><span data-stu-id="466a1-161">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="466a1-162">要了解详细信息，请阅读[了解 Teams 和 Skype for Business 的共存和互操作性](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md)。</span><span class="sxs-lookup"><span data-stu-id="466a1-162">To learn more, read [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="install-the-staffhub-powershell-module"></a><span data-ttu-id="466a1-163">安装 StaffHub PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="466a1-163">Install the StaffHub PowerShell module</span></span>

<span data-ttu-id="466a1-164">如果你没有此模块，请[安装 StaffHub PowerShell 模块](install-the-staffhub-powershell-module.md)。</span><span class="sxs-lookup"><span data-stu-id="466a1-164">If you haven't already, [install the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span> 

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a><span data-ttu-id="466a1-165">为在 Azure AD 中没有标识的 StaffHub 用户预配帐户</span><span class="sxs-lookup"><span data-stu-id="466a1-165">Provision accounts for StaffHub users who don't have an identity in Azure AD</span></span>

<span data-ttu-id="466a1-166">每个经理和团队成员都必须在 Azure Active Directory (Azure AD) 中具有标识。</span><span class="sxs-lookup"><span data-stu-id="466a1-166">Each manager and team member must have an identity in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="466a1-167">如果用户在 Azure AD 中没有标识，请为其预配帐户。</span><span class="sxs-lookup"><span data-stu-id="466a1-167">If a user doesn't already have an identity in Azure AD, provision an account for them.</span></span> <span data-ttu-id="466a1-168">方法如下。</span><span class="sxs-lookup"><span data-stu-id="466a1-168">Here's how.</span></span> 

#### <a name="get-a-list-of-all-users-on-staffhub-teams-that-have-team-members-that-arent-provisioned-with-an-azure-ad-account"></a><span data-ttu-id="466a1-169">获取 TeamHub 团队中所有用户的列表，其团队成员未预配 Azure AD 帐户</span><span class="sxs-lookup"><span data-stu-id="466a1-169">Get a list of all users on StaffHub teams that have team members that aren't provisioned with an Azure AD account</span></span>

<span data-ttu-id="466a1-170">运行下面的命令：</span><span class="sxs-lookup"><span data-stu-id="466a1-170">Run the following:</span></span>
```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
foreach($team in $StaffHubTeams[0]) {Get-StaffHubMember -TeamId $team.Id | where {$_.Email -eq $null -or $_.State -eq "Invited"}}
```

#### <a name="provision-the-account"></a><span data-ttu-id="466a1-171">预配帐户</span><span class="sxs-lookup"><span data-stu-id="466a1-171">Provision the account</span></span>

<span data-ttu-id="466a1-172">请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="466a1-172">Do one of the following:</span></span>

- <span data-ttu-id="466a1-173">转换帐户并将其链接到预配帐户。</span><span class="sxs-lookup"><span data-stu-id="466a1-173">Convert and link the account to a provisioned account.</span></span>

  <span data-ttu-id="466a1-174">StaffHub 团队所有者和经理可以转换虚拟或非活动帐户，并将其链接到 StaffHub 中的预配帐户，方法是在 StaffHub 团队设置页面上将用户的电子邮件地址更改为有效 UPN。</span><span class="sxs-lookup"><span data-stu-id="466a1-174">StaffHub team owners and managers can convert a dummy or inactive account and link it to a provisioned account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="466a1-175">删除未设置的帐户，然后使用 UPN 重新添加帐户。</span><span class="sxs-lookup"><span data-stu-id="466a1-175">Remove the non-provisioned account and then re-add the account by using the UPN.</span></span>
    1. <span data-ttu-id="466a1-176">运行 [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) cmdlet 以从 StaffHub 团队中删除未配置的帐户。</span><span class="sxs-lookup"><span data-stu-id="466a1-176">Run the [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) cmdlet to remove the non-provisioned account from the StaffHub team.</span></span>
    2. <span data-ttu-id="466a1-177">运行 [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) cmdlet 以使用 UPN 将帐户添加回 StaffHub 团队。</span><span class="sxs-lookup"><span data-stu-id="466a1-177">Run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) cmdlet to add the account back to the StaffHub team by using the UPN.</span></span> 

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a><span data-ttu-id="466a1-178">为用户分配 FirstlineWorker 应用设置策略</span><span class="sxs-lookup"><span data-stu-id="466a1-178">Assign the FirstlineWorker app setup policy to users</span></span>

<span data-ttu-id="466a1-179">Teams 包含内置的 FirstlineWorker 应用设置策略，你可以使用该策略来自定义 Teams，以突出显示对组织内的一线员工最重要的应用。</span><span class="sxs-lookup"><span data-stu-id="466a1-179">Teams includes a built-in FirstlineWorker app setup policy that you can use to customize Teams to highlight the apps that are most important for the Firstline Workers in your organization.</span></span> <span data-ttu-id="466a1-180">为用户分配此策略时，策略中的应用程序将固定到 Teams 中的应用栏，以便快速轻松地进行访问。</span><span class="sxs-lookup"><span data-stu-id="466a1-180">When you assign this policy to users, the apps in the policy are pinned to the app bar in Teams for quick and easy access.</span></span> <span data-ttu-id="466a1-181">通过单击 Teams 桌面和 Web 客户端中的“**...更多应用**”或在 Teams 移动客户端中向上滑动，可以在应用栏中找到添加到 Teams 的其他应用。</span><span class="sxs-lookup"><span data-stu-id="466a1-181">Other apps added to Teams can be found in the app bar by clicking **... More apps** in the Teams desktop and web clients and by swiping up in the Teams mobile client.</span></span> <span data-ttu-id="466a1-182">默认情况下，FirstlineWorker 应用设置策略包括活动、排班、聊天和呼叫应用。</span><span class="sxs-lookup"><span data-stu-id="466a1-182">By default, the FirstlineWorker app setup policy includes the Activity, Shifts, Chat, and Calling apps.</span></span>

<span data-ttu-id="466a1-183">有关如何为用户分配 FirstlineWorker 应用设置策略的步骤，请参阅[使用 FirstlineWorker 应用设置策略将排班固定到 Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams)。</span><span class="sxs-lookup"><span data-stu-id="466a1-183">For steps on how to assign the FirstlineWorker app setup policy to users, see [Use the FirstlineWorker app setup policy to pin Shifts to Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span></span> <span data-ttu-id="466a1-184">分配策略后，最长可能需要 24 小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="466a1-184">After you assign a policy, it can take up to 24 hours to take effect.</span></span>

<span data-ttu-id="466a1-185">我们建议你将 StaffHub 团队和用户迁移到 Teams 之前至少提前一周完成此步骤。</span><span class="sxs-lookup"><span data-stu-id="466a1-185">We recommend you complete this step at least a week before you move your StaffHub teams and users to Teams.</span></span> <span data-ttu-id="466a1-186">当用户在 Teams 中时，请确认他们可以查看和访问排班应用。</span><span class="sxs-lookup"><span data-stu-id="466a1-186">When users are on Teams, confirm that they can see and access the Shifts app.</span></span>

<span data-ttu-id="466a1-187">你还可以创建自定义应用设置策略，并在全局应用设置策略中编辑设置。</span><span class="sxs-lookup"><span data-stu-id="466a1-187">You can also create custom app setup policies and edit the settings in the global app setup policy.</span></span> <span data-ttu-id="466a1-188">若要了解详细信息，请参阅[在 Teams 中管理应用设置策略](../../teams-app-setup-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="466a1-188">To learn more, check out [Manage app setup policies in Teams](../../teams-app-setup-policies.md).</span></span>

### <a name="onboard-users-to-teams"></a><span data-ttu-id="466a1-189">为用户提供 Teams 培训</span><span class="sxs-lookup"><span data-stu-id="466a1-189">Onboard users to Teams</span></span>

<span data-ttu-id="466a1-190">作为入职策略的一部分，为用户提供培训和指导，帮助他们熟悉 Teams。</span><span class="sxs-lookup"><span data-stu-id="466a1-190">As part of your onboarding strategy, provide training and guidance for users to help them get familiar with Teams.</span></span> <span data-ttu-id="466a1-191">与用户共享以下资源，以便他们知道从何处获得 Teams 客户端、培训和支持：</span><span class="sxs-lookup"><span data-stu-id="466a1-191">Share the following resources with users so they know where to get Teams clients, training, and support:</span></span>

- [<span data-ttu-id="466a1-192">Teams Web 客户端</span><span class="sxs-lookup"><span data-stu-id="466a1-192">Teams web client</span></span>](https://teams.microsoft.com)
- [<span data-ttu-id="466a1-193">桌面和移动客户端下载链接</span><span class="sxs-lookup"><span data-stu-id="466a1-193">Desktop and mobile client download links</span></span>](https://teams.microsoft.com/downloads)
- [<span data-ttu-id="466a1-194">Teams 培训视频</span><span class="sxs-lookup"><span data-stu-id="466a1-194">Teams training videos</span></span>](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [<span data-ttu-id="466a1-195">Teams 帮助文档</span><span class="sxs-lookup"><span data-stu-id="466a1-195">Teams Help documentation</span></span>](https://support.office.com/teams)

<span data-ttu-id="466a1-196">有关部署 Teams 和推动 Teams 采用的指南，请参阅[如何部署 Teams](../../How-to-roll-out-teams.md) 和[采用 Teams](../../adopt-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="466a1-196">For guidance on deploying Teams and driving Teams adoption, see [How to roll out Teams](../../How-to-roll-out-teams.md) and [Adopt Teams](../../adopt-microsoft-teams-landing-page.md).</span></span>

## <a name="conduct-a-pilot"></a><span data-ttu-id="466a1-197">执行试点</span><span class="sxs-lookup"><span data-stu-id="466a1-197">Conduct a user pilot</span></span>

<span data-ttu-id="466a1-198">我们建议你先为一组早期采用者迁移两个或三个 StaffHub 团队。</span><span class="sxs-lookup"><span data-stu-id="466a1-198">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="466a1-199">运行试点可帮助你优化过渡计划，并确保你已准备好将组织的所有 StaffHub 团队迁移到 Teams。</span><span class="sxs-lookup"><span data-stu-id="466a1-199">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="466a1-200">它还将确定有助于推动整个组织采用的支持者。</span><span class="sxs-lookup"><span data-stu-id="466a1-200">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="466a1-201">如果你拥有一家不需要分阶段方法的小型企业，那么本节所述的步骤即为从 StaffHub 过渡到 Teams 所需执行的全部步骤。</span><span class="sxs-lookup"><span data-stu-id="466a1-201">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="466a1-202">确定试点团队</span><span class="sxs-lookup"><span data-stu-id="466a1-202">Identify pilot teams</span></span>

<span data-ttu-id="466a1-203">请联系各个团队以确定两个或三个试点团队。</span><span class="sxs-lookup"><span data-stu-id="466a1-203">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="466a1-204">所有团队成员都应承诺使用 Teams 中的排班应用来管理其日程安排，并相互沟通和协作。</span><span class="sxs-lookup"><span data-stu-id="466a1-204">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="466a1-205">确定团队支持者</span><span class="sxs-lookup"><span data-stu-id="466a1-205">Identify team champions</span></span>

<span data-ttu-id="466a1-206">确定试点团队的支持者，并让他们帮助宣传排班应用。</span><span class="sxs-lookup"><span data-stu-id="466a1-206">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="466a1-207">团队支持者对他们的工作充满热情，将分享他们自己的知识，并为团队成员提供支持和指导。</span><span class="sxs-lookup"><span data-stu-id="466a1-207">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="466a1-208">团队支持者可以是团队所有者或经理。</span><span class="sxs-lookup"><span data-stu-id="466a1-208">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="466a1-209">通过致力于让每位团队成员[获取 Teams 客户端](../../get-clients.md)、登录 Teams 并在排班应用中查看其日程安排以及开始相互聊天，团队支持者应确保这些成员参与其中。</span><span class="sxs-lookup"><span data-stu-id="466a1-209">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="466a1-210">已熟悉 StaffHub 的用户可在排班应用中快速启动并运行。</span><span class="sxs-lookup"><span data-stu-id="466a1-210">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="466a1-211">你还可以指向[排班帮助](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)以获取更多帮助。</span><span class="sxs-lookup"><span data-stu-id="466a1-211">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team"></a><span data-ttu-id="466a1-212">迁移 StaffHub 团队</span><span class="sxs-lookup"><span data-stu-id="466a1-212">Move a StaffHub team</span></span>

<span data-ttu-id="466a1-213">使用这些步骤一次迁移一个 StaffHub 团队。</span><span class="sxs-lookup"><span data-stu-id="466a1-213">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="466a1-214">我们建议为你的试点团队推荐这种方法。</span><span class="sxs-lookup"><span data-stu-id="466a1-214">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="466a1-215">之后，当你准备好迁移组织的所有 StaffHub 团队时，请参阅[迁移 StaffHub 团队](#move-your-staffhub-teams)，了解有关如何一次迁移多个团队的步骤。</span><span class="sxs-lookup"><span data-stu-id="466a1-215">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="466a1-216">运行以下命令以迁移 StaffHub 团队。</span><span class="sxs-lookup"><span data-stu-id="466a1-216">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -TeamId <String>
```
<span data-ttu-id="466a1-217">示例：</span><span class="sxs-lookup"><span data-stu-id="466a1-217">Example</span></span>

```
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="466a1-218">以下是当你提交将 StaffHub 团队迁移到 Teams 的请求时获得的响应示例。</span><span class="sxs-lookup"><span data-stu-id="466a1-218">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="466a1-219">若要检查迁移请求的状态，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="466a1-219">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <String>
```
<span data-ttu-id="466a1-220">示例：</span><span class="sxs-lookup"><span data-stu-id="466a1-220">Example</span></span>

```
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

<span data-ttu-id="466a1-221">以下是你在迁移过程中获得的响应示例。</span><span class="sxs-lookup"><span data-stu-id="466a1-221">Here's an example of the response you get when a move is in progress.</span></span>

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a><span data-ttu-id="466a1-222">将文件从 StaffHub 团队迁移到 Teams</span><span class="sxs-lookup"><span data-stu-id="466a1-222">Move files from a StaffHub team to Teams</span></span>

<span data-ttu-id="466a1-223">此步骤仅适用于以下情形，即已迁移到 Teams 的 StaffHub 团队还包含要迁移到 Teams 的文件。</span><span class="sxs-lookup"><span data-stu-id="466a1-223">This step only applies if the StaffHub team that you moved to Teams has files that you want to also move to Teams.</span></span> <span data-ttu-id="466a1-224">你可以直接在 SharePoint Online 中或使用 PowerShell 来迁移这些文件。</span><span class="sxs-lookup"><span data-stu-id="466a1-224">You can move files directly in SharePoint Online or by using PowerShell.</span></span> 

#### <a name="in-sharepoint-online"></a><span data-ttu-id="466a1-225">在 SharePoint Online 中</span><span class="sxs-lookup"><span data-stu-id="466a1-225">In SharePoint Online</span></span>

<span data-ttu-id="466a1-226">请参阅[如何在 SharePoint Online 中迁移文件](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30)。</span><span class="sxs-lookup"><span data-stu-id="466a1-226">See [How to move files in SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="466a1-227">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="466a1-227">Using Windows PowerShell</span></span>

<span data-ttu-id="466a1-228">下载并安装 [SharePoint Online 命令行管理程序](https://www.microsoft.com/download/details.aspx?id=35588)（如果尚未安装）。</span><span class="sxs-lookup"><span data-stu-id="466a1-228">Download and install the [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588), if you haven't already.</span></span> <span data-ttu-id="466a1-229">其中包含迁移文件所需的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="466a1-229">It contains the cmdlets you need to move files.</span></span>  

<span data-ttu-id="466a1-230">使用 [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) cmdlet 连接到 SharePoint Online 团队网站。</span><span class="sxs-lookup"><span data-stu-id="466a1-230">Use the [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) cmdlet to connect to the SharePoint Online team site.</span></span>

```
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

<span data-ttu-id="466a1-231">对于要从 StaffHub 迁移到 Teams 的每个文件，请使用 [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) cmdlet 来迁移这些文件。</span><span class="sxs-lookup"><span data-stu-id="466a1-231">For each file that you want to move from StaffHub to Teams, use the [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) cmdlet to move the file.</span></span>

```
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

<span data-ttu-id="466a1-232">若要迁移多个文件，请遍历各个文件并在循环时运行第二个命令。</span><span class="sxs-lookup"><span data-stu-id="466a1-232">To move multiple files, loop over the files and run the second command on the loop.</span></span> <span data-ttu-id="466a1-233">如果会话保持活动状态，则无需重复第一个命令。</span><span class="sxs-lookup"><span data-stu-id="466a1-233">You don't need to repeat the first command if the session remains active.</span></span>

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a><span data-ttu-id="466a1-234">超越试点并迁移所有 StaffHub 团队</span><span class="sxs-lookup"><span data-stu-id="466a1-234">Go beyond your pilot and move all StaffHub teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="466a1-235">提高意识</span><span class="sxs-lookup"><span data-stu-id="466a1-235">Raise awareness</span></span>

<span data-ttu-id="466a1-236">如果你已准备好超越试点团队并将组织的 StaffHub 团队迁移到 Teams，则需要在整个组织内传达更改，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="466a1-236">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="466a1-237">宣传关于排班应用和向 Teams 过渡的信息，以提高意识、激发热情并推动采用。</span><span class="sxs-lookup"><span data-stu-id="466a1-237">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams"></a><span data-ttu-id="466a1-238">迁移 StaffHub 团队</span><span class="sxs-lookup"><span data-stu-id="466a1-238">Move your StaffHub teams to Shifts in Microsoft Teams</span></span>

<span data-ttu-id="466a1-239">使用这些步骤批量迁移 StaffHub 团队。</span><span class="sxs-lookup"><span data-stu-id="466a1-239">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="466a1-240">你可以选择迁移组织的所有 StaffHub 团队或迁移特定 StaffHub 团队。</span><span class="sxs-lookup"><span data-stu-id="466a1-240">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="466a1-241">如果你希望一次迁移一个 StaffHub 团队，请参阅[迁移 StaffHub 团队](#move-a-staffhub-team)。</span><span class="sxs-lookup"><span data-stu-id="466a1-241">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team).</span></span>

#### <a name="move-all-staffhub-teams"></a><span data-ttu-id="466a1-242">迁移所有 StaffHub 团队</span><span class="sxs-lookup"><span data-stu-id="466a1-242">Move all StaffHub teams</span></span>

<span data-ttu-id="466a1-243">运行以下命令以获取组织中所有 StaffHub 团队的列表。</span><span class="sxs-lookup"><span data-stu-id="466a1-243">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="466a1-244">然后，运行以下命令以迁移所有团队。</span><span class="sxs-lookup"><span data-stu-id="466a1-244">Then, run the following to move all teams.</span></span>

```
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

<span data-ttu-id="466a1-245">以下是响应示例。</span><span class="sxs-lookup"><span data-stu-id="466a1-245">Here's an example of the response.</span></span>

<span data-ttu-id="466a1-246">对于已迁移到 Teams 或已存在于 Teams 的任何团队，jobId 将为“null”，因为无需提交作业即可迁移该团队。</span><span class="sxs-lookup"><span data-stu-id="466a1-246">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a><span data-ttu-id="466a1-247">迁移特定 StaffHub 团队</span><span class="sxs-lookup"><span data-stu-id="466a1-247">Move specific StaffHub teams</span></span>

<span data-ttu-id="466a1-248">运行以下命令以获取组织中所有 StaffHub 团队 ID 的列表。</span><span class="sxs-lookup"><span data-stu-id="466a1-248">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="466a1-249">在由先前运行的 `Get-StaffHubteamsForTenant` cmdlet 返回的结果中，选择要迁移的团队 ID，然后将它们添加到逗号分隔值 (CSV) 文件中。</span><span class="sxs-lookup"><span data-stu-id="466a1-249">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="466a1-250">以下是如何格式化 CSV 文件的示例。</span><span class="sxs-lookup"><span data-stu-id="466a1-250">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="466a1-251">Id</span><span class="sxs-lookup"><span data-stu-id="466a1-251">ID</span></span>  |
|---------|
|<span data-ttu-id="466a1-252">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="466a1-252">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="466a1-253">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="466a1-253">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="466a1-254">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="466a1-254">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="466a1-255">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="466a1-255">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="466a1-256">创建 CSV 文件后，运行以下命令以迁移你在 CSV 文件中指定的团队。</span><span class="sxs-lookup"><span data-stu-id="466a1-256">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```
$StaffHubTeams = Import-Csv .\teams.csv
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a><span data-ttu-id="466a1-257">确认你的 StaffHub 团队已迁移到 Teams</span><span class="sxs-lookup"><span data-stu-id="466a1-257">Confirm that your StaffHub teams have moved to Teams</span></span>

<span data-ttu-id="466a1-258">运行以下命令以获取组织的排班应用中的所有团队列表。</span><span class="sxs-lookup"><span data-stu-id="466a1-258">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a><span data-ttu-id="466a1-259">将文件从 StaffHub 团队迁移到 Teams</span><span class="sxs-lookup"><span data-stu-id="466a1-259">Move files from your StaffHub teams to Teams</span></span>

<span data-ttu-id="466a1-260">如果已迁移的 StaffHub 团队还包含要迁移到 Teams 的文件，请参阅[将文件从 StaffHub 团队迁移到 Teams](#move-files-from-a-staffhub-team-to-teams)。</span><span class="sxs-lookup"><span data-stu-id="466a1-260">If the StaffHub teams that you moved contain files that you also want to move to Teams, see [Move files from a StaffHub team to Teams](#move-files-from-a-staffhub-team-to-teams).</span></span>

## <a name="monitor-teams-usage"></a><span data-ttu-id="466a1-261">监视 Teams 使用情况</span><span class="sxs-lookup"><span data-stu-id="466a1-261">Monitor Teams usage against your baseline</span></span>

<span data-ttu-id="466a1-262">使用情况报告可以帮助你更好地了解使用模式，并为你提供相关见解，让你了解在组织内的何处设置培训和通信工作的优先级。</span><span class="sxs-lookup"><span data-stu-id="466a1-262">Usage reports can help you better understand usage patterns, and along with user feedback, give you insights to inform your wider rollout and where to prioritize training and communication efforts.</span></span> <span data-ttu-id="466a1-263">由于排班是 Teams 中的应用，因此你可以通过 Teams 报告查看使用情况。</span><span class="sxs-lookup"><span data-stu-id="466a1-263">Because Shifts is an app in Teams, you can view usage through Teams reports.</span></span> <span data-ttu-id="466a1-264">有关详细信息，请参阅 [Microsoft Teams 管理中心中的 Teams 报告](../../teams-analytics-and-reports/teams-reporting-reference.md)和 [Microsoft 365 管理中心中的 Teams 活动报告](../../teams-activity-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="466a1-264">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="466a1-265">疑难解答</span><span class="sxs-lookup"><span data-stu-id="466a1-265">Troubleshooting</span></span> 

<span data-ttu-id="466a1-266">**当你尝试将文件从 StaffHub 迁移到 Teams 时，你会收到“权限被拒绝”错误消息。**</span><span class="sxs-lookup"><span data-stu-id="466a1-266">**When you try to move files from StaffHub to Teams, you get a "Permission denied" error message.**</span></span>

<span data-ttu-id="466a1-267">如果你尝试在自己不是其成员的私有 Office 365 组中迁移文件，则可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="466a1-267">This may occur if you're trying to move files in a private Office 365 group that you're not a member of.</span></span> <span data-ttu-id="466a1-268">如果是这种情况，请使用 [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) cmdlet 将自己添加到 StaffHub 团队，然后迁移这些文件。</span><span class="sxs-lookup"><span data-stu-id="466a1-268">If this is the case, use the [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) cmdlet to add yourself to the StaffHub team, and then move the files.</span></span> <span data-ttu-id="466a1-269">迁移文件后，请使用 [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) cmdlet 将你自己从团队中删除。</span><span class="sxs-lookup"><span data-stu-id="466a1-269">After you move the files, use the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) cmdlet to remove yourself from the team.</span></span> 

<span data-ttu-id="466a1-270">**当你尝试将文件从 StaffHub 迁移到 Teams 时，你会收到一则错误消息，指出“常规”文件夹不存在。**</span><span class="sxs-lookup"><span data-stu-id="466a1-270">**When you try to move files from StaffHub to Teams, you get an error that says the General folder doesn't exist.**</span></span>

<span data-ttu-id="466a1-271">运行以下命令以将“常规”文件夹添加到 SharePoint，然后重试：</span><span class="sxs-lookup"><span data-stu-id="466a1-271">Run the following command to add the General folder to SharePoint, and then try again:</span></span>

  ```
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a><span data-ttu-id="466a1-272">相关主题</span><span class="sxs-lookup"><span data-stu-id="466a1-272">Related topics</span></span>
- [<span data-ttu-id="466a1-273">如何部署 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="466a1-273">How to roll out Microsoft Teams</span></span>](../../How-to-roll-out-teams.md)
- [<span data-ttu-id="466a1-274">Microsoft StaffHub 将停用</span><span class="sxs-lookup"><span data-stu-id="466a1-274">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="466a1-275">在 Microsoft Teams 中为组织管理排班应用</span><span class="sxs-lookup"><span data-stu-id="466a1-275">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="466a1-276">StaffHub PowerShell 参考</span><span class="sxs-lookup"><span data-stu-id="466a1-276">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
