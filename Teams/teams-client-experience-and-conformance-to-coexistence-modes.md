---
title: Teams 客户端体验和共存模式的一致性
author: dearbeen
ms.author: bjwhalen
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: bjwhalen
description: 团队客户端体验和 comformance 到共存模式
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: bd81915739d9ad2087dec5b66595efd1c49e2c84
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2019
ms.locfileid: "30120889"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="93388-103">Teams 客户端体验和共存模式的一致性</span><span class="sxs-lookup"><span data-stu-id="93388-103">Teams client experience and conformance to coexistence modes</span></span>

> [!NOTE]
> <span data-ttu-id="93388-104">当用户在任何业务模式 （SfBOnly、 SfBWithTeamsCollab SfBWithTeamsCollabAndMeetings） Skype 中时，此页介绍团队客户端的行为重要即将发生变化。</span><span class="sxs-lookup"><span data-stu-id="93388-104">This page describes important upcoming changes in the behavior of Teams client when users are in any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).</span></span>


<span data-ttu-id="93388-105">共存模式旨在简单、 可预测体验的最终用户提供组织转换为从 for Business 的 Skype 向工作组。</span><span class="sxs-lookup"><span data-stu-id="93388-105">The purpose of co-existence modes is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="93388-106">将移动到团队的组织，TeamsOnly 模式是最终目标为每个用户，但并非所有用户都需要分配有 TeamsOnly （或任何其他模式） 在同一时间。</span><span class="sxs-lookup"><span data-stu-id="93388-106">For an organization moving to Teams, the TeamsOnly mode is the final destination for each user, though not all users need to be assigned TeamsOnly (or any other mode) at the same time.</span></span>  <span data-ttu-id="93388-107">之前达到 TeamsOnly 模式的用户，组织可以使用任何 Skype 业务模式 （SfBOnly SfBWithTeamsCollab、 SfBWithTeamsCollabAndMeetings） 以确保可预测 TeamsOnly 用户和那些尚未之间的通信。</span><span class="sxs-lookup"><span data-stu-id="93388-107">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) to ensure predictable communication between users who are TeamsOnly and those who aren’t yet.</span></span> 

<span data-ttu-id="93388-108">当用户在任何业务模式 Skype，所有传入的聊天和呼叫路由至业务客户端的用户的 Skype。</span><span class="sxs-lookup"><span data-stu-id="93388-108">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user’s Skype for Business client.</span></span> <span data-ttu-id="93388-109">若要避免最终用户混淆情况和确保正确路由，在客户端中的团队呼叫和聊天功能旨在时用户是在任何业务模式 Skype 禁用。</span><span class="sxs-lookup"><span data-stu-id="93388-109">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is intended to be disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="93388-110">同样，在工作组中计划会议是应将其显式禁用 SfBOnly 或 SfBWithTeamsCollab 模式，用户时，明确启用当用户处于 SfBWithTeamsCollabAndMeetings 模式。</span><span class="sxs-lookup"><span data-stu-id="93388-110">Similarly, meeting scheduling in Teams is intended to be explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>  <span data-ttu-id="93388-111">自动禁用的功能聊天和呼叫功能，以及启用/禁用会议安排基于模式立即启动到向点击客户推出。</span><span class="sxs-lookup"><span data-stu-id="93388-111">The functionality to automatically disable chat and calling functionality, as well as enable/disable meeting scheduling based on mode is now starting to rollout to TAP customers.</span></span>  

<span data-ttu-id="93388-112">此功能之前, Microsoft 的指南是通过消息、 呼叫和会议策略中设置相应的设置确保正确的用户体验。</span><span class="sxs-lookup"><span data-stu-id="93388-112">Prior to this functionality, Microsoft’s guidance was to ensure the proper user experience by setting the corresponding settings in Messaging, Calling and Meeting policies.</span></span> <span data-ttu-id="93388-113">但是，出现此，不正式强制执行，因为默认情况下用户在工作组客户端具有完全访问权限的所有功能，可能有某些用户保留访问部分或所有这些团队客户端，而不考虑其模式中的体验。</span><span class="sxs-lookup"><span data-stu-id="93388-113">However, there was no formal enforcement of this, and since users by default had full access to all functionality in the Teams client, some users may have retained access to some or all of these  experiences in the Teams client, regardless of their mode.</span></span>  <span data-ttu-id="93388-114">因此，滚动此功能，如某些用户可能会看到团队客户端中其体验中的更改的用户体验开始符合其模式。</span><span class="sxs-lookup"><span data-stu-id="93388-114">As a result, as this functionality rolls out, some users may see a change in their experience in the Teams client as the user experience begins to conform to their mode.</span></span>  <span data-ttu-id="93388-115">下表显示了新的行为：</span><span class="sxs-lookup"><span data-stu-id="93388-115">The table below shows the new behavior:</span></span>


