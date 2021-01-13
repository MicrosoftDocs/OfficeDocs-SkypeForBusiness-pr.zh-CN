---
title: Teams 客户端体验和共存模式的一致性
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: 了解 Teams 客户端体验和符合共存模式 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) 。
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
ms.openlocfilehash: 20d1ff52fa59f31b796d2580a0e2819c80caaf42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821022"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="45b46-103">Teams 客户端体验和共存模式的一致性</span><span class="sxs-lookup"><span data-stu-id="45b46-103">Teams client experience and conformance to coexistence modes</span></span>

<a name="about-upgrade-basic"></a>

<span data-ttu-id="45b46-104">Skype for Business 共存模式 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) 的目的是在组织从 Skype for Business 过渡到 Teams 时为最终用户提供简单且可预测的体验。</span><span class="sxs-lookup"><span data-stu-id="45b46-104">The purpose of the Skype for Business coexistence modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="45b46-105">对于迁移到 Teams 的组织，"仅 **Teams"** 模式是每个用户的最终目标，尽管并非所有用户都需要同时分配 **Teams** (或其他任何) 模式。</span><span class="sxs-lookup"><span data-stu-id="45b46-105">For an organization moving to Teams, the **Teams Only** mode is the final destination for each user, though not all users need to be assigned **Teams Only** (or any other mode) at the same time.</span></span>  <span data-ttu-id="45b46-106">在用户进入 TeamsOnly 模式之前，组织可以使用任何 Skype for Business 共存模式来确保仅 Teams 用户与尚未加入 **Teams** 的用户之间的通信可预测。</span><span class="sxs-lookup"><span data-stu-id="45b46-106">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business coexistence modes to ensure predictable communication between users who are **Teams Only** and those who aren't yet.</span></span> 

<span data-ttu-id="45b46-107">当用户在任何 Skype for Business 模式下时，所有传入聊天和呼叫将路由到用户的 Skype for Business 客户端。</span><span class="sxs-lookup"><span data-stu-id="45b46-107">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user's Skype for Business client.</span></span> <span data-ttu-id="45b46-108">为了避免最终用户混淆并确保正确的路由，当用户处于任何 Skype for Business 模式时，Teams 客户端中的呼叫和聊天功能将被禁用。</span><span class="sxs-lookup"><span data-stu-id="45b46-108">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="45b46-109">同样，当用户处于 SfBOnly 或 SfBWithTeamsCollab 模式时，将显式禁用 Teams 中的会议计划，当用户处于 SfBWithTeamsCollabAndMeetings 模式时显式启用。</span><span class="sxs-lookup"><span data-stu-id="45b46-109">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>

<span data-ttu-id="45b46-110">由于状态通过聊天和通话指示可联系性，因此当禁用聊天和通话时，Teams (中的自我存在（即，在用户的图片中的 Teams 客户端中显示自己的状态) 也会隐藏。</span><span class="sxs-lookup"><span data-stu-id="45b46-110">Because presence is an indication of reachability through chat and calling, when chat and calling are disabled, self-presence in Teams (that is, the display of one's own presence in the Teams client in the user's picture) is also hidden.</span></span> 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="45b46-111">Teams 客户端中的可用功能如何根据模式变化</span><span class="sxs-lookup"><span data-stu-id="45b46-111">How the available functionality in Teams client changes based on mode</span></span>

<span data-ttu-id="45b46-112">Teams 中的可用功能取决于 TeamsUpgradePolicy 设置的用户共存模式。</span><span class="sxs-lookup"><span data-stu-id="45b46-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="45b46-113">下表总结了此行为：</span><span class="sxs-lookup"><span data-stu-id="45b46-113">The following table summarizes the behavior:</span></span>

