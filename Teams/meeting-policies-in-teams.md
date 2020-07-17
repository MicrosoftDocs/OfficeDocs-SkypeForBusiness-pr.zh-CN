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
ms.openlocfilehash: 1b7c94cd8dc0f46b72cea21ae46d98ed9a974fc5
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938301"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="59b06-103">管理团队中的会议策略</span><span class="sxs-lookup"><span data-stu-id="59b06-103">Manage meeting policies in Teams</span></span>

::: zone target="docs"
<span data-ttu-id="59b06-104">会议策略Meeting policies用于控制组织中用户安排的会议的与会者可用的功能。</span><span class="sxs-lookup"><span data-stu-id="59b06-104">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="59b06-105">你可以使用自动创建的全局（组织范围的默认）策略，也可以创建和分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-105">You can use the global (Org-wide default) policy that's automatically created or create and assign custom policies.</span></span> <span data-ttu-id="59b06-106">可在 Microsoft 团队管理中心或通过使用[PowerShell](teams-powershell-overview.md)管理会议策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-106">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="59b06-107">有关使用角色管理会议演示者和与会者的权限的信息，请参阅[团队会议中的角色](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)。</span><span class="sxs-lookup"><span data-stu-id="59b06-107">For information about using roles to manage the permissions of meeting presenters and attendees, see [Roles in a Teams meeting](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).</span></span>

<span data-ttu-id="59b06-108">你可以通过以下方式实施策略，这会在会议开始之前、会议期间或会议后影响用户的会议体验。</span><span class="sxs-lookup"><span data-stu-id="59b06-108">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="59b06-109">实现类型</span><span class="sxs-lookup"><span data-stu-id="59b06-109">Implementation type</span></span>  |<span data-ttu-id="59b06-110">说明</span><span class="sxs-lookup"><span data-stu-id="59b06-110">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="59b06-111">每个组织者</span><span class="sxs-lookup"><span data-stu-id="59b06-111">Per-organizer</span></span>    |<span data-ttu-id="59b06-112">实施按组织者策略时，所有会议参与者都将继承组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-112">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="59b06-113">例如，**自动允许人员**为每个组织者策略，并控制用户是否直接加入会议，或在会议厅中等待分配了该策略的用户安排的会议。</span><span class="sxs-lookup"><span data-stu-id="59b06-113">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="59b06-114">每用户</span><span class="sxs-lookup"><span data-stu-id="59b06-114">Per-user</span></span>    |<span data-ttu-id="59b06-115">当你实现每用户策略时，仅应用每用户策略来限制组织者和/或会议参与者的某些功能。</span><span class="sxs-lookup"><span data-stu-id="59b06-115">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="59b06-116">例如，"**允许在频道中立即开会**" 是每用户策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-116">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="59b06-117">每个组织者和每用户</span><span class="sxs-lookup"><span data-stu-id="59b06-117">Per-organizer and per-user</span></span>     |<span data-ttu-id="59b06-118">当你实现每个组织单位和每用户策略的组合时，某些功能将根据其策略和组织者的策略来限制会议参与者。</span><span class="sxs-lookup"><span data-stu-id="59b06-118">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="59b06-119">例如，"**允许云录制**" 是基于每个组织者和每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-119">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="59b06-120">启用此设置可允许会议组织者和参与者开始和停止录制。</span><span class="sxs-lookup"><span data-stu-id="59b06-120">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span>

<span data-ttu-id="59b06-121">你可以编辑全局策略中的设置，或者创建并分配一个或多个自定义策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-121">You can edit the settings in the global policy or create and assign one or more custom policies.</span></span> <span data-ttu-id="59b06-122">除非你创建和分配自定义策略，否则用户将获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-122">Users will get the global policy unless you create and assign a custom policy.</span></span>

> [!NOTE]
> <span data-ttu-id="59b06-123">"会议详细信息" 按钮在用户启用音频会议许可证或用户允许音频会议的情况下可用时，会议详细信息将不可用。</span><span class="sxs-lookup"><span data-stu-id="59b06-123">Meeting details button will be available if a user has the audio conference licenses enabled or the user is allow for audio conferencing, if not, the meeting details will not be available.</span></span>

## <a name="create-a-custom-meeting-policy"></a><span data-ttu-id="59b06-124">创建自定义会议策略</span><span class="sxs-lookup"><span data-stu-id="59b06-124">Create a custom meeting policy</span></span>

1. <span data-ttu-id="59b06-125">在 Microsoft 团队管理中心的左侧导航中，转到 "**会议**  >  **会议策略**"。</span><span class="sxs-lookup"><span data-stu-id="59b06-125">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="59b06-126">单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="59b06-126">Click **Add**.</span></span>
3. <span data-ttu-id="59b06-127">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="59b06-127">Enter a name and description for the policy.</span></span> <span data-ttu-id="59b06-128">名称不能包含特殊字符或超过 64 个字符。</span><span class="sxs-lookup"><span data-stu-id="59b06-128">The name can't contain special characters or be longer than 64 characters.</span></span>
4. <span data-ttu-id="59b06-129">选择所需的设置。</span><span class="sxs-lookup"><span data-stu-id="59b06-129">Choose the settings that you want.</span></span>
5. <span data-ttu-id="59b06-130">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="59b06-130">Click **Save**.</span></span>

<span data-ttu-id="59b06-131">例如，假设你有一组用户并且你想要限制这组用户的会议所需的带宽量。</span><span class="sxs-lookup"><span data-stu-id="59b06-131">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="59b06-132">你要创建新的自定义策略并命名为“带宽限制”，然后禁用以下设置：</span><span class="sxs-lookup"><span data-stu-id="59b06-132">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="59b06-133">在“音频和视频”中：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="59b06-133">Under **Audio & video**:</span></span>

- <span data-ttu-id="59b06-134">禁用“允许云录制”。</span><span class="sxs-lookup"><span data-stu-id="59b06-134">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="59b06-135">禁用“允许 IP 视频”。</span><span class="sxs-lookup"><span data-stu-id="59b06-135">Turn off Allow IP video.</span></span>

<span data-ttu-id="59b06-136">在“内容共享”中：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="59b06-136">Under **Content sharing**:</span></span>

- <span data-ttu-id="59b06-137">禁用屏幕共享模式。</span><span class="sxs-lookup"><span data-stu-id="59b06-137">Disable screen sharing mode.</span></span>
- <span data-ttu-id="59b06-138">禁用“允许白板”。</span><span class="sxs-lookup"><span data-stu-id="59b06-138">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="59b06-139">禁用“允许共享笔记”。</span><span class="sxs-lookup"><span data-stu-id="59b06-139">Turn off Allow shared notes.</span></span>

<span data-ttu-id="59b06-140">然后将此策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="59b06-140">Then assign the policy to the users.</span></span>

## <a name="edit-a-meeting-policy"></a><span data-ttu-id="59b06-141">编辑会议策略</span><span class="sxs-lookup"><span data-stu-id="59b06-141">Edit a meeting policy</span></span>

<span data-ttu-id="59b06-142">你可以编辑全局策略你创建的任何自定义策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-142">You can edit the global policy an any custom policies that you create.</span></span> 

1. <span data-ttu-id="59b06-143">在 Microsoft 团队管理中心的左侧导航中，转到 "**会议**  >  **会议策略**"。</span><span class="sxs-lookup"><span data-stu-id="59b06-143">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="59b06-144">通过单击策略名称左侧，然后单击 "**编辑**"，选择策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-144">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="59b06-145">在此处进行所需的更改。</span><span class="sxs-lookup"><span data-stu-id="59b06-145">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="59b06-146">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="59b06-146">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="59b06-147">一次只能向一个用户分配一个会议策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-147">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="59b06-148">将会议策略分配给用户</span><span class="sxs-lookup"><span data-stu-id="59b06-148">Assign a meeting policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> <span data-ttu-id="59b06-149">如果向用户分配了该策略，则不能删除该策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-149">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="59b06-150">必须先为所有受影响的用户分配不同的策略，然后才能删除原始策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-150">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="59b06-151">会议策略设置</span><span class="sxs-lookup"><span data-stu-id="59b06-151">Meeting policy settings</span></span>

