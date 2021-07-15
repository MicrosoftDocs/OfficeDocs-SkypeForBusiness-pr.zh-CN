---
title: 适用于 IT 管理员的升级策略
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 本文适用于 IT 管理员，并介绍了实现从本地到 Skype for Business Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f11d14bc7bf302a864afe3062ef8f2bb8eccd7da
ms.sourcegitcommit: e19fdedca6573110d08c7d114e05b84779e36b58
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53437639"
---
# <a name="upgrade-strategies-for-it-administrators"></a><span data-ttu-id="0d892-103">适用于 IT 管理员的升级策略</span><span class="sxs-lookup"><span data-stu-id="0d892-103">Upgrade strategies for IT administrators</span></span>

<span data-ttu-id="0d892-104">![升级旅程的阶段，着重强调部署和实施阶段](media/upgrade-banner-deployment.png "升级旅程的阶段，着重强调部署和实施阶段")</span><span class="sxs-lookup"><span data-stu-id="0d892-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="0d892-105">本文适用于想要从 Teams 升级到 Skype for Business 的 IT 管理员。</span><span class="sxs-lookup"><span data-stu-id="0d892-105">This article is for IT administrators who want to implement their upgrade to Teams from Skype for Business.</span></span>

<span data-ttu-id="0d892-106">在实施升级之前，我们建议阅读以下文章，其中介绍了重要的升级概念和共存行为：</span><span class="sxs-lookup"><span data-stu-id="0d892-106">Before implementing your upgrade, we recommend the following articles which describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="0d892-107">了解 Microsoft Teams 和 Skype for Business 的共存和互操作性</span><span class="sxs-lookup"><span data-stu-id="0d892-107">Understand Microsoft Teams and Skype for Business coexistence and interoperability</span></span>](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="0d892-108">共存模式 - 参考</span><span class="sxs-lookup"><span data-stu-id="0d892-108">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="0d892-109">Teams 客户端体验和共存模式的一致性</span><span class="sxs-lookup"><span data-stu-id="0d892-109">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a><span data-ttu-id="0d892-110">升级选项</span><span class="sxs-lookup"><span data-stu-id="0d892-110">Upgrade options</span></span>

<span data-ttu-id="0d892-111">本部分介绍如何使用下列升级选项之一实现升级：</span><span class="sxs-lookup"><span data-stu-id="0d892-111">This section describes how to implement your upgrade by using one of the following upgrade options:</span></span>

- [<span data-ttu-id="0d892-112">使用群岛模式 (重叠功能升级) </span><span class="sxs-lookup"><span data-stu-id="0d892-112">Overlapping capabilities upgrade (using Islands mode)</span></span>](#overlapping-capabilities-upgrade-using-islands-mode)
- [<span data-ttu-id="0d892-113">为尚未开始使用 Teams 的组织选择功能升级</span><span class="sxs-lookup"><span data-stu-id="0d892-113">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [<span data-ttu-id="0d892-114">为已在群岛模式下使用Teams选择功能升级</span><span class="sxs-lookup"><span data-stu-id="0d892-114">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

<span data-ttu-id="0d892-115">如果需要有关选项的详细信息，请确保已阅读选择从 Skype for Business 到[Teams 的升级Teams。](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="0d892-115">If you need more information about the options, make sure you have already read [Choose your upgrade journey from Skype for Business to Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).</span></span>

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a><span data-ttu-id="0d892-116">使用群岛模式 (重叠功能升级) </span><span class="sxs-lookup"><span data-stu-id="0d892-116">Overlapping capabilities upgrade (using Islands mode)</span></span>

<span data-ttu-id="0d892-117">对于重叠功能升级选项：</span><span class="sxs-lookup"><span data-stu-id="0d892-117">For the overlapping capabilities upgrade option:</span></span>

- <span data-ttu-id="0d892-118">如果可以针对整个组织执行快速升级，请考虑使用此选项。</span><span class="sxs-lookup"><span data-stu-id="0d892-118">Consider this option if you can do a fast upgrade for your overall organization.</span></span>  <span data-ttu-id="0d892-119">由于运行这两个客户端的最终用户存在混淆的潜在风险，因此最好尽量减少用户必须运行这两个客户端的时间段。</span><span class="sxs-lookup"><span data-stu-id="0d892-119">Since there is potential risk of confusion for end users with running both clients, it’s best if you can minimize the time period during which users must run both clients.</span></span> <span data-ttu-id="0d892-120">应确保用户知道运行这两个客户端。</span><span class="sxs-lookup"><span data-stu-id="0d892-120">You should ensure your users know to run both clients.</span></span>

- <span data-ttu-id="0d892-121">此选项是开箱即用模型，不需要管理员操作，Teams许可证或Microsoft 365 Office 365许可证。</span><span class="sxs-lookup"><span data-stu-id="0d892-121">This option is the out-of-the box model, and doesn’t require administrator action to get started with Teams except to assign the Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="0d892-122">如果你的用户已拥有 Skype for Business Online，则你可能已在此模型中。</span><span class="sxs-lookup"><span data-stu-id="0d892-122">If your users already have Skype for Business Online, you may already be in this model.</span></span>

- <span data-ttu-id="0d892-123">从重叠的功能模式迁移到 TeamsOnly 可能很有难度。</span><span class="sxs-lookup"><span data-stu-id="0d892-123">It can be challenging getting out of overlapping capabilities mode and moving to TeamsOnly.</span></span> <span data-ttu-id="0d892-124">由于升级后的用户仅Teams通信，因此组织中与该用户通信的其他任何用户都必须使用Teams。</span><span class="sxs-lookup"><span data-stu-id="0d892-124">Because upgraded users only communicate via Teams, any other user in the organization communicating with that user must be using Teams.</span></span>  <span data-ttu-id="0d892-125">如果用户尚未开始使用 Teams，则他们可能会丢失消息。</span><span class="sxs-lookup"><span data-stu-id="0d892-125">If you have users that have not started using Teams, they will be exposed to missing messages.</span></span> <span data-ttu-id="0d892-126">此外，他们将不会看到 TeamsOnly 用户在 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="0d892-126">Furthermore, they won’t see the TeamsOnly users online in Skype for Business.</span></span> <span data-ttu-id="0d892-127">某些组织选择使用租户全局策略进行租户级升级以避免这种情况，但是，这需要提前规划，并等待所有用户准备好升级。</span><span class="sxs-lookup"><span data-stu-id="0d892-127">Some organizations choose to do a tenant-wide upgrade using the Tenant global policy to avoid this, however that requires upfront planning as well as waiting until all users are ready to be upgraded.</span></span>


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a><span data-ttu-id="0d892-128">为尚未开始使用 Teams 的组织选择功能升级</span><span class="sxs-lookup"><span data-stu-id="0d892-128">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>

<span data-ttu-id="0d892-129">如果组织在 Teams 中没有任何活动用户，第一步是将 TeamsUpgradePolicy 的默认租户范围策略设置为 Skype for Business 模式之一，例如 SfbWithTeamsCollab。</span><span class="sxs-lookup"><span data-stu-id="0d892-129">If your organization does not yet have any active users in Teams, the first step is to set the default tenant-wide policy for TeamsUpgradePolicy to one of the Skype for Business modes, for example, SfbWithTeamsCollab.</span></span>  <span data-ttu-id="0d892-130">尚未开始使用此Teams不会注意到任何行为差异。</span><span class="sxs-lookup"><span data-stu-id="0d892-130">Users who have not yet started using Teams won’t notice any difference in behavior.</span></span> <span data-ttu-id="0d892-131">但是，在租户级别设置此策略可以开始将用户升级到 TeamsOnly 模式，并确保升级的用户仍可以与非升级的用户通信。</span><span class="sxs-lookup"><span data-stu-id="0d892-131">However, setting this policy at the tenant level makes it possible to start upgrading users to TeamsOnly mode, and ensures that the upgraded users can still communicate with non-upgraded users.</span></span>  <span data-ttu-id="0d892-132">确定试点用户后，可将其升级到 TeamsOnly。</span><span class="sxs-lookup"><span data-stu-id="0d892-132">Once you have identified your pilot users you can upgrade them to TeamsOnly.</span></span>  <span data-ttu-id="0d892-133">如果它们位于本地，请使用 Move-CsUser。</span><span class="sxs-lookup"><span data-stu-id="0d892-133">If they are on-premises, use Move-CsUser.</span></span> <span data-ttu-id="0d892-134">如果他们在线，只需使用 Grant-CsTeamsUpgradePolicy 为其分配 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="0d892-134">If they are online, simply assign them TeamsOnly mode by using Grant-CsTeamsUpgradePolicy.</span></span> <span data-ttu-id="0d892-135">默认情况下，这些Skype for Business安排的任何会议都将迁移到Teams。</span><span class="sxs-lookup"><span data-stu-id="0d892-135">By default, any Skype for Business meetings scheduled by these users will be migrated to Teams.</span></span>

<span data-ttu-id="0d892-136">下面是关键命令：</span><span class="sxs-lookup"><span data-stu-id="0d892-136">Following are the key commands:</span></span>

1. <span data-ttu-id="0d892-137">将租户范围的默认值设置为 SfbWithTeamsCollab 模式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0d892-137">Set the tenant-wide default to mode SfbWithTeamsCollab as follows:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. <span data-ttu-id="0d892-138">将试点用户升级到 TeamsOnly，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0d892-138">Upgrade the pilot users to TeamsOnly as follows:</span></span>

   - <span data-ttu-id="0d892-139">对于联机用户：</span><span class="sxs-lookup"><span data-stu-id="0d892-139">For a user who is online:</span></span>

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - <span data-ttu-id="0d892-140">对于本地用户：</span><span class="sxs-lookup"><span data-stu-id="0d892-140">For a user who is on-premises:</span></span>

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

<span data-ttu-id="0d892-141">注释</span><span class="sxs-lookup"><span data-stu-id="0d892-141">Notes</span></span>
 
- <span data-ttu-id="0d892-142">可以设置为 SfbWithTeamsCollabAndMeetings，而不是将租户范围策略设置为 SfbWithTeamsCollabAndMeetings。</span><span class="sxs-lookup"><span data-stu-id="0d892-142">Instead of setting the tenant-wide policy to SfbWithTeamsCollab, you could set it to SfbWithTeamsCollabAndMeetings.</span></span> <span data-ttu-id="0d892-143">这会导致所有用户在会议中安排所有新Teams。</span><span class="sxs-lookup"><span data-stu-id="0d892-143">This causes all users to schedule all new meetings in Teams.</span></span>
- <span data-ttu-id="0d892-144">默认情况下，Skype for Business TeamsOnly 模式或分配 SfbWithTeamsCollabAndMeetings 模式时，Teams会议迁移到其他会议。</span><span class="sxs-lookup"><span data-stu-id="0d892-144">By default, Skype for Business meetings are migrated to Teams when upgrading to TeamsOnly mode or when assigning SfbWithTeamsCollabAndMeetings mode.</span></span>  

> [!NOTE]
> <span data-ttu-id="0d892-145">为准备即将停用 Skype for Business Online，Microsoft 简化了组织转移到 Teams。</span><span class="sxs-lookup"><span data-stu-id="0d892-145">In preparation for the upcoming retirement of Skype for Business Online, Microsoft has simplified how organizations move to Teams.</span></span> <span data-ttu-id="0d892-146">不再需要指定 中的开关，直接将用户从本地 `-MoveToTeams` `Move-CsUser` 移动到 TeamsOnly。</span><span class="sxs-lookup"><span data-stu-id="0d892-146">It is no longer required to specify the `-MoveToTeams` switch in `Move-CsUser` to move users directly from on-premises directly to TeamsOnly.</span></span> <span data-ttu-id="0d892-147">以前，如果未指定此开关，则用户从本地Skype for Business Server到 Skype for Business Online，其模式保持不变。</span><span class="sxs-lookup"><span data-stu-id="0d892-147">Previously, if this switch was not specified, users transitioned from being homed in Skype for Business Server on-premises to Skype for Business Online, and their mode remained unchanged.</span></span> <span data-ttu-id="0d892-148">现在，使用 将用户从本地移动到云时，系统会自动为用户分配 TeamsOnly 模式，并且其会议从本地自动转换为 Teams 会议，就像 ， 而不考虑是否实际指定了开关一样。 `Move-CsUser` `-MoveToTeams switch had been specified`</span><span class="sxs-lookup"><span data-stu-id="0d892-148">Now when moving a user from on-premises to the cloud with `Move-CsUser`, users are automatically assigned TeamsOnly mode and their meetings from on-premises are automtically converted to Teams meetings, just as if the `-MoveToTeams switch had been specified`, regardless of whether the switch is actually specified.</span></span> <span data-ttu-id="0d892-149">此行为适用于从未支持 Skype For Business Server 和 Lync Server 2013 (的所有 `-MoveToTeams` 版本) 。</span><span class="sxs-lookup"><span data-stu-id="0d892-149">This behavior is available on all versions of Skype For Business Server and Lync Server 2013 (which never had support for `-MoveToTeams`).</span></span>

<span data-ttu-id="0d892-150">下图显示了组织中未事先使用特定功能升级功能的概念Teams。</span><span class="sxs-lookup"><span data-stu-id="0d892-150">The diagram below shows the conceptual phases of select capabilities upgrade for an organization with no prior usage of Teams.</span></span> <span data-ttu-id="0d892-151">条形图的高度表示用户数。</span><span class="sxs-lookup"><span data-stu-id="0d892-151">The height of the bars represents number of users.</span></span> <span data-ttu-id="0d892-152">在升级的任何阶段，所有用户都可以相互通信。</span><span class="sxs-lookup"><span data-stu-id="0d892-152">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="0d892-153">Skype for Business使用互操作与 TeamsOnly 用户通信，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="0d892-153">Skype for Business users communicate with TeamsOnly users using Interop, and vice versa.</span></span> <span data-ttu-id="0d892-154">位于群岛模式的用户必须确保运行这两个客户端。</span><span class="sxs-lookup"><span data-stu-id="0d892-154">Users in Islands mode must be sure to run both clients.</span></span>

![显示选择功能升级的示意图，其中未事先使用Teams](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a><span data-ttu-id="0d892-156">为已在群岛模式下使用Teams选择功能升级</span><span class="sxs-lookup"><span data-stu-id="0d892-156">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>

<span data-ttu-id="0d892-157">如果组织中的某些用户正在以Teams模式主动使用云，则你可能不希望删除现有用户的功能。</span><span class="sxs-lookup"><span data-stu-id="0d892-157">If some users in your organization are actively using Teams in Islands mode, you probably do not want to remove functionality from existing users.</span></span> <span data-ttu-id="0d892-158">因此，在更改租户范围策略之前，需要执行额外的步骤。</span><span class="sxs-lookup"><span data-stu-id="0d892-158">Therefore, an extra step is required before changing the tenant-wide policy.</span></span> <span data-ttu-id="0d892-159">解决方法是在将租户范围策略设置为 SfbWithTeamsCollab 之前，Teams现有活动用户"加入群岛模式"。</span><span class="sxs-lookup"><span data-stu-id="0d892-159">The solution is to “grandfather” these existing active Teams users into Islands mode, before setting the tenant-wide policy to SfbWithTeamsCollab.</span></span>  <span data-ttu-id="0d892-160">完成上述部署后，可以继续部署，但是，你将有两组用户迁移到 TeamsOnly：在 Teams 中处于活动状态的用户将位于群岛模式，其余用户将位于 SfbWithTeamsCollab 模式下。</span><span class="sxs-lookup"><span data-stu-id="0d892-160">Once you’ve done that, you can proceed with deployment as above, however, you’ll have two groups of users who are moving to TeamsOnly:  the users who were active in Teams will be in Islands mode, and the remaining users will be in SfbWithTeamsCollab mode.</span></span> <span data-ttu-id="0d892-161">可以逐步将这些用户移动到 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="0d892-161">You can progressively move these users to TeamsOnly mode.</span></span>

1. <span data-ttu-id="0d892-162">按如下所示查找Teams活动的用户：</span><span class="sxs-lookup"><span data-stu-id="0d892-162">Find users who are active in Teams as follows:</span></span>

   1. <span data-ttu-id="0d892-163">在Microsoft 365 管理中心导航栏中，转到"报表"，然后转到"使用情况"。</span><span class="sxs-lookup"><span data-stu-id="0d892-163">From the Microsoft 365 admin center, in the left-hand navigation, go to Reports, and then Usage.</span></span> 
   2. <span data-ttu-id="0d892-164">在"选择报表"下拉列表中，选择"Microsoft Teams"，然后选择"用户活动"。</span><span class="sxs-lookup"><span data-stu-id="0d892-164">In the “Select a report” dropdown, choose Microsoft Teams, and then User Activity.</span></span> <span data-ttu-id="0d892-165">这会提供已处于活动状态的用户的可导出表，Teams。</span><span class="sxs-lookup"><span data-stu-id="0d892-165">This will provide an exportable table of users who have been active in Teams.</span></span> 
   3. <span data-ttu-id="0d892-166">单击"导出"，Excel，然后进行筛选，以便只显示当前在 Teams。</span><span class="sxs-lookup"><span data-stu-id="0d892-166">Click Export, open Excel, and filter to show only the users who are active in Teams.</span></span>

2. <span data-ttu-id="0d892-167">对于在Teams 1 找到的每个活动用户，在远程 PowerShell 中为其分配"群岛"模式。</span><span class="sxs-lookup"><span data-stu-id="0d892-167">For each active Teams user found in step 1, assign them Islands mode in remote PowerShell.</span></span> <span data-ttu-id="0d892-168">这样，你可以转到下一步，并确保不会更改用户体验。</span><span class="sxs-lookup"><span data-stu-id="0d892-168">This allows you to go to the next step, and ensures you don’t change the user experience.</span></span>  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. <span data-ttu-id="0d892-169">将租户范围策略设置为 SfbWithTeamsCollab：</span><span class="sxs-lookup"><span data-stu-id="0d892-169">Set the tenant-wide policy to SfbWithTeamsCollab:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. <span data-ttu-id="0d892-170">将所选用户升级到 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="0d892-170">Upgrade selected users to TeamsOnly mode.</span></span> <span data-ttu-id="0d892-171">可以选择在群岛模式或 SfbWithTeamsCollab 模式下升级用户，尽管你可能希望首先优先升级在群岛模式下的用户，以尽量减少在用户进入群岛模式时可能出现的混淆。</span><span class="sxs-lookup"><span data-stu-id="0d892-171">You can choose to upgrade either users in Islands mode or SfbWithTeamsCollab mode, although you might want to prioritize upgrading the users in Islands mode first to minimize the potential for confusion that can arise when users are in Islands mode.</span></span>   

   <span data-ttu-id="0d892-172">对于在 Skype for Business Online 中的用户：</span><span class="sxs-lookup"><span data-stu-id="0d892-172">For users homed in Skype for Business Online:</span></span>  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   <span data-ttu-id="0d892-173">对于本地Skype for Business Server用户：</span><span class="sxs-lookup"><span data-stu-id="0d892-173">For users homed in Skype for Business Server on-premises:</span></span>  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

<span data-ttu-id="0d892-174">下图显示了一些选择功能过渡的概念阶段，其中一开始有活跃的群岛用户。</span><span class="sxs-lookup"><span data-stu-id="0d892-174">The diagram below shows the conceptual phases of a select capabilities transition in which there are active Islands users at the start.</span></span> <span data-ttu-id="0d892-175">条形图的高度表示用户数。</span><span class="sxs-lookup"><span data-stu-id="0d892-175">The height of the bars represents the number of users.</span></span> <span data-ttu-id="0d892-176">在升级的任何阶段，所有用户都可以相互通信。</span><span class="sxs-lookup"><span data-stu-id="0d892-176">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="0d892-177">Skype for Business使用互操作与 TeamsOnly 用户通信，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="0d892-177">Skype for Business users communicate with TeamsOnly users using interop, and vice versa.</span></span> 


![显示以岛屿模式活动用户进行选择功能升级的示意图](media/teams-upgrade-2.png)

   



## <a name="related-links"></a><span data-ttu-id="0d892-179">相关链接</span><span class="sxs-lookup"><span data-stu-id="0d892-179">Related links</span></span>

[<span data-ttu-id="0d892-180">面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导</span><span class="sxs-lookup"><span data-stu-id="0d892-180">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="0d892-181">配置 Skype for Business Server 与 Microsoft 365 或 Office 365 之间的混合连接</span><span class="sxs-lookup"><span data-stu-id="0d892-181">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="0d892-182">在本地和云之间移动用户</span><span class="sxs-lookup"><span data-stu-id="0d892-182">Move users between on-premises and cloud</span></span>](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="0d892-183">设置共存和升级设置</span><span class="sxs-lookup"><span data-stu-id="0d892-183">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="0d892-184">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="0d892-184">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="0d892-185">使用会议迁移服务 (MMS)</span><span class="sxs-lookup"><span data-stu-id="0d892-185">Using the Meeting Migration Service (MMS)</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
