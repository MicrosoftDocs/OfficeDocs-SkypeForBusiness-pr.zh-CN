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
description: 了解如何管理团队中的会议策略设置，并使用它们控制由用户安排的会议参与者可使用的功能。
ms.openlocfilehash: 8846dea07d0e25a628341e853dee64d42d3e043a
ms.sourcegitcommit: fb4edc26c566228d74c10cb51a063b5fdc7e11a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48177402"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="1afd3-103">管理团队中的会议策略</span><span class="sxs-lookup"><span data-stu-id="1afd3-103">Manage meeting policies in Teams</span></span>

::: zone target="docs"
<span data-ttu-id="1afd3-104">会议策略Meeting policies用于控制组织中用户安排的会议的与会者可用的功能。</span><span class="sxs-lookup"><span data-stu-id="1afd3-104">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="1afd3-105">你可以使用自动创建或创建和分配自定义策略的全局 (组织范围默认) 策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-105">You can use the global (Org-wide default) policy that's automatically created or create and assign custom policies.</span></span> <span data-ttu-id="1afd3-106">可在 Microsoft 团队管理中心或通过使用 [PowerShell](teams-powershell-overview.md)管理会议策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-106">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1afd3-107">有关使用角色管理会议演示者和与会者的权限的信息，请参阅 [团队会议中的角色](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)。</span><span class="sxs-lookup"><span data-stu-id="1afd3-107">For information about using roles to manage the permissions of meeting presenters and attendees, see [Roles in a Teams meeting](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).</span></span>

<span data-ttu-id="1afd3-108">你可以通过以下方式实施策略，这会在会议开始之前、会议期间或会议后影响用户的会议体验。</span><span class="sxs-lookup"><span data-stu-id="1afd3-108">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="1afd3-109">实现类型</span><span class="sxs-lookup"><span data-stu-id="1afd3-109">Implementation type</span></span>  |<span data-ttu-id="1afd3-110">说明</span><span class="sxs-lookup"><span data-stu-id="1afd3-110">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="1afd3-111">每个组织者</span><span class="sxs-lookup"><span data-stu-id="1afd3-111">Per-organizer</span></span>    |<span data-ttu-id="1afd3-112">实施按组织者策略时，所有会议参与者都将继承组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-112">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="1afd3-113">例如， **自动允许人员** 为每个组织者策略，并控制用户是否直接加入会议，或在会议厅中等待分配了该策略的用户安排的会议。</span><span class="sxs-lookup"><span data-stu-id="1afd3-113">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="1afd3-114">每用户</span><span class="sxs-lookup"><span data-stu-id="1afd3-114">Per-user</span></span>    |<span data-ttu-id="1afd3-115">当你实现每用户策略时，仅应用每用户策略来限制组织者和/或会议参与者的某些功能。</span><span class="sxs-lookup"><span data-stu-id="1afd3-115">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="1afd3-116">例如，" **允许在频道中立即开会** " 是每用户策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-116">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="1afd3-117">每个组织者和每用户</span><span class="sxs-lookup"><span data-stu-id="1afd3-117">Per-organizer and per-user</span></span>     |<span data-ttu-id="1afd3-118">当你实现每个组织单位和每用户策略的组合时，某些功能将根据其策略和组织者的策略来限制会议参与者。</span><span class="sxs-lookup"><span data-stu-id="1afd3-118">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="1afd3-119">例如，" **允许云录制** " 是基于每个组织者和每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-119">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="1afd3-120">启用此设置可允许会议组织者和参与者开始和停止录制。</span><span class="sxs-lookup"><span data-stu-id="1afd3-120">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span>

<span data-ttu-id="1afd3-121">你可以编辑全局策略中的设置，或者创建并分配一个或多个自定义策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-121">You can edit the settings in the global policy or create and assign one or more custom policies.</span></span> <span data-ttu-id="1afd3-122">除非你创建和分配自定义策略，否则用户将获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-122">Users will get the global policy unless you create and assign a custom policy.</span></span>

> [!NOTE]
> <span data-ttu-id="1afd3-123">"会议详细信息" 按钮在用户启用音频会议许可证或用户允许音频会议的情况下可用时，会议详细信息将不可用。</span><span class="sxs-lookup"><span data-stu-id="1afd3-123">Meeting details button will be available if a user has the audio conference licenses enabled or the user is allow for audio conferencing, if not, the meeting details will not be available.</span></span>

## <a name="create-a-custom-meeting-policy"></a><span data-ttu-id="1afd3-124">创建自定义会议策略</span><span class="sxs-lookup"><span data-stu-id="1afd3-124">Create a custom meeting policy</span></span>

1. <span data-ttu-id="1afd3-125">在 Microsoft 团队管理中心的左侧导航中，转到 "**会议**  >  **会议策略**"。</span><span class="sxs-lookup"><span data-stu-id="1afd3-125">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="1afd3-126">单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1afd3-126">Click **Add**.</span></span>
3. <span data-ttu-id="1afd3-127">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="1afd3-127">Enter a name and description for the policy.</span></span> <span data-ttu-id="1afd3-128">名称不能包含特殊字符或超过 64 个字符。</span><span class="sxs-lookup"><span data-stu-id="1afd3-128">The name can't contain special characters or be longer than 64 characters.</span></span>
4. <span data-ttu-id="1afd3-129">选择所需的设置。</span><span class="sxs-lookup"><span data-stu-id="1afd3-129">Choose the settings that you want.</span></span>
5. <span data-ttu-id="1afd3-130">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="1afd3-130">Click **Save**.</span></span>

<span data-ttu-id="1afd3-131">例如，假设你有一组用户并且你想要限制这组用户的会议所需的带宽量。</span><span class="sxs-lookup"><span data-stu-id="1afd3-131">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="1afd3-132">你要创建新的自定义策略并命名为“带宽限制”，然后禁用以下设置：</span><span class="sxs-lookup"><span data-stu-id="1afd3-132">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="1afd3-133">在“音频和视频”中：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="1afd3-133">Under **Audio & video**:</span></span>

- <span data-ttu-id="1afd3-134">禁用“允许云录制”。</span><span class="sxs-lookup"><span data-stu-id="1afd3-134">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="1afd3-135">禁用“允许 IP 视频”。</span><span class="sxs-lookup"><span data-stu-id="1afd3-135">Turn off Allow IP video.</span></span>

<span data-ttu-id="1afd3-136">在“内容共享”中：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="1afd3-136">Under **Content sharing**:</span></span>

- <span data-ttu-id="1afd3-137">禁用屏幕共享模式。</span><span class="sxs-lookup"><span data-stu-id="1afd3-137">Disable screen sharing mode.</span></span>
- <span data-ttu-id="1afd3-138">禁用“允许白板”。</span><span class="sxs-lookup"><span data-stu-id="1afd3-138">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="1afd3-139">禁用“允许共享笔记”。</span><span class="sxs-lookup"><span data-stu-id="1afd3-139">Turn off Allow shared notes.</span></span>

<span data-ttu-id="1afd3-140">然后将此策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="1afd3-140">Then assign the policy to the users.</span></span>

## <a name="edit-a-meeting-policy"></a><span data-ttu-id="1afd3-141">编辑会议策略</span><span class="sxs-lookup"><span data-stu-id="1afd3-141">Edit a meeting policy</span></span>

<span data-ttu-id="1afd3-142">你可以编辑全局策略和你创建的任何自定义策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-142">You can edit the global policy and any custom policies that you create.</span></span>

1. <span data-ttu-id="1afd3-143">在 Microsoft 团队管理中心的左侧导航中，转到 "**会议**  >  **会议策略**"。</span><span class="sxs-lookup"><span data-stu-id="1afd3-143">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="1afd3-144">通过单击策略名称左侧，然后单击 " **编辑**"，选择策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-144">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="1afd3-145">在此处进行所需的更改。</span><span class="sxs-lookup"><span data-stu-id="1afd3-145">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="1afd3-146">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="1afd3-146">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="1afd3-147">一次只能向一个用户分配一个会议策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-147">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="1afd3-148">将会议策略分配给用户</span><span class="sxs-lookup"><span data-stu-id="1afd3-148">Assign a meeting policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> <span data-ttu-id="1afd3-149">如果向用户分配了该策略，则不能删除该策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-149">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="1afd3-150">必须先为所有受影响的用户分配不同的策略，然后才能删除原始策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-150">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="1afd3-151">会议策略设置</span><span class="sxs-lookup"><span data-stu-id="1afd3-151">Meeting policy settings</span></span>

