---
title: Teams 客户端体验和共存模式的一致性
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: 了解团队客户端体验和与共存模式的一致性（SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings）。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0c67046128c79608f19a4a1f4474164a949f37ef
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "43903357"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="8349e-103">Teams 客户端体验和共存模式的一致性</span><span class="sxs-lookup"><span data-stu-id="8349e-103">Teams client experience and conformance to coexistence modes</span></span>

<a name="about-upgrade-basic"></a>

<span data-ttu-id="8349e-104">Skype for Business 共存模式（SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings）的用途是为最终用户提供简单、可预测的体验，因为组织从 Skype for Business 过渡到团队。</span><span class="sxs-lookup"><span data-stu-id="8349e-104">The purpose of the Skype for Business coexistence modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="8349e-105">对于迁移到团队的组织，"**仅团队**" 模式是每个用户的最终目标，但并非所有用户都需要同时分配**团队**（或任何其他模式）。</span><span class="sxs-lookup"><span data-stu-id="8349e-105">For an organization moving to Teams, the **Teams Only** mode is the final destination for each user, though not all users need to be assigned **Teams Only** (or any other mode) at the same time.</span></span>  <span data-ttu-id="8349e-106">在用户到达 TeamsOnly 模式之前，组织可以使用任何 Skype for Business 共存模式来确保**仅有团队**的用户和尚未使用的用户之间的可预测通信。</span><span class="sxs-lookup"><span data-stu-id="8349e-106">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business coexistence modes to ensure predictable communication between users who are **Teams Only** and those who aren't yet.</span></span> 

<span data-ttu-id="8349e-107">当用户处于任何 Skype for Business 模式时，所有传入聊天和通话都将路由到用户的 Skype for business 客户端。</span><span class="sxs-lookup"><span data-stu-id="8349e-107">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user's Skype for Business client.</span></span> <span data-ttu-id="8349e-108">为避免最终用户混淆和确保正确路由，当用户处于任何 Skype for Business 模式时，将禁用团队客户端中的 "调用和聊天" 功能。</span><span class="sxs-lookup"><span data-stu-id="8349e-108">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="8349e-109">同样，当用户处于 SfBOnly 或 SfBWithTeamsCollab 模式时，将显式禁用团队中的会议计划，并在用户处于 SfBWithTeamsCollabAndMeetings 模式时显式启用。</span><span class="sxs-lookup"><span data-stu-id="8349e-109">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>

<span data-ttu-id="8349e-110">由于状态是通过聊天和通话的可访问性指示，当聊天和通话处于禁用状态时，团队中的自保持状态（即用户图片中的团队客户端的显示状态）也会隐藏。</span><span class="sxs-lookup"><span data-stu-id="8349e-110">Because presence is an indication of reachability through chat and calling, when chat and calling are disabled, self-presence in Teams (that is, the display of one's own presence in the Teams client in the user's picture) is also hidden.</span></span> 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="8349e-111">团队客户端中的可用功能如何根据模式更改</span><span class="sxs-lookup"><span data-stu-id="8349e-111">How the available functionality in Teams client changes based on mode</span></span>

<span data-ttu-id="8349e-112">团队中的可用功能取决于用户的共存模式（由 TeamsUpgradePolicy 设置）。</span><span class="sxs-lookup"><span data-stu-id="8349e-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="8349e-113">下表总结了该行为：</span><span class="sxs-lookup"><span data-stu-id="8349e-113">The following table summarizes the behavior:</span></span>

|<span data-ttu-id="8349e-114">用户的有效模式</span><span class="sxs-lookup"><span data-stu-id="8349e-114">User's effective mode</span></span>|<span data-ttu-id="8349e-115">团队客户端中的体验</span><span class="sxs-lookup"><span data-stu-id="8349e-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="8349e-116">任何 Skype for Business 模式</span><span class="sxs-lookup"><span data-stu-id="8349e-116">Any Skype for Business mode</span></span>|<span data-ttu-id="8349e-117">已禁用通话、聊天和自展示。</span><span class="sxs-lookup"><span data-stu-id="8349e-117">Calling, Chat, and self-presence are disabled.</span></span>|
|<span data-ttu-id="8349e-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="8349e-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="8349e-119">会议计划可用</span><span class="sxs-lookup"><span data-stu-id="8349e-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="8349e-120">SfBWithTeamsCollab 或 SfBOnly<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="8349e-120">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="8349e-121">会议日程安排不可用</span><span class="sxs-lookup"><span data-stu-id="8349e-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="8349e-122">下面的屏幕截图演示**团队**的区别或**孤岛**模式与所有其他模式之间的区别。</span><span class="sxs-lookup"><span data-stu-id="8349e-122">The following screenshots illustrate the difference between **Teams Only** or **Islands** mode and all other modes.</span></span> <span data-ttu-id="8349e-123">请注意，"聊天" 和 "呼叫" 图标默认情况下仅适用于**团队**或**孤岛**模式（左屏幕截图），但不适用于其他模式（右屏幕截图）：</span><span class="sxs-lookup"><span data-stu-id="8349e-123">Note that the chat and calling icons are available by default with **Teams Only** or **Islands** mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![团队模式的并排比较](media/teams-mode-comparison.png)

<span data-ttu-id="8349e-125">此外，自联机状态在其他模式下不可用，如下所示。</span><span class="sxs-lookup"><span data-stu-id="8349e-125">In addition, self presence is not available in the other modes, as shown here.</span></span>

![会议中的自我出席的屏幕截图](media/meetings-first-no-self-presence-general.png)
 
