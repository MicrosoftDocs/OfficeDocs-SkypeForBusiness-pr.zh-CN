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
description: 了解如何移动 Microsoft StaffHub 团队并将数据安排到 Microsoft 团队中的倒班。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: b6354c2edd4d8504aeb2c84715b982f6bf793d33
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548291"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="53587-103">将 Microsoft StaffHub 团队移动到 Microsoft 团队中的倒班</span><span class="sxs-lookup"><span data-stu-id="53587-103">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="53587-104">2019年10月1日生效, Microsoft StaffHub 将停用。</span><span class="sxs-lookup"><span data-stu-id="53587-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="53587-105">我们正在将 StaffHub 功能构建到 Microsoft 团队中。</span><span class="sxs-lookup"><span data-stu-id="53587-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="53587-106">今天, 团队包括 "倒班" 应用, 用于计划管理, 而其他功能将随着时间的推移而推出。</span><span class="sxs-lookup"><span data-stu-id="53587-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="53587-107">StaffHub 将停止为2019年10月1日的所有用户工作。</span><span class="sxs-lookup"><span data-stu-id="53587-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="53587-108">任何试图打开 StaffHub 的人都将显示一条消息, 指导他们下载团队。</span><span class="sxs-lookup"><span data-stu-id="53587-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="53587-109">若要了解详细信息, 请参阅[Microsoft StaffHub 已停用](microsoft-staffhub-to-be-retired.md)。</span><span class="sxs-lookup"><span data-stu-id="53587-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

