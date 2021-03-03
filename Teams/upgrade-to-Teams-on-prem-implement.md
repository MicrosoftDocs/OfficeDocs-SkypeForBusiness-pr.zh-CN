---
title: 适用于 IT 管理员的升级策略
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 本文适用于 IT 管理员，并介绍了实现从 Skype for Business 升级到 Teams 的策略
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb884f26862466dcd70c9efe81e5293d277adbde
ms.sourcegitcommit: b0753baa55841a2c6c5dc006dcdd117704af3b42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2021
ms.locfileid: "50401334"
---
# <a name="upgrade-strategies-for-it-administrators"></a><span data-ttu-id="54546-103">适用于 IT 管理员的升级策略</span><span class="sxs-lookup"><span data-stu-id="54546-103">Upgrade strategies for IT administrators</span></span>

<span data-ttu-id="54546-104">![升级旅程的阶段，侧重于部署和实施阶段](media/upgrade-banner-deployment.png "升级旅程的阶段，侧重于部署和实施阶段")</span><span class="sxs-lookup"><span data-stu-id="54546-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="54546-105">本文适用于想要从 Skype for Business 升级到 Teams 的 IT 管理员。</span><span class="sxs-lookup"><span data-stu-id="54546-105">This article is for IT administrators who want to implement their upgrade to Teams from Skype for Business.</span></span>