<span data-ttu-id="1afd3-152">在 " **会议策略** " 页面上选择现有策略或选择 " **添加** " 以添加新策略时，可以为以下项配置设置。</span><span class="sxs-lookup"><span data-stu-id="1afd3-152">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="1afd3-153">常规</span><span class="sxs-lookup"><span data-stu-id="1afd3-153">General</span></span>](#meeting-policy-settings---general)
- [<span data-ttu-id="1afd3-154">音频 & 视频</span><span class="sxs-lookup"><span data-stu-id="1afd3-154">Audio & video</span></span>](#meeting-policy-settings---audio--video)
- [<span data-ttu-id="1afd3-155">内容共享</span><span class="sxs-lookup"><span data-stu-id="1afd3-155">Content sharing</span></span>](#meeting-policy-settings---content-sharing)
- [<span data-ttu-id="1afd3-156">参与者 & 来宾</span><span class="sxs-lookup"><span data-stu-id="1afd3-156">Participants & guests</span></span>](#meeting-policy-settings---participants--guests)

::: zone-end

<span data-ttu-id="1afd3-157"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="1afd3-157"><a name="bkgeneral"> </a></span></span>

## <a name="meeting-policy-settings---general"></a><span data-ttu-id="1afd3-158">会议策略设置-常规</span><span class="sxs-lookup"><span data-stu-id="1afd3-158">Meeting policy settings - General</span></span>

- [<span data-ttu-id="1afd3-159">允许在频道中立即开会</span><span class="sxs-lookup"><span data-stu-id="1afd3-159">Allow Meet now in channels</span></span>](#allow-meet-now-in-channels)
- [<span data-ttu-id="1afd3-160">允许 Outlook 加载项</span><span class="sxs-lookup"><span data-stu-id="1afd3-160">Allow the Outlook add-in</span></span>](#allow-the-outlook-add-in)
- [<span data-ttu-id="1afd3-161">允许频道会议安排</span><span class="sxs-lookup"><span data-stu-id="1afd3-161">Allow channel meeting scheduling</span></span>](#allow-channel-meeting-scheduling)
- [<span data-ttu-id="1afd3-162">允许安排私人会议</span><span class="sxs-lookup"><span data-stu-id="1afd3-162">Allow scheduling private meetings</span></span>](#allow-scheduling-private-meetings)
- [<span data-ttu-id="1afd3-163">允许在私人会议中立即开会</span><span class="sxs-lookup"><span data-stu-id="1afd3-163">Allow Meet now in private meetings</span></span>](#allow-meet-now-in-private-meetings)

### <a name="allow-meet-now-in-channels"></a><span data-ttu-id="1afd3-164">允许在频道中立即开会</span><span class="sxs-lookup"><span data-stu-id="1afd3-164">Allow Meet now in channels</span></span>

<span data-ttu-id="1afd3-165">这是每用户策略，在会议开始之前应用。</span><span class="sxs-lookup"><span data-stu-id="1afd3-165">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="1afd3-166">此设置控制用户是否可以在团队频道中启动临时会议。</span><span class="sxs-lookup"><span data-stu-id="1afd3-166">This setting controls whether a user can start an ad hoc meeting in a Teams channel.</span></span> <span data-ttu-id="1afd3-167">如果启用此操作，则用户可以单击 " **开会** " 按钮启动临时会议或在频道中安排会议。</span><span class="sxs-lookup"><span data-stu-id="1afd3-167">If you turn this on, users can click **Meet** button to start an ad hoc meeting or schedule a meeting in the channel.</span></span> <span data-ttu-id="1afd3-168">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="1afd3-168">The default value is True.</span></span>

<span data-ttu-id="1afd3-169">[![显示邮件 ](media/meeting-policies-meet-now.png) 下方的 "立即开会" 图标的屏幕截图](media/meeting-policies-meet-now.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="1afd3-169">[ ![Screenshot showing the Meet now icon below a message](media/meeting-policies-meet-now.png) ](media/meeting-policies-meet-now.png#lightbox)</span></span>

### <a name="allow-the-outlook-add-in"></a><span data-ttu-id="1afd3-170">允许 Outlook 加载项</span><span class="sxs-lookup"><span data-stu-id="1afd3-170">Allow the Outlook add-in</span></span>

<span data-ttu-id="1afd3-171">这是每用户策略，在会议开始之前应用。</span><span class="sxs-lookup"><span data-stu-id="1afd3-171">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="1afd3-172">此设置控制是否可以在 Outlook (Windows、Mac、web 和移动) 中安排团队会议。</span><span class="sxs-lookup"><span data-stu-id="1afd3-172">This setting controls whether Teams meetings can be scheduled from within Outlook (Windows, Mac, web, and mobile).</span></span>

![显示安排新会议的功能的屏幕截图](media/meeting-policies-outlook-add-in.png)

<span data-ttu-id="1afd3-174">如果关闭此功能，用户在 Outlook 中创建新会议时，无法安排团队会议。</span><span class="sxs-lookup"><span data-stu-id="1afd3-174">If you turn this off, users are unable to schedule Teams meetings when they create a new meeting in Outlook.</span></span> <span data-ttu-id="1afd3-175">例如，在 Windows 上的 Outlook 中，" **新建团队会议** " 选项不会显示在功能区中。</span><span class="sxs-lookup"><span data-stu-id="1afd3-175">For example, in Outlook on Windows, the **New Teams Meeting** option won't show up in the ribbon.</span></span>

### <a name="allow-channel-meeting-scheduling"></a><span data-ttu-id="1afd3-176">允许频道会议安排</span><span class="sxs-lookup"><span data-stu-id="1afd3-176">Allow channel meeting scheduling</span></span>

<span data-ttu-id="1afd3-177">使用现有的 AllowChannelMeetingScheduling 策略控制可在团队频道日历上创建的事件类型。</span><span class="sxs-lookup"><span data-stu-id="1afd3-177">Use the existing AllowChannelMeetingScheduling policy to control the types of events that can be created on the team channel calendars.</span></span> <span data-ttu-id="1afd3-178">这是每用户策略，在会议开始之前应用。</span><span class="sxs-lookup"><span data-stu-id="1afd3-178">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="1afd3-179">此设置控制用户是否可以在团队频道中安排会议。</span><span class="sxs-lookup"><span data-stu-id="1afd3-179">This setting controls whether users can schedule a meeting in a Teams channel.</span></span> <span data-ttu-id="1afd3-180">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="1afd3-180">The default value is True.</span></span>

<span data-ttu-id="1afd3-181">如果此策略已关闭，用户将无法创建新的频道会议。</span><span class="sxs-lookup"><span data-stu-id="1afd3-181">If this policy is OFF, users will not be able to create new channel meetings.</span></span> <span data-ttu-id="1afd3-182">但是，现有频道会议可由事件的组织者编辑。</span><span class="sxs-lookup"><span data-stu-id="1afd3-182">However, existing channel meetings can be edited by the organizer of the event.</span></span>

<span data-ttu-id="1afd3-183">安排会议将被禁用。</span><span class="sxs-lookup"><span data-stu-id="1afd3-183">Schedule a meeting will be disabled.</span></span>

![显示团队中的 "安排会议" 选项的屏幕截图](media/schedule-meeting-option.png)

<span data-ttu-id="1afd3-185">频道选择已禁用。</span><span class="sxs-lookup"><span data-stu-id="1afd3-185">Channel selection is disabled.</span></span>

<span data-ttu-id="1afd3-186">[![显示 "日历" 选项的屏幕截图，用于选择要在其中安排会议的频道。 ](media/meeting-policies-select-a-channel-to-meet-in.png)](media/meeting-policies-select-a-channel-to-meet-in.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="1afd3-186">[ ![Screenshot showing the calendar option for selecting a channel that you want to schedule a meeting in.](media/meeting-policies-select-a-channel-to-meet-in.png) ](media/meeting-policies-select-a-channel-to-meet-in.png#lightbox)</span></span>

<span data-ttu-id="1afd3-187">在 "频道发布" 页面中，将禁用以下内容：</span><span class="sxs-lookup"><span data-stu-id="1afd3-187">In the channel posts page, the following will be disabled:</span></span>

- <span data-ttu-id="1afd3-188">"频道答复撰写" 框中的 "**安排会议**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="1afd3-188">**Schedule a meeting** button on the channel reply compose box.</span></span>
  <span data-ttu-id="1afd3-189">![显示 "日历" 选项的屏幕截图，用于选择要在其中安排会议的频道。](media/schedule-meeting-disabled-in-chat2.png)</span><span class="sxs-lookup"><span data-stu-id="1afd3-189">![Screenshot showing the calendar option for selecting a channel that you want to schedule a meeting in.](media/schedule-meeting-disabled-in-chat2.png)</span></span>
  
- <span data-ttu-id="1afd3-190">"在频道标题上**安排会议**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="1afd3-190">**Schedule a meeting** button on the channel header.</span></span>
  <span data-ttu-id="1afd3-191">![显示 "日历" 选项的屏幕截图，用于选择要在其中安排会议的频道。](media/schedule-now-in-header.png)</span><span class="sxs-lookup"><span data-stu-id="1afd3-191">![Screenshot showing the calendar option for selecting a channel that you want to schedule a meeting in.](media/schedule-now-in-header.png)</span></span>

<span data-ttu-id="1afd3-192">在频道日历中：</span><span class="sxs-lookup"><span data-stu-id="1afd3-192">In the channel calendar:</span></span>

- <span data-ttu-id="1afd3-193">将禁用频道日历标题上的 "**添加新事件**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="1afd3-193">**Add new event** button on channel calendar header will be disabled.</span></span>
  <span data-ttu-id="1afd3-194">![显示 "日历" 选项的屏幕截图，用于选择要在其中安排会议的频道。](media/add-new-event-disabled.png)</span><span class="sxs-lookup"><span data-stu-id="1afd3-194">![Screenshot showing the calendar option for selecting a channel that you want to schedule a meeting in.](media/add-new-event-disabled.png)</span></span>

- <span data-ttu-id="1afd3-195">用户将无法在频道日历上拖动和选择时间段以创建渠道会议。</span><span class="sxs-lookup"><span data-stu-id="1afd3-195">Users will not be able to drag and select a time block on the channel calendar to create a channel meeting.</span></span>

- <span data-ttu-id="1afd3-196">用户无法使用键盘快捷方式在频道日历上创建会议。</span><span class="sxs-lookup"><span data-stu-id="1afd3-196">Users cannot use Keyboard shortcuts to create a meeting on the channel calendar.</span></span>

<span data-ttu-id="1afd3-197">在管理中心：</span><span class="sxs-lookup"><span data-stu-id="1afd3-197">In the Admin Center:</span></span>

<span data-ttu-id="1afd3-198">"频道日历" 应用将显示在权限策略的 "管理员" 面板中的 " **Microsoft 应用** " 部分下方。</span><span class="sxs-lookup"><span data-stu-id="1afd3-198">The channel calendar app will show up under the **Microsoft apps** section in the admin panel for permission policies.</span></span>

![显示团队管理员控制台中的 Microsoft 应用策略的屏幕截图。](media/manage-microsoft-apps-policy.png)

### <a name="allow-scheduling-private-meetings"></a><span data-ttu-id="1afd3-200">允许安排私人会议</span><span class="sxs-lookup"><span data-stu-id="1afd3-200">Allow scheduling private meetings</span></span>

<span data-ttu-id="1afd3-201">这是每用户策略，在会议开始之前应用。</span><span class="sxs-lookup"><span data-stu-id="1afd3-201">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="1afd3-202">此设置控制用户是否可以在团队中安排私人会议。</span><span class="sxs-lookup"><span data-stu-id="1afd3-202">This setting controls whether users can schedule private meetings in Teams.</span></span> <span data-ttu-id="1afd3-203">当会议未发布到团队中的频道时，它是私有的。</span><span class="sxs-lookup"><span data-stu-id="1afd3-203">A meeting is private when it's not published to a channel in a team.</span></span>

<span data-ttu-id="1afd3-204">请注意，如果关闭 " **允许安排私人会议** " 和 " **允许频道会议计划**"，则会为团队中的用户禁用 " **添加必需与会者** " 和 " **添加频道** " 选项。</span><span class="sxs-lookup"><span data-stu-id="1afd3-204">Note that if you turn off **Allow scheduling private meetings** and **Allow channel meeting scheduling**,  the **Add required attendees** and **Add channel** options are disabled for users in Teams.</span></span> <span data-ttu-id="1afd3-205">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="1afd3-205">The default value is True.</span></span>

### <a name="allow-meet-now-in-private-meetings"></a><span data-ttu-id="1afd3-206">允许在私人会议中立即开会</span><span class="sxs-lookup"><span data-stu-id="1afd3-206">Allow Meet now in private meetings</span></span>

<span data-ttu-id="1afd3-207">这是每用户策略，在会议开始之前应用。</span><span class="sxs-lookup"><span data-stu-id="1afd3-207">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="1afd3-208">此设置控制用户是否可以启动 ad hoc 私人会议。</span><span class="sxs-lookup"><span data-stu-id="1afd3-208">This setting controls whether a user can start an ad hoc private meeting.</span></span>  <span data-ttu-id="1afd3-209">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="1afd3-209">The default value is True.</span></span>

<span data-ttu-id="1afd3-210"><a name="bkaudioandvideo"> </a></span><span class="sxs-lookup"><span data-stu-id="1afd3-210"><a name="bkaudioandvideo"> </a></span></span>

## <a name="meeting-policy-settings---audio--video"></a><span data-ttu-id="1afd3-211">会议策略设置-音频 & 视频</span><span class="sxs-lookup"><span data-stu-id="1afd3-211">Meeting policy settings - Audio & video</span></span>

- [<span data-ttu-id="1afd3-212">允许脚本</span><span class="sxs-lookup"><span data-stu-id="1afd3-212">Allow transcription</span></span>](#allow-transcription)
- [<span data-ttu-id="1afd3-213">允许云录制</span><span class="sxs-lookup"><span data-stu-id="1afd3-213">Allow cloud recording</span></span>](#allow-cloud-recording)
- [<span data-ttu-id="1afd3-214">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="1afd3-214">Allow IP video</span></span>](#allow-ip-video)
- [<span data-ttu-id="1afd3-215">媒体比特率 (Kbs) </span><span class="sxs-lookup"><span data-stu-id="1afd3-215">Media bit rate (Kbs)</span></span>](#media-bit-rate-kbs)

### <a name="allow-transcription"></a><span data-ttu-id="1afd3-216">允许脚本</span><span class="sxs-lookup"><span data-stu-id="1afd3-216">Allow transcription</span></span>

<span data-ttu-id="1afd3-217">这是每个组织单位和每用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="1afd3-217">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="1afd3-218">此设置控制播放会议录制期间是否提供字幕和脚本功能。</span><span class="sxs-lookup"><span data-stu-id="1afd3-218">This setting controls whether captions and transcription features are available during playback of meeting recordings.</span></span> <span data-ttu-id="1afd3-219">如果关闭此功能，在播放会议录制的过程中，" **搜索** " 和 **"抄送** " 选项将不可用。</span><span class="sxs-lookup"><span data-stu-id="1afd3-219">If you turn this off, the **Search** and **CC** options won't be available during playback of a meeting recording.</span></span> <span data-ttu-id="1afd3-220">启动录制的人员需要启用此设置，以便录制还包括脚本。</span><span class="sxs-lookup"><span data-stu-id="1afd3-220">The person who started the recording needs this setting turned on so that the recording also includes transcription.</span></span>

<span data-ttu-id="1afd3-221">请注意，当前只有在团队中将语言设置为英语且在会议中朗读英语的用户才支持使用录制的会议。</span><span class="sxs-lookup"><span data-stu-id="1afd3-221">Note that transcription for recorded meetings is currently only supported for users who have the language in Teams set to English and when English is spoken in the meeting.</span></span>

![显示会议中的脚本选项的屏幕截图](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a><span data-ttu-id="1afd3-223">允许云录制</span><span class="sxs-lookup"><span data-stu-id="1afd3-223">Allow cloud recording</span></span>

<span data-ttu-id="1afd3-224">这是每个组织单位和每用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="1afd3-224">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="1afd3-225">此设置控制是否可以录制此用户的会议。</span><span class="sxs-lookup"><span data-stu-id="1afd3-225">This setting controls whether this user's meetings can be recorded.</span></span> <span data-ttu-id="1afd3-226">录制可以由会议组织者或其他会议参与者启动（如果为参与者启用了该策略设置，并且他们是来自同一组织的经过身份验证的用户）。</span><span class="sxs-lookup"><span data-stu-id="1afd3-226">The recording can be started by the meeting organizer or by another meeting participant if the policy setting is turned on for the participant and if they're an authenticated user from the same organization.</span></span>

<span data-ttu-id="1afd3-227">组织外部的人员（如联盟用户和匿名用户）无法启动录制。</span><span class="sxs-lookup"><span data-stu-id="1afd3-227">People outside your organization, such as federated and anonymous users, can't start the recording.</span></span> <span data-ttu-id="1afd3-228">来宾用户无法启动或停止录制。</span><span class="sxs-lookup"><span data-stu-id="1afd3-228">Guest users can't start or stop the recording.</span></span>

![显示录制选项的屏幕截图](media/meeting-policies-recording.png)

<span data-ttu-id="1afd3-230">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="1afd3-230">Let's look at the following example.</span></span>

|<span data-ttu-id="1afd3-231">用户</span><span class="sxs-lookup"><span data-stu-id="1afd3-231">User</span></span> |<span data-ttu-id="1afd3-232">会议策略</span><span class="sxs-lookup"><span data-stu-id="1afd3-232">Meeting policy</span></span>  |<span data-ttu-id="1afd3-233">允许云录制</span><span class="sxs-lookup"><span data-stu-id="1afd3-233">Allow cloud recording</span></span> |
|---------|---------|---------|
|<span data-ttu-id="1afd3-234">Daniela</span><span class="sxs-lookup"><span data-stu-id="1afd3-234">Daniela</span></span> | <span data-ttu-id="1afd3-235">全局</span><span class="sxs-lookup"><span data-stu-id="1afd3-235">Global</span></span>   | <span data-ttu-id="1afd3-236">False</span><span class="sxs-lookup"><span data-stu-id="1afd3-236">False</span></span> |
|<span data-ttu-id="1afd3-237">Amanda</span><span class="sxs-lookup"><span data-stu-id="1afd3-237">Amanda</span></span> | <span data-ttu-id="1afd3-238">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="1afd3-238">Location1MeetingPolicy</span></span> | <span data-ttu-id="1afd3-239">True</span><span class="sxs-lookup"><span data-stu-id="1afd3-239">True</span></span>|
|<span data-ttu-id="1afd3-240">John (外部用户) </span><span class="sxs-lookup"><span data-stu-id="1afd3-240">John (external user)</span></span> | <span data-ttu-id="1afd3-241">不适用</span><span class="sxs-lookup"><span data-stu-id="1afd3-241">Not applicable</span></span> | <span data-ttu-id="1afd3-242">不适用</span><span class="sxs-lookup"><span data-stu-id="1afd3-242">Not applicable</span></span>|

<span data-ttu-id="1afd3-243">按 Daniela 组织的会议无法录制，并且 Amanda 已启用策略设置，无法录制 Daniela 组织的会议。</span><span class="sxs-lookup"><span data-stu-id="1afd3-243">Meetings organized by Daniela can't be recorded and Amanda, who has the policy setting enabled, can't record meetings organized by Daniela.</span></span> <span data-ttu-id="1afd3-244">可记录由 Amanda 组织的会议，但 Daniela，他们已禁用策略设置，并且 John 是外部用户，无法录制 Amanda 组织的会议。</span><span class="sxs-lookup"><span data-stu-id="1afd3-244">Meetings organized by Amanda can be recorded, however,  Daniela, who has the policy setting disabled and John who is an external user, can't record meetings organized by Amanda.</span></span>

<span data-ttu-id="1afd3-245">若要了解有关云会议录制的详细信息，请参阅 [团队云会议录制](cloud-recording.md)。</span><span class="sxs-lookup"><span data-stu-id="1afd3-245">To learn more about cloud meeting recording, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

### <a name="allow-ip-video"></a><span data-ttu-id="1afd3-246">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="1afd3-246">Allow IP video</span></span>

<span data-ttu-id="1afd3-247">这是每个组织单位和每用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="1afd3-247">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="1afd3-248">视频是会议的关键组件。</span><span class="sxs-lookup"><span data-stu-id="1afd3-248">Video is a key component to meetings.</span></span> <span data-ttu-id="1afd3-249">在某些组织中，管理员可能希望更好地控制哪些用户的会议有视频。</span><span class="sxs-lookup"><span data-stu-id="1afd3-249">In some organizations, admins might want more control over which users' meetings have video.</span></span> <span data-ttu-id="1afd3-250">此设置控制是否可以在用户托管的会议中以及用户开始的1:1 呼叫和组通话中打开视频。</span><span class="sxs-lookup"><span data-stu-id="1afd3-250">This setting controls whether video can be turned on in meetings hosted by a user and in 1:1 calls and group calls started by a user.</span></span> <span data-ttu-id="1afd3-251">已启用此策略的用户组织的会议，如果会议参与者也启用了该策略，则会议参与者允许会议中的视频共享。</span><span class="sxs-lookup"><span data-stu-id="1afd3-251">Meetings organized by a user who has this policy enabled, allow video sharing in the meeting by the meeting participants, if the meeting participants also have the policy enabled.</span></span> <span data-ttu-id="1afd3-252">未分配任何策略的会议参与者 (例如，匿名参与者和联盟参与者) 继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-252">Meeting participants who don't have any policies assigned (for example, anonymous and federated participants) inherit the policy of the meeting organizer.</span></span>

![显示带有音频和视频设置的会议的屏幕截图](media/meeting-policies-audio-video-settings.png)

<span data-ttu-id="1afd3-254">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="1afd3-254">Let's look at the following example.</span></span>

|<span data-ttu-id="1afd3-255">用户</span><span class="sxs-lookup"><span data-stu-id="1afd3-255">User</span></span> |<span data-ttu-id="1afd3-256">会议策略</span><span class="sxs-lookup"><span data-stu-id="1afd3-256">Meeting policy</span></span>  |<span data-ttu-id="1afd3-257">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="1afd3-257">Allow IP Video</span></span> |
|---------|---------|---------|
|<span data-ttu-id="1afd3-258">Daniela</span><span class="sxs-lookup"><span data-stu-id="1afd3-258">Daniela</span></span>   | <span data-ttu-id="1afd3-259">全局</span><span class="sxs-lookup"><span data-stu-id="1afd3-259">Global</span></span>   | <span data-ttu-id="1afd3-260">True</span><span class="sxs-lookup"><span data-stu-id="1afd3-260">True</span></span>        |
|<span data-ttu-id="1afd3-261">Amanda</span><span class="sxs-lookup"><span data-stu-id="1afd3-261">Amanda</span></span>    | <span data-ttu-id="1afd3-262">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="1afd3-262">Location1MeetingPolicy</span></span>        | <span data-ttu-id="1afd3-263">False</span><span class="sxs-lookup"><span data-stu-id="1afd3-263">False</span></span>      |

<span data-ttu-id="1afd3-264">通过 Daniela 托管的会议允许打开视频。</span><span class="sxs-lookup"><span data-stu-id="1afd3-264">Meetings hosted by Daniela allow video to be turned on.</span></span> <span data-ttu-id="1afd3-265">Daniela 可以加入会议并打开视频。</span><span class="sxs-lookup"><span data-stu-id="1afd3-265">Daniela can join the meeting and turn on video.</span></span> <span data-ttu-id="1afd3-266">Amanda 无法在 Daniela 的会议中启用视频，因为 Amanda 的策略设置为 "不允许视频"。</span><span class="sxs-lookup"><span data-stu-id="1afd3-266">Amanda can't turn on video in Daniela's meeting because Amanda's policy is set to not allow video.</span></span> <span data-ttu-id="1afd3-267">Amanda 可以查看会议中其他参与者共享的视频。</span><span class="sxs-lookup"><span data-stu-id="1afd3-267">Amanda can see videos shared by other participants in the meeting.</span></span>

<span data-ttu-id="1afd3-268">在 Amanda 托管的会议中，无论分配给他们的视频策略如何，任何人都无法打开视频。</span><span class="sxs-lookup"><span data-stu-id="1afd3-268">In meetings hosted by Amanda, no one can turn on video, regardless of the video policy assigned to them.</span></span> <span data-ttu-id="1afd3-269">这意味着 Daniela 无法在 Amanda 的会议中打开视频。</span><span class="sxs-lookup"><span data-stu-id="1afd3-269">This means Daniela can't turn on video in Amanda's meetings.</span></span>  

<span data-ttu-id="1afd3-270">如果 Daniela 通过视频 Amanda 调用，Amanda 只能通过音频应答呼叫。</span><span class="sxs-lookup"><span data-stu-id="1afd3-270">If Daniela calls Amanda with video on, Amanda can answer the call with audio only.</span></span>  <span data-ttu-id="1afd3-271">当呼叫连接时，Amanda 可以看到 Daniela 的视频，但无法打开视频。</span><span class="sxs-lookup"><span data-stu-id="1afd3-271">When the call is connected, Amanda can see Daniela's video, but can't turn on video.</span></span> <span data-ttu-id="1afd3-272">如果 Amanda 呼叫 Daniela，Daniela 可以通过视频和音频接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="1afd3-272">If Amanda calls Daniela, Daniela can answer the call with video and audio.</span></span> <span data-ttu-id="1afd3-273">通话接通后，Daniela 可以根据需要打开或关闭她的视频。</span><span class="sxs-lookup"><span data-stu-id="1afd3-273">When the call is connected, Daniela can turn on or turn off her video, as needed.</span></span>

### <a name="media-bit-rate-kbs"></a><span data-ttu-id="1afd3-274">媒体比特率 (Kbs) </span><span class="sxs-lookup"><span data-stu-id="1afd3-274">Media bit rate (Kbs)</span></span>

<span data-ttu-id="1afd3-275">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-275">This is a per-user policy.</span></span> <span data-ttu-id="1afd3-276">此设置确定用户的通话和会议中音频、视频和基于视频的应用共享传输的媒体比特率。</span><span class="sxs-lookup"><span data-stu-id="1afd3-276">This setting determines the media bit rate for audio, video, and video-based app sharing transmissions in calls and meetings for the user.</span></span> <span data-ttu-id="1afd3-277">它同时应用于呼叫或会议中用户的上行媒体和下行媒体遍历。</span><span class="sxs-lookup"><span data-stu-id="1afd3-277">It's applied to both the uplink and downlink media traversal for users in the call or meeting.</span></span> <span data-ttu-id="1afd3-278">此设置使你能够更细致地控制组织中的带宽管理。</span><span class="sxs-lookup"><span data-stu-id="1afd3-278">This setting gives you granular control over managing bandwidth in your organization.</span></span> <span data-ttu-id="1afd3-279">根据用户所需的会议方案，我们建议有足够的带宽来实现优质体验。</span><span class="sxs-lookup"><span data-stu-id="1afd3-279">Depending on the meetings scenarios required by users, we recommend having enough bandwidth in place for a good quality experience.</span></span> <span data-ttu-id="1afd3-280">最小值为 30 Kbps，最大值取决于会议方案。</span><span class="sxs-lookup"><span data-stu-id="1afd3-280">The minimum value is 30 Kbps and the maximum value depends on the meeting scenario.</span></span> <span data-ttu-id="1afd3-281">若要了解更多有关建议的最小带宽以供团队的优质会议、通话和实时活动，请参阅 [带宽要求](prepare-network.md#bandwidth-requirements)。</span><span class="sxs-lookup"><span data-stu-id="1afd3-281">To learn more about the minimum recommended bandwidth for good quality meetings, calls, and live events in Teams, see [Bandwidth requirements](prepare-network.md#bandwidth-requirements).</span></span>

<span data-ttu-id="1afd3-282">如果会议带宽不足，参与者会看到指示网络质量不佳的消息。</span><span class="sxs-lookup"><span data-stu-id="1afd3-282">If there isn't enough bandwidth for a meeting, participants see a message that indicates poor network quality.</span></span>

<span data-ttu-id="1afd3-283">对于需要高质量视频体验的会议（如 CEO 董事会会议和团队现场活动），建议将带宽设置为 10 Mbps。</span><span class="sxs-lookup"><span data-stu-id="1afd3-283">For meetings that need the highest-quality video experience, such as CEO board meetings and Teams live events, we recommend you set the bandwidth to 10 Mbps.</span></span> <span data-ttu-id="1afd3-284">即使设置了最大体验，团队媒体堆栈也会在检测到某些网络条件时适应低带宽条件，具体取决于方案。</span><span class="sxs-lookup"><span data-stu-id="1afd3-284">Even when the maximum experience is set, the Teams media stack adapts to low-bandwidth conditions when certain network conditions are detected, depending on the scenario.</span></span>

## <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="1afd3-285">会议策略设置-内容共享</span><span class="sxs-lookup"><span data-stu-id="1afd3-285">Meeting policy settings - Content sharing</span></span>

- [<span data-ttu-id="1afd3-286">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="1afd3-286">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="1afd3-287">允许参与者授予或请求控制</span><span class="sxs-lookup"><span data-stu-id="1afd3-287">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="1afd3-288">允许外部参与者授予或请求控制</span><span class="sxs-lookup"><span data-stu-id="1afd3-288">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="1afd3-289">允许 PowerPoint 共享</span><span class="sxs-lookup"><span data-stu-id="1afd3-289">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="1afd3-290">允许白板</span><span class="sxs-lookup"><span data-stu-id="1afd3-290">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="1afd3-291">允许共享笔记</span><span class="sxs-lookup"><span data-stu-id="1afd3-291">Allow shared notes</span></span>](#allow-shared-notes)

### <a name="screen-sharing-mode"></a><span data-ttu-id="1afd3-292">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="1afd3-292">Screen sharing mode</span></span>

<span data-ttu-id="1afd3-293">这是每个组织单位和每用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="1afd3-293">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="1afd3-294">此设置控制是否允许在用户的会议中共享桌面和/或窗口共享。</span><span class="sxs-lookup"><span data-stu-id="1afd3-294">This setting controls whether desktop and/or window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="1afd3-295">未分配任何策略的会议参与者 (例如，匿名、来宾、B2B 和联盟参与者) 继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-295">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="1afd3-296">设置值</span><span class="sxs-lookup"><span data-stu-id="1afd3-296">Setting value</span></span> |<span data-ttu-id="1afd3-297">行为</span><span class="sxs-lookup"><span data-stu-id="1afd3-297">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="1afd3-298">**整个屏幕**</span><span class="sxs-lookup"><span data-stu-id="1afd3-298">**Entire screen**</span></span>    | <span data-ttu-id="1afd3-299">会议中允许进行完整的桌面共享和应用程序共享</span><span class="sxs-lookup"><span data-stu-id="1afd3-299">Full desktop sharing and application sharing are allowed in the meeting</span></span> |
|<span data-ttu-id="1afd3-300">**单应用程序**</span><span class="sxs-lookup"><span data-stu-id="1afd3-300">**Single application**</span></span>   | <span data-ttu-id="1afd3-301">允许在会议中共享应用程序</span><span class="sxs-lookup"><span data-stu-id="1afd3-301">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="1afd3-302">**已禁用**</span><span class="sxs-lookup"><span data-stu-id="1afd3-302">**Disabled**</span></span>     |<span data-ttu-id="1afd3-303">会议中已关闭屏幕共享和应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="1afd3-303">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="1afd3-304">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="1afd3-304">Let's look at the following example.</span></span>

|<span data-ttu-id="1afd3-305">用户</span><span class="sxs-lookup"><span data-stu-id="1afd3-305">User</span></span> |<span data-ttu-id="1afd3-306">会议策略</span><span class="sxs-lookup"><span data-stu-id="1afd3-306">Meeting policy</span></span> |<span data-ttu-id="1afd3-307">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="1afd3-307">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="1afd3-308">Daniela</span><span class="sxs-lookup"><span data-stu-id="1afd3-308">Daniela</span></span>  | <span data-ttu-id="1afd3-309">全局</span><span class="sxs-lookup"><span data-stu-id="1afd3-309">Global</span></span>   | <span data-ttu-id="1afd3-310">整个屏幕</span><span class="sxs-lookup"><span data-stu-id="1afd3-310">Entire screen</span></span> |
|<span data-ttu-id="1afd3-311">Amanda</span><span class="sxs-lookup"><span data-stu-id="1afd3-311">Amanda</span></span>   | <span data-ttu-id="1afd3-312">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="1afd3-312">Location1MeetingPolicy</span></span>  | <span data-ttu-id="1afd3-313">已禁用</span><span class="sxs-lookup"><span data-stu-id="1afd3-313">Disabled</span></span> |

<span data-ttu-id="1afd3-314">由 Daniela 托管的会议允许会议参与者共享其整个屏幕或特定应用程序。</span><span class="sxs-lookup"><span data-stu-id="1afd3-314">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="1afd3-315">如果 Amanda 加入 Daniela 的会议，Amanda 无法共享她的屏幕或特定应用程序，因为她的策略设置已被禁用。</span><span class="sxs-lookup"><span data-stu-id="1afd3-315">If Amanda joins Daniela's meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="1afd3-316">在 Amanda 托管的会议中，不允许任何人共享其屏幕或单个应用程序，而不管分配给他们的屏幕共享模式策略如何。</span><span class="sxs-lookup"><span data-stu-id="1afd3-316">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span> <span data-ttu-id="1afd3-317">这意味着 Daniela 不能在 Amanda 的会议中共享她的屏幕或单个应用程序。</span><span class="sxs-lookup"><span data-stu-id="1afd3-317">This means that Daniela can't share her screen or a single application in Amanda's meetings.</span></span>  

<span data-ttu-id="1afd3-318">当前，如果用户使用的是 Google Chrome，则用户无法在团队会议中播放视频或共享其屏幕。</span><span class="sxs-lookup"><span data-stu-id="1afd3-318">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

### <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="1afd3-319">允许参与者授予或请求控制</span><span class="sxs-lookup"><span data-stu-id="1afd3-319">Allow a participant to give or request control</span></span>

<span data-ttu-id="1afd3-320">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-320">This is a per-user policy.</span></span> <span data-ttu-id="1afd3-321">此设置控制用户是否可以将共享桌面或窗口的控制权授予其他会议参与者。</span><span class="sxs-lookup"><span data-stu-id="1afd3-321">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="1afd3-322">若要赋予控制权，请将鼠标悬停在屏幕顶部。</span><span class="sxs-lookup"><span data-stu-id="1afd3-322">To give control, hover over the top of the screen.</span></span>

<span data-ttu-id="1afd3-323">如果为用户启用此设置，则 " **授予控制权** " 选项显示在共享会话的顶部栏中。</span><span class="sxs-lookup"><span data-stu-id="1afd3-323">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span>

![显示 "提供控制" 选项的屏幕截图](media/meeting-policies-give-control.png)

<span data-ttu-id="1afd3-325">如果用户的设置处于关闭状态，则 " **提供控制** " 选项不可用。</span><span class="sxs-lookup"><span data-stu-id="1afd3-325">If the settings is turned off for the user, the **Give Control** option isn't available.</span></span>

![显示 "提供控件" 选项不可用的屏幕截图](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="1afd3-327">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="1afd3-327">Let's look at the following example.</span></span>

|<span data-ttu-id="1afd3-328">用户</span><span class="sxs-lookup"><span data-stu-id="1afd3-328">User</span></span> |<span data-ttu-id="1afd3-329">会议策略</span><span class="sxs-lookup"><span data-stu-id="1afd3-329">Meeting policy</span></span>  |<span data-ttu-id="1afd3-330">允许参与者授予或请求控制</span><span class="sxs-lookup"><span data-stu-id="1afd3-330">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="1afd3-331">Daniela</span><span class="sxs-lookup"><span data-stu-id="1afd3-331">Daniela</span></span>   | <span data-ttu-id="1afd3-332">全局</span><span class="sxs-lookup"><span data-stu-id="1afd3-332">Global</span></span>   | <span data-ttu-id="1afd3-333">True</span><span class="sxs-lookup"><span data-stu-id="1afd3-333">True</span></span>       |
|<span data-ttu-id="1afd3-334">Babek</span><span class="sxs-lookup"><span data-stu-id="1afd3-334">Babek</span></span>    | <span data-ttu-id="1afd3-335">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="1afd3-335">Location1MeetingPolicy</span></span>        | <span data-ttu-id="1afd3-336">False</span><span class="sxs-lookup"><span data-stu-id="1afd3-336">False</span></span>   |

<span data-ttu-id="1afd3-337">Daniela 可以将共享桌面或窗口的控制权交给 Babek 组织的会议中的其他参与者，Babek 无法将控制权授予其他参与者。</span><span class="sxs-lookup"><span data-stu-id="1afd3-337">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek whereas Babek can't give control to other participants.</span></span>

<span data-ttu-id="1afd3-338">若要使用 PowerShell 控制哪些人可以授予控制请求或接受控制请求，请使用 AllowParticipantGiveRequestControl cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1afd3-338">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="1afd3-339">若要在共享期间提供和控制共享内容，双方都必须使用团队桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="1afd3-339">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="1afd3-340">如果任何一方在浏览器中运行 Teams，则不支持控制。</span><span class="sxs-lookup"><span data-stu-id="1afd3-340">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="1afd3-341">这是由我们计划修复的一个技术限制造成。</span><span class="sxs-lookup"><span data-stu-id="1afd3-341">This is due to a technical limitation that we're planning to fix.</span></span>

### <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="1afd3-342">允许外部参与者授予或请求控制</span><span class="sxs-lookup"><span data-stu-id="1afd3-342">Allow an external participant to give or request control</span></span>

<span data-ttu-id="1afd3-343">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-343">This is a per-user policy.</span></span> <span data-ttu-id="1afd3-344">组织是否为用户设置此集不会控制外部参与者可以执行的操作，无论会议组织者已设置了哪些内容。</span><span class="sxs-lookup"><span data-stu-id="1afd3-344">Whether an organization has this set for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="1afd3-345">此参数控制是否可以向外部参与者提供控制或请求控制共享者的屏幕，具体取决于共享者在其组织的会议策略中设置的内容。</span><span class="sxs-lookup"><span data-stu-id="1afd3-345">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span> <span data-ttu-id="1afd3-346">团队会议中的外部参与者可以按如下方式进行分类：</span><span class="sxs-lookup"><span data-stu-id="1afd3-346">External participants in Teams meetings can be categorized as follows:</span></span>  

- <span data-ttu-id="1afd3-347">匿名用户</span><span class="sxs-lookup"><span data-stu-id="1afd3-347">Anonymous user</span></span>
- <span data-ttu-id="1afd3-348">来宾用户</span><span class="sxs-lookup"><span data-stu-id="1afd3-348">Guest users</span></span>  
- <span data-ttu-id="1afd3-349">B2B 用户</span><span class="sxs-lookup"><span data-stu-id="1afd3-349">B2B user</span></span>
- <span data-ttu-id="1afd3-350">联合用户</span><span class="sxs-lookup"><span data-stu-id="1afd3-350">Federated user</span></span>  

<span data-ttu-id="1afd3-351">联盟用户是否可以向外部用户授予控制权，同时共享受允许外部参与者在其组织中 **授予或请求控制** 设置的控制。</span><span class="sxs-lookup"><span data-stu-id="1afd3-351">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="1afd3-352">若要使用 PowerShell 控制外部参与者是否可以授予控制或接受控制请求，请使用 AllowExternalParticipantGiveRequestControl cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1afd3-352">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="1afd3-353">允许 PowerPoint 共享</span><span class="sxs-lookup"><span data-stu-id="1afd3-353">Allow PowerPoint sharing</span></span>

<span data-ttu-id="1afd3-354">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-354">This is a per-user policy.</span></span> <span data-ttu-id="1afd3-355">此设置控制用户是否可以在会议中共享 PowerPoint 幻灯片放映。</span><span class="sxs-lookup"><span data-stu-id="1afd3-355">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="1afd3-356">外部用户（包括匿名用户、来宾和联盟用户）继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-356">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="1afd3-357">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="1afd3-357">Let's look at the following example.</span></span>

|<span data-ttu-id="1afd3-358">用户</span><span class="sxs-lookup"><span data-stu-id="1afd3-358">User</span></span> |<span data-ttu-id="1afd3-359">会议策略</span><span class="sxs-lookup"><span data-stu-id="1afd3-359">Meeting policy</span></span>  |<span data-ttu-id="1afd3-360">允许 PowerPoint 共享</span><span class="sxs-lookup"><span data-stu-id="1afd3-360">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="1afd3-361">Daniela</span><span class="sxs-lookup"><span data-stu-id="1afd3-361">Daniela</span></span>   | <span data-ttu-id="1afd3-362">全局</span><span class="sxs-lookup"><span data-stu-id="1afd3-362">Global</span></span>   | <span data-ttu-id="1afd3-363">True</span><span class="sxs-lookup"><span data-stu-id="1afd3-363">True</span></span>       |
|<span data-ttu-id="1afd3-364">Amanda</span><span class="sxs-lookup"><span data-stu-id="1afd3-364">Amanda</span></span>   | <span data-ttu-id="1afd3-365">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="1afd3-365">Location1MeetingPolicy</span></span>        | <span data-ttu-id="1afd3-366">False</span><span class="sxs-lookup"><span data-stu-id="1afd3-366">False</span></span>   |

<span data-ttu-id="1afd3-367">Amanda 不能在会议中共享 PowerPoint 幻灯片卡座，即使她是会议组织者也是如此。</span><span class="sxs-lookup"><span data-stu-id="1afd3-367">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="1afd3-368">Daniela 可以共享 PowerPoint 幻灯片放映，即使会议由 Amanda 组织。</span><span class="sxs-lookup"><span data-stu-id="1afd3-368">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="1afd3-369">Amanda 可以查看会议中其他人共享的 PowerPoint 幻灯片卡座，即使她无法共享 PowerPoint 幻灯片放映。</span><span class="sxs-lookup"><span data-stu-id="1afd3-369">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

### <a name="allow-whiteboard"></a><span data-ttu-id="1afd3-370">允许白板</span><span class="sxs-lookup"><span data-stu-id="1afd3-370">Allow whiteboard</span></span>

<span data-ttu-id="1afd3-371">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-371">This is a per-user policy.</span></span> <span data-ttu-id="1afd3-372">此设置控制用户是否可以在会议中共享白板。</span><span class="sxs-lookup"><span data-stu-id="1afd3-372">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="1afd3-373">外部用户（包括匿名用户、B2B 和联盟用户）继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-373">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="1afd3-374">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="1afd3-374">Let's look at the following example.</span></span>

|<span data-ttu-id="1afd3-375">用户</span><span class="sxs-lookup"><span data-stu-id="1afd3-375">User</span></span> |<span data-ttu-id="1afd3-376">会议策略</span><span class="sxs-lookup"><span data-stu-id="1afd3-376">Meeting policy</span></span>  |<span data-ttu-id="1afd3-377">允许白板</span><span class="sxs-lookup"><span data-stu-id="1afd3-377">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="1afd3-378">Daniela</span><span class="sxs-lookup"><span data-stu-id="1afd3-378">Daniela</span></span>   | <span data-ttu-id="1afd3-379">全局</span><span class="sxs-lookup"><span data-stu-id="1afd3-379">Global</span></span>   | <span data-ttu-id="1afd3-380">True</span><span class="sxs-lookup"><span data-stu-id="1afd3-380">True</span></span>       |
|<span data-ttu-id="1afd3-381">Amanda</span><span class="sxs-lookup"><span data-stu-id="1afd3-381">Amanda</span></span>   | <span data-ttu-id="1afd3-382">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="1afd3-382">Location1MeetingPolicy</span></span>        | <span data-ttu-id="1afd3-383">False</span><span class="sxs-lookup"><span data-stu-id="1afd3-383">False</span></span>   |

<span data-ttu-id="1afd3-384">Amanda 无法在会议中共享白板，即使她是会议组织者也是如此。</span><span class="sxs-lookup"><span data-stu-id="1afd3-384">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="1afd3-385">即使会议是按 Amanda 组织的，Daniela 也可以共享白板。</span><span class="sxs-lookup"><span data-stu-id="1afd3-385">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

### <a name="allow-shared-notes"></a><span data-ttu-id="1afd3-386">允许共享笔记</span><span class="sxs-lookup"><span data-stu-id="1afd3-386">Allow shared notes</span></span>

<span data-ttu-id="1afd3-387">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-387">This is a per-user policy.</span></span> <span data-ttu-id="1afd3-388">此设置控制用户是否可以在会议中创建和共享笔记。</span><span class="sxs-lookup"><span data-stu-id="1afd3-388">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="1afd3-389">外部用户（包括匿名用户、B2B 和联盟用户）继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-389">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="1afd3-390">" **会议笔记** " 选项卡目前仅在具有少于20个参与者的会议中受支持。</span><span class="sxs-lookup"><span data-stu-id="1afd3-390">The **Meeting Notes** tab is currently only supported in meetings that have fewer than 20 participants.</span></span>

<span data-ttu-id="1afd3-391">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="1afd3-391">Let's look at the following example.</span></span>

|<span data-ttu-id="1afd3-392">用户</span><span class="sxs-lookup"><span data-stu-id="1afd3-392">User</span></span> |<span data-ttu-id="1afd3-393">会议策略</span><span class="sxs-lookup"><span data-stu-id="1afd3-393">Meeting policy</span></span>  |<span data-ttu-id="1afd3-394">允许共享笔记</span><span class="sxs-lookup"><span data-stu-id="1afd3-394">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="1afd3-395">Daniela</span><span class="sxs-lookup"><span data-stu-id="1afd3-395">Daniela</span></span>   | <span data-ttu-id="1afd3-396">全局</span><span class="sxs-lookup"><span data-stu-id="1afd3-396">Global</span></span>   | <span data-ttu-id="1afd3-397">True</span><span class="sxs-lookup"><span data-stu-id="1afd3-397">True</span></span>       |
|<span data-ttu-id="1afd3-398">Amanda</span><span class="sxs-lookup"><span data-stu-id="1afd3-398">Amanda</span></span>   | <span data-ttu-id="1afd3-399">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="1afd3-399">Location1MeetingPolicy</span></span> | <span data-ttu-id="1afd3-400">False</span><span class="sxs-lookup"><span data-stu-id="1afd3-400">False</span></span> |

<span data-ttu-id="1afd3-401">Daniela 可以在 Amanda 的会议中做笔记，Amanda 不能在任何会议中做笔记。</span><span class="sxs-lookup"><span data-stu-id="1afd3-401">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>

## <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="1afd3-402">会议策略设置-参与者 & 来宾</span><span class="sxs-lookup"><span data-stu-id="1afd3-402">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="1afd3-403">这些设置控制在会议厅中等待的会议参与者，以及他们在会议中允许的参与级别。</span><span class="sxs-lookup"><span data-stu-id="1afd3-403">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="1afd3-404">让匿名人员开始会议</span><span class="sxs-lookup"><span data-stu-id="1afd3-404">Let anonymous people start a meeting</span></span>](#let-anonymous-people-start-a-meeting)
- [<span data-ttu-id="1afd3-405">自动允许人员</span><span class="sxs-lookup"><span data-stu-id="1afd3-405">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="1afd3-406">允许拨入用户绕过大厅</span><span class="sxs-lookup"><span data-stu-id="1afd3-406">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby)
- [<span data-ttu-id="1afd3-407">启用实时字幕</span><span class="sxs-lookup"><span data-stu-id="1afd3-407">Enable live captions</span></span>](#enable-live-captions)
- [<span data-ttu-id="1afd3-408">允许在会议中聊天</span><span class="sxs-lookup"><span data-stu-id="1afd3-408">Allow chat in meetings</span></span>](#allow-chat-in-meetings)

> [!NOTE]
><span data-ttu-id="1afd3-409">用于加入会议的选项会有所不同，具体取决于每个团队组的设置和连接方法。</span><span class="sxs-lookup"><span data-stu-id="1afd3-409">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="1afd3-410">如果你的组具有音频会议，并使用它进行连接，请参阅 [音频会议](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="1afd3-410">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="1afd3-411">如果你的团队组没有音频会议，请参阅 [在团队中加入会议](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)。</span><span class="sxs-lookup"><span data-stu-id="1afd3-411">If your Teams group does not have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

### <a name="let-anonymous-people-start-a-meeting"></a><span data-ttu-id="1afd3-412">让匿名人员开始会议</span><span class="sxs-lookup"><span data-stu-id="1afd3-412">Let anonymous people start a meeting</span></span>

<span data-ttu-id="1afd3-413">这是每个组织者策略，允许 leaderless 电话拨入式会议会议。</span><span class="sxs-lookup"><span data-stu-id="1afd3-413">This is a per-organizer policy that allows for leaderless dial-in conferencing meetings.</span></span> <span data-ttu-id="1afd3-414">此设置控制在没有经过身份验证的组织中，拨入用户是否可以加入会议。</span><span class="sxs-lookup"><span data-stu-id="1afd3-414">This setting controls whether dial-in users can join the meeting without an authenticated user from the organization in attendance.</span></span> <span data-ttu-id="1afd3-415">默认值为 False，表示拨入用户将在大厅中等待，直到组织中的经过身份验证的用户加入会议。</span><span class="sxs-lookup"><span data-stu-id="1afd3-415">The default value is False which means dial-in users will wait in the lobby until an authenticated user from the organization joins the meeting.</span></span>

> [!NOTE]
> <span data-ttu-id="1afd3-416">如果为 False，并且拨入用户首先加入会议，并且放置在会议厅中，则组织用户必须加入与团队客户的会议，以允许用户使用会议厅。</span><span class="sxs-lookup"><span data-stu-id="1afd3-416">If False and a dial-in user joins the meeting first and is placed in the lobby, an organization user must join the meeting with a Teams client to admit the user from the lobby.</span></span> <span data-ttu-id="1afd3-417">没有可用于在用户中拨打的会议厅控件。</span><span class="sxs-lookup"><span data-stu-id="1afd3-417">There are no lobby controls available for dialed in users.</span></span>

### <a name="automatically-admit-people"></a><span data-ttu-id="1afd3-418">自动允许人员</span><span class="sxs-lookup"><span data-stu-id="1afd3-418">Automatically admit people</span></span>

<span data-ttu-id="1afd3-419">这是每个组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-419">This is a per-organizer policy.</span></span> <span data-ttu-id="1afd3-420">此设置控制用户是否直接加入会议或在大厅中等待，直到他们被经过身份验证的用户许可。</span><span class="sxs-lookup"><span data-stu-id="1afd3-420">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span> <span data-ttu-id="1afd3-421">此设置不会应用于拨入用户。</span><span class="sxs-lookup"><span data-stu-id="1afd3-421">This setting does not apply to dial-in users.</span></span>

![显示会议厅中有用户的会议的屏幕截图](media/meeting-policies-lobby.png)

 <span data-ttu-id="1afd3-423">会议组织者可以单击会议邀请中的 " **会议选项** "，为其计划的每个会议更改此设置。</span><span class="sxs-lookup"><span data-stu-id="1afd3-423">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span>

> [!NOTE]
> <span data-ttu-id="1afd3-424">在会议选项中，该设置标记为 "哪些人可以绕过会议厅"。</span><span class="sxs-lookup"><span data-stu-id="1afd3-424">In the meeting options the setting is labeled "Who can bypass the lobby".</span></span> <span data-ttu-id="1afd3-425">如果更改任何用户的默认设置，则该设置将应用于该用户和任何之前的会议（用户未修改会议选项）组织的所有新会议。</span><span class="sxs-lookup"><span data-stu-id="1afd3-425">If you change the default setting for any user, it will apply to all new meetings organized by that user and any prior meetings where the user didn't modify Meeting options.</span></span>
  
|<span data-ttu-id="1afd3-426">设置值</span><span class="sxs-lookup"><span data-stu-id="1afd3-426">Setting value</span></span>  |<span data-ttu-id="1afd3-427">联接行为</span><span class="sxs-lookup"><span data-stu-id="1afd3-427">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="1afd3-428">**所有人**</span><span class="sxs-lookup"><span data-stu-id="1afd3-428">**Everyone**</span></span>   |<span data-ttu-id="1afd3-429">所有会议参与者都直接加入会议，而无需在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="1afd3-429">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="1afd3-430">这包括经过身份验证的用户、来自受信任组织的外部用户 (联盟) 、来宾和匿名用户。</span><span class="sxs-lookup"><span data-stu-id="1afd3-430">This includes authenticated users, external users from trusted organizations (federated), guests, and anonymous users.</span></span>     |
|<span data-ttu-id="1afd3-431">**组织和联盟组织中的每个人**</span><span class="sxs-lookup"><span data-stu-id="1afd3-431">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="1afd3-432">组织内的经过身份验证的用户，包括来宾用户和来自受信任组织的用户，直接加入会议，而无需在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="1afd3-432">Authenticated users within the organization, including guest users and the users from trusted organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="1afd3-433">匿名用户在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="1afd3-433">Anonymous users wait in the lobby.</span></span>   |
|<span data-ttu-id="1afd3-434">**您的组织中的每个人**</span><span class="sxs-lookup"><span data-stu-id="1afd3-434">**Everyone in your organization**</span></span>    |<span data-ttu-id="1afd3-435">来自组织内部的经过身份验证的用户（包括来宾用户）直接加入会议，而无需在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="1afd3-435">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="1afd3-436">来自受信任组织和匿名用户在大厅中等待的用户。</span><span class="sxs-lookup"><span data-stu-id="1afd3-436">Users from trusted organizations and anonymous users wait in the lobby.</span></span> <span data-ttu-id="1afd3-437">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="1afd3-437">This is the default setting.</span></span>           |
|<span data-ttu-id="1afd3-438">**仅组织者**</span><span class="sxs-lookup"><span data-stu-id="1afd3-438">**Organizer only**</span></span>    |<span data-ttu-id="1afd3-439">只有会议组织者可以直接加入会议，而无需在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="1afd3-439">Only meeting organizers can join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="1afd3-440">其他所有人（包括组织内的经过身份验证的用户、来宾用户、受信任组织的用户和匿名用户）都必须在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="1afd3-440">Everyone else, including authenticated users within the organization, guest users, users from trusted organizations and anonymous users must wait in the lobby.</span></span>           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a><span data-ttu-id="1afd3-441">允许拨入用户绕过大厅</span><span class="sxs-lookup"><span data-stu-id="1afd3-441">Allow dial-in users to bypass the lobby</span></span>

<span data-ttu-id="1afd3-442">这是每个组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-442">This is a per-organizer policy.</span></span> <span data-ttu-id="1afd3-443">此设置控制通过电话拨入的用户是否直接加入会议或在会议厅中等待，而不管 "是否 **自动允许人员** " 设置。</span><span class="sxs-lookup"><span data-stu-id="1afd3-443">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span> <span data-ttu-id="1afd3-444">默认值为 False。</span><span class="sxs-lookup"><span data-stu-id="1afd3-444">The default value is False.</span></span> <span data-ttu-id="1afd3-445">当为 False 时，拨入用户将在大厅中等待，直到组织用户通过团队客户加入会议并准许他们。</span><span class="sxs-lookup"><span data-stu-id="1afd3-445">When False, dial-in users will wait in the lobby until a organization user joins the meeting with a Teams client and admits them.</span></span> <span data-ttu-id="1afd3-446">当为 True 时，当组织用户加入会议时，拨入用户将自动加入会议。</span><span class="sxs-lookup"><span data-stu-id="1afd3-446">When True, dial-in users will automatically join the meeting when an organization user joins the meeting.</span></span>

> [!NOTE]
> <span data-ttu-id="1afd3-447">如果拨入用户在组织用户加入会议之前加入会议，则会将其放在大厅中，直到组织用户使用团队客户端加入会议并将其准许。</span><span class="sxs-lookup"><span data-stu-id="1afd3-447">If a dial-in user joins a meeting before an organization user joins the meeting, they will be placed in the lobby until an organization user joins the meeting using a Teams client and admits them.</span></span> <span data-ttu-id="1afd3-448">如果更改任何用户的默认设置，则该设置将应用于该用户和任何之前的会议（用户未修改会议选项）组织的所有新会议。</span><span class="sxs-lookup"><span data-stu-id="1afd3-448">If you change the default setting for any user, it will apply to all new meetings organized by that user and any prior meetings where the user didn't modify Meeting options.</span></span>

### <a name="enable-live-captions"></a><span data-ttu-id="1afd3-449">启用实时字幕</span><span class="sxs-lookup"><span data-stu-id="1afd3-449">Enable live captions</span></span>

<span data-ttu-id="1afd3-450">这是每用户策略，在会议期间应用。</span><span class="sxs-lookup"><span data-stu-id="1afd3-450">This is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="1afd3-451">此设置控制用户是否可以使用 " **打开实时标题** " 选项来打开和关闭用户出席的会议中的实时字幕。</span><span class="sxs-lookup"><span data-stu-id="1afd3-451">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![显示 "打开实时字幕" 选项的屏幕截图](media/meeting-policies-live-captions.png)

|<span data-ttu-id="1afd3-453">设置值</span><span class="sxs-lookup"><span data-stu-id="1afd3-453">Setting value</span></span> |<span data-ttu-id="1afd3-454">行为</span><span class="sxs-lookup"><span data-stu-id="1afd3-454">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="1afd3-455">**已禁用，但用户可以替代**</span><span class="sxs-lookup"><span data-stu-id="1afd3-455">**Disabled but the user can override**</span></span>     | <span data-ttu-id="1afd3-456">会议期间不会为用户自动打开实时字幕。</span><span class="sxs-lookup"><span data-stu-id="1afd3-456">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="1afd3-457">用户可以在 "溢出 () **...** " 菜单中看到 "**打开实时标题**" 选项，将其打开。</span><span class="sxs-lookup"><span data-stu-id="1afd3-457">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="1afd3-458">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="1afd3-458">This is the default setting.</span></span> |
|<span data-ttu-id="1afd3-459">**已禁用**</span><span class="sxs-lookup"><span data-stu-id="1afd3-459">**Disabled**</span></span>     | <span data-ttu-id="1afd3-460">会议期间，用户已禁用实时字幕。</span><span class="sxs-lookup"><span data-stu-id="1afd3-460">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="1afd3-461">用户不能选择将其打开。</span><span class="sxs-lookup"><span data-stu-id="1afd3-461">The user doesn't have the option to turn them on.</span></span>          |

<span data-ttu-id="1afd3-462"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="1afd3-462"><a name="bkcontentsharing"> </a></span></span>

### <a name="allow-chat-in-meetings"></a><span data-ttu-id="1afd3-463">允许在会议中聊天</span><span class="sxs-lookup"><span data-stu-id="1afd3-463">Allow chat in meetings</span></span>

<span data-ttu-id="1afd3-464">这是一个每个参与者的设置。</span><span class="sxs-lookup"><span data-stu-id="1afd3-464">This is a per-participant setting.</span></span> <span data-ttu-id="1afd3-465">此设置控制是否允许在用户的会议中使用会议聊天。</span><span class="sxs-lookup"><span data-stu-id="1afd3-465">This setting controls whether meeting chat is allowed in the user's meeting.</span></span>

<span data-ttu-id="1afd3-466"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="1afd3-466"><a name="bkparticipantsandguests"> </a></span></span>

## <a name="meeting-policy-settings---designated-presenter-role-mode"></a><span data-ttu-id="1afd3-467">会议策略设置-指定的演示者角色模式</span><span class="sxs-lookup"><span data-stu-id="1afd3-467">Meeting policy settings - Designated presenter role mode</span></span>

<span data-ttu-id="1afd3-468">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-468">This is a per-user policy.</span></span> <span data-ttu-id="1afd3-469">此设置允许你更改团队客户端的 "**会议选项**" 中的 "**可以显示的人员**" 的默认值。</span><span class="sxs-lookup"><span data-stu-id="1afd3-469">This setting lets you change the default value of the **Who can present?** setting in **Meeting options** in the Teams client.</span></span> <span data-ttu-id="1afd3-470">此策略设置影响所有会议，包括 "立即开会" 会议。</span><span class="sxs-lookup"><span data-stu-id="1afd3-470">This policy setting affects all meetings, including Meet Now meetings.</span></span>

<span data-ttu-id="1afd3-471">" **可以显示的人员** " 设置让会议组织者可以选择哪些人可以在会议中成为演示者。</span><span class="sxs-lookup"><span data-stu-id="1afd3-471">The **Who can present?** setting lets meeting organizers choose who can be presenters in a meeting.</span></span> <span data-ttu-id="1afd3-472">若要了解详细信息，请参阅更改[团队会议中](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)团队会议和角色的[参与者设置](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e)。</span><span class="sxs-lookup"><span data-stu-id="1afd3-472">To learn more, see [Change participant settings for a Teams meeting](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) and [Roles in a Teams meeting](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).</span></span>

<span data-ttu-id="1afd3-473">目前，您只能使用 PowerShell 配置此策略设置。</span><span class="sxs-lookup"><span data-stu-id="1afd3-473">Currently, you can only use PowerShell to configure this policy setting.</span></span> <span data-ttu-id="1afd3-474">你可以使用 [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有团队会议策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-474">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="1afd3-475">或者，使用 CsTeamsMeetingPolicy cmdlet 创建新 [的](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) 团队会议策略，并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="1afd3-475">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="1afd3-476">若要指定 **可显示的人员** 的默认值？在团队中设置，请将 **DesignatedPresenterRoleMode** 参数设置为下列之一：</span><span class="sxs-lookup"><span data-stu-id="1afd3-476">To specify the default value of the **Who can present?** setting in Teams, set the **DesignatedPresenterRoleMode** parameter to one of the following:</span></span>

- <span data-ttu-id="1afd3-477">**EveryoneUserOverride**：所有会议参与者都可以是演示者。</span><span class="sxs-lookup"><span data-stu-id="1afd3-477">**EveryoneUserOverride**:  All meeting participants can be presenters.</span></span> <span data-ttu-id="1afd3-478">此值为默认值。</span><span class="sxs-lookup"><span data-stu-id="1afd3-478">This is the default value.</span></span> <span data-ttu-id="1afd3-479">此参数对应于团队中的 " **所有人** " 设置。</span><span class="sxs-lookup"><span data-stu-id="1afd3-479">This parameter corresponds to the **Everyone** setting in Teams.</span></span>
- <span data-ttu-id="1afd3-480">**EveryoneInCompanyUserOverride**：组织中的经过身份验证的用户（包括来宾用户）可以是演示者。</span><span class="sxs-lookup"><span data-stu-id="1afd3-480">**EveryoneInCompanyUserOverride**: Authenticated users in the organization, including guest users, can be presenters.</span></span> <span data-ttu-id="1afd3-481">此参数对应于团队中的 " **我的组织** " 设置中的人员。</span><span class="sxs-lookup"><span data-stu-id="1afd3-481">This parameter corresponds to the **People in my organization** setting in Teams.</span></span>
- <span data-ttu-id="1afd3-482">**OrganizerOnlyUserOverride**：只有会议组织者可以是演示者，并且所有会议参与者都指定为 "与会者"。</span><span class="sxs-lookup"><span data-stu-id="1afd3-482">**OrganizerOnlyUserOverride**: Only the meeting organizer can be a presenter and all meeting participants are designated as attendees.</span></span> <span data-ttu-id="1afd3-483">此参数对应于 "团队" 中的 " **仅我** " 设置。</span><span class="sxs-lookup"><span data-stu-id="1afd3-483">This parameter corresponds to the **Only me** setting in Teams.</span></span>

<span data-ttu-id="1afd3-484">请记住，在设置默认值后，会议组织者仍可以在团队中更改此设置，并选择哪些人可以在他们计划的会议中显示。</span><span class="sxs-lookup"><span data-stu-id="1afd3-484">Keep in mind that after you set the default value, meeting organizers can still change this setting in Teams and choose who can present in the meetings that they schedule.</span></span>

## <a name="meeting-policy-settings---meeting-attendance-report"></a><span data-ttu-id="1afd3-485">会议策略设置-会议出席情况报告</span><span class="sxs-lookup"><span data-stu-id="1afd3-485">Meeting policy settings - Meeting attendance report</span></span>

<span data-ttu-id="1afd3-486">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-486">This is a per-user policy.</span></span> <span data-ttu-id="1afd3-487">此设置控制会议组织者是否可以下载 [会议出席报告](teams-analytics-and-reports/meeting-attendance-report.md)。</span><span class="sxs-lookup"><span data-stu-id="1afd3-487">This setting controls whether meeting organizers can download the [meeting attendance report](teams-analytics-and-reports/meeting-attendance-report.md).</span></span>

<span data-ttu-id="1afd3-488">目前，您只能使用 PowerShell 配置此策略设置。</span><span class="sxs-lookup"><span data-stu-id="1afd3-488">Currently, you can only use PowerShell to configure this policy setting.</span></span> <span data-ttu-id="1afd3-489">你可以使用 [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有团队会议策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-489">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="1afd3-490">或者，使用 CsTeamsMeetingPolicy cmdlet 创建新 [的](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) 团队会议策略，并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="1afd3-490">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="1afd3-491">若要使会议组织者能够下载会议出席报告，请将 **AllowEngagementReport** 参数设置为 " **已启用**"。</span><span class="sxs-lookup"><span data-stu-id="1afd3-491">To enable a meeting organizer to download the meeting attendance report, set the **AllowEngagementReport** parameter  to **Enabled**.</span></span> <span data-ttu-id="1afd3-492">启用后，用于下载报告的选项将显示在 " **参与者** " 窗格中。</span><span class="sxs-lookup"><span data-stu-id="1afd3-492">When enabled, the option to download the report is displayed in the **Participants** pane.</span></span>

<span data-ttu-id="1afd3-493">若要阻止会议组织者下载报表，请将该参数设置为 " **已禁用**"。</span><span class="sxs-lookup"><span data-stu-id="1afd3-493">To prevent a meeting organizer from downloading the report, set the parameter to **Disabled**.</span></span> <span data-ttu-id="1afd3-494">默认情况下，此设置处于禁用状态，无法使用下载报表的选项。</span><span class="sxs-lookup"><span data-stu-id="1afd3-494">By default, this setting is disabled and the option to download the report isn't available.</span></span>

## <a name="meeting-policy-settings---meeting-provider-for-islands-mode"></a><span data-ttu-id="1afd3-495">会议策略设置-岛模式的会议提供商</span><span class="sxs-lookup"><span data-stu-id="1afd3-495">Meeting policy settings - Meeting provider for Islands mode</span></span>

<span data-ttu-id="1afd3-496">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-496">This is a per-user policy.</span></span> <span data-ttu-id="1afd3-497">此设置控制将哪些 Outlook 会议加载项用于 *以孤岛模式*使用的用户。</span><span class="sxs-lookup"><span data-stu-id="1afd3-497">This setting controls which Outlook meeting add-in is used for *users who are in Islands mode*.</span></span> <span data-ttu-id="1afd3-498">你可以指定用户是否只能使用团队会议加载项或团队会议和 Skype for business 会议加载项在 Outlook 中安排会议。</span><span class="sxs-lookup"><span data-stu-id="1afd3-498">You can specify whether users can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins to schedule meetings in Outlook.</span></span>

<span data-ttu-id="1afd3-499">你只能将此策略应用到处于孤岛模式的用户，并在其团队会议策略中将 **AllowOutlookAddIn** 参数设置为 **True** 。</span><span class="sxs-lookup"><span data-stu-id="1afd3-499">You can only apply this policy to users who are in Islands mode and have the **AllowOutlookAddIn** parameter set to **True** in their Teams meeting policy.</span></span>

<span data-ttu-id="1afd3-500">目前，您只能使用 PowerShell 设置此策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-500">Currently, you can only use PowerShell to set this policy.</span></span> <span data-ttu-id="1afd3-501">你可以使用 [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有团队会议策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-501">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="1afd3-502">或者，使用 CsTeamsMeetingPolicy cmdlet 创建新 [的](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) 团队会议策略，并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="1afd3-502">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="1afd3-503">若要指定希望用户可以使用哪个会议加载项，请按如下方式设置 **PreferredMeetingProviderForIslandsMode** 参数：</span><span class="sxs-lookup"><span data-stu-id="1afd3-503">To specify which meeting add-in you want to be available to users, set the **PreferredMeetingProviderForIslandsMode** parameter as follows:</span></span>

- <span data-ttu-id="1afd3-504">将参数设置为 **TeamsAndSfB** 可在 Outlook 中启用团队会议加载项和 Skype for business 加载项。</span><span class="sxs-lookup"><span data-stu-id="1afd3-504">Set the parameter to **TeamsAndSfB** to enable both the Teams Meeting add-in and Skype for Business add-in in Outlook.</span></span> <span data-ttu-id="1afd3-505">此值为默认值。</span><span class="sxs-lookup"><span data-stu-id="1afd3-505">This is the default value.</span></span>
- <span data-ttu-id="1afd3-506">将该参数设置为 " **团队** "，仅在 Outlook 中启用团队会议外接程序。</span><span class="sxs-lookup"><span data-stu-id="1afd3-506">Set the parameter to **Teams** to enable only the Teams Meeting add-in in Outlook.</span></span> <span data-ttu-id="1afd3-507">此策略设置可确保所有未来会议都有团队会议加入链接。</span><span class="sxs-lookup"><span data-stu-id="1afd3-507">This policy setting ensures that all future meetings have a Teams meeting join link.</span></span> <span data-ttu-id="1afd3-508">它不会将现有 Skype for Business 会议加入链接迁移到团队。</span><span class="sxs-lookup"><span data-stu-id="1afd3-508">It doesn't migrate existing Skype for Business meeting join links to Teams.</span></span> <span data-ttu-id="1afd3-509">此政策设置不会影响 Skype for Business 中的状态、聊天、PSTN 呼叫或任何其他功能，这意味着用户将继续使用 Skype for Business 进行这些功能。</span><span class="sxs-lookup"><span data-stu-id="1afd3-509">This policy setting doesn't affect presence, chat, PSTN calling, or any other capabilities in Skype for Business, which means that users will continue to use Skype for Business for these capabilities.</span></span>

  <span data-ttu-id="1afd3-510">如果你将参数设置为 " **团队**"，然后切换回 **TeamsAndSfB**，则将启用这两个会议加载项。</span><span class="sxs-lookup"><span data-stu-id="1afd3-510">If you set the parameter to **Teams**, and then switch back to **TeamsAndSfB**, both meeting add-ins are enabled.</span></span> <span data-ttu-id="1afd3-511">但是，请注意，现有团队会议联接链接不会迁移到 Skype for business。</span><span class="sxs-lookup"><span data-stu-id="1afd3-511">However, note that existing Teams meeting join links won't be migrated to Skype for Business.</span></span> <span data-ttu-id="1afd3-512">只有在更改后安排的 Skype for Business 会议才会有 Skype for business 会议加入链接。</span><span class="sxs-lookup"><span data-stu-id="1afd3-512">Only Skype for Business meetings scheduled after the change will have a Skype for Business meeting join link.</span></span>

## <a name="meeting-policy-settings---video-filters-mode"></a><span data-ttu-id="1afd3-513">会议策略设置-视频筛选器模式</span><span class="sxs-lookup"><span data-stu-id="1afd3-513">Meeting policy settings - Video filters mode</span></span>

<span data-ttu-id="1afd3-514">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-514">This is a per-user policy.</span></span> <span data-ttu-id="1afd3-515">此设置控制用户是否可以在会议中自定义其视频背景。</span><span class="sxs-lookup"><span data-stu-id="1afd3-515">This setting controls whether users can customize their video background in a meeting.</span></span>

<span data-ttu-id="1afd3-516">目前，您只能使用 PowerShell 设置此策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-516">Currently, you can only use PowerShell to set this policy.</span></span> <span data-ttu-id="1afd3-517">你可以使用 [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有团队会议策略。</span><span class="sxs-lookup"><span data-stu-id="1afd3-517">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="1afd3-518">或者，使用 CsTeamsMeetingPolicy cmdlet 创建新 [的](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) 团队会议策略，然后将策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="1afd3-518">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet, and then assign the policy to users.</span></span>

<span data-ttu-id="1afd3-519">若要指定用户是否可以在会议中自定义其视频背景，请设置 **VideoFiltersMode** 参数，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1afd3-519">To specify whether users can customize their video background in a meeting, set the **VideoFiltersMode** parameter as follows:</span></span>

|<span data-ttu-id="1afd3-520">在 PowerShell 中设置值</span><span class="sxs-lookup"><span data-stu-id="1afd3-520">Setting value in PowerShell</span></span> |<span data-ttu-id="1afd3-521">行为</span><span class="sxs-lookup"><span data-stu-id="1afd3-521">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="1afd3-522">**NoFilters**</span><span class="sxs-lookup"><span data-stu-id="1afd3-522">**NoFilters**</span></span>     |<span data-ttu-id="1afd3-523">用户无法自定义其视频背景。</span><span class="sxs-lookup"><span data-stu-id="1afd3-523">User can't customize their video background.</span></span>|
|<span data-ttu-id="1afd3-524">**BlurOnly**</span><span class="sxs-lookup"><span data-stu-id="1afd3-524">**BlurOnly**</span></span>     |<span data-ttu-id="1afd3-525">用户可以选择对视频背景进行模糊处理。</span><span class="sxs-lookup"><span data-stu-id="1afd3-525">User has the option to blur their video background.</span></span> |
|<span data-ttu-id="1afd3-526">**BlurandDefaultBackgrounds**</span><span class="sxs-lookup"><span data-stu-id="1afd3-526">**BlurandDefaultBackgrounds**</span></span>     |<span data-ttu-id="1afd3-527">用户可以选择对其视频背景进行模糊处理，或选择默认的图像集作为其背景。</span><span class="sxs-lookup"><span data-stu-id="1afd3-527">User has the option to blur their video background or choose from the default set of images to use as their background.</span></span> |
|<span data-ttu-id="1afd3-528">**AllFilters**</span><span class="sxs-lookup"><span data-stu-id="1afd3-528">**AllFilters**</span></span>     |<span data-ttu-id="1afd3-529">使用可选择对其视频背景进行模糊处理，从默认的图像集进行选择，或上载自定义图像用作其背景。</span><span class="sxs-lookup"><span data-stu-id="1afd3-529">Use has the option to blur their video background, choose from the default set of images, or upload custom images to use as their background.</span></span> |

> [!NOTE]
> <span data-ttu-id="1afd3-530">用户上载的图像不会由团队进行筛选。</span><span class="sxs-lookup"><span data-stu-id="1afd3-530">Images uploaded by users aren't screened by Teams.</span></span> <span data-ttu-id="1afd3-531">使用 **AllFilters** 设置时，你应具有内部组织策略，以防止用户上传攻击性或不合适的图像，或者你的组织无权使用团队会议背景的图像。</span><span class="sxs-lookup"><span data-stu-id="1afd3-531">When you use the **AllFilters** setting, you should have internal organization policies to prevent users from uploading offensive or inappropriate images, or images your organization don't have rights to use for Teams meeting backgrounds.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1afd3-532">相关主题</span><span class="sxs-lookup"><span data-stu-id="1afd3-532">Related topics</span></span>

- [<span data-ttu-id="1afd3-533">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="1afd3-533">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="1afd3-534">向团队中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="1afd3-534">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="1afd3-535">从用户中删除 RestrictedAnonymousAccess 团队会议策略</span><span class="sxs-lookup"><span data-stu-id="1afd3-535">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)
