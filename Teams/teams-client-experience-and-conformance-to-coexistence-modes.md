---
title: Teams 客户端体验和共存模式的一致性
author: dearbeen
ms.author: bjwhalen
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
description: 团队客户端体验和 comformance 到共存模式
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4865d66d4d3ff1257d0fc4bd355a65c7c1330101
ms.sourcegitcommit: 5b33cfc828906917f76b0d2a9ae402c9336388a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30934785"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="33432-103">Teams 客户端体验和共存模式的一致性</span><span class="sxs-lookup"><span data-stu-id="33432-103">Teams client experience and conformance to coexistence modes</span></span>

> [!NOTE]
> <span data-ttu-id="33432-104">当用户在任何业务模式 （SfBOnly、 SfBWithTeamsCollab SfBWithTeamsCollabAndMeetings） Skype 中时，此页描述重要，最近发布更改团队客户端的行为。</span><span class="sxs-lookup"><span data-stu-id="33432-104">This page describes important, recently released changes in the behavior of Teams client when users are in any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).</span></span>


<span data-ttu-id="33432-105">共存模式旨在简单、 可预测体验的最终用户提供组织转换为从 for Business 的 Skype 向工作组。</span><span class="sxs-lookup"><span data-stu-id="33432-105">The purpose of co-existence modes is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="33432-106">将移动到团队的组织，TeamsOnly 模式是最终目标为每个用户，但并非所有用户都需要分配有 TeamsOnly （或任何其他模式） 在同一时间。</span><span class="sxs-lookup"><span data-stu-id="33432-106">For an organization moving to Teams, the TeamsOnly mode is the final destination for each user, though not all users need to be assigned TeamsOnly (or any other mode) at the same time.</span></span>  <span data-ttu-id="33432-107">之前达到 TeamsOnly 模式的用户，组织可以使用任何 Skype 业务模式 （SfBOnly SfBWithTeamsCollab、 SfBWithTeamsCollabAndMeetings） 以确保可预测 TeamsOnly 用户和那些尚未之间的通信。</span><span class="sxs-lookup"><span data-stu-id="33432-107">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) to ensure predictable communication between users who are TeamsOnly and those who aren’t yet.</span></span> 

<span data-ttu-id="33432-108">当用户在任何业务模式 Skype，所有传入的聊天和呼叫路由至业务客户端的用户的 Skype。</span><span class="sxs-lookup"><span data-stu-id="33432-108">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user’s Skype for Business client.</span></span> <span data-ttu-id="33432-109">若要避免最终用户混淆情况和确保正确路由，在客户端中的团队呼叫和聊天功能且被禁用时用户是在任何业务模式 Skype。</span><span class="sxs-lookup"><span data-stu-id="33432-109">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="33432-110">同样，在工作组中计划会议是显式禁用 SfBOnly 或 SfBWithTeamsCollab 模式，用户时，将明确启用当用户处于 SfBWithTeamsCollabAndMeetings 模式。</span><span class="sxs-lookup"><span data-stu-id="33432-110">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>   

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="33432-111">如何团队客户端中可用的功能更改基于模式</span><span class="sxs-lookup"><span data-stu-id="33432-111">How the available functionality in Teams client changes based on mode</span></span>
<span data-ttu-id="33432-112">用户的共存模式，团队 dependes 中由 TeamsUpgradePolicy 设置的可用功能。</span><span class="sxs-lookup"><span data-stu-id="33432-112">The available functionality in Teams dependes on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="33432-113">下表总结了行为：</span><span class="sxs-lookup"><span data-stu-id="33432-113">The table below summarizes the  behavior:</span></span>

|<span data-ttu-id="33432-114">用户的有效模式</span><span class="sxs-lookup"><span data-stu-id="33432-114">User's effective mode</span></span>|<span data-ttu-id="33432-115">在工作组客户端体验</span><span class="sxs-lookup"><span data-stu-id="33432-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="33432-116">业务模式的任何 Skype</span><span class="sxs-lookup"><span data-stu-id="33432-116">Any Skype for Business mode</span></span>|<span data-ttu-id="33432-117">禁用呼叫和聊天<sup>1</sup> 。</span><span class="sxs-lookup"><span data-stu-id="33432-117">Calling and Chat<sup>1</sup> are disabled.</span></span>|
|<span data-ttu-id="33432-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="33432-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="33432-119">会议安排位于</span><span class="sxs-lookup"><span data-stu-id="33432-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="33432-120">SfBWithTeamsCollab 或 SfBOnly<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="33432-120">SfBWithTeamsCollab or SfBOnly<sup>2</sup></span></span>|<span data-ttu-id="33432-121">会议安排不可用</span><span class="sxs-lookup"><span data-stu-id="33432-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="33432-122">以下屏幕快照说明 TeamsOnly 或群岛模式和所有其他模式之间的差异。</span><span class="sxs-lookup"><span data-stu-id="33432-122">The following screenshots illustrate the difference between TeamsOnly or Islands mode and all other modes.</span></span> <span data-ttu-id="33432-123">请注意，聊天和呼叫图标可使用 TeamsOnly 或群岛模式 （左屏幕截图），但不是与其他模式 （右屏幕截图）：</span><span class="sxs-lookup"><span data-stu-id="33432-123">Note that the chat and calling icons are available with TeamsOnly or Islands mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![显示工作组模式比较](media/teams-mode-comparison.png)


 
<span data-ttu-id="33432-125">**说明：**
<sup>1</sup>会议聊天是仍然可用。</span><span class="sxs-lookup"><span data-stu-id="33432-125">**Notes:**
<sup>1</sup> Meeting chat is still available.</span></span>

