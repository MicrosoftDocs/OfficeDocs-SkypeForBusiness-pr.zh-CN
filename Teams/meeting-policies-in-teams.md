---
title: 管理会议策略
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Priority
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
description: 了解如何在 Teams 中管理会议策略设置。 使用策略设置来控制用户安排会议参与者可用的功能。
ms.openlocfilehash: 09d821eb4a0ae6f1315ff5ff817c4b702512a974
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282789"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="a9e6a-104">管理 Teams 中的会议策略</span><span class="sxs-lookup"><span data-stu-id="a9e6a-104">Manage meeting policies in Teams</span></span>

::: zone target="docs"
<span data-ttu-id="a9e6a-105">使用会议策略来控制用户在组织中安排会议中对会议参与者可用的功能。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-105">Use meeting policies to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="a9e6a-106">可以使用自动创建的全局 (默认整个组织) 策略，也可以创建和分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-106">You can use the global (Org-wide default) policy that's automatically created or create and assign custom policies.</span></span> <span data-ttu-id="a9e6a-107">可以在 Microsoft Teams 管理中心内或使用 [PowerShell](teams-powershell-overview.md) 管理会议策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-107">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a9e6a-108">有关使用角色管理会议演示者和与会者权限的信息，请参阅 [Teams 会议角色](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-108">For information about using roles to manage the permissions of meeting presenters and attendees, see [Roles in a Teams meeting](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).</span></span>

<span data-ttu-id="a9e6a-109">可以通过以下方式实施策略，这些策略会在会议开始前、会议期间或会议结束后影响用户的会议体验。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-109">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="a9e6a-110">实施类型</span><span class="sxs-lookup"><span data-stu-id="a9e6a-110">Implementation type</span></span>  |<span data-ttu-id="a9e6a-111">说明</span><span class="sxs-lookup"><span data-stu-id="a9e6a-111">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="a9e6a-112">按组织者</span><span class="sxs-lookup"><span data-stu-id="a9e6a-112">Per-organizer</span></span>    |<span data-ttu-id="a9e6a-113">如果你实现按组织者策略，所有会议参加者都会继承组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-113">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="a9e6a-114">例如， **自动允许人员** 为按组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-114">For example, **Automatically admit people** is a per-organizer policy.</span></span> <span data-ttu-id="a9e6a-115">它控制用户是直接加入会议还是在大厅里等待由分配策略的用户安排的会议。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-115">It controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="a9e6a-116">按用户</span><span class="sxs-lookup"><span data-stu-id="a9e6a-116">Per-user</span></span>    |<span data-ttu-id="a9e6a-117">实施按用户策略时，只有每用户策略适用于限制组织者和/或会议参与者的某些功能。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-117">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="a9e6a-118">例如， **“在频道中允许立即开会”** 是按用户策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-118">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="a9e6a-119">按组织者和按用户</span><span class="sxs-lookup"><span data-stu-id="a9e6a-119">Per-organizer and per-user</span></span>     |<span data-ttu-id="a9e6a-120">当实施按组织者和按用户策略的组合时，会根据会议参与者的策略和组织者的策略对其进行某些功能限制。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-120">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="a9e6a-121">例如，**“允许云录制”** 是按组织者和按用户策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-121">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="a9e6a-122">打开此设置以允许用户开始和停止录制。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-122">Turn on this setting to allow users to start and stop a recording.</span></span>

<span data-ttu-id="a9e6a-123">可编辑全局策略中的设置，或创建和分配一个或多个自定义策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-123">You can edit the settings in the global policy or create and assign one or more custom policies.</span></span> <span data-ttu-id="a9e6a-124">除非创建并指定一个自定义策略，否则用户将获得全局策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-124">Users will get the global policy unless you create and assign a custom policy.</span></span>

> [!NOTE]
> <span data-ttu-id="a9e6a-125">如果用户启用了音频会议许可或允许用户进行音频会议，则会议详情按钮将可用，否则，会议详情将不可用。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-125">Meeting details button will be available if a user has the audio conference licenses enabled or the user is allow for audio conferencing, if not, the meeting details will not be available.</span></span>

## <a name="create-a-custom-meeting-policy"></a><span data-ttu-id="a9e6a-126">创建自定义会议策略</span><span class="sxs-lookup"><span data-stu-id="a9e6a-126">Create a custom meeting policy</span></span>

1. <span data-ttu-id="a9e6a-127">在 Microsoft Teams 管理员中心的左侧导航中，转到 **“会议”** > **“会议策略”**。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-127">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="a9e6a-128">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-128">Select **Add**.</span></span>
3. <span data-ttu-id="a9e6a-129">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-129">Enter a name and description for the policy.</span></span> <span data-ttu-id="a9e6a-130">名称不能包含特殊字符或超过 64 个字符。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-130">The name can't contain special characters or be longer than 64 characters.</span></span>
4. <span data-ttu-id="a9e6a-131">选择想要的设置。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-131">Choose the settings that you want.</span></span>
5. <span data-ttu-id="a9e6a-132">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-132">Select **Save**.</span></span>

<span data-ttu-id="a9e6a-133">例如，假设你有一组用户并且你想要限制这组用户的会议所需的带宽量。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-133">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="a9e6a-134">你要创建新的自定义策略并命名为“带宽限制”，然后禁用以下设置：</span><span class="sxs-lookup"><span data-stu-id="a9e6a-134">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="a9e6a-135">在“音频和视频”中：</span><span class="sxs-lookup"><span data-stu-id="a9e6a-135">Under **Audio & video**:</span></span>

- <span data-ttu-id="a9e6a-136">禁用“允许云录制”。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-136">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="a9e6a-137">禁用“允许 IP 视频”。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-137">Turn off Allow IP video.</span></span>

<span data-ttu-id="a9e6a-138">在“内容共享”中：</span><span class="sxs-lookup"><span data-stu-id="a9e6a-138">Under **Content sharing**:</span></span>

- <span data-ttu-id="a9e6a-139">禁用屏幕共享模式。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-139">Disable screen sharing mode.</span></span>
- <span data-ttu-id="a9e6a-140">禁用“允许白板”。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-140">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="a9e6a-141">禁用“允许共享笔记”。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-141">Turn off Allow shared notes.</span></span>

<span data-ttu-id="a9e6a-142">然后将此策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-142">Then assign the policy to the users.</span></span>

## <a name="edit-a-meeting-policy"></a><span data-ttu-id="a9e6a-143">编辑会议策略</span><span class="sxs-lookup"><span data-stu-id="a9e6a-143">Edit a meeting policy</span></span>

<span data-ttu-id="a9e6a-144">可以编辑全局策略和创建的任何自定义策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-144">You can edit the global policy and any custom policies that you create.</span></span>

1. <span data-ttu-id="a9e6a-145">在 Microsoft Teams 管理员中心的左侧导航中，转到 **“会议”** > **“会议策略”**。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-145">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="a9e6a-146">通过单击策略名称的左侧选择策略，然后选择 **“编辑”**。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-146">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>
3. <span data-ttu-id="a9e6a-147">在此处根据需要进行更改。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-147">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="a9e6a-148">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-148">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="a9e6a-149">一次只能向一个用户分配一个会议策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-149">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="a9e6a-150">将会议策略分配给用户</span><span class="sxs-lookup"><span data-stu-id="a9e6a-150">Assign a meeting policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> <span data-ttu-id="a9e6a-151">如果已将它分配给用户，则无法删除该策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-151">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="a9e6a-152">必须首先为所有受影响的用户指定不同的策略，然后才能删除原来的策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-152">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="a9e6a-153">会议策略设置</span><span class="sxs-lookup"><span data-stu-id="a9e6a-153">Meeting policy settings</span></span>

<span data-ttu-id="a9e6a-154">在 **“会议策略”** 页面上选择现有策略，或选择 **“添加”** 以添加新策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-154">Select an existing policy on the **Meeting policies** page or select **Add** to add a new policy.</span></span> <span data-ttu-id="a9e6a-155">为以下内容配置设置。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-155">Configure settings for the following.</span></span>

