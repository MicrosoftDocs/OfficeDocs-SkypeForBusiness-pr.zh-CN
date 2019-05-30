---
title: Teams 客户端体验和共存模式的一致性
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
description: 团队客户体验和 comformance 到共存模式
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 08bc09ac316a41dfe7ff39bc741dbaa514f30044
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548650"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="a05ee-103">Teams 客户端体验和共存模式的一致性</span><span class="sxs-lookup"><span data-stu-id="a05ee-103">Teams client experience and conformance to coexistence modes</span></span>

> [!NOTE]
> <span data-ttu-id="a05ee-104">此页面介绍团队客户端在用户处于任何 Skype for Business 模式 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) 时的行为中的重要、最近发布的更改。</span><span class="sxs-lookup"><span data-stu-id="a05ee-104">This page describes important, recently released changes in the behavior of Teams client when users are in any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).</span></span>


<span data-ttu-id="a05ee-105">当组织从 Skype for Business 切换到团队时, 共存模式的用途是为最终用户提供简单且可预测的体验。</span><span class="sxs-lookup"><span data-stu-id="a05ee-105">The purpose of co-existence modes is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="a05ee-106">对于迁移到团队的组织, TeamsOnly 模式是每个用户的最终目标, 但并非所有用户都需要同时分配 TeamsOnly (或任何其他模式)。</span><span class="sxs-lookup"><span data-stu-id="a05ee-106">For an organization moving to Teams, the TeamsOnly mode is the final destination for each user, though not all users need to be assigned TeamsOnly (or any other mode) at the same time.</span></span>  <span data-ttu-id="a05ee-107">在用户到达 TeamsOnly 模式之前, 组织可以使用任何 Skype for Business 模式 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) 确保 TeamsOnly 用户和尚未使用的用户之间可预测的通信。</span><span class="sxs-lookup"><span data-stu-id="a05ee-107">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) to ensure predictable communication between users who are TeamsOnly and those who aren’t yet.</span></span> 

<span data-ttu-id="a05ee-108">当用户处于任何 Skype for Business 模式时, 所有传入聊天和通话都将路由到用户的 Skype for business 客户端。</span><span class="sxs-lookup"><span data-stu-id="a05ee-108">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user’s Skype for Business client.</span></span> <span data-ttu-id="a05ee-109">为避免最终用户混淆和确保正确路由, 当用户处于任何 Skype for Business 模式时, 将禁用团队客户端中的 "调用和聊天" 功能。</span><span class="sxs-lookup"><span data-stu-id="a05ee-109">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="a05ee-110">同样, 当用户处于 SfBOnly 或 SfBWithTeamsCollab 模式时, 将显式禁用团队中的会议计划, 并在用户处于 SfBWithTeamsCollabAndMeetings 模式时显式启用。</span><span class="sxs-lookup"><span data-stu-id="a05ee-110">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>   

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="a05ee-111">团队客户端中的可用功能如何根据模式更改</span><span class="sxs-lookup"><span data-stu-id="a05ee-111">How the available functionality in Teams client changes based on mode</span></span>
<span data-ttu-id="a05ee-112">团队中的可用功能取决于用户的共存模式 (由 TeamsUpgradePolicy 设置)。</span><span class="sxs-lookup"><span data-stu-id="a05ee-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="a05ee-113">下表总结了该行为:</span><span class="sxs-lookup"><span data-stu-id="a05ee-113">The table below summarizes the  behavior:</span></span>