<span data-ttu-id="59b06-152">在 "**会议策略**" 页面上选择现有策略或选择 "**添加**" 以添加新策略时，可以为以下项配置设置。</span><span class="sxs-lookup"><span data-stu-id="59b06-152">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="59b06-153">常规</span><span class="sxs-lookup"><span data-stu-id="59b06-153">General</span></span>](#meeting-policy-settings---general)
- [<span data-ttu-id="59b06-154">音频 & 视频</span><span class="sxs-lookup"><span data-stu-id="59b06-154">Audio & video</span></span>](#meeting-policy-settings---audio--video)
- [<span data-ttu-id="59b06-155">内容共享</span><span class="sxs-lookup"><span data-stu-id="59b06-155">Content sharing</span></span>](#meeting-policy-settings---content-sharing)
- [<span data-ttu-id="59b06-156">参与者 & 来宾</span><span class="sxs-lookup"><span data-stu-id="59b06-156">Participants & guests</span></span>](#meeting-policy-settings---participants--guests)

::: zone-end 

<span data-ttu-id="59b06-157"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="59b06-157"><a name="bkgeneral"> </a></span></span>

## <a name="meeting-policy-settings---general"></a><span data-ttu-id="59b06-158">会议策略设置-常规</span><span class="sxs-lookup"><span data-stu-id="59b06-158">Meeting policy settings - General</span></span>

- [<span data-ttu-id="59b06-159">允许在频道中立即开会</span><span class="sxs-lookup"><span data-stu-id="59b06-159">Allow Meet now in channels</span></span>](#allow-meet-now-in-channels)
- [<span data-ttu-id="59b06-160">允许 Outlook 加载项</span><span class="sxs-lookup"><span data-stu-id="59b06-160">Allow the Outlook add-in</span></span>](#allow-the-outlook-add-in)
- [<span data-ttu-id="59b06-161">允许频道会议安排</span><span class="sxs-lookup"><span data-stu-id="59b06-161">Allow channel meeting scheduling</span></span>](#allow-channel-meeting-scheduling)
- [<span data-ttu-id="59b06-162">允许安排私人会议</span><span class="sxs-lookup"><span data-stu-id="59b06-162">Allow scheduling private meetings</span></span>](#allow-scheduling-private-meetings)
- [<span data-ttu-id="59b06-163">允许在私人会议中立即开会</span><span class="sxs-lookup"><span data-stu-id="59b06-163">Allow Meet now in private meetings</span></span>](#allow-meet-now-in-private-meetings)

### <a name="allow-meet-now-in-channels"></a><span data-ttu-id="59b06-164">允许在频道中立即开会</span><span class="sxs-lookup"><span data-stu-id="59b06-164">Allow Meet now in channels</span></span>

<span data-ttu-id="59b06-165">这是每用户策略，在会议开始之前应用。</span><span class="sxs-lookup"><span data-stu-id="59b06-165">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="59b06-166">此设置控制用户是否可以在团队频道中启动临时会议。</span><span class="sxs-lookup"><span data-stu-id="59b06-166">This setting controls whether a user can start an ad hoc meeting in a Teams channel.</span></span> <span data-ttu-id="59b06-167">如果启用此操作，当用户在团队频道中发布消息时，用户可以单击 "撰写" 框下的 "**立即开会**" 以在频道中启动临时会议。</span><span class="sxs-lookup"><span data-stu-id="59b06-167">If you turn this on, when a user posts a message in a Teams channel, the user can click **Meet now** under the compose box to start an ad hoc meeting in the channel.</span></span> <span data-ttu-id="59b06-168">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="59b06-168">The default value is True.</span></span>

![显示邮件下方的 "立即开会" 图标的屏幕截图](media/meeting-policies-meet-now.png)

### <a name="allow-the-outlook-add-in"></a><span data-ttu-id="59b06-170">允许 Outlook 加载项</span><span class="sxs-lookup"><span data-stu-id="59b06-170">Allow the Outlook add-in</span></span>

<span data-ttu-id="59b06-171">这是每用户策略，在会议开始之前应用。</span><span class="sxs-lookup"><span data-stu-id="59b06-171">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="59b06-172">此设置控制是否可以从 Outlook （Windows、Mac、web 和手机）内安排团队会议。</span><span class="sxs-lookup"><span data-stu-id="59b06-172">This setting controls whether Teams meetings can be scheduled from within Outlook (Windows, Mac, web, and mobile).</span></span>

![显示安排新会议的功能的屏幕截图](media/meeting-policies-outlook-add-in.png)

<span data-ttu-id="59b06-174">如果关闭此功能，用户在 Outlook 中创建新会议时，无法安排团队会议。</span><span class="sxs-lookup"><span data-stu-id="59b06-174">If you turn this off, users are unable to schedule Teams meetings when they create a new meeting in Outlook.</span></span> <span data-ttu-id="59b06-175">例如，在 Windows 上的 Outlook 中，"**新建团队会议**" 选项不会显示在功能区中。</span><span class="sxs-lookup"><span data-stu-id="59b06-175">For example, in Outlook on Windows, the **New Teams Meeting** option won't show up in the ribbon.</span></span>

### <a name="allow-channel-meeting-scheduling"></a><span data-ttu-id="59b06-176">允许频道会议安排</span><span class="sxs-lookup"><span data-stu-id="59b06-176">Allow channel meeting scheduling</span></span>

<span data-ttu-id="59b06-177">这是每用户策略，在会议开始之前应用。</span><span class="sxs-lookup"><span data-stu-id="59b06-177">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="59b06-178">此设置控制用户是否可以在团队频道中安排会议。</span><span class="sxs-lookup"><span data-stu-id="59b06-178">This setting controls whether users can schedule a meeting in a Teams channel.</span></span>  <span data-ttu-id="59b06-179">如果关闭此功能，则当用户在团队频道中启动会议，并且为团队中的用户禁用 "**添加频道**" 选项时，"**安排会议**" 选项将不可用。</span><span class="sxs-lookup"><span data-stu-id="59b06-179">If you turn this off, the **Schedule a meeting** option won't be available to the user when they start a meeting in a Teams channel and the **Add channel** option is disabled for users in Teams.</span></span> <span data-ttu-id="59b06-180">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="59b06-180">The default value is True.</span></span>

![显示团队中的 "安排会议" 选项的屏幕截图](media/meeting-policies-schedule-a-meeting.png)

![显示 "选择要开会的频道" 选项的屏幕截图](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a><span data-ttu-id="59b06-183">允许安排私人会议</span><span class="sxs-lookup"><span data-stu-id="59b06-183">Allow scheduling private meetings</span></span>

<span data-ttu-id="59b06-184">这是每用户策略，在会议开始之前应用。</span><span class="sxs-lookup"><span data-stu-id="59b06-184">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="59b06-185">此设置控制用户是否可以在团队中安排私人会议。</span><span class="sxs-lookup"><span data-stu-id="59b06-185">This setting controls whether users can schedule private meetings in Teams.</span></span> <span data-ttu-id="59b06-186">当会议未发布到团队中的频道时，它是私有的。</span><span class="sxs-lookup"><span data-stu-id="59b06-186">A meeting is private when it's not published to a channel in a team.</span></span>

<span data-ttu-id="59b06-187">请注意，如果关闭 "**允许安排私人会议**" 和 "**允许频道会议计划**"，则会为团队中的用户禁用 "**添加必需与会者**" 和 "**添加频道**" 选项。</span><span class="sxs-lookup"><span data-stu-id="59b06-187">Note that if you turn off **Allow scheduling private meetings** and **Allow channel meeting scheduling**,  the **Add required attendees** and **Add channel** options are disabled for users in Teams.</span></span> <span data-ttu-id="59b06-188">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="59b06-188">The default value is True.</span></span>

### <a name="allow-meet-now-in-private-meetings"></a><span data-ttu-id="59b06-189">允许在私人会议中立即开会</span><span class="sxs-lookup"><span data-stu-id="59b06-189">Allow Meet now in private meetings</span></span>

<span data-ttu-id="59b06-190">这是每用户策略，在会议开始之前应用。</span><span class="sxs-lookup"><span data-stu-id="59b06-190">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="59b06-191">此设置控制用户是否可以启动 ad hoc 私人会议。</span><span class="sxs-lookup"><span data-stu-id="59b06-191">This setting controls whether a user can start an ad hoc private meeting.</span></span>  <span data-ttu-id="59b06-192">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="59b06-192">The default value is True.</span></span>

<span data-ttu-id="59b06-193"><a name="bkaudioandvideo"> </a></span><span class="sxs-lookup"><span data-stu-id="59b06-193"><a name="bkaudioandvideo"> </a></span></span>

## <a name="meeting-policy-settings---audio--video"></a><span data-ttu-id="59b06-194">会议策略设置-音频 & 视频</span><span class="sxs-lookup"><span data-stu-id="59b06-194">Meeting policy settings - Audio & video</span></span>

- [<span data-ttu-id="59b06-195">允许脚本</span><span class="sxs-lookup"><span data-stu-id="59b06-195">Allow transcription</span></span>](#allow-transcription)
- [<span data-ttu-id="59b06-196">允许云录制</span><span class="sxs-lookup"><span data-stu-id="59b06-196">Allow cloud recording</span></span>](#allow-cloud-recording)
- [<span data-ttu-id="59b06-197">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="59b06-197">Allow IP video</span></span>](#allow-ip-video)
- [<span data-ttu-id="59b06-198">媒体比特率（Kbs）</span><span class="sxs-lookup"><span data-stu-id="59b06-198">Media bit rate (Kbs)</span></span>](#media-bit-rate-kbs)

### <a name="allow-transcription"></a><span data-ttu-id="59b06-199">允许脚本</span><span class="sxs-lookup"><span data-stu-id="59b06-199">Allow transcription</span></span>

<span data-ttu-id="59b06-200">这是每个组织单位和每用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="59b06-200">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="59b06-201">此设置控制播放会议录制期间是否提供字幕和脚本功能。</span><span class="sxs-lookup"><span data-stu-id="59b06-201">This setting controls whether captions and transcription features are available during playback of meeting recordings.</span></span> <span data-ttu-id="59b06-202">如果关闭此功能，在播放会议录制的过程中，"**搜索**" 和 **"抄送**" 选项将不可用。</span><span class="sxs-lookup"><span data-stu-id="59b06-202">If you turn this off, the **Search** and **CC** options won't be available during playback of a meeting recording.</span></span> <span data-ttu-id="59b06-203">启动录制的人员需要启用此设置，以便录制还包括脚本。</span><span class="sxs-lookup"><span data-stu-id="59b06-203">The person who started the recording needs this setting turned on so that the recording also includes transcription.</span></span> 

<span data-ttu-id="59b06-204">请注意，当前只有在团队中将语言设置为英语且在会议中朗读英语的用户才支持使用录制的会议。</span><span class="sxs-lookup"><span data-stu-id="59b06-204">Note that transcription for recorded meetings is currently only supported for users who have the language in Teams set to English and when English is spoken in the meeting.</span></span>

![显示会议中的脚本选项的屏幕截图](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a><span data-ttu-id="59b06-206">允许云录制</span><span class="sxs-lookup"><span data-stu-id="59b06-206">Allow cloud recording</span></span>

<span data-ttu-id="59b06-207">这是每个组织单位和每用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="59b06-207">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="59b06-208">此设置控制是否可以录制此用户的会议。</span><span class="sxs-lookup"><span data-stu-id="59b06-208">This setting controls whether this user's meetings can be recorded.</span></span> <span data-ttu-id="59b06-209">录制可以由会议组织者或其他会议参与者启动（如果为参与者启用了该策略设置，并且他们是来自同一组织的经过身份验证的用户）。</span><span class="sxs-lookup"><span data-stu-id="59b06-209">The recording can be started by the meeting organizer or by another meeting participant if the policy setting is turned on for the participant and if they're an authenticated user from the same organization.</span></span>

<span data-ttu-id="59b06-210">组织外部的人员（如联盟用户和匿名用户）无法启动录制。</span><span class="sxs-lookup"><span data-stu-id="59b06-210">People outside your organization, such as federated and anonymous users, can't start the recording.</span></span> <span data-ttu-id="59b06-211">来宾用户无法启动或停止录制。</span><span class="sxs-lookup"><span data-stu-id="59b06-211">Guest users can't start or stop the recording.</span></span> 

![显示录制选项的屏幕截图](media/meeting-policies-recording.png)

<span data-ttu-id="59b06-213">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="59b06-213">Let's look at the following example.</span></span>

|<span data-ttu-id="59b06-214">用户</span><span class="sxs-lookup"><span data-stu-id="59b06-214">User</span></span> |<span data-ttu-id="59b06-215">会议策略</span><span class="sxs-lookup"><span data-stu-id="59b06-215">Meeting policy</span></span>  |<span data-ttu-id="59b06-216">允许云录制</span><span class="sxs-lookup"><span data-stu-id="59b06-216">Allow cloud recording</span></span> |
|---------|---------|---------|
|<span data-ttu-id="59b06-217">Daniela</span><span class="sxs-lookup"><span data-stu-id="59b06-217">Daniela</span></span> | <span data-ttu-id="59b06-218">全局</span><span class="sxs-lookup"><span data-stu-id="59b06-218">Global</span></span>   | <span data-ttu-id="59b06-219">False</span><span class="sxs-lookup"><span data-stu-id="59b06-219">False</span></span> |
|<span data-ttu-id="59b06-220">Amanda</span><span class="sxs-lookup"><span data-stu-id="59b06-220">Amanda</span></span> | <span data-ttu-id="59b06-221">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="59b06-221">Location1MeetingPolicy</span></span> | <span data-ttu-id="59b06-222">True</span><span class="sxs-lookup"><span data-stu-id="59b06-222">True</span></span>|
|<span data-ttu-id="59b06-223">John （外部用户）</span><span class="sxs-lookup"><span data-stu-id="59b06-223">John (external user)</span></span> | <span data-ttu-id="59b06-224">不适用</span><span class="sxs-lookup"><span data-stu-id="59b06-224">Not applicable</span></span> | <span data-ttu-id="59b06-225">不适用</span><span class="sxs-lookup"><span data-stu-id="59b06-225">Not applicable</span></span>|

<span data-ttu-id="59b06-226">按 Daniela 组织的会议无法录制，并且 Amanda 已启用策略设置，无法录制 Daniela 组织的会议。</span><span class="sxs-lookup"><span data-stu-id="59b06-226">Meetings organized by Daniela can't be recorded and Amanda, who has the policy setting enabled, can't record meetings organized by Daniela.</span></span> <span data-ttu-id="59b06-227">可记录由 Amanda 组织的会议，但 Daniela，他们已禁用策略设置，并且 John 是外部用户，无法录制 Amanda 组织的会议。</span><span class="sxs-lookup"><span data-stu-id="59b06-227">Meetings organized by Amanda can be recorded, however,  Daniela, who has the policy setting disabled and John who is an external user, can't record meetings organized by Amanda.</span></span>

<span data-ttu-id="59b06-228">若要了解有关云会议录制的详细信息，请参阅[团队云会议录制](cloud-recording.md)。</span><span class="sxs-lookup"><span data-stu-id="59b06-228">To learn more about cloud meeting recording, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

### <a name="allow-ip-video"></a><span data-ttu-id="59b06-229">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="59b06-229">Allow IP video</span></span>

<span data-ttu-id="59b06-230">这是每个组织单位和每用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="59b06-230">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="59b06-231">视频是会议的关键组件。</span><span class="sxs-lookup"><span data-stu-id="59b06-231">Video is a key component to meetings.</span></span> <span data-ttu-id="59b06-232">在某些组织中，管理员可能希望更好地控制哪些用户的会议有视频。</span><span class="sxs-lookup"><span data-stu-id="59b06-232">In some organizations, admins might want more control over which users' meetings have video.</span></span> <span data-ttu-id="59b06-233">此设置控制是否可以在用户托管的会议中以及用户开始的1:1 呼叫和组通话中打开视频。</span><span class="sxs-lookup"><span data-stu-id="59b06-233">This setting controls whether video can be turned on in meetings hosted by a user and in 1:1 calls and group calls started by a user.</span></span> <span data-ttu-id="59b06-234">已启用此策略的用户组织的会议，如果会议参与者也启用了该策略，则会议参与者允许会议中的视频共享。</span><span class="sxs-lookup"><span data-stu-id="59b06-234">Meetings organized by a user who has this policy enabled, allow video sharing in the meeting by the meeting participants, if the meeting participants also have the policy enabled.</span></span> <span data-ttu-id="59b06-235">未分配任何策略的会议参与者（如匿名和联盟参与者）将继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-235">Meeting participants who don't have any policies assigned (for example, anonymous and federated participants) inherit the policy of the meeting organizer.</span></span>

![显示带有音频和视频设置的会议的屏幕截图](media/meeting-policies-audio-video-settings.png)

<span data-ttu-id="59b06-237">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="59b06-237">Let's look at the following example.</span></span>

|<span data-ttu-id="59b06-238">用户</span><span class="sxs-lookup"><span data-stu-id="59b06-238">User</span></span> |<span data-ttu-id="59b06-239">会议策略</span><span class="sxs-lookup"><span data-stu-id="59b06-239">Meeting policy</span></span>  |<span data-ttu-id="59b06-240">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="59b06-240">Allow IP Video</span></span> |
|---------|---------|---------|
|<span data-ttu-id="59b06-241">Daniela</span><span class="sxs-lookup"><span data-stu-id="59b06-241">Daniela</span></span>   | <span data-ttu-id="59b06-242">全局</span><span class="sxs-lookup"><span data-stu-id="59b06-242">Global</span></span>   | <span data-ttu-id="59b06-243">True</span><span class="sxs-lookup"><span data-stu-id="59b06-243">True</span></span>        |
|<span data-ttu-id="59b06-244">Amanda</span><span class="sxs-lookup"><span data-stu-id="59b06-244">Amanda</span></span>    | <span data-ttu-id="59b06-245">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="59b06-245">Location1MeetingPolicy</span></span>        | <span data-ttu-id="59b06-246">False</span><span class="sxs-lookup"><span data-stu-id="59b06-246">False</span></span>      |

<span data-ttu-id="59b06-247">通过 Daniela 托管的会议允许打开视频。</span><span class="sxs-lookup"><span data-stu-id="59b06-247">Meetings hosted by Daniela allow video to be turned on.</span></span> <span data-ttu-id="59b06-248">Daniela 可以加入会议并打开视频。</span><span class="sxs-lookup"><span data-stu-id="59b06-248">Daniela can join the meeting and turn on video.</span></span> <span data-ttu-id="59b06-249">Amanda 无法在 Daniela 的会议中启用视频，因为 Amanda 的策略设置为 "不允许视频"。</span><span class="sxs-lookup"><span data-stu-id="59b06-249">Amanda can't turn on video in Daniela's meeting because Amanda's policy is set to not allow video.</span></span> <span data-ttu-id="59b06-250">Amanda 可以查看会议中其他参与者共享的视频。</span><span class="sxs-lookup"><span data-stu-id="59b06-250">Amanda can see videos shared by other participants in the meeting.</span></span>

<span data-ttu-id="59b06-251">在 Amanda 托管的会议中，无论分配给他们的视频策略如何，任何人都无法打开视频。</span><span class="sxs-lookup"><span data-stu-id="59b06-251">In meetings hosted by Amanda, no one can turn on video, regardless of the video policy assigned to them.</span></span> <span data-ttu-id="59b06-252">这意味着 Daniela 无法在 Amanda 的会议中打开视频。</span><span class="sxs-lookup"><span data-stu-id="59b06-252">This means Daniela can't turn on video in Amanda's meetings.</span></span>  

<span data-ttu-id="59b06-253">如果 Daniela 通过视频 Amanda 调用，Amanda 只能通过音频应答呼叫。</span><span class="sxs-lookup"><span data-stu-id="59b06-253">If Daniela calls Amanda with video on, Amanda can answer the call with audio only.</span></span>  <span data-ttu-id="59b06-254">当呼叫连接时，Amanda 可以看到 Daniela 的视频，但无法打开视频。</span><span class="sxs-lookup"><span data-stu-id="59b06-254">When the call is connected, Amanda can see Daniela's video, but can't turn on video.</span></span> <span data-ttu-id="59b06-255">如果 Amanda 呼叫 Daniela，Daniela 可以通过视频和音频接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="59b06-255">If Amanda calls Daniela, Daniela can answer the call with video and audio.</span></span> <span data-ttu-id="59b06-256">通话接通后，Daniela 可以根据需要打开或关闭她的视频。</span><span class="sxs-lookup"><span data-stu-id="59b06-256">When the call is connected, Daniela can turn on or turn off her video, as needed.</span></span>

### <a name="media-bit-rate-kbs"></a><span data-ttu-id="59b06-257">媒体比特率（Kbs）</span><span class="sxs-lookup"><span data-stu-id="59b06-257">Media bit rate (Kbs)</span></span>

<span data-ttu-id="59b06-258">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-258">This is a per-user policy.</span></span> <span data-ttu-id="59b06-259">此设置确定用户的通话和会议中音频、视频和基于视频的应用共享传输的媒体比特率。</span><span class="sxs-lookup"><span data-stu-id="59b06-259">This setting determines the media bit rate for audio, video, and video-based app sharing transmissions in calls and meetings for the user.</span></span> <span data-ttu-id="59b06-260">它同时应用于呼叫或会议中用户的上行媒体和下行媒体遍历。</span><span class="sxs-lookup"><span data-stu-id="59b06-260">It's applied to both the uplink and downlink media traversal for users in the call or meeting.</span></span> <span data-ttu-id="59b06-261">此设置使你能够更细致地控制组织中的带宽管理。</span><span class="sxs-lookup"><span data-stu-id="59b06-261">This setting gives you granular control over managing bandwidth in your organization.</span></span> <span data-ttu-id="59b06-262">根据用户所需的会议方案，我们建议有足够的带宽来实现优质体验。</span><span class="sxs-lookup"><span data-stu-id="59b06-262">Depending on the meetings scenarios required by users, we recommend having enough bandwidth in place for a good quality experience.</span></span> <span data-ttu-id="59b06-263">最小值为 30 Kbps，最大值取决于会议方案。</span><span class="sxs-lookup"><span data-stu-id="59b06-263">The minimum value is 30 Kbps and the maximum value depends on the meeting scenario.</span></span> <span data-ttu-id="59b06-264">若要了解更多有关建议的最小带宽以供团队的优质会议、通话和实时活动，请参阅[带宽要求](prepare-network.md#bandwidth-requirements)。</span><span class="sxs-lookup"><span data-stu-id="59b06-264">To learn more about the minimum recommended bandwidth for good quality meetings, calls, and live events in Teams, see [Bandwidth requirements](prepare-network.md#bandwidth-requirements).</span></span>

<span data-ttu-id="59b06-265">如果会议带宽不足，参与者会看到指示网络质量不佳的消息。</span><span class="sxs-lookup"><span data-stu-id="59b06-265">If there isn't enough bandwidth for a meeting, participants see a message that indicates poor network quality.</span></span>

<span data-ttu-id="59b06-266">对于需要最高质量视频体验的会议（如 CEO 董事会会议和团队现场活动），我们建议您将带宽设置为 10 Mbps。</span><span class="sxs-lookup"><span data-stu-id="59b06-266">For meetings that need the highest quality video experience, such as CEO board meetings and Teams live events, we recommend you set the bandwidth to 10 Mbps.</span></span> <span data-ttu-id="59b06-267">即使设置了最大体验，团队媒体堆栈也会在检测到某些网络条件时适应低带宽条件，具体取决于方案。</span><span class="sxs-lookup"><span data-stu-id="59b06-267">Even when the maximum experience is set, the Teams media stack adapts to low bandwidth conditions when certain network conditions are detected, depending on the scenario.</span></span> 

## <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="59b06-268">会议策略设置-内容共享</span><span class="sxs-lookup"><span data-stu-id="59b06-268">Meeting policy settings - Content sharing</span></span>

- [<span data-ttu-id="59b06-269">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="59b06-269">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="59b06-270">允许参与者授予或请求控制</span><span class="sxs-lookup"><span data-stu-id="59b06-270">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="59b06-271">允许外部参与者授予或请求控制</span><span class="sxs-lookup"><span data-stu-id="59b06-271">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="59b06-272">允许 PowerPoint 共享</span><span class="sxs-lookup"><span data-stu-id="59b06-272">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="59b06-273">允许白板</span><span class="sxs-lookup"><span data-stu-id="59b06-273">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="59b06-274">允许共享笔记</span><span class="sxs-lookup"><span data-stu-id="59b06-274">Allow shared notes</span></span>](#allow-shared-notes)

### <a name="screen-sharing-mode"></a><span data-ttu-id="59b06-275">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="59b06-275">Screen sharing mode</span></span>

<span data-ttu-id="59b06-276">这是每个组织单位和每用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="59b06-276">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="59b06-277">此设置控制是否允许在用户的会议中共享桌面和/或窗口共享。</span><span class="sxs-lookup"><span data-stu-id="59b06-277">This setting controls whether desktop and/or window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="59b06-278">未分配任何策略的会议参与者（如匿名、来宾、B2B 和联盟参与者）将继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-278">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="59b06-279">设置值</span><span class="sxs-lookup"><span data-stu-id="59b06-279">Setting value</span></span> |<span data-ttu-id="59b06-280">行为</span><span class="sxs-lookup"><span data-stu-id="59b06-280">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="59b06-281">**整个屏幕**</span><span class="sxs-lookup"><span data-stu-id="59b06-281">**Entire screen**</span></span>    | <span data-ttu-id="59b06-282">会议中允许进行完整的桌面共享和应用程序共享</span><span class="sxs-lookup"><span data-stu-id="59b06-282">Full desktop sharing and application sharing is allowed in the meeting</span></span> |
|<span data-ttu-id="59b06-283">**单应用程序**</span><span class="sxs-lookup"><span data-stu-id="59b06-283">**Single application**</span></span>   | <span data-ttu-id="59b06-284">允许在会议中共享应用程序</span><span class="sxs-lookup"><span data-stu-id="59b06-284">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="59b06-285">**已禁用**</span><span class="sxs-lookup"><span data-stu-id="59b06-285">**Disabled**</span></span>     |<span data-ttu-id="59b06-286">会议中已关闭屏幕共享和应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="59b06-286">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="59b06-287">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="59b06-287">Let's look at the following example.</span></span>

|<span data-ttu-id="59b06-288">用户</span><span class="sxs-lookup"><span data-stu-id="59b06-288">User</span></span> |<span data-ttu-id="59b06-289">会议策略</span><span class="sxs-lookup"><span data-stu-id="59b06-289">Meeting policy</span></span> |<span data-ttu-id="59b06-290">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="59b06-290">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="59b06-291">Daniela</span><span class="sxs-lookup"><span data-stu-id="59b06-291">Daniela</span></span>  | <span data-ttu-id="59b06-292">全局</span><span class="sxs-lookup"><span data-stu-id="59b06-292">Global</span></span>   | <span data-ttu-id="59b06-293">整个屏幕</span><span class="sxs-lookup"><span data-stu-id="59b06-293">Entire screen</span></span> |
|<span data-ttu-id="59b06-294">Amanda</span><span class="sxs-lookup"><span data-stu-id="59b06-294">Amanda</span></span>   | <span data-ttu-id="59b06-295">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="59b06-295">Location1MeetingPolicy</span></span>  | <span data-ttu-id="59b06-296">已禁用</span><span class="sxs-lookup"><span data-stu-id="59b06-296">Disabled</span></span> |

<span data-ttu-id="59b06-297">由 Daniela 托管的会议允许会议参与者共享其整个屏幕或特定应用程序。</span><span class="sxs-lookup"><span data-stu-id="59b06-297">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="59b06-298">如果 Amanda 加入 Daniela 的会议，Amanda 无法共享她的屏幕或特定应用程序，因为她的策略设置已被禁用。</span><span class="sxs-lookup"><span data-stu-id="59b06-298">If Amanda joins Daniela's meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="59b06-299">在 Amanda 托管的会议中，不允许任何人共享其屏幕或单个应用程序，而不管分配给他们的屏幕共享模式策略如何。</span><span class="sxs-lookup"><span data-stu-id="59b06-299">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span> <span data-ttu-id="59b06-300">这意味着 Daniela 不能在 Amanda 的会议中共享她的屏幕或单个应用程序。</span><span class="sxs-lookup"><span data-stu-id="59b06-300">This means that Daniela can't share her screen or a single application in Amanda's meetings.</span></span>  

<span data-ttu-id="59b06-301">当前，如果用户使用的是 Google Chrome，则用户无法在团队会议中播放视频或共享其屏幕。</span><span class="sxs-lookup"><span data-stu-id="59b06-301">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

### <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="59b06-302">允许参与者授予或请求控制</span><span class="sxs-lookup"><span data-stu-id="59b06-302">Allow a participant to give or request control</span></span>

<span data-ttu-id="59b06-303">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-303">This is a per-user policy.</span></span> <span data-ttu-id="59b06-304">此设置控制用户是否可以将共享桌面或窗口的控制权授予其他会议参与者。</span><span class="sxs-lookup"><span data-stu-id="59b06-304">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="59b06-305">若要赋予控制权，请将鼠标悬停在屏幕顶部。</span><span class="sxs-lookup"><span data-stu-id="59b06-305">To give control, hover over the top of the screen.</span></span> 

<span data-ttu-id="59b06-306">如果为用户启用此设置，则 "**授予控制权**" 选项显示在共享会话的顶部栏中。</span><span class="sxs-lookup"><span data-stu-id="59b06-306">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span> 

![显示 "提供控制" 选项的屏幕截图](media/meeting-policies-give-control.png)

<span data-ttu-id="59b06-308">如果用户的设置处于关闭状态，则 "**提供控制**" 选项不可用。</span><span class="sxs-lookup"><span data-stu-id="59b06-308">If the settings is turned off for the user, the **Give Control** option isn't available.</span></span>

![显示 "提供控件" 选项不可用的屏幕截图](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="59b06-310">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="59b06-310">Let's look at the following example.</span></span>

|<span data-ttu-id="59b06-311">用户</span><span class="sxs-lookup"><span data-stu-id="59b06-311">User</span></span> |<span data-ttu-id="59b06-312">会议策略</span><span class="sxs-lookup"><span data-stu-id="59b06-312">Meeting policy</span></span>  |<span data-ttu-id="59b06-313">允许参与者授予或请求控制</span><span class="sxs-lookup"><span data-stu-id="59b06-313">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="59b06-314">Daniela</span><span class="sxs-lookup"><span data-stu-id="59b06-314">Daniela</span></span>   | <span data-ttu-id="59b06-315">全局</span><span class="sxs-lookup"><span data-stu-id="59b06-315">Global</span></span>   | <span data-ttu-id="59b06-316">True</span><span class="sxs-lookup"><span data-stu-id="59b06-316">True</span></span>       |
|<span data-ttu-id="59b06-317">Babek</span><span class="sxs-lookup"><span data-stu-id="59b06-317">Babek</span></span>    | <span data-ttu-id="59b06-318">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="59b06-318">Location1MeetingPolicy</span></span>        | <span data-ttu-id="59b06-319">False</span><span class="sxs-lookup"><span data-stu-id="59b06-319">False</span></span>   |

<span data-ttu-id="59b06-320">Daniela 可以将共享桌面或窗口的控制权交给 Babek 组织的会议中的其他参与者，Babek 无法将控制权授予其他参与者。</span><span class="sxs-lookup"><span data-stu-id="59b06-320">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek whereas Babek can't give control to other participants.</span></span>

<span data-ttu-id="59b06-321">若要使用 PowerShell 控制哪些人可以授予控制请求或接受控制请求，请使用 AllowParticipantGiveRequestControl cmdlet。</span><span class="sxs-lookup"><span data-stu-id="59b06-321">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="59b06-322">若要在共享期间提供和控制共享内容，双方都必须使用团队桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="59b06-322">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="59b06-323">如果任何一方在浏览器中运行 Teams，则不支持控制。</span><span class="sxs-lookup"><span data-stu-id="59b06-323">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="59b06-324">这是由我们计划修复的一个技术限制造成。</span><span class="sxs-lookup"><span data-stu-id="59b06-324">This is due to a technical limitation that we're planning to fix.</span></span> 

### <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="59b06-325">允许外部参与者授予或请求控制</span><span class="sxs-lookup"><span data-stu-id="59b06-325">Allow an external participant to give or request control</span></span>

<span data-ttu-id="59b06-326">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-326">This is a per-user policy.</span></span> <span data-ttu-id="59b06-327">此设置控制会议中的外部参与者是否可以将其共享桌面或窗口的控制权交给会议中的其他参与者。</span><span class="sxs-lookup"><span data-stu-id="59b06-327">This setting controls whether external participants in a meeting can give control of their shared desktop or window to other participants in the meeting.</span></span> <span data-ttu-id="59b06-328">团队会议中的外部参与者可以按如下方式进行分类：</span><span class="sxs-lookup"><span data-stu-id="59b06-328">External participants in Teams meetings can be categorized as follows:</span></span>  

- <span data-ttu-id="59b06-329">匿名用户</span><span class="sxs-lookup"><span data-stu-id="59b06-329">Anonymous user</span></span>
- <span data-ttu-id="59b06-330">来宾用户</span><span class="sxs-lookup"><span data-stu-id="59b06-330">Guest users</span></span>  
- <span data-ttu-id="59b06-331">B2B 用户</span><span class="sxs-lookup"><span data-stu-id="59b06-331">B2B user</span></span>
- <span data-ttu-id="59b06-332">联合用户</span><span class="sxs-lookup"><span data-stu-id="59b06-332">Federated user</span></span>  

<span data-ttu-id="59b06-333">联盟用户是否可以向外部用户授予控制权，同时共享受允许外部参与者在其组织中**授予或请求控制**设置的控制。</span><span class="sxs-lookup"><span data-stu-id="59b06-333">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="59b06-334">若要使用 PowerShell 控制外部参与者是否可以授予控制或接受控制请求，请使用 AllowExternalParticipantGiveRequestControl cmdlet。</span><span class="sxs-lookup"><span data-stu-id="59b06-334">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="59b06-335">允许 PowerPoint 共享</span><span class="sxs-lookup"><span data-stu-id="59b06-335">Allow PowerPoint sharing</span></span>

<span data-ttu-id="59b06-336">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-336">This is a per-user policy.</span></span> <span data-ttu-id="59b06-337">此设置控制用户是否可以在会议中共享 PowerPoint 幻灯片放映。</span><span class="sxs-lookup"><span data-stu-id="59b06-337">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="59b06-338">外部用户（包括匿名用户、来宾和联盟用户）继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-338">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="59b06-339">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="59b06-339">Let's look at the following example.</span></span>

|<span data-ttu-id="59b06-340">用户</span><span class="sxs-lookup"><span data-stu-id="59b06-340">User</span></span> |<span data-ttu-id="59b06-341">会议策略</span><span class="sxs-lookup"><span data-stu-id="59b06-341">Meeting policy</span></span>  |<span data-ttu-id="59b06-342">允许 PowerPoint 共享</span><span class="sxs-lookup"><span data-stu-id="59b06-342">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="59b06-343">Daniela</span><span class="sxs-lookup"><span data-stu-id="59b06-343">Daniela</span></span>   | <span data-ttu-id="59b06-344">全局</span><span class="sxs-lookup"><span data-stu-id="59b06-344">Global</span></span>   | <span data-ttu-id="59b06-345">True</span><span class="sxs-lookup"><span data-stu-id="59b06-345">True</span></span>       |
|<span data-ttu-id="59b06-346">Amanda</span><span class="sxs-lookup"><span data-stu-id="59b06-346">Amanda</span></span>   | <span data-ttu-id="59b06-347">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="59b06-347">Location1MeetingPolicy</span></span>        | <span data-ttu-id="59b06-348">False</span><span class="sxs-lookup"><span data-stu-id="59b06-348">False</span></span>   |

<span data-ttu-id="59b06-349">Amanda 不能在会议中共享 PowerPoint 幻灯片卡座，即使她是会议组织者也是如此。</span><span class="sxs-lookup"><span data-stu-id="59b06-349">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="59b06-350">Daniela 可以共享 PowerPoint 幻灯片放映，即使会议由 Amanda 组织。</span><span class="sxs-lookup"><span data-stu-id="59b06-350">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="59b06-351">Amanda 可以查看会议中其他人共享的 PowerPoint 幻灯片卡座，即使她无法共享 PowerPoint 幻灯片放映。</span><span class="sxs-lookup"><span data-stu-id="59b06-351">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

### <a name="allow-whiteboard"></a><span data-ttu-id="59b06-352">允许白板</span><span class="sxs-lookup"><span data-stu-id="59b06-352">Allow whiteboard</span></span>

<span data-ttu-id="59b06-353">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-353">This is a per-user policy.</span></span> <span data-ttu-id="59b06-354">此设置控制用户是否可以在会议中共享白板。</span><span class="sxs-lookup"><span data-stu-id="59b06-354">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="59b06-355">外部用户（包括匿名用户、B2B 和联盟用户）继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-355">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> 

<span data-ttu-id="59b06-356">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="59b06-356">Let's look at the following example.</span></span>

|<span data-ttu-id="59b06-357">用户</span><span class="sxs-lookup"><span data-stu-id="59b06-357">User</span></span> |<span data-ttu-id="59b06-358">会议策略</span><span class="sxs-lookup"><span data-stu-id="59b06-358">Meeting policy</span></span>  |<span data-ttu-id="59b06-359">允许白板</span><span class="sxs-lookup"><span data-stu-id="59b06-359">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="59b06-360">Daniela</span><span class="sxs-lookup"><span data-stu-id="59b06-360">Daniela</span></span>   | <span data-ttu-id="59b06-361">全局</span><span class="sxs-lookup"><span data-stu-id="59b06-361">Global</span></span>   | <span data-ttu-id="59b06-362">True</span><span class="sxs-lookup"><span data-stu-id="59b06-362">True</span></span>       |
|<span data-ttu-id="59b06-363">Amanda</span><span class="sxs-lookup"><span data-stu-id="59b06-363">Amanda</span></span>   | <span data-ttu-id="59b06-364">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="59b06-364">Location1MeetingPolicy</span></span>        | <span data-ttu-id="59b06-365">False</span><span class="sxs-lookup"><span data-stu-id="59b06-365">False</span></span>   |

<span data-ttu-id="59b06-366">Amanda 无法在会议中共享白板，即使她是会议组织者也是如此。</span><span class="sxs-lookup"><span data-stu-id="59b06-366">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="59b06-367">即使会议是按 Amanda 组织的，Daniela 也可以共享白板。</span><span class="sxs-lookup"><span data-stu-id="59b06-367">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

### <a name="allow-shared-notes"></a><span data-ttu-id="59b06-368">允许共享笔记</span><span class="sxs-lookup"><span data-stu-id="59b06-368">Allow shared notes</span></span>

<span data-ttu-id="59b06-369">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-369">This is a per-user policy.</span></span> <span data-ttu-id="59b06-370">此设置控制用户是否可以在会议中创建和共享笔记。</span><span class="sxs-lookup"><span data-stu-id="59b06-370">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="59b06-371">外部用户（包括匿名用户、B2B 和联盟用户）继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-371">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="59b06-372">"**会议笔记**" 选项卡目前仅在具有少于20个参与者的会议中受支持。</span><span class="sxs-lookup"><span data-stu-id="59b06-372">The **Meeting Notes** tab is currently only supported in meetings that have less than 20 participants.</span></span>

<span data-ttu-id="59b06-373">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="59b06-373">Let's look at the following example.</span></span>

|<span data-ttu-id="59b06-374">用户</span><span class="sxs-lookup"><span data-stu-id="59b06-374">User</span></span> |<span data-ttu-id="59b06-375">会议策略</span><span class="sxs-lookup"><span data-stu-id="59b06-375">Meeting policy</span></span>  |<span data-ttu-id="59b06-376">允许共享笔记</span><span class="sxs-lookup"><span data-stu-id="59b06-376">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="59b06-377">Daniela</span><span class="sxs-lookup"><span data-stu-id="59b06-377">Daniela</span></span>   | <span data-ttu-id="59b06-378">全局</span><span class="sxs-lookup"><span data-stu-id="59b06-378">Global</span></span>   | <span data-ttu-id="59b06-379">True</span><span class="sxs-lookup"><span data-stu-id="59b06-379">True</span></span>       |
|<span data-ttu-id="59b06-380">Amanda</span><span class="sxs-lookup"><span data-stu-id="59b06-380">Amanda</span></span>   | <span data-ttu-id="59b06-381">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="59b06-381">Location1MeetingPolicy</span></span> | <span data-ttu-id="59b06-382">False</span><span class="sxs-lookup"><span data-stu-id="59b06-382">False</span></span> |

<span data-ttu-id="59b06-383">Daniela 可以在 Amanda 的会议中做笔记，Amanda 不能在任何会议中做笔记。</span><span class="sxs-lookup"><span data-stu-id="59b06-383">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>

## <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="59b06-384">会议策略设置-参与者 & 来宾</span><span class="sxs-lookup"><span data-stu-id="59b06-384">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="59b06-385">这些设置控制在会议厅中等待的会议参与者，以及他们在会议中允许的参与级别。</span><span class="sxs-lookup"><span data-stu-id="59b06-385">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="59b06-386">让匿名人员开始会议</span><span class="sxs-lookup"><span data-stu-id="59b06-386">Let anonymous people start a meeting</span></span>](#let-anonymous-people-start-a-meeting)
- [<span data-ttu-id="59b06-387">自动允许人员</span><span class="sxs-lookup"><span data-stu-id="59b06-387">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="59b06-388">允许拨入用户绕过大厅</span><span class="sxs-lookup"><span data-stu-id="59b06-388">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby)
- [<span data-ttu-id="59b06-389">启用实时字幕</span><span class="sxs-lookup"><span data-stu-id="59b06-389">Enable live captions </span></span>](#enable-live-captions)
- [<span data-ttu-id="59b06-390">允许在会议中聊天</span><span class="sxs-lookup"><span data-stu-id="59b06-390">Allow chat in meetings </span></span>](#allow-chat-in-meetings)

> [!NOTE]
><span data-ttu-id="59b06-391">用于加入会议的选项会有所不同，具体取决于每个团队组的设置和连接方法。</span><span class="sxs-lookup"><span data-stu-id="59b06-391">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="59b06-392">如果你的组具有音频会议，并使用它进行连接，请参阅[音频会议](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="59b06-392">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="59b06-393">如果你的团队组没有音频会议，请参阅[在团队中加入会议](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)。</span><span class="sxs-lookup"><span data-stu-id="59b06-393">If your Teams group does not have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

### <a name="let-anonymous-people-start-a-meeting"></a><span data-ttu-id="59b06-394">让匿名人员开始会议</span><span class="sxs-lookup"><span data-stu-id="59b06-394">Let anonymous people start a meeting</span></span>

<span data-ttu-id="59b06-395">这是每个组织单位策略，允许在会议会议中进行 leaderless 拨号。</span><span class="sxs-lookup"><span data-stu-id="59b06-395">This is a per-organizer policy that allows for leaderless dial in conferencing meetings.</span></span> <span data-ttu-id="59b06-396">此设置控制在没有经过身份验证的组织中，拨号用户是否可以加入会议。</span><span class="sxs-lookup"><span data-stu-id="59b06-396">This setting controls whether dial in users can join the meeting without an authenticated user from the organization in attendance.</span></span> <span data-ttu-id="59b06-397">默认值为 False，表示用户将在大厅中等待，直到组织中的经过身份验证的用户加入会议。</span><span class="sxs-lookup"><span data-stu-id="59b06-397">The default value is False which means dial in users will wait in the lobby until an authenticated user from the organization joins the meeting.</span></span> 

<span data-ttu-id="59b06-398">**注意**如果为 False 且用户先加入会议，并将其放置在会议厅中，则组织用户必须使用团队客户端加入会议，以便从会议厅中允许用户。</span><span class="sxs-lookup"><span data-stu-id="59b06-398">**Note** If False and a dial in user joins the meeting first and is placed in the lobby, an organization user must join the meeting with a Teams client to admit the user from the lobby.</span></span> <span data-ttu-id="59b06-399">没有可用于在用户中拨打的会议厅控件。</span><span class="sxs-lookup"><span data-stu-id="59b06-399">There are no lobby controls available for dialed in users.</span></span> 


### <a name="automatically-admit-people"></a><span data-ttu-id="59b06-400">自动允许人员</span><span class="sxs-lookup"><span data-stu-id="59b06-400">Automatically admit people</span></span>

<span data-ttu-id="59b06-401">这是每个组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-401">This is a per-organizer policy.</span></span> <span data-ttu-id="59b06-402">此设置控制用户是否直接加入会议或在大厅中等待，直到他们被经过身份验证的用户许可。</span><span class="sxs-lookup"><span data-stu-id="59b06-402">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span> <span data-ttu-id="59b06-403">此设置不会应用于拨入用户。</span><span class="sxs-lookup"><span data-stu-id="59b06-403">This setting does not apply to dial in users.</span></span> 

![显示会议厅中有用户的会议的屏幕截图](media/meeting-policies-lobby.png)

 <span data-ttu-id="59b06-405">会议组织者可以单击会议邀请中的 "**会议选项**"，为其计划的每个会议更改此设置。</span><span class="sxs-lookup"><span data-stu-id="59b06-405">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span>
 
 <span data-ttu-id="59b06-406">**注意**在会议选项中，该设置标记为 "哪些人可以绕过会议厅"</span><span class="sxs-lookup"><span data-stu-id="59b06-406">**Note** In the meeting options the setting is labeled "Who can bypass the lobby"</span></span>
  
|<span data-ttu-id="59b06-407">设置值</span><span class="sxs-lookup"><span data-stu-id="59b06-407">Setting value</span></span>  |<span data-ttu-id="59b06-408">联接行为</span><span class="sxs-lookup"><span data-stu-id="59b06-408">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="59b06-409">**所有人**</span><span class="sxs-lookup"><span data-stu-id="59b06-409">**Everyone**</span></span>   |<span data-ttu-id="59b06-410">所有会议参与者都直接加入会议，而无需在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="59b06-410">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="59b06-411">这包括经过身份验证的用户、来自受信任组织（联合）、来宾和匿名用户的外部用户。</span><span class="sxs-lookup"><span data-stu-id="59b06-411">This includes authenticated users, external users from trusted organizations (federated), guests, and anonymous users.</span></span>     |
|<span data-ttu-id="59b06-412">**组织和联盟组织中的每个人**</span><span class="sxs-lookup"><span data-stu-id="59b06-412">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="59b06-413">组织内的经过身份验证的用户，包括来宾用户和来自受信任组织的用户，直接加入会议，而无需在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="59b06-413">Authenticated users within the organization, including guest users and the users from trusted organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="59b06-414">匿名用户在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="59b06-414">Anonymous users wait in the lobby.</span></span>   |
|<span data-ttu-id="59b06-415">**您的组织中的每个人**</span><span class="sxs-lookup"><span data-stu-id="59b06-415">**Everyone in your organization**</span></span>    |<span data-ttu-id="59b06-416">来自组织内部的经过身份验证的用户（包括来宾用户）直接加入会议，而无需在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="59b06-416">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="59b06-417">来自受信任组织和匿名用户在大厅中等待的用户。</span><span class="sxs-lookup"><span data-stu-id="59b06-417">Users from trusted organizations and anonymous users wait in the lobby.</span></span> <span data-ttu-id="59b06-418">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="59b06-418">This is the default setting.</span></span>           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a><span data-ttu-id="59b06-419">允许拨入用户绕过大厅</span><span class="sxs-lookup"><span data-stu-id="59b06-419">Allow dial-in users to bypass the lobby</span></span>

<span data-ttu-id="59b06-420">这是每个组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-420">This is a per-organizer policy.</span></span> <span data-ttu-id="59b06-421">此设置控制通过电话拨入的用户是否直接加入会议或在会议厅中等待，而不管 "是否**自动允许人员**" 设置。</span><span class="sxs-lookup"><span data-stu-id="59b06-421">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span> <span data-ttu-id="59b06-422">默认值为 False。</span><span class="sxs-lookup"><span data-stu-id="59b06-422">The default value is False.</span></span> <span data-ttu-id="59b06-423">当为 False 时，用户将在大厅中等待，直到组织用户通过团队客户加入会议并准许他们。</span><span class="sxs-lookup"><span data-stu-id="59b06-423">When False, dial in users will wait in the lobby until a organization user joins the meeting with a Teams client and admits them.</span></span> <span data-ttu-id="59b06-424">当为 True 时，当组织用户加入会议时，拨号用户将自动加入会议。</span><span class="sxs-lookup"><span data-stu-id="59b06-424">When True, dial in users will automatically join the meeting when an organization user joins the meeting.</span></span> 

<span data-ttu-id="59b06-425">**注意**如果用户在组织用户加入会议之前加入会议，则会将其放在大厅中，直到组织用户使用团队客户端加入会议并将其准许。</span><span class="sxs-lookup"><span data-stu-id="59b06-425">**Note** If a dial in user joins a meeting before an organization user joins the meeting, they will be placed in the lobby until an organization user joins the meeting using a Teams client and admits them.</span></span> 


### <a name="enable-live-captions"></a><span data-ttu-id="59b06-426">启用实时字幕</span><span class="sxs-lookup"><span data-stu-id="59b06-426">Enable live captions</span></span>

<span data-ttu-id="59b06-427">这是每用户策略，在会议期间应用。</span><span class="sxs-lookup"><span data-stu-id="59b06-427">This is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="59b06-428">此设置控制用户是否可以使用 "**打开实时标题**" 选项来打开和关闭用户出席的会议中的实时字幕。</span><span class="sxs-lookup"><span data-stu-id="59b06-428">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![显示 "打开实时字幕" 选项的屏幕截图](media/meeting-policies-live-captions.png)

|<span data-ttu-id="59b06-430">设置值</span><span class="sxs-lookup"><span data-stu-id="59b06-430">Setting value</span></span> |<span data-ttu-id="59b06-431">行为</span><span class="sxs-lookup"><span data-stu-id="59b06-431">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="59b06-432">**已禁用，但用户可以替代**</span><span class="sxs-lookup"><span data-stu-id="59b06-432">**Disabled but the user can override**</span></span>     | <span data-ttu-id="59b06-433">会议期间不会为用户自动打开实时字幕。</span><span class="sxs-lookup"><span data-stu-id="59b06-433">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="59b06-434">用户可以在 "溢出（**...**）" 菜单中看到 "**打开实时标题**" 选项以将其打开。</span><span class="sxs-lookup"><span data-stu-id="59b06-434">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="59b06-435">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="59b06-435">This is the default setting.</span></span> |
|<span data-ttu-id="59b06-436">**已禁用**</span><span class="sxs-lookup"><span data-stu-id="59b06-436">**Disabled**</span></span>     | <span data-ttu-id="59b06-437">会议期间，用户已禁用实时字幕。</span><span class="sxs-lookup"><span data-stu-id="59b06-437">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="59b06-438">用户不能选择将其打开。</span><span class="sxs-lookup"><span data-stu-id="59b06-438">The user doesn't have the option to turn them on.</span></span>          |

<span data-ttu-id="59b06-439"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="59b06-439"><a name="bkcontentsharing"> </a></span></span>

### <a name="allow-chat-in-meetings"></a><span data-ttu-id="59b06-440">允许在会议中聊天</span><span class="sxs-lookup"><span data-stu-id="59b06-440">Allow chat in meetings</span></span>

<span data-ttu-id="59b06-441">这是每个组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-441">This is a per-organizer policy.</span></span> <span data-ttu-id="59b06-442">此设置控制是否允许在用户的会议中使用会议聊天。</span><span class="sxs-lookup"><span data-stu-id="59b06-442">This setting controls whether meeting chat is allowed in the user's meeting.</span></span>

<span data-ttu-id="59b06-443"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="59b06-443"><a name="bkparticipantsandguests"> </a></span></span>

## <a name="meeting-policy-settings---designated-presenter-role-mode"></a><span data-ttu-id="59b06-444">会议策略设置-指定的演示者角色模式</span><span class="sxs-lookup"><span data-stu-id="59b06-444">Meeting policy settings - Designated presenter role mode</span></span>

<span data-ttu-id="59b06-445">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-445">This is a per-user policy.</span></span> <span data-ttu-id="59b06-446">此设置允许你更改团队客户端的 "**会议选项**" 中的 "**可以显示的人员**" 的默认值。</span><span class="sxs-lookup"><span data-stu-id="59b06-446">This setting lets you change the default value of the **Who can present?** setting in **Meeting options** in the Teams client.</span></span> <span data-ttu-id="59b06-447">此策略设置影响所有会议，包括 "立即开会" 会议。</span><span class="sxs-lookup"><span data-stu-id="59b06-447">This policy setting affects all meetings, including Meet Now meetings.</span></span>

<span data-ttu-id="59b06-448">"**可以显示的人员**" 设置让会议组织者可以选择哪些人可以在会议中成为演示者。</span><span class="sxs-lookup"><span data-stu-id="59b06-448">The **Who can present?** setting lets meeting organizers choose who can be presenters in a meeting.</span></span> <span data-ttu-id="59b06-449">若要了解详细信息，请参阅更改[团队会议中](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)团队会议和角色的[参与者设置](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e)。</span><span class="sxs-lookup"><span data-stu-id="59b06-449">To learn more, see [Change participant settings for a Teams meeting](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) and [Roles in a Teams meeting](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).</span></span>

<span data-ttu-id="59b06-450">目前，您只能使用 PowerShell 配置此策略设置。</span><span class="sxs-lookup"><span data-stu-id="59b06-450">Currently, you can only use PowerShell to configure this policy setting.</span></span> <span data-ttu-id="59b06-451">你可以使用[CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有团队会议策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-451">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="59b06-452">或者，使用 CsTeamsMeetingPolicy cmdlet 创建新[的](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy)团队会议策略，并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="59b06-452">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="59b06-453">若要指定**可显示的人员**的默认值？在团队中设置，请将**DesignatedPresenterRoleMode**参数设置为下列之一：</span><span class="sxs-lookup"><span data-stu-id="59b06-453">To specify the default value of the **Who can present?** setting in Teams, set the **DesignatedPresenterRoleMode** parameter to one of the following:</span></span>

- <span data-ttu-id="59b06-454">**EveryoneUserOverride**：所有会议参与者都可以是演示者。</span><span class="sxs-lookup"><span data-stu-id="59b06-454">**EveryoneUserOverride**:  All meeting participants can be presenters.</span></span> <span data-ttu-id="59b06-455">此值为默认值。</span><span class="sxs-lookup"><span data-stu-id="59b06-455">This is the default value.</span></span> <span data-ttu-id="59b06-456">此参数对应于团队中的 "**所有人**" 设置。</span><span class="sxs-lookup"><span data-stu-id="59b06-456">This parameter corresponds to the **Everyone** setting in Teams.</span></span>
- <span data-ttu-id="59b06-457">**EveryoneInCompanyUserOverride**：组织中的经过身份验证的用户（包括来宾用户）可以是演示者。</span><span class="sxs-lookup"><span data-stu-id="59b06-457">**EveryoneInCompanyUserOverride**: Authenticated users in the organization, including guest users, can be presenters.</span></span> <span data-ttu-id="59b06-458">此参数对应于团队中的 "**我的组织**" 设置中的人员。</span><span class="sxs-lookup"><span data-stu-id="59b06-458">This parameter corresponds to the **People in my organization** setting in Teams.</span></span>
- <span data-ttu-id="59b06-459">**OrganizerOnlyUserOverride**：只有会议组织者可以是演示者，并且所有会议参与者都指定为 "与会者"。</span><span class="sxs-lookup"><span data-stu-id="59b06-459">**OrganizerOnlyUserOverride**: Only the meeting organizer can be a presenter and all meeting participants are designated as attendees.</span></span> <span data-ttu-id="59b06-460">此参数对应于 "团队" 中的 "**仅我**" 设置。</span><span class="sxs-lookup"><span data-stu-id="59b06-460">This parameter corresponds to the **Only me** setting in Teams.</span></span>

<span data-ttu-id="59b06-461">请记住，在设置默认值后，会议组织者仍可以在团队中更改此设置，并选择哪些人可以在他们计划的会议中显示。</span><span class="sxs-lookup"><span data-stu-id="59b06-461">Keep in mind that after you set the default value, meeting organizers can still change this setting in Teams and choose who can present in the meetings that they schedule.</span></span>

## <a name="meeting-policy-settings---meeting-attendance-report"></a><span data-ttu-id="59b06-462">会议策略设置-会议出席情况报告</span><span class="sxs-lookup"><span data-stu-id="59b06-462">Meeting policy settings - Meeting attendance report</span></span>

<span data-ttu-id="59b06-463">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-463">This is a per-user policy.</span></span> <span data-ttu-id="59b06-464">此设置控制会议组织者是否可以下载[会议出席报告](teams-analytics-and-reports/meeting-attendance-report.md)。</span><span class="sxs-lookup"><span data-stu-id="59b06-464">This setting controls whether meeting organizers can download the [meeting attendance report](teams-analytics-and-reports/meeting-attendance-report.md).</span></span>

<span data-ttu-id="59b06-465">目前，您只能使用 PowerShell 配置此策略设置。</span><span class="sxs-lookup"><span data-stu-id="59b06-465">Currently, you can only use PowerShell to configure this policy setting.</span></span> <span data-ttu-id="59b06-466">你可以使用[CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有团队会议策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-466">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="59b06-467">或者，使用 CsTeamsMeetingPolicy cmdlet 创建新[的](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy)团队会议策略，并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="59b06-467">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="59b06-468">若要使会议组织者能够下载会议出席报告，请将**AllowEngagementReport**参数设置为 "**已启用**"。</span><span class="sxs-lookup"><span data-stu-id="59b06-468">To enable a meeting organizer to download the meeting attendance report, set the **AllowEngagementReport** parameter  to **Enabled**.</span></span> <span data-ttu-id="59b06-469">启用后，用于下载报告的选项将显示在 "**参与者**" 窗格中。</span><span class="sxs-lookup"><span data-stu-id="59b06-469">When enabled, the option to download the report is displayed in the **Participants** pane.</span></span>

<span data-ttu-id="59b06-470">若要阻止会议组织者下载报表，请将该参数设置为 "**已禁用**"。</span><span class="sxs-lookup"><span data-stu-id="59b06-470">To prevent a meeting organizer from downloading the report, set the parameter to **Disabled**.</span></span> <span data-ttu-id="59b06-471">默认情况下，此设置处于禁用状态，无法使用下载报表的选项。</span><span class="sxs-lookup"><span data-stu-id="59b06-471">By default, this setting is disabled and the option to download the report isn't available.</span></span>

## <a name="meeting-policy-settings---meeting-provider-for-islands-mode"></a><span data-ttu-id="59b06-472">会议策略设置-岛模式的会议提供商</span><span class="sxs-lookup"><span data-stu-id="59b06-472">Meeting policy settings - Meeting provider for Islands mode</span></span>

<span data-ttu-id="59b06-473">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-473">This is a per-user policy.</span></span> <span data-ttu-id="59b06-474">此设置控制将哪些 Outlook 会议加载项用于*以孤岛模式*使用的用户。</span><span class="sxs-lookup"><span data-stu-id="59b06-474">This setting controls which Outlook meeting add-in is used for *users who are in Islands mode*.</span></span> <span data-ttu-id="59b06-475">你可以指定用户是否只能使用团队会议加载项或团队会议和 Skype for business 会议加载项在 Outlook 中安排会议。</span><span class="sxs-lookup"><span data-stu-id="59b06-475">You can specify whether users can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins to schedule meetings in Outlook.</span></span>

<span data-ttu-id="59b06-476">你只能将此策略应用到处于孤岛模式的用户，并在其团队会议策略中将**AllowOutlookAddIn**参数设置为**True** 。</span><span class="sxs-lookup"><span data-stu-id="59b06-476">You can only apply this policy to users who are in Islands mode and have the **AllowOutlookAddIn** parameter set to **True** in their Teams meeting policy.</span></span>

<span data-ttu-id="59b06-477">目前，您只能使用 PowerShell 设置此策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-477">Currently, you can only use PowerShell to set this policy.</span></span> <span data-ttu-id="59b06-478">你可以使用[CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有团队会议策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-478">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="59b06-479">或者，使用 CsTeamsMeetingPolicy cmdlet 创建新[的](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy)团队会议策略，并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="59b06-479">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="59b06-480">若要指定希望用户可以使用哪个会议加载项，请按如下方式设置**PreferredMeetingProviderForIslandsMode**参数：</span><span class="sxs-lookup"><span data-stu-id="59b06-480">To specify which meeting add-in you want to be available to users, set the **PreferredMeetingProviderForIslandsMode** parameter as follows:</span></span>

- <span data-ttu-id="59b06-481">将参数设置为**TeamsAndSfB**可在 Outlook 中启用团队会议加载项和 Skype for business 加载项。</span><span class="sxs-lookup"><span data-stu-id="59b06-481">Set the parameter to **TeamsAndSfB** to enable both the Teams Meeting add-in and Skype for Business add-in in Outlook.</span></span> <span data-ttu-id="59b06-482">此值为默认值。</span><span class="sxs-lookup"><span data-stu-id="59b06-482">This is the default value.</span></span>
- <span data-ttu-id="59b06-483">将该参数设置为 "**团队**"，仅在 Outlook 中启用团队会议外接程序。</span><span class="sxs-lookup"><span data-stu-id="59b06-483">Set the parameter to **Teams** to enable only the Teams Meeting add-in in Outlook.</span></span> <span data-ttu-id="59b06-484">此策略设置可确保所有未来会议都有团队会议加入链接。</span><span class="sxs-lookup"><span data-stu-id="59b06-484">This policy setting ensures that all future meetings have a Teams meeting join link.</span></span> <span data-ttu-id="59b06-485">它不会将现有 Skype for Business 会议加入链接迁移到团队。</span><span class="sxs-lookup"><span data-stu-id="59b06-485">It doesn't migrate existing Skype for Business meeting join links to Teams.</span></span> <span data-ttu-id="59b06-486">此政策设置不会影响 Skype for Business 中的状态、聊天、PSTN 呼叫或任何其他功能，这意味着用户将继续使用 Skype for Business 进行这些功能。</span><span class="sxs-lookup"><span data-stu-id="59b06-486">This policy setting doesn't affect presence, chat, PSTN calling, or any other capabilities in Skype for Business, which means that users will continue to use Skype for Business for these capabilities.</span></span>

  <span data-ttu-id="59b06-487">如果你将参数设置为 "**团队**"，然后切换回**TeamsAndSfB**，则将启用这两个会议加载项。</span><span class="sxs-lookup"><span data-stu-id="59b06-487">If you set the parameter to **Teams**, and then switch back to **TeamsAndSfB**, both meeting add-ins are enabled.</span></span> <span data-ttu-id="59b06-488">但是，请注意，现有团队会议联接链接不会迁移到 Skype for business。</span><span class="sxs-lookup"><span data-stu-id="59b06-488">However, note that existing Teams meeting join links won't be migrated to Skype for Business.</span></span> <span data-ttu-id="59b06-489">只有在更改后安排的 Skype for Business 会议才会有 Skype for business 会议加入链接。</span><span class="sxs-lookup"><span data-stu-id="59b06-489">Only Skype for Business meetings scheduled after the change will have a Skype for Business meeting join link.</span></span>

## <a name="meeting-policy-settings---video-filters-mode"></a><span data-ttu-id="59b06-490">会议策略设置-视频筛选器模式</span><span class="sxs-lookup"><span data-stu-id="59b06-490">Meeting policy settings - Video filters mode</span></span>

<span data-ttu-id="59b06-491">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-491">This is a per-user policy.</span></span> <span data-ttu-id="59b06-492">此设置控制用户是否可以在会议中自定义其视频背景。</span><span class="sxs-lookup"><span data-stu-id="59b06-492">This setting controls whether users can customize their video background in a meeting.</span></span>

<span data-ttu-id="59b06-493">目前，您只能使用 PowerShell 设置此策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-493">Currently, you can only use PowerShell to set this policy.</span></span> <span data-ttu-id="59b06-494">你可以使用[CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有团队会议策略。</span><span class="sxs-lookup"><span data-stu-id="59b06-494">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="59b06-495">或者，使用 CsTeamsMeetingPolicy cmdlet 创建新[的](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy)团队会议策略，然后将策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="59b06-495">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet, and then assign the policy to users.</span></span>

<span data-ttu-id="59b06-496">若要指定用户是否可以在会议中自定义其视频背景，请设置**VideoFiltersMode**参数，如下所示：</span><span class="sxs-lookup"><span data-stu-id="59b06-496">To specify whether users can customize their video background in a meeting, set the **VideoFiltersMode** parameter as follows:</span></span>

|<span data-ttu-id="59b06-497">在 PowerShell 中设置值</span><span class="sxs-lookup"><span data-stu-id="59b06-497">Setting value in PowerShell</span></span> |<span data-ttu-id="59b06-498">行为</span><span class="sxs-lookup"><span data-stu-id="59b06-498">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="59b06-499">**NoFilters**</span><span class="sxs-lookup"><span data-stu-id="59b06-499">**NoFilters**</span></span>     |<span data-ttu-id="59b06-500">用户无法自定义其视频背景。</span><span class="sxs-lookup"><span data-stu-id="59b06-500">User can't customize their video background.</span></span>|
|<span data-ttu-id="59b06-501">**BlurOnly**</span><span class="sxs-lookup"><span data-stu-id="59b06-501">**BlurOnly**</span></span>     |<span data-ttu-id="59b06-502">用户可以选择对视频背景进行模糊处理。</span><span class="sxs-lookup"><span data-stu-id="59b06-502">User has the option to blur their video background.</span></span> |
|<span data-ttu-id="59b06-503">**BlurandDefaultBackgrounds**</span><span class="sxs-lookup"><span data-stu-id="59b06-503">**BlurandDefaultBackgrounds**</span></span>     |<span data-ttu-id="59b06-504">用户可以选择对其视频背景进行模糊处理，或选择默认的图像集作为其背景。</span><span class="sxs-lookup"><span data-stu-id="59b06-504">User has the option to blur their video background or choose from the default set of images to use as their background.</span></span> |
|<span data-ttu-id="59b06-505">**AllFilters**</span><span class="sxs-lookup"><span data-stu-id="59b06-505">**AllFilters**</span></span>     |<span data-ttu-id="59b06-506">使用可选择对其视频背景进行模糊处理，从默认的图像集进行选择，或上载自定义图像用作其背景。</span><span class="sxs-lookup"><span data-stu-id="59b06-506">Use has the option to blur their video background, choose from the default set of images, or upload custom images to use as their background.</span></span> |

> [!NOTE]
> <span data-ttu-id="59b06-507">用户上载的图像不会由团队进行筛选。</span><span class="sxs-lookup"><span data-stu-id="59b06-507">Images uploaded by users aren't screened by Teams.</span></span> <span data-ttu-id="59b06-508">使用**AllFilters**设置时，你应具有内部组织策略，以防止用户上传攻击性或不合适的图像，或者你的组织无权使用团队会议背景的图像。</span><span class="sxs-lookup"><span data-stu-id="59b06-508">When you use the **AllFilters** setting, you should have internal organization policies to prevent users from uploading offensive or inappropriate images, or images your organization don't have rights to use for Teams meeting backgrounds.</span></span>

## <a name="related-topics"></a><span data-ttu-id="59b06-509">相关主题</span><span class="sxs-lookup"><span data-stu-id="59b06-509">Related topics</span></span>

- [<span data-ttu-id="59b06-510">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="59b06-510">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="59b06-511">向团队中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="59b06-511">Assign policies to your users in Teams</span></span>](assign-policies.md)