- [<span data-ttu-id="a9e6a-156">常规</span><span class="sxs-lookup"><span data-stu-id="a9e6a-156">General</span></span>](#meeting-policy-settings---general)
- [<span data-ttu-id="a9e6a-157">音频和视频</span><span class="sxs-lookup"><span data-stu-id="a9e6a-157">Audio & video</span></span>](#meeting-policy-settings---audio--video)
- [<span data-ttu-id="a9e6a-158">内容共享</span><span class="sxs-lookup"><span data-stu-id="a9e6a-158">Content sharing</span></span>](#meeting-policy-settings---content-sharing)
- [<span data-ttu-id="a9e6a-159">参与者和来宾</span><span class="sxs-lookup"><span data-stu-id="a9e6a-159">Participants & guests</span></span>](#meeting-policy-settings---participants--guests)

::: zone-end

<span data-ttu-id="a9e6a-160"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="a9e6a-160"><a name="bkgeneral"> </a></span></span>

## <a name="meeting-policy-settings---general"></a><span data-ttu-id="a9e6a-161">会议策略设置 - 常规</span><span class="sxs-lookup"><span data-stu-id="a9e6a-161">Meeting policy settings - General</span></span>

- [<span data-ttu-id="a9e6a-162">允许在频道中立即开会</span><span class="sxs-lookup"><span data-stu-id="a9e6a-162">Allow Meet now in channels</span></span>](#allow-meet-now-in-channels)
- [<span data-ttu-id="a9e6a-163">允许 Outlook 加载项</span><span class="sxs-lookup"><span data-stu-id="a9e6a-163">Allow the Outlook add-in</span></span>](#allow-the-outlook-add-in)
- [<span data-ttu-id="a9e6a-164">允许频道会议安排</span><span class="sxs-lookup"><span data-stu-id="a9e6a-164">Allow channel meeting scheduling</span></span>](#allow-channel-meeting-scheduling)
- [<span data-ttu-id="a9e6a-165">允许安排私人会议</span><span class="sxs-lookup"><span data-stu-id="a9e6a-165">Allow scheduling private meetings</span></span>](#allow-scheduling-private-meetings)
- [<span data-ttu-id="a9e6a-166">允许在私人会议中立即开会</span><span class="sxs-lookup"><span data-stu-id="a9e6a-166">Allow Meet now in private meetings</span></span>](#allow-meet-now-in-private-meetings)

### <a name="allow-meet-now-in-channels"></a><span data-ttu-id="a9e6a-167">允许在频道中立即开会</span><span class="sxs-lookup"><span data-stu-id="a9e6a-167">Allow Meet now in channels</span></span>

<span data-ttu-id="a9e6a-168">允许 **立即开会** 是按用户策略，在会议开始之前适用。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-168">Allow **Meet now** is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="a9e6a-169">此设置可控制用户是否可以在 Teams 频道中启动非计划会议。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-169">This setting controls whether a user can start an unplanned meeting in a Teams channel.</span></span> <span data-ttu-id="a9e6a-170">如果打开此设置，用户可以选择 **“会议”** 按钮开始非计划的会议或在频道中安排会议。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-170">If you turn on this setting, users can select the **Meet** button to start an unplanned meeting or schedule a meeting in the channel.</span></span> <span data-ttu-id="a9e6a-171">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-171">The default value is True.</span></span>

![截图显示消息下方的 “立即开会” 图标](media/meeting-policies-meet-now.png)

### <a name="allow-the-outlook-add-in"></a><span data-ttu-id="a9e6a-173">允许 Outlook 加载项</span><span class="sxs-lookup"><span data-stu-id="a9e6a-173">Allow the Outlook add-in</span></span>

<span data-ttu-id="a9e6a-174">允许 Outlook 加载项是按用户的策略，在会议开始前适用。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-174">Allow the Outlook add-in is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="a9e6a-175">此设置控制是否可以从 Outlook (Windows、Mac、Web和移动设备) 内安排 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-175">This setting controls whether Teams meetings can be scheduled from within Outlook (Windows, Mac, web, and mobile).</span></span>

![截图显示了安排新会议的能力](media/meeting-policies-outlook-add-in.png)

<span data-ttu-id="a9e6a-177">如果关闭此功能，用户将无法进行日程安排。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-177">If you turn off this feature, users are unable to schedule.</span></span> <span data-ttu-id="a9e6a-178">当他们在 Outlook 中创建一个新会议时进行 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-178">Teams meetings when they create a new meeting in Outlook.</span></span> <span data-ttu-id="a9e6a-179">例如，在 Windows 上的 Outlook 中，**“新 Teams 会议”** 选项不会显示在功能区中。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-179">For example, in Outlook on Windows, the **New Teams Meeting** option won't show up in the ribbon.</span></span>

### <a name="allow-channel-meeting-scheduling"></a><span data-ttu-id="a9e6a-180">允许安排频道会议</span><span class="sxs-lookup"><span data-stu-id="a9e6a-180">Allow channel meeting scheduling</span></span>

<span data-ttu-id="a9e6a-181">使用现有的 AllowChannelMeetingScheduling 策略来控制可以在团队频道日历上创建的事件类型。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-181">Use the existing AllowChannelMeetingScheduling policy to control the types of events that can be created on the team channel calendars.</span></span> <span data-ttu-id="a9e6a-182">这是按用户政策，在会议开始前适用。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-182">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="a9e6a-183">此设置控制用户是否可以在 Teams 频道中安排会议。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-183">This setting controls whether users can schedule a meeting in a Teams channel.</span></span> <span data-ttu-id="a9e6a-184">默认情况下，此设置已启动。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-184">By default, this setting is turned on.</span></span>

<span data-ttu-id="a9e6a-185">如果该策略关闭，用户就无法创建新频道会议。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-185">If this policy is turned off, users can't create new channel meetings.</span></span> <span data-ttu-id="a9e6a-186">但是，现有的频道会议可以由活动的组织者进行编辑。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-186">However, existing channel meetings can be edited by the organizer of the event.</span></span>

<span data-ttu-id="a9e6a-187">将禁用会议日程安排。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-187">Schedule a meeting will be disabled.</span></span>

 ![Teams 中的 “安排会议” 选项](media/schedule-meeting-option.png)

<span data-ttu-id="a9e6a-189">将禁用“频道选择”。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-189">Channel selection is disabled.</span></span>

![“日历选项”，用于选择要安排会议的频道。](media/meeting-policies-select-a-channel-to-meet-in.png)

<span data-ttu-id="a9e6a-191">在频道公告页面上，将禁用以下功能:</span><span class="sxs-lookup"><span data-stu-id="a9e6a-191">In the channel posts page, the following features will be disabled:</span></span>

- <span data-ttu-id="a9e6a-192">在频道回复撰写框中的 **“安排会议”** 按钮。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-192">**Schedule a meeting** button on the channel reply compose box.</span></span>
  <span data-ttu-id="a9e6a-193">![“安排会议”按钮回复撰写框](media/schedule-meeting-disabled-in-chat2.png)</span><span class="sxs-lookup"><span data-stu-id="a9e6a-193">![schedule a meeting button reply compose box](media/schedule-meeting-disabled-in-chat2.png)</span></span>
  
- <span data-ttu-id="a9e6a-194">频道标题上的 **“安排会议”** 按钮。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-194">**Schedule a meeting** button on the channel header.</span></span>
  <span data-ttu-id="a9e6a-195">![频道标题中的“安排会议”按钮](media/schedule-now-in-header.png)</span><span class="sxs-lookup"><span data-stu-id="a9e6a-195">![schedule a meeting button in the channel header](media/schedule-now-in-header.png)</span></span>

<span data-ttu-id="a9e6a-196">在频道日历中:</span><span class="sxs-lookup"><span data-stu-id="a9e6a-196">In the channel calendar:</span></span>

- <span data-ttu-id="a9e6a-197">将禁用频道日历标题上的 **“添加新事件”** 按钮。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-197">**Add new event** button on channel calendar header will be disabled.</span></span>
  <span data-ttu-id="a9e6a-198">![已禁用频道日历标题上的按钮](media/add-new-event-disabled.png)</span><span class="sxs-lookup"><span data-stu-id="a9e6a-198">![button on channel calendar header disabled](media/add-new-event-disabled.png)</span></span>

- <span data-ttu-id="a9e6a-199">用户无法在频道日历上拖动和选择时间块来创建频道会议。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-199">Users can't drag and select a time block on the channel calendar to create a channel meeting.</span></span>

- <span data-ttu-id="a9e6a-200">用户无法使用键盘快捷键在频道日历上创建会议。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-200">Users can't use Keyboard shortcuts to create a meeting on the channel calendar.</span></span>

<span data-ttu-id="a9e6a-201">在管理中心:</span><span class="sxs-lookup"><span data-stu-id="a9e6a-201">In the admin center:</span></span>

<span data-ttu-id="a9e6a-202">频道日历应用将显示在应用权限策略页面的 **Microsoft 应用** 部分。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-202">The channel calendar app will show up in the **Microsoft apps** section on the app permission policies page.</span></span>

 ![Teams 管理中心中的应用权限策略](media/manage-microsoft-apps-policy.png)

### <a name="allow-scheduling-private-meetings"></a><span data-ttu-id="a9e6a-204">允许安排私人会议</span><span class="sxs-lookup"><span data-stu-id="a9e6a-204">Allow scheduling private meetings</span></span>

<span data-ttu-id="a9e6a-205">“安排私人会议”是按用户策略，在会议开始前适用。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-205">Scheduling private meetings is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="a9e6a-206">此设置控制用户是否可以在 Teams 中安排私人会议。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-206">This setting controls whether users can schedule private meetings in Teams.</span></span> <span data-ttu-id="a9e6a-207">当会议未发布到团队中的某个频道时，这个会议就是私人的。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-207">A meeting is private when it's not published to a channel in a team.</span></span>

<span data-ttu-id="a9e6a-208">如果关闭 **“允许安排私人会议”** 和 **“允许频道会议安排”**，则 Teams 中的用户将禁用 **“添加所需与会者”** 和 **“添加频道”** 选项。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-208">If you turn off **Allow scheduling private meetings** and **Allow channel meeting scheduling**, the **Add required attendees** and **Add channel** options are disabled for users in Teams.</span></span> <span data-ttu-id="a9e6a-209">默认情况下，此设置已启动。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-209">By default, this setting is turned on.</span></span>

### <a name="allow-meet-now-in-private-meetings"></a><span data-ttu-id="a9e6a-210">允许在私人会议中立即开会</span><span class="sxs-lookup"><span data-stu-id="a9e6a-210">Allow Meet now in private meetings</span></span>

<span data-ttu-id="a9e6a-211">这是按用户政策，在会议开始前适用。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-211">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="a9e6a-212">此设置控制用户是否可以启动非计划的私人会议。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-212">This setting controls whether a user can start an unplanned private meeting.</span></span> <span data-ttu-id="a9e6a-213">默认情况下，此设置已启动。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-213">By default, this setting is turned on.</span></span>

<span data-ttu-id="a9e6a-214"><a name="bkaudioandvideo"> </a></span><span class="sxs-lookup"><span data-stu-id="a9e6a-214"><a name="bkaudioandvideo"> </a></span></span>

## <a name="meeting-policy-settings---audio--video"></a><span data-ttu-id="a9e6a-215">会议策略设置 - 音频和视频</span><span class="sxs-lookup"><span data-stu-id="a9e6a-215">Meeting policy settings - Audio & video</span></span>

- [<span data-ttu-id="a9e6a-216">允许转录</span><span class="sxs-lookup"><span data-stu-id="a9e6a-216">Allow transcription</span></span>](#allow-transcription)
- [<span data-ttu-id="a9e6a-217">允许云录制</span><span class="sxs-lookup"><span data-stu-id="a9e6a-217">Allow cloud recording</span></span>](#allow-cloud-recording)
- [<span data-ttu-id="a9e6a-218">IP 音频模式</span><span class="sxs-lookup"><span data-stu-id="a9e6a-218">Mode for IP audio</span></span>](#mode-for-ip-audio)
- [<span data-ttu-id="a9e6a-219">IP 视频模式</span><span class="sxs-lookup"><span data-stu-id="a9e6a-219">Mode for IP video</span></span>](#mode-for-ip-video)
- [<span data-ttu-id="a9e6a-220">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="a9e6a-220">Allow IP video</span></span>](#allow-ip-video)
- [<span data-ttu-id="a9e6a-221">媒体位率 (Kbs)</span><span class="sxs-lookup"><span data-stu-id="a9e6a-221">Media bit rate (Kbs)</span></span>](#media-bit-rate-kbs)

### <a name="allow-transcription"></a><span data-ttu-id="a9e6a-222">允许转录</span><span class="sxs-lookup"><span data-stu-id="a9e6a-222">Allow transcription</span></span>

<span data-ttu-id="a9e6a-223">此策略将启用实时转录功能。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-223">This policy turns on Live transcription.</span></span> <span data-ttu-id="a9e6a-224">允许转录是按用户的策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-224">Allow transcription is a per-user policy.</span></span> <span data-ttu-id="a9e6a-225">此设置控制是否可以转录这个特定团队的会议。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-225">This setting controls whether this specific Team's meeting can be transcribed.</span></span>

![会议策略中的转录选项](media/live-transcription.png)

<span data-ttu-id="a9e6a-227">实时转录在团队会议期间以近乎实时的方式显示口语内容的语音转文本。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-227">Live transcription shows speech-to-text of spoken content during a Teams meeting in near real time.</span></span> <span data-ttu-id="a9e6a-228">文字与会议视频一起出现，包括演示者的姓名和时间戳。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-228">The text appears alongside the meeting video, including the speaker's name and a time stamp.</span></span> <span data-ttu-id="a9e6a-229">有关详细信息，请参阅 [Teams 会议中的实时转录](https://support.microsoft.com/office/view-live-transcription-in-a-teams-meeting-dc1a8f23-2e20-4684-885e-2152e06a4a8b)。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-229">To learn more, see [View live transcription in a Teams meeting](https://support.microsoft.com/office/view-live-transcription-in-a-teams-meeting-dc1a8f23-2e20-4684-885e-2152e06a4a8b).</span></span>

<span data-ttu-id="a9e6a-230">目前，Teams 桌面客户端支持实时转录。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-230">Currently, live transcription is supported on the Teams desktop client.</span></span> <span data-ttu-id="a9e6a-231">支持美国英语口语的转录。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-231">Transcription is supported for spoken U.S. English.</span></span> <span data-ttu-id="a9e6a-232">会议结束后，可在 Teams 桌面或 Web 上查看转录内容。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-232">The transcript is available after the meeting on Teams desktop or web.</span></span>

<span data-ttu-id="a9e6a-233">以下是 **“允许转录”** 和 **“允许云录制”** 策略设置如何共同工作。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-233">Here's how the **Allow transcription** and **Allow cloud recording** policy settings work together.</span></span> <span data-ttu-id="a9e6a-234">下表介绍了这些设置的值和会议行为。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-234">The following table describes the values for these settings and the meeting behavior.</span></span>

|<span data-ttu-id="a9e6a-235">允许转录</span><span class="sxs-lookup"><span data-stu-id="a9e6a-235">Allow transcription</span></span>|<span data-ttu-id="a9e6a-236">允许云录制</span><span class="sxs-lookup"><span data-stu-id="a9e6a-236">Allow cloud recording</span></span>|<span data-ttu-id="a9e6a-237">行为</span><span class="sxs-lookup"><span data-stu-id="a9e6a-237">Behavior</span></span>|
|---------|---------|---------|
|<span data-ttu-id="a9e6a-238">**打开**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-238">**On**</span></span>|<span data-ttu-id="a9e6a-239">**打开**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-239">**On**</span></span>|<span data-ttu-id="a9e6a-240">Teams 会议中可使用 **“开始转录”** 选项。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-240">The **Start transcription** option is available in Teams meetings.</span></span> <span data-ttu-id="a9e6a-241">会议组织者或会议参与者可以开始和停止转录。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-241">The meeting organizer or meeting participants can start and stop transcription.</span></span> <span data-ttu-id="a9e6a-242">Teams 会议中可使用 **“开始录制”** 选项。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-242">The **Start recording** option is available in Teams meetings.</span></span> <span data-ttu-id="a9e6a-243">会议组织者或会议参与者可以开始和停止录制。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-243">The meeting organizer or meeting participants can start and stop recording.</span></span> |
|<span data-ttu-id="a9e6a-244">**打开**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-244">**On**</span></span>|<span data-ttu-id="a9e6a-245">**禁用**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-245">**Off**</span></span>|<span data-ttu-id="a9e6a-246">Teams 会议中可使用 **“开始转录”** 选项。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-246">The **Start transcription** option is available in Teams meetings.</span></span> <span data-ttu-id="a9e6a-247">Teams 会议中无法使用 **“开始录制”** 选项。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-247">The **Start recording** option isn't available in Teams meetings.</span></span> |
|<span data-ttu-id="a9e6a-248">**禁用**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-248">**Off**</span></span>|<span data-ttu-id="a9e6a-249">**打开**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-249">**On**</span></span>|<span data-ttu-id="a9e6a-250">Teams 会议中可使用 **“开始录制”** 选项。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-250">The **Start recording** option is available in Teams meetings.</span></span> <span data-ttu-id="a9e6a-251">**“开始录制”** 选项在 Teams 会议中不可用。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-251">The **Start transcription** option isn't available in Teams meetings.</span></span>|
|<span data-ttu-id="a9e6a-252">**禁用**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-252">**Off**</span></span>|<span data-ttu-id="a9e6a-253">**禁用**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-253">**Off**</span></span>|<span data-ttu-id="a9e6a-254">Teams 会议中没有录制和转录功能。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-254">Recording and transcription aren't available in Teams meetings.</span></span>  |

### <a name="allow-cloud-recording"></a><span data-ttu-id="a9e6a-255">允许云录制</span><span class="sxs-lookup"><span data-stu-id="a9e6a-255">Allow cloud recording</span></span>

<span data-ttu-id="a9e6a-256">允许云录制是在按用户策略中控制的。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-256">Allow cloud recording is controlled at a per-user policy.</span></span> <span data-ttu-id="a9e6a-257">此设置控制用户是否可以录制。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-257">This setting controls whether a user can record.</span></span> <span data-ttu-id="a9e6a-258">如果会议组织者或其他会议参与者的特定策略设置已打开，并且他们是与组织者来自同一组织的认证用户，则可由他们启动录制。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-258">The recording can be started by the meeting organizer or by another meeting participant if their specific policy setting is turned on and if they're an authenticated user from the same organization as the organizer.</span></span>

<span data-ttu-id="a9e6a-259">组织之外的人员，如联合和匿名用户，无法启动录制。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-259">People outside your organization, such as federated and anonymous users, can't start the recording.</span></span> <span data-ttu-id="a9e6a-260">来宾用户无法启动或停止录制。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-260">Guest users can't start or stop the recording.</span></span>

![录制选项](media/meeting-policies-recording.png)

<span data-ttu-id="a9e6a-262">若要了解有关云会议记录的更多信息，请参阅 [Teams 云会议录制](cloud-recording.md)。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-262">To learn more about cloud meeting recording, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

### <a name="mode-for-ip-audio"></a><span data-ttu-id="a9e6a-263">IP 音频模式</span><span class="sxs-lookup"><span data-stu-id="a9e6a-263">Mode for IP audio</span></span>

<span data-ttu-id="a9e6a-264">IP 音频的模式是按用户策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-264">Mode for IP audio is a per-user policy.</span></span> <span data-ttu-id="a9e6a-265">此设置控制是否可以在会议和群组通话中打开音频。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-265">This setting controls whether audio can be turned on in meetings and group calls.</span></span> <span data-ttu-id="a9e6a-266">下面是此设置的值。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-266">Here are the values for this setting.</span></span>

|<span data-ttu-id="a9e6a-267">设置值</span><span class="sxs-lookup"><span data-stu-id="a9e6a-267">Setting value</span></span> |<span data-ttu-id="a9e6a-268">行为</span><span class="sxs-lookup"><span data-stu-id="a9e6a-268">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="a9e6a-269">**已启用传出和传入音频**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-269">**Outgoing and incoming audio enabled**</span></span>    |<span data-ttu-id="a9e6a-p132">会议允许传出和传入音频。这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-p132">Outgoing and incoming audio is allowed in the meeting. This is the default setting.</span></span> |
|<span data-ttu-id="a9e6a-272">**禁用**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-272">**Disabled**</span></span>     |<span data-ttu-id="a9e6a-273">传出和传入音频在会议中已关闭。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-273">Outgoing and incoming audio is turned off in the meeting.</span></span>     |

<span data-ttu-id="a9e6a-274">如果为用户设置为 **禁用**，该用户仍然可以安排和组织会议，但不能使用音频。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-274">If set to **Disabled** for a user, that user can still schedule and organize meetings but can't use audio.</span></span> <span data-ttu-id="a9e6a-275">若要加入会议，用户必须通过公共交换电话网 (PSTN) 拨入，或由会议通过电话呼叫加入用户。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-275">To join a meeting, the user has to dial in through the Public Switched Telephone Network (PSTN) or have the meeting call to join the user by phone.</span></span> <span data-ttu-id="a9e6a-276">没有指定任何策略的会议参与者 (例如，匿名参与者) 将此设置为默认 **启用传出和传入音频**。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-276">Meeting participants who don't have any policies assigned (for example, anonymous participants) have this set to **Outgoing and incoming audio enabled** by default.</span></span> <span data-ttu-id="a9e6a-277">在 Teams 移动客户端上，如果禁用此设置，用户必须通过 PSTN 拨入会议。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-277">On Teams mobile clients, if this setting is disabled, the user has to dial in to the meeting through the PSTN.</span></span>

<span data-ttu-id="a9e6a-278">此设置不适用于 1:1 呼叫。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-278">This setting doesn't apply to 1:1 calls.</span></span> <span data-ttu-id="a9e6a-279">若要限制 1:1 通话，请配置 Teams [通话策略](teams-calling-policy.md) 并关闭 **“进行私人通话”** 设置。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-279">To restrict 1:1 calls, configure a Teams [calling policy](teams-calling-policy.md) and turn off the **Make private calls** setting.</span></span> <span data-ttu-id="a9e6a-280">此设置也不适用于 Surface Hub 和 Microsoft Teams 会议室设备等会议室设备。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-280">This setting also doesn't apply to conference room devices such as Surface Hub and Microsoft Teams Rooms devices.</span></span>

<span data-ttu-id="a9e6a-281">此设置尚未适用于 Microsoft 365 政府社区云 (GCC)、GCC High 或国防部 (DoD) 环境。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-281">This setting isn't yet available for Microsoft 365 Government Community Cloud (GCC), GCC High, or Department of Defense (DoD) environments.</span></span>

<span data-ttu-id="a9e6a-282">有关详细信息，请参阅 [会议参与者管理音频/视频](#manage-audiovideo-for-meeting-participants)。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-282">To learn more, see [Manage audio/video for meeting participants](#manage-audiovideo-for-meeting-participants).</span></span>

### <a name="mode-for-ip-video"></a><span data-ttu-id="a9e6a-283">IP 视频模式</span><span class="sxs-lookup"><span data-stu-id="a9e6a-283">Mode for IP video</span></span>

<span data-ttu-id="a9e6a-284">IP 视频的模式是按用户策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-284">Mode for IP video is a per-user policy.</span></span> <span data-ttu-id="a9e6a-285">此设置控制是否可以在会议和群组通话中打开视频。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-285">This setting controls whether video can be turned on in meetings and group calls.</span></span> <span data-ttu-id="a9e6a-286">下面是此设置的值。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-286">Here are the values for this setting.</span></span>

|<span data-ttu-id="a9e6a-287">设置值</span><span class="sxs-lookup"><span data-stu-id="a9e6a-287">Setting value</span></span> |<span data-ttu-id="a9e6a-288">行为</span><span class="sxs-lookup"><span data-stu-id="a9e6a-288">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="a9e6a-289">**已启用传出和传入视频**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-289">**Outgoing and incoming video enabled**</span></span>    | <span data-ttu-id="a9e6a-290">默认设置是允许会议中传出和传入视频。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-290">Outgoing and incoming video is allowed in the meeting is the default setting.</span></span> |
|<span data-ttu-id="a9e6a-291">**禁用**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-291">**Disabled**</span></span>     | <span data-ttu-id="a9e6a-292">传出和传入视频在会议中已关闭。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-292">Outgoing and incoming video is turned off in the meeting.</span></span> <span data-ttu-id="a9e6a-293">在 Teams 移动客户端上，用户无法在会议中分享视频或照片。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-293">On Teams mobile clients, users can't share videos or photos in the meeting.</span></span> <br><br><span data-ttu-id="a9e6a-294">如果禁用 **IP 音频的模式**，那么 **IP 视频的模式** 也将保持禁用。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-294">If **Mode for IP audio** is disabled, then **Mode for IP video** will also remain disabled.</span></span>  |

<span data-ttu-id="a9e6a-295">如果为用户设置为 **禁用**，则该用户无法打开视频或查看其他会议参与者共享的视频。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-295">If set to **Disabled** for a  user, that user can't turn on video or view videos shared by other meeting participants.</span></span> <span data-ttu-id="a9e6a-296">没有指定任何策略的会议参与者 (例如，匿名参与者) 将此设置为默认 **启用传出和传入视频**。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-296">Meeting participants who don't have any policies assigned (for example, anonymous participants) have this set to **Outgoing and incoming video enabled** by default.</span></span>

<span data-ttu-id="a9e6a-297">此设置不适用于 Surface Hub 和 Microsoft Teams 会议室设备等会议室设备。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-297">This setting doesn't apply to conference room devices such as Surface Hub and Microsoft Teams Rooms devices.</span></span>

<span data-ttu-id="a9e6a-298">此设置尚未适用于 Microsoft 365 政府社区云 (GCC)、GCC High 或国防部 (DoD) 环境。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-298">This setting isn't yet available for Microsoft 365 Government Community Cloud (GCC), GCC High, or Department of Defense (DoD) environments.</span></span>

> [!NOTE]
> <span data-ttu-id="a9e6a-299">请记住，该设置同时控制传出和传入的视频，而 **允许 IP 视频** 设置则控制传出视频。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-299">Keep in mind that this setting controls both outgoing and incoming video whereas the **Allow IP video** setting controls outgoing video.</span></span> <span data-ttu-id="a9e6a-300">若要了解更多信息，请参阅[哪些 IP 视频策略设置优先?](#which-ip-video-policy-setting-takes-precedence) 和 [管理会议参与者的音频/视频 ](#manage-audiovideo-for-meeting-participants)。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-300">To learn more, see [Which IP video policy setting takes precedence?](#which-ip-video-policy-setting-takes-precedence) and [Manage audio/video for meeting participants](#manage-audiovideo-for-meeting-participants).</span></span>

<span data-ttu-id="a9e6a-301">有关详细信息，请参阅 [会议参与者管理音频/视频](#manage-audiovideo-for-meeting-participants)。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-301">To learn more, see [Manage audio/video for meeting participants](#manage-audiovideo-for-meeting-participants).</span></span>

### <a name="allow-ip-video"></a><span data-ttu-id="a9e6a-302">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="a9e6a-302">Allow IP video</span></span>

<span data-ttu-id="a9e6a-303">允许 IP 视频是按组织者和按用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-303">Allow IP video is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="a9e6a-304">视频是会议的重要组成部分。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-304">Video is a key component to meetings.</span></span> <span data-ttu-id="a9e6a-305">在一些组织中，管理员可能希望对有视频的用户会议进行更多的控制。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-305">In some organizations, admins might want more control over which users' meetings have video.</span></span> <span data-ttu-id="a9e6a-306">此设置控制是否可以在用户主持的会议和用户启动的 1:1 和群组通话中打开视频。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-306">This setting controls whether video can be turned on in meetings hosted by a user and in 1:1 and group calls started by a user.</span></span> <span data-ttu-id="a9e6a-307">在 Teams 移动客户端上，该设置可以控制用户是否可以在会议中共享照片和视频。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-307">On Teams mobile clients, this setting control whether users can share photos and videos in a meeting.</span></span>

<span data-ttu-id="a9e6a-308">由启用了此策略设置的用户组织的会议，如果与会者也启用了此策略设置，则允许与会者在会议中进行视频共享。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-308">Meetings organized by a user who has this policy setting enabled, allow video sharing in the meeting by the meeting participants, if the participants also have the policy setting enabled.</span></span> <span data-ttu-id="a9e6a-309">没有指定任何策略的会议参与者 (例如，匿名和联合参与者) 继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-309">Meeting participants who don't have any policies assigned (for example, anonymous and federated participants) inherit the policy of the meeting organizer.</span></span>

> [!NOTE]
> <span data-ttu-id="a9e6a-310">请记住，此设置控制传出视频，而 **IP 视频的模式** 设置则控制传出和传入视频。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-310">Keep in mind that this setting controls outgoing video whereas the **Mode for IP video** setting controls both outgoing and incoming video.</span></span> <span data-ttu-id="a9e6a-311">若要了解更多信息，请参阅[哪些 IP 视频策略设置优先?](#which-ip-video-policy-setting-takes-precedence) 和 [管理会议参与者的音频/视频 ](#manage-audiovideo-for-meeting-participants)。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-311">To learn more, see [Which IP video policy setting takes precedence?](#which-ip-video-policy-setting-takes-precedence) and [Manage audio/video for meeting participants](#manage-audiovideo-for-meeting-participants).</span></span>

| <span data-ttu-id="a9e6a-312">Teams 桌面和 Web 客户端</span><span class="sxs-lookup"><span data-stu-id="a9e6a-312">Teams desktop and web client</span></span> |<span data-ttu-id="a9e6a-313">Teams 移动客户端</span><span class="sxs-lookup"><span data-stu-id="a9e6a-313">Teams mobile client</span></span>  |
|:-------:|:-------:|
|![截图截图显示在桌面上通过音频/视频设置加入会议的画面](media/meeting-policies-audio-video-settings.png)    |![屏幕截图显示在移动设备上通过音频/视频设置加入会议的画面](media/meeting-policies-mobile-join.png)          |

<span data-ttu-id="a9e6a-316">查看以下示例。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-316">Let's look at the following example.</span></span>

|<span data-ttu-id="a9e6a-317">用户</span><span class="sxs-lookup"><span data-stu-id="a9e6a-317">User</span></span> |<span data-ttu-id="a9e6a-318">会议策略</span><span class="sxs-lookup"><span data-stu-id="a9e6a-318">Meeting policy</span></span>  |<span data-ttu-id="a9e6a-319">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="a9e6a-319">Allow IP video</span></span> |
|---------|---------|---------|
|<span data-ttu-id="a9e6a-320">Daniela</span><span class="sxs-lookup"><span data-stu-id="a9e6a-320">Daniela</span></span>   | <span data-ttu-id="a9e6a-321">全局</span><span class="sxs-lookup"><span data-stu-id="a9e6a-321">Global</span></span>   | <span data-ttu-id="a9e6a-322">开</span><span class="sxs-lookup"><span data-stu-id="a9e6a-322">On</span></span>       |
|<span data-ttu-id="a9e6a-323">Amanda</span><span class="sxs-lookup"><span data-stu-id="a9e6a-323">Amanda</span></span>    | <span data-ttu-id="a9e6a-324">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="a9e6a-324">Location1MeetingPolicy</span></span>        | <span data-ttu-id="a9e6a-325">关闭</span><span class="sxs-lookup"><span data-stu-id="a9e6a-325">Off</span></span>      |

<span data-ttu-id="a9e6a-326">由 Daniela 主持的会议允许开启视频。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-326">Meetings hosted by Daniela allow video to be turned on.</span></span> <span data-ttu-id="a9e6a-327">Daniela 可以加入会议并打开视频。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-327">Daniela can join the meeting and turn on video.</span></span> <span data-ttu-id="a9e6a-328">Amanda 不能在 Daniela 的会议上开视频，因为 Amanda 的策略不允许视频。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-328">Amanda can't turn on video in Daniela's meeting, because Amanda's policy is set to not allow video.</span></span> <span data-ttu-id="a9e6a-329">Amanda 可以看到其他与会者在会议上分享的视频。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-329">Amanda can see videos shared by other participants in the meeting.</span></span>

<span data-ttu-id="a9e6a-330">在 Amanda 主持的会议中，无论分配给他们的视频策略如何，任何人都无法打开视频。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-330">In meetings hosted by Amanda, no one can turn on video, regardless of the video policy assigned to them.</span></span> <span data-ttu-id="a9e6a-331">这意味着 Daniela 不能在 Amanda 的会议上开视频。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-331">This means Daniela can't turn on video in Amanda's meetings.</span></span>  

<span data-ttu-id="a9e6a-332">如果 Daniela 给 Amanda 打电话时开着视频，Amanda 可以只用音频接听电话。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-332">If Daniela calls Amanda with video on, Amanda can answer the call with audio only.</span></span> <span data-ttu-id="a9e6a-333">电话接通后，Amanda 可以看到 Daniela 的视频，但无法打开视频。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-333">When the call is connected, Amanda can see Daniela's video, but can't turn on video.</span></span> <span data-ttu-id="a9e6a-334">如果 Amanda 给 Daniela 打电话，Daniela 可以用视频和音频接听电话。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-334">If Amanda calls Daniela, Daniela can answer the call with video and audio.</span></span> <span data-ttu-id="a9e6a-335">通话接通后，Daniela 可以根据需要打开或关闭其视频。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-335">When the call is connected, Daniela can turn on or turn off her video, as needed.</span></span>

<span data-ttu-id="a9e6a-336">有关详细信息，请参阅 [会议参与者管理音频/视频](#manage-audiovideo-for-meeting-participants)。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-336">To learn more, see [Manage audio/video for meeting participants](#manage-audiovideo-for-meeting-participants).</span></span>

#### <a name="which-ip-video-policy-setting-takes-precedence"></a><span data-ttu-id="a9e6a-337">哪些 IP 视频策略设置优先</span><span class="sxs-lookup"><span data-stu-id="a9e6a-337">Which IP video policy setting takes precedence</span></span>

<span data-ttu-id="a9e6a-p145">对于用户，视频的最多限制策略设置优先。此处为一些示例。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-p145">For a user, the most restrictive policy setting for video takes precedence. Here's some examples.</span></span>

|<span data-ttu-id="a9e6a-340">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="a9e6a-340">Allow IP video</span></span>|<span data-ttu-id="a9e6a-341">IP 视频模式</span><span class="sxs-lookup"><span data-stu-id="a9e6a-341">Mode for IP video</span></span>|<span data-ttu-id="a9e6a-342">会议体验</span><span class="sxs-lookup"><span data-stu-id="a9e6a-342">Meeting experience</span></span>|
|---------|---------|---------|
|<span data-ttu-id="a9e6a-343">组织者: **打开**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-343">Organizer: **On**</span></span><br><br><span data-ttu-id="a9e6a-344">参与者: **打开**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-344">Participant: **On**</span></span> |<span data-ttu-id="a9e6a-345">参与者: **禁用**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-345">Participant: **Disabled**</span></span>        |<span data-ttu-id="a9e6a-346">**IP 视频模式** 设置优先。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-346">The **Mode for IP video** setting takes precedence.</span></span> <span data-ttu-id="a9e6a-347">分配到此策略的参与者不能开启或查看他人分享的视频。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-347">The participant who is assigned this policy can't turn on or view videos shared by others.</span></span>|
|<span data-ttu-id="a9e6a-348">组织者: **打开**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-348">Organizer: **On**</span></span><br><br><span data-ttu-id="a9e6a-349">参与者: **打开**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-349">Participant: **On**</span></span> |<span data-ttu-id="a9e6a-350">参与者: **启用传出和传入视频**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-350">Participant: **Outgoing and incoming video enabled**</span></span>          |<span data-ttu-id="a9e6a-351">分配到该策略的参与者可以打开或查看他人分享的视频。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-351">The participant who is assigned this policy can turn on or view videos shared by others.</span></span>         |
|<span data-ttu-id="a9e6a-352">组织者: **打开**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-352">Organizer: **On**</span></span><br><br><span data-ttu-id="a9e6a-353">参与者: **关闭**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-353">Participant: **Off**</span></span> |<span data-ttu-id="a9e6a-354">参与者: **启用传出和传入视频**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-354">Participant: **Outgoing and incoming video enabled**</span></span>         |<span data-ttu-id="a9e6a-355">允许 **IP 视频** 设置优先。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-355">The **Allow IP video** setting takes precedence.</span></span> <span data-ttu-id="a9e6a-356">参与者只能看到传入视频，无法发送传出视频。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-356">Participants can only see incoming video and can't send outgoing video.</span></span>         |
|<span data-ttu-id="a9e6a-357">组织者: **打开**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-357">Organizer: **On**</span></span><br><br><span data-ttu-id="a9e6a-358">参与者: **关闭**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-358">Participant: **Off**</span></span> |<span data-ttu-id="a9e6a-359">参与者: **禁用**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-359">Participant: **Disabled**</span></span>         |<span data-ttu-id="a9e6a-360">**IP 视频模式** 设置优先。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-360">The **Mode for IP video** setting takes precedence.</span></span> <span data-ttu-id="a9e6a-361">参与者无法看到传入或传出的视频。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-361">The participant can't see incoming or outgoing video.</span></span>|
|<span data-ttu-id="a9e6a-362">组织者: **关闭**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-362">Organizer: **Off**</span></span>    |       |<span data-ttu-id="a9e6a-363">**允许 IP 视频** 设置优先，因为它已为组织者关闭。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-363">The **Allow IP video** setting takes precedence because it's turned off for the organizer.</span></span> <span data-ttu-id="a9e6a-364">任何人都不能在分配此策略的用户组织会议中打开视频。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-364">No one can turn on video in meetings organized by the user who is assigned this policy.</span></span>         |

### <a name="manage-audiovideo-for-meeting-participants"></a><span data-ttu-id="a9e6a-365">管理与会者的音频/视频</span><span class="sxs-lookup"><span data-stu-id="a9e6a-365">Manage audio/video for meeting participants</span></span>

|<span data-ttu-id="a9e6a-366">如果你想要...</span><span class="sxs-lookup"><span data-stu-id="a9e6a-366">If you want to...</span></span>  |<span data-ttu-id="a9e6a-367">设置以下策略设置</span><span class="sxs-lookup"><span data-stu-id="a9e6a-367">Set the following policy settings</span></span>  |
|---------|---------|
|<span data-ttu-id="a9e6a-368">禁用会议参与者的音频和视频</span><span class="sxs-lookup"><span data-stu-id="a9e6a-368">Disable audio and video for participants in meetings</span></span>  |<span data-ttu-id="a9e6a-369">IP 音频模式: **禁用**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-369">Mode for IP audio: **Disabled**</span></span><br> <span data-ttu-id="a9e6a-370">IP 视频模式: **禁用**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-370">Mode for IP video: **Disabled**</span></span><br><span data-ttu-id="a9e6a-371">允许 IP 视频: 不适用</span><span class="sxs-lookup"><span data-stu-id="a9e6a-371">Allow IP video: N/A</span></span>       |
|<span data-ttu-id="a9e6a-372">只为会议参与者启用传入的视频和音频</span><span class="sxs-lookup"><span data-stu-id="a9e6a-372">Enable only incoming video and audio for participants in meetings</span></span>  |<span data-ttu-id="a9e6a-373">IP 音频模式: **启用传出和传入音频**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-373">Mode for IP audio: **Outgoing and incoming audio enabled**</span></span><br> <span data-ttu-id="a9e6a-374">IP 视频模式: **启用传出和传入视频**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-374">Mode for IP video: **Outgoing and incoming video enabled**</span></span><br><span data-ttu-id="a9e6a-375">允许 IP 视频: **关闭**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-375">Allow IP video: **Off**</span></span>       |
|<span data-ttu-id="a9e6a-376">禁用会议参与者的视频 (参与者仅有音频)</span><span class="sxs-lookup"><span data-stu-id="a9e6a-376">Disable video for participants in meetings (participants have audio only)</span></span>|  <span data-ttu-id="a9e6a-377">IP 音频模式: **启用传出和传入音频**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-377">Mode for IP audio: **Enable outgoing and incoming audio**</span></span><br> <span data-ttu-id="a9e6a-378">IP 视频模式: **禁用**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-378">Mode for IP video: **Disabled**</span></span><br><span data-ttu-id="a9e6a-379">允许 IP 视频: 不适用</span><span class="sxs-lookup"><span data-stu-id="a9e6a-379">Allow IP video: N/A</span></span>
|<span data-ttu-id="a9e6a-380">为会议参与者启用音频和视频</span><span class="sxs-lookup"><span data-stu-id="a9e6a-380">Enable audio and video for participants in meetings</span></span>    |<span data-ttu-id="a9e6a-381">IP 音频模式: **启用的传出和传入** (默认)</span><span class="sxs-lookup"><span data-stu-id="a9e6a-381">Mode for IP audio: **Outgoing and incoming audio enabled** (default)</span></span><br> <span data-ttu-id="a9e6a-382">IP 视频模式: **启用传出和传入视频** (默认)</span><span class="sxs-lookup"><span data-stu-id="a9e6a-382">Mode for IP video: **Outgoing and incoming video enabled** (default)</span></span><br><span data-ttu-id="a9e6a-383">允许 IP 视频: **打开** (默认)</span><span class="sxs-lookup"><span data-stu-id="a9e6a-383">Allow IP video: **On** (default)</span></span>    |

<span data-ttu-id="a9e6a-384">适用会议组织者政策和用户政策之间最严格的政策。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-384">The most restrictive policy between the meeting organizer’s policy and the user’s policy applies.</span></span> <span data-ttu-id="a9e6a-385">例如，如果组织者有限制视频的策略，而用户的策略不限制视频，那么会议参与者就会继承会议组织者的策略，在会议中无法访问视频。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-385">For example, if an organizer has a policy that restricts video and a user’s policy doesn't restrict video, meeting participants inherit the policy of the meeting organizer and don't have access to video in meetings.</span></span> <span data-ttu-id="a9e6a-386">这意味着他们只能使用音频加入会议。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-386">This means that they can join the meeting with audio only.</span></span>

> [!NOTE]
> <span data-ttu-id="a9e6a-387">当用户通过电话启动群组呼叫加入时，不会出现 **使用电话进行音频** 的画面。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-387">When a user starts a group call to join by phone, the **Use phone for audio** screen doesn't appear.</span></span> <span data-ttu-id="a9e6a-388">这是一个已知的问题，我们正在努力解决。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-388">This is a known issue that we're working to resolve.</span></span> <span data-ttu-id="a9e6a-389">若要解决这个问题，选择 **其他加入选项** 下的 **电话音频**。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-389">To work around this issue, select **Phone audio** under **Other join options**.</span></span>  

#### <a name="teams-mobile-clients"></a><span data-ttu-id="a9e6a-390">Teams 移动设备客户端</span><span class="sxs-lookup"><span data-stu-id="a9e6a-390">Teams mobile clients</span></span>

<span data-ttu-id="a9e6a-391">对于 Teams 移动设备客户端的用户来说，在会议期间分享照片和视频的能力由 **允许 IP 视频** 或 **IP 视频模式** 设置决定。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-391">For users on Teams mobile clients, the ability to share photos and videos during a meeting is determined by the **Allow IP video** or **IP video mode** setting.</span></span> <span data-ttu-id="a9e6a-392">根据策略设置优先，将无法使用分享视频和照片的功能。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-392">Depending on which policy setting takes precedence, the ability to share videos and photos won't be available.</span></span> <span data-ttu-id="a9e6a-393">这不会影响屏幕共享，可以使用单独的 [屏幕共享模式](#screen-sharing-mode) 设置进行配置。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-393">This doesn't affect screen sharing, which you configure using a separate [Screen sharing mode](#screen-sharing-mode) setting.</span></span> <span data-ttu-id="a9e6a-394">此外，还可以设置 [Teams 移动性策略](/powershell/module/skype/new-csteamsmobilitypolicy)，防止移动用户通过蜂窝连接使用 IP 视频，这意味着他们必须使用 WiFi 连接。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-394">Additionally, you can set a [Teams mobility policy](/powershell/module/skype/new-csteamsmobilitypolicy) to prevent mobile users from using IP video over a cellular connection, which means they must use a WiFi connection.</span></span>

### <a name="media-bit-rate-kbs"></a><span data-ttu-id="a9e6a-395">媒体位率 (Kbs)</span><span class="sxs-lookup"><span data-stu-id="a9e6a-395">Media bit rate (Kbs)</span></span>

<span data-ttu-id="a9e6a-396">这是按用户策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-396">This is a per-user policy.</span></span> <span data-ttu-id="a9e6a-397">此设置决定了用户在通话和会议中的音频、视频和基于视频的应用共享传输的总平均媒体位速率。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-397">This setting determines the total average media bit rate for audio, video, and video-based app sharing transmissions in calls and meetings for the user.</span></span> <span data-ttu-id="a9e6a-398">它适用于通话或会议中用户的上行和下行媒体遍历。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-398">It's applied to both the uplink and downlink media traversal for users in the call or meeting.</span></span> <span data-ttu-id="a9e6a-399">此设置可让你对组织中的带宽管理进行精细控制。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-399">This setting gives you granular control over managing bandwidth in your organization.</span></span> <span data-ttu-id="a9e6a-400">根据用户所需的会议场景，我们建议准备足够的带宽，以保证优质的体验。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-400">Depending on the meetings scenarios required by users, we recommend having enough bandwidth in place for a good quality experience.</span></span> <span data-ttu-id="a9e6a-401">最小值为 30Kbps，最大值取决于会议场景。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-401">The minimum value is 30 Kbps and the maximum value depends on the meeting scenario.</span></span> <span data-ttu-id="a9e6a-402">若要了解有关在 Teams 中举行高质量会议、通话和实时活动的最低推荐带宽的更多信息，请参阅 [“带宽要求”](prepare-network.md#bandwidth-requirements)。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-402">To learn more about the minimum recommended bandwidth for good quality meetings, calls, and live events in Teams, see [Bandwidth requirements](prepare-network.md#bandwidth-requirements).</span></span>

<span data-ttu-id="a9e6a-403">如果没有足够的带宽供会议使用，与会者会看到一条表明网络质量差的消息。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-403">If there isn't enough bandwidth for a meeting, participants see a message that indicates poor network quality.</span></span>

<span data-ttu-id="a9e6a-404">对于需要最高质量视频体验的会议，如 CEO 董事会会议和 Teams 直播活动，我们建议将带宽设置为 10 Mbps。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-404">For meetings that need the highest-quality video experience, such as CEO board meetings and Teams live events, we recommend you set the bandwidth to 10 Mbps.</span></span> <span data-ttu-id="a9e6a-405">即使设置了最大体验，当检测到某些网络状况时，Teams 媒体栈也会根据不同的场景，适应低带宽的条件。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-405">Even when the maximum experience is set, the Teams media stack adapts to low-bandwidth conditions when certain network conditions are detected, depending on the scenario.</span></span>

## <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="a9e6a-406">会议策略设置 - 内容共享</span><span class="sxs-lookup"><span data-stu-id="a9e6a-406">Meeting policy settings - Content sharing</span></span>

- [<span data-ttu-id="a9e6a-407">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="a9e6a-407">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="a9e6a-408">允许参与者授予或请求控制权</span><span class="sxs-lookup"><span data-stu-id="a9e6a-408">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="a9e6a-409">允许外部参与者授予或请求控制权</span><span class="sxs-lookup"><span data-stu-id="a9e6a-409">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="a9e6a-410">允许 PowerPoint 共享</span><span class="sxs-lookup"><span data-stu-id="a9e6a-410">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="a9e6a-411">允许白板</span><span class="sxs-lookup"><span data-stu-id="a9e6a-411">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="a9e6a-412">允许共享笔记</span><span class="sxs-lookup"><span data-stu-id="a9e6a-412">Allow shared notes</span></span>](#allow-shared-notes)

### <a name="screen-sharing-mode"></a><span data-ttu-id="a9e6a-413">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="a9e6a-413">Screen sharing mode</span></span>

> [!NOTE]
> <span data-ttu-id="a9e6a-p155">此功能仍处于开发阶段。屏幕共享是按参与者的策略，但是，如本节中所述，可能会受组织者的屏幕共享设置的影响。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-p155">This feature is still in development. Screen sharing is a per-participant policy, however, it can be affected by the organizer's screen sharing settings, as described in this section.</span></span>

<span data-ttu-id="a9e6a-416">此设置控制是否允许在用户的会议中进行桌面和/或窗口共享。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-416">This setting controls whether desktop and/or window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="a9e6a-417">未分配任何策略的会议参与者 (例如，匿名、嘉宾、B2B和联合参与者) 继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-417">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="a9e6a-418">设置值</span><span class="sxs-lookup"><span data-stu-id="a9e6a-418">Setting value</span></span> |<span data-ttu-id="a9e6a-419">行为</span><span class="sxs-lookup"><span data-stu-id="a9e6a-419">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="a9e6a-420">**整个屏幕**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-420">**Entire screen**</span></span>    | <span data-ttu-id="a9e6a-421">会议中可以实现完全的桌面共享和应用共享</span><span class="sxs-lookup"><span data-stu-id="a9e6a-421">Full desktop sharing and application sharing are allowed in the meeting</span></span> |
|<span data-ttu-id="a9e6a-422">**单个应用程序**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-422">**Single application**</span></span>   | <span data-ttu-id="a9e6a-423">会议中允许应用共享</span><span class="sxs-lookup"><span data-stu-id="a9e6a-423">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="a9e6a-424">**禁用**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-424">**Disabled**</span></span>     |<span data-ttu-id="a9e6a-425">会议中关闭了屏幕共享和应用共享。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-425">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="a9e6a-426">查看以下示例。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-426">Let's look at the following example.</span></span>

|<span data-ttu-id="a9e6a-427">用户</span><span class="sxs-lookup"><span data-stu-id="a9e6a-427">User</span></span> |<span data-ttu-id="a9e6a-428">会议策略</span><span class="sxs-lookup"><span data-stu-id="a9e6a-428">Meeting policy</span></span> |<span data-ttu-id="a9e6a-429">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="a9e6a-429">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="a9e6a-430">Daniela</span><span class="sxs-lookup"><span data-stu-id="a9e6a-430">Daniela</span></span>  | <span data-ttu-id="a9e6a-431">全局</span><span class="sxs-lookup"><span data-stu-id="a9e6a-431">Global</span></span>   | <span data-ttu-id="a9e6a-432">整个屏幕</span><span class="sxs-lookup"><span data-stu-id="a9e6a-432">Entire screen</span></span> |
|<span data-ttu-id="a9e6a-433">Amanda</span><span class="sxs-lookup"><span data-stu-id="a9e6a-433">Amanda</span></span>   | <span data-ttu-id="a9e6a-434">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="a9e6a-434">Location1MeetingPolicy</span></span>  | <span data-ttu-id="a9e6a-435">已禁用</span><span class="sxs-lookup"><span data-stu-id="a9e6a-435">Disabled</span></span> |

<span data-ttu-id="a9e6a-436">由 Daniela 主持的会议允许会议参与者分享他们的整个屏幕或特定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-436">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="a9e6a-437">如果 Amanda 加入 Daniela 的会议，Amanda 则无法分享她的屏幕或特定的应用程序，因为她已禁用她的策略设置。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-437">If Amanda joins Daniela's meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="a9e6a-438">在 Amanda 主持的会议中，无论分配给他们的屏幕共享模式策略是什么，都不允许任何人共享他们的屏幕或单个应用程序。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-438">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span> <span data-ttu-id="a9e6a-439">这意味着 Daniela 无法在 Amanda 的会议上分享她的屏幕或单个应用程序。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-439">This means that Daniela can't share her screen or a single application in Amanda's meetings.</span></span>  

<span data-ttu-id="a9e6a-440">目前，如果用户使用谷歌浏览器，就无法在 Teams 会议中播放视频或分享屏幕。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-440">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

### <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="a9e6a-441">允许参加者授予或请求控制权</span><span class="sxs-lookup"><span data-stu-id="a9e6a-441">Allow a participant to give or request control</span></span>

<span data-ttu-id="a9e6a-442">这是按用户策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-442">This is a per-user policy.</span></span> <span data-ttu-id="a9e6a-443">此设置可控制用户是否可以将共享桌面或窗口的控制权交给其他会议参与者。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-443">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="a9e6a-444">若要想进行控制，请将鼠标悬停在屏幕上方。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-444">To give control, hover over the top of the screen.</span></span>

<span data-ttu-id="a9e6a-445">如果为用户开启此设置，则在共享会话中的顶部栏中会显示 **“授予控制”** 选项。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-445">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span>

![显示 “授予控制” 选项的屏幕截图](media/meeting-policies-give-control.png)

<span data-ttu-id="a9e6a-447">如果已关闭用户的设置，则无法使用 **“授予控制”** 选项。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-447">If the setting is turned off for the user, the **Give Control** option isn't available.</span></span>

![显示“授予控制”选项不可用的屏幕截图](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="a9e6a-449">查看以下示例。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-449">Let's look at the following example.</span></span>

|<span data-ttu-id="a9e6a-450">用户</span><span class="sxs-lookup"><span data-stu-id="a9e6a-450">User</span></span> |<span data-ttu-id="a9e6a-451">会议策略</span><span class="sxs-lookup"><span data-stu-id="a9e6a-451">Meeting policy</span></span>  |<span data-ttu-id="a9e6a-452">允许参加者授予或请求控制权</span><span class="sxs-lookup"><span data-stu-id="a9e6a-452">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="a9e6a-453">Daniela</span><span class="sxs-lookup"><span data-stu-id="a9e6a-453">Daniela</span></span>   | <span data-ttu-id="a9e6a-454">全局</span><span class="sxs-lookup"><span data-stu-id="a9e6a-454">Global</span></span>   | <span data-ttu-id="a9e6a-455">开</span><span class="sxs-lookup"><span data-stu-id="a9e6a-455">On</span></span>       |
|<span data-ttu-id="a9e6a-456">Babek</span><span class="sxs-lookup"><span data-stu-id="a9e6a-456">Babek</span></span>    | <span data-ttu-id="a9e6a-457">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="a9e6a-457">Location1MeetingPolicy</span></span>        | <span data-ttu-id="a9e6a-458">关闭</span><span class="sxs-lookup"><span data-stu-id="a9e6a-458">Off</span></span>   |

<span data-ttu-id="a9e6a-459">在 Babek 组织的会议中，Daniela 可以将共享桌面或窗口的控制权交给其他参与者，而 Babek 则无法将控制权交给其他参与者。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-459">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek whereas Babek can't give control to other participants.</span></span>

<span data-ttu-id="a9e6a-460">若要使用 PowerShell 来控制可以授予控制权或接受控制权请求的人选，请使用 AllowParticipantGiveRequestControl cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-460">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="a9e6a-461">若要在共享过程中授予并控制共享内容，双方必须都使用 Teams 桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-461">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="a9e6a-462">如果任何一方在浏览器中运行 Teams，则不支持控制。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-462">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="a9e6a-463">这是由我们计划修复的一个技术限制造成。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-463">This is due to a technical limitation that we're planning to fix.</span></span>

### <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="a9e6a-464">允许外部参加者授予或请求控制权</span><span class="sxs-lookup"><span data-stu-id="a9e6a-464">Allow an external participant to give or request control</span></span>

<span data-ttu-id="a9e6a-465">这是按用户策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-465">This is a per-user policy.</span></span> <span data-ttu-id="a9e6a-466">无论会议组织者设置了什么，组织是否为用户设置了这个功能，都无法控制外部参与者的行为。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-466">Whether an organization has this set for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="a9e6a-467">该参数控制是否可以让外部参与者控制或请求控制共享者的屏幕，这取决于共享者在其组织的会议策略中设置的内容。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-467">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span> <span data-ttu-id="a9e6a-468">Teams 会议的外部与会者可分为以下几类:</span><span class="sxs-lookup"><span data-stu-id="a9e6a-468">External participants in Teams meetings can be categorized as follows:</span></span>  

- <span data-ttu-id="a9e6a-469">匿名用户</span><span class="sxs-lookup"><span data-stu-id="a9e6a-469">Anonymous user</span></span>
- <span data-ttu-id="a9e6a-470">来宾用户</span><span class="sxs-lookup"><span data-stu-id="a9e6a-470">Guest users</span></span>  
- <span data-ttu-id="a9e6a-471">B2B 用户</span><span class="sxs-lookup"><span data-stu-id="a9e6a-471">B2B user</span></span>
- <span data-ttu-id="a9e6a-472">联合用户</span><span class="sxs-lookup"><span data-stu-id="a9e6a-472">Federated user</span></span>  

<span data-ttu-id="a9e6a-473">联合用户在共享时是否可以将控制权交给外部用户，由组织中的 **允许外部参与者授予或请求控制权** 设置控制。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-473">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="a9e6a-474">要使用 PowerShell 来控制外部参与者是否可以授予控制权或接受控制权请求，请使用AllowExternalParticipantGiveRequestControl cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-474">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="a9e6a-475">允许 PowerPoint 共享</span><span class="sxs-lookup"><span data-stu-id="a9e6a-475">Allow PowerPoint sharing</span></span>

<span data-ttu-id="a9e6a-476">这是按用户策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-476">This is a per-user policy.</span></span> <span data-ttu-id="a9e6a-477">此设置可控制用户是否可以在会议中共享 PowerPoint 幻灯片。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-477">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="a9e6a-478">外部用户，包括匿名用户、来宾用户和联合用户，继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-478">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="a9e6a-479">查看以下示例。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-479">Let's look at the following example.</span></span>

|<span data-ttu-id="a9e6a-480">用户</span><span class="sxs-lookup"><span data-stu-id="a9e6a-480">User</span></span> |<span data-ttu-id="a9e6a-481">会议策略</span><span class="sxs-lookup"><span data-stu-id="a9e6a-481">Meeting policy</span></span>  |<span data-ttu-id="a9e6a-482">允许 PowerPoint 共享</span><span class="sxs-lookup"><span data-stu-id="a9e6a-482">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="a9e6a-483">Daniela</span><span class="sxs-lookup"><span data-stu-id="a9e6a-483">Daniela</span></span>   | <span data-ttu-id="a9e6a-484">全局</span><span class="sxs-lookup"><span data-stu-id="a9e6a-484">Global</span></span>   | <span data-ttu-id="a9e6a-485">开</span><span class="sxs-lookup"><span data-stu-id="a9e6a-485">On</span></span>       |
|<span data-ttu-id="a9e6a-486">Amanda</span><span class="sxs-lookup"><span data-stu-id="a9e6a-486">Amanda</span></span>   | <span data-ttu-id="a9e6a-487">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="a9e6a-487">Location1MeetingPolicy</span></span>        | <span data-ttu-id="a9e6a-488">关闭</span><span class="sxs-lookup"><span data-stu-id="a9e6a-488">Off</span></span>   |

<span data-ttu-id="a9e6a-489">Amanda 无法在会议上共享 PowerPoint 幻灯片，即使她是会议组织者。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-489">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="a9e6a-490">Daniela 可以分享 PowerPoint 幻灯片，即使会议是由 Amanda 组织的。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-490">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="a9e6a-491">Amanda 可以查看会议中其他人共享的 PowerPoint 幻灯片，尽管她不能共享 PowerPoint 幻灯片。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-491">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

### <a name="allow-whiteboard"></a><span data-ttu-id="a9e6a-492">允许白板</span><span class="sxs-lookup"><span data-stu-id="a9e6a-492">Allow whiteboard</span></span>

<span data-ttu-id="a9e6a-493">这是按用户策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-493">This is a per-user policy.</span></span> <span data-ttu-id="a9e6a-494">此设置控制用户是否可以在会议中共享白板。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-494">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="a9e6a-495">外部用户，包括匿名用户、B2B用户和联盟用户，继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-495">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="a9e6a-496">查看以下示例。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-496">Let's look at the following example.</span></span>

|<span data-ttu-id="a9e6a-497">用户</span><span class="sxs-lookup"><span data-stu-id="a9e6a-497">User</span></span> |<span data-ttu-id="a9e6a-498">会议策略</span><span class="sxs-lookup"><span data-stu-id="a9e6a-498">Meeting policy</span></span>  |<span data-ttu-id="a9e6a-499">允许白板</span><span class="sxs-lookup"><span data-stu-id="a9e6a-499">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="a9e6a-500">Daniela</span><span class="sxs-lookup"><span data-stu-id="a9e6a-500">Daniela</span></span>   | <span data-ttu-id="a9e6a-501">全局</span><span class="sxs-lookup"><span data-stu-id="a9e6a-501">Global</span></span>   | <span data-ttu-id="a9e6a-502">开</span><span class="sxs-lookup"><span data-stu-id="a9e6a-502">On</span></span>       |
|<span data-ttu-id="a9e6a-503">Amanda</span><span class="sxs-lookup"><span data-stu-id="a9e6a-503">Amanda</span></span>   | <span data-ttu-id="a9e6a-504">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="a9e6a-504">Location1MeetingPolicy</span></span>        | <span data-ttu-id="a9e6a-505">关闭</span><span class="sxs-lookup"><span data-stu-id="a9e6a-505">Off</span></span>   |

<span data-ttu-id="a9e6a-506">Amanda 不能在会议上共享白板，即使她是会议组织者。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-506">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="a9e6a-507">Daniela 可以共享白板，即使会议是由 Amanda 组织的。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-507">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

### <a name="allow-shared-notes"></a><span data-ttu-id="a9e6a-508">允许共享的笔记</span><span class="sxs-lookup"><span data-stu-id="a9e6a-508">Allow shared notes</span></span>

<span data-ttu-id="a9e6a-509">这是按用户策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-509">This is a per-user policy.</span></span> <span data-ttu-id="a9e6a-510">此设置控制用户是否可以在会议中创建和共享笔记。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-510">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="a9e6a-511">外部用户，包括匿名用户、B2B用户和联盟用户，继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-511">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="a9e6a-512">在最多100人参加的会议中，支持 **“会议记录”** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-512">The **Meeting Notes** tab is supported in meetings with up to 100 participants.</span></span>

<span data-ttu-id="a9e6a-513">查看以下示例。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-513">Let's look at the following example.</span></span>

|<span data-ttu-id="a9e6a-514">用户</span><span class="sxs-lookup"><span data-stu-id="a9e6a-514">User</span></span> |<span data-ttu-id="a9e6a-515">会议策略</span><span class="sxs-lookup"><span data-stu-id="a9e6a-515">Meeting policy</span></span>  |<span data-ttu-id="a9e6a-516">允许共享的笔记</span><span class="sxs-lookup"><span data-stu-id="a9e6a-516">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="a9e6a-517">Daniela</span><span class="sxs-lookup"><span data-stu-id="a9e6a-517">Daniela</span></span>   | <span data-ttu-id="a9e6a-518">全局</span><span class="sxs-lookup"><span data-stu-id="a9e6a-518">Global</span></span>   | <span data-ttu-id="a9e6a-519">开</span><span class="sxs-lookup"><span data-stu-id="a9e6a-519">On</span></span>       |
|<span data-ttu-id="a9e6a-520">Amanda</span><span class="sxs-lookup"><span data-stu-id="a9e6a-520">Amanda</span></span>   | <span data-ttu-id="a9e6a-521">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="a9e6a-521">Location1MeetingPolicy</span></span> | <span data-ttu-id="a9e6a-522">关闭</span><span class="sxs-lookup"><span data-stu-id="a9e6a-522">Off</span></span> |

<span data-ttu-id="a9e6a-523">Daniela 可以在 Amanda 的会议上做笔记，而 Amanda 不能在任何会议上做笔记。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-523">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="a9e6a-524"><a name="bkmeetingparticipants"> </a></span><span class="sxs-lookup"><span data-stu-id="a9e6a-524"><a name="bkmeetingparticipants"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

## <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="a9e6a-525">会议策略设置 - 参与者和来宾</span><span class="sxs-lookup"><span data-stu-id="a9e6a-525">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="a9e6a-526">这些设置可以控制哪些与会者在进入会议之前在大厅等待，以及允许他们参与会议的级别。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-526">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="a9e6a-527">允许匿名用户启动会议</span><span class="sxs-lookup"><span data-stu-id="a9e6a-527">Let anonymous people start a meeting</span></span>](#let-anonymous-people-start-a-meeting)
- [<span data-ttu-id="a9e6a-528">自动管理人员</span><span class="sxs-lookup"><span data-stu-id="a9e6a-528">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="a9e6a-529">允许拨入用户绕过问题</span><span class="sxs-lookup"><span data-stu-id="a9e6a-529">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby)
- [<span data-ttu-id="a9e6a-530">允许团队成员绕过问题</span><span class="sxs-lookup"><span data-stu-id="a9e6a-530">Allow team members to bypass the lobby</span></span>](#allow-team-members-to-bypass-the-lobby)
- [<span data-ttu-id="a9e6a-531">启用实时字幕</span><span class="sxs-lookup"><span data-stu-id="a9e6a-531">Enable live captions</span></span>](#enable-live-captions)
- [<span data-ttu-id="a9e6a-532">在会议中允许聊天</span><span class="sxs-lookup"><span data-stu-id="a9e6a-532">Allow chat in meetings</span></span>](#allow-chat-in-meetings)

> [!NOTE]
><span data-ttu-id="a9e6a-533">加入会议的选项会有所不同，这取决于每个 Teams 组的设置和连接方法。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-533">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="a9e6a-534">如果小组有音频会议，并使用它来连接，请参阅 [音频会议](./audio-conferencing-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-534">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing](./audio-conferencing-in-office-365.md).</span></span> <span data-ttu-id="a9e6a-535">如果 Teams 组没有音频会议，请参阅 [在 Teams 中加入会议](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-535">If your Teams group doesn't have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

### <a name="let-anonymous-people-start-a-meeting"></a><span data-ttu-id="a9e6a-536">允许匿名人员发起会议</span><span class="sxs-lookup"><span data-stu-id="a9e6a-536">Let anonymous people start a meeting</span></span>

<span data-ttu-id="a9e6a-537">这是按组织者的策略，允许召开无领导会议。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-537">This is a per-organizer policy that allows for leaderless conferencing meetings.</span></span> <span data-ttu-id="a9e6a-538">此设置可控制匿名用户是否可以在没有来自组织的认证用户出席的情况下加入会议。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-538">This setting controls whether anonymous users can join the meeting without an authenticated user from the organization in attendance.</span></span> <span data-ttu-id="a9e6a-539">默认情况下，这个设置是关闭的，这意味着匿名用户将在大厅里等待，直到组织的认证用户加入会议。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-539">By default, this setting is turned off which means anonymous users will wait in the lobby until an authenticated user from the organization joins the meeting.</span></span>

> [!NOTE]
> <span data-ttu-id="a9e6a-p168">如果关闭此设置，并且匿名用户先加入会议且放在俱乐部中，则组织用户必须与 Teams 客户端加入会议，以将用户从俱乐部中离开。没有可供拨号用户的控音控件。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-p168">If this setting is turned off and an anonymous user joins the meeting first and is placed in the lobby, an organization user must join the meeting with a Teams client to admit the user from the lobby. There are no lobby controls available for dialed in users.</span></span>

### <a name="automatically-admit-people"></a><span data-ttu-id="a9e6a-542">自动允许人员</span><span class="sxs-lookup"><span data-stu-id="a9e6a-542">Automatically admit people</span></span>

<span data-ttu-id="a9e6a-543">这是按组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-543">This is a per-organizer policy.</span></span> <span data-ttu-id="a9e6a-544">此设置可以控制人员是直接加入会议还是在大厅里等待，直到受认证的用户入场。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-544">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span> <span data-ttu-id="a9e6a-545">此设置不适用于拨入用户。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-545">This setting does not apply to dial-in users.</span></span>

![屏幕截图显示在大厅里与用户见面的画面](media/meeting-policies-lobby.png)

 <span data-ttu-id="a9e6a-547">会议组织者可以在会议邀请中选择 **“会议选项”**，为他们安排的每次会议更改此设置。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-547">Meeting organizers can select **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span>

> [!NOTE]
> <span data-ttu-id="a9e6a-p170">在会议选项中，设置标记为"谁可以绕过问题"。如果更改任何用户的默认设置，它将应用于该用户组织的所有新会议以及用户未修改会议选项的任何之前会议。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-p170">In the meeting options the setting is labeled "Who can bypass the lobby". If you change the default setting for any user, it will apply to all new meetings organized by that user and any prior meetings where the user didn't modify Meeting options.</span></span>
  
|<span data-ttu-id="a9e6a-550">设置值</span><span class="sxs-lookup"><span data-stu-id="a9e6a-550">Setting value</span></span>  |<span data-ttu-id="a9e6a-551">加入行为</span><span class="sxs-lookup"><span data-stu-id="a9e6a-551">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="a9e6a-552">**每个人**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-552">**Everyone**</span></span>   |<span data-ttu-id="a9e6a-553">所有参会人员无需在大厅等待，直接加入会议。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-553">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="a9e6a-554">这包括经过认证的用户、来自受信任组织的外部用户 (联合)、客人和匿名用户。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-554">This includes authenticated users, external users from trusted organizations (federated), guests, and anonymous users.</span></span>     |
|<span data-ttu-id="a9e6a-555">**我的组织中人员、受信任的组织和来宾**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-555">**People in my organization, trusted organizations, and guests**</span></span>     |<span data-ttu-id="a9e6a-p172">组织中经过身份验证的用户（包括来宾用户和受信任的组织的用户）直接加入会议，而无需等待。匿名用户等待等待。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-p172">Authenticated users within the organization, including guest users and the users from trusted organizations, join the meeting directly without waiting in the lobby. Anonymous users wait in the lobby.</span></span>   |
|<span data-ttu-id="a9e6a-558">**组织中用户和来宾**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-558">**People in my organization and guests**</span></span>    |<span data-ttu-id="a9e6a-559">来自组织内部的认证用户，包括来宾用户，直接加入会议，无需在大厅等待。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-559">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="a9e6a-560">来自可信组织的用户和匿名用户在大厅里等待。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-560">Users from trusted organizations and anonymous users wait in the lobby.</span></span> <span data-ttu-id="a9e6a-561">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-561">This is the default setting.</span></span>           |
|<span data-ttu-id="a9e6a-562">**仅管理器**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-562">**Organizer only**</span></span>    |<span data-ttu-id="a9e6a-563">只有会议组织者才能直接参加会议，无需在大厅等待。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-563">Only meeting organizers can join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="a9e6a-564">其他所有人，包括组织内部的认证用户、访客用户、来自受信任组织的用户和匿名用户都必须在大厅里等待。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-564">Everyone else, including authenticated users within the organization, guest users, users from trusted organizations and anonymous users must wait in the lobby.</span></span>           |
|<span data-ttu-id="a9e6a-565">**我的组织中人员**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-565">**People in my organization**</span></span>  |<span data-ttu-id="a9e6a-566">来自组织内部的认证用户，包括来宾用户，直接加入会议，无需在大厅等待。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-566">Authenticated users from within the organization, excluding guest users, join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="a9e6a-567">来自可信组织的用户和匿名用户在大厅里等待。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-567">Guests and users from trusted organizations and anonymous users wait in the lobby.</span></span>|

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a><span data-ttu-id="a9e6a-568">允许拨入用户绕过大厅</span><span class="sxs-lookup"><span data-stu-id="a9e6a-568">Allow dial-in users to bypass the lobby</span></span>

<span data-ttu-id="a9e6a-569">这是按组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-569">This is a per-organizer policy.</span></span> <span data-ttu-id="a9e6a-570">此设置可控制通过电话拨入的人是直接加入会议还是在大厅等待，而不考虑 **“自动接收人员”** 设置。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-570">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span> <span data-ttu-id="a9e6a-571">默认情况下，此设置已关闭。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-571">By default, this setting is turned off.</span></span> <span data-ttu-id="a9e6a-572">当此设置关闭时，拨号用户将在大厅中等待，直到组织用户用 Teams 客户端加入会议并接收他们。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-572">When this setting is turned off, dial-in users will wait in the lobby until an organization user joins the meeting with a Teams client and admits them.</span></span> <span data-ttu-id="a9e6a-573">打开此设置后，拨入用户将自动加入会议。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-573">When this setting is turned on, dial-in users will automatically join the meeting.</span></span>

> [!NOTE]
> <span data-ttu-id="a9e6a-574">如果更改任何用户的默认设置，它将适用于该用户组织的所有新会议以及该用户没有修改会议选项的任何之前会议。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-574">If you change the default setting for any user, it will apply to all new meetings organized by that user and any prior meetings where the user didn't modify Meeting options.</span></span>

### <a name="allow-team-members-to-bypass-the-lobby"></a><span data-ttu-id="a9e6a-575">允许团队成员绕过绕过问题</span><span class="sxs-lookup"><span data-stu-id="a9e6a-575">Allow team members to bypass the lobby</span></span>

<span data-ttu-id="a9e6a-576">会议策略有一个设置，允许工作组成员绕过会议主场。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-576">Meeting policies have a setting for letting team members bypass the meeting lobby.</span></span> <span data-ttu-id="a9e6a-577">我们已为组织内部人员添加了 EveryoneInCompanyExcludingGuests 选项，以便绕过客人，但阻止来宾用户绕过客人。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-577">We've added the EveryoneInCompanyExcludingGuests option for people in the organization to bypass the lobby but exclude guest users from bypassing the lobby.</span></span>

### <a name="enable-live-captions"></a><span data-ttu-id="a9e6a-578">启用实时字幕</span><span class="sxs-lookup"><span data-stu-id="a9e6a-578">Enable live captions</span></span>

<span data-ttu-id="a9e6a-579">这是按用户策略，在会议期间适用。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-579">This is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="a9e6a-580">此设置控制 **开启实时字幕** 选项是否可以让用户在参加的会议中开启和关闭实时字幕。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-580">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![显示开启实时字幕选项的屏幕截图](media/meeting-policies-live-captions.png)

|<span data-ttu-id="a9e6a-582">设置值</span><span class="sxs-lookup"><span data-stu-id="a9e6a-582">Setting value</span></span> |<span data-ttu-id="a9e6a-583">行为</span><span class="sxs-lookup"><span data-stu-id="a9e6a-583">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="a9e6a-584">**已禁用，但用户可以替代**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-584">**Disabled but the user can override**</span></span>     | <span data-ttu-id="a9e6a-585">在会议期间，实时字幕不会自动为用户开启。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-585">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="a9e6a-586">用户在溢出 (**...**) 菜单中看到 **“开启实时字幕”** 选项，即可其打开。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-586">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="a9e6a-587">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-587">This is the default setting.</span></span> |
|<span data-ttu-id="a9e6a-588">**禁用**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-588">**Disabled**</span></span>     | <span data-ttu-id="a9e6a-589">在会议期间，将禁用用户的实时字幕。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-589">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="a9e6a-590">用户无法选择启用它们。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-590">The user doesn't have the option to turn them on.</span></span>          |

<span data-ttu-id="a9e6a-591"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="a9e6a-591"><a name="bkcontentsharing"> </a></span></span>

### <a name="allow-chat-in-meetings"></a><span data-ttu-id="a9e6a-592">允许在会议中聊天</span><span class="sxs-lookup"><span data-stu-id="a9e6a-592">Allow chat in meetings</span></span>

<span data-ttu-id="a9e6a-p181">这是按参与者设置。此设置控制用户会议是否允许进行会议聊天。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-p181">This is a per-participant setting. This setting controls whether meeting chat is allowed in the user's meeting.</span></span>

<span data-ttu-id="a9e6a-595"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="a9e6a-595"><a name="bkparticipantsandguests"> </a></span></span>

## <a name="meeting-policy-settings---designated-presenter-role-mode"></a><span data-ttu-id="a9e6a-596">会议策略设置 - 指定的演示者角色模式</span><span class="sxs-lookup"><span data-stu-id="a9e6a-596">Meeting policy settings - Designated presenter role mode</span></span>

<span data-ttu-id="a9e6a-597">这是按用户策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-597">This is a per-user policy.</span></span> <span data-ttu-id="a9e6a-598">通过此设置，可更改 Teams 客户端中 **“会议选项中”** 的 **“谁能演示?”** 设置的默认值。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-598">This setting lets you change the default value of the **Who can present?** setting in **Meeting options** in the Teams client.</span></span> <span data-ttu-id="a9e6a-599">此策略设置影响所有会议，包括 “立即开会会议”。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-599">This policy setting affects all meetings, including Meet Now meetings.</span></span>

<span data-ttu-id="a9e6a-600">通过 **“谁能演示?”** 会议组织者可以选择谁可以成为会议中的演示者。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-600">The **Who can present?** setting lets meeting organizers choose who can be presenters in a meeting.</span></span> <span data-ttu-id="a9e6a-601">要了解更多信息，请参阅 [更改 Teams 会议的与会者设置](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) 和 [Teams 会议中的角色](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-601">To learn more, see [Change participant settings for a Teams meeting](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) and [Roles in a Teams meeting](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).</span></span>

<span data-ttu-id="a9e6a-602">可以使用 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有的 Teams 会议策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-602">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="a9e6a-603">或者，使用 [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet 创建一个新的 Teams 会议策略，并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-603">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="a9e6a-604">要在 Teams 中指定 **“谁能演示?”** 设置的默认值，请将 **DesignatedPresenterRoleMode** 参数设置为以下之一:</span><span class="sxs-lookup"><span data-stu-id="a9e6a-604">To specify the default value of the **Who can present?** setting in Teams, set the **DesignatedPresenterRoleMode** parameter to one of the following settings:</span></span>

- <span data-ttu-id="a9e6a-605">**EveryoneUserOverride**:  所有会议参与者都能成为演示者。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-605">**EveryoneUserOverride**:  All meeting participants can be presenters.</span></span> <span data-ttu-id="a9e6a-606">此值为默认值。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-606">This is the default value.</span></span> <span data-ttu-id="a9e6a-607">该参数对应 Teams 中的 **“每个人”** 设置。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-607">This parameter corresponds to the **Everyone** setting in Teams.</span></span>
- <span data-ttu-id="a9e6a-608">**EveryoneInCompanyUserOverride**: 组织中的认证用户，包括客人用户，都能成为演示者。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-608">**EveryoneInCompanyUserOverride**: Authenticated users in the organization, including guest users, can be presenters.</span></span> <span data-ttu-id="a9e6a-609">此参数对应 Teams 中 **“我的组织中的人员”** 设置。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-609">This parameter corresponds to the **People in my organization** setting in Teams.</span></span>
- <span data-ttu-id="a9e6a-610">**OrganizerOnlyUserOverride**: 只有会议组织者可以成为演示者，所有其他会议参与者都将指定为与会者。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-610">**OrganizerOnlyUserOverride**: Only the meeting organizer can be a presenter and all meeting participants are designated as attendees.</span></span> <span data-ttu-id="a9e6a-611">此参数对应 Teams 中的 **“只有我”** 设置。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-611">This parameter corresponds to the **Only me** setting in Teams.</span></span>

<span data-ttu-id="a9e6a-612">此外，还可以在 Teams 管理中心编辑此策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-612">Additionally, you can edit this policy in the Teams admin center.</span></span>

![Teams 管理中心的屏幕截图](media/designated-presenter-role.png)

<span data-ttu-id="a9e6a-614">请记住，在设置默认值后，会议组织者仍然可以在 Teams 中更改此设置，并选择谁可以在他们安排的会议中演示。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-614">Keep in mind that after you set the default value, meeting organizers can still change this setting in Teams and choose who can present in the meetings that they schedule.</span></span>

## <a name="meeting-policy-settings---meeting-attendance-report"></a><span data-ttu-id="a9e6a-615">会议策略设置 - 会议出席报告</span><span class="sxs-lookup"><span data-stu-id="a9e6a-615">Meeting policy settings - Meeting attendance report</span></span>

<span data-ttu-id="a9e6a-616">这是按用户策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-616">This is a per-user policy.</span></span> <span data-ttu-id="a9e6a-617">此设置控制会议组织者是否可以下载 [会议出席报告](teams-analytics-and-reports/meeting-attendance-report.md)。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-617">This setting controls whether meeting organizers can download the [meeting attendance report](teams-analytics-and-reports/meeting-attendance-report.md).</span></span>

<span data-ttu-id="a9e6a-618">目前，只能使用 PowerShell 来配置此策略设置。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-618">Currently, you can only use PowerShell to configure this policy setting.</span></span> <span data-ttu-id="a9e6a-619">可以使用 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有的 Teams 会议策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-619">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="a9e6a-620">或者，使用 [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet 创建一个新的 Teams 会议策略，并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-620">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="a9e6a-621">若要启用会议组织者下载会议出席报告，请将 **AllowEngagementReport** 参数设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-621">To enable a meeting organizer to download the meeting attendance report, set the **AllowEngagementReport** parameter  to **Enabled**.</span></span> <span data-ttu-id="a9e6a-622">启用后，下载报告的选项会显示在 **“参与者”** 窗格中。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-622">When enabled, the option to download the report is displayed in the **Participants** pane.</span></span>

<span data-ttu-id="a9e6a-623">若要防止会议组织者下载报告，请将该参数设置为 **禁用**。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-623">To prevent a meeting organizer from downloading the report, set the parameter to **Disabled**.</span></span> <span data-ttu-id="a9e6a-624">默认情况下，该设置是禁用的，并且下载报告的选项不可用。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-624">By default, this setting is disabled and the option to download the report isn't available.</span></span>

## <a name="meeting-policy-settings---meeting-provider-for-islands-mode"></a><span data-ttu-id="a9e6a-625">会议策略设置 - 并行模式的会议提供程序</span><span class="sxs-lookup"><span data-stu-id="a9e6a-625">Meeting policy settings - Meeting provider for Islands mode</span></span>

<span data-ttu-id="a9e6a-626">这是按用户策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-626">This is a per-user policy.</span></span> <span data-ttu-id="a9e6a-627">此设置可控制 *处于并行模式的用户* 使用哪个 Outlook 会议加载项。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-627">This setting controls which Outlook meeting add-in is used for *users who are in Islands mode*.</span></span> <span data-ttu-id="a9e6a-628">你可以指定用户是只能使用 Team 会议加载项，还是可同时使用 Teams 会议加载项和 Skype for Business 会议加载项来在 Outlook 中安排会议。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-628">You can specify whether users can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins to schedule meetings in Outlook.</span></span>

<span data-ttu-id="a9e6a-629">你只能将此策略应用于处于孤岛模式且其 Teams 会议策略中的 **AllowOutlookAddIn** 参数设置为 **True** 的用户。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-629">You can only apply this policy to users who are in Islands mode and have the **AllowOutlookAddIn** parameter set to **True** in their Teams meeting policy.</span></span>

<span data-ttu-id="a9e6a-630">目前，只能使用 PowerShell 来设置该策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-630">Currently, you can only use PowerShell to set this policy.</span></span> <span data-ttu-id="a9e6a-631">可以使用 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有的 Teams 会议策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-631">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="a9e6a-632">或者，使用 [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet 创建一个新的 Teams 会议策略，并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-632">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="a9e6a-633">若要指定希望用户可以使用哪种会议加载项，请按以下方式设置 **PreferredMeetingProviderForIslandsMode** 参数:</span><span class="sxs-lookup"><span data-stu-id="a9e6a-633">To specify which meeting add-in you want to be available to users, set the **PreferredMeetingProviderForIslandsMode** parameter as follows:</span></span>

- <span data-ttu-id="a9e6a-634">将参数设置为 **TeamsAndSfB** 以启用 Outlook 中的 Teams 会议加载项和 Skype for Business 加载项。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-634">Set the parameter to **TeamsAndSfB** to enable both the Teams Meeting add-in and Skype for Business add-in in Outlook.</span></span> <span data-ttu-id="a9e6a-635">此值为默认值。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-635">This is the default value.</span></span>
- <span data-ttu-id="a9e6a-636">将参数设置为 **Teams**，以便仅启用 Outlook 中的 Teams 会议加载项。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-636">Set the parameter to **Teams** to enable only the Teams Meeting add-in in Outlook.</span></span> <span data-ttu-id="a9e6a-637">此策略设置可确保所有将来的会议均具有 Teams 会议的加入链接。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-637">This policy setting ensures that all future meetings have a Teams meeting join link.</span></span> <span data-ttu-id="a9e6a-638">它不能将现有的 Skype for Business 会议加入链接迁移到 Teams。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-638">It doesn't migrate existing Skype for Business meeting join links to Teams.</span></span> <span data-ttu-id="a9e6a-639">该策略设置不会影响 Skype for Business 中的状态、聊天、PSTN 呼叫或任何其他功能，这意味着用户将继续使用 Skype for Business 的这些功能。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-639">This policy setting doesn't affect presence, chat, PSTN calling, or any other capabilities in Skype for Business, which means that users will continue to use Skype for Business for these capabilities.</span></span>

  <span data-ttu-id="a9e6a-640">如果将参数设置为 **Teams**，然后切换回 **TeamsAndSfB**，则将启用这两个会议加载项。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-640">If you set the parameter to **Teams**, and then switch back to **TeamsAndSfB**, both meeting add-ins are enabled.</span></span> <span data-ttu-id="a9e6a-641">现有的团队会议加入链接将 **不会** 迁移到 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-641">Existing Teams meeting join links **won't** be migrated to Skype for Business.</span></span> <span data-ttu-id="a9e6a-642">只有在更改后安排的 Skype for Business 会议才会有 Skype for Business 会议加入链接。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-642">Only Skype for Business meetings scheduled after the change will have a Skype for Business meeting join link.</span></span>

## <a name="meeting-policy-settings---video-filters-mode"></a><span data-ttu-id="a9e6a-643">会议策略设置 - 视频筛选器模式</span><span class="sxs-lookup"><span data-stu-id="a9e6a-643">Meeting policy settings - Video filters mode</span></span>

<span data-ttu-id="a9e6a-p197">这是每用户策略。此设置控制用户是否可以自定义他们在会议中的视频背景。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-p197">This is a per-user policy. This setting controls whether users can customize their video background in a meeting.</span></span>

<span data-ttu-id="a9e6a-646">目前，只能使用 PowerShell 来设置该策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-646">Currently, you can only use PowerShell to set this policy.</span></span> <span data-ttu-id="a9e6a-647">可以使用 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有的 Teams 会议策略。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-647">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="a9e6a-648">或者，使用 [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet 创建一个新的 Teams 会议策略，然后将该策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-648">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet, and then assign the policy to users.</span></span>

<span data-ttu-id="a9e6a-649">要指定用户是否可以在会议中自定义视频背景，请按以下方式设置 **VideoFiltersMode** 参数:</span><span class="sxs-lookup"><span data-stu-id="a9e6a-649">To specify whether users can customize their video background in a meeting, set the **VideoFiltersMode** parameter as follows:</span></span>

|<span data-ttu-id="a9e6a-650">在 PowerShell 中设置值</span><span class="sxs-lookup"><span data-stu-id="a9e6a-650">Setting value in PowerShell</span></span> |<span data-ttu-id="a9e6a-651">行为</span><span class="sxs-lookup"><span data-stu-id="a9e6a-651">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="a9e6a-652">**NoFilters**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-652">**NoFilters**</span></span>     |<span data-ttu-id="a9e6a-653">用户无法自定义其视频背景。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-653">User can't customize their video background.</span></span>|
|<span data-ttu-id="a9e6a-654">**BlurOnly**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-654">**BlurOnly**</span></span>     |<span data-ttu-id="a9e6a-655">用户可以模糊显示其视频背景。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-655">Users can blur their video background.</span></span> |
|<span data-ttu-id="a9e6a-656">**BlurandDefaultBackgrounds**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-656">**BlurandDefaultBackgrounds**</span></span>     |<span data-ttu-id="a9e6a-657">用户可以选择模糊显示视频背景或选择从默认的图像集作为他们的背景。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-657">User has the option to blur their video background or choose from the default set of images to use as their background.</span></span> |
|<span data-ttu-id="a9e6a-658">**AllFilters**</span><span class="sxs-lookup"><span data-stu-id="a9e6a-658">**AllFilters**</span></span>     |<span data-ttu-id="a9e6a-659">用户可以选择模糊显示视频背景、从默认的图像集选择、或上传自定义图像作为他们的背景。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-659">User has the option to blur their video background, choose from the default set of images, or upload custom images to use as their background.</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="a9e6a-660">用户上传的图片不会经过 Teams 的筛选。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-660">Images uploaded by users aren't screened by Teams.</span></span> <span data-ttu-id="a9e6a-661">当使用 **AllFilters** 设置时，应该制定内部组织政策，以防止用户上传攻击性或不适当的图像，或组织无权用于 Teams 会议背景的图像。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-661">When you use the **AllFilters** setting, you should have internal organization policies to prevent users from uploading offensive or inappropriate images, or images your organization don't have rights to use for Teams meeting backgrounds.</span></span>

> [!NOTE]
> <span data-ttu-id="a9e6a-662">并非所有 Teams 客户端都有这些功能。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-662">These features are not available for all Teams clients.</span></span> <span data-ttu-id="a9e6a-663">更多信息，请参阅 [会议和现场活动](https://support.microsoft.com/office/meetings-and-live-events-5c3e0646-dc37-45ad-84a4-1666fac62d4e) 中的 _视频和背景_ 标题。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-663">For more information, see the _Video and backgrounds_ title in [Meetings and live events](https://support.microsoft.com/office/meetings-and-live-events-5c3e0646-dc37-45ad-84a4-1666fac62d4e).</span></span>

## <a name="meeting-policy-settings---meeting-reactions"></a><span data-ttu-id="a9e6a-664">会议策略设置 - 会议回应</span><span class="sxs-lookup"><span data-stu-id="a9e6a-664">Meeting policy settings - Meeting reactions</span></span>

<span data-ttu-id="a9e6a-665">AllowMeetingReactions 设置只能使用 PowerShell 应用。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-665">The AllowMeetingReactions setting can only be applied using PowerShell.</span></span> <span data-ttu-id="a9e6a-666">在 Teams 管理中心，没有任何选项可以打开或关闭 AllowMeetingReactions。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-666">There is no option to toggle AllowMeetingReactions on or off from the Teams admin center.</span></span>

<span data-ttu-id="a9e6a-667">会议回应默认为“关闭”。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-667">Meeting reactions are Off by default.</span></span> <span data-ttu-id="a9e6a-668">关闭用户的回应，并不意味着用户不能在自己安排的会议中使用回应。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-668">Turning off reactions for a user doesn't mean that a user can't use reactions in meetings they schedule.</span></span> <span data-ttu-id="a9e6a-669">无论默认设置如何，会议组织者仍然可以从会议选项页面开启回应。</span><span class="sxs-lookup"><span data-stu-id="a9e6a-669">The meeting organizer can still turn on reactions from the meeting option page, regardless of the default setting.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a9e6a-670">相关主题</span><span class="sxs-lookup"><span data-stu-id="a9e6a-670">Related topics</span></span>

- [<span data-ttu-id="a9e6a-671">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="a9e6a-671">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="a9e6a-672">向 Teams 中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="a9e6a-672">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="a9e6a-673">从用户删除 RestrictedAnonymousAccess Teams 会议策略</span><span class="sxs-lookup"><span data-stu-id="a9e6a-673">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)