> <span data-ttu-id="53587-110">本文中讨论的功能尚未发布。</span><span class="sxs-lookup"><span data-stu-id="53587-110">The capability discussed in this article hasn't yet been released.</span></span> <span data-ttu-id="53587-111">它已宣布推出, 即将在2019年6月早些时候推出。</span><span class="sxs-lookup"><span data-stu-id="53587-111">It's been announced, and is coming soon, in early June 2019.</span></span> <span data-ttu-id="53587-112">如果您是管理员, 则可以在邮件中心 (在[Microsoft 365 管理中心](https://portal.office.com/adminportal/home)) 中了解何时将提供此功能。</span><span class="sxs-lookup"><span data-stu-id="53587-112">If you're an admin, you can find out when this will be available in the Message Center (in the [Microsoft 365 admin center](https://portal.office.com/adminportal/home)).</span></span>

<span data-ttu-id="53587-113">团队中的倒班应用提供了一种简单的方法来管理计划, 以及每天发生的班次交换和取消的持续流。</span><span class="sxs-lookup"><span data-stu-id="53587-113">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="53587-114">团队成员可以直接在应用和其设备上访问其计划和转移信息, 以设置其首选项、管理其计划和请求超时。</span><span class="sxs-lookup"><span data-stu-id="53587-114">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="53587-115">本文将向你介绍如何移动组织的 StaffHub 团队并将数据安排到团队中的倒班。</span><span class="sxs-lookup"><span data-stu-id="53587-115">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="53587-116">无论您是拥有一个或两个 StaffHub 团队的小型企业, 还是有数百个 StaffHub 团队的大型企业, 在这里, 您将找到所需的管理员指南, 帮助您成功过渡到团队。</span><span class="sxs-lookup"><span data-stu-id="53587-116">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="53587-117">只有全局管理员才能执行本文中的步骤。</span><span class="sxs-lookup"><span data-stu-id="53587-117">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="53587-118">如果尚未执行此操作, 请查看[StaffHub 退休常见问题](microsoft-staffhub-to-be-retired.md), 获取你可能遇到的任何问题的答案。</span><span class="sxs-lookup"><span data-stu-id="53587-118">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span> 

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="53587-119">您需要了解的有关迁移到团队的哪些信息</span><span class="sxs-lookup"><span data-stu-id="53587-119">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="53587-120">何时转到团队</span><span class="sxs-lookup"><span data-stu-id="53587-120">When to move to Teams</span></span>

<span data-ttu-id="53587-121">将在2019年10月1日生效, StaffHub 将停用。</span><span class="sxs-lookup"><span data-stu-id="53587-121">Effective October 1, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="53587-122">我们鼓励你立即开始使用团队, 并开始从 StaffHub 过渡你的组织的团队和用户。</span><span class="sxs-lookup"><span data-stu-id="53587-122">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="53587-123">在 StaffHub 中, 如果计划管理是最常用的功能, 我们建议你使用团队中的倒班应用继续。</span><span class="sxs-lookup"><span data-stu-id="53587-123">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="53587-124">哪些内容被移动到团队</span><span class="sxs-lookup"><span data-stu-id="53587-124">What is moved to Teams</span></span>

<span data-ttu-id="53587-125">用户详细信息、日程安排信息和聊天和文件数据将转换为团队。</span><span class="sxs-lookup"><span data-stu-id="53587-125">User details, schedule information, and chat and file data are transitioned to Teams.</span></span> <span data-ttu-id="53587-126">这包括过去90天的团队成员身份、团队日程安排以及聊天和文件。</span><span class="sxs-lookup"><span data-stu-id="53587-126">This includes team membership, team schedules, and chats and files from the last 90 days.</span></span>

<span data-ttu-id="53587-127">每个 StaffHub 团队都需要一个相应的 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="53587-127">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="53587-128">如果 StaffHub 团队没有与之关联的 Office 365 组, 则会自动为您创建一个以支持切换。</span><span class="sxs-lookup"><span data-stu-id="53587-128">If a StaffHub team doesn't have an Office 365 Group associated with it, one is automatically created for you to support the transition.</span></span> <span data-ttu-id="53587-129">由于团队和 StaffHub 之间的团队和组命名之间的差异, 团队中可能会显示不同的团队名称。</span><span class="sxs-lookup"><span data-stu-id="53587-129">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span>

<span data-ttu-id="53587-130">当您将团队从 StaffHub 过渡到团队时, 用户将无法再访问其在 StaffHub 中的日程安排, 并且会被重定向到团队中的倒班。</span><span class="sxs-lookup"><span data-stu-id="53587-130">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="53587-131">我们建议你将此更改与你的组织进行沟通, 以最大限度地减少中断, 并鼓励用户采纳和探索团队。</span><span class="sxs-lookup"><span data-stu-id="53587-131">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span> <span data-ttu-id="53587-132">如果你有 Azure AD Premium, 则可以[运行报表](run-report-to-show-staffhub-usage.md)来获取组织中需要了解此更改的 StaffHub 用户的列表。</span><span class="sxs-lookup"><span data-stu-id="53587-132">If you have Azure AD Premium, you can [run a report](run-report-to-show-staffhub-usage.md) to get a list of StaffHub users in your organization who need to know about this change.</span></span>  

<span data-ttu-id="53587-133">将 StaffHub 团队移动到团队后, 没有回滚选项。</span><span class="sxs-lookup"><span data-stu-id="53587-133">There's no rollback option after you move a StaffHub team to Teams.</span></span>

### <a name="user-experience-when-you-move-a-team"></a><span data-ttu-id="53587-134">移动团队时的用户体验</span><span class="sxs-lookup"><span data-stu-id="53587-134">User experience when you move a team</span></span>

<span data-ttu-id="53587-135">当用户的团队从 StaffHub 切换到团队成员时, 停机时间最少 (如果有)。</span><span class="sxs-lookup"><span data-stu-id="53587-135">There's minimal downtime (less than a second, if any at all) for users when their team is switched from StaffHub to Shifts in Teams.</span></span> <span data-ttu-id="53587-136">用户可以继续使用 StaffHub, 直到完成到团队的移动。</span><span class="sxs-lookup"><span data-stu-id="53587-136">Users can continue using StaffHub until the move to Teams is completed.</span></span> <span data-ttu-id="53587-137">完成移动后, 团队成员将看到一条消息, 告知他们需要开始使用团队中的倒班访问其团队日程。</span><span class="sxs-lookup"><span data-stu-id="53587-137">When the move is completed, team members will see a message to let them know that they need to start using Shifts in Teams to access their team schedule.</span></span> <span data-ttu-id="53587-138">下面是用户在 StaffHub 团队移到团队后在 StaffHub 中看到的消息的示例。</span><span class="sxs-lookup"><span data-stu-id="53587-138">Here's an example of the message that users see in StaffHub after the StaffHub team is moved to Teams.</span></span>

<span data-ttu-id="53587-139">![用户看到的消息的示例。](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "用户在 StaffHub 团队移到团队后在 StaffHub 中看到的消息示例")</span><span class="sxs-lookup"><span data-stu-id="53587-139">![Example of the message that users see.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Example of the message that users see in StaffHub after the StaffHub team is moved to Teams")</span></span>

## <a name="prepare"></a><span data-ttu-id="53587-140">准备</span><span class="sxs-lookup"><span data-stu-id="53587-140">Prepare</span></span>

<span data-ttu-id="53587-141">下面介绍了如何准备迁移到团队。</span><span class="sxs-lookup"><span data-stu-id="53587-141">Here's how to prepare for the move to Teams.</span></span>

### <a name="assign-teams-licenses"></a><span data-ttu-id="53587-142">分配 Teams 许可证</span><span class="sxs-lookup"><span data-stu-id="53587-142">Assign Teams licenses</span></span>

<span data-ttu-id="53587-143">每个用户都必须具有[符合条件的计划](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in)的活动 Microsoft 365 或 Office 365 许可证, 并且必须分配有团队许可证。</span><span class="sxs-lookup"><span data-stu-id="53587-143">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan ](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="53587-144">为用户分配团队许可证后, 他们可以访问团队。</span><span class="sxs-lookup"><span data-stu-id="53587-144">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="53587-145">可在 Microsoft 365 管理中心内管理团队许可证。</span><span class="sxs-lookup"><span data-stu-id="53587-145">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="53587-146">若要了解详细信息, 请参阅[管理用户对团队的访问权限](../../user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="53587-146">To learn more, see [Manage user access to Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="53587-147">如果你的组织使用 Skype for Business, 并且尚未准备好将所有用户移到团队, 你可以为你的一线工作人员启用团队, 然后将团队与 Skype for Business 一起运行。</span><span class="sxs-lookup"><span data-stu-id="53587-147">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="53587-148">在此共存模式 (名为 "*岛*") 中, 每个客户端应用都作为单独的解决方案运行。</span><span class="sxs-lookup"><span data-stu-id="53587-148">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="53587-149">若要了解详细信息, 请参阅[了解团队和 Skype for business 共存和互操作性](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md)。</span><span class="sxs-lookup"><span data-stu-id="53587-149">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a><span data-ttu-id="53587-150">为在 Azure AD 中没有标识的 StaffHub 用户设置帐户</span><span class="sxs-lookup"><span data-stu-id="53587-150">Provision accounts for StaffHub users who don't have an identity in Azure AD</span></span>

<span data-ttu-id="53587-151">每个管理者和团队成员都必须在 Azure Active Directory (Azure AD) 中拥有一个标识。</span><span class="sxs-lookup"><span data-stu-id="53587-151">Each manager and team member must have an identity in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="53587-152">如果用户在 Azure AD 中尚没有标识, 请为其设置帐户。</span><span class="sxs-lookup"><span data-stu-id="53587-152">If a user doesn't already have an identity in Azure AD, provision an account for them.</span></span> <span data-ttu-id="53587-153">方法如下。</span><span class="sxs-lookup"><span data-stu-id="53587-153">Here's how.</span></span>

- <span data-ttu-id="53587-154">StaffHub 团队所有者和经理可以通过将用户的电子邮件地址更改为 "StaffHub 团队设置" 页面上的有效 UPN 来转换虚拟或非活动帐户并将其链接到 StaffHub 中的预配帐户。</span><span class="sxs-lookup"><span data-stu-id="53587-154">StaffHub team owners and managers can convert a dummy or inactive account and link it to a provisioned account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="53587-155">管理员可以运行[StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps)和[StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) cmdlet 从 StaffHub 团队中删除非预配帐户, 并使用 UPN 重新添加帐户。</span><span class="sxs-lookup"><span data-stu-id="53587-155">Admins can run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) and [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) cmdlets to remove a non-provisioned account from a StaffHub team and add the account back by using the UPN.</span></span>

### <a name="install-the-staffhub-powershell-module"></a><span data-ttu-id="53587-156">安装 StaffHub PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="53587-156">Install the StaffHub PowerShell module</span></span>

<span data-ttu-id="53587-157">如果尚未安装, 请[安装 StaffHub PowerShell 模块](install-the-staffhub-powershell-module.md)。</span><span class="sxs-lookup"><span data-stu-id="53587-157">If you haven't already, [install the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span>

<span data-ttu-id="53587-158">移动 StaffHub 团队时, 移动请求将检查系统必备。</span><span class="sxs-lookup"><span data-stu-id="53587-158">When you move a StaffHub team, the move request checks for prerequisites.</span></span> <span data-ttu-id="53587-159">以下是移动请求可能失败的原因:</span><span class="sxs-lookup"><span data-stu-id="53587-159">Here's reasons why a move request may fail:</span></span>

- <span data-ttu-id="53587-160">登录用户不是全局管理员</span><span class="sxs-lookup"><span data-stu-id="53587-160">The signed-in user is not a global admin</span></span>
- <span data-ttu-id="53587-161">已针对租户中的所有用户禁用团队</span><span class="sxs-lookup"><span data-stu-id="53587-161">Teams is disabled for all users in the tenant</span></span>
- <span data-ttu-id="53587-162">租户中已禁用 Office 365 组创建</span><span class="sxs-lookup"><span data-stu-id="53587-162">Office 365 Groups creation is disabled in the tenant</span></span>
- <span data-ttu-id="53587-163">StaffHub teamId 无效或没有成员</span><span class="sxs-lookup"><span data-stu-id="53587-163">The StaffHub teamId is not valid or has no members</span></span>
- <span data-ttu-id="53587-164">StaffHub 团队包含未链接到 Azure AD 帐户的成员</span><span class="sxs-lookup"><span data-stu-id="53587-164">The StaffHub team includes members that aren't linked to an Azure AD account</span></span>  

## <a name="run-a-pilot"></a><span data-ttu-id="53587-165">运行试验</span><span class="sxs-lookup"><span data-stu-id="53587-165">Run a pilot</span></span>

<span data-ttu-id="53587-166">我们建议您首先将两个或三个 StaffHub 团队移动到一组早期采纳者。</span><span class="sxs-lookup"><span data-stu-id="53587-166">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="53587-167">运行试验可帮助你优化过渡计划, 并确保你已准备好将组织的所有 StaffHub 团队移动到团队。</span><span class="sxs-lookup"><span data-stu-id="53587-167">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="53587-168">它还标识了可帮助推动组织内采用的拥护者。</span><span class="sxs-lookup"><span data-stu-id="53587-168">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="53587-169">如果您是不需要分阶段方法的小型企业, 那么本部分中的步骤可能是您将从 StaffHub 切换到团队的所有步骤。</span><span class="sxs-lookup"><span data-stu-id="53587-169">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="53587-170">确定试生产团队</span><span class="sxs-lookup"><span data-stu-id="53587-170">Identify pilot teams</span></span>

<span data-ttu-id="53587-171">联系以确定两个或三个试验团队。</span><span class="sxs-lookup"><span data-stu-id="53587-171">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="53587-172">所有团队成员都应承诺使用团队中的倒班管理其日程并相互沟通和协作。</span><span class="sxs-lookup"><span data-stu-id="53587-172">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="53587-173">确定团队拥护人员</span><span class="sxs-lookup"><span data-stu-id="53587-173">Identify team champions</span></span>

<span data-ttu-id="53587-174">在试点团队中确定拥护人员, 并登记它们以帮助布道倒班。</span><span class="sxs-lookup"><span data-stu-id="53587-174">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="53587-175">团队拥护者热心他们所做的工作, 分享他们自己的发现以向团队成员提供支持和指导。</span><span class="sxs-lookup"><span data-stu-id="53587-175">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="53587-176">团队拥护者可以是团队所有者或经理。</span><span class="sxs-lookup"><span data-stu-id="53587-176">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="53587-177">团队拥护者应确保团队成员可以通过专门的时间让每个人[获得团队客户](../../get-clients.md), 登录团队并查看他们的日程安排, 并相互开始聊天。</span><span class="sxs-lookup"><span data-stu-id="53587-177">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="53587-178">已熟悉 StaffHub 的用户将在倒班中快速启动并运行。</span><span class="sxs-lookup"><span data-stu-id="53587-178">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="53587-179">你还可以指向它们以[移动帮助](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)以获取其他帮助。</span><span class="sxs-lookup"><span data-stu-id="53587-179">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team-coming-soon"></a><span data-ttu-id="53587-180">移动 StaffHub 团队 (即将推出)</span><span class="sxs-lookup"><span data-stu-id="53587-180">Move a StaffHub team (coming soon)</span></span>

<span data-ttu-id="53587-181">使用以下步骤一次移动一个 StaffHub 团队。</span><span class="sxs-lookup"><span data-stu-id="53587-181">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="53587-182">我们建议你的试点团队采用此方法。</span><span class="sxs-lookup"><span data-stu-id="53587-182">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="53587-183">稍后, 当你准备好移动组织的所有 StaffHub 团队时, 请参阅[移动你的 StaffHub 团队](#move-your-staffhub-teams-coming-soon), 了解如何一次移动多个团队的步骤。</span><span class="sxs-lookup"><span data-stu-id="53587-183">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams-coming-soon) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="53587-184">运行以下操作以移动 StaffHub 团队。</span><span class="sxs-lookup"><span data-stu-id="53587-184">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -TeamId <String>

Sample:

Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="53587-185">下面是提交请求以将 StaffHub 团队移动到团队时收到的答复的示例。</span><span class="sxs-lookup"><span data-stu-id="53587-185">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="53587-186">若要检查移动请求的状态, 请运行以下。</span><span class="sxs-lookup"><span data-stu-id="53587-186">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <String>

Sample:
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"

```

<span data-ttu-id="53587-187">下面是在移动进行过程中获取的响应的示例。</span><span class="sxs-lookup"><span data-stu-id="53587-187">Here's an example of the response you get when a move is in progress.</span></span>

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

## <a name="make-the-transition-from-staffhub-to-teams"></a><span data-ttu-id="53587-188">从 StaffHub 切换到团队</span><span class="sxs-lookup"><span data-stu-id="53587-188">Make the transition from StaffHub to Teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="53587-189">提高意识</span><span class="sxs-lookup"><span data-stu-id="53587-189">Raise awareness</span></span>

<span data-ttu-id="53587-190">当您准备好超越试点团队, 并将组织的 StaffHub 团队移动到团队时, 首先要在组织中传达更改, 这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="53587-190">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="53587-191">传播关于倒班和过渡到团队的内容, 以提高意识、产生兴奋和推动采纳。</span><span class="sxs-lookup"><span data-stu-id="53587-191">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams-coming-soon"></a><span data-ttu-id="53587-192">移动 StaffHub 团队 (即将推出)</span><span class="sxs-lookup"><span data-stu-id="53587-192">Move your StaffHub teams (coming soon)</span></span>

<span data-ttu-id="53587-193">使用以下步骤批量移动 StaffHub 团队。</span><span class="sxs-lookup"><span data-stu-id="53587-193">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="53587-194">你可以选择移动组织的所有 StaffHub 团队或移动特定的 StaffHub 团队。</span><span class="sxs-lookup"><span data-stu-id="53587-194">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="53587-195">如果想要一次移动一个团队, 请参阅[移动 StaffHub 团队](#move-a-staffhub-team-coming-soon)。</span><span class="sxs-lookup"><span data-stu-id="53587-195">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team-coming-soon).</span></span>

#### <a name="move-all-staffhub-teams-coming-soon"></a><span data-ttu-id="53587-196">移动所有 StaffHub 团队 (即将推出)</span><span class="sxs-lookup"><span data-stu-id="53587-196">Move all StaffHub teams (coming soon)</span></span>

<span data-ttu-id="53587-197">运行以下操作以获取组织中所有 StaffHub 团队的列表。</span><span class="sxs-lookup"><span data-stu-id="53587-197">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="53587-198">然后, 运行以下操作以移动所有团队。</span><span class="sxs-lookup"><span data-stu-id="53587-198">Then, run the following to move all teams.</span></span>

```
$StaffHubTeams | foreach {Move-StaffHubTeam -TeamId {$_.Id}}
```

<span data-ttu-id="53587-199">下面是该响应的一个示例。</span><span class="sxs-lookup"><span data-stu-id="53587-199">Here's an example of the response.</span></span>

<span data-ttu-id="53587-200">对于已迁移到团队或已存在于团队中的任何团队, 作业 Id 将为 "null", 因为不需要提交作业即可移动该团队。</span><span class="sxs-lookup"><span data-stu-id="53587-200">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams-coming-soon"></a><span data-ttu-id="53587-201">移动特定的 StaffHub 团队 (即将推出)</span><span class="sxs-lookup"><span data-stu-id="53587-201">Move specific StaffHub teams (coming soon)</span></span>

<span data-ttu-id="53587-202">运行以下操作以获取组织中所有 StaffHub 团队 Id 的列表。</span><span class="sxs-lookup"><span data-stu-id="53587-202">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="53587-203">在之前运行的`Get-StaffHubteamsForTenant` cmdlet 返回的结果中, 选择要移动的团队 id, 然后将其添加到逗号分隔值 (CSV) 文件。</span><span class="sxs-lookup"><span data-stu-id="53587-203">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="53587-204">下面是如何设置 CSV 文件格式的示例。</span><span class="sxs-lookup"><span data-stu-id="53587-204">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="53587-205">标识号</span><span class="sxs-lookup"><span data-stu-id="53587-205">Id</span></span>  |
|---------|
|<span data-ttu-id="53587-206">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="53587-206">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="53587-207">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="53587-207">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="53587-208">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="53587-208">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="53587-209">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="53587-209">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="53587-210">创建 CSV 文件后, 请运行以下操作以移动您在 CSV 文件中指定的团队。</span><span class="sxs-lookup"><span data-stu-id="53587-210">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```
Import-Csv .\teams.txt | foreach {Move-StaffHubTeam -TeamdId {$_.Id}}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams-coming-soon"></a><span data-ttu-id="53587-211">确认你的 StaffHub 团队已迁移到团队 (即将推出)</span><span class="sxs-lookup"><span data-stu-id="53587-211">Confirm that your StaffHub teams have moved to Teams (coming soon)</span></span>

<span data-ttu-id="53587-212">运行以下操作, 获取组织中所有团队成员的列表。</span><span class="sxs-lookup"><span data-stu-id="53587-212">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

## <a name="monitor-teams-usage"></a><span data-ttu-id="53587-213">监视团队使用情况</span><span class="sxs-lookup"><span data-stu-id="53587-213">Monitor Teams usage</span></span>

<span data-ttu-id="53587-214">使用情况报告可帮助你更好地了解使用模式, 并向你提供有关在你的组织中对培训和沟通工作进行排序的位置的见解。</span><span class="sxs-lookup"><span data-stu-id="53587-214">Usage reports can help you better understand usage patterns and give you insights on where to prioritize training and communication efforts across your organization.</span></span> <span data-ttu-id="53587-215">由于倒班是团队中的应用, 因此你可以通过团队报表查看使用情况。</span><span class="sxs-lookup"><span data-stu-id="53587-215">Because Shifts is an app in Teams, you can view usage through Teams reports.</span></span> <span data-ttu-id="53587-216">有关详细信息, 请参阅 Microsoft[团队管理中心中的团队报告](../../teams-analytics-and-reports/teams-reporting-reference.md)和[microsoft 365 管理中心中的团队活动报表](../../teams-activity-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="53587-216">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="53587-217">相关主题</span><span class="sxs-lookup"><span data-stu-id="53587-217">Related topics</span></span>
- [<span data-ttu-id="53587-218">Microsoft StaffHub 将停用</span><span class="sxs-lookup"><span data-stu-id="53587-218">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="53587-219">在 Microsoft Teams 中为组织管理 Shifts 应用</span><span class="sxs-lookup"><span data-stu-id="53587-219">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="53587-220">StaffHub PowerShell 参考</span><span class="sxs-lookup"><span data-stu-id="53587-220">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
