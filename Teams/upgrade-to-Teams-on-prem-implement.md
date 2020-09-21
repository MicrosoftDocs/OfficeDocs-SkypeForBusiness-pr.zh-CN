---
title: 从 Skype for Business 内部部署升级到团队-Microsoft 团队
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 从 Skype for Business 升级到 Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8239d1fdbda10a61cd0846a0d56b1f1ffa62f597
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955899"
---
# <a name="implement-your-upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="ce63d-103">实现从 Skype for Business 升级到 &mdash; IT 管理员的团队</span><span class="sxs-lookup"><span data-stu-id="ce63d-103">Implement your upgrade from Skype for Business to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="ce63d-104">本文介绍如何实现升级。</span><span class="sxs-lookup"><span data-stu-id="ce63d-104">This article describes how to implement your upgrade.</span></span> <span data-ttu-id="ce63d-105">本文是介绍 IT 管理员的升级概念和实现的第五个。</span><span class="sxs-lookup"><span data-stu-id="ce63d-105">This article is the fifth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="ce63d-106">概述</span><span class="sxs-lookup"><span data-stu-id="ce63d-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="ce63d-107">升级方法</span><span class="sxs-lookup"><span data-stu-id="ce63d-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="ce63d-108">用于管理升级的工具</span><span class="sxs-lookup"><span data-stu-id="ce63d-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- [<span data-ttu-id="ce63d-109">具有 Skype for business 内部部署的组织的其他注意事项</span><span class="sxs-lookup"><span data-stu-id="ce63d-109">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- <span data-ttu-id="ce63d-110"> (本文中**实施升级**) </span><span class="sxs-lookup"><span data-stu-id="ce63d-110">**Implement your upgrade** (this article)</span></span>
- [<span data-ttu-id="ce63d-111"> (PSTN) 注意事项的公共交换电话网络</span><span class="sxs-lookup"><span data-stu-id="ce63d-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="ce63d-112">此外，以下文章介绍了重要的升级概念和共存行为：</span><span class="sxs-lookup"><span data-stu-id="ce63d-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="ce63d-113">团队和 Skype for business 的共存</span><span class="sxs-lookup"><span data-stu-id="ce63d-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="ce63d-114">共存模式-参考</span><span class="sxs-lookup"><span data-stu-id="ce63d-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="ce63d-115">Teams 客户端体验和共存模式的一致性</span><span class="sxs-lookup"><span data-stu-id="ce63d-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a><span data-ttu-id="ce63d-116">升级选项</span><span class="sxs-lookup"><span data-stu-id="ce63d-116">Upgrade options</span></span>

<span data-ttu-id="ce63d-117">本部分介绍如何使用以下升级选项之一实现升级：</span><span class="sxs-lookup"><span data-stu-id="ce63d-117">This section describes how to implement your upgrade by using one of the following upgrade options:</span></span>

- [<span data-ttu-id="ce63d-118">使用孤岛模式升级 (重叠功能) </span><span class="sxs-lookup"><span data-stu-id="ce63d-118">Overlapping capabilities upgrade (using Islands mode)</span></span>](#overlapping-capabilities-upgrade-using-islands-mode)
- [<span data-ttu-id="ce63d-119">尚未使用团队开始的组织的 "选择功能" 升级</span><span class="sxs-lookup"><span data-stu-id="ce63d-119">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [<span data-ttu-id="ce63d-120">已在孤岛模式下使用团队的组织的 "选择功能" 升级</span><span class="sxs-lookup"><span data-stu-id="ce63d-120">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

<span data-ttu-id="ce63d-121">如果需要有关这些选项的详细信息，请确保已阅读 [升级方法](upgrade-to-teams-on-prem-upgrade-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="ce63d-121">If you need more information about the options, make sure you have already read [Upgrade methods](upgrade-to-teams-on-prem-upgrade-methods.md).</span></span>

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a><span data-ttu-id="ce63d-122">使用孤岛模式升级 (重叠功能) </span><span class="sxs-lookup"><span data-stu-id="ce63d-122">Overlapping capabilities upgrade (using Islands mode)</span></span>

<span data-ttu-id="ce63d-123">对于重叠功能升级选项：</span><span class="sxs-lookup"><span data-stu-id="ce63d-123">For the overlapping capabilities upgrade option:</span></span>

- <span data-ttu-id="ce63d-124">如果您可以快速升级整个组织，请考虑此选项。</span><span class="sxs-lookup"><span data-stu-id="ce63d-124">Consider this option if you can do a fast upgrade for your overall organization.</span></span>  <span data-ttu-id="ce63d-125">由于对最终用户运行两个客户端有潜在的风险，因此最好最大限度地减少用户必须在其中运行这两个客户端的时间段。</span><span class="sxs-lookup"><span data-stu-id="ce63d-125">Since there is potential risk of confusion for end users with running both clients, it’s best if you can minimize the time period during which users must run both clients.</span></span> <span data-ttu-id="ce63d-126">你应该确保你的用户知道运行这两个客户端。</span><span class="sxs-lookup"><span data-stu-id="ce63d-126">You should ensure your users know to run both clients.</span></span>

- <span data-ttu-id="ce63d-127">此选项是现成模型，不需要管理员操作即可开始使用团队，除非分配 Microsoft 365 或 Office 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="ce63d-127">This option is the out-of-the box model, and doesn’t require administrator action to get started with Teams except to assign the Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="ce63d-128">如果你的用户已有 Skype for Business Online，则你可能已在使用此模型。</span><span class="sxs-lookup"><span data-stu-id="ce63d-128">If your users already have Skype for Business Online, you may already be in this model.</span></span>

- <span data-ttu-id="ce63d-129">在重叠的功能模式和移动到 TeamsOnly 时，可能会有挑战性。</span><span class="sxs-lookup"><span data-stu-id="ce63d-129">It can be challenging getting out of overlapping capabilities mode and moving to TeamsOnly.</span></span> <span data-ttu-id="ce63d-130">由于升级用户仅通过团队进行通信，因此组织中与该用户通信的任何其他用户都必须使用团队。</span><span class="sxs-lookup"><span data-stu-id="ce63d-130">Because upgraded users only communicate via Teams, any other user in the organization communicating with that user must be using Teams.</span></span>  <span data-ttu-id="ce63d-131">如果你有尚未开始使用团队的用户，这些用户将暴露给缺失的消息。</span><span class="sxs-lookup"><span data-stu-id="ce63d-131">If you have users that have not started using Teams, they will be exposed to missing messages.</span></span> <span data-ttu-id="ce63d-132">此外，他们在 Skype for Business 中看不到 TeamsOnly 用户在线。</span><span class="sxs-lookup"><span data-stu-id="ce63d-132">Furthermore, they won’t see the TeamsOnly users online in Skype for Business.</span></span> <span data-ttu-id="ce63d-133">某些组织选择使用租户全局策略执行租户范围内的升级以避免这种情况，但需要前期计划以及等待所有用户都准备好升级。</span><span class="sxs-lookup"><span data-stu-id="ce63d-133">Some organizations choose to do a tenant-wide upgrade using the Tenant global policy to avoid this, however that requires upfront planning as well as waiting until all users are ready to be upgraded.</span></span>


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a><span data-ttu-id="ce63d-134">尚未使用团队开始的组织的 "选择功能" 升级</span><span class="sxs-lookup"><span data-stu-id="ce63d-134">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>

<span data-ttu-id="ce63d-135">如果你的组织还没有团队中的任何活动用户，第一步是将 TeamsUpgradePolicy 的默认租户范围策略设置为 Skype for Business 模式之一，例如 SfbWithTeamsCollab。</span><span class="sxs-lookup"><span data-stu-id="ce63d-135">If your organization does not yet have any active users in Teams, the first step is to set the default tenant-wide policy for TeamsUpgradePolicy to one of the Skype for Business modes, for example, SfbWithTeamsCollab.</span></span>  <span data-ttu-id="ce63d-136">尚未开始使用团队的用户将不会注意到行为的任何差异。</span><span class="sxs-lookup"><span data-stu-id="ce63d-136">Users who have not yet started using Teams won’t notice any difference in behavior.</span></span> <span data-ttu-id="ce63d-137">但是，在租户级别设置此策略将使用户能够开始将用户升级到 TeamsOnly 模式，并确保已升级的用户仍可以与未升级的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="ce63d-137">However, setting this policy at the tenant level makes it possible to start upgrading users to TeamsOnly mode, and ensures that the upgraded users can still communicate with non-upgraded users.</span></span>  <span data-ttu-id="ce63d-138">一旦你确定了你的试点用户，你可以将其升级到 TeamsOnly。</span><span class="sxs-lookup"><span data-stu-id="ce63d-138">Once you have identified your pilot users you can upgrade them to TeamsOnly.</span></span>  <span data-ttu-id="ce63d-139">如果他们在本地，请使用 Move-csuser。</span><span class="sxs-lookup"><span data-stu-id="ce63d-139">If they are on-premises, use Move-CsUser.</span></span> <span data-ttu-id="ce63d-140">如果它们处于联机状态，只需使用 Grant-CsTeamsUpgradePolicy 将其分配 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="ce63d-140">If they are online, simply assign them TeamsOnly mode by using Grant-CsTeamsUpgradePolicy.</span></span> <span data-ttu-id="ce63d-141">默认情况下，由这些用户安排的任何 Skype for Business 会议将迁移到团队。</span><span class="sxs-lookup"><span data-stu-id="ce63d-141">By default, any Skype for Business meetings scheduled by these users will be migrated to Teams.</span></span>

<span data-ttu-id="ce63d-142">下面是键命令：</span><span class="sxs-lookup"><span data-stu-id="ce63d-142">Following are the key commands:</span></span>

1. <span data-ttu-id="ce63d-143">将租户范围的默认值设置为 mode SfbWithTeamsCollab，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ce63d-143">Set the tenant-wide default to mode SfbWithTeamsCollab as follows:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. <span data-ttu-id="ce63d-144">将试点用户升级到 TeamsOnly，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ce63d-144">Upgrade the pilot users to TeamsOnly as follows:</span></span>

   - <span data-ttu-id="ce63d-145">对于处于联机状态的用户：</span><span class="sxs-lookup"><span data-stu-id="ce63d-145">For a user who is online:</span></span>

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - <span data-ttu-id="ce63d-146">对于本地用户：</span><span class="sxs-lookup"><span data-stu-id="ce63d-146">For a user who is on-premises:</span></span>

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

<span data-ttu-id="ce63d-147">注释</span><span class="sxs-lookup"><span data-stu-id="ce63d-147">Notes</span></span>
 
- <span data-ttu-id="ce63d-148">你可以将租户范围内的策略设置为 SfbWithTeamsCollab，而不是将其设置为 SfbWithTeamsCollabAndMeetings。</span><span class="sxs-lookup"><span data-stu-id="ce63d-148">Instead of setting the tenant-wide policy to SfbWithTeamsCollab, you could set it to SfbWithTeamsCollabAndMeetings.</span></span> <span data-ttu-id="ce63d-149">这将导致所有用户在团队中安排所有新会议。</span><span class="sxs-lookup"><span data-stu-id="ce63d-149">This causes all users to schedule all new meetings in Teams.</span></span>
- <span data-ttu-id="ce63d-150">`Move-CsUser` 是本地工具中的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ce63d-150">`Move-CsUser` is a cmdlet in the on-premises tools.</span></span> <span data-ttu-id="ce63d-151">`MoveToTeams`切换器需要具有 skype for Business server 2019 或 skype for Business server 2015 和 CU8 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="ce63d-151">The `MoveToTeams` switch requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span> <span data-ttu-id="ce63d-152">如果你使用的是以前的版本，你可以先将用户移动到 Skype for business Online，然后向该用户授予 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="ce63d-152">If you are using a prior version, you can first move the user to Skype for Business Online, and then grant TeamsOnly mode to that user.</span></span>
- <span data-ttu-id="ce63d-153">默认情况下，当升级到 TeamsOnly 模式或分配 SfbWithTeamsCollabAndMeetings 模式时，Skype for business 会议将迁移到团队。</span><span class="sxs-lookup"><span data-stu-id="ce63d-153">By default, Skype for Business meetings are migrated to Teams when upgrading to TeamsOnly mode or when assigning SfbWithTeamsCollabAndMeetings mode.</span></span>  

<span data-ttu-id="ce63d-154">下图显示了未事先使用团队的组织的 "选择功能" 升级的概念阶段。</span><span class="sxs-lookup"><span data-stu-id="ce63d-154">The diagram below shows the conceptual phases of select capabilities upgrade for an organization with no prior usage of Teams.</span></span> <span data-ttu-id="ce63d-155">条形图的高度表示用户数。</span><span class="sxs-lookup"><span data-stu-id="ce63d-155">The height of the bars represents number of users.</span></span> <span data-ttu-id="ce63d-156">在升级的任何阶段，所有用户都可以相互通信。</span><span class="sxs-lookup"><span data-stu-id="ce63d-156">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="ce63d-157">Skype for Business 用户使用互操作与 TeamsOnly 用户通信，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="ce63d-157">Skype for Business users communicate with TeamsOnly users using Interop, and vice versa.</span></span> <span data-ttu-id="ce63d-158">在孤岛模式下的用户必须确保同时运行两个客户端。</span><span class="sxs-lookup"><span data-stu-id="ce63d-158">Users in Islands mode must be sure to run both clients.</span></span>

![图表显示选择功能升级但不事先使用团队](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a><span data-ttu-id="ce63d-160">已在孤岛模式下使用团队的组织的 "选择功能" 升级</span><span class="sxs-lookup"><span data-stu-id="ce63d-160">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>

<span data-ttu-id="ce63d-161">如果您的组织中的某些用户在以孤岛模式使用团队，则您可能不希望删除现有用户的功能。</span><span class="sxs-lookup"><span data-stu-id="ce63d-161">If some users in your organization are actively using Teams in Islands mode, you probably do not want to remove functionality from existing users.</span></span> <span data-ttu-id="ce63d-162">因此，在更改租户范围的策略之前，需要额外步骤。</span><span class="sxs-lookup"><span data-stu-id="ce63d-162">Therefore, an extra step is required before changing the tenant-wide policy.</span></span> <span data-ttu-id="ce63d-163">解决方案是先将这些现有活动团队用户 "grandfather" 用户转换为孤岛模式，然后再将租户范围内的策略设置为 "SfbWithTeamsCollab"。</span><span class="sxs-lookup"><span data-stu-id="ce63d-163">The solution is to “grandfather” these existing active Teams users into Islands mode, before setting the tenant-wide policy to SfbWithTeamsCollab.</span></span>  <span data-ttu-id="ce63d-164">完成此操作后，你可以按照上面的步骤继续部署，但是你将有两组用户迁移到 TeamsOnly：团队中处于活动状态的用户将处于 "孤岛" 模式下，其余用户将处于 "SfbWithTeamsCollab" 模式。</span><span class="sxs-lookup"><span data-stu-id="ce63d-164">Once you’ve done that, you can proceed with deployment as above, however, you’ll have two groups of users who are moving to TeamsOnly:  the users who were active in Teams will be in Islands mode, and the remaining users will be in SfbWithTeamsCollab mode.</span></span> <span data-ttu-id="ce63d-165">你可以逐步将这些用户移动到 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="ce63d-165">You can progressively move these users to TeamsOnly mode.</span></span>

1. <span data-ttu-id="ce63d-166">查找团队中处于活动状态的用户，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ce63d-166">Find users who are active in Teams as follows:</span></span>

   1. <span data-ttu-id="ce63d-167">从 Microsoft 365 管理中心的左侧导航中，转到 "报表"，然后转到 "使用情况"。</span><span class="sxs-lookup"><span data-stu-id="ce63d-167">From the Microsoft 365 admin center, in the left-hand navigation, go to Reports, and then Usage.</span></span> 
   2. <span data-ttu-id="ce63d-168">在 "选择报表" 下拉列表中，选择 "Microsoft 团队"，然后选择 "用户活动"。</span><span class="sxs-lookup"><span data-stu-id="ce63d-168">In the “Select a report” dropdown, choose Microsoft Teams, and then User Activity.</span></span> <span data-ttu-id="ce63d-169">这将提供已在团队中处于活动状态的用户的可导出表。</span><span class="sxs-lookup"><span data-stu-id="ce63d-169">This will provide an exportable table of users who have been active in Teams.</span></span> 
   3. <span data-ttu-id="ce63d-170">单击 "导出"、"打开 Excel" 和 "筛选" 以仅显示团队中处于活动状态的用户。</span><span class="sxs-lookup"><span data-stu-id="ce63d-170">Click Export, open Excel, and filter to show only the users who are active in Teams.</span></span>

2. <span data-ttu-id="ce63d-171">对于在步骤1中发现的每个活动团队用户，请在远程 PowerShell 中为其分配孤岛模式。</span><span class="sxs-lookup"><span data-stu-id="ce63d-171">For each active Teams user found in step 1, assign them Islands mode in remote PowerShell.</span></span> <span data-ttu-id="ce63d-172">这允许你转到下一步，并确保不更改用户体验。</span><span class="sxs-lookup"><span data-stu-id="ce63d-172">This allows you to go to the next step, and ensures you don’t change the user experience.</span></span>  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. <span data-ttu-id="ce63d-173">将租户范围内的策略设置为 SfbWithTeamsCollab：</span><span class="sxs-lookup"><span data-stu-id="ce63d-173">Set the tenant-wide policy to SfbWithTeamsCollab:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. <span data-ttu-id="ce63d-174">将所选用户升级到 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="ce63d-174">Upgrade selected users to TeamsOnly mode.</span></span> <span data-ttu-id="ce63d-175">你可以选择在 "孤岛模式" 或 "SfbWithTeamsCollab" 模式下升级用户，但你可能希望首先优先于在孤岛模式下升级用户，以最大程度减少用户处于 "孤岛模式" 时可能出现的混淆的可能性。</span><span class="sxs-lookup"><span data-stu-id="ce63d-175">You can choose to upgrade either users in Islands mode or SfbWithTeamsCollab mode, although you might want to prioritize upgrading the users in Islands mode first to minimize the potential for confusion that can arise when users are in Islands mode.</span></span>   

   <span data-ttu-id="ce63d-176">对于驻留在 Skype for business Online 中的用户：</span><span class="sxs-lookup"><span data-stu-id="ce63d-176">For users homed in Skype for Business Online:</span></span>  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   <span data-ttu-id="ce63d-177">对于驻留在本地 Skype for business 服务器的用户：</span><span class="sxs-lookup"><span data-stu-id="ce63d-177">For users homed in Skype for Business Server on-premises:</span></span>  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

<span data-ttu-id="ce63d-178">下图显示了一个选择功能过渡的概念阶段，其中的 "开始" 中有活动的孤岛用户。</span><span class="sxs-lookup"><span data-stu-id="ce63d-178">The diagram below shows the conceptual phases of a select capabilities transition in which there are active Islands users at the start.</span></span> <span data-ttu-id="ce63d-179">条形图的高度表示用户数。</span><span class="sxs-lookup"><span data-stu-id="ce63d-179">The height of the bars represents the number of users.</span></span> <span data-ttu-id="ce63d-180">在升级的任何阶段，所有用户都可以相互通信。</span><span class="sxs-lookup"><span data-stu-id="ce63d-180">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="ce63d-181">Skype for Business 用户使用互操作与 TeamsOnly 用户通信，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="ce63d-181">Skype for Business users communicate with TeamsOnly users using interop, and vice versa.</span></span> 


![图中显示了在孤岛模式下与活动用户进行升级的 "选择功能"](media/teams-upgrade-2.png)

   



## <a name="related-links"></a><span data-ttu-id="ce63d-183">相关链接</span><span class="sxs-lookup"><span data-stu-id="ce63d-183">Related links</span></span>

[<span data-ttu-id="ce63d-184">面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导</span><span class="sxs-lookup"><span data-stu-id="ce63d-184">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="ce63d-185">配置 Skype for Business 服务器与 Microsoft 365 或 Office 365 之间的混合连接</span><span class="sxs-lookup"><span data-stu-id="ce63d-185">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="ce63d-186">在本地和云之间移动用户</span><span class="sxs-lookup"><span data-stu-id="ce63d-186">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="ce63d-187">设置共存和升级设置</span><span class="sxs-lookup"><span data-stu-id="ce63d-187">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="ce63d-188">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="ce63d-188">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="ce63d-189">使用会议迁移服务 (MMS) </span><span class="sxs-lookup"><span data-stu-id="ce63d-189">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