|<span data-ttu-id="45b46-114">用户的有效模式</span><span class="sxs-lookup"><span data-stu-id="45b46-114">User's effective mode</span></span>|<span data-ttu-id="45b46-115">Teams 客户端体验</span><span class="sxs-lookup"><span data-stu-id="45b46-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="45b46-116">任何 Skype for Business 模式</span><span class="sxs-lookup"><span data-stu-id="45b46-116">Any Skype for Business mode</span></span>|<span data-ttu-id="45b46-117">通话、聊天和自我状态处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="45b46-117">Calling, Chat, and self-presence are disabled.</span></span>|
|<span data-ttu-id="45b46-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="45b46-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="45b46-119">会议安排可用</span><span class="sxs-lookup"><span data-stu-id="45b46-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="45b46-120">SfBWithTeamsCollab 或 SfBOnly<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="45b46-120">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="45b46-121">会议安排不可用</span><span class="sxs-lookup"><span data-stu-id="45b46-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="45b46-122">以下屏幕截图说明了"仅 **Teams"** 或" **群岛** "模式与所有其他模式的区别。</span><span class="sxs-lookup"><span data-stu-id="45b46-122">The following screenshots illustrate the difference between **Teams Only** or **Islands** mode and all other modes.</span></span> <span data-ttu-id="45b46-123">请注意，默认情况下，聊天和呼叫图标在左侧屏幕截图 (**Teams** 模式或岛屿模式) 可用，但无法与其他模式 (屏幕快照) ：</span><span class="sxs-lookup"><span data-stu-id="45b46-123">Note that the chat and calling icons are available by default with **Teams Only** or **Islands** mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![Teams 模式的并排比较](media/teams-mode-comparison.png)

<span data-ttu-id="45b46-125">此外，自我状态在其他模式中不可用，如下所示。</span><span class="sxs-lookup"><span data-stu-id="45b46-125">In addition, self presence is not available in the other modes, as shown here.</span></span>

!["会议第一"中自我存在的屏幕截图](media/meetings-first-no-self-presence-general.png)
 