|<span data-ttu-id="93388-116">用户的有效模式</span><span class="sxs-lookup"><span data-stu-id="93388-116">User's effective mode</span></span>|<span data-ttu-id="93388-117">在工作组客户端体验</span><span class="sxs-lookup"><span data-stu-id="93388-117">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="93388-118">业务模式的任何 Skype</span><span class="sxs-lookup"><span data-stu-id="93388-118">Any Skype for Business mode</span></span>|<span data-ttu-id="93388-119">禁用呼叫和聊天<sup>1</sup> 。</span><span class="sxs-lookup"><span data-stu-id="93388-119">Calling and Chat<sup>1</sup> are disabled.</span></span>|
|<span data-ttu-id="93388-120">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="93388-120">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="93388-121">会议安排位于</span><span class="sxs-lookup"><span data-stu-id="93388-121">Meeting scheduling is available</span></span>|
|<span data-ttu-id="93388-122">SfBWithTeamsCollab 或 SfBOnly<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="93388-122">SfBWithTeamsCollab or SfBOnly<sup>2</sup></span></span>|<span data-ttu-id="93388-123">会议安排不可用</span><span class="sxs-lookup"><span data-stu-id="93388-123">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="93388-124">**说明：**
<sup>1</sup>会议聊天是仍然可用。</span><span class="sxs-lookup"><span data-stu-id="93388-124">**Notes:**
<sup>1</sup> Meeting chat is still available.</span></span>
<span data-ttu-id="93388-125"><sup>2</sup>现在，SfBwithTeamsCollab 和 SfBOnly 的行为相同，但 SfBOnly 模式也禁用团队; 中的通道和文件功能的用途是但是，当前此功能允许在要禁用的团队中没有设置。</span><span class="sxs-lookup"><span data-stu-id="93388-125"><sup>2</sup> For now, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams; however, there is currently no setting that allows this functionality in Teams to be disabled.</span></span>


## <a name="how-organizations-can-prepare-for-automatic-ux-conformance-to-modes"></a><span data-ttu-id="93388-126">组织可以如何准备自动 UX 符合模式</span><span class="sxs-lookup"><span data-stu-id="93388-126">How organizations can prepare for automatic UX conformance to modes</span></span>

<span data-ttu-id="93388-127">之前推出此更改，组织可以实现此部分中所述使用其他策略的团队客户端中的所需的体验。</span><span class="sxs-lookup"><span data-stu-id="93388-127">Prior to this change rolling out, organizations can achieve the desired experience in the Teams client using additional policies as described in this section.</span></span> <span data-ttu-id="93388-128">这样可确保推出是无缝面向最终用户。</span><span class="sxs-lookup"><span data-stu-id="93388-128">This ensures the rollout is seamless for end users.</span></span> <span data-ttu-id="93388-129">请注意，一旦更改滚动，设置这些策略不需要。</span><span class="sxs-lookup"><span data-stu-id="93388-129">Note that once the change rolls out, setting these policies will NOT be required.</span></span>  <span data-ttu-id="93388-130">此外，不希望用户团队客户端中的，功能有所缩减的组织可以转向其用户群岛模式或 TeamsOnly 模式，但将影响以及路由。</span><span class="sxs-lookup"><span data-stu-id="93388-130">Alternatively, organizations that do not wish for users to have reduced functionality in the Teams client can shift their users to Islands mode or TeamsOnly mode, however that will impact routing as well.</span></span>

<span data-ttu-id="93388-131">若要手动配置最终用户体验，管理员使用的以下策略和设置：</span><span class="sxs-lookup"><span data-stu-id="93388-131">To manually configure the end user experience, administrators use the following policies and settings:</span></span>