<span data-ttu-id="33432-126"><sup>2</sup>现在，SfBwithTeamsCollab 和 SfBOnly 的行为相同，但 SfBOnly 模式也禁用团队; 中的通道和文件功能的用途是但是，当前此功能允许在要禁用的团队中没有设置。</span><span class="sxs-lookup"><span data-stu-id="33432-126"><sup>2</sup> For now, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams; however, there is currently no setting that allows this functionality in Teams to be disabled.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="33432-127">对其他策略设置模式的影响</span><span class="sxs-lookup"><span data-stu-id="33432-127">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="33432-128">如上所述，用户的共存模式影响哪些功能，用户的工作组客户端中提供。</span><span class="sxs-lookup"><span data-stu-id="33432-128">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="33432-129">这意味着，模式的值可以优先于其他策略设置，具体取决于模式的值。</span><span class="sxs-lookup"><span data-stu-id="33432-129">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="33432-130">具体而言，共存模式影响是否有效以下策略设置：</span><span class="sxs-lookup"><span data-stu-id="33432-130">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="33432-131">**形式 （应用程序）**</span><span class="sxs-lookup"><span data-stu-id="33432-131">**Modality (App)**</span></span>|<span data-ttu-id="33432-132">**Policy.Setting**</span><span class="sxs-lookup"><span data-stu-id="33432-132">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="33432-133">聊天</span><span class="sxs-lookup"><span data-stu-id="33432-133">Chat</span></span>|<span data-ttu-id="33432-134">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="33432-134">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="33432-135">通话</span><span class="sxs-lookup"><span data-stu-id="33432-135">Calling</span></span>|<span data-ttu-id="33432-136">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="33432-136">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="33432-137">会议日程安排</span><span class="sxs-lookup"><span data-stu-id="33432-137">Meeting scheduling</span></span>|<span data-ttu-id="33432-138">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="33432-138">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="33432-139">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="33432-139">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="33432-140">管理员需要*不*明确地设置这些策略设置，使用共存模式，但它时需要了解，这些设置有效的行为，如下所示为给定的模式。</span><span class="sxs-lookup"><span data-stu-id="33432-140">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="33432-141">模式</span><span class="sxs-lookup"><span data-stu-id="33432-141">Mode</span></span>|<span data-ttu-id="33432-142">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="33432-142">AllowUserChat</span></span>|<span data-ttu-id="33432-143">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="33432-143">AllowPrivateCalling</span></span>|<span data-ttu-id="33432-144">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="33432-144">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="33432-145">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="33432-145">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="33432-146">TeamsOnly 或群岛</span><span class="sxs-lookup"><span data-stu-id="33432-146">TeamsOnly or Islands</span></span>|<span data-ttu-id="33432-147">已启用</span><span class="sxs-lookup"><span data-stu-id="33432-147">Enabled</span></span>|<span data-ttu-id="33432-148">已启用</span><span class="sxs-lookup"><span data-stu-id="33432-148">Enabled</span></span>|<span data-ttu-id="33432-149">已启用</span><span class="sxs-lookup"><span data-stu-id="33432-149">Enabled</span></span>|<span data-ttu-id="33432-150">已启用</span><span class="sxs-lookup"><span data-stu-id="33432-150">Enabled</span></span>|
|<span data-ttu-id="33432-151">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="33432-151">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="33432-152">已禁用</span><span class="sxs-lookup"><span data-stu-id="33432-152">Disabled</span></span>|<span data-ttu-id="33432-153">已禁用</span><span class="sxs-lookup"><span data-stu-id="33432-153">Disabled</span></span>|<span data-ttu-id="33432-154">已启用</span><span class="sxs-lookup"><span data-stu-id="33432-154">Enabled</span></span>|<span data-ttu-id="33432-155">已启用</span><span class="sxs-lookup"><span data-stu-id="33432-155">Enabled</span></span>|
|<span data-ttu-id="33432-156">SfBWithTeamsCollab 或 SfBOnly</span><span class="sxs-lookup"><span data-stu-id="33432-156">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="33432-157">已禁用</span><span class="sxs-lookup"><span data-stu-id="33432-157">Disabled</span></span>|<span data-ttu-id="33432-158">已禁用</span><span class="sxs-lookup"><span data-stu-id="33432-158">Disabled</span></span>|<span data-ttu-id="33432-159">已禁用</span><span class="sxs-lookup"><span data-stu-id="33432-159">Disabled</span></span>|<span data-ttu-id="33432-160">已禁用</span><span class="sxs-lookup"><span data-stu-id="33432-160">Disabled</span></span>|
||||||

<span data-ttu-id="33432-161">近期， `Grant-CsTeamsUpgradePolicy` cmdlet 将检查 TeamsMessagingPolicy、 TeamsCallingPolicy 和 TeamsMeetingPolicy，以确定是否将由 TeamsUpgradePolicy 取代这些设置，以及如果是这样中, 相应的设置的配置在 PowerShell 中提供的信息性消息。</span><span class="sxs-lookup"><span data-stu-id="33432-161">In the near future, the `Grant-CsTeamsUpgradePolicy` cmdlet will check the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings will be superceded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="33432-162">如上所述，不再需要设置这些其他策略设置。</span><span class="sxs-lookup"><span data-stu-id="33432-162">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="33432-163">下面是示例 PowerShell 警告如下所示：</span><span class="sxs-lookup"><span data-stu-id="33432-163">Below is an example of what the PowerShell warning  looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a><span data-ttu-id="33432-164">相关主题</span><span class="sxs-lookup"><span data-stu-id="33432-164">Related topics</span></span>

[<span data-ttu-id="33432-165">面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导</span><span class="sxs-lookup"><span data-stu-id="33432-165">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