<span data-ttu-id="54546-106">在实施升级之前，我们建议阅读以下文章，其中介绍了重要的升级概念和共存行为：</span><span class="sxs-lookup"><span data-stu-id="54546-106">Before implementing your upgrade, we recommend the following articles which describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="54546-107">了解 Microsoft Teams 和 Skype for Business 共存和互操作性</span><span class="sxs-lookup"><span data-stu-id="54546-107">Understand Microsoft Teams and Skype for Business coexistence and interoperability</span></span>](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="54546-108">共存模式 - 参考</span><span class="sxs-lookup"><span data-stu-id="54546-108">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="54546-109">Teams 客户端体验和共存模式的一致性</span><span class="sxs-lookup"><span data-stu-id="54546-109">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a><span data-ttu-id="54546-110">升级选项</span><span class="sxs-lookup"><span data-stu-id="54546-110">Upgrade options</span></span>

<span data-ttu-id="54546-111">本部分介绍如何使用下列升级选项之一实现升级：</span><span class="sxs-lookup"><span data-stu-id="54546-111">This section describes how to implement your upgrade by using one of the following upgrade options:</span></span>

- [<span data-ttu-id="54546-112">使用群岛模式升级 (重叠功能) </span><span class="sxs-lookup"><span data-stu-id="54546-112">Overlapping capabilities upgrade (using Islands mode)</span></span>](#overlapping-capabilities-upgrade-using-islands-mode)
- [<span data-ttu-id="54546-113">针对尚未开始使用 Teams 的组织进行选择功能升级</span><span class="sxs-lookup"><span data-stu-id="54546-113">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [<span data-ttu-id="54546-114">针对已在群岛模式下使用 Teams 的组织进行选择功能升级</span><span class="sxs-lookup"><span data-stu-id="54546-114">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

<span data-ttu-id="54546-115">如果你需要有关选项的详细信息，请确保已阅读"选择从 Skype for Business 到[Teams 的升级旅程"。](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="54546-115">If you need more information about the options, make sure you have already read [Choose your upgrade journey from Skype for Business to Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).</span></span>

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a><span data-ttu-id="54546-116">使用群岛模式升级 (重叠功能) </span><span class="sxs-lookup"><span data-stu-id="54546-116">Overlapping capabilities upgrade (using Islands mode)</span></span>

<span data-ttu-id="54546-117">对于重叠功能升级选项：</span><span class="sxs-lookup"><span data-stu-id="54546-117">For the overlapping capabilities upgrade option:</span></span>

- <span data-ttu-id="54546-118">如果可以针对整个组织执行快速升级，请考虑使用此选项。</span><span class="sxs-lookup"><span data-stu-id="54546-118">Consider this option if you can do a fast upgrade for your overall organization.</span></span>  <span data-ttu-id="54546-119">由于最终用户在运行这两个客户端时存在混淆的潜在风险，因此最好可以最大程度地缩短用户必须运行这两个客户端的时间段。</span><span class="sxs-lookup"><span data-stu-id="54546-119">Since there is potential risk of confusion for end users with running both clients, it’s best if you can minimize the time period during which users must run both clients.</span></span> <span data-ttu-id="54546-120">应确保用户知道要运行这两个客户端。</span><span class="sxs-lookup"><span data-stu-id="54546-120">You should ensure your users know to run both clients.</span></span>

- <span data-ttu-id="54546-121">此选项是开箱即用模型，除了分配 Microsoft 365 或 Office 365 许可证外，不需要管理员操作来开始使用 Teams。</span><span class="sxs-lookup"><span data-stu-id="54546-121">This option is the out-of-the box model, and doesn’t require administrator action to get started with Teams except to assign the Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="54546-122">如果你的用户已经拥有 Skype for Business Online，则你可能已在此模型中。</span><span class="sxs-lookup"><span data-stu-id="54546-122">If your users already have Skype for Business Online, you may already be in this model.</span></span>

- <span data-ttu-id="54546-123">退出重叠功能模式并迁移到 TeamsOnly 可能很有难度。</span><span class="sxs-lookup"><span data-stu-id="54546-123">It can be challenging getting out of overlapping capabilities mode and moving to TeamsOnly.</span></span> <span data-ttu-id="54546-124">由于升级后的用户仅通过 Teams 进行通信，因此组织中与该用户通信的其他任何用户都必须使用 Teams。</span><span class="sxs-lookup"><span data-stu-id="54546-124">Because upgraded users only communicate via Teams, any other user in the organization communicating with that user must be using Teams.</span></span>  <span data-ttu-id="54546-125">如果用户尚未开始使用 Teams，则他们可能会丢失消息。</span><span class="sxs-lookup"><span data-stu-id="54546-125">If you have users that have not started using Teams, they will be exposed to missing messages.</span></span> <span data-ttu-id="54546-126">此外，他们也不会在 Skype for Business 中在线看到 TeamsOnly 用户。</span><span class="sxs-lookup"><span data-stu-id="54546-126">Furthermore, they won’t see the TeamsOnly users online in Skype for Business.</span></span> <span data-ttu-id="54546-127">某些组织选择使用租户全局策略进行租户级升级以避免这种情况，但是，这需要提前规划，并等待所有用户准备好升级。</span><span class="sxs-lookup"><span data-stu-id="54546-127">Some organizations choose to do a tenant-wide upgrade using the Tenant global policy to avoid this, however that requires upfront planning as well as waiting until all users are ready to be upgraded.</span></span>


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a><span data-ttu-id="54546-128">针对尚未开始使用 Teams 的组织进行选择功能升级</span><span class="sxs-lookup"><span data-stu-id="54546-128">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>

<span data-ttu-id="54546-129">如果你的组织在 Teams 中没有任何活动用户，第一步是将 TeamsUpgradePolicy 的默认租户范围策略设置为其中一种 Skype for Business 模式，例如 SfbWithTeamsCollab。</span><span class="sxs-lookup"><span data-stu-id="54546-129">If your organization does not yet have any active users in Teams, the first step is to set the default tenant-wide policy for TeamsUpgradePolicy to one of the Skype for Business modes, for example, SfbWithTeamsCollab.</span></span>  <span data-ttu-id="54546-130">尚未开始使用 Teams 的用户不会注意到任何行为差异。</span><span class="sxs-lookup"><span data-stu-id="54546-130">Users who have not yet started using Teams won’t notice any difference in behavior.</span></span> <span data-ttu-id="54546-131">但是，在租户级别设置此策略可以开始将用户升级到 TeamsOnly 模式，并确保升级后的用户仍可以与非升级的用户通信。</span><span class="sxs-lookup"><span data-stu-id="54546-131">However, setting this policy at the tenant level makes it possible to start upgrading users to TeamsOnly mode, and ensures that the upgraded users can still communicate with non-upgraded users.</span></span>  <span data-ttu-id="54546-132">确定试点用户后，可以将其升级到 TeamsOnly。</span><span class="sxs-lookup"><span data-stu-id="54546-132">Once you have identified your pilot users you can upgrade them to TeamsOnly.</span></span>  <span data-ttu-id="54546-133">如果它们位于本地，请使用 Move-CsUser。</span><span class="sxs-lookup"><span data-stu-id="54546-133">If they are on-premises, use Move-CsUser.</span></span> <span data-ttu-id="54546-134">如果他们在线，只需使用 Grant-CsTeamsUpgradePolicy 为其分配 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="54546-134">If they are online, simply assign them TeamsOnly mode by using Grant-CsTeamsUpgradePolicy.</span></span> <span data-ttu-id="54546-135">默认情况下，这些用户安排的任何 Skype for Business 会议都将迁移到 Teams。</span><span class="sxs-lookup"><span data-stu-id="54546-135">By default, any Skype for Business meetings scheduled by these users will be migrated to Teams.</span></span>

<span data-ttu-id="54546-136">下面是关键命令：</span><span class="sxs-lookup"><span data-stu-id="54546-136">Following are the key commands:</span></span>

1. <span data-ttu-id="54546-137">将租户范围的默认值设置为 SfbWithTeamsCollab 模式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="54546-137">Set the tenant-wide default to mode SfbWithTeamsCollab as follows:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. <span data-ttu-id="54546-138">将试点用户升级到 TeamsOnly，如下所示：</span><span class="sxs-lookup"><span data-stu-id="54546-138">Upgrade the pilot users to TeamsOnly as follows:</span></span>

   - <span data-ttu-id="54546-139">对于联机用户：</span><span class="sxs-lookup"><span data-stu-id="54546-139">For a user who is online:</span></span>

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - <span data-ttu-id="54546-140">对于本地用户：</span><span class="sxs-lookup"><span data-stu-id="54546-140">For a user who is on-premises:</span></span>

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

<span data-ttu-id="54546-141">注释</span><span class="sxs-lookup"><span data-stu-id="54546-141">Notes</span></span>
 
- <span data-ttu-id="54546-142">可以设置为 SfbWithTeamsCollabsAndMeetings，而不是将租户范围策略设置为 SfbWithTeamsCollabAndMeetings。</span><span class="sxs-lookup"><span data-stu-id="54546-142">Instead of setting the tenant-wide policy to SfbWithTeamsCollab, you could set it to SfbWithTeamsCollabAndMeetings.</span></span> <span data-ttu-id="54546-143">这会导致所有用户在 Teams 中安排所有新会议。</span><span class="sxs-lookup"><span data-stu-id="54546-143">This causes all users to schedule all new meetings in Teams.</span></span>
- <span data-ttu-id="54546-144">`Move-CsUser` 是本地工具中的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="54546-144">`Move-CsUser` is a cmdlet in the on-premises tools.</span></span> <span data-ttu-id="54546-145">此 `MoveToTeams` 开关需要具有 CU8 或更高版本的 Skype for Business Server 2019 或 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="54546-145">The `MoveToTeams` switch requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span> <span data-ttu-id="54546-146">如果你使用的是早期版本，你可以先将用户移动到 Skype for Business Online，然后向该用户授予 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="54546-146">If you are using a prior version, you can first move the user to Skype for Business Online, and then grant TeamsOnly mode to that user.</span></span>
- <span data-ttu-id="54546-147">默认情况下，升级到 TeamsOnly 模式或分配 SfbWithTeamsCollabAndMeetings 模式时，Skype for Business 会议将迁移到 Teams。</span><span class="sxs-lookup"><span data-stu-id="54546-147">By default, Skype for Business meetings are migrated to Teams when upgrading to TeamsOnly mode or when assigning SfbWithTeamsCollabAndMeetings mode.</span></span>  

<span data-ttu-id="54546-148">下图显示了未事先使用 Teams 的组织选择功能升级的概念阶段。</span><span class="sxs-lookup"><span data-stu-id="54546-148">The diagram below shows the conceptual phases of select capabilities upgrade for an organization with no prior usage of Teams.</span></span> <span data-ttu-id="54546-149">条形图的高度表示用户数。</span><span class="sxs-lookup"><span data-stu-id="54546-149">The height of the bars represents number of users.</span></span> <span data-ttu-id="54546-150">在升级的任何阶段，所有用户都可以相互通信。</span><span class="sxs-lookup"><span data-stu-id="54546-150">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="54546-151">Skype for Business 用户使用互操作与 TeamsOnly 用户通信，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="54546-151">Skype for Business users communicate with TeamsOnly users using Interop, and vice versa.</span></span> <span data-ttu-id="54546-152">在群岛模式下的用户必须确保运行这两个客户端。</span><span class="sxs-lookup"><span data-stu-id="54546-152">Users in Islands mode must be sure to run both clients.</span></span>

![显示未事先使用 Teams 的选定功能升级的示意图](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a><span data-ttu-id="54546-154">针对已在群岛模式下使用 Teams 的组织进行选择功能升级</span><span class="sxs-lookup"><span data-stu-id="54546-154">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>

<span data-ttu-id="54546-155">如果贵组织中某些用户正在以群岛模式主动使用 Teams，则你可能不希望删除现有用户的功能。</span><span class="sxs-lookup"><span data-stu-id="54546-155">If some users in your organization are actively using Teams in Islands mode, you probably do not want to remove functionality from existing users.</span></span> <span data-ttu-id="54546-156">因此，在更改租户范围策略之前，需要执行额外的步骤。</span><span class="sxs-lookup"><span data-stu-id="54546-156">Therefore, an extra step is required before changing the tenant-wide policy.</span></span> <span data-ttu-id="54546-157">解决方法是在将租户范围策略设置为 SfbWithTeamsCollab 之前，将这些现有活动 Teams 用户"隔离"到群岛模式。</span><span class="sxs-lookup"><span data-stu-id="54546-157">The solution is to “grandfather” these existing active Teams users into Islands mode, before setting the tenant-wide policy to SfbWithTeamsCollab.</span></span>  <span data-ttu-id="54546-158">完成上述操作后，可以继续部署，但是，你将有两组用户迁移到 TeamsOnly：在 Teams 中处于活动状态的用户将位于群岛模式，其余用户将位于 SfbWithTeamsCollab 模式。</span><span class="sxs-lookup"><span data-stu-id="54546-158">Once you’ve done that, you can proceed with deployment as above, however, you’ll have two groups of users who are moving to TeamsOnly:  the users who were active in Teams will be in Islands mode, and the remaining users will be in SfbWithTeamsCollab mode.</span></span> <span data-ttu-id="54546-159">可以渐进式地将这些用户移动到 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="54546-159">You can progressively move these users to TeamsOnly mode.</span></span>

1. <span data-ttu-id="54546-160">查找在 Teams 中处于活动状态的用户，如下所示：</span><span class="sxs-lookup"><span data-stu-id="54546-160">Find users who are active in Teams as follows:</span></span>

   1. <span data-ttu-id="54546-161">在 Microsoft 365 管理中心的左侧导航栏中，转到"报表"，然后转到"使用情况"。</span><span class="sxs-lookup"><span data-stu-id="54546-161">From the Microsoft 365 admin center, in the left-hand navigation, go to Reports, and then Usage.</span></span> 
   2. <span data-ttu-id="54546-162">在"选择报表"下拉列表中，选择 Microsoft Teams，然后选择"用户活动"。</span><span class="sxs-lookup"><span data-stu-id="54546-162">In the “Select a report” dropdown, choose Microsoft Teams, and then User Activity.</span></span> <span data-ttu-id="54546-163">这会提供已在 Teams 中处于活动状态的用户的可导出表。</span><span class="sxs-lookup"><span data-stu-id="54546-163">This will provide an exportable table of users who have been active in Teams.</span></span> 
   3. <span data-ttu-id="54546-164">单击"导出"，打开 Excel，然后筛选以仅显示 Teams 中处于活动状态的用户。</span><span class="sxs-lookup"><span data-stu-id="54546-164">Click Export, open Excel, and filter to show only the users who are active in Teams.</span></span>

2. <span data-ttu-id="54546-165">对于在步骤 1 中发现的每个活动 Teams 用户，在远程 PowerShell 中为其分配"群岛"模式。</span><span class="sxs-lookup"><span data-stu-id="54546-165">For each active Teams user found in step 1, assign them Islands mode in remote PowerShell.</span></span> <span data-ttu-id="54546-166">这样，你可转到下一步，并确保不会更改用户体验。</span><span class="sxs-lookup"><span data-stu-id="54546-166">This allows you to go to the next step, and ensures you don’t change the user experience.</span></span>  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. <span data-ttu-id="54546-167">将租户范围策略设置为 SfbWithTeamsCollab：</span><span class="sxs-lookup"><span data-stu-id="54546-167">Set the tenant-wide policy to SfbWithTeamsCollab:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. <span data-ttu-id="54546-168">将所选用户升级到 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="54546-168">Upgrade selected users to TeamsOnly mode.</span></span> <span data-ttu-id="54546-169">可以选择在群岛模式或 SfbWithTeamsCollab 模式下升级用户，尽管你可能希望首先优先升级在群岛模式下的用户，以尽量减少用户进入群岛模式时可能出现的混淆。</span><span class="sxs-lookup"><span data-stu-id="54546-169">You can choose to upgrade either users in Islands mode or SfbWithTeamsCollab mode, although you might want to prioritize upgrading the users in Islands mode first to minimize the potential for confusion that can arise when users are in Islands mode.</span></span>   

   <span data-ttu-id="54546-170">对于在 Skype for Business Online 中家庭的用户：</span><span class="sxs-lookup"><span data-stu-id="54546-170">For users homed in Skype for Business Online:</span></span>  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   <span data-ttu-id="54546-171">对于本地 Skype for Business Server 中的用户：</span><span class="sxs-lookup"><span data-stu-id="54546-171">For users homed in Skype for Business Server on-premises:</span></span>  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

<span data-ttu-id="54546-172">下图显示了选择功能转换的概念阶段，其中一开始有活动的群岛用户。</span><span class="sxs-lookup"><span data-stu-id="54546-172">The diagram below shows the conceptual phases of a select capabilities transition in which there are active Islands users at the start.</span></span> <span data-ttu-id="54546-173">条形图的高度表示用户数。</span><span class="sxs-lookup"><span data-stu-id="54546-173">The height of the bars represents the number of users.</span></span> <span data-ttu-id="54546-174">在升级的任何阶段，所有用户都可以相互通信。</span><span class="sxs-lookup"><span data-stu-id="54546-174">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="54546-175">Skype for Business 用户使用互操作与 TeamsOnly 用户通信，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="54546-175">Skype for Business users communicate with TeamsOnly users using interop, and vice versa.</span></span> 


![显示在群岛模式下使用活动用户进行选择功能升级的示意图](media/teams-upgrade-2.png)

   



## <a name="related-links"></a><span data-ttu-id="54546-177">相关链接</span><span class="sxs-lookup"><span data-stu-id="54546-177">Related links</span></span>

[<span data-ttu-id="54546-178">面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导</span><span class="sxs-lookup"><span data-stu-id="54546-178">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="54546-179">在 Skype for Business Server 与 Microsoft 365 或 Office 365 之间配置混合连接</span><span class="sxs-lookup"><span data-stu-id="54546-179">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="54546-180">在本地和云之间移动用户</span><span class="sxs-lookup"><span data-stu-id="54546-180">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="54546-181">设置共存和升级设置</span><span class="sxs-lookup"><span data-stu-id="54546-181">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="54546-182">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="54546-182">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="54546-183">使用会议迁移服务 (MMS) </span><span class="sxs-lookup"><span data-stu-id="54546-183">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