<span data-ttu-id="45b46-127">**注意：** 
<sup>1</sup>目前，SfBwithTeamsCollab 和 SfBOnly 的行为相同，但目的是让 SfBOnly 模式也禁用 Teams 中的频道和文件功能。</span><span class="sxs-lookup"><span data-stu-id="45b46-127">**Note:**
<sup>1</sup> At this time, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams.</span></span> <span data-ttu-id="45b46-128">在过渡期间，可以使用应用权限策略隐藏通道。</span><span class="sxs-lookup"><span data-stu-id="45b46-128">In the interim, Channels can be hidden using the App Permissions policy.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="45b46-129">模式对其他策略设置的影响</span><span class="sxs-lookup"><span data-stu-id="45b46-129">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="45b46-130">如上所述，用户的共存模式影响用户的 Teams 客户端中可用的功能。</span><span class="sxs-lookup"><span data-stu-id="45b46-130">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="45b46-131">这意味着，模式的值可以优先于其他策略设置的值，具体取决于模式。</span><span class="sxs-lookup"><span data-stu-id="45b46-131">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="45b46-132">具体而言，共存模式会影响是否遵循以下策略设置：</span><span class="sxs-lookup"><span data-stu-id="45b46-132">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="45b46-133">**形式 (应用)**</span><span class="sxs-lookup"><span data-stu-id="45b46-133">**Modality (App)**</span></span>|<span data-ttu-id="45b46-134">**Policy.Setting**</span><span class="sxs-lookup"><span data-stu-id="45b46-134">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="45b46-135">聊天</span><span class="sxs-lookup"><span data-stu-id="45b46-135">Chat</span></span>|<span data-ttu-id="45b46-136">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="45b46-136">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="45b46-137">通话</span><span class="sxs-lookup"><span data-stu-id="45b46-137">Calling</span></span>|<span data-ttu-id="45b46-138">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="45b46-138">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="45b46-139">会议安排</span><span class="sxs-lookup"><span data-stu-id="45b46-139">Meeting scheduling</span></span>|<span data-ttu-id="45b46-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="45b46-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="45b46-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="45b46-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="45b46-142">使用共存 *模式* 时，管理员无需显式设置这些策略设置，但必须了解这些设置在给定模式下的行为方式如下。</span><span class="sxs-lookup"><span data-stu-id="45b46-142">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="45b46-143">模式</span><span class="sxs-lookup"><span data-stu-id="45b46-143">Mode</span></span>|<span data-ttu-id="45b46-144">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="45b46-144">AllowUserChat</span></span>|<span data-ttu-id="45b46-145">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="45b46-145">AllowPrivateCalling</span></span>|<span data-ttu-id="45b46-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="45b46-146">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="45b46-147">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="45b46-147">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="45b46-148">TeamsOnly 或群岛</span><span class="sxs-lookup"><span data-stu-id="45b46-148">TeamsOnly or Islands</span></span>|<span data-ttu-id="45b46-149">已启用</span><span class="sxs-lookup"><span data-stu-id="45b46-149">Enabled</span></span>|<span data-ttu-id="45b46-150">已启用</span><span class="sxs-lookup"><span data-stu-id="45b46-150">Enabled</span></span>|<span data-ttu-id="45b46-151">已启用</span><span class="sxs-lookup"><span data-stu-id="45b46-151">Enabled</span></span>|<span data-ttu-id="45b46-152">已启用</span><span class="sxs-lookup"><span data-stu-id="45b46-152">Enabled</span></span>|
|<span data-ttu-id="45b46-153">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="45b46-153">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="45b46-154">已禁用</span><span class="sxs-lookup"><span data-stu-id="45b46-154">Disabled</span></span>|<span data-ttu-id="45b46-155">已禁用</span><span class="sxs-lookup"><span data-stu-id="45b46-155">Disabled</span></span>|<span data-ttu-id="45b46-156">已启用</span><span class="sxs-lookup"><span data-stu-id="45b46-156">Enabled</span></span>|<span data-ttu-id="45b46-157">已启用</span><span class="sxs-lookup"><span data-stu-id="45b46-157">Enabled</span></span>|
|<span data-ttu-id="45b46-158">SfBWithTeamsCollab 或 SfBOnly</span><span class="sxs-lookup"><span data-stu-id="45b46-158">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="45b46-159">已禁用</span><span class="sxs-lookup"><span data-stu-id="45b46-159">Disabled</span></span>|<span data-ttu-id="45b46-160">已禁用</span><span class="sxs-lookup"><span data-stu-id="45b46-160">Disabled</span></span>|<span data-ttu-id="45b46-161">已禁用</span><span class="sxs-lookup"><span data-stu-id="45b46-161">Disabled</span></span>|<span data-ttu-id="45b46-162">已禁用</span><span class="sxs-lookup"><span data-stu-id="45b46-162">Disabled</span></span>|
||||||

<span data-ttu-id="45b46-163">使用 PowerShell 时，该 cmdlet 会检查 `Grant-CsTeamsUpgradePolicy` TeamsMessagingPolicy、TeamsCallingPolicy 和 TeamsMeetingPolicy 中相应设置的配置，以确定这些设置是否将被 TeamsUpgradePolicy 取代，如果是，PowerShell 中会提供一条信息性消息。</span><span class="sxs-lookup"><span data-stu-id="45b46-163">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superseded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="45b46-164">如上所述，不再需要设置这些其他策略设置。</span><span class="sxs-lookup"><span data-stu-id="45b46-164">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="45b46-165">下面是 PowerShell 警告的示例：</span><span class="sxs-lookup"><span data-stu-id="45b46-165">The following is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a><span data-ttu-id="45b46-166">相关主题</span><span class="sxs-lookup"><span data-stu-id="45b46-166">Related topics</span></span>

[<span data-ttu-id="45b46-167">面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导</span><span class="sxs-lookup"><span data-stu-id="45b46-167">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)