|<span data-ttu-id="93388-132">**形式 （应用程序）**</span><span class="sxs-lookup"><span data-stu-id="93388-132">**Modality (App)**</span></span>|<span data-ttu-id="93388-133">**Policy.Setting**</span><span class="sxs-lookup"><span data-stu-id="93388-133">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="93388-134">聊天</span><span class="sxs-lookup"><span data-stu-id="93388-134">Chat</span></span>|<span data-ttu-id="93388-135">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="93388-135">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="93388-136">通话</span><span class="sxs-lookup"><span data-stu-id="93388-136">Calling</span></span>|<span data-ttu-id="93388-137">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="93388-137">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="93388-138">会议日程安排</span><span class="sxs-lookup"><span data-stu-id="93388-138">Meeting scheduling</span></span>|<span data-ttu-id="93388-139">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="93388-139">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="93388-140">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="93388-140">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||


<span data-ttu-id="93388-141">管理员应将每个这些设置设置为给定的模式的下列值：</span><span class="sxs-lookup"><span data-stu-id="93388-141">Administrators should set each of these settings to the following values for a given mode:</span></span>

|<span data-ttu-id="93388-142">模式</span><span class="sxs-lookup"><span data-stu-id="93388-142">Mode</span></span>|<span data-ttu-id="93388-143">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="93388-143">AllowUserChat</span></span>|<span data-ttu-id="93388-144">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="93388-144">AllowPrivateCalling</span></span>|<span data-ttu-id="93388-145">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="93388-145">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="93388-146">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="93388-146">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="93388-147">TeamsOnly 或群岛</span><span class="sxs-lookup"><span data-stu-id="93388-147">TeamsOnly or Islands</span></span>|<span data-ttu-id="93388-148">已启用</span><span class="sxs-lookup"><span data-stu-id="93388-148">Enabled</span></span>|<span data-ttu-id="93388-149">已启用</span><span class="sxs-lookup"><span data-stu-id="93388-149">Enabled</span></span>|<span data-ttu-id="93388-150">已启用</span><span class="sxs-lookup"><span data-stu-id="93388-150">Enabled</span></span>|<span data-ttu-id="93388-151">已启用</span><span class="sxs-lookup"><span data-stu-id="93388-151">Enabled</span></span>|
|<span data-ttu-id="93388-152">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="93388-152">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="93388-153">已禁用</span><span class="sxs-lookup"><span data-stu-id="93388-153">Disabled</span></span>|<span data-ttu-id="93388-154">已禁用</span><span class="sxs-lookup"><span data-stu-id="93388-154">Disabled</span></span>|<span data-ttu-id="93388-155">已启用</span><span class="sxs-lookup"><span data-stu-id="93388-155">Enabled</span></span>|<span data-ttu-id="93388-156">已启用</span><span class="sxs-lookup"><span data-stu-id="93388-156">Enabled</span></span>|
|<span data-ttu-id="93388-157">SfBWithTeamsCollab 或 SfBOnly</span><span class="sxs-lookup"><span data-stu-id="93388-157">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="93388-158">已禁用</span><span class="sxs-lookup"><span data-stu-id="93388-158">Disabled</span></span>|<span data-ttu-id="93388-159">已禁用</span><span class="sxs-lookup"><span data-stu-id="93388-159">Disabled</span></span>|<span data-ttu-id="93388-160">已禁用</span><span class="sxs-lookup"><span data-stu-id="93388-160">Disabled</span></span>|<span data-ttu-id="93388-161">已禁用</span><span class="sxs-lookup"><span data-stu-id="93388-161">Disabled</span></span>|
||||||

<span data-ttu-id="93388-162">自动根据模式，用户体验的一致性声明推出之前`Grant-CsTeamsUpgradePolicy`cmdlet 检查 TeamsMessagingPolicy、 TeamsCallingPolicy 和 TeamsMeetingPolicy，以确定它们是否中相应的设置的配置设置可以与指定模式兼容。</span><span class="sxs-lookup"><span data-stu-id="93388-162">Prior to the rollout of automatic conformance of the user experience based on modes, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if these settings are compatible with the specified mode.</span></span> <span data-ttu-id="93388-163">如果任何未正确配置，则授予会成功，但警告将提供在 PowerShell 中指示的特定设置的配置不正确。</span><span class="sxs-lookup"><span data-stu-id="93388-163">If any are not configured properly, the grant will succeed but a warning will be provided in PowerShell indicating which specific settings are not configured properly.</span></span> <span data-ttu-id="93388-164">下面是 PowerShell 警告可能外观的示例：</span><span class="sxs-lookup"><span data-stu-id="93388-164">Below is an example of what the PowerShell warning could look like:</span></span>