|<span data-ttu-id="a05ee-114">用户的有效模式</span><span class="sxs-lookup"><span data-stu-id="a05ee-114">User's effective mode</span></span>|<span data-ttu-id="a05ee-115">团队客户端中的体验</span><span class="sxs-lookup"><span data-stu-id="a05ee-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="a05ee-116">任何 Skype for Business 模式</span><span class="sxs-lookup"><span data-stu-id="a05ee-116">Any Skype for Business mode</span></span>|<span data-ttu-id="a05ee-117">已禁用通话和聊天。</span><span class="sxs-lookup"><span data-stu-id="a05ee-117">Calling and Chat are disabled.</span></span>|
|<span data-ttu-id="a05ee-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="a05ee-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="a05ee-119">会议计划可用</span><span class="sxs-lookup"><span data-stu-id="a05ee-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="a05ee-120">SfBWithTeamsCollab 或 SfBOnly<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a05ee-120">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="a05ee-121">会议日程安排不可用</span><span class="sxs-lookup"><span data-stu-id="a05ee-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="a05ee-122">下面的屏幕截图演示了 TeamsOnly 或孤岛模式与所有其他模式之间的差异。</span><span class="sxs-lookup"><span data-stu-id="a05ee-122">The following screenshots illustrate the difference between TeamsOnly or Islands mode and all other modes.</span></span> <span data-ttu-id="a05ee-123">请注意, 聊天和呼叫图标可通过 TeamsOnly 或孤岛模式 (左屏幕截图) 使用, 但不适用于其他模式 (右屏幕截图):</span><span class="sxs-lookup"><span data-stu-id="a05ee-123">Note that the chat and calling icons are available with TeamsOnly or Islands mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![团队模式的并排比较](media/teams-mode-comparison.png)


 
<span data-ttu-id="a05ee-125">**注意:**
<sup>1</sup>现在, SfBwithTeamsCollab 和 SfBOnly 的行为相同, 但意图适用于 SfBOnly 模式以禁用团队中的频道和文件功能;但是, 当前没有任何可允许团队中的此功能被禁用的设置。</span><span class="sxs-lookup"><span data-stu-id="a05ee-125">**Note:**
<sup>1</sup> For now, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams; however, there is currently no setting that allows this functionality in Teams to be disabled.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="a05ee-126">模式对其他策略设置的影响</span><span class="sxs-lookup"><span data-stu-id="a05ee-126">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="a05ee-127">如上所述, 用户的共存模式影响的是用户的团队客户端提供的功能。</span><span class="sxs-lookup"><span data-stu-id="a05ee-127">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="a05ee-128">这意味着, mode 的值可以优先于其他策略设置的值, 具体取决于模式。</span><span class="sxs-lookup"><span data-stu-id="a05ee-128">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="a05ee-129">特别是, 共存模式会影响是否遵守下列策略设置:</span><span class="sxs-lookup"><span data-stu-id="a05ee-129">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="a05ee-130">**模态 (应用)**</span><span class="sxs-lookup"><span data-stu-id="a05ee-130">**Modality (App)**</span></span>|<span data-ttu-id="a05ee-131">**策略。设置**</span><span class="sxs-lookup"><span data-stu-id="a05ee-131">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="a05ee-132">聊天</span><span class="sxs-lookup"><span data-stu-id="a05ee-132">Chat</span></span>|<span data-ttu-id="a05ee-133">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="a05ee-133">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="a05ee-134">通话</span><span class="sxs-lookup"><span data-stu-id="a05ee-134">Calling</span></span>|<span data-ttu-id="a05ee-135">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="a05ee-135">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="a05ee-136">会议计划</span><span class="sxs-lookup"><span data-stu-id="a05ee-136">Meeting scheduling</span></span>|<span data-ttu-id="a05ee-137">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="a05ee-137">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="a05ee-138">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="a05ee-138">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="a05ee-139">管理员*无*需在使用共存模式时显式设置这些策略设置, 但重要的是要了解这些设置在给定模式下的行为方式是有效的。</span><span class="sxs-lookup"><span data-stu-id="a05ee-139">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="a05ee-140">众</span><span class="sxs-lookup"><span data-stu-id="a05ee-140">Mode</span></span>|<span data-ttu-id="a05ee-141">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="a05ee-141">AllowUserChat</span></span>|<span data-ttu-id="a05ee-142">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="a05ee-142">AllowPrivateCalling</span></span>|<span data-ttu-id="a05ee-143">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="a05ee-143">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="a05ee-144">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="a05ee-144">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="a05ee-145">TeamsOnly 或孤岛</span><span class="sxs-lookup"><span data-stu-id="a05ee-145">TeamsOnly or Islands</span></span>|<span data-ttu-id="a05ee-146">已启用</span><span class="sxs-lookup"><span data-stu-id="a05ee-146">Enabled</span></span>|<span data-ttu-id="a05ee-147">已启用</span><span class="sxs-lookup"><span data-stu-id="a05ee-147">Enabled</span></span>|<span data-ttu-id="a05ee-148">已启用</span><span class="sxs-lookup"><span data-stu-id="a05ee-148">Enabled</span></span>|<span data-ttu-id="a05ee-149">已启用</span><span class="sxs-lookup"><span data-stu-id="a05ee-149">Enabled</span></span>|
|<span data-ttu-id="a05ee-150">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="a05ee-150">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="a05ee-151">已禁用</span><span class="sxs-lookup"><span data-stu-id="a05ee-151">Disabled</span></span>|<span data-ttu-id="a05ee-152">已禁用</span><span class="sxs-lookup"><span data-stu-id="a05ee-152">Disabled</span></span>|<span data-ttu-id="a05ee-153">已启用</span><span class="sxs-lookup"><span data-stu-id="a05ee-153">Enabled</span></span>|<span data-ttu-id="a05ee-154">已启用</span><span class="sxs-lookup"><span data-stu-id="a05ee-154">Enabled</span></span>|
|<span data-ttu-id="a05ee-155">SfBWithTeamsCollab 或 SfBOnly</span><span class="sxs-lookup"><span data-stu-id="a05ee-155">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="a05ee-156">已禁用</span><span class="sxs-lookup"><span data-stu-id="a05ee-156">Disabled</span></span>|<span data-ttu-id="a05ee-157">已禁用</span><span class="sxs-lookup"><span data-stu-id="a05ee-157">Disabled</span></span>|<span data-ttu-id="a05ee-158">已禁用</span><span class="sxs-lookup"><span data-stu-id="a05ee-158">Disabled</span></span>|<span data-ttu-id="a05ee-159">已禁用</span><span class="sxs-lookup"><span data-stu-id="a05ee-159">Disabled</span></span>|
||||||

<span data-ttu-id="a05ee-160">使用 PowerShell 时, `Grant-CsTeamsUpgradePolicy` Cmdlet 检查 TeamsMessagingPolicy、TeamsCallingPolicy 和 TeamsMeetingPolicy 中的相应设置的配置, 以确定这些设置是否会被 TeamsUpgradePolicy 取代, 如果是, 则PowerShell 中提供了信息性消息。</span><span class="sxs-lookup"><span data-stu-id="a05ee-160">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superceded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="a05ee-161">如上所述, 不需要再设置其他策略设置。</span><span class="sxs-lookup"><span data-stu-id="a05ee-161">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="a05ee-162">下面是 PowerShell 警告的示例如下:</span><span class="sxs-lookup"><span data-stu-id="a05ee-162">Below is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a><span data-ttu-id="a05ee-163">相关主题</span><span class="sxs-lookup"><span data-stu-id="a05ee-163">Related topics</span></span>

[<span data-ttu-id="a05ee-164">面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导</span><span class="sxs-lookup"><span data-stu-id="a05ee-164">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




