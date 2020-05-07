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
ms.openlocfilehash: 4a61d2563a63d2dc8d1b55bbf0bbc6c52230d900
ms.sourcegitcommit: c3f44fccdbd9178d30b52bb0db6f6d31a6dd174b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "44139206"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="87d11-103">管理团队中的会议策略</span><span class="sxs-lookup"><span data-stu-id="87d11-103">Manage meeting policies in Teams</span></span>

::: zone target="docs"
<span data-ttu-id="87d11-104">会议策略Meeting policies用于控制组织中用户安排的会议的与会者可用的功能。</span><span class="sxs-lookup"><span data-stu-id="87d11-104">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="87d11-105">创建策略并进行更改后，即可以将用户分配到策略。</span><span class="sxs-lookup"><span data-stu-id="87d11-105">After you create a policy and make your changes, you can then assign users to the policy.</span></span> <span data-ttu-id="87d11-106">可在 Microsoft 团队管理中心或通过使用[PowerShell](teams-powershell-overview.md)管理会议策略。</span><span class="sxs-lookup"><span data-stu-id="87d11-106">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

<span data-ttu-id="87d11-107">你可以通过以下方式实施策略，这会在会议开始之前、会议期间或会议后影响用户的会议体验。</span><span class="sxs-lookup"><span data-stu-id="87d11-107">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="87d11-108">实现类型</span><span class="sxs-lookup"><span data-stu-id="87d11-108">Implementation type</span></span>  |<span data-ttu-id="87d11-109">说明</span><span class="sxs-lookup"><span data-stu-id="87d11-109">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="87d11-110">每个组织者</span><span class="sxs-lookup"><span data-stu-id="87d11-110">Per-organizer</span></span>    |<span data-ttu-id="87d11-111">实施按组织者策略时，所有会议参与者都将继承组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="87d11-111">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="87d11-112">例如，**自动允许人员**为每个组织者策略，并控制用户是否直接加入会议，或在会议厅中等待分配了该策略的用户安排的会议。</span><span class="sxs-lookup"><span data-stu-id="87d11-112">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="87d11-113">每用户</span><span class="sxs-lookup"><span data-stu-id="87d11-113">Per-user</span></span>    |<span data-ttu-id="87d11-114">当你实现每用户策略时，仅应用每用户策略来限制组织者和/或会议参与者的某些功能。</span><span class="sxs-lookup"><span data-stu-id="87d11-114">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="87d11-115">例如，"**允许在频道中立即开会**" 是每用户策略。</span><span class="sxs-lookup"><span data-stu-id="87d11-115">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="87d11-116">每个组织者和每用户</span><span class="sxs-lookup"><span data-stu-id="87d11-116">Per-organizer and per-user</span></span>     |<span data-ttu-id="87d11-117">当你实现每个组织单位和每用户策略的组合时，某些功能将根据其策略和组织者的策略来限制会议参与者。</span><span class="sxs-lookup"><span data-stu-id="87d11-117">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="87d11-118">例如，"**允许云录制**" 是基于每个组织者和每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="87d11-118">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="87d11-119">启用此设置可允许会议组织者和参与者开始和停止录制。</span><span class="sxs-lookup"><span data-stu-id="87d11-119">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span>

<span data-ttu-id="87d11-120">默认情况下，将创建名为 Global 的策略（组织范围的默认设置）。</span><span class="sxs-lookup"><span data-stu-id="87d11-120">By default, a policy named Global (Org-wide default) is created.</span></span> <span data-ttu-id="87d11-121">默认情况下，组织中的所有用户都分配有 "全局会议策略"。</span><span class="sxs-lookup"><span data-stu-id="87d11-121">All users in your organization are assigned the Global meeting policy by default.</span></span> <span data-ttu-id="87d11-122">你可以对其进行更改或创建一个或多个自定义策略，并向其分配用户。</span><span class="sxs-lookup"><span data-stu-id="87d11-122">You can either make changes to it or create one or more custom policies and assign users to them.</span></span> <span data-ttu-id="87d11-123">除非你创建和分配自定义策略，否则用户将获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="87d11-123">Users will get the Global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="87d11-124">创建自定义策略时，你可以允许或阻止你的用户使用某些功能，然后将其分配给将对其应用设置的一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="87d11-124">When you create a custom policy, you can allow or prevent certain features from being available to your users, and then assign it to one or more users who will have the settings applied to them.</span></span>

> [!NOTE]
> <span data-ttu-id="87d11-125">"会议详细信息" 按钮在用户启用音频会议许可证或用户允许音频会议时可用，如果不是，则会议详细信息将不可用</span><span class="sxs-lookup"><span data-stu-id="87d11-125">Meeting details button will be available if a user has the audio conference licenses enabled or the user is allow for audio conferencing, if not, the meeting details will not be available</span></span>

## <a name="change-or-create-a-meeting-policy"></a><span data-ttu-id="87d11-126">更改或创建会议策略</span><span class="sxs-lookup"><span data-stu-id="87d11-126">Change or create a meeting policy</span></span>

<span data-ttu-id="87d11-127">若要更改或创建会议策略，请转到 Microsoft Teams 管理中心 >“**会议**” > “**会议策略**”。</span><span class="sxs-lookup"><span data-stu-id="87d11-127">To change or create a meeting policy, go to the Microsoft Teams admin center > **Meetings** > **Meeting policies**.</span></span> <span data-ttu-id="87d11-128">从列表中选择一个策略，或者选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="87d11-128">Select a policy from the list or select **Add**.</span></span> <span data-ttu-id="87d11-129">若正在创建新策略，则添加名称和说明。</span><span class="sxs-lookup"><span data-stu-id="87d11-129">If you're creating a new policy, add a name and description.</span></span> <span data-ttu-id="87d11-130">名称不能包含特殊字符或超过 64 个字符。</span><span class="sxs-lookup"><span data-stu-id="87d11-130">The name can't contain special characters or be longer than 64 characters.</span></span> <span data-ttu-id="87d11-131">选择您的设置，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="87d11-131">Choose your settings, and then select **Save**.</span></span>

<span data-ttu-id="87d11-132">例如，假设你有一组用户并且你想要限制这组用户的会议所需的带宽量。</span><span class="sxs-lookup"><span data-stu-id="87d11-132">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="87d11-133">你要创建新的自定义策略并命名为“带宽限制”，然后禁用以下设置：</span><span class="sxs-lookup"><span data-stu-id="87d11-133">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="87d11-134">在“音频和视频”中：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="87d11-134">Under **Audio & video**:</span></span>
- <span data-ttu-id="87d11-135">禁用“允许云录制”。</span><span class="sxs-lookup"><span data-stu-id="87d11-135">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="87d11-136">禁用“允许 IP 视频”。</span><span class="sxs-lookup"><span data-stu-id="87d11-136">Turn off Allow IP video.</span></span>

<span data-ttu-id="87d11-137">在“内容共享”中：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="87d11-137">Under **Content sharing**:</span></span>
- <span data-ttu-id="87d11-138">禁用屏幕共享模式。</span><span class="sxs-lookup"><span data-stu-id="87d11-138">Disable screen sharing mode.</span></span>
- <span data-ttu-id="87d11-139">禁用“允许白板”。</span><span class="sxs-lookup"><span data-stu-id="87d11-139">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="87d11-140">禁用“允许共享笔记”。</span><span class="sxs-lookup"><span data-stu-id="87d11-140">Turn off Allow shared notes.</span></span>

<span data-ttu-id="87d11-141">然后将此策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="87d11-141">Then assign the policy to the users.</span></span>

> [!NOTE]
> <span data-ttu-id="87d11-142">一次只能向一个用户分配一个会议策略。</span><span class="sxs-lookup"><span data-stu-id="87d11-142">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="87d11-143">将会议策略分配给用户</span><span class="sxs-lookup"><span data-stu-id="87d11-143">Assign a meeting policy to users</span></span>

1. <span data-ttu-id="87d11-144">在 Microsoft Teams 管理员中心的左侧导航中，转到“用户”，然后单击相应的用户。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="87d11-144">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="87d11-145">单击用户名的左侧以选择用户，然后单击“编辑设置”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="87d11-145">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="87d11-146">在“会议策略”中，选择想要分配的策略，然后单击“应用”。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="87d11-146">Under **Meeting policy**, select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="87d11-147">若要将策略一次性分配给多个用户，请参阅[批量编辑 Teams 用户设置](edit-user-settings-in-bulk.md)。</span><span class="sxs-lookup"><span data-stu-id="87d11-147">To assign a policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="87d11-148">或者，您也可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="87d11-148">Or, you can also do the following:</span></span>

