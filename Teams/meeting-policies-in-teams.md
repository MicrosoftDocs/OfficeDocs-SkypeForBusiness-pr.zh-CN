---
title: 管理会议策略
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.overview
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- ms.teamsadmincenter.meetingpolicies.contentsharing
- ms.teamsadmincenter.meetingpolicies.general
- ms.teamsadmincenter.meetingpolicies.participantandguests
- seo-marvel-apr2020
description: 了解如何在 Teams 中管理会议策略设置，并使用它们来控制可供会议参与者用于用户安排的会议的功能。
ms.openlocfilehash: 5b3b2e3975906e130d81804c2db51973bf50521c
ms.sourcegitcommit: 54140f6f8f2279a0eaf2e9c79699d6cff306791c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/03/2021
ms.locfileid: "50408198"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="41b3c-103">在 Teams 中管理会议策略</span><span class="sxs-lookup"><span data-stu-id="41b3c-103">Manage meeting policies in Teams</span></span>

::: zone target="docs"
<span data-ttu-id="41b3c-104">使用会议策略控制可供会议参与者用于组织中用户安排的会议的功能。</span><span class="sxs-lookup"><span data-stu-id="41b3c-104">Use meeting policies to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="41b3c-105">可以使用全局策略 (组织范围的默认) 自动创建或创建和分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-105">You can use the global (Org-wide default) policy that's automatically created or create and assign custom policies.</span></span> <span data-ttu-id="41b3c-106">在 Microsoft Teams 管理中心或 [PowerShell](teams-powershell-overview.md)中管理会议策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-106">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="41b3c-107">有关使用角色管理会议演示者和与会者的权限的信息，请参阅 [Teams 会议的角色](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)。</span><span class="sxs-lookup"><span data-stu-id="41b3c-107">For information about using roles to manage the permissions of meeting presenters and attendees, see [Roles in a Teams meeting](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).</span></span>

<span data-ttu-id="41b3c-108">您可以通过以下方式实施策略，这会影响用户在会议启动、会议期间或会议后的会议体验。</span><span class="sxs-lookup"><span data-stu-id="41b3c-108">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="41b3c-109">实现类型</span><span class="sxs-lookup"><span data-stu-id="41b3c-109">Implementation type</span></span>  |<span data-ttu-id="41b3c-110">说明</span><span class="sxs-lookup"><span data-stu-id="41b3c-110">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="41b3c-111">按组织者</span><span class="sxs-lookup"><span data-stu-id="41b3c-111">Per-organizer</span></span>    |<span data-ttu-id="41b3c-112">实现按组织者的策略时，所有会议参与者将继承组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-112">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="41b3c-113">例如，自动允许 **人员** 是按组织者的策略，控制用户是直接加入会议，还是等待分配策略的用户安排的会议在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="41b3c-113">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="41b3c-114">按用户</span><span class="sxs-lookup"><span data-stu-id="41b3c-114">Per-user</span></span>    |<span data-ttu-id="41b3c-115">实现每用户策略时，仅按用户策略适用于限制组织者和/或会议参与者的某些功能。</span><span class="sxs-lookup"><span data-stu-id="41b3c-115">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="41b3c-116">例如， **频道中的"现在允许** 开会"是按用户的策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-116">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="41b3c-117">按组织者和按用户</span><span class="sxs-lookup"><span data-stu-id="41b3c-117">Per-organizer and per-user</span></span>     |<span data-ttu-id="41b3c-118">实施按组织者和按用户策略的组合时，某些功能会基于会议参与者的策略和组织者的策略进行限制。</span><span class="sxs-lookup"><span data-stu-id="41b3c-118">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="41b3c-119">例如， **允许云录制** 是按组织者和按用户的策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-119">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="41b3c-120">打开此设置以允许用户开始和停止录制。</span><span class="sxs-lookup"><span data-stu-id="41b3c-120">Turn on this setting to allow users to start and stop a recording.</span></span>

<span data-ttu-id="41b3c-121">可以编辑全局策略中的设置，也可以创建和分配一个或多个自定义策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-121">You can edit the settings in the global policy or create and assign one or more custom policies.</span></span> <span data-ttu-id="41b3c-122">除非创建并分配自定义策略，否则用户将获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-122">Users will get the global policy unless you create and assign a custom policy.</span></span>

> [!NOTE]
> <span data-ttu-id="41b3c-123">如果用户启用了音频会议许可证或允许用户进行音频会议，则会议详细信息按钮将可用，否则会议详细信息将不可用。</span><span class="sxs-lookup"><span data-stu-id="41b3c-123">Meeting details button will be available if a user has the audio conference licenses enabled or the user is allow for audio conferencing, if not, the meeting details will not be available.</span></span>

## <a name="create-a-custom-meeting-policy"></a><span data-ttu-id="41b3c-124">创建自定义会议策略</span><span class="sxs-lookup"><span data-stu-id="41b3c-124">Create a custom meeting policy</span></span>

1. <span data-ttu-id="41b3c-125">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"会议**  >  **会议策略"。**</span><span class="sxs-lookup"><span data-stu-id="41b3c-125">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="41b3c-126">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="41b3c-126">Select **Add**.</span></span>
3. <span data-ttu-id="41b3c-127">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="41b3c-127">Enter a name and description for the policy.</span></span> <span data-ttu-id="41b3c-128">名称不能包含特殊字符或超过 64 个字符。</span><span class="sxs-lookup"><span data-stu-id="41b3c-128">The name can't contain special characters or be longer than 64 characters.</span></span>
4. <span data-ttu-id="41b3c-129">选择想要的设置。</span><span class="sxs-lookup"><span data-stu-id="41b3c-129">Choose the settings that you want.</span></span>
5. <span data-ttu-id="41b3c-130">选择 **"保存"。**</span><span class="sxs-lookup"><span data-stu-id="41b3c-130">Select **Save**.</span></span>

<span data-ttu-id="41b3c-131">例如，假设你有一组用户并且你想要限制这组用户的会议所需的带宽量。</span><span class="sxs-lookup"><span data-stu-id="41b3c-131">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="41b3c-132">你要创建新的自定义策略并命名为“带宽限制”，然后禁用以下设置：</span><span class="sxs-lookup"><span data-stu-id="41b3c-132">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="41b3c-133">在“音频和视频”中：</span><span class="sxs-lookup"><span data-stu-id="41b3c-133">Under **Audio & video**:</span></span>

- <span data-ttu-id="41b3c-134">禁用“允许云录制”。</span><span class="sxs-lookup"><span data-stu-id="41b3c-134">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="41b3c-135">禁用“允许 IP 视频”。</span><span class="sxs-lookup"><span data-stu-id="41b3c-135">Turn off Allow IP video.</span></span>

<span data-ttu-id="41b3c-136">在“内容共享”中：</span><span class="sxs-lookup"><span data-stu-id="41b3c-136">Under **Content sharing**:</span></span>

- <span data-ttu-id="41b3c-137">禁用屏幕共享模式。</span><span class="sxs-lookup"><span data-stu-id="41b3c-137">Disable screen sharing mode.</span></span>
- <span data-ttu-id="41b3c-138">禁用“允许白板”。</span><span class="sxs-lookup"><span data-stu-id="41b3c-138">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="41b3c-139">禁用“允许共享笔记”。</span><span class="sxs-lookup"><span data-stu-id="41b3c-139">Turn off Allow shared notes.</span></span>

<span data-ttu-id="41b3c-140">然后将此策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="41b3c-140">Then assign the policy to the users.</span></span>

## <a name="edit-a-meeting-policy"></a><span data-ttu-id="41b3c-141">编辑会议策略</span><span class="sxs-lookup"><span data-stu-id="41b3c-141">Edit a meeting policy</span></span>

<span data-ttu-id="41b3c-142">可以编辑全局策略和创建的任何自定义策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-142">You can edit the global policy and any custom policies that you create.</span></span>

1. <span data-ttu-id="41b3c-143">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"会议**  >  **会议策略"。**</span><span class="sxs-lookup"><span data-stu-id="41b3c-143">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="41b3c-144">单击策略名称左侧选择策略，然后选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="41b3c-144">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>
3. <span data-ttu-id="41b3c-145">在此处根据需要进行更改。</span><span class="sxs-lookup"><span data-stu-id="41b3c-145">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="41b3c-146">选择 **"保存"。**</span><span class="sxs-lookup"><span data-stu-id="41b3c-146">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="41b3c-147">一次只能为用户分配一个会议策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-147">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="41b3c-148">将会议策略分配给用户</span><span class="sxs-lookup"><span data-stu-id="41b3c-148">Assign a meeting policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> <span data-ttu-id="41b3c-149">如果将用户分配到某个策略，则不能删除该策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-149">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="41b3c-150">必须先将不同的策略分配给所有受影响的用户，然后可以删除原始策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-150">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="41b3c-151">会议策略设置</span><span class="sxs-lookup"><span data-stu-id="41b3c-151">Meeting policy settings</span></span>

<span data-ttu-id="41b3c-152">当您在"会议策略"页面上选择现有策略或选择"添加"以添加新策略时，您可以配置以下功能的设置。</span><span class="sxs-lookup"><span data-stu-id="41b3c-152">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following features.</span></span>