<span data-ttu-id="8349e-127">**注意：**
<sup>1</sup>此时，SfBwithTeamsCollab 和 SfBOnly 的行为相同，但意图适用于 SfBOnly 模式，以禁用团队中的频道和文件功能。</span><span class="sxs-lookup"><span data-stu-id="8349e-127">**Note:**
<sup>1</sup> At this time, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams.</span></span> <span data-ttu-id="8349e-128">在过渡期间，可以使用应用权限策略隐藏频道。</span><span class="sxs-lookup"><span data-stu-id="8349e-128">In the interim, Channels can be hidden using the App Permissions policy.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="8349e-129">模式对其他策略设置的影响</span><span class="sxs-lookup"><span data-stu-id="8349e-129">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="8349e-130">如上所述，用户的共存模式影响的是用户的团队客户端提供的功能。</span><span class="sxs-lookup"><span data-stu-id="8349e-130">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="8349e-131">这意味着，mode 的值可以优先于其他策略设置的值，具体取决于模式。</span><span class="sxs-lookup"><span data-stu-id="8349e-131">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="8349e-132">特别是，共存模式会影响是否遵守下列策略设置：</span><span class="sxs-lookup"><span data-stu-id="8349e-132">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="8349e-133">**模态（应用）**</span><span class="sxs-lookup"><span data-stu-id="8349e-133">**Modality (App)**</span></span>|<span data-ttu-id="8349e-134">**策略。设置**</span><span class="sxs-lookup"><span data-stu-id="8349e-134">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="8349e-135">聊天</span><span class="sxs-lookup"><span data-stu-id="8349e-135">Chat</span></span>|<span data-ttu-id="8349e-136">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="8349e-136">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="8349e-137">通话</span><span class="sxs-lookup"><span data-stu-id="8349e-137">Calling</span></span>|<span data-ttu-id="8349e-138">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="8349e-138">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="8349e-139">会议计划</span><span class="sxs-lookup"><span data-stu-id="8349e-139">Meeting scheduling</span></span>|<span data-ttu-id="8349e-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="8349e-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="8349e-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="8349e-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="8349e-142">管理员*无*需在使用共存模式时显式设置这些策略设置，但重要的是要了解这些设置在给定模式下的行为方式是有效的。</span><span class="sxs-lookup"><span data-stu-id="8349e-142">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="8349e-143">众</span><span class="sxs-lookup"><span data-stu-id="8349e-143">Mode</span></span>|<span data-ttu-id="8349e-144">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="8349e-144">AllowUserChat</span></span>|<span data-ttu-id="8349e-145">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="8349e-145">AllowPrivateCalling</span></span>|<span data-ttu-id="8349e-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="8349e-146">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="8349e-147">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="8349e-147">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="8349e-148">TeamsOnly 或孤岛</span><span class="sxs-lookup"><span data-stu-id="8349e-148">TeamsOnly or Islands</span></span>|<span data-ttu-id="8349e-149">已启用</span><span class="sxs-lookup"><span data-stu-id="8349e-149">Enabled</span></span>|<span data-ttu-id="8349e-150">已启用</span><span class="sxs-lookup"><span data-stu-id="8349e-150">Enabled</span></span>|<span data-ttu-id="8349e-151">已启用</span><span class="sxs-lookup"><span data-stu-id="8349e-151">Enabled</span></span>|<span data-ttu-id="8349e-152">已启用</span><span class="sxs-lookup"><span data-stu-id="8349e-152">Enabled</span></span>|
|<span data-ttu-id="8349e-153">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="8349e-153">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="8349e-154">已禁用</span><span class="sxs-lookup"><span data-stu-id="8349e-154">Disabled</span></span>|<span data-ttu-id="8349e-155">已禁用</span><span class="sxs-lookup"><span data-stu-id="8349e-155">Disabled</span></span>|<span data-ttu-id="8349e-156">已启用</span><span class="sxs-lookup"><span data-stu-id="8349e-156">Enabled</span></span>|<span data-ttu-id="8349e-157">已启用</span><span class="sxs-lookup"><span data-stu-id="8349e-157">Enabled</span></span>|
|<span data-ttu-id="8349e-158">SfBWithTeamsCollab 或 SfBOnly</span><span class="sxs-lookup"><span data-stu-id="8349e-158">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="8349e-159">已禁用</span><span class="sxs-lookup"><span data-stu-id="8349e-159">Disabled</span></span>|<span data-ttu-id="8349e-160">已禁用</span><span class="sxs-lookup"><span data-stu-id="8349e-160">Disabled</span></span>|<span data-ttu-id="8349e-161">已禁用</span><span class="sxs-lookup"><span data-stu-id="8349e-161">Disabled</span></span>|<span data-ttu-id="8349e-162">已禁用</span><span class="sxs-lookup"><span data-stu-id="8349e-162">Disabled</span></span>|
||||||

<span data-ttu-id="8349e-163">使用 PowerShell 时， `Grant-CsTeamsUpgradePolicy` Cmdlet 检查 TeamsMessagingPolicy、TeamsCallingPolicy 和 TeamsMeetingPolicy 中的相应设置的配置，以确定这些设置是否将被 TeamsUpgradePolicy 取代，如果是，则会在 PowerShell 中提供一条信息性消息。</span><span class="sxs-lookup"><span data-stu-id="8349e-163">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superseded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="8349e-164">如上所述，不需要再设置其他策略设置。</span><span class="sxs-lookup"><span data-stu-id="8349e-164">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="8349e-165">下面是 PowerShell 警告的示例：</span><span class="sxs-lookup"><span data-stu-id="8349e-165">The following is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a><span data-ttu-id="8349e-166">相关主题</span><span class="sxs-lookup"><span data-stu-id="8349e-166">Related topics</span></span>

[<span data-ttu-id="8349e-167">面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导</span><span class="sxs-lookup"><span data-stu-id="8349e-167">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)