1. <span data-ttu-id="87d11-149">在 Microsoft 团队管理中心的左侧导航中，转到 "**会议** > **会议策略**"。</span><span class="sxs-lookup"><span data-stu-id="87d11-149">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="87d11-150">单击策略名称的左侧以选择该策略。</span><span class="sxs-lookup"><span data-stu-id="87d11-150">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="87d11-151">选择“管理用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="87d11-151">Select **Manage users**.</span></span>
4. <span data-ttu-id="87d11-152">在“**管理用户**”窗格中，按显示名称或用户名搜索用户，选择用户名，然后选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="87d11-152">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="87d11-153">对想要添加的每一个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="87d11-153">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="87d11-154">添加完用户后，选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="87d11-154">After you finish adding users, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="87d11-155">如果向用户分配了该策略，则不能删除该策略。</span><span class="sxs-lookup"><span data-stu-id="87d11-155">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="87d11-156">必须先为所有受影响的用户分配不同的策略，然后才能删除原始策略。</span><span class="sxs-lookup"><span data-stu-id="87d11-156">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="87d11-157">会议策略设置</span><span class="sxs-lookup"><span data-stu-id="87d11-157">Meeting policy settings</span></span>

<span data-ttu-id="87d11-158">在 "**会议策略**" 页面上选择现有策略或选择 "**添加**" 以添加新策略时，可以为以下项配置设置。</span><span class="sxs-lookup"><span data-stu-id="87d11-158">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="87d11-159">常规</span><span class="sxs-lookup"><span data-stu-id="87d11-159">General</span></span>](#meeting-policy-settings---general)
- [<span data-ttu-id="87d11-160">音频 & 视频</span><span class="sxs-lookup"><span data-stu-id="87d11-160">Audio & video</span></span>](#meeting-policy-settings---audio--video)
- [<span data-ttu-id="87d11-161">内容共享</span><span class="sxs-lookup"><span data-stu-id="87d11-161">Content sharing</span></span>](#meeting-policy-settings---content-sharing)
- [<span data-ttu-id="87d11-162">参与者 & 来宾</span><span class="sxs-lookup"><span data-stu-id="87d11-162">Participants & guests</span></span>](#meeting-policy-settings---participants--guests)

::: zone-end 

<span data-ttu-id="87d11-163"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="87d11-163"><a name="bkgeneral"> </a></span></span>

## <a name="meeting-policy-settings---general"></a><span data-ttu-id="87d11-164">会议策略设置-常规</span><span class="sxs-lookup"><span data-stu-id="87d11-164">Meeting policy settings - General</span></span>

- [<span data-ttu-id="87d11-165">允许在频道中立即开会</span><span class="sxs-lookup"><span data-stu-id="87d11-165">Allow Meet now in channels</span></span>](#allow-meet-now-in-channels)
- [<span data-ttu-id="87d11-166">允许 Outlook 加载项</span><span class="sxs-lookup"><span data-stu-id="87d11-166">Allow the Outlook add-in</span></span>](#allow-the-outlook-add-in)
- [<span data-ttu-id="87d11-167">允许频道会议安排</span><span class="sxs-lookup"><span data-stu-id="87d11-167">Allow channel meeting scheduling</span></span>](#allow-channel-meeting-scheduling)
- [<span data-ttu-id="87d11-168">允许安排私人会议</span><span class="sxs-lookup"><span data-stu-id="87d11-168">Allow scheduling private meetings</span></span>](#allow-scheduling-private-meetings)
- [<span data-ttu-id="87d11-169">允许在私人会议中立即开会</span><span class="sxs-lookup"><span data-stu-id="87d11-169">Allow Meet now in private meetings</span></span>](#allow-meet-now-in-private-meetings)

### <a name="allow-meet-now-in-channels"></a><span data-ttu-id="87d11-170">允许在频道中立即开会</span><span class="sxs-lookup"><span data-stu-id="87d11-170">Allow Meet now in channels</span></span>

<span data-ttu-id="87d11-171">这是每用户策略，在会议开始之前应用。</span><span class="sxs-lookup"><span data-stu-id="87d11-171">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="87d11-172">此设置控制用户是否可以在团队频道中启动临时会议。</span><span class="sxs-lookup"><span data-stu-id="87d11-172">This setting controls whether a user can start an ad hoc meeting in a Teams channel.</span></span> <span data-ttu-id="87d11-173">如果启用此操作，当用户在团队频道中发布消息时，用户可以单击 "撰写" 框下的 "**立即开会**" 以在频道中启动临时会议。</span><span class="sxs-lookup"><span data-stu-id="87d11-173">If you turn this on, when a user posts a message in a Teams channel, the user can click **Meet now** under the compose box to start an ad hoc meeting in the channel.</span></span> <span data-ttu-id="87d11-174">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="87d11-174">The default value is True.</span></span>

![显示邮件下方的 "立即开会" 图标的屏幕截图](media/meeting-policies-meet-now.png)

### <a name="allow-the-outlook-add-in"></a><span data-ttu-id="87d11-176">允许 Outlook 加载项</span><span class="sxs-lookup"><span data-stu-id="87d11-176">Allow the Outlook add-in</span></span>

<span data-ttu-id="87d11-177">这是每用户策略，在会议开始之前应用。</span><span class="sxs-lookup"><span data-stu-id="87d11-177">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="87d11-178">此设置控制是否可以从 Outlook （Windows、Mac、web 和手机）内安排团队会议。</span><span class="sxs-lookup"><span data-stu-id="87d11-178">This setting controls whether Teams meetings can be scheduled from within Outlook (Windows, Mac, web, and mobile).</span></span>

![显示安排新会议的功能的屏幕截图](media/meeting-policies-outlook-add-in.png)

<span data-ttu-id="87d11-180">如果关闭此功能，用户在 Outlook 中创建新会议时，无法安排团队会议。</span><span class="sxs-lookup"><span data-stu-id="87d11-180">If you turn this off, users are unable to schedule Teams meetings when they create a new meeting in Outlook.</span></span> <span data-ttu-id="87d11-181">例如，在 Windows 上的 Outlook 中，"**新建团队会议**" 选项不会显示在功能区中。</span><span class="sxs-lookup"><span data-stu-id="87d11-181">For example, in Outlook on Windows, the **New Teams Meeting** option won't show up in the ribbon.</span></span>

### <a name="allow-channel-meeting-scheduling"></a><span data-ttu-id="87d11-182">允许频道会议安排</span><span class="sxs-lookup"><span data-stu-id="87d11-182">Allow channel meeting scheduling</span></span>

<span data-ttu-id="87d11-183">这是每用户策略，在会议开始之前应用。</span><span class="sxs-lookup"><span data-stu-id="87d11-183">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="87d11-184">此设置控制用户是否可以在团队频道中安排会议。</span><span class="sxs-lookup"><span data-stu-id="87d11-184">This setting controls whether users can schedule a meeting in a Teams channel.</span></span>  <span data-ttu-id="87d11-185">如果关闭此功能，则当用户在团队频道中启动会议，并且为团队中的用户禁用 "**添加频道**" 选项时，"**安排会议**" 选项将不可用。</span><span class="sxs-lookup"><span data-stu-id="87d11-185">If you turn this off, the **Schedule a meeting** option won't be available to the user when they start a meeting in a Teams channel and the **Add channel** option is disabled for users in Teams.</span></span> <span data-ttu-id="87d11-186">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="87d11-186">The default value is True.</span></span>

![显示团队中的 "安排会议" 选项的屏幕截图](media/meeting-policies-schedule-a-meeting.png)

![显示 "选择要开会的频道" 选项的屏幕截图](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a><span data-ttu-id="87d11-189">允许安排私人会议</span><span class="sxs-lookup"><span data-stu-id="87d11-189">Allow scheduling private meetings</span></span>

<span data-ttu-id="87d11-190">这是每用户策略，在会议开始之前应用。</span><span class="sxs-lookup"><span data-stu-id="87d11-190">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="87d11-191">此设置控制用户是否可以在团队中安排私人会议。</span><span class="sxs-lookup"><span data-stu-id="87d11-191">This setting controls whether users can schedule private meetings in Teams.</span></span> <span data-ttu-id="87d11-192">当会议未发布到团队中的频道时，它是私有的。</span><span class="sxs-lookup"><span data-stu-id="87d11-192">A meeting is private when it's not published to a channel in a team.</span></span>

<span data-ttu-id="87d11-193">请注意，如果关闭 "**允许安排私人会议**" 和 "**允许频道会议计划**"，则会为团队中的用户禁用 "**添加必需与会者**" 和 "**添加频道**" 选项。</span><span class="sxs-lookup"><span data-stu-id="87d11-193">Note that if you turn off **Allow scheduling private meetings** and **Allow channel meeting scheduling**,  the **Add required attendees** and **Add channel** options are disabled for users in Teams.</span></span> <span data-ttu-id="87d11-194">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="87d11-194">The default value is True.</span></span>

### <a name="allow-meet-now-in-private-meetings"></a><span data-ttu-id="87d11-195">允许在私人会议中立即开会</span><span class="sxs-lookup"><span data-stu-id="87d11-195">Allow Meet now in private meetings</span></span>

<span data-ttu-id="87d11-196">这是每用户策略，在会议开始之前应用。</span><span class="sxs-lookup"><span data-stu-id="87d11-196">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="87d11-197">此设置控制用户是否可以启动 ad hoc 私人会议。</span><span class="sxs-lookup"><span data-stu-id="87d11-197">This setting controls whether a user can start an ad hoc private meeting.</span></span>  <span data-ttu-id="87d11-198">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="87d11-198">The default value is True.</span></span>

<span data-ttu-id="87d11-199"><a name="bkaudioandvideo"> </a></span><span class="sxs-lookup"><span data-stu-id="87d11-199"><a name="bkaudioandvideo"> </a></span></span>

## <a name="meeting-policy-settings---audio--video"></a><span data-ttu-id="87d11-200">会议策略设置-音频 & 视频</span><span class="sxs-lookup"><span data-stu-id="87d11-200">Meeting policy settings - Audio & video</span></span>

- [<span data-ttu-id="87d11-201">允许脚本</span><span class="sxs-lookup"><span data-stu-id="87d11-201">Allow transcription</span></span>](#allow-transcription)
- [<span data-ttu-id="87d11-202">允许云录制</span><span class="sxs-lookup"><span data-stu-id="87d11-202">Allow cloud recording</span></span>](#allow-cloud-recording)
- [<span data-ttu-id="87d11-203">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="87d11-203">Allow IP video</span></span>](#allow-ip-video)
- [<span data-ttu-id="87d11-204">媒体比特率（Kbs）</span><span class="sxs-lookup"><span data-stu-id="87d11-204">Media bit rate (Kbs)</span></span>](#media-bit-rate-kbs)

### <a name="allow-transcription"></a><span data-ttu-id="87d11-205">允许脚本</span><span class="sxs-lookup"><span data-stu-id="87d11-205">Allow transcription</span></span>

<span data-ttu-id="87d11-206">这是每个组织单位和每用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="87d11-206">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="87d11-207">此设置控制播放会议录制期间是否提供字幕和脚本功能。</span><span class="sxs-lookup"><span data-stu-id="87d11-207">This setting controls whether captions and transcription features are available during playback of meeting recordings.</span></span> <span data-ttu-id="87d11-208">如果关闭此功能，在播放会议录制的过程中，"**搜索**" 和 **"抄送**" 选项将不可用。</span><span class="sxs-lookup"><span data-stu-id="87d11-208">If you turn this off, the **Search** and **CC** options won't be available during playback of a meeting recording.</span></span> <span data-ttu-id="87d11-209">启动录制的人员需要启用此设置，以便录制还包括脚本。</span><span class="sxs-lookup"><span data-stu-id="87d11-209">The person who started the recording needs this setting turned on so that the recording also includes transcription.</span></span> 

<span data-ttu-id="87d11-210">请注意，当前只有在团队中将语言设置为英语且在会议中朗读英语的用户才支持使用录制的会议。</span><span class="sxs-lookup"><span data-stu-id="87d11-210">Note that transcription for recorded meetings is currently only supported for users who have the language in Teams set to English and when English is spoken in the meeting.</span></span>

![显示会议中的脚本选项的屏幕截图](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a><span data-ttu-id="87d11-212">允许云录制</span><span class="sxs-lookup"><span data-stu-id="87d11-212">Allow cloud recording</span></span>

<span data-ttu-id="87d11-213">这是每个组织单位和每用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="87d11-213">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="87d11-214">此设置控制是否可以录制此用户的会议。</span><span class="sxs-lookup"><span data-stu-id="87d11-214">This setting controls whether this user's meetings can be recorded.</span></span> <span data-ttu-id="87d11-215">录制可以由会议组织者或其他会议参与者启动（如果为参与者启用了该策略设置，并且他们是来自同一组织的经过身份验证的用户）。</span><span class="sxs-lookup"><span data-stu-id="87d11-215">The recording can be started by the meeting organizer or by another meeting participant if the policy setting is turned on for the participant and if they're an authenticated user from the same organization.</span></span>

<span data-ttu-id="87d11-216">组织外部的人员（如联盟用户和匿名用户）无法启动录制。</span><span class="sxs-lookup"><span data-stu-id="87d11-216">People outside your organization, such as federated and anonymous users, can't start the recording.</span></span> <span data-ttu-id="87d11-217">来宾用户无法启动或停止录制。</span><span class="sxs-lookup"><span data-stu-id="87d11-217">Guest users can't start or stop the recording.</span></span> 

![显示录制选项的屏幕截图](media/meeting-policies-recording.png)

<span data-ttu-id="87d11-219">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="87d11-219">Let's look at the following example.</span></span>

|<span data-ttu-id="87d11-220">用户</span><span class="sxs-lookup"><span data-stu-id="87d11-220">User</span></span> |<span data-ttu-id="87d11-221">会议策略</span><span class="sxs-lookup"><span data-stu-id="87d11-221">Meeting policy</span></span>  |<span data-ttu-id="87d11-222">允许云录制</span><span class="sxs-lookup"><span data-stu-id="87d11-222">Allow cloud recording</span></span> |
|---------|---------|---------|
|<span data-ttu-id="87d11-223">Daniela</span><span class="sxs-lookup"><span data-stu-id="87d11-223">Daniela</span></span> | <span data-ttu-id="87d11-224">全局</span><span class="sxs-lookup"><span data-stu-id="87d11-224">Global</span></span>   | <span data-ttu-id="87d11-225">False</span><span class="sxs-lookup"><span data-stu-id="87d11-225">False</span></span> |
|<span data-ttu-id="87d11-226">Amanda</span><span class="sxs-lookup"><span data-stu-id="87d11-226">Amanda</span></span> | <span data-ttu-id="87d11-227">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="87d11-227">Location1MeetingPolicy</span></span> | <span data-ttu-id="87d11-228">True</span><span class="sxs-lookup"><span data-stu-id="87d11-228">True</span></span>|
|<span data-ttu-id="87d11-229">John （外部用户）</span><span class="sxs-lookup"><span data-stu-id="87d11-229">John (external user)</span></span> | <span data-ttu-id="87d11-230">不适用</span><span class="sxs-lookup"><span data-stu-id="87d11-230">Not applicable</span></span> | <span data-ttu-id="87d11-231">不适用</span><span class="sxs-lookup"><span data-stu-id="87d11-231">Not applicable</span></span>|

<span data-ttu-id="87d11-232">按 Daniela 组织的会议无法录制，并且 Amanda 已启用策略设置，无法录制 Daniela 组织的会议。</span><span class="sxs-lookup"><span data-stu-id="87d11-232">Meetings organized by Daniela can't be recorded and Amanda, who has the policy setting enabled, can't record meetings organized by Daniela.</span></span> <span data-ttu-id="87d11-233">可记录由 Amanda 组织的会议，但 Daniela，他们已禁用策略设置，并且 John 是外部用户，无法录制 Amanda 组织的会议。</span><span class="sxs-lookup"><span data-stu-id="87d11-233">Meetings organized by Amanda can be recorded, however,  Daniela, who has the policy setting disabled and John who is an external user, can't record meetings organized by Amanda.</span></span>

<span data-ttu-id="87d11-234">若要了解有关云会议录制的详细信息，请参阅[团队云会议录制](cloud-recording.md)。</span><span class="sxs-lookup"><span data-stu-id="87d11-234">To learn more about cloud meeting recording, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

### <a name="allow-ip-video"></a><span data-ttu-id="87d11-235">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="87d11-235">Allow IP video</span></span>

<span data-ttu-id="87d11-236">这是每个组织单位和每用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="87d11-236">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="87d11-237">视频是会议的关键组件。</span><span class="sxs-lookup"><span data-stu-id="87d11-237">Video is a key component to meetings.</span></span> <span data-ttu-id="87d11-238">在某些组织中，管理员可能希望更好地控制哪些用户的会议有视频。</span><span class="sxs-lookup"><span data-stu-id="87d11-238">In some organizations, admins might want more control over which users' meetings have video.</span></span> <span data-ttu-id="87d11-239">此设置控制是否可以在用户托管的会议中以及用户开始的1:1 呼叫和组通话中打开视频。</span><span class="sxs-lookup"><span data-stu-id="87d11-239">This setting controls whether video can be turned on in meetings hosted by a user and in 1:1 calls and group calls started by a user.</span></span> <span data-ttu-id="87d11-240">已启用此策略的用户组织的会议，如果会议参与者也启用了该策略，则会议参与者允许会议中的视频共享。</span><span class="sxs-lookup"><span data-stu-id="87d11-240">Meetings organized by a user who has this policy enabled, allow video sharing in the meeting by the meeting participants, if the meeting participants also have the policy enabled.</span></span> <span data-ttu-id="87d11-241">未分配任何策略的会议参与者（如匿名和联盟参与者）将继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="87d11-241">Meeting participants who don't have any policies assigned (for example, anonymous and federated participants) inherit the policy of the meeting organizer.</span></span>

![显示带有音频和视频设置的会议的屏幕截图](media/meeting-policies-audio-video-settings.png)

<span data-ttu-id="87d11-243">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="87d11-243">Let's look at the following example.</span></span>

|<span data-ttu-id="87d11-244">用户</span><span class="sxs-lookup"><span data-stu-id="87d11-244">User</span></span> |<span data-ttu-id="87d11-245">会议策略</span><span class="sxs-lookup"><span data-stu-id="87d11-245">Meeting policy</span></span>  |<span data-ttu-id="87d11-246">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="87d11-246">Allow IP Video</span></span> |
|---------|---------|---------|
|<span data-ttu-id="87d11-247">Daniela</span><span class="sxs-lookup"><span data-stu-id="87d11-247">Daniela</span></span>   | <span data-ttu-id="87d11-248">全局</span><span class="sxs-lookup"><span data-stu-id="87d11-248">Global</span></span>   | <span data-ttu-id="87d11-249">True</span><span class="sxs-lookup"><span data-stu-id="87d11-249">True</span></span>        |
|<span data-ttu-id="87d11-250">Amanda</span><span class="sxs-lookup"><span data-stu-id="87d11-250">Amanda</span></span>    | <span data-ttu-id="87d11-251">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="87d11-251">Location1MeetingPolicy</span></span>        | <span data-ttu-id="87d11-252">False</span><span class="sxs-lookup"><span data-stu-id="87d11-252">False</span></span>      |

<span data-ttu-id="87d11-253">通过 Daniela 托管的会议允许打开视频。</span><span class="sxs-lookup"><span data-stu-id="87d11-253">Meetings hosted by Daniela allow video to be turned on.</span></span> <span data-ttu-id="87d11-254">Daniela 可以加入会议并打开视频。</span><span class="sxs-lookup"><span data-stu-id="87d11-254">Daniela can join the meeting and turn on video.</span></span> <span data-ttu-id="87d11-255">Amanda 无法在 Daniela 的会议中启用视频，因为 Amanda 的策略设置为 "不允许视频"。</span><span class="sxs-lookup"><span data-stu-id="87d11-255">Amanda can't turn on video in Daniela's meeting because Amanda's policy is set to not allow video.</span></span> <span data-ttu-id="87d11-256">Amanda 可以查看会议中其他参与者共享的视频。</span><span class="sxs-lookup"><span data-stu-id="87d11-256">Amanda can see videos shared by other participants in the meeting.</span></span>

<span data-ttu-id="87d11-257">在 Amanda 托管的会议中，无论分配给他们的视频策略如何，任何人都无法打开视频。</span><span class="sxs-lookup"><span data-stu-id="87d11-257">In meetings hosted by Amanda, no one can turn on video, regardless of the video policy assigned to them.</span></span> <span data-ttu-id="87d11-258">这意味着 Daniela 无法在 Amanda 的会议中打开视频。</span><span class="sxs-lookup"><span data-stu-id="87d11-258">This means Daniela can't turn on video in Amanda's meetings.</span></span>  

<span data-ttu-id="87d11-259">如果 Daniela 通过视频 Amanda 调用，Amanda 只能通过音频应答呼叫。</span><span class="sxs-lookup"><span data-stu-id="87d11-259">If Daniela calls Amanda with video on, Amanda can answer the call with audio only.</span></span>  <span data-ttu-id="87d11-260">当呼叫连接时，Amanda 可以看到 Daniela 的视频，但无法打开视频。</span><span class="sxs-lookup"><span data-stu-id="87d11-260">When the call is connected, Amanda can see Daniela's video, but can't turn on video.</span></span> <span data-ttu-id="87d11-261">如果 Amanda 呼叫 Daniela，Daniela 可以通过视频和音频接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="87d11-261">If Amanda calls Daniela, Daniela can answer the call with video and audio.</span></span> <span data-ttu-id="87d11-262">通话接通后，Daniela 可以根据需要打开或关闭她的视频。</span><span class="sxs-lookup"><span data-stu-id="87d11-262">When the call is connected, Daniela can turn on or turn off her video, as needed.</span></span>

### <a name="media-bit-rate-kbs"></a><span data-ttu-id="87d11-263">媒体比特率（Kbs）</span><span class="sxs-lookup"><span data-stu-id="87d11-263">Media bit rate (Kbs)</span></span>

<span data-ttu-id="87d11-264">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="87d11-264">This is a per-user policy.</span></span> <span data-ttu-id="87d11-265">此设置确定用户的通话和会议中音频、视频和基于视频的应用共享传输的媒体比特率。</span><span class="sxs-lookup"><span data-stu-id="87d11-265">This setting determines the media bit rate for audio, video, and video-based app sharing transmissions in calls and meetings for the user.</span></span> <span data-ttu-id="87d11-266">它同时应用于呼叫或会议中用户的上行媒体和下行媒体遍历。</span><span class="sxs-lookup"><span data-stu-id="87d11-266">It's applied to both the uplink and downlink media traversal for users in the call or meeting.</span></span> <span data-ttu-id="87d11-267">此设置使你能够更细致地控制组织中的带宽管理。</span><span class="sxs-lookup"><span data-stu-id="87d11-267">This setting gives you granular control over managing bandwidth in your organization.</span></span> <span data-ttu-id="87d11-268">根据用户所需的会议方案，我们建议有足够的带宽来实现优质体验。</span><span class="sxs-lookup"><span data-stu-id="87d11-268">Depending on the meetings scenarios required by users, we recommend having enough bandwidth in place for a good quality experience.</span></span> <span data-ttu-id="87d11-269">最小值为 30 Kbps，最大值取决于会议方案。</span><span class="sxs-lookup"><span data-stu-id="87d11-269">The minimum value is 30 Kbps and the maximum value depends on the meeting scenario.</span></span> <span data-ttu-id="87d11-270">若要了解更多有关建议的最小带宽以供团队的优质会议、通话和实时活动，请参阅[带宽要求](prepare-network.md#bandwidth-requirements)。</span><span class="sxs-lookup"><span data-stu-id="87d11-270">To learn more about the minimum recommended bandwidth for good quality meetings, calls, and live events in Teams, see [Bandwidth requirements](prepare-network.md#bandwidth-requirements).</span></span>

<span data-ttu-id="87d11-271">如果会议带宽不足，参与者会看到指示网络质量不佳的消息。</span><span class="sxs-lookup"><span data-stu-id="87d11-271">If there isn't enough bandwidth for a meeting, participants see a message that indicates poor network quality.</span></span>

<span data-ttu-id="87d11-272">对于需要最高质量视频体验的会议（如 CEO 董事会会议和团队现场活动），我们建议您将带宽设置为 10 Mbps。</span><span class="sxs-lookup"><span data-stu-id="87d11-272">For meetings that need the highest quality video experience, such as CEO board meetings and Teams live events, we recommend you set the bandwidth to 10 Mbps.</span></span> <span data-ttu-id="87d11-273">即使设置了最大体验，团队媒体堆栈也会在检测到某些网络条件时适应低带宽条件，具体取决于方案。</span><span class="sxs-lookup"><span data-stu-id="87d11-273">Even when the maximum experience is set, the Teams media stack adapts to low bandwidth conditions when certain network conditions are detected, depending on the scenario.</span></span> 

## <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="87d11-274">会议策略设置-内容共享</span><span class="sxs-lookup"><span data-stu-id="87d11-274">Meeting policy settings - Content sharing</span></span>

- [<span data-ttu-id="87d11-275">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="87d11-275">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="87d11-276">允许参与者授予或请求控制</span><span class="sxs-lookup"><span data-stu-id="87d11-276">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="87d11-277">允许外部参与者授予或请求控制</span><span class="sxs-lookup"><span data-stu-id="87d11-277">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="87d11-278">允许 PowerPoint 共享</span><span class="sxs-lookup"><span data-stu-id="87d11-278">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="87d11-279">允许白板</span><span class="sxs-lookup"><span data-stu-id="87d11-279">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="87d11-280">允许共享笔记</span><span class="sxs-lookup"><span data-stu-id="87d11-280">Allow shared notes</span></span>](#allow-shared-notes)

### <a name="screen-sharing-mode"></a><span data-ttu-id="87d11-281">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="87d11-281">Screen sharing mode</span></span>

<span data-ttu-id="87d11-282">这是每个组织单位和每用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="87d11-282">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="87d11-283">此设置控制是否允许在用户的会议中共享桌面和/或窗口共享。</span><span class="sxs-lookup"><span data-stu-id="87d11-283">This setting controls whether desktop and/or window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="87d11-284">未分配任何策略的会议参与者（如匿名、来宾、B2B 和联盟参与者）将继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="87d11-284">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="87d11-285">设置值</span><span class="sxs-lookup"><span data-stu-id="87d11-285">Setting value</span></span> |<span data-ttu-id="87d11-286">行为</span><span class="sxs-lookup"><span data-stu-id="87d11-286">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="87d11-287">**整个屏幕**</span><span class="sxs-lookup"><span data-stu-id="87d11-287">**Entire screen**</span></span>    | <span data-ttu-id="87d11-288">会议中允许进行完整的桌面共享和应用程序共享</span><span class="sxs-lookup"><span data-stu-id="87d11-288">Full desktop sharing and application sharing is allowed in the meeting</span></span> |
|<span data-ttu-id="87d11-289">**单应用程序**</span><span class="sxs-lookup"><span data-stu-id="87d11-289">**Single application**</span></span>   | <span data-ttu-id="87d11-290">允许在会议中共享应用程序</span><span class="sxs-lookup"><span data-stu-id="87d11-290">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="87d11-291">**已禁用**</span><span class="sxs-lookup"><span data-stu-id="87d11-291">**Disabled**</span></span>     |<span data-ttu-id="87d11-292">会议中已关闭屏幕共享和应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="87d11-292">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="87d11-293">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="87d11-293">Let's look at the following example.</span></span>

|<span data-ttu-id="87d11-294">用户</span><span class="sxs-lookup"><span data-stu-id="87d11-294">User</span></span> |<span data-ttu-id="87d11-295">会议策略</span><span class="sxs-lookup"><span data-stu-id="87d11-295">Meeting policy</span></span> |<span data-ttu-id="87d11-296">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="87d11-296">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="87d11-297">Daniela</span><span class="sxs-lookup"><span data-stu-id="87d11-297">Daniela</span></span>  | <span data-ttu-id="87d11-298">全局</span><span class="sxs-lookup"><span data-stu-id="87d11-298">Global</span></span>   | <span data-ttu-id="87d11-299">整个屏幕</span><span class="sxs-lookup"><span data-stu-id="87d11-299">Entire screen</span></span> |
|<span data-ttu-id="87d11-300">Amanda</span><span class="sxs-lookup"><span data-stu-id="87d11-300">Amanda</span></span>   | <span data-ttu-id="87d11-301">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="87d11-301">Location1MeetingPolicy</span></span>  | <span data-ttu-id="87d11-302">已禁用</span><span class="sxs-lookup"><span data-stu-id="87d11-302">Disabled</span></span> |

<span data-ttu-id="87d11-303">由 Daniela 托管的会议允许会议参与者共享其整个屏幕或特定应用程序。</span><span class="sxs-lookup"><span data-stu-id="87d11-303">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="87d11-304">如果 Amanda 加入 Daniela 的会议，Amanda 无法共享她的屏幕或特定应用程序，因为她的策略设置已被禁用。</span><span class="sxs-lookup"><span data-stu-id="87d11-304">If Amanda joins Daniela's meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="87d11-305">在 Amanda 托管的会议中，不允许任何人共享其屏幕或单个应用程序，而不管分配给他们的屏幕共享模式策略如何。</span><span class="sxs-lookup"><span data-stu-id="87d11-305">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span> <span data-ttu-id="87d11-306">这意味着 Daniela 不能在 Amanda 的会议中共享她的屏幕或单个应用程序。</span><span class="sxs-lookup"><span data-stu-id="87d11-306">This means that Daniela can't share her screen or a single application in Amanda's meetings.</span></span>  

<span data-ttu-id="87d11-307">当前，如果用户使用的是 Google Chrome，则用户无法在团队会议中播放视频或共享其屏幕。</span><span class="sxs-lookup"><span data-stu-id="87d11-307">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

### <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="87d11-308">允许参与者授予或请求控制</span><span class="sxs-lookup"><span data-stu-id="87d11-308">Allow a participant to give or request control</span></span>

<span data-ttu-id="87d11-309">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="87d11-309">This is a per-user policy.</span></span> <span data-ttu-id="87d11-310">此设置控制用户是否可以将共享桌面或窗口的控制权授予其他会议参与者。</span><span class="sxs-lookup"><span data-stu-id="87d11-310">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="87d11-311">若要赋予控制权，请将鼠标悬停在屏幕顶部。</span><span class="sxs-lookup"><span data-stu-id="87d11-311">To give control, hover over the top of the screen.</span></span> 

<span data-ttu-id="87d11-312">如果为用户启用此设置，则 "**授予控制权**" 选项显示在共享会话的顶部栏中。</span><span class="sxs-lookup"><span data-stu-id="87d11-312">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span> 

![显示 "提供控制" 选项的屏幕截图](media/meeting-policies-give-control.png)

<span data-ttu-id="87d11-314">如果用户的设置处于关闭状态，则 "**提供控制**" 选项不可用。</span><span class="sxs-lookup"><span data-stu-id="87d11-314">If the settings is turned off for the user, the **Give Control** option isn't available.</span></span>

![显示 "提供控件" 选项不可用的屏幕截图](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="87d11-316">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="87d11-316">Let's look at the following example.</span></span>

|<span data-ttu-id="87d11-317">用户</span><span class="sxs-lookup"><span data-stu-id="87d11-317">User</span></span> |<span data-ttu-id="87d11-318">会议策略</span><span class="sxs-lookup"><span data-stu-id="87d11-318">Meeting policy</span></span>  |<span data-ttu-id="87d11-319">允许参与者授予或请求控制</span><span class="sxs-lookup"><span data-stu-id="87d11-319">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="87d11-320">Daniela</span><span class="sxs-lookup"><span data-stu-id="87d11-320">Daniela</span></span>   | <span data-ttu-id="87d11-321">全局</span><span class="sxs-lookup"><span data-stu-id="87d11-321">Global</span></span>   | <span data-ttu-id="87d11-322">True</span><span class="sxs-lookup"><span data-stu-id="87d11-322">True</span></span>       |
|<span data-ttu-id="87d11-323">Babek</span><span class="sxs-lookup"><span data-stu-id="87d11-323">Babek</span></span>    | <span data-ttu-id="87d11-324">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="87d11-324">Location1MeetingPolicy</span></span>        | <span data-ttu-id="87d11-325">False</span><span class="sxs-lookup"><span data-stu-id="87d11-325">False</span></span>   |

<span data-ttu-id="87d11-326">Daniela 可以将共享桌面或窗口的控制权交给 Babek 组织的会议中的其他参与者，Babek 无法将控制权授予其他参与者。</span><span class="sxs-lookup"><span data-stu-id="87d11-326">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek whereas Babek can't give control to other participants.</span></span>

<span data-ttu-id="87d11-327">若要使用 PowerShell 控制哪些人可以授予控制请求或接受控制请求，请使用 AllowParticipantGiveRequestControl cmdlet。</span><span class="sxs-lookup"><span data-stu-id="87d11-327">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="87d11-328">若要在共享期间提供和控制共享内容，双方都必须使用团队桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="87d11-328">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="87d11-329">如果任何一方在浏览器中运行 Teams，则不支持控制。</span><span class="sxs-lookup"><span data-stu-id="87d11-329">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="87d11-330">这是由我们计划修复的一个技术限制造成。</span><span class="sxs-lookup"><span data-stu-id="87d11-330">This is due to a technical limitation that we're planning to fix.</span></span> 

### <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="87d11-331">允许外部参与者授予或请求控制</span><span class="sxs-lookup"><span data-stu-id="87d11-331">Allow an external participant to give or request control</span></span>

<span data-ttu-id="87d11-332">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="87d11-332">This is a per-user policy.</span></span> <span data-ttu-id="87d11-333">此设置控制会议中的外部参与者是否可以将其共享桌面或窗口的控制权交给会议中的其他参与者。</span><span class="sxs-lookup"><span data-stu-id="87d11-333">This setting controls whether external participants in a meeting can give control of their shared desktop or window to other participants in the meeting.</span></span> <span data-ttu-id="87d11-334">团队会议中的外部参与者可以按如下方式进行分类：</span><span class="sxs-lookup"><span data-stu-id="87d11-334">External participants in Teams meetings can be categorized as follows:</span></span>  

- <span data-ttu-id="87d11-335">匿名用户</span><span class="sxs-lookup"><span data-stu-id="87d11-335">Anonymous user</span></span>
- <span data-ttu-id="87d11-336">来宾用户</span><span class="sxs-lookup"><span data-stu-id="87d11-336">Guest users</span></span>  
- <span data-ttu-id="87d11-337">B2B 用户</span><span class="sxs-lookup"><span data-stu-id="87d11-337">B2B user</span></span>
- <span data-ttu-id="87d11-338">联合用户</span><span class="sxs-lookup"><span data-stu-id="87d11-338">Federated user</span></span>  

<span data-ttu-id="87d11-339">联盟用户是否可以向外部用户授予控制权，同时共享受允许外部参与者在其组织中**授予或请求控制**设置的控制。</span><span class="sxs-lookup"><span data-stu-id="87d11-339">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="87d11-340">若要使用 PowerShell 控制外部参与者是否可以授予控制或接受控制请求，请使用 AllowExternalParticipantGiveRequestControl cmdlet。</span><span class="sxs-lookup"><span data-stu-id="87d11-340">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="87d11-341">允许 PowerPoint 共享</span><span class="sxs-lookup"><span data-stu-id="87d11-341">Allow PowerPoint sharing</span></span>

<span data-ttu-id="87d11-342">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="87d11-342">This is a per-user policy.</span></span> <span data-ttu-id="87d11-343">此设置控制用户是否可以在会议中共享 PowerPoint 幻灯片放映。</span><span class="sxs-lookup"><span data-stu-id="87d11-343">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="87d11-344">外部用户（包括匿名用户、来宾和联盟用户）继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="87d11-344">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="87d11-345">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="87d11-345">Let's look at the following example.</span></span>

|<span data-ttu-id="87d11-346">用户</span><span class="sxs-lookup"><span data-stu-id="87d11-346">User</span></span> |<span data-ttu-id="87d11-347">会议策略</span><span class="sxs-lookup"><span data-stu-id="87d11-347">Meeting policy</span></span>  |<span data-ttu-id="87d11-348">允许 PowerPoint 共享</span><span class="sxs-lookup"><span data-stu-id="87d11-348">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="87d11-349">Daniela</span><span class="sxs-lookup"><span data-stu-id="87d11-349">Daniela</span></span>   | <span data-ttu-id="87d11-350">全局</span><span class="sxs-lookup"><span data-stu-id="87d11-350">Global</span></span>   | <span data-ttu-id="87d11-351">True</span><span class="sxs-lookup"><span data-stu-id="87d11-351">True</span></span>       |
|<span data-ttu-id="87d11-352">Amanda</span><span class="sxs-lookup"><span data-stu-id="87d11-352">Amanda</span></span>   | <span data-ttu-id="87d11-353">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="87d11-353">Location1MeetingPolicy</span></span>        | <span data-ttu-id="87d11-354">False</span><span class="sxs-lookup"><span data-stu-id="87d11-354">False</span></span>   |

<span data-ttu-id="87d11-355">Amanda 不能在会议中共享 PowerPoint 幻灯片卡座，即使她是会议组织者也是如此。</span><span class="sxs-lookup"><span data-stu-id="87d11-355">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="87d11-356">Daniela 可以共享 PowerPoint 幻灯片放映，即使会议由 Amanda 组织。</span><span class="sxs-lookup"><span data-stu-id="87d11-356">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="87d11-357">Amanda 可以查看会议中其他人共享的 PowerPoint 幻灯片卡座，即使她无法共享 PowerPoint 幻灯片放映。</span><span class="sxs-lookup"><span data-stu-id="87d11-357">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

### <a name="allow-whiteboard"></a><span data-ttu-id="87d11-358">允许白板</span><span class="sxs-lookup"><span data-stu-id="87d11-358">Allow whiteboard</span></span>

<span data-ttu-id="87d11-359">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="87d11-359">This is a per-user policy.</span></span> <span data-ttu-id="87d11-360">此设置控制用户是否可以在会议中共享白板。</span><span class="sxs-lookup"><span data-stu-id="87d11-360">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="87d11-361">外部用户（包括匿名用户、B2B 和联盟用户）继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="87d11-361">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> 

<span data-ttu-id="87d11-362">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="87d11-362">Let's look at the following example.</span></span>

|<span data-ttu-id="87d11-363">用户</span><span class="sxs-lookup"><span data-stu-id="87d11-363">User</span></span> |<span data-ttu-id="87d11-364">会议策略</span><span class="sxs-lookup"><span data-stu-id="87d11-364">Meeting policy</span></span>  |<span data-ttu-id="87d11-365">允许白板</span><span class="sxs-lookup"><span data-stu-id="87d11-365">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="87d11-366">Daniela</span><span class="sxs-lookup"><span data-stu-id="87d11-366">Daniela</span></span>   | <span data-ttu-id="87d11-367">全局</span><span class="sxs-lookup"><span data-stu-id="87d11-367">Global</span></span>   | <span data-ttu-id="87d11-368">True</span><span class="sxs-lookup"><span data-stu-id="87d11-368">True</span></span>       |
|<span data-ttu-id="87d11-369">Amanda</span><span class="sxs-lookup"><span data-stu-id="87d11-369">Amanda</span></span>   | <span data-ttu-id="87d11-370">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="87d11-370">Location1MeetingPolicy</span></span>        | <span data-ttu-id="87d11-371">False</span><span class="sxs-lookup"><span data-stu-id="87d11-371">False</span></span>   |

<span data-ttu-id="87d11-372">Amanda 无法在会议中共享白板，即使她是会议组织者也是如此。</span><span class="sxs-lookup"><span data-stu-id="87d11-372">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="87d11-373">即使会议是按 Amanda 组织的，Daniela 也可以共享白板。</span><span class="sxs-lookup"><span data-stu-id="87d11-373">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

### <a name="allow-shared-notes"></a><span data-ttu-id="87d11-374">允许共享笔记</span><span class="sxs-lookup"><span data-stu-id="87d11-374">Allow shared notes</span></span>

<span data-ttu-id="87d11-375">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="87d11-375">This is a per-user policy.</span></span> <span data-ttu-id="87d11-376">此设置控制用户是否可以在会议中创建和共享笔记。</span><span class="sxs-lookup"><span data-stu-id="87d11-376">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="87d11-377">外部用户（包括匿名用户、B2B 和联盟用户）继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="87d11-377">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="87d11-378">"**会议笔记**" 选项卡目前仅在具有少于20个参与者的会议中受支持。</span><span class="sxs-lookup"><span data-stu-id="87d11-378">The **Meeting Notes** tab is currently only supported in meetings that have less than 20 participants.</span></span>

<span data-ttu-id="87d11-379">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="87d11-379">Let's look at the following example.</span></span>

|<span data-ttu-id="87d11-380">用户</span><span class="sxs-lookup"><span data-stu-id="87d11-380">User</span></span> |<span data-ttu-id="87d11-381">会议策略</span><span class="sxs-lookup"><span data-stu-id="87d11-381">Meeting policy</span></span>  |<span data-ttu-id="87d11-382">允许共享笔记</span><span class="sxs-lookup"><span data-stu-id="87d11-382">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="87d11-383">Daniela</span><span class="sxs-lookup"><span data-stu-id="87d11-383">Daniela</span></span>   | <span data-ttu-id="87d11-384">全局</span><span class="sxs-lookup"><span data-stu-id="87d11-384">Global</span></span>   | <span data-ttu-id="87d11-385">True</span><span class="sxs-lookup"><span data-stu-id="87d11-385">True</span></span>       |
|<span data-ttu-id="87d11-386">Amanda</span><span class="sxs-lookup"><span data-stu-id="87d11-386">Amanda</span></span>   | <span data-ttu-id="87d11-387">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="87d11-387">Location1MeetingPolicy</span></span> | <span data-ttu-id="87d11-388">False</span><span class="sxs-lookup"><span data-stu-id="87d11-388">False</span></span> |

<span data-ttu-id="87d11-389">Daniela 可以在 Amanda 的会议中做笔记，Amanda 不能在任何会议中做笔记。</span><span class="sxs-lookup"><span data-stu-id="87d11-389">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>

## <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="87d11-390">会议策略设置-参与者 & 来宾</span><span class="sxs-lookup"><span data-stu-id="87d11-390">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="87d11-391">这些设置控制在会议厅中等待的会议参与者，以及他们在会议中允许的参与级别。</span><span class="sxs-lookup"><span data-stu-id="87d11-391">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="87d11-392">让匿名人员开始会议</span><span class="sxs-lookup"><span data-stu-id="87d11-392">Let anonymous people start a meeting</span></span>](#let-anonymous-people-start-a-meeting)
- [<span data-ttu-id="87d11-393">自动允许人员</span><span class="sxs-lookup"><span data-stu-id="87d11-393">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="87d11-394">允许拨入用户绕过大厅</span><span class="sxs-lookup"><span data-stu-id="87d11-394">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby)
- [<span data-ttu-id="87d11-395">启用实时字幕</span><span class="sxs-lookup"><span data-stu-id="87d11-395">Enable live captions </span></span>](#enable-live-captions)
- [<span data-ttu-id="87d11-396">允许在会议中聊天</span><span class="sxs-lookup"><span data-stu-id="87d11-396">Allow chat in meetings </span></span>](#allow-chat-in-meetings)

> [!NOTE]
><span data-ttu-id="87d11-397">用于加入会议的选项会有所不同，具体取决于每个团队组的设置和连接方法。</span><span class="sxs-lookup"><span data-stu-id="87d11-397">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="87d11-398">如果你的组具有音频会议，并使用它进行连接，请参阅[Office 365 中的音频会议](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="87d11-398">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing in Office 365](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="87d11-399">如果你的团队组没有音频会议，请参阅[在团队中加入会议](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)。</span><span class="sxs-lookup"><span data-stu-id="87d11-399">If your Teams group does not have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

### <a name="let-anonymous-people-start-a-meeting"></a><span data-ttu-id="87d11-400">让匿名人员开始会议</span><span class="sxs-lookup"><span data-stu-id="87d11-400">Let anonymous people start a meeting</span></span>

<span data-ttu-id="87d11-401">这是每个组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="87d11-401">This is a per-organizer policy.</span></span> <span data-ttu-id="87d11-402">此设置控制匿名人员（包括 B2B）和联盟用户是否可以在没有经过身份验证的组织中加入用户的会议。</span><span class="sxs-lookup"><span data-stu-id="87d11-402">This setting controls whether anonymous people, including B2B, and federated users, can join the user's meeting without an authenticated user from the organization in attendance.</span></span> 

![显示一条消息给正在等待的用户的屏幕截图](media/meeting-policies-anonymous-user-lobby.png)

<span data-ttu-id="87d11-404">下面是在会议中提供了身份验证用户时匿名用户的加入行为。</span><span class="sxs-lookup"><span data-stu-id="87d11-404">Here's the join behavior of anonymous people when authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="87d11-405">让匿名人员开始会议</span><span class="sxs-lookup"><span data-stu-id="87d11-405">Let anonymous people start a meeting</span></span>  |<span data-ttu-id="87d11-406">自动允许人员</span><span class="sxs-lookup"><span data-stu-id="87d11-406">Automatically admit people</span></span> |<span data-ttu-id="87d11-407">匿名人员的加入行为</span><span class="sxs-lookup"><span data-stu-id="87d11-407">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="87d11-408">True</span><span class="sxs-lookup"><span data-stu-id="87d11-408">True</span></span>    | <span data-ttu-id="87d11-409">所有人</span><span class="sxs-lookup"><span data-stu-id="87d11-409">Everyone</span></span>      | <span data-ttu-id="87d11-410">直接加入</span><span class="sxs-lookup"><span data-stu-id="87d11-410">Join directly</span></span>         |
|   | <span data-ttu-id="87d11-411">您的组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="87d11-411">Everyone in your organization</span></span>       | <span data-ttu-id="87d11-412">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="87d11-412">Wait in lobby</span></span>        |
|   | <span data-ttu-id="87d11-413">组织和联盟组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="87d11-413">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="87d11-414">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="87d11-414">Wait in lobby</span></span>         |
|<span data-ttu-id="87d11-415">False</span><span class="sxs-lookup"><span data-stu-id="87d11-415">False</span></span>    | <span data-ttu-id="87d11-416">所有人</span><span class="sxs-lookup"><span data-stu-id="87d11-416">Everyone</span></span>        | <span data-ttu-id="87d11-417">直接加入</span><span class="sxs-lookup"><span data-stu-id="87d11-417">Join directly</span></span>        |
|   | <span data-ttu-id="87d11-418">您的组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="87d11-418">Everyone in your organization</span></span>     | <span data-ttu-id="87d11-419">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="87d11-419">Wait in lobby</span></span>        |
|   | <span data-ttu-id="87d11-420">组织和联盟组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="87d11-420">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="87d11-421">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="87d11-421">Wait in lobby</span></span>         |

<span data-ttu-id="87d11-422">下面是当会议中没有经过身份验证的用户时匿名用户的加入行为。</span><span class="sxs-lookup"><span data-stu-id="87d11-422">Here's the join behavior of anonymous people when no authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="87d11-423">让匿名人员开始会议</span><span class="sxs-lookup"><span data-stu-id="87d11-423">Let anonymous people start a meeting</span></span> |<span data-ttu-id="87d11-424">自动允许人员</span><span class="sxs-lookup"><span data-stu-id="87d11-424">Automatically admit people</span></span>  |<span data-ttu-id="87d11-425">匿名人员的加入行为</span><span class="sxs-lookup"><span data-stu-id="87d11-425">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="87d11-426">True</span><span class="sxs-lookup"><span data-stu-id="87d11-426">True</span></span>    | <span data-ttu-id="87d11-427">所有人</span><span class="sxs-lookup"><span data-stu-id="87d11-427">Everyone</span></span>      | <span data-ttu-id="87d11-428">直接加入</span><span class="sxs-lookup"><span data-stu-id="87d11-428">Join directly</span></span>         |
|   | <span data-ttu-id="87d11-429">您的组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="87d11-429">Everyone in your organization</span></span>       | <span data-ttu-id="87d11-430">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="87d11-430">Wait in lobby</span></span>        |
|   | <span data-ttu-id="87d11-431">组织和联盟组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="87d11-431">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="87d11-432">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="87d11-432">Wait in lobby</span></span>         |
|<span data-ttu-id="87d11-433">False</span><span class="sxs-lookup"><span data-stu-id="87d11-433">False</span></span>    | <span data-ttu-id="87d11-434">所有人</span><span class="sxs-lookup"><span data-stu-id="87d11-434">Everyone</span></span>        | <span data-ttu-id="87d11-435">在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="87d11-435">Wait in lobby.</span></span> <span data-ttu-id="87d11-436">当第一个经过身份验证的用户加入会议时，将自动向用户提供许可。</span><span class="sxs-lookup"><span data-stu-id="87d11-436">Users are automatically admitted when the first authenticated user joins the meeting.</span></span>        |
|   | <span data-ttu-id="87d11-437">您的组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="87d11-437">Everyone in your organization</span></span>     |<span data-ttu-id="87d11-438">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="87d11-438">Wait in lobby</span></span>         |
|   | <span data-ttu-id="87d11-439">组织和联盟组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="87d11-439">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="87d11-440">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="87d11-440">Wait in lobby</span></span>         |

### <a name="automatically-admit-people"></a><span data-ttu-id="87d11-441">自动允许人员</span><span class="sxs-lookup"><span data-stu-id="87d11-441">Automatically admit people</span></span>

<span data-ttu-id="87d11-442">这是每个组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="87d11-442">This is a per-organizer policy.</span></span> <span data-ttu-id="87d11-443">此设置控制用户是否直接加入会议或在大厅中等待，直到他们被经过身份验证的用户许可。</span><span class="sxs-lookup"><span data-stu-id="87d11-443">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span>

![显示会议厅中有用户的会议的屏幕截图](media/meeting-policies-lobby.png)

 <span data-ttu-id="87d11-445">会议组织者可以单击会议邀请中的 "**会议选项**"，为其计划的每个会议更改此设置。</span><span class="sxs-lookup"><span data-stu-id="87d11-445">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span>
  
|<span data-ttu-id="87d11-446">设置值</span><span class="sxs-lookup"><span data-stu-id="87d11-446">Setting value</span></span>  |<span data-ttu-id="87d11-447">联接行为</span><span class="sxs-lookup"><span data-stu-id="87d11-447">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="87d11-448">**所有人**</span><span class="sxs-lookup"><span data-stu-id="87d11-448">**Everyone**</span></span>   |<span data-ttu-id="87d11-449">所有会议参与者都直接加入会议，而无需在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="87d11-449">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="87d11-450">这包括经过身份验证的用户、联盟用户、来宾、匿名用户和通过电话拨入的用户。</span><span class="sxs-lookup"><span data-stu-id="87d11-450">This includes authenticated users, federated users, guests, anonymous users, and people who dial in by phone.</span></span>       |
|<span data-ttu-id="87d11-451">**组织和联盟组织中的每个人**</span><span class="sxs-lookup"><span data-stu-id="87d11-451">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="87d11-452">组织内的经过身份验证的用户，包括来宾用户和联盟组织中的用户，直接加入会议，而无需在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="87d11-452">Authenticated users within the organization, including guest users and the users from federated organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="87d11-453">通过电话拨入的匿名用户和用户在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="87d11-453">Anonymous users and users who dial in by phone wait in the lobby.</span></span>   |
|<span data-ttu-id="87d11-454">**您的组织中的每个人**</span><span class="sxs-lookup"><span data-stu-id="87d11-454">**Everyone in your organization**</span></span>    |<span data-ttu-id="87d11-455">来自组织内部的经过身份验证的用户（包括来宾用户）直接加入会议，而无需在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="87d11-455">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="87d11-456">联合用户、匿名用户和通过电话拨入的用户在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="87d11-456">Federated users, anonymous users, and users who dial in by phone wait in the lobby.</span></span>           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a><span data-ttu-id="87d11-457">允许拨入用户绕过大厅</span><span class="sxs-lookup"><span data-stu-id="87d11-457">Allow dial-in users to bypass the lobby</span></span>

<span data-ttu-id="87d11-458">这是每个组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="87d11-458">This is a per-organizer policy.</span></span> <span data-ttu-id="87d11-459">此设置控制通过电话拨入的用户是否直接加入会议或在会议厅中等待，而不管 "是否**自动允许人员**" 设置。</span><span class="sxs-lookup"><span data-stu-id="87d11-459">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span>

<span data-ttu-id="87d11-460">下面是通过电话拨入的用户的加入行为。</span><span class="sxs-lookup"><span data-stu-id="87d11-460">Here's the join behavior of people who dial in by phone.</span></span>

|<span data-ttu-id="87d11-461">允许拨入用户绕过大厅</span><span class="sxs-lookup"><span data-stu-id="87d11-461">Allow dial-in users to bypass the lobby</span></span>  |<span data-ttu-id="87d11-462">自动允许人员</span><span class="sxs-lookup"><span data-stu-id="87d11-462">Automatically admit people</span></span>  |<span data-ttu-id="87d11-463">拨入的用户的加入行为</span><span class="sxs-lookup"><span data-stu-id="87d11-463">Join behavior of people who dial in</span></span> |
|---------|---------|---------|
|<span data-ttu-id="87d11-464">True</span><span class="sxs-lookup"><span data-stu-id="87d11-464">True</span></span>    | <span data-ttu-id="87d11-465">所有人</span><span class="sxs-lookup"><span data-stu-id="87d11-465">Everyone</span></span>      | <span data-ttu-id="87d11-466">直接加入</span><span class="sxs-lookup"><span data-stu-id="87d11-466">Join directly</span></span>         |
|   | <span data-ttu-id="87d11-467">您的组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="87d11-467">Everyone in your organization</span></span>       | <span data-ttu-id="87d11-468">直接加入</span><span class="sxs-lookup"><span data-stu-id="87d11-468">Join directly</span></span>        |
|   | <span data-ttu-id="87d11-469">组织和联盟组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="87d11-469">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="87d11-470">直接加入</span><span class="sxs-lookup"><span data-stu-id="87d11-470">Join directly</span></span>         |
|<span data-ttu-id="87d11-471">False</span><span class="sxs-lookup"><span data-stu-id="87d11-471">False</span></span>    | <span data-ttu-id="87d11-472">所有人</span><span class="sxs-lookup"><span data-stu-id="87d11-472">Everyone</span></span>        | <span data-ttu-id="87d11-473">直接加入</span><span class="sxs-lookup"><span data-stu-id="87d11-473">Join directly</span></span>        |
|   | <span data-ttu-id="87d11-474">您的组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="87d11-474">Everyone in your organization</span></span>     |<span data-ttu-id="87d11-475">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="87d11-475">Wait in lobby</span></span>         |
|   | <span data-ttu-id="87d11-476">组织和联盟组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="87d11-476">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="87d11-477">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="87d11-477">Wait in lobby</span></span>         |


### <a name="enable-live-captions"></a><span data-ttu-id="87d11-478">启用实时字幕</span><span class="sxs-lookup"><span data-stu-id="87d11-478">Enable live captions</span></span>

<span data-ttu-id="87d11-479">这是每用户策略，在会议期间应用。</span><span class="sxs-lookup"><span data-stu-id="87d11-479">This is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="87d11-480">此设置控制用户是否可以使用 "**打开实时标题**" 选项来打开和关闭用户出席的会议中的实时字幕。</span><span class="sxs-lookup"><span data-stu-id="87d11-480">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![显示 "打开实时字幕" 选项的屏幕截图](media/meeting-policies-live-captions.png)

|<span data-ttu-id="87d11-482">设置值</span><span class="sxs-lookup"><span data-stu-id="87d11-482">Setting value</span></span> |<span data-ttu-id="87d11-483">行为</span><span class="sxs-lookup"><span data-stu-id="87d11-483">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="87d11-484">**已禁用，但组织者可以替代**</span><span class="sxs-lookup"><span data-stu-id="87d11-484">**Disabled but the organizer can override**</span></span>     | <span data-ttu-id="87d11-485">会议期间不会为用户自动打开实时字幕。</span><span class="sxs-lookup"><span data-stu-id="87d11-485">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="87d11-486">用户可以在 "溢出（**...**）" 菜单中看到 "**打开实时标题**" 选项以将其打开。</span><span class="sxs-lookup"><span data-stu-id="87d11-486">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="87d11-487">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="87d11-487">This is the default setting.</span></span> |
|<span data-ttu-id="87d11-488">**已禁用**</span><span class="sxs-lookup"><span data-stu-id="87d11-488">**Disabled**</span></span>     | <span data-ttu-id="87d11-489">会议期间，用户已禁用实时字幕。</span><span class="sxs-lookup"><span data-stu-id="87d11-489">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="87d11-490">用户不能选择将其打开。</span><span class="sxs-lookup"><span data-stu-id="87d11-490">The user doesn't have the option to turn them on.</span></span>          |

<span data-ttu-id="87d11-491"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="87d11-491"><a name="bkcontentsharing"> </a></span></span>

### <a name="allow-chat-in-meetings"></a><span data-ttu-id="87d11-492">允许在会议中聊天</span><span class="sxs-lookup"><span data-stu-id="87d11-492">Allow chat in meetings</span></span>

<span data-ttu-id="87d11-493">这是每个组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="87d11-493">This is a per-organizer policy.</span></span> <span data-ttu-id="87d11-494">此设置控制是否允许在用户的会议中使用会议聊天。</span><span class="sxs-lookup"><span data-stu-id="87d11-494">This setting controls whether meeting chat is allowed in the user's meeting.</span></span>

<span data-ttu-id="87d11-495"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="87d11-495"><a name="bkparticipantsandguests"> </a></span></span>

## <a name="related-topics"></a><span data-ttu-id="87d11-496">相关主题</span><span class="sxs-lookup"><span data-stu-id="87d11-496">Related topics</span></span>

[<span data-ttu-id="87d11-497">团队中的消息传递策略</span><span class="sxs-lookup"><span data-stu-id="87d11-497">Messaging policies in Teams</span></span>](messaging-policies-in-teams.md)