`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

<span data-ttu-id="93388-165">*警告: user1@contoso.com' 用户当前已启用的有效策略值： AllowUserChat AllowPrivateCalling、 AllowPrivateMeetingScheduling、 AllowChannelMeetingScheduling。Near 术语，当使用模式授予 TeamsUpgradePolicy = SfBWithTeamsCollab 给用户，您必须单独还分配策略，以确保用户具有有效策略禁用值： AllowUserChat、 AllowPrivateCalling，AllowPrivateMeetingScheduling，AllowChannelMeetingScheduling。将来，功能也会自动授予 TeamsUpgradePolicy。*</span><span class="sxs-lookup"><span data-stu-id="93388-165">*WARNING: The user 'user1@contoso.com' currently has effective policy enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling. In the near term, when granting TeamsUpgradePolicy with mode=SfBWithTeamsCollab to a user, you must also separately assign policy to ensure the user has effective policy disabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling. In the future, the capability will automatically honor TeamsUpgradePolicy.*</span></span>

<span data-ttu-id="93388-166">时看到这样的警告，管理员随后应更新指示的策略中团队提供兼容的最终用户体验。</span><span class="sxs-lookup"><span data-stu-id="93388-166">Upon seeing such a warning, the administrator should subsequently update the indicated policies to deliver a compatible end user experience in Teams.</span></span> <span data-ttu-id="93388-167">如果管理员决定不执行任何操作由于警告，用户仍可以访问聊天，呼叫和/或会议中团队的日程安排功能，具体取决于 TeamsMessagingPolicy、 TeamsCallingPolicy 和 TeamsMeetingPolicy 的值可能会造成的混乱的最终用户体验。</span><span class="sxs-lookup"><span data-stu-id="93388-167">If the administrator decides to take no action as a result of the warning, users may still have access to chat, calling, and/or meeting scheduling capabilities in Teams depending on the values of TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy, which may result in a confusing end user experience.</span></span>

<span data-ttu-id="93388-168">可用自动根据 TeamsUpgradePolicy 模式的团队客户端体验的一致性声明后，它将不再需要将这些策略设置。</span><span class="sxs-lookup"><span data-stu-id="93388-168">Once automatic conformance of the Teams client experience based on TeamsUpgradePolicy mode is available, it will no longer be necessary to set these policies.</span></span> <span data-ttu-id="93388-169">TeamsUpgradePolicy 模式的值将优先于这些特定设置的值。</span><span class="sxs-lookup"><span data-stu-id="93388-169">The value of TeamsUpgradePolicy mode will take precedence over the values of these specific settings.</span></span> <span data-ttu-id="93388-170">自动一致性声明被通过解析策略策略基础结构。</span><span class="sxs-lookup"><span data-stu-id="93388-170">Automatic conformance is achieved during policy resolution by the policy infrastructure.</span></span> <span data-ttu-id="93388-171">在发生冲突的不同设置的基于模式的行为将 win 通过 AllowUserChat、 AllowPrivateCalling、 AllowPrivateMeetingScheduling 和 AllowChannelMeetingScheduling 的值。</span><span class="sxs-lookup"><span data-stu-id="93388-171">In case of conflict of the different settings, the behavior based on mode will win over the values of AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling and AllowChannelMeetingScheduling.</span></span> <span data-ttu-id="93388-172">自动一致性声明是传递之后，将更新 PowerShell 警告，告知客户端体验将自动应用，而不考虑 TeamsMessagingPolicy、 TeamsCallingPolicy 和 TeamsMeetingPolicy 的任何值的管理员。</span><span class="sxs-lookup"><span data-stu-id="93388-172">Once automatic conformance is delivered, the PowerShell warnings will be updated to inform the administrator that the client experience will automatically apply, despite any values of TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy.</span></span>