- [<span data-ttu-id="41b3c-153">常规</span><span class="sxs-lookup"><span data-stu-id="41b3c-153">General</span></span>](#meeting-policy-settings---general)
- [<span data-ttu-id="41b3c-154">音频&视频</span><span class="sxs-lookup"><span data-stu-id="41b3c-154">Audio & video</span></span>](#meeting-policy-settings---audio--video)
- [<span data-ttu-id="41b3c-155">内容共享</span><span class="sxs-lookup"><span data-stu-id="41b3c-155">Content sharing</span></span>](#meeting-policy-settings---content-sharing)
- [<span data-ttu-id="41b3c-156">来宾&参与者</span><span class="sxs-lookup"><span data-stu-id="41b3c-156">Participants & guests</span></span>](#meeting-policy-settings---participants--guests)

::: zone-end

<span data-ttu-id="41b3c-157"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="41b3c-157"><a name="bkgeneral"> </a></span></span>

## <a name="meeting-policy-settings---general"></a><span data-ttu-id="41b3c-158">会议策略设置 - 常规</span><span class="sxs-lookup"><span data-stu-id="41b3c-158">Meeting policy settings - General</span></span>

- [<span data-ttu-id="41b3c-159">在频道中允许"现在开会"</span><span class="sxs-lookup"><span data-stu-id="41b3c-159">Allow Meet now in channels</span></span>](#allow-meet-now-in-channels)
- [<span data-ttu-id="41b3c-160">允许 Outlook 加载项</span><span class="sxs-lookup"><span data-stu-id="41b3c-160">Allow the Outlook add-in</span></span>](#allow-the-outlook-add-in)
- [<span data-ttu-id="41b3c-161">允许频道会议安排</span><span class="sxs-lookup"><span data-stu-id="41b3c-161">Allow channel meeting scheduling</span></span>](#allow-channel-meeting-scheduling)
- [<span data-ttu-id="41b3c-162">允许安排私人会议</span><span class="sxs-lookup"><span data-stu-id="41b3c-162">Allow scheduling private meetings</span></span>](#allow-scheduling-private-meetings)
- [<span data-ttu-id="41b3c-163">允许现在在私人会议中召开会议</span><span class="sxs-lookup"><span data-stu-id="41b3c-163">Allow Meet now in private meetings</span></span>](#allow-meet-now-in-private-meetings)

### <a name="allow-meet-now-in-channels"></a><span data-ttu-id="41b3c-164">在频道中允许"现在开会"</span><span class="sxs-lookup"><span data-stu-id="41b3c-164">Allow Meet now in channels</span></span>

<span data-ttu-id="41b3c-165">**"现在允许** 开会"是按用户的策略，在会议启动之前适用。</span><span class="sxs-lookup"><span data-stu-id="41b3c-165">Allow **Meet now** is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="41b3c-166">此设置控制用户是否可以在 Teams 频道中启动计划外会议。</span><span class="sxs-lookup"><span data-stu-id="41b3c-166">This setting controls whether a user can start an unplanned meeting in a Teams channel.</span></span> <span data-ttu-id="41b3c-167">如果启用此设置，用户可以选择"会议"按钮以启动计划外会议或在频道中安排会议。</span><span class="sxs-lookup"><span data-stu-id="41b3c-167">If you turn on this setting, users can select the **Meet** button to start an unplanned meeting or schedule a meeting in the channel.</span></span> <span data-ttu-id="41b3c-168">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="41b3c-168">The default value is True.</span></span>

![显示消息下方的"现在开会"图标的屏幕截图](media/meeting-policies-meet-now.png)

### <a name="allow-the-outlook-add-in"></a><span data-ttu-id="41b3c-170">允许 Outlook 加载项</span><span class="sxs-lookup"><span data-stu-id="41b3c-170">Allow the Outlook add-in</span></span>

<span data-ttu-id="41b3c-171">这是按用户的策略，在会议启动之前适用。</span><span class="sxs-lookup"><span data-stu-id="41b3c-171">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="41b3c-172">此设置控制是否可以在 Outlook 中安排 Teams 会议 (Windows、Mac、Web 和移动) 。</span><span class="sxs-lookup"><span data-stu-id="41b3c-172">This setting controls whether Teams meetings can be scheduled from within Outlook (Windows, Mac, web, and mobile).</span></span>

![显示安排新会议的能力的屏幕截图](media/meeting-policies-outlook-add-in.png)

<span data-ttu-id="41b3c-174">如果将其关闭，用户将无法进行计划。</span><span class="sxs-lookup"><span data-stu-id="41b3c-174">If you turn this off, users are unable to schedule.</span></span> <span data-ttu-id="41b3c-175">Teams 会议：在 Outlook 中创建新会议时。</span><span class="sxs-lookup"><span data-stu-id="41b3c-175">Teams meetings when they create a new meeting in Outlook.</span></span> <span data-ttu-id="41b3c-176">例如，在 Outlook on Windows 中，" **新建 Teams** 会议"选项不会显示在功能区中。</span><span class="sxs-lookup"><span data-stu-id="41b3c-176">For example, in Outlook on Windows, the **New Teams Meeting** option won't show up in the ribbon.</span></span>

### <a name="allow-channel-meeting-scheduling"></a><span data-ttu-id="41b3c-177">允许频道会议安排</span><span class="sxs-lookup"><span data-stu-id="41b3c-177">Allow channel meeting scheduling</span></span>

<span data-ttu-id="41b3c-178">使用现有的 AllowChannelMeetingScheduling 策略来控制可在团队频道日历上创建的事件类型。</span><span class="sxs-lookup"><span data-stu-id="41b3c-178">Use the existing AllowChannelMeetingScheduling policy to control the types of events that can be created on the team channel calendars.</span></span> <span data-ttu-id="41b3c-179">这是按用户的策略，在会议启动之前适用。</span><span class="sxs-lookup"><span data-stu-id="41b3c-179">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="41b3c-180">此设置控制用户是否可以在 Teams 频道中安排会议。</span><span class="sxs-lookup"><span data-stu-id="41b3c-180">This setting controls whether users can schedule a meeting in a Teams channel.</span></span> <span data-ttu-id="41b3c-181">默认情况下，此设置已打开。</span><span class="sxs-lookup"><span data-stu-id="41b3c-181">By default, this setting is turned on.</span></span>

<span data-ttu-id="41b3c-182">如果此策略已关闭，用户无法创建新的频道会议。</span><span class="sxs-lookup"><span data-stu-id="41b3c-182">If this policy is turned off, users can't create new channel meetings.</span></span> <span data-ttu-id="41b3c-183">但是，活动的组织者可以编辑现有频道会议。</span><span class="sxs-lookup"><span data-stu-id="41b3c-183">However, existing channel meetings can be edited by the organizer of the event.</span></span>

<span data-ttu-id="41b3c-184">计划会议将被禁用。</span><span class="sxs-lookup"><span data-stu-id="41b3c-184">Schedule a meeting will be disabled.</span></span>

 ![显示 Teams 中的"安排会议"选项的屏幕截图](media/schedule-meeting-option.png)

<span data-ttu-id="41b3c-186">频道选择被禁用。</span><span class="sxs-lookup"><span data-stu-id="41b3c-186">Channel selection is disabled.</span></span>

![用于选择要安排会议的频道的日历选项。](media/meeting-policies-select-a-channel-to-meet-in.png)

<span data-ttu-id="41b3c-188">在频道帖子页面中，将禁用以下功能：</span><span class="sxs-lookup"><span data-stu-id="41b3c-188">In the channel posts page, the following features will be disabled:</span></span>

- <span data-ttu-id="41b3c-189">**频道答复撰写** 框上的"安排会议"按钮。</span><span class="sxs-lookup"><span data-stu-id="41b3c-189">**Schedule a meeting** button on the channel reply compose box.</span></span>
  <span data-ttu-id="41b3c-190">![安排会议按钮答复撰写框](media/schedule-meeting-disabled-in-chat2.png)</span><span class="sxs-lookup"><span data-stu-id="41b3c-190">![schedule a meeting button reply compose box](media/schedule-meeting-disabled-in-chat2.png)</span></span>
  
- <span data-ttu-id="41b3c-191">**频道标题上的** "安排会议"按钮。</span><span class="sxs-lookup"><span data-stu-id="41b3c-191">**Schedule a meeting** button on the channel header.</span></span>
  <span data-ttu-id="41b3c-192">![频道标题中的"安排会议"按钮](media/schedule-now-in-header.png)</span><span class="sxs-lookup"><span data-stu-id="41b3c-192">![schedule a meeting button in the channel header](media/schedule-now-in-header.png)</span></span>

<span data-ttu-id="41b3c-193">在频道日历中：</span><span class="sxs-lookup"><span data-stu-id="41b3c-193">In the channel calendar:</span></span>

- <span data-ttu-id="41b3c-194">**频道日历标题** 上的"添加新事件"按钮将被禁用。</span><span class="sxs-lookup"><span data-stu-id="41b3c-194">**Add new event** button on channel calendar header will be disabled.</span></span>
  <span data-ttu-id="41b3c-195">![通道日历标题上的按钮已禁用](media/add-new-event-disabled.png)</span><span class="sxs-lookup"><span data-stu-id="41b3c-195">![button on channel calendar header disabled](media/add-new-event-disabled.png)</span></span>

- <span data-ttu-id="41b3c-196">用户无法拖动并选择频道日历上的一个时间块来创建频道会议。</span><span class="sxs-lookup"><span data-stu-id="41b3c-196">Users won't be able to drag and select a time block on the channel calendar to create a channel meeting.</span></span>

- <span data-ttu-id="41b3c-197">用户不能使用键盘快捷方式在频道日历上创建会议。</span><span class="sxs-lookup"><span data-stu-id="41b3c-197">Users can't use Keyboard shortcuts to create a meeting on the channel calendar.</span></span>

<span data-ttu-id="41b3c-198">在管理中心中：</span><span class="sxs-lookup"><span data-stu-id="41b3c-198">In the admin center:</span></span>

<span data-ttu-id="41b3c-199">通道日历应用会显示在应用权限策略页面的 **"Microsoft** 应用"部分。</span><span class="sxs-lookup"><span data-stu-id="41b3c-199">The channel calendar app will show up in the **Microsoft apps** section on the app permission policies page.</span></span>

 ![Teams 管理中心的应用权限策略](media/manage-microsoft-apps-policy.png)

### <a name="allow-scheduling-private-meetings"></a><span data-ttu-id="41b3c-201">允许安排私人会议</span><span class="sxs-lookup"><span data-stu-id="41b3c-201">Allow scheduling private meetings</span></span>

<span data-ttu-id="41b3c-202">这是按用户的策略，在会议启动之前适用。</span><span class="sxs-lookup"><span data-stu-id="41b3c-202">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="41b3c-203">此设置控制用户是否可以在 Teams 中安排私人会议。</span><span class="sxs-lookup"><span data-stu-id="41b3c-203">This setting controls whether users can schedule private meetings in Teams.</span></span> <span data-ttu-id="41b3c-204">会议未发布到团队中的频道时是私密的。</span><span class="sxs-lookup"><span data-stu-id="41b3c-204">A meeting is private when it's not published to a channel in a team.</span></span>

<span data-ttu-id="41b3c-205">如果关闭"允许 **安排** 私人会议和允许频道会议计划"，则 Teams中的用户禁用"添加所需与会者"和"添加频道"选项。 </span><span class="sxs-lookup"><span data-stu-id="41b3c-205">If you turn off **Allow scheduling private meetings** and **Allow channel meeting scheduling**,  the **Add required attendees** and **Add channel** options are disabled for users in Teams.</span></span> <span data-ttu-id="41b3c-206">默认情况下，此设置已打开。</span><span class="sxs-lookup"><span data-stu-id="41b3c-206">By default, this setting is turned on.</span></span>

### <a name="allow-meet-now-in-private-meetings"></a><span data-ttu-id="41b3c-207">允许现在在私人会议中召开会议</span><span class="sxs-lookup"><span data-stu-id="41b3c-207">Allow Meet now in private meetings</span></span>

<span data-ttu-id="41b3c-208">这是按用户的策略，在会议启动之前适用。</span><span class="sxs-lookup"><span data-stu-id="41b3c-208">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="41b3c-209">此设置控制用户是否可以启动计划外私人会议。</span><span class="sxs-lookup"><span data-stu-id="41b3c-209">This setting controls whether a user can start an unplanned private meeting.</span></span> <span data-ttu-id="41b3c-210">默认情况下，此设置已打开。</span><span class="sxs-lookup"><span data-stu-id="41b3c-210">By default, this setting is turned on.</span></span>

<span data-ttu-id="41b3c-211"><a name="bkaudioandvideo"> </a></span><span class="sxs-lookup"><span data-stu-id="41b3c-211"><a name="bkaudioandvideo"> </a></span></span>

## <a name="meeting-policy-settings---audio--video"></a><span data-ttu-id="41b3c-212">会议策略设置 - 音频&视频</span><span class="sxs-lookup"><span data-stu-id="41b3c-212">Meeting policy settings - Audio & video</span></span>

- [<span data-ttu-id="41b3c-213">允许听录</span><span class="sxs-lookup"><span data-stu-id="41b3c-213">Allow transcription</span></span>](#allow-transcription)
- [<span data-ttu-id="41b3c-214">允许云录制</span><span class="sxs-lookup"><span data-stu-id="41b3c-214">Allow cloud recording</span></span>](#allow-cloud-recording)
- [<span data-ttu-id="41b3c-215">IP 音频模式</span><span class="sxs-lookup"><span data-stu-id="41b3c-215">Mode for IP audio</span></span>](#mode-for-ip-audio)
- [<span data-ttu-id="41b3c-216">IP 视频的模式</span><span class="sxs-lookup"><span data-stu-id="41b3c-216">Mode for IP video</span></span>](#mode-for-ip-video)
- [<span data-ttu-id="41b3c-217">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="41b3c-217">Allow IP video</span></span>](#allow-ip-video)
- [<span data-ttu-id="41b3c-218">媒体比特率 (Kbs) </span><span class="sxs-lookup"><span data-stu-id="41b3c-218">Media bit rate (Kbs)</span></span>](#media-bit-rate-kbs)

### <a name="allow-transcription"></a><span data-ttu-id="41b3c-219">允许听录</span><span class="sxs-lookup"><span data-stu-id="41b3c-219">Allow transcription</span></span>

<span data-ttu-id="41b3c-220">这是按组织者和按用户的策略的组合。</span><span class="sxs-lookup"><span data-stu-id="41b3c-220">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="41b3c-221">此设置控制在播放会议录制期间字幕和听录功能是否可用。</span><span class="sxs-lookup"><span data-stu-id="41b3c-221">This setting controls whether captions and transcription features are available during playback of meeting recordings.</span></span> <span data-ttu-id="41b3c-222">如果将其关闭，则播放会议录制期间，"搜索"和"抄送"选项将不可用。</span><span class="sxs-lookup"><span data-stu-id="41b3c-222">If you turn this off, the **Search** and **CC** options won't be available during playback of a meeting recording.</span></span> <span data-ttu-id="41b3c-223">开始录制的人需要启用此设置，以便录制还包括听录。</span><span class="sxs-lookup"><span data-stu-id="41b3c-223">The person who started the recording needs this setting turned on so that the recording also includes transcription.</span></span>

<span data-ttu-id="41b3c-224">录制的会议听录功能目前仅支持 Teams 中语言设置为英语和会议中使用英语的用户。</span><span class="sxs-lookup"><span data-stu-id="41b3c-224">Transcription for recorded meetings is currently only supported for users who have the language in Teams set to English and when English is spoken in the meeting.</span></span>

![会议中的听录选项](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a><span data-ttu-id="41b3c-226">允许云录制</span><span class="sxs-lookup"><span data-stu-id="41b3c-226">Allow cloud recording</span></span>

<span data-ttu-id="41b3c-227">这由每个用户的策略控制。</span><span class="sxs-lookup"><span data-stu-id="41b3c-227">This is controlled at a per-user policy.</span></span> <span data-ttu-id="41b3c-228">此设置控制用户是否可以录制。</span><span class="sxs-lookup"><span data-stu-id="41b3c-228">This setting controls whether a user can record.</span></span> <span data-ttu-id="41b3c-229">如果会议组织者或另一个会议参与者的特定策略设置已打开，并且他们是与组织者相同的组织中经过身份验证的用户，则录制内容可以由会议组织者或其他会议参与者启动。</span><span class="sxs-lookup"><span data-stu-id="41b3c-229">The recording can be started by the meeting organizer or by another meeting participant if their specific policy setting is turned on and if they're an authenticated user from the same organization as the organizer.</span></span>

<span data-ttu-id="41b3c-230">组织外部的用户（例如联合用户和匿名用户）无法开始录制。</span><span class="sxs-lookup"><span data-stu-id="41b3c-230">People outside your organization, such as federated and anonymous users, can't start the recording.</span></span> <span data-ttu-id="41b3c-231">来宾用户无法启动或停止录制。</span><span class="sxs-lookup"><span data-stu-id="41b3c-231">Guest users can't start or stop the recording.</span></span>

![录制选项](media/meeting-policies-recording.png)

<span data-ttu-id="41b3c-233">让我们看看以下示例。</span><span class="sxs-lookup"><span data-stu-id="41b3c-233">Let's look at the following example.</span></span>

|<span data-ttu-id="41b3c-234">用户</span><span class="sxs-lookup"><span data-stu-id="41b3c-234">User</span></span> |<span data-ttu-id="41b3c-235">会议策略</span><span class="sxs-lookup"><span data-stu-id="41b3c-235">Meeting policy</span></span>  |<span data-ttu-id="41b3c-236">允许云录制</span><span class="sxs-lookup"><span data-stu-id="41b3c-236">Allow cloud recording</span></span> |
|---------|---------|---------|
|<span data-ttu-id="41b3c-237">Daniela</span><span class="sxs-lookup"><span data-stu-id="41b3c-237">Daniela</span></span> | <span data-ttu-id="41b3c-238">全局</span><span class="sxs-lookup"><span data-stu-id="41b3c-238">Global</span></span>   | <span data-ttu-id="41b3c-239">关</span><span class="sxs-lookup"><span data-stu-id="41b3c-239">Off</span></span> |
|<span data-ttu-id="41b3c-240">阿兰达</span><span class="sxs-lookup"><span data-stu-id="41b3c-240">Amanda</span></span> | <span data-ttu-id="41b3c-241">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="41b3c-241">Location1MeetingPolicy</span></span> | <span data-ttu-id="41b3c-242">开</span><span class="sxs-lookup"><span data-stu-id="41b3c-242">On</span></span>|
|<span data-ttu-id="41b3c-243">John (外部用户) </span><span class="sxs-lookup"><span data-stu-id="41b3c-243">John (external user)</span></span> | <span data-ttu-id="41b3c-244">不适用</span><span class="sxs-lookup"><span data-stu-id="41b3c-244">Not applicable</span></span> | <span data-ttu-id="41b3c-245">不适用</span><span class="sxs-lookup"><span data-stu-id="41b3c-245">Not applicable</span></span>|

<span data-ttu-id="41b3c-246">Daniela（即使她是组织者）无法录制，因为策略已设置为关闭。</span><span class="sxs-lookup"><span data-stu-id="41b3c-246">Daniela, even if she were the organizer, can't record because her policy is set to off.</span></span> <span data-ttu-id="41b3c-247">已启用策略设置的 Amanda 可以录制会议，即使是由 Daniela 组织的会议。</span><span class="sxs-lookup"><span data-stu-id="41b3c-247">Amanda, who has the policy setting enabled, can record meetings, even those organized by Daniela.</span></span> <span data-ttu-id="41b3c-248">如果 Amanda 要组织会议，她将能够录制该会议。</span><span class="sxs-lookup"><span data-stu-id="41b3c-248">If Amanda were to organize a meeting, she'll be able to record that meeting.</span></span> <span data-ttu-id="41b3c-249">但是，禁用了策略设置的 Daniela 和外部用户的 John 无法录制该会议。</span><span class="sxs-lookup"><span data-stu-id="41b3c-249">However, Daniela, who has the policy setting disabled and John who is an external user, can't record that meeting.</span></span>

<span data-ttu-id="41b3c-250">若要详细了解云会议录制，请参阅 [Teams 云会议录制](cloud-recording.md)。</span><span class="sxs-lookup"><span data-stu-id="41b3c-250">To learn more about cloud meeting recording, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

### <a name="mode-for-ip-audio"></a><span data-ttu-id="41b3c-251">IP 音频模式</span><span class="sxs-lookup"><span data-stu-id="41b3c-251">Mode for IP audio</span></span>

<span data-ttu-id="41b3c-252">这是按用户的策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-252">This is a per-user policy.</span></span> <span data-ttu-id="41b3c-253">此设置控制是否可以在会议和群组通话中打开音频。</span><span class="sxs-lookup"><span data-stu-id="41b3c-253">This setting controls whether audio can be turned on in meetings and group calls.</span></span> <span data-ttu-id="41b3c-254">下面是此设置的值。</span><span class="sxs-lookup"><span data-stu-id="41b3c-254">Here are the values for this setting.</span></span>

|<span data-ttu-id="41b3c-255">设置值</span><span class="sxs-lookup"><span data-stu-id="41b3c-255">Setting value</span></span> |<span data-ttu-id="41b3c-256">行为</span><span class="sxs-lookup"><span data-stu-id="41b3c-256">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="41b3c-257">**已启用传出和传入音频**</span><span class="sxs-lookup"><span data-stu-id="41b3c-257">**Outgoing and incoming audio enabled**</span></span>    |<span data-ttu-id="41b3c-258">会议允许传出和传入音频。</span><span class="sxs-lookup"><span data-stu-id="41b3c-258">Outgoing and incoming audio is allowed in the meeting.</span></span> <span data-ttu-id="41b3c-259">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="41b3c-259">This is the default setting.</span></span> |
|<span data-ttu-id="41b3c-260">**已禁用**</span><span class="sxs-lookup"><span data-stu-id="41b3c-260">**Disabled**</span></span>     |<span data-ttu-id="41b3c-261">传出和传入音频在会议中关闭。</span><span class="sxs-lookup"><span data-stu-id="41b3c-261">Outgoing and incoming audio is turned off in the meeting.</span></span>     |

<span data-ttu-id="41b3c-262">如果用户设置为 **"** 已禁用"，该用户仍然可以安排和组织会议，但他们不能使用音频。</span><span class="sxs-lookup"><span data-stu-id="41b3c-262">If set to **Disabled** for a user, that user can still schedule and organize meetings but they can't use audio.</span></span> <span data-ttu-id="41b3c-263">若要加入会议，他们必须通过 PSTN 公用电话交换网 (PSTN) 或通过电话拨入会议呼叫并加入。</span><span class="sxs-lookup"><span data-stu-id="41b3c-263">To join a meeting, they have to dial in through the Public Switched Telephone Network (PSTN) or have the meeting call and join them by phone.</span></span> <span data-ttu-id="41b3c-264">未分配任何策略的会议参与者（例如 (匿名参与者) 默认设置为"传出"和"传入"音频。 </span><span class="sxs-lookup"><span data-stu-id="41b3c-264">Meeting participants who don't have any policies assigned (for example, anonymous participants) have this set to **Outgoing and incoming audio enabled** by default.</span></span> <span data-ttu-id="41b3c-265">在 Teams 移动客户端上，如果禁用此设置，用户必须通过 PSTN 拨入会议。</span><span class="sxs-lookup"><span data-stu-id="41b3c-265">On Teams mobile clients, if this setting is disabled, the user has to dial in to the meeting through the PSTN.</span></span>

<span data-ttu-id="41b3c-266">此设置不适用于 1：1 调用。</span><span class="sxs-lookup"><span data-stu-id="41b3c-266">This setting doesn't apply to 1:1 calls.</span></span> <span data-ttu-id="41b3c-267">若要限制 1 对 1 通话，请配置 [Teams](teams-calling-policy.md) 呼叫策略并关闭"拨打 **私人电话"** 设置。</span><span class="sxs-lookup"><span data-stu-id="41b3c-267">To restrict 1:1 calls, configure a Teams [calling policy](teams-calling-policy.md) and turn off the **Make private calls** setting.</span></span> <span data-ttu-id="41b3c-268">此设置也不适用于会议室设备，例如 Surface Hub 和 Microsoft Teams 会议室设备。</span><span class="sxs-lookup"><span data-stu-id="41b3c-268">This setting also doesn't apply to conference room devices such as Surface Hub and Microsoft Teams Rooms devices.</span></span>

<span data-ttu-id="41b3c-269">此设置尚不可用于 Microsoft 365 政府社区云 (GCC) 、GCC High 或国防部 (DoD) 环境。</span><span class="sxs-lookup"><span data-stu-id="41b3c-269">This setting isn't yet available for Microsoft 365 Government Community Cloud (GCC), GCC High, or Department of Defense (DoD) environments.</span></span>

<span data-ttu-id="41b3c-270">若要了解有关详细信息，请参阅"[管理会议参与者的音频/视频"。](#manage-audiovideo-for-meeting-participants)</span><span class="sxs-lookup"><span data-stu-id="41b3c-270">To learn more, see [Manage audio/video for meeting participants](#manage-audiovideo-for-meeting-participants).</span></span>

### <a name="mode-for-ip-video"></a><span data-ttu-id="41b3c-271">IP 视频的模式</span><span class="sxs-lookup"><span data-stu-id="41b3c-271">Mode for IP video</span></span>

<span data-ttu-id="41b3c-272">这是按用户的策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-272">This is a per-user policy.</span></span> <span data-ttu-id="41b3c-273">此设置控制是否可以在会议和群组通话中打开视频。</span><span class="sxs-lookup"><span data-stu-id="41b3c-273">This setting controls whether video can be turned on in meetings and group calls.</span></span> <span data-ttu-id="41b3c-274">下面是此设置的值。</span><span class="sxs-lookup"><span data-stu-id="41b3c-274">Here are the values for this setting.</span></span>

|<span data-ttu-id="41b3c-275">设置值</span><span class="sxs-lookup"><span data-stu-id="41b3c-275">Setting value</span></span> |<span data-ttu-id="41b3c-276">行为</span><span class="sxs-lookup"><span data-stu-id="41b3c-276">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="41b3c-277">**已启用传出和传入视频**</span><span class="sxs-lookup"><span data-stu-id="41b3c-277">**Outgoing and incoming video enabled**</span></span>    | <span data-ttu-id="41b3c-278">会议允许传出和传入视频。</span><span class="sxs-lookup"><span data-stu-id="41b3c-278">Outgoing and incoming video is allowed in the meeting.</span></span> <span data-ttu-id="41b3c-279">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="41b3c-279">This is the default setting.</span></span> |
|<span data-ttu-id="41b3c-280">**已禁用**</span><span class="sxs-lookup"><span data-stu-id="41b3c-280">**Disabled**</span></span>     | <span data-ttu-id="41b3c-281">传出和传入视频在会议中关闭。</span><span class="sxs-lookup"><span data-stu-id="41b3c-281">Outgoing and incoming video is turned off in the meeting.</span></span> <span data-ttu-id="41b3c-282">在 Teams 移动客户端上，用户无法共享会议中的视频或照片。</span><span class="sxs-lookup"><span data-stu-id="41b3c-282">On Teams mobile clients, users can't share videos or photos in the meeting.</span></span> <br><br><span data-ttu-id="41b3c-283">请注意，如果 **禁用 IP** 音频的模式，则 **IP 视频** 的模式也将保持禁用状态。</span><span class="sxs-lookup"><span data-stu-id="41b3c-283">Note that if **Mode for IP audio** is disabled, then **Mode for IP video** will also remain disabled.</span></span>  |

<span data-ttu-id="41b3c-284">如果用户设置为 **"** 禁用"，该用户无法打开视频或查看其他会议参与者共享的视频。</span><span class="sxs-lookup"><span data-stu-id="41b3c-284">If set to **Disabled** for a  user, that user can't turn on video or view videos shared by other meeting participants.</span></span> <span data-ttu-id="41b3c-285">未分配任何策略的会议参与者 (例如，匿名参与者) 默认设置为启用传出和传入视频。 </span><span class="sxs-lookup"><span data-stu-id="41b3c-285">Meeting participants who don't have any policies assigned (for example, anonymous participants) have this set to **Outgoing and incoming video enabled** by default.</span></span>

<span data-ttu-id="41b3c-286">此设置不适用于会议室设备，例如 Surface Hub 和 Microsoft Teams 会议室设备。</span><span class="sxs-lookup"><span data-stu-id="41b3c-286">This setting doesn't apply to conference room devices such as Surface Hub and Microsoft Teams Rooms devices.</span></span>

<span data-ttu-id="41b3c-287">此设置尚不可用于 Microsoft 365 政府社区云 (GCC) 、GCC High 或国防部 (DoD) 环境。</span><span class="sxs-lookup"><span data-stu-id="41b3c-287">This setting isn't yet available for Microsoft 365 Government Community Cloud (GCC), GCC High, or Department of Defense (DoD) environments.</span></span>

> [!NOTE]
> <span data-ttu-id="41b3c-288">请记住，此设置控制传出和传入视频，而 **"允许 IP 视频** "设置控制传出视频。</span><span class="sxs-lookup"><span data-stu-id="41b3c-288">Keep in mind that this setting controls both outgoing and incoming video whereas the **Allow IP video** setting controls outgoing video.</span></span> <span data-ttu-id="41b3c-289">若要了解有关详细信息，请参阅 [哪个 IP 视频策略设置优先？](#which-ip-video-policy-setting-takes-precedence) 以及 [管理会议参与者的音频/视频](#manage-audiovideo-for-meeting-participants)。</span><span class="sxs-lookup"><span data-stu-id="41b3c-289">To learn more, see [Which IP video policy setting takes precedence?](#which-ip-video-policy-setting-takes-precedence) and [Manage audio/video for meeting participants](#manage-audiovideo-for-meeting-participants).</span></span>

<span data-ttu-id="41b3c-290">若要了解有关详细信息，请参阅"[管理会议参与者的音频/视频"。](#manage-audiovideo-for-meeting-participants)</span><span class="sxs-lookup"><span data-stu-id="41b3c-290">To learn more, see [Manage audio/video for meeting participants](#manage-audiovideo-for-meeting-participants).</span></span>

### <a name="allow-ip-video"></a><span data-ttu-id="41b3c-291">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="41b3c-291">Allow IP video</span></span>

<span data-ttu-id="41b3c-292">这是按组织者和按用户的策略的组合。</span><span class="sxs-lookup"><span data-stu-id="41b3c-292">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="41b3c-293">视频是会议的关键组成部分。</span><span class="sxs-lookup"><span data-stu-id="41b3c-293">Video is a key component to meetings.</span></span> <span data-ttu-id="41b3c-294">在某些组织中，管理员可能希望对哪些用户的会议具有视频进行更多控制。</span><span class="sxs-lookup"><span data-stu-id="41b3c-294">In some organizations, admins might want more control over which users' meetings have video.</span></span> <span data-ttu-id="41b3c-295">此设置控制是否可以在用户主持的会议以及由用户启动的 1：1 和群组通话中打开视频。</span><span class="sxs-lookup"><span data-stu-id="41b3c-295">This setting controls whether video can be turned on in meetings hosted by a user and in 1:1 and group calls started by a user.</span></span> <span data-ttu-id="41b3c-296">在 Teams 移动客户端上，此设置控制用户是否可以在会议中共享照片和视频。</span><span class="sxs-lookup"><span data-stu-id="41b3c-296">On Teams mobile clients, this setting control whether users can share photos and videos in a meeting.</span></span>

<span data-ttu-id="41b3c-297">由启用了此策略设置的用户组织的会议，如果参与者还启用了策略设置，则允许会议参与者在会议中共享视频。</span><span class="sxs-lookup"><span data-stu-id="41b3c-297">Meetings organized by a user who has this policy setting enabled, allow video sharing in the meeting by the meeting participants, if the participants also have the policy setting enabled.</span></span> <span data-ttu-id="41b3c-298">未分配任何策略的会议参与者， (匿名和联合参与者) 继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-298">Meeting participants who don't have any policies assigned (for example, anonymous and federated participants) inherit the policy of the meeting organizer.</span></span>

> [!NOTE]
> <span data-ttu-id="41b3c-299">请记住，此设置控制传出视频，而 IP **视频设置模式** 控制传出和传入视频。</span><span class="sxs-lookup"><span data-stu-id="41b3c-299">Keep in mind that this setting controls outgoing video whereas the **Mode for IP video** setting controls both outgoing and incoming video.</span></span> <span data-ttu-id="41b3c-300">若要了解有关详细信息，请参阅 [哪个 IP 视频策略设置优先？](#which-ip-video-policy-setting-takes-precedence) 以及 [管理会议参与者的音频/视频](#manage-audiovideo-for-meeting-participants)。</span><span class="sxs-lookup"><span data-stu-id="41b3c-300">To learn more, see [Which IP video policy setting takes precedence?](#which-ip-video-policy-setting-takes-precedence) and [Manage audio/video for meeting participants](#manage-audiovideo-for-meeting-participants).</span></span>

| <span data-ttu-id="41b3c-301">Teams 桌面和 Web 客户端</span><span class="sxs-lookup"><span data-stu-id="41b3c-301">Teams desktop and web client</span></span> |<span data-ttu-id="41b3c-302">Teams 移动客户端</span><span class="sxs-lookup"><span data-stu-id="41b3c-302">Teams mobile client</span></span>  |
|:-------:|:-------:|
|![显示桌面音频/视频设置的会议加入的屏幕截图](media/meeting-policies-audio-video-settings.png)    |![显示移动设备上音频/视频设置的会议加入的屏幕截图](media/meeting-policies-mobile-join.png)          |

<span data-ttu-id="41b3c-305">让我们看看以下示例。</span><span class="sxs-lookup"><span data-stu-id="41b3c-305">Let's look at the following example.</span></span>

|<span data-ttu-id="41b3c-306">用户</span><span class="sxs-lookup"><span data-stu-id="41b3c-306">User</span></span> |<span data-ttu-id="41b3c-307">会议策略</span><span class="sxs-lookup"><span data-stu-id="41b3c-307">Meeting policy</span></span>  |<span data-ttu-id="41b3c-308">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="41b3c-308">Allow IP video</span></span> |
|---------|---------|---------|
|<span data-ttu-id="41b3c-309">Daniela</span><span class="sxs-lookup"><span data-stu-id="41b3c-309">Daniela</span></span>   | <span data-ttu-id="41b3c-310">全局</span><span class="sxs-lookup"><span data-stu-id="41b3c-310">Global</span></span>   | <span data-ttu-id="41b3c-311">开</span><span class="sxs-lookup"><span data-stu-id="41b3c-311">On</span></span>       |
|<span data-ttu-id="41b3c-312">阿兰达</span><span class="sxs-lookup"><span data-stu-id="41b3c-312">Amanda</span></span>    | <span data-ttu-id="41b3c-313">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="41b3c-313">Location1MeetingPolicy</span></span>        | <span data-ttu-id="41b3c-314">关</span><span class="sxs-lookup"><span data-stu-id="41b3c-314">Off</span></span>      |

<span data-ttu-id="41b3c-315">Daniela 主持的会议允许打开视频。</span><span class="sxs-lookup"><span data-stu-id="41b3c-315">Meetings hosted by Daniela allow video to be turned on.</span></span> <span data-ttu-id="41b3c-316">Daniela 可以加入会议并打开视频。</span><span class="sxs-lookup"><span data-stu-id="41b3c-316">Daniela can join the meeting and turn on video.</span></span> <span data-ttu-id="41b3c-317">Amanda 无法打开 Daniela 会议的视频，因为 Amanda 的策略设置为不允许视频。</span><span class="sxs-lookup"><span data-stu-id="41b3c-317">Amanda can't turn on video in Daniela's meeting because Amanda's policy is set to not allow video.</span></span> <span data-ttu-id="41b3c-318">Amanda 可以在会议中查看其他参与者共享的视频。</span><span class="sxs-lookup"><span data-stu-id="41b3c-318">Amanda can see videos shared by other participants in the meeting.</span></span>

<span data-ttu-id="41b3c-319">在 Amanda 主持的会议中，无论分配给他们的视频策略如何，均无法打开视频。</span><span class="sxs-lookup"><span data-stu-id="41b3c-319">In meetings hosted by Amanda, no one can turn on video, regardless of the video policy assigned to them.</span></span> <span data-ttu-id="41b3c-320">这意味着 Daniela 无法打开 Amanda 会议中的视频。</span><span class="sxs-lookup"><span data-stu-id="41b3c-320">This means Daniela can't turn on video in Amanda's meetings.</span></span>  

<span data-ttu-id="41b3c-321">如果 Daniela 通过视频呼叫 Amanda，Amanda 只能使用音频应答呼叫。</span><span class="sxs-lookup"><span data-stu-id="41b3c-321">If Daniela calls Amanda with video on, Amanda can answer the call with audio only.</span></span> <span data-ttu-id="41b3c-322">当呼叫已连接时，Amanda 可以看到 Daniela 的视频，但无法打开视频。</span><span class="sxs-lookup"><span data-stu-id="41b3c-322">When the call is connected, Amanda can see Daniela's video but can't turn on video.</span></span> <span data-ttu-id="41b3c-323">如果 Amanda 呼叫 Daniela，Daniela 可以使用视频和音频应答呼叫。</span><span class="sxs-lookup"><span data-stu-id="41b3c-323">If Amanda calls Daniela, Daniela can answer the call with video and audio.</span></span> <span data-ttu-id="41b3c-324">当呼叫接通后，Daniela 可根据需要打开或关闭其视频。</span><span class="sxs-lookup"><span data-stu-id="41b3c-324">When the call is connected, Daniela can turn on or turn off her video, as needed.</span></span>

<span data-ttu-id="41b3c-325">若要了解有关详细信息，请参阅"[管理会议参与者的音频/视频"。](#manage-audiovideo-for-meeting-participants)</span><span class="sxs-lookup"><span data-stu-id="41b3c-325">To learn more, see [Manage audio/video for meeting participants](#manage-audiovideo-for-meeting-participants).</span></span>

#### <a name="which-ip-video-policy-setting-takes-precedence"></a><span data-ttu-id="41b3c-326">哪个 IP 视频策略设置优先</span><span class="sxs-lookup"><span data-stu-id="41b3c-326">Which IP video policy setting takes precedence</span></span>

<span data-ttu-id="41b3c-327">对于用户，最严格的视频策略设置优先。</span><span class="sxs-lookup"><span data-stu-id="41b3c-327">For a user, the most restrictive policy setting for video takes precedence.</span></span> <span data-ttu-id="41b3c-328">下面是一些示例。</span><span class="sxs-lookup"><span data-stu-id="41b3c-328">Here's some examples.</span></span>

|<span data-ttu-id="41b3c-329">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="41b3c-329">Allow IP video</span></span>|<span data-ttu-id="41b3c-330">IP 视频的模式</span><span class="sxs-lookup"><span data-stu-id="41b3c-330">Mode for IP video</span></span>|<span data-ttu-id="41b3c-331">会议体验</span><span class="sxs-lookup"><span data-stu-id="41b3c-331">Meeting experience</span></span>|
|---------|---------|---------|
|<span data-ttu-id="41b3c-332">组织者： **打开**</span><span class="sxs-lookup"><span data-stu-id="41b3c-332">Organizer: **On**</span></span><br><br><span data-ttu-id="41b3c-333">参与者： **打开**</span><span class="sxs-lookup"><span data-stu-id="41b3c-333">Participant: **On**</span></span> |<span data-ttu-id="41b3c-334">参与者： **已禁用**</span><span class="sxs-lookup"><span data-stu-id="41b3c-334">Participant: **Disabled**</span></span>        |<span data-ttu-id="41b3c-335">IP **视频设置的模式** 优先。</span><span class="sxs-lookup"><span data-stu-id="41b3c-335">The **Mode for IP video** setting takes precedence.</span></span> <span data-ttu-id="41b3c-336">分配了此策略的参与者无法打开或查看其他人共享的视频。</span><span class="sxs-lookup"><span data-stu-id="41b3c-336">The participant who is assigned this policy can't turn on or view videos shared by others.</span></span>|
|<span data-ttu-id="41b3c-337">组织者： **打开**</span><span class="sxs-lookup"><span data-stu-id="41b3c-337">Organizer: **On**</span></span><br><br><span data-ttu-id="41b3c-338">参与者： **打开**</span><span class="sxs-lookup"><span data-stu-id="41b3c-338">Participant: **On**</span></span> |<span data-ttu-id="41b3c-339">参与者： **已启用传出和传入视频**</span><span class="sxs-lookup"><span data-stu-id="41b3c-339">Participant: **Outgoing and incoming video enabled**</span></span>          |<span data-ttu-id="41b3c-340">分配了此策略的参与者可以打开或查看其他人共享的视频。</span><span class="sxs-lookup"><span data-stu-id="41b3c-340">The participant who is assigned this policy can turn on or view videos shared by others.</span></span>         |
|<span data-ttu-id="41b3c-341">组织者： **打开**</span><span class="sxs-lookup"><span data-stu-id="41b3c-341">Organizer: **On**</span></span><br><br><span data-ttu-id="41b3c-342">参与者： **关闭**</span><span class="sxs-lookup"><span data-stu-id="41b3c-342">Participant: **Off**</span></span> |<span data-ttu-id="41b3c-343">参与者： **已启用传出和传入视频**</span><span class="sxs-lookup"><span data-stu-id="41b3c-343">Participant: **Outgoing and incoming video enabled**</span></span>         |<span data-ttu-id="41b3c-344">" **允许 IP 视频** "设置优先。</span><span class="sxs-lookup"><span data-stu-id="41b3c-344">The **Allow IP video** setting takes precedence.</span></span> <span data-ttu-id="41b3c-345">参与者只能看到传入的视频，不能发送传出视频。</span><span class="sxs-lookup"><span data-stu-id="41b3c-345">Participants can only see incoming video and can't send outgoing video.</span></span>         |
|<span data-ttu-id="41b3c-346">组织者： **打开**</span><span class="sxs-lookup"><span data-stu-id="41b3c-346">Organizer: **On**</span></span><br><br><span data-ttu-id="41b3c-347">参与者： **关闭**</span><span class="sxs-lookup"><span data-stu-id="41b3c-347">Participant: **Off**</span></span> |<span data-ttu-id="41b3c-348">参与者： **已禁用**</span><span class="sxs-lookup"><span data-stu-id="41b3c-348">Participant: **Disabled**</span></span>         |<span data-ttu-id="41b3c-349">IP **视频设置的模式** 优先。</span><span class="sxs-lookup"><span data-stu-id="41b3c-349">The **Mode for IP video** setting takes precedence.</span></span> <span data-ttu-id="41b3c-350">参与者无法看到传入或传出视频。</span><span class="sxs-lookup"><span data-stu-id="41b3c-350">The participant can't see incoming or outgoing video.</span></span>|
|<span data-ttu-id="41b3c-351">组织者： **关闭**</span><span class="sxs-lookup"><span data-stu-id="41b3c-351">Organizer: **Off**</span></span>    |       |<span data-ttu-id="41b3c-352">" **允许 IP 视频** "设置优先，因为组织者已关闭该设置。</span><span class="sxs-lookup"><span data-stu-id="41b3c-352">The **Allow IP video** setting takes precedence because it's turned off for the organizer.</span></span> <span data-ttu-id="41b3c-353">在由分配有此策略的用户组织的会议中，没有人可以打开视频。</span><span class="sxs-lookup"><span data-stu-id="41b3c-353">No one can turn on video in meetings organized by the user who is assigned this policy.</span></span>         |

### <a name="manage-audiovideo-for-meeting-participants"></a><span data-ttu-id="41b3c-354">管理会议参与者的音频/视频</span><span class="sxs-lookup"><span data-stu-id="41b3c-354">Manage audio/video for meeting participants</span></span>

|<span data-ttu-id="41b3c-355">如果你希望...</span><span class="sxs-lookup"><span data-stu-id="41b3c-355">If you want to...</span></span>  |<span data-ttu-id="41b3c-356">设置以下策略设置</span><span class="sxs-lookup"><span data-stu-id="41b3c-356">Set the following policy settings</span></span>  |
|---------|---------|
|<span data-ttu-id="41b3c-357">为会议中的参与者禁用音频和视频</span><span class="sxs-lookup"><span data-stu-id="41b3c-357">Disable audio and video for participants in meetings</span></span>  |<span data-ttu-id="41b3c-358">IP 音频模式： **已禁用**</span><span class="sxs-lookup"><span data-stu-id="41b3c-358">Mode for IP audio: **Disabled**</span></span><br> <span data-ttu-id="41b3c-359">IP 视频模式： **已禁用**</span><span class="sxs-lookup"><span data-stu-id="41b3c-359">Mode for IP video: **Disabled**</span></span><br><span data-ttu-id="41b3c-360">允许 IP 视频：N/A</span><span class="sxs-lookup"><span data-stu-id="41b3c-360">Allow IP video: N/A</span></span>       |
|<span data-ttu-id="41b3c-361">仅为会议中的参与者启用传入视频和音频</span><span class="sxs-lookup"><span data-stu-id="41b3c-361">Enable only incoming video and audio for participants in meetings</span></span>  |<span data-ttu-id="41b3c-362">IP 音频模式： **已启用传出和传入音频**</span><span class="sxs-lookup"><span data-stu-id="41b3c-362">Mode for IP audio: **Outgoing and incoming audio enabled**</span></span><br> <span data-ttu-id="41b3c-363">IP 视频模式： **已启用传出和传入视频**</span><span class="sxs-lookup"><span data-stu-id="41b3c-363">Mode for IP video: **Outgoing and incoming video enabled**</span></span><br><span data-ttu-id="41b3c-364">允许 IP 视频： **关闭**</span><span class="sxs-lookup"><span data-stu-id="41b3c-364">Allow IP video: **Off**</span></span>       |
|<span data-ttu-id="41b3c-365">禁用会议中参与者的视频， (只有音频) </span><span class="sxs-lookup"><span data-stu-id="41b3c-365">Disable video for participants in meetings (participants have audio only)</span></span>|  <span data-ttu-id="41b3c-366">IP 音频模式： **启用传出和传入音频**</span><span class="sxs-lookup"><span data-stu-id="41b3c-366">Mode for IP audio: **Enable outgoing and incoming audio**</span></span><br> <span data-ttu-id="41b3c-367">IP 视频模式： **已禁用**</span><span class="sxs-lookup"><span data-stu-id="41b3c-367">Mode for IP video: **Disabled**</span></span><br><span data-ttu-id="41b3c-368">允许 IP 视频：N/A</span><span class="sxs-lookup"><span data-stu-id="41b3c-368">Allow IP video: N/A</span></span>
|<span data-ttu-id="41b3c-369">为会议参与者启用音频和视频</span><span class="sxs-lookup"><span data-stu-id="41b3c-369">Enable audio and video for participants in meetings</span></span>    |<span data-ttu-id="41b3c-370">IP 音频模式： **已启用传出和传入音频 (** 默认) </span><span class="sxs-lookup"><span data-stu-id="41b3c-370">Mode for IP audio: **Outgoing and incoming audio enabled** (default)</span></span><br> <span data-ttu-id="41b3c-371">IP 视频模式： **启用传出和传入视频 (** 默认) </span><span class="sxs-lookup"><span data-stu-id="41b3c-371">Mode for IP video: **Outgoing and incoming video enabled** (default)</span></span><br><span data-ttu-id="41b3c-372">允许 IP 视频： **在** (上) </span><span class="sxs-lookup"><span data-stu-id="41b3c-372">Allow IP video: **On** (default)</span></span>    |

<span data-ttu-id="41b3c-373">会议组织者的策略与用户策略之间的限制性最强的策略适用。</span><span class="sxs-lookup"><span data-stu-id="41b3c-373">The most restrictive policy between the meeting organizer’s policy and the user’s policy applies.</span></span> <span data-ttu-id="41b3c-374">例如，如果组织者的策略限制视频，而用户的策略不限制视频，则会议参与者将继承会议组织者的策略，并且无法访问会议中的视频。</span><span class="sxs-lookup"><span data-stu-id="41b3c-374">For example, if an organizer has a policy that restricts video and a user’s policy doesn't restrict video, meeting participants inherit the policy of the meeting organizer and don't have access to video in meetings.</span></span> <span data-ttu-id="41b3c-375">这意味着他们只能使用音频加入会议。</span><span class="sxs-lookup"><span data-stu-id="41b3c-375">This means that they can join the meeting with audio only.</span></span>

> [!NOTE]
> <span data-ttu-id="41b3c-376">当用户启动群组通话以通过电话加入时，不显示"使用电话 **进行** 音频屏幕"。</span><span class="sxs-lookup"><span data-stu-id="41b3c-376">When a user starts a group call to join by phone, the **Use phone for audio** screen doesn't appear.</span></span> <span data-ttu-id="41b3c-377">这是一个已知问题，我们正在努力解决。</span><span class="sxs-lookup"><span data-stu-id="41b3c-377">This is a known issue that we're working to resolve.</span></span> <span data-ttu-id="41b3c-378">若要解决此问题，请在"其他加入选项"下 **选择"电话音频"。**</span><span class="sxs-lookup"><span data-stu-id="41b3c-378">To work around this issue, select **Phone audio** under **Other join options**.</span></span>  

#### <a name="teams-mobile-clients"></a><span data-ttu-id="41b3c-379">Teams 移动客户端</span><span class="sxs-lookup"><span data-stu-id="41b3c-379">Teams mobile clients</span></span>

<span data-ttu-id="41b3c-380">对于 Teams 移动客户端上的用户，会议期间共享照片和视频的能力也取决于"允许 **IP** 视频"或 **"IP 视频模式"设置** 。</span><span class="sxs-lookup"><span data-stu-id="41b3c-380">For users on Teams mobile clients, the ability to share photos and videos during a meeting is also determined by the **Allow IP video** or **IP video mode** setting.</span></span> <span data-ttu-id="41b3c-381">共享视频和照片的能力将不可用，具体取决于哪个策略设置优先。</span><span class="sxs-lookup"><span data-stu-id="41b3c-381">Depending on which policy setting takes precedence, the ability to share videos and photos won't be available.</span></span> <span data-ttu-id="41b3c-382">这不会影响屏幕共享，这是使用单独的屏幕共享模式设置 [配置的](#screen-sharing-mode) 。</span><span class="sxs-lookup"><span data-stu-id="41b3c-382">This doesn't affect screen sharing, which you configure using a separate [Screen sharing mode](#screen-sharing-mode) setting.</span></span> <span data-ttu-id="41b3c-383">此外，可以设置 [Teams](https://docs.microsoft.com/powershell/module/skype/new-csteamsmobilitypolicy) 移动策略来防止移动用户通过手机网络连接使用 IP 视频，这意味着他们必须使用 WiFi 连接。</span><span class="sxs-lookup"><span data-stu-id="41b3c-383">Additionally, you can set a [Teams mobility policy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmobilitypolicy) to prevent mobile users from using IP video over a cellular connection, which means they must use a WiFi connection.</span></span>

### <a name="media-bit-rate-kbs"></a><span data-ttu-id="41b3c-384">媒体比特率 (Kbs) </span><span class="sxs-lookup"><span data-stu-id="41b3c-384">Media bit rate (Kbs)</span></span>

<span data-ttu-id="41b3c-385">这是按用户的策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-385">This is a per-user policy.</span></span> <span data-ttu-id="41b3c-386">此设置确定在呼叫和会议中为用户共享音频、视频和基于视频的应用的传输的媒体比特率。</span><span class="sxs-lookup"><span data-stu-id="41b3c-386">This setting determines the media bit rate for audio, video, and video-based app sharing transmissions in calls and meetings for the user.</span></span> <span data-ttu-id="41b3c-387">它同时应用于呼叫或会议中的用户的上行和下行媒体遍历。</span><span class="sxs-lookup"><span data-stu-id="41b3c-387">It's applied to both the uplink and downlink media traversal for users in the call or meeting.</span></span> <span data-ttu-id="41b3c-388">此设置可让你精细控制组织中带宽的管理。</span><span class="sxs-lookup"><span data-stu-id="41b3c-388">This setting gives you granular control over managing bandwidth in your organization.</span></span> <span data-ttu-id="41b3c-389">根据用户所需的会议方案，我们建议有足够的带宽，以便获得优质体验。</span><span class="sxs-lookup"><span data-stu-id="41b3c-389">Depending on the meetings scenarios required by users, we recommend having enough bandwidth in place for a good quality experience.</span></span> <span data-ttu-id="41b3c-390">最小值为 30 Kbps，最大值取决于会议方案。</span><span class="sxs-lookup"><span data-stu-id="41b3c-390">The minimum value is 30 Kbps and the maximum value depends on the meeting scenario.</span></span> <span data-ttu-id="41b3c-391">若要详细了解在 Teams 中为优质会议、通话和实时事件建议的最小带宽，请参阅 [带宽要求](prepare-network.md#bandwidth-requirements)。</span><span class="sxs-lookup"><span data-stu-id="41b3c-391">To learn more about the minimum recommended bandwidth for good quality meetings, calls, and live events in Teams, see [Bandwidth requirements](prepare-network.md#bandwidth-requirements).</span></span>

<span data-ttu-id="41b3c-392">如果没有足够的带宽用于会议，参与者将看到一条消息，指示网络质量差。</span><span class="sxs-lookup"><span data-stu-id="41b3c-392">If there isn't enough bandwidth for a meeting, participants see a message that indicates poor network quality.</span></span>

<span data-ttu-id="41b3c-393">对于需要最高质量的视频体验的会议，例如 CEO 董事会会议和 Teams 实时活动，建议将带宽设置为 10 Mbps。</span><span class="sxs-lookup"><span data-stu-id="41b3c-393">For meetings that need the highest-quality video experience, such as CEO board meetings and Teams live events, we recommend you set the bandwidth to 10 Mbps.</span></span> <span data-ttu-id="41b3c-394">即使设置了最大体验，在检测到特定网络条件时，Teams 媒体堆栈也能够适应低带宽条件，具体取决于方案。</span><span class="sxs-lookup"><span data-stu-id="41b3c-394">Even when the maximum experience is set, the Teams media stack adapts to low-bandwidth conditions when certain network conditions are detected, depending on the scenario.</span></span>

## <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="41b3c-395">会议策略设置 - 内容共享</span><span class="sxs-lookup"><span data-stu-id="41b3c-395">Meeting policy settings - Content sharing</span></span>

- [<span data-ttu-id="41b3c-396">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="41b3c-396">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="41b3c-397">允许参与者授予或请求控制权</span><span class="sxs-lookup"><span data-stu-id="41b3c-397">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="41b3c-398">允许外部参与者授予或请求控制权</span><span class="sxs-lookup"><span data-stu-id="41b3c-398">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="41b3c-399">允许 PowerPoint 共享</span><span class="sxs-lookup"><span data-stu-id="41b3c-399">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="41b3c-400">允许白板</span><span class="sxs-lookup"><span data-stu-id="41b3c-400">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="41b3c-401">允许共享笔记</span><span class="sxs-lookup"><span data-stu-id="41b3c-401">Allow shared notes</span></span>](#allow-shared-notes)

### <a name="screen-sharing-mode"></a><span data-ttu-id="41b3c-402">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="41b3c-402">Screen sharing mode</span></span>

> [!NOTE]
> <span data-ttu-id="41b3c-403">此功能仍在开发中。</span><span class="sxs-lookup"><span data-stu-id="41b3c-403">This feature is still in development.</span></span> <span data-ttu-id="41b3c-404">屏幕共享是按参与者的策略，但是，它可能会受组织者的屏幕共享设置的影响，如本部分中所述。</span><span class="sxs-lookup"><span data-stu-id="41b3c-404">Screen sharing is a per-participant policy, however, it can be affected by the organizer's screen sharing settings, as described in this section.</span></span>

<span data-ttu-id="41b3c-405">此设置控制是否在用户的会议中允许桌面和/或窗口共享。</span><span class="sxs-lookup"><span data-stu-id="41b3c-405">This setting controls whether desktop and/or window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="41b3c-406">未分配任何策略的会议参与者 (匿名、来宾、B2B 和联合参与者) 继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-406">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="41b3c-407">设置值</span><span class="sxs-lookup"><span data-stu-id="41b3c-407">Setting value</span></span> |<span data-ttu-id="41b3c-408">行为</span><span class="sxs-lookup"><span data-stu-id="41b3c-408">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="41b3c-409">**整个屏幕**</span><span class="sxs-lookup"><span data-stu-id="41b3c-409">**Entire screen**</span></span>    | <span data-ttu-id="41b3c-410">会议允许完全桌面共享和应用程序共享</span><span class="sxs-lookup"><span data-stu-id="41b3c-410">Full desktop sharing and application sharing are allowed in the meeting</span></span> |
|<span data-ttu-id="41b3c-411">**单个应用程序**</span><span class="sxs-lookup"><span data-stu-id="41b3c-411">**Single application**</span></span>   | <span data-ttu-id="41b3c-412">会议允许应用程序共享</span><span class="sxs-lookup"><span data-stu-id="41b3c-412">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="41b3c-413">**已禁用**</span><span class="sxs-lookup"><span data-stu-id="41b3c-413">**Disabled**</span></span>     |<span data-ttu-id="41b3c-414">会议中已关闭屏幕共享和应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="41b3c-414">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="41b3c-415">让我们看看以下示例。</span><span class="sxs-lookup"><span data-stu-id="41b3c-415">Let's look at the following example.</span></span>

|<span data-ttu-id="41b3c-416">用户</span><span class="sxs-lookup"><span data-stu-id="41b3c-416">User</span></span> |<span data-ttu-id="41b3c-417">会议策略</span><span class="sxs-lookup"><span data-stu-id="41b3c-417">Meeting policy</span></span> |<span data-ttu-id="41b3c-418">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="41b3c-418">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="41b3c-419">Daniela</span><span class="sxs-lookup"><span data-stu-id="41b3c-419">Daniela</span></span>  | <span data-ttu-id="41b3c-420">全局</span><span class="sxs-lookup"><span data-stu-id="41b3c-420">Global</span></span>   | <span data-ttu-id="41b3c-421">整个屏幕</span><span class="sxs-lookup"><span data-stu-id="41b3c-421">Entire screen</span></span> |
|<span data-ttu-id="41b3c-422">阿兰达</span><span class="sxs-lookup"><span data-stu-id="41b3c-422">Amanda</span></span>   | <span data-ttu-id="41b3c-423">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="41b3c-423">Location1MeetingPolicy</span></span>  | <span data-ttu-id="41b3c-424">已禁用</span><span class="sxs-lookup"><span data-stu-id="41b3c-424">Disabled</span></span> |

<span data-ttu-id="41b3c-425">Daniela 主持的会议允许会议参与者共享其整个屏幕或特定应用程序。</span><span class="sxs-lookup"><span data-stu-id="41b3c-425">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="41b3c-426">如果 Amanda 加入 Daniela 的会议，Amanda 无法共享她的屏幕或特定应用程序，因为禁用了策略设置。</span><span class="sxs-lookup"><span data-stu-id="41b3c-426">If Amanda joins Daniela's meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="41b3c-427">在 Amanda 主持的会议中，无论分配给他们的屏幕共享模式策略如何，都不允许任何人共享其屏幕或单个应用程序。</span><span class="sxs-lookup"><span data-stu-id="41b3c-427">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span> <span data-ttu-id="41b3c-428">这意味着 Daniela 无法共享她的屏幕或 Amanda 会议中的单个应用程序。</span><span class="sxs-lookup"><span data-stu-id="41b3c-428">This means that Daniela can't share her screen or a single application in Amanda's meetings.</span></span>  

<span data-ttu-id="41b3c-429">目前，如果用户使用 Google Chrome，则他们无法播放视频或在 Teams 会议中共享其屏幕。</span><span class="sxs-lookup"><span data-stu-id="41b3c-429">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

### <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="41b3c-430">允许参与者授予或请求控制权</span><span class="sxs-lookup"><span data-stu-id="41b3c-430">Allow a participant to give or request control</span></span>

<span data-ttu-id="41b3c-431">这是按用户的策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-431">This is a per-user policy.</span></span> <span data-ttu-id="41b3c-432">此设置控制用户是否可以将共享桌面或窗口的控制权授予其他会议参与者。</span><span class="sxs-lookup"><span data-stu-id="41b3c-432">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="41b3c-433">若要授予控制权，请将鼠标悬停在屏幕顶部。</span><span class="sxs-lookup"><span data-stu-id="41b3c-433">To give control, hover over the top of the screen.</span></span>

<span data-ttu-id="41b3c-434">如果为用户启用此设置，共享会话的顶部栏中会显示"授予控制"选项。</span><span class="sxs-lookup"><span data-stu-id="41b3c-434">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span>

![显示"授予控制权"选项的屏幕截图](media/meeting-policies-give-control.png)

<span data-ttu-id="41b3c-436">如果用户的设置已关闭，则"授予 **控制** "选项不可用。</span><span class="sxs-lookup"><span data-stu-id="41b3c-436">If the setting is turned off for the user, the **Give Control** option isn't available.</span></span>

![显示"授予控制"选项不可用的屏幕截图](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="41b3c-438">让我们看看以下示例。</span><span class="sxs-lookup"><span data-stu-id="41b3c-438">Let's look at the following example.</span></span>

|<span data-ttu-id="41b3c-439">用户</span><span class="sxs-lookup"><span data-stu-id="41b3c-439">User</span></span> |<span data-ttu-id="41b3c-440">会议策略</span><span class="sxs-lookup"><span data-stu-id="41b3c-440">Meeting policy</span></span>  |<span data-ttu-id="41b3c-441">允许参与者授予或请求控制权</span><span class="sxs-lookup"><span data-stu-id="41b3c-441">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="41b3c-442">Daniela</span><span class="sxs-lookup"><span data-stu-id="41b3c-442">Daniela</span></span>   | <span data-ttu-id="41b3c-443">全局</span><span class="sxs-lookup"><span data-stu-id="41b3c-443">Global</span></span>   | <span data-ttu-id="41b3c-444">开</span><span class="sxs-lookup"><span data-stu-id="41b3c-444">On</span></span>       |
|<span data-ttu-id="41b3c-445">法拉尼克</span><span class="sxs-lookup"><span data-stu-id="41b3c-445">Babek</span></span>    | <span data-ttu-id="41b3c-446">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="41b3c-446">Location1MeetingPolicy</span></span>        | <span data-ttu-id="41b3c-447">关</span><span class="sxs-lookup"><span data-stu-id="41b3c-447">Off</span></span>   |

<span data-ttu-id="41b3c-448">Daniela 可以将共享桌面或窗口的控制权授予由"小娜"组织的会议的其他参与者，而"小娜"不能将控制权授予其他参与者。</span><span class="sxs-lookup"><span data-stu-id="41b3c-448">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek whereas Babek can't give control to other participants.</span></span>

<span data-ttu-id="41b3c-449">若要使用 PowerShell 控制谁可以授予控制权或接受控制请求，请使用 AllowParticipantGiveRequestControl cmdlet。</span><span class="sxs-lookup"><span data-stu-id="41b3c-449">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="41b3c-450">若要在共享过程中授予并控制共享内容，双方必须使用 Teams 桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="41b3c-450">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="41b3c-451">如果任何一方在浏览器中运行 Teams，则不支持控制。</span><span class="sxs-lookup"><span data-stu-id="41b3c-451">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="41b3c-452">这是由我们计划修复的一个技术限制造成。</span><span class="sxs-lookup"><span data-stu-id="41b3c-452">This is due to a technical limitation that we're planning to fix.</span></span>

### <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="41b3c-453">允许外部参与者授予或请求控制权</span><span class="sxs-lookup"><span data-stu-id="41b3c-453">Allow an external participant to give or request control</span></span>

<span data-ttu-id="41b3c-454">这是按用户的策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-454">This is a per-user policy.</span></span> <span data-ttu-id="41b3c-455">无论会议组织者设置什么，组织是否为用户设置此集都无法控制外部参与者可以执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="41b3c-455">Whether an organization has this set for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="41b3c-456">此参数控制是否可以向外部参与者提供对共享者屏幕的控制或请求控制权，具体取决于共享者在其组织的会议策略中设置的内容。</span><span class="sxs-lookup"><span data-stu-id="41b3c-456">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span> <span data-ttu-id="41b3c-457">Teams 会议的外部参与者可分类如下：</span><span class="sxs-lookup"><span data-stu-id="41b3c-457">External participants in Teams meetings can be categorized as follows:</span></span>  

- <span data-ttu-id="41b3c-458">匿名用户</span><span class="sxs-lookup"><span data-stu-id="41b3c-458">Anonymous user</span></span>
- <span data-ttu-id="41b3c-459">来宾用户</span><span class="sxs-lookup"><span data-stu-id="41b3c-459">Guest users</span></span>  
- <span data-ttu-id="41b3c-460">B2B 用户</span><span class="sxs-lookup"><span data-stu-id="41b3c-460">B2B user</span></span>
- <span data-ttu-id="41b3c-461">联合用户</span><span class="sxs-lookup"><span data-stu-id="41b3c-461">Federated user</span></span>  

<span data-ttu-id="41b3c-462">联合用户是否可以在共享时向外部用户授予控制权，这由"允许外部参与者授予或 **请求** 其组织中控制设置"控制。</span><span class="sxs-lookup"><span data-stu-id="41b3c-462">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="41b3c-463">若要使用 PowerShell 控制外部参与者是否可以授予控制权或接受控制请求，请使用 AllowExternalParticipantGiveRequestControl cmdlet。</span><span class="sxs-lookup"><span data-stu-id="41b3c-463">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="41b3c-464">允许 PowerPoint 共享</span><span class="sxs-lookup"><span data-stu-id="41b3c-464">Allow PowerPoint sharing</span></span>

<span data-ttu-id="41b3c-465">这是按用户的策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-465">This is a per-user policy.</span></span> <span data-ttu-id="41b3c-466">此设置控制用户是否可以在会议中共享 PowerPoint 幻灯片。</span><span class="sxs-lookup"><span data-stu-id="41b3c-466">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="41b3c-467">外部用户（包括匿名用户、来宾用户和联合用户）继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-467">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="41b3c-468">让我们看看以下示例。</span><span class="sxs-lookup"><span data-stu-id="41b3c-468">Let's look at the following example.</span></span>

|<span data-ttu-id="41b3c-469">用户</span><span class="sxs-lookup"><span data-stu-id="41b3c-469">User</span></span> |<span data-ttu-id="41b3c-470">会议策略</span><span class="sxs-lookup"><span data-stu-id="41b3c-470">Meeting policy</span></span>  |<span data-ttu-id="41b3c-471">允许 PowerPoint 共享</span><span class="sxs-lookup"><span data-stu-id="41b3c-471">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="41b3c-472">Daniela</span><span class="sxs-lookup"><span data-stu-id="41b3c-472">Daniela</span></span>   | <span data-ttu-id="41b3c-473">全局</span><span class="sxs-lookup"><span data-stu-id="41b3c-473">Global</span></span>   | <span data-ttu-id="41b3c-474">开</span><span class="sxs-lookup"><span data-stu-id="41b3c-474">On</span></span>       |
|<span data-ttu-id="41b3c-475">阿兰达</span><span class="sxs-lookup"><span data-stu-id="41b3c-475">Amanda</span></span>   | <span data-ttu-id="41b3c-476">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="41b3c-476">Location1MeetingPolicy</span></span>        | <span data-ttu-id="41b3c-477">关</span><span class="sxs-lookup"><span data-stu-id="41b3c-477">Off</span></span>   |

<span data-ttu-id="41b3c-478">Amanda 不能共享会议中 PowerPoint 幻灯片，即使她是会议组织者。</span><span class="sxs-lookup"><span data-stu-id="41b3c-478">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="41b3c-479">Daniela 可以共享 PowerPoint 幻灯片，即使会议是由 Amanda 组织的。</span><span class="sxs-lookup"><span data-stu-id="41b3c-479">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="41b3c-480">Amanda 可以查看会议中其他人共享的 PowerPoint 幻灯片，即使她无法共享 PowerPoint 幻灯片。</span><span class="sxs-lookup"><span data-stu-id="41b3c-480">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

### <a name="allow-whiteboard"></a><span data-ttu-id="41b3c-481">允许白板</span><span class="sxs-lookup"><span data-stu-id="41b3c-481">Allow whiteboard</span></span>

<span data-ttu-id="41b3c-482">这是按用户的策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-482">This is a per-user policy.</span></span> <span data-ttu-id="41b3c-483">此设置控制用户是否可以在会议中共享白板。</span><span class="sxs-lookup"><span data-stu-id="41b3c-483">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="41b3c-484">外部用户（包括匿名用户、B2B 用户和联合用户）继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-484">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="41b3c-485">让我们看看以下示例。</span><span class="sxs-lookup"><span data-stu-id="41b3c-485">Let's look at the following example.</span></span>

|<span data-ttu-id="41b3c-486">用户</span><span class="sxs-lookup"><span data-stu-id="41b3c-486">User</span></span> |<span data-ttu-id="41b3c-487">会议策略</span><span class="sxs-lookup"><span data-stu-id="41b3c-487">Meeting policy</span></span>  |<span data-ttu-id="41b3c-488">允许白板</span><span class="sxs-lookup"><span data-stu-id="41b3c-488">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="41b3c-489">Daniela</span><span class="sxs-lookup"><span data-stu-id="41b3c-489">Daniela</span></span>   | <span data-ttu-id="41b3c-490">全局</span><span class="sxs-lookup"><span data-stu-id="41b3c-490">Global</span></span>   | <span data-ttu-id="41b3c-491">开</span><span class="sxs-lookup"><span data-stu-id="41b3c-491">On</span></span>       |
|<span data-ttu-id="41b3c-492">阿兰达</span><span class="sxs-lookup"><span data-stu-id="41b3c-492">Amanda</span></span>   | <span data-ttu-id="41b3c-493">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="41b3c-493">Location1MeetingPolicy</span></span>        | <span data-ttu-id="41b3c-494">关</span><span class="sxs-lookup"><span data-stu-id="41b3c-494">Off</span></span>   |

<span data-ttu-id="41b3c-495">Amanda 不能共享会议中的白板，即使她是会议组织者。</span><span class="sxs-lookup"><span data-stu-id="41b3c-495">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="41b3c-496">Daniela 可以共享白板，即使会议是由 Amanda 组织的。</span><span class="sxs-lookup"><span data-stu-id="41b3c-496">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

### <a name="allow-shared-notes"></a><span data-ttu-id="41b3c-497">允许共享笔记</span><span class="sxs-lookup"><span data-stu-id="41b3c-497">Allow shared notes</span></span>

<span data-ttu-id="41b3c-498">这是按用户的策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-498">This is a per-user policy.</span></span> <span data-ttu-id="41b3c-499">此设置控制用户是否可以在会议创建和共享笔记。</span><span class="sxs-lookup"><span data-stu-id="41b3c-499">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="41b3c-500">外部用户（包括匿名用户、B2B 用户和联合用户）继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-500">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="41b3c-501">最多 **包含** 100 位参与者的会议支持"会议笔记"选项卡。</span><span class="sxs-lookup"><span data-stu-id="41b3c-501">The **Meeting Notes** tab is supported in meetings with up to 100 participants.</span></span>

<span data-ttu-id="41b3c-502">让我们看看以下示例。</span><span class="sxs-lookup"><span data-stu-id="41b3c-502">Let's look at the following example.</span></span>

|<span data-ttu-id="41b3c-503">用户</span><span class="sxs-lookup"><span data-stu-id="41b3c-503">User</span></span> |<span data-ttu-id="41b3c-504">会议策略</span><span class="sxs-lookup"><span data-stu-id="41b3c-504">Meeting policy</span></span>  |<span data-ttu-id="41b3c-505">允许共享笔记</span><span class="sxs-lookup"><span data-stu-id="41b3c-505">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="41b3c-506">Daniela</span><span class="sxs-lookup"><span data-stu-id="41b3c-506">Daniela</span></span>   | <span data-ttu-id="41b3c-507">全局</span><span class="sxs-lookup"><span data-stu-id="41b3c-507">Global</span></span>   | <span data-ttu-id="41b3c-508">开</span><span class="sxs-lookup"><span data-stu-id="41b3c-508">On</span></span>       |
|<span data-ttu-id="41b3c-509">阿兰达</span><span class="sxs-lookup"><span data-stu-id="41b3c-509">Amanda</span></span>   | <span data-ttu-id="41b3c-510">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="41b3c-510">Location1MeetingPolicy</span></span> | <span data-ttu-id="41b3c-511">关</span><span class="sxs-lookup"><span data-stu-id="41b3c-511">Off</span></span> |

<span data-ttu-id="41b3c-512">Daniela 可以在 Amanda 的会议中做笔记，而 Amanda 不能在任何会议中做笔记。</span><span class="sxs-lookup"><span data-stu-id="41b3c-512">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>

## <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="41b3c-513">会议策略设置 - 参与者&来宾</span><span class="sxs-lookup"><span data-stu-id="41b3c-513">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="41b3c-514">这些设置控制哪些会议参与者在进入会议之前在大厅中等待，以及允许他们参加会议的参与级别。</span><span class="sxs-lookup"><span data-stu-id="41b3c-514">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="41b3c-515">让匿名人员启动会议</span><span class="sxs-lookup"><span data-stu-id="41b3c-515">Let anonymous people start a meeting</span></span>](#let-anonymous-people-start-a-meeting)
- [<span data-ttu-id="41b3c-516">自动允许人员</span><span class="sxs-lookup"><span data-stu-id="41b3c-516">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="41b3c-517">允许拨入用户绕过大厅</span><span class="sxs-lookup"><span data-stu-id="41b3c-517">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby)
- [<span data-ttu-id="41b3c-518">启用实时字幕</span><span class="sxs-lookup"><span data-stu-id="41b3c-518">Enable live captions</span></span>](#enable-live-captions)
- [<span data-ttu-id="41b3c-519">允许在会议中聊天</span><span class="sxs-lookup"><span data-stu-id="41b3c-519">Allow chat in meetings</span></span>](#allow-chat-in-meetings)

> [!NOTE]
><span data-ttu-id="41b3c-520">加入会议的选项因每个 Teams 组的设置和连接方法而异。</span><span class="sxs-lookup"><span data-stu-id="41b3c-520">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="41b3c-521">如果你的群组有音频会议，并使用它进行连接，请参阅 [音频会议](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="41b3c-521">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="41b3c-522">如果你的 Teams 组没有音频会议，请参阅"在[Teams 中加入会议"。](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)</span><span class="sxs-lookup"><span data-stu-id="41b3c-522">If your Teams group doesn't have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

### <a name="let-anonymous-people-start-a-meeting"></a><span data-ttu-id="41b3c-523">让匿名人员启动会议</span><span class="sxs-lookup"><span data-stu-id="41b3c-523">Let anonymous people start a meeting</span></span>

<span data-ttu-id="41b3c-524">这是每个组织者的策略，允许无领导电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="41b3c-524">This is a per-organizer policy that allows for leaderless dial-in conferencing meetings.</span></span> <span data-ttu-id="41b3c-525">此设置控制拨入用户是否可以在没有组织中经过身份验证的用户出席的情况下加入会议。</span><span class="sxs-lookup"><span data-stu-id="41b3c-525">This setting controls whether dial-in users can join the meeting without an authenticated user from the organization in attendance.</span></span> <span data-ttu-id="41b3c-526">默认情况下，此设置已关闭，这意味着拨入用户将在大厅中等待，直到组织中经过身份验证的用户加入会议。</span><span class="sxs-lookup"><span data-stu-id="41b3c-526">By default, this setting is turned off which means dial-in users will wait in the lobby until an authenticated user from the organization joins the meeting.</span></span>

> [!NOTE]
> <span data-ttu-id="41b3c-527">如果此设置已关闭，并且拨入用户先加入会议并放置在大厅中，则组织用户必须与 Teams 客户端加入会议，以允许用户从大厅进入。</span><span class="sxs-lookup"><span data-stu-id="41b3c-527">If this setting is turned off and a dial-in user joins the meeting first and is placed in the lobby, an organization user must join the meeting with a Teams client to admit the user from the lobby.</span></span> <span data-ttu-id="41b3c-528">拨入用户没有可用的大厅控件。</span><span class="sxs-lookup"><span data-stu-id="41b3c-528">There are no lobby controls available for dialed in users.</span></span>

### <a name="automatically-admit-people"></a><span data-ttu-id="41b3c-529">自动允许人员</span><span class="sxs-lookup"><span data-stu-id="41b3c-529">Automatically admit people</span></span>

<span data-ttu-id="41b3c-530">这是按组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-530">This is a per-organizer policy.</span></span> <span data-ttu-id="41b3c-531">此设置控制用户是直接加入会议，还是等待大厅中，直到经过身份验证的用户获准。</span><span class="sxs-lookup"><span data-stu-id="41b3c-531">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span> <span data-ttu-id="41b3c-532">此设置不适用于拨入用户。</span><span class="sxs-lookup"><span data-stu-id="41b3c-532">This setting does not apply to dial-in users.</span></span>

![显示与大厅中的用户的会议的屏幕截图](media/meeting-policies-lobby.png)

 <span data-ttu-id="41b3c-534">会议组织者可以选择 **会议** 邀请中的"会议选项"，以更改他们计划的每个会议的此设置。</span><span class="sxs-lookup"><span data-stu-id="41b3c-534">Meeting organizers can select **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span>

> [!NOTE]
> <span data-ttu-id="41b3c-535">在会议选项中，设置标记为"谁可以绕过大厅"。</span><span class="sxs-lookup"><span data-stu-id="41b3c-535">In the meeting options the setting is labeled "Who can bypass the lobby".</span></span> <span data-ttu-id="41b3c-536">如果更改任何用户的默认设置，它将应用于该用户组织的所有新会议以及用户未修改会议选项的任何以前会议。</span><span class="sxs-lookup"><span data-stu-id="41b3c-536">If you change the default setting for any user, it will apply to all new meetings organized by that user and any prior meetings where the user didn't modify Meeting options.</span></span>
  
|<span data-ttu-id="41b3c-537">设置值</span><span class="sxs-lookup"><span data-stu-id="41b3c-537">Setting value</span></span>  |<span data-ttu-id="41b3c-538">联接行为</span><span class="sxs-lookup"><span data-stu-id="41b3c-538">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="41b3c-539">**所有人**</span><span class="sxs-lookup"><span data-stu-id="41b3c-539">**Everyone**</span></span>   |<span data-ttu-id="41b3c-540">所有会议参与者都直接加入会议，无需在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="41b3c-540">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="41b3c-541">这包括经过身份验证的用户、来自受信任组织的外部 (联合) 、来宾和匿名用户。</span><span class="sxs-lookup"><span data-stu-id="41b3c-541">This includes authenticated users, external users from trusted organizations (federated), guests, and anonymous users.</span></span>     |
|<span data-ttu-id="41b3c-542">**组织和联盟组织中所有人**</span><span class="sxs-lookup"><span data-stu-id="41b3c-542">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="41b3c-543">组织中经过身份验证的用户（包括来宾用户和受信任组织的用户）直接加入会议，无需在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="41b3c-543">Authenticated users within the organization, including guest users and the users from trusted organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="41b3c-544">匿名用户在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="41b3c-544">Anonymous users wait in the lobby.</span></span>   |
|<span data-ttu-id="41b3c-545">**您的组织中的每个人**</span><span class="sxs-lookup"><span data-stu-id="41b3c-545">**Everyone in your organization**</span></span>    |<span data-ttu-id="41b3c-546">组织中经过身份验证的用户（包括来宾用户）无需在大厅中等待即可直接加入会议。</span><span class="sxs-lookup"><span data-stu-id="41b3c-546">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="41b3c-547">来自受信任组织和匿名用户的用户在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="41b3c-547">Users from trusted organizations and anonymous users wait in the lobby.</span></span> <span data-ttu-id="41b3c-548">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="41b3c-548">This is the default setting.</span></span>           |
|<span data-ttu-id="41b3c-549">**仅组织者**</span><span class="sxs-lookup"><span data-stu-id="41b3c-549">**Organizer only**</span></span>    |<span data-ttu-id="41b3c-550">只有会议组织者可以直接加入会议，而无需在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="41b3c-550">Only meeting organizers can join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="41b3c-551">其他所有人（包括组织中经过身份验证的用户、来宾用户、受信任组织和匿名用户）必须在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="41b3c-551">Everyone else, including authenticated users within the organization, guest users, users from trusted organizations and anonymous users must wait in the lobby.</span></span>           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a><span data-ttu-id="41b3c-552">允许拨入用户绕过大厅</span><span class="sxs-lookup"><span data-stu-id="41b3c-552">Allow dial-in users to bypass the lobby</span></span>

<span data-ttu-id="41b3c-553">这是按组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-553">This is a per-organizer policy.</span></span> <span data-ttu-id="41b3c-554">此设置控制通过电话拨入的人是直接加入会议还是在大厅中等待，而不考虑 **"自动允许人员"** 设置。</span><span class="sxs-lookup"><span data-stu-id="41b3c-554">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span> <span data-ttu-id="41b3c-555">默认情况下，此设置已关闭。</span><span class="sxs-lookup"><span data-stu-id="41b3c-555">By default, this setting is turned off.</span></span> <span data-ttu-id="41b3c-556">当此设置关闭时，拨入用户将在大厅中等待，直到组织用户使用 Teams 客户端加入会议并准许他们加入会议。</span><span class="sxs-lookup"><span data-stu-id="41b3c-556">When this setting is turned off, dial-in users will wait in the lobby until an organization user joins the meeting with a Teams client and admits them.</span></span> <span data-ttu-id="41b3c-557">启用此设置后，当组织用户加入会议时，拨入用户将自动加入会议。</span><span class="sxs-lookup"><span data-stu-id="41b3c-557">When this setting is turned on, dial-in users will automatically join the meeting when an organization user joins the meeting.</span></span>

> [!NOTE]
> <span data-ttu-id="41b3c-558">如果拨入用户在组织用户加入会议之前加入会议，他们将被置于大厅中，直到组织用户使用 Teams 客户端加入会议并准许他们加入会议。</span><span class="sxs-lookup"><span data-stu-id="41b3c-558">If a dial-in user joins a meeting before an organization user joins the meeting, they will be placed in the lobby until an organization user joins the meeting using a Teams client and admits them.</span></span> <span data-ttu-id="41b3c-559">如果更改任何用户的默认设置，它将应用于该用户组织的所有新会议以及用户未修改会议选项的任何以前会议。</span><span class="sxs-lookup"><span data-stu-id="41b3c-559">If you change the default setting for any user, it will apply to all new meetings organized by that user and any prior meetings where the user didn't modify Meeting options.</span></span>

### <a name="enable-live-captions"></a><span data-ttu-id="41b3c-560">启用实时字幕</span><span class="sxs-lookup"><span data-stu-id="41b3c-560">Enable live captions</span></span>

<span data-ttu-id="41b3c-561">这是按用户的策略，在会议期间适用。</span><span class="sxs-lookup"><span data-stu-id="41b3c-561">This is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="41b3c-562">此设置控制" **启用实时** 字幕"选项是否可供用户在用户参加的会议中打开和关闭实时字幕。</span><span class="sxs-lookup"><span data-stu-id="41b3c-562">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![显示"启用实时字幕"选项的屏幕截图](media/meeting-policies-live-captions.png)

|<span data-ttu-id="41b3c-564">设置值</span><span class="sxs-lookup"><span data-stu-id="41b3c-564">Setting value</span></span> |<span data-ttu-id="41b3c-565">行为</span><span class="sxs-lookup"><span data-stu-id="41b3c-565">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="41b3c-566">**已禁用，但用户可以替代**</span><span class="sxs-lookup"><span data-stu-id="41b3c-566">**Disabled but the user can override**</span></span>     | <span data-ttu-id="41b3c-567">在会议期间，用户不会自动打开实时字幕。</span><span class="sxs-lookup"><span data-stu-id="41b3c-567">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="41b3c-568">用户将看到"在溢出菜单上打开实时字幕 **" (...)** 菜单以将其打开。</span><span class="sxs-lookup"><span data-stu-id="41b3c-568">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="41b3c-569">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="41b3c-569">This is the default setting.</span></span> |
|<span data-ttu-id="41b3c-570">**已禁用**</span><span class="sxs-lookup"><span data-stu-id="41b3c-570">**Disabled**</span></span>     | <span data-ttu-id="41b3c-571">会议期间为用户禁用了实时字幕。</span><span class="sxs-lookup"><span data-stu-id="41b3c-571">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="41b3c-572">用户没有启用它们的选项。</span><span class="sxs-lookup"><span data-stu-id="41b3c-572">The user doesn't have the option to turn them on.</span></span>          |

<span data-ttu-id="41b3c-573"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="41b3c-573"><a name="bkcontentsharing"> </a></span></span>

### <a name="allow-chat-in-meetings"></a><span data-ttu-id="41b3c-574">允许在会议中聊天</span><span class="sxs-lookup"><span data-stu-id="41b3c-574">Allow chat in meetings</span></span>

<span data-ttu-id="41b3c-575">这是每个参与者的设置。</span><span class="sxs-lookup"><span data-stu-id="41b3c-575">This is a per-participant setting.</span></span> <span data-ttu-id="41b3c-576">此设置控制是否在用户的会议中允许会议聊天。</span><span class="sxs-lookup"><span data-stu-id="41b3c-576">This setting controls whether meeting chat is allowed in the user's meeting.</span></span>

<span data-ttu-id="41b3c-577"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="41b3c-577"><a name="bkparticipantsandguests"> </a></span></span>

## <a name="meeting-policy-settings---designated-presenter-role-mode"></a><span data-ttu-id="41b3c-578">会议策略设置 - 指定的演示者角色模式</span><span class="sxs-lookup"><span data-stu-id="41b3c-578">Meeting policy settings - Designated presenter role mode</span></span>

<span data-ttu-id="41b3c-579">这是按用户的策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-579">This is a per-user policy.</span></span> <span data-ttu-id="41b3c-580">此设置允许您在 Teams 客户端的会议选项中更改"谁可以展示 **？"** 设置的默认值。 </span><span class="sxs-lookup"><span data-stu-id="41b3c-580">This setting lets you change the default value of the **Who can present?** setting in **Meeting options** in the Teams client.</span></span> <span data-ttu-id="41b3c-581">此策略设置会影响所有会议，包括"现在开会"会议。</span><span class="sxs-lookup"><span data-stu-id="41b3c-581">This policy setting affects all meetings, including Meet Now meetings.</span></span>

<span data-ttu-id="41b3c-582">" **谁可以演示？"** 设置允许会议组织者选择谁可以是会议中的演示者。</span><span class="sxs-lookup"><span data-stu-id="41b3c-582">The **Who can present?** setting lets meeting organizers choose who can be presenters in a meeting.</span></span> <span data-ttu-id="41b3c-583">若要了解有关详细信息，请参阅["更改 Teams 会议的参与者设置"](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e)和["Teams 会议的角色"。](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)</span><span class="sxs-lookup"><span data-stu-id="41b3c-583">To learn more, see [Change participant settings for a Teams meeting](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) and [Roles in a Teams meeting](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).</span></span>

<span data-ttu-id="41b3c-584">可以使用 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有的 Teams 会议策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-584">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="41b3c-585">或者，使用 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet 创建新的 Teams 会议策略并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="41b3c-585">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="41b3c-586">若要在 Teams 中指定"谁可以展示 **？"** 设置的默认值，将 **SpecifyedPresenterRoleMode** 参数设置为以下参数之一：</span><span class="sxs-lookup"><span data-stu-id="41b3c-586">To specify the default value of the **Who can present?** setting in Teams, set the **DesignatedPresenterRoleMode** parameter to one of the following:</span></span>

- <span data-ttu-id="41b3c-587">**EveryoneUserOverride：** 所有会议参与者都可以是演示者。</span><span class="sxs-lookup"><span data-stu-id="41b3c-587">**EveryoneUserOverride**:  All meeting participants can be presenters.</span></span> <span data-ttu-id="41b3c-588">此值为默认值。</span><span class="sxs-lookup"><span data-stu-id="41b3c-588">This is the default value.</span></span> <span data-ttu-id="41b3c-589">此参数对应于 Teams **中的 Everyone** 设置。</span><span class="sxs-lookup"><span data-stu-id="41b3c-589">This parameter corresponds to the **Everyone** setting in Teams.</span></span>
- <span data-ttu-id="41b3c-590">**EveryoneInCompanyUserOverride：** 组织中经过身份验证的用户（包括来宾用户）可以是演示者。</span><span class="sxs-lookup"><span data-stu-id="41b3c-590">**EveryoneInCompanyUserOverride**: Authenticated users in the organization, including guest users, can be presenters.</span></span> <span data-ttu-id="41b3c-591">此参数对应于 Teams **中的组织人员** 设置。</span><span class="sxs-lookup"><span data-stu-id="41b3c-591">This parameter corresponds to the **People in my organization** setting in Teams.</span></span>
- <span data-ttu-id="41b3c-592">**OrganizerOnlyUserOverride：** 只有会议组织者才能成为演示者，所有会议参与者都将被指定为与会者。</span><span class="sxs-lookup"><span data-stu-id="41b3c-592">**OrganizerOnlyUserOverride**: Only the meeting organizer can be a presenter and all meeting participants are designated as attendees.</span></span> <span data-ttu-id="41b3c-593">此参数对应于 Teams **中的"仅我** "设置。</span><span class="sxs-lookup"><span data-stu-id="41b3c-593">This parameter corresponds to the **Only me** setting in Teams.</span></span>

<span data-ttu-id="41b3c-594">此外，还可以在 Teams 管理中心编辑此策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-594">Additionally, you can edit this policy in the Teams admin center.</span></span>

![Teams 管理中心的屏幕截图](media/designated-presenter-role.png)

<span data-ttu-id="41b3c-596">请记住，设置默认值后，会议组织者仍然可以在 Teams 中更改此设置，并选择谁可以在他们安排的会议中参加。</span><span class="sxs-lookup"><span data-stu-id="41b3c-596">Keep in mind that after you set the default value, meeting organizers can still change this setting in Teams and choose who can present in the meetings that they schedule.</span></span>

## <a name="meeting-policy-settings---meeting-attendance-report"></a><span data-ttu-id="41b3c-597">会议策略设置 - 会议出席报告</span><span class="sxs-lookup"><span data-stu-id="41b3c-597">Meeting policy settings - Meeting attendance report</span></span>

<span data-ttu-id="41b3c-598">这是按用户的策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-598">This is a per-user policy.</span></span> <span data-ttu-id="41b3c-599">此设置控制会议组织者是否可以下载 [会议出席报告](teams-analytics-and-reports/meeting-attendance-report.md)。</span><span class="sxs-lookup"><span data-stu-id="41b3c-599">This setting controls whether meeting organizers can download the [meeting attendance report](teams-analytics-and-reports/meeting-attendance-report.md).</span></span>

<span data-ttu-id="41b3c-600">目前，只能使用 PowerShell 配置此策略设置。</span><span class="sxs-lookup"><span data-stu-id="41b3c-600">Currently, you can only use PowerShell to configure this policy setting.</span></span> <span data-ttu-id="41b3c-601">可以使用 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有的 Teams 会议策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-601">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="41b3c-602">或者，使用 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet 创建新的 Teams 会议策略并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="41b3c-602">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="41b3c-603">若要使会议组织者能够下载会议出席情况报告，将 **AllowEngagementReport** 参数设置为 **"已启用"。**</span><span class="sxs-lookup"><span data-stu-id="41b3c-603">To enable a meeting organizer to download the meeting attendance report, set the **AllowEngagementReport** parameter  to **Enabled**.</span></span> <span data-ttu-id="41b3c-604">启用后，下载报表的选项会显示在"参与者 **"窗格中** 。</span><span class="sxs-lookup"><span data-stu-id="41b3c-604">When enabled, the option to download the report is displayed in the **Participants** pane.</span></span>

<span data-ttu-id="41b3c-605">若要防止会议组织者下载报告，将参数设置为 **"已禁用"。**</span><span class="sxs-lookup"><span data-stu-id="41b3c-605">To prevent a meeting organizer from downloading the report, set the parameter to **Disabled**.</span></span> <span data-ttu-id="41b3c-606">默认情况下，此设置已禁用，并且下载报表的选项不可用。</span><span class="sxs-lookup"><span data-stu-id="41b3c-606">By default, this setting is disabled and the option to download the report isn't available.</span></span>

## <a name="meeting-policy-settings---meeting-provider-for-islands-mode"></a><span data-ttu-id="41b3c-607">会议策略设置 - 群岛模式的会议提供商</span><span class="sxs-lookup"><span data-stu-id="41b3c-607">Meeting policy settings - Meeting provider for Islands mode</span></span>

<span data-ttu-id="41b3c-608">这是按用户的策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-608">This is a per-user policy.</span></span> <span data-ttu-id="41b3c-609">此设置控制哪些 Outlook 会议加载项用于位于 *群岛模式的用户*。</span><span class="sxs-lookup"><span data-stu-id="41b3c-609">This setting controls which Outlook meeting add-in is used for *users who are in Islands mode*.</span></span> <span data-ttu-id="41b3c-610">你可以指定用户是只能使用 Team 会议加载项，还是可同时使用 Teams 会议加载项和 Skype for Business 会议加载项来在 Outlook 中安排会议。</span><span class="sxs-lookup"><span data-stu-id="41b3c-610">You can specify whether users can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins to schedule meetings in Outlook.</span></span>

<span data-ttu-id="41b3c-611">你只能将此策略应用于处于孤岛模式且其 Teams 会议策略中的 **AllowOutlookAddIn** 参数设置为 **True** 的用户。</span><span class="sxs-lookup"><span data-stu-id="41b3c-611">You can only apply this policy to users who are in Islands mode and have the **AllowOutlookAddIn** parameter set to **True** in their Teams meeting policy.</span></span>

<span data-ttu-id="41b3c-612">目前，只能使用 PowerShell 设置此策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-612">Currently, you can only use PowerShell to set this policy.</span></span> <span data-ttu-id="41b3c-613">可以使用 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有的 Teams 会议策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-613">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="41b3c-614">或者，使用 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet 创建新的 Teams 会议策略并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="41b3c-614">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="41b3c-615">若要指定希望哪些会议加载项可供用户使用，请设置 **PreferredMeetingProviderForIslandsMode** 参数，如下所示：</span><span class="sxs-lookup"><span data-stu-id="41b3c-615">To specify which meeting add-in you want to be available to users, set the **PreferredMeetingProviderForIslandsMode** parameter as follows:</span></span>

- <span data-ttu-id="41b3c-616">将参数设置为 **TeamsAndSfB，** 以在 Outlook 中同时启用 Teams 会议加载项和 Skype for Business 加载项。</span><span class="sxs-lookup"><span data-stu-id="41b3c-616">Set the parameter to **TeamsAndSfB** to enable both the Teams Meeting add-in and Skype for Business add-in in Outlook.</span></span> <span data-ttu-id="41b3c-617">此值为默认值。</span><span class="sxs-lookup"><span data-stu-id="41b3c-617">This is the default value.</span></span>
- <span data-ttu-id="41b3c-618">将参数设置为 **Teams** 以在 Outlook 中仅启用 Teams 会议加载项。</span><span class="sxs-lookup"><span data-stu-id="41b3c-618">Set the parameter to **Teams** to enable only the Teams Meeting add-in in Outlook.</span></span> <span data-ttu-id="41b3c-619">此策略设置可确保所有将来的会议都有 Teams 会议加入链接。</span><span class="sxs-lookup"><span data-stu-id="41b3c-619">This policy setting ensures that all future meetings have a Teams meeting join link.</span></span> <span data-ttu-id="41b3c-620">它不会将现有 Skype for Business 会议加入链接迁移到 Teams。</span><span class="sxs-lookup"><span data-stu-id="41b3c-620">It doesn't migrate existing Skype for Business meeting join links to Teams.</span></span> <span data-ttu-id="41b3c-621">此策略设置不会影响 Skype for Business 中的状态、聊天、PSTN 呼叫或其他任何功能，这意味着用户将继续使用 Skype for Business 实现这些功能。</span><span class="sxs-lookup"><span data-stu-id="41b3c-621">This policy setting doesn't affect presence, chat, PSTN calling, or any other capabilities in Skype for Business, which means that users will continue to use Skype for Business for these capabilities.</span></span>

  <span data-ttu-id="41b3c-622">如果将参数设置为 **Teams，** 然后切换回 **TeamsAndSfB，** 则两个会议加载项都已启用。</span><span class="sxs-lookup"><span data-stu-id="41b3c-622">If you set the parameter to **Teams**, and then switch back to **TeamsAndSfB**, both meeting add-ins are enabled.</span></span> <span data-ttu-id="41b3c-623">现有 Teams 会议 **加入链接** 不会迁移到 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="41b3c-623">Existing Teams meeting join links **won't** be migrated to Skype for Business.</span></span> <span data-ttu-id="41b3c-624">只有更改后安排的 Skype for Business 会议才具有 Skype for Business 会议加入链接。</span><span class="sxs-lookup"><span data-stu-id="41b3c-624">Only Skype for Business meetings scheduled after the change will have a Skype for Business meeting join link.</span></span>

## <a name="meeting-policy-settings---video-filters-mode"></a><span data-ttu-id="41b3c-625">会议策略设置 - 视频筛选器模式</span><span class="sxs-lookup"><span data-stu-id="41b3c-625">Meeting policy settings - Video filters mode</span></span>

<span data-ttu-id="41b3c-626">这是按用户的策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-626">This is a per-user policy.</span></span> <span data-ttu-id="41b3c-627">此设置控制用户是否可以在会议中自定义其视频背景。</span><span class="sxs-lookup"><span data-stu-id="41b3c-627">This setting controls whether users can customize their video background in a meeting.</span></span>

<span data-ttu-id="41b3c-628">目前，只能使用 PowerShell 设置此策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-628">Currently, you can only use PowerShell to set this policy.</span></span> <span data-ttu-id="41b3c-629">可以使用 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有的 Teams 会议策略。</span><span class="sxs-lookup"><span data-stu-id="41b3c-629">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="41b3c-630">或者，使用 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet 创建新的 Teams 会议策略，然后将该策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="41b3c-630">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet, and then assign the policy to users.</span></span>

<span data-ttu-id="41b3c-631">若要指定用户是否可以在会议中自定义其视频背景，请设置 **VideoFiltersMode** 参数，如下所示：</span><span class="sxs-lookup"><span data-stu-id="41b3c-631">To specify whether users can customize their video background in a meeting, set the **VideoFiltersMode** parameter as follows:</span></span>

|<span data-ttu-id="41b3c-632">在 PowerShell 中设置值</span><span class="sxs-lookup"><span data-stu-id="41b3c-632">Setting value in PowerShell</span></span> |<span data-ttu-id="41b3c-633">行为</span><span class="sxs-lookup"><span data-stu-id="41b3c-633">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="41b3c-634">**NoFilters**</span><span class="sxs-lookup"><span data-stu-id="41b3c-634">**NoFilters**</span></span>     |<span data-ttu-id="41b3c-635">用户无法自定义其视频背景。</span><span class="sxs-lookup"><span data-stu-id="41b3c-635">User can't customize their video background.</span></span>|
|<span data-ttu-id="41b3c-636">**BlurOnly**</span><span class="sxs-lookup"><span data-stu-id="41b3c-636">**BlurOnly**</span></span>     |<span data-ttu-id="41b3c-637">用户可以选择模糊其视频背景。</span><span class="sxs-lookup"><span data-stu-id="41b3c-637">User has the option to blur their video background.</span></span> |
|<span data-ttu-id="41b3c-638">**BlurandDefaultBackgrounds**</span><span class="sxs-lookup"><span data-stu-id="41b3c-638">**BlurandDefaultBackgrounds**</span></span>     |<span data-ttu-id="41b3c-639">用户可以选择模糊其视频背景，或者从用作背景的默认图像集中选择。</span><span class="sxs-lookup"><span data-stu-id="41b3c-639">User has the option to blur their video background or choose from the default set of images to use as their background.</span></span> |
|<span data-ttu-id="41b3c-640">**AllFilters**</span><span class="sxs-lookup"><span data-stu-id="41b3c-640">**AllFilters**</span></span>     |<span data-ttu-id="41b3c-641">用户可以选择模糊其视频背景、从默认图像集选择或上传自定义图像以用作背景。</span><span class="sxs-lookup"><span data-stu-id="41b3c-641">User has the option to blur their video background, choose from the default set of images, or upload custom images to use as their background.</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="41b3c-642">Teams 不会筛选用户上传的图像。</span><span class="sxs-lookup"><span data-stu-id="41b3c-642">Images uploaded by users aren't screened by Teams.</span></span> <span data-ttu-id="41b3c-643">使用 **AllFilters** 设置时，应制定内部组织策略，防止用户上传冒犯性或不适当图像，或组织没有权限用于 Teams 会议背景的图像。</span><span class="sxs-lookup"><span data-stu-id="41b3c-643">When you use the **AllFilters** setting, you should have internal organization policies to prevent users from uploading offensive or inappropriate images, or images your organization don't have rights to use for Teams meeting backgrounds.</span></span>

> [!NOTE]
> <span data-ttu-id="41b3c-644">这些功能不可用于所有 Teams 客户端。</span><span class="sxs-lookup"><span data-stu-id="41b3c-644">These features are not available for all Teams clients.</span></span> <span data-ttu-id="41b3c-645">有关详细信息，请参阅会议和实时 _活动中_ 的视频 [和背景标题](https://support.microsoft.com/office/meetings-and-live-events-5c3e0646-dc37-45ad-84a4-1666fac62d4e)。</span><span class="sxs-lookup"><span data-stu-id="41b3c-645">For more information, see the _Video and backgrounds_ title in [Meetings and live events](https://support.microsoft.com/office/meetings-and-live-events-5c3e0646-dc37-45ad-84a4-1666fac62d4e).</span></span>

## <a name="meeting-policy-settings---meeting-reactions"></a><span data-ttu-id="41b3c-646">会议策略设置 - 会议回应</span><span class="sxs-lookup"><span data-stu-id="41b3c-646">Meeting policy settings - Meeting reactions</span></span>

<span data-ttu-id="41b3c-647">AllowMeetingReactions 设置只能使用 PowerShell 应用。</span><span class="sxs-lookup"><span data-stu-id="41b3c-647">The AllowMeetingReactions setting can only be applied using PowerShell.</span></span> <span data-ttu-id="41b3c-648">无法从 Teams 管理中心打开或关闭 AllowMeetingReactions。</span><span class="sxs-lookup"><span data-stu-id="41b3c-648">There is no option to toggle AllowMeetingReactions on or off from the Teams admin center.</span></span>

<span data-ttu-id="41b3c-649">会议回应默认为"关闭"。</span><span class="sxs-lookup"><span data-stu-id="41b3c-649">Meeting reactions are Off by default.</span></span> <span data-ttu-id="41b3c-650">关闭用户的反应并不意味着用户无法安排在会议中使用回应。</span><span class="sxs-lookup"><span data-stu-id="41b3c-650">Turning off reactions for a user doesn't mean that a user can't use reactions in meetings they schedule.</span></span> <span data-ttu-id="41b3c-651">无论默认设置如何，会议组织者仍可打开会议选项页面中的反应。</span><span class="sxs-lookup"><span data-stu-id="41b3c-651">The meeting organizer can still turn on reactions from the meeting option page, regardless of the default setting.</span></span>

## <a name="related-topics"></a><span data-ttu-id="41b3c-652">相关主题</span><span class="sxs-lookup"><span data-stu-id="41b3c-652">Related topics</span></span>

- [<span data-ttu-id="41b3c-653">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="41b3c-653">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="41b3c-654">向 Teams 中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="41b3c-654">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="41b3c-655">从用户中删除 RestrictedAnonymousAccess Teams 会议策略</span><span class="sxs-lookup"><span data-stu-id="41b3c-655">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)
