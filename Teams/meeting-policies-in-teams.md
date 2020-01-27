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
f1keywords:
- ms.teamsadmincenter.meetingpolicies.overview
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- ms.teamsadmincenter.meetingpolicies.contentsharing
- ms.teamsadmincenter.meetingpolicies.general
- ms.teamsadmincenter.meetingpolicies.participantandguests
description: 了解如何在团队中管理会议策略设置。
ms.openlocfilehash: 41d1bf8c68ef96f3a657113864c21a993dfc3826
ms.sourcegitcommit: a6e051c5c5c100dbf2ff3ca8fc7babc4415babf3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2020
ms.locfileid: "41554339"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="b88c9-103">管理团队中的会议策略</span><span class="sxs-lookup"><span data-stu-id="b88c9-103">Manage meeting policies in Teams</span></span>

::: zone target="docs"
<span data-ttu-id="b88c9-104">会议策略用于控制会议参与者对由您的组织中的用户安排的会议参与者可用的功能。</span><span class="sxs-lookup"><span data-stu-id="b88c9-104">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="b88c9-105">创建策略并进行更改后，您可以将用户分配到该策略。</span><span class="sxs-lookup"><span data-stu-id="b88c9-105">After you create a policy and make your changes, you can then assign users to the policy.</span></span> <span data-ttu-id="b88c9-106">可在 Microsoft 团队管理中心或通过[使用 PowerShell](teams-powershell-overview.md)管理会议策略。</span><span class="sxs-lookup"><span data-stu-id="b88c9-106">You manage meeting policies in the Microsoft Teams admin center or by [using PowerShell](teams-powershell-overview.md).</span></span>

<span data-ttu-id="b88c9-107">你可以通过以下方式实施策略，这会在会议开始之前、会议期间或会议后影响用户的会议体验。</span><span class="sxs-lookup"><span data-stu-id="b88c9-107">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="b88c9-108">实现类型</span><span class="sxs-lookup"><span data-stu-id="b88c9-108">Implementation type</span></span>  |<span data-ttu-id="b88c9-109">说明</span><span class="sxs-lookup"><span data-stu-id="b88c9-109">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="b88c9-110">每个组织者</span><span class="sxs-lookup"><span data-stu-id="b88c9-110">Per-organizer</span></span>    |<span data-ttu-id="b88c9-111">实施按组织者策略时，所有会议参与者都将继承组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="b88c9-111">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="b88c9-112">例如，**自动允许人员**为每个组织者策略，并控制用户是否直接加入会议，或在会议厅中等待分配了该策略的用户安排的会议。</span><span class="sxs-lookup"><span data-stu-id="b88c9-112">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="b88c9-113">每用户</span><span class="sxs-lookup"><span data-stu-id="b88c9-113">Per-user</span></span>    |<span data-ttu-id="b88c9-114">当你实现每用户策略时，仅应用每用户策略来限制组织者和/或会议参与者的某些功能。</span><span class="sxs-lookup"><span data-stu-id="b88c9-114">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="b88c9-115">例如，"**允许现在开会**" 是每用户策略。</span><span class="sxs-lookup"><span data-stu-id="b88c9-115">For example, **Allow Meet now** is a per-user policy.</span></span>     |
|<span data-ttu-id="b88c9-116">每个组织者和每用户</span><span class="sxs-lookup"><span data-stu-id="b88c9-116">Per-organizer and per-user</span></span>     |<span data-ttu-id="b88c9-117">当你实现每个组织单位和每用户策略的组合时，某些功能将根据其策略和组织者的策略来限制会议参与者。</span><span class="sxs-lookup"><span data-stu-id="b88c9-117">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="b88c9-118">例如，"**允许云录制**" 是基于每个组织者和每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="b88c9-118">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="b88c9-119">启用此设置可允许会议组织者和参与者开始和停止录制。</span><span class="sxs-lookup"><span data-stu-id="b88c9-119">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span> 

<span data-ttu-id="b88c9-120">默认情况下，将创建名为 Global 的策略（组织范围的默认设置）。</span><span class="sxs-lookup"><span data-stu-id="b88c9-120">By default, a policy named Global (org-wide default) is created.</span></span> <span data-ttu-id="b88c9-121">默认情况下，将为组织中的所有用户分配此会议策略。</span><span class="sxs-lookup"><span data-stu-id="b88c9-121">All users in your organization will be assigned this meeting policy by default.</span></span> <span data-ttu-id="b88c9-122">你可以更改此策略，也可以创建一个或多个自定义策略并向其分配用户。</span><span class="sxs-lookup"><span data-stu-id="b88c9-122">You can either make changes to this policy or create one or more custom policies and assign users to them.</span></span> <span data-ttu-id="b88c9-123">创建自定义策略时，你可以允许或阻止你的用户使用某些功能，然后将其分配给将对其应用设置的一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="b88c9-123">When you create a custom policy, you can allow or prevent certain features from being available to your users, and then assign it to one or more users who will have the settings applied to them.</span></span> 

## <a name="change-or-create-a-meeting-policy"></a><span data-ttu-id="b88c9-124">更改或创建会议策略</span><span class="sxs-lookup"><span data-stu-id="b88c9-124">Change or create a meeting policy</span></span>

<span data-ttu-id="b88c9-125">若要更改或创建会议策略，请转到 Microsoft 团队**管理中心 >** > "会议**策略**"。</span><span class="sxs-lookup"><span data-stu-id="b88c9-125">To change or create a meeting policy, go to the Microsoft Teams admin center > **Meetings** > **Meeting policies**.</span></span> <span data-ttu-id="b88c9-126">从列表中选择一个策略，或选择 "**新建策略**"。</span><span class="sxs-lookup"><span data-stu-id="b88c9-126">Select a policy from the list or select **New policy**.</span></span> <span data-ttu-id="b88c9-127">如果要创建新策略，请添加名称和说明。</span><span class="sxs-lookup"><span data-stu-id="b88c9-127">If you're creating a new policy, add a name and description.</span></span> <span data-ttu-id="b88c9-128">名称不能包含特殊字符，也不能超过64个字符。</span><span class="sxs-lookup"><span data-stu-id="b88c9-128">The name can't contain special characters or be longer than 64 characters.</span></span> <span data-ttu-id="b88c9-129">选择您的设置，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="b88c9-129">Choose your settings, and then select **Save**.</span></span>

<span data-ttu-id="b88c9-130">例如，假设你有一组用户，并且想要限制其会议所需的带宽量。</span><span class="sxs-lookup"><span data-stu-id="b88c9-130">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="b88c9-131">您将创建一个名为 "有限带宽" 的新自定义策略，并禁用以下设置：</span><span class="sxs-lookup"><span data-stu-id="b88c9-131">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="b88c9-132">在 "**音频 & 视频**：</span><span class="sxs-lookup"><span data-stu-id="b88c9-132">Under **Audio & video**:</span></span>
- <span data-ttu-id="b88c9-133">关闭云录制</span><span class="sxs-lookup"><span data-stu-id="b88c9-133">Turn off cloud recording</span></span>
- <span data-ttu-id="b88c9-134">关闭 "允许 IP 视频"</span><span class="sxs-lookup"><span data-stu-id="b88c9-134">Turn off Allow IP video</span></span>

<span data-ttu-id="b88c9-135">在 "**内容共享**" 下：</span><span class="sxs-lookup"><span data-stu-id="b88c9-135">Under **Content sharing**:</span></span>
- <span data-ttu-id="b88c9-136">禁用屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="b88c9-136">Disable screen sharing mode</span></span>
- <span data-ttu-id="b88c9-137">关闭白板</span><span class="sxs-lookup"><span data-stu-id="b88c9-137">Turn off whiteboard</span></span>
- <span data-ttu-id="b88c9-138">关闭共享笔记</span><span class="sxs-lookup"><span data-stu-id="b88c9-138">Turn off shared notes</span></span>

<span data-ttu-id="b88c9-139">然后向用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="b88c9-139">Then assign the policy to the users.</span></span>

> [!NOTE] 
> <span data-ttu-id="b88c9-140">一次只能向一个用户分配一个会议策略。</span><span class="sxs-lookup"><span data-stu-id="b88c9-140">A user can be assigned only one meeting policy at a time.</span></span> 

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="b88c9-141">向用户分配会议策略</span><span class="sxs-lookup"><span data-stu-id="b88c9-141">Assign a meeting policy to users</span></span>

<span data-ttu-id="b88c9-142">如果要将策略应用到一个用户，请在左侧导航窗格中选择 "**用户**"，然后单击用户的显示名称。</span><span class="sxs-lookup"><span data-stu-id="b88c9-142">If you're applying the policy to one user, select **Users** on the left navigation pane, and then click the user's display name.</span></span> <span data-ttu-id="b88c9-143">在用户的页面上，在 "**分配的策略**" 旁边，选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="b88c9-143">On the user's page, next to **Assigned policies**, select **Edit**.</span></span> <span data-ttu-id="b88c9-144">然后，在 "**编辑用户策略**" 窗格中的 "**会议策略**" 下，从下拉列表中选择 "会议策略"，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="b88c9-144">Then, in the **Edit user policies** pane, under **Meeting policy**, select the meeting policy from the drop-down list, and then select **Save**.</span></span> <span data-ttu-id="b88c9-145">您还可以从用户列表中分配策略。</span><span class="sxs-lookup"><span data-stu-id="b88c9-145">You can also assign policies from the list of users.</span></span> <span data-ttu-id="b88c9-146">若要执行此操作，请单击用户的显示名称左侧的用户选择用户。</span><span class="sxs-lookup"><span data-stu-id="b88c9-146">To do this, select the user by clicking to the left of the user's display name.</span></span> <span data-ttu-id="b88c9-147">选择 "**编辑设置**"。</span><span class="sxs-lookup"><span data-stu-id="b88c9-147">Select **Edit settings**.</span></span> <span data-ttu-id="b88c9-148">然后，在 "**编辑设置**" 窗格的 "**会议策略**" 下，从下拉列表中选择策略，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="b88c9-148">Then, on the **Edit settings** pane, under **Meeting policy**, select the policy from the drop-down list, and then select **Save**.</span></span> 
 
<span data-ttu-id="b88c9-149">如果要将策略应用于多个用户，请在左侧导航窗格中选择 "**用户**"，然后单击用户名左侧的 "**编辑设置**"，选择每个用户。</span><span class="sxs-lookup"><span data-stu-id="b88c9-149">If you're applying a policy to more than one user, select **Users** on the left navigation pane, and then select each user by clicking to the left of the user name, and then click **Edit settings**.</span></span> <span data-ttu-id="b88c9-150">在 "**编辑设置**" 窗格的 "**会议策略**" 下，从下拉列表中选择策略，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="b88c9-150">On the **Edit Settings** pane, under **Meeting policy**, select the policy from the drop-down list, and then select **Save**.</span></span>
 
<span data-ttu-id="b88c9-151">您还可以将会议策略分配给一个或多个用户，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b88c9-151">You can also assign a meeting policy to one or more users as follows:</span></span>

1. <span data-ttu-id="b88c9-152">转到**Microsoft 团队管理中心** > **会议** > **会议策略**。</span><span class="sxs-lookup"><span data-stu-id="b88c9-152">Go to **Microsoft Teams admin center** > **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="b88c9-153">通过单击策略名称的左侧，选择策略。</span><span class="sxs-lookup"><span data-stu-id="b88c9-153">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="b88c9-154">选择 "**管理用户**"。</span><span class="sxs-lookup"><span data-stu-id="b88c9-154">Select **Manage users**.</span></span>
4. <span data-ttu-id="b88c9-155">在 "**管理用户**" 窗格中，按 "显示名称" 或 "按用户名搜索用户"，选择名称，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="b88c9-155">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="b88c9-156">对要添加的每个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="b88c9-156">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="b88c9-157">添加完用户后，请选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="b88c9-157">When you're finished adding users, select **Save**.</span></span>
 
> [!NOTE] 
> <span data-ttu-id="b88c9-158">如果向用户分配了该策略，则不能删除该策略。</span><span class="sxs-lookup"><span data-stu-id="b88c9-158">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="b88c9-159">必须先为所有受影响的用户分配不同的策略，然后才能删除原始策略。</span><span class="sxs-lookup"><span data-stu-id="b88c9-159">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>
 
## <a name="meeting-policy-settings"></a><span data-ttu-id="b88c9-160">会议策略设置</span><span class="sxs-lookup"><span data-stu-id="b88c9-160">Meeting policy settings</span></span>

<span data-ttu-id="b88c9-161">在 "**会议策略**" 页面上选择现有策略或选择 "**新建策略**" 以添加新策略时，可以为以下项配置设置。</span><span class="sxs-lookup"><span data-stu-id="b88c9-161">When you select an existing policy on the **Meeting policies** page or select **New policy** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="b88c9-162">常规</span><span class="sxs-lookup"><span data-stu-id="b88c9-162">General</span></span>](#meeting-policy-settings---general)
- [<span data-ttu-id="b88c9-163">音频 & 视频</span><span class="sxs-lookup"><span data-stu-id="b88c9-163">Audio & video</span></span>](#meeting-policy-settings---audio--video)
- [<span data-ttu-id="b88c9-164">内容共享</span><span class="sxs-lookup"><span data-stu-id="b88c9-164">Content sharing</span></span>](#meeting-policy-settings---content-sharing)
- [<span data-ttu-id="b88c9-165">参与者 & 来宾</span><span class="sxs-lookup"><span data-stu-id="b88c9-165">Participants & guests</span></span>](#meeting-policy-settings---participants--guests)

::: zone-end 

<span data-ttu-id="b88c9-166"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="b88c9-166"></span></span>

## <a name="meeting-policy-settings---general"></a><span data-ttu-id="b88c9-167">会议策略设置-常规</span><span class="sxs-lookup"><span data-stu-id="b88c9-167">Meeting policy settings - General</span></span>

- [<span data-ttu-id="b88c9-168">允许在频道中立即开会</span><span class="sxs-lookup"><span data-stu-id="b88c9-168">Allow Meet now in channels</span></span>](#allow-meet-now-in-channels)
- [<span data-ttu-id="b88c9-169">允许私人开会立即开会</span><span class="sxs-lookup"><span data-stu-id="b88c9-169">Allow private Meet now</span></span>](#allow-private-meet-now)
- [<span data-ttu-id="b88c9-170">允许 Outlook 加载项</span><span class="sxs-lookup"><span data-stu-id="b88c9-170">Allow the Outlook add-in</span></span>](#allow-the-outlook-add-in)
- [<span data-ttu-id="b88c9-171">允许频道会议安排</span><span class="sxs-lookup"><span data-stu-id="b88c9-171">Allow channel meeting scheduling</span></span>](#allow-channel-meeting-scheduling)
- [<span data-ttu-id="b88c9-172">允许安排私人会议</span><span class="sxs-lookup"><span data-stu-id="b88c9-172">Allow scheduling private meetings</span></span>](#allow-scheduling-private-meetings)

### <a name="allow-meet-now-in-channels"></a><span data-ttu-id="b88c9-173">允许在频道中立即开会</span><span class="sxs-lookup"><span data-stu-id="b88c9-173">Allow Meet now in channels</span></span>

<span data-ttu-id="b88c9-174">这是每用户策略，在会议开始之前应用。</span><span class="sxs-lookup"><span data-stu-id="b88c9-174">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="b88c9-175">此设置控制用户是否可以在团队频道中启动临时会议。</span><span class="sxs-lookup"><span data-stu-id="b88c9-175">This setting controls whether a user can start an ad hoc meeting in a Teams channel.</span></span> <span data-ttu-id="b88c9-176">如果启用此操作，当用户在团队频道中发布消息时，用户可以单击 "撰写" 框下方的 "**立即开会**" 以在频道中启动临时会议。</span><span class="sxs-lookup"><span data-stu-id="b88c9-176">If you turn this on, when a user posts a message in a Teams channel, the user can click **Meet now** beneath the compose box to start an ad hoc meeting in the channel.</span></span>

![显示邮件下方的 "立即开会" 图标的屏幕截图](media/meeting-policies-meet-now.png)
### <a name="allow-private-meet-now"></a><span data-ttu-id="b88c9-178">允许私人开会立即开会</span><span class="sxs-lookup"><span data-stu-id="b88c9-178">Allow private Meet now</span></span>

<span data-ttu-id="b88c9-179">这是每用户策略，在会议开始之前应用。</span><span class="sxs-lookup"><span data-stu-id="b88c9-179">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="b88c9-180">此设置控制用户是否可以启动 ad hoc 私人会议。</span><span class="sxs-lookup"><span data-stu-id="b88c9-180">This setting controls whether a user can start an ad hoc private meeting.</span></span>  


### <a name="allow-the-outlook-add-in"></a><span data-ttu-id="b88c9-181">允许 Outlook 加载项</span><span class="sxs-lookup"><span data-stu-id="b88c9-181">Allow the Outlook add-in</span></span>

<span data-ttu-id="b88c9-182">这是每用户策略，在会议开始之前应用。</span><span class="sxs-lookup"><span data-stu-id="b88c9-182">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="b88c9-183">此设置控制是否可以从 Outlook （Windows、Mac、web 和手机）内安排团队会议。</span><span class="sxs-lookup"><span data-stu-id="b88c9-183">This setting controls whether Teams meetings can be scheduled from within Outlook (Windows, Mac, web, and mobile).</span></span>

![显示安排新会议的功能的屏幕截图](media/meeting-policies-outlook-add-in.png)

<span data-ttu-id="b88c9-185">如果关闭此功能，用户在 Outlook 中创建新会议时，无法安排团队会议。</span><span class="sxs-lookup"><span data-stu-id="b88c9-185">If you turn this off, users are unable to schedule Teams meetings when they create a new meeting in Outlook.</span></span> <span data-ttu-id="b88c9-186">例如，在 Windows 上的 Outlook 中，"**新建团队会议**" 选项不会显示在功能区中。</span><span class="sxs-lookup"><span data-stu-id="b88c9-186">For example, in Outlook on Windows, the **New Teams Meeting** option won't show up in the ribbon.</span></span>

### <a name="allow-channel-meeting-scheduling"></a><span data-ttu-id="b88c9-187">允许频道会议安排</span><span class="sxs-lookup"><span data-stu-id="b88c9-187">Allow channel meeting scheduling</span></span>

<span data-ttu-id="b88c9-188">这是每用户策略，在会议开始之前应用。</span><span class="sxs-lookup"><span data-stu-id="b88c9-188">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="b88c9-189">此设置控制用户是否可以在团队频道中安排会议。</span><span class="sxs-lookup"><span data-stu-id="b88c9-189">This setting controls whether users can schedule a meeting in a Teams channel.</span></span>  <span data-ttu-id="b88c9-190">如果关闭此功能，则当用户在团队频道中启动会议，并且为团队中的用户禁用 "**添加频道**" 选项时，"**安排会议**" 选项将不可用。</span><span class="sxs-lookup"><span data-stu-id="b88c9-190">If you turn this off, the **Schedule a meeting** option won't be available to the user when they start a meeting in a Teams channel and the **Add a channel** option is disabled for users in Teams.</span></span>

![显示团队中的 "安排会议" 选项的屏幕截图](media/meeting-policies-schedule-a-meeting.png)

![显示 "选择要开会的频道" 选项的屏幕截图](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a><span data-ttu-id="b88c9-193">允许安排私人会议</span><span class="sxs-lookup"><span data-stu-id="b88c9-193">Allow scheduling private meetings</span></span>

<span data-ttu-id="b88c9-194">这是每用户策略，在会议开始之前应用。</span><span class="sxs-lookup"><span data-stu-id="b88c9-194">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="b88c9-195">此设置控制用户是否可以在团队中安排私人会议。</span><span class="sxs-lookup"><span data-stu-id="b88c9-195">This setting controls whether users can schedule private meetings in Teams.</span></span> <span data-ttu-id="b88c9-196">当会议未发布到团队中的频道时，它是私有的。</span><span class="sxs-lookup"><span data-stu-id="b88c9-196">A meeting is private when it's not published to a channel in a team.</span></span>

<span data-ttu-id="b88c9-197">请注意，如果关闭 "**允许安排私人会议**" 和 "**允许频道会议计划**"，则会为团队中的用户禁用 "**添加必需与会者**" 和 "**添加频道**" 选项。</span><span class="sxs-lookup"><span data-stu-id="b88c9-197">Note that if you turn off **Allow scheduling private meetings** and **Allow channel meeting scheduling**,  the **Add required attendees** and **Add channel** options are disabled for users in Teams.</span></span>

<span data-ttu-id="b88c9-198"><a name="bkaudioandvideo"> </a></span><span class="sxs-lookup"><span data-stu-id="b88c9-198"></span></span>

## <a name="meeting-policy-settings---audio--video"></a><span data-ttu-id="b88c9-199">会议策略设置-音频 & 视频</span><span class="sxs-lookup"><span data-stu-id="b88c9-199">Meeting policy settings - Audio & video</span></span>

- [<span data-ttu-id="b88c9-200">允许脚本</span><span class="sxs-lookup"><span data-stu-id="b88c9-200">Allow transcription</span></span>](#allow-transcription)
- [<span data-ttu-id="b88c9-201">允许云录制</span><span class="sxs-lookup"><span data-stu-id="b88c9-201">Allow cloud recording</span></span>](#allow-cloud-recording)
- [<span data-ttu-id="b88c9-202">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="b88c9-202">Allow IP video</span></span>](#allow-ip-video)
- [<span data-ttu-id="b88c9-203">媒体比特率（KBs）</span><span class="sxs-lookup"><span data-stu-id="b88c9-203">Media bit rate (KBs)</span></span>](#media-bit-rate-kbs)

### <a name="allow-transcription"></a><span data-ttu-id="b88c9-204">允许脚本</span><span class="sxs-lookup"><span data-stu-id="b88c9-204">Allow transcription</span></span>

<span data-ttu-id="b88c9-205">这是每个组织单位和每用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="b88c9-205">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="b88c9-206">此设置控制播放会议录制期间是否提供字幕和脚本功能。</span><span class="sxs-lookup"><span data-stu-id="b88c9-206">This setting controls whether captions and transcription features are available during playback of meeting recordings.</span></span> <span data-ttu-id="b88c9-207">如果关闭此功能，在播放会议录制的过程中，"**搜索**" 和 **"抄送**" 选项将不可用。</span><span class="sxs-lookup"><span data-stu-id="b88c9-207">If you turn this off, the **Search** and **CC** options won't be available during playback of a meeting recording.</span></span> <span data-ttu-id="b88c9-208">启动录制的人员需要启用此设置，以便录制还包括脚本。</span><span class="sxs-lookup"><span data-stu-id="b88c9-208">The person who started the recording needs this setting turned on so that the recording also includes transcription.</span></span> 

<span data-ttu-id="b88c9-209">请注意，当前只有在团队中将语言设置为英语且在会议中朗读英语的用户才支持使用录制的会议。</span><span class="sxs-lookup"><span data-stu-id="b88c9-209">Note that transcription for recorded meetings is currently only supported for users who have the language in Teams set to English and when English is spoken in the meeting.</span></span>

![显示会议中的脚本选项的屏幕截图](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a><span data-ttu-id="b88c9-211">允许云录制</span><span class="sxs-lookup"><span data-stu-id="b88c9-211">Allow cloud recording</span></span>

<span data-ttu-id="b88c9-212">这是每个组织单位和每用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="b88c9-212">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="b88c9-213">此设置控制是否可以录制此用户的会议。</span><span class="sxs-lookup"><span data-stu-id="b88c9-213">This setting controls whether this user's meetings can be recorded.</span></span> <span data-ttu-id="b88c9-214">录制可以由会议组织者或其他会议参与者启动（如果为参与者启用了该策略设置，并且他们是来自同一组织的经过身份验证的用户）。</span><span class="sxs-lookup"><span data-stu-id="b88c9-214">The recording can be started by the meeting organizer or by another meeting participant if the policy setting is turned on for the participant and if they're an authenticated user from the same organization.</span></span>

<span data-ttu-id="b88c9-215">组织外部的人员（如联盟用户和匿名用户）无法启动录制。</span><span class="sxs-lookup"><span data-stu-id="b88c9-215">People outside your organization, such as federated and anonymous users, can't start the recording.</span></span> <span data-ttu-id="b88c9-216">来宾用户无法启动或停止录制。</span><span class="sxs-lookup"><span data-stu-id="b88c9-216">Guest users can't start or stop the recording.</span></span> 

![显示录制选项的屏幕截图](media/meeting-policies-recording.png)

<span data-ttu-id="b88c9-218">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="b88c9-218">Let's look at the following example.</span></span>

|<span data-ttu-id="b88c9-219">用户</span><span class="sxs-lookup"><span data-stu-id="b88c9-219">User</span></span> |<span data-ttu-id="b88c9-220">会议策略</span><span class="sxs-lookup"><span data-stu-id="b88c9-220">Meeting policy</span></span>  |<span data-ttu-id="b88c9-221">允许云录制</span><span class="sxs-lookup"><span data-stu-id="b88c9-221">Allow cloud recording</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b88c9-222">Daniela</span><span class="sxs-lookup"><span data-stu-id="b88c9-222">Daniela</span></span> | <span data-ttu-id="b88c9-223">全局</span><span class="sxs-lookup"><span data-stu-id="b88c9-223">Global</span></span>   | <span data-ttu-id="b88c9-224">False</span><span class="sxs-lookup"><span data-stu-id="b88c9-224">False</span></span> |
|<span data-ttu-id="b88c9-225">Amanda</span><span class="sxs-lookup"><span data-stu-id="b88c9-225">Amanda</span></span> | <span data-ttu-id="b88c9-226">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="b88c9-226">Location1MeetingPolicy</span></span> | <span data-ttu-id="b88c9-227">True</span><span class="sxs-lookup"><span data-stu-id="b88c9-227">True</span></span>|
|<span data-ttu-id="b88c9-228">John （外部用户）</span><span class="sxs-lookup"><span data-stu-id="b88c9-228">John (external user)</span></span> | <span data-ttu-id="b88c9-229">不适用</span><span class="sxs-lookup"><span data-stu-id="b88c9-229">Not applicable</span></span> | <span data-ttu-id="b88c9-230">不适用</span><span class="sxs-lookup"><span data-stu-id="b88c9-230">Not applicable</span></span>|

<span data-ttu-id="b88c9-231">按 Daniela 组织的会议无法录制，并且 Amanda 已启用策略设置，无法录制 Daniela 组织的会议。</span><span class="sxs-lookup"><span data-stu-id="b88c9-231">Meetings organized by Daniela can't be recorded and Amanda, who has the policy setting enabled, can't record meetings organized by Daniela.</span></span> <span data-ttu-id="b88c9-232">可记录由 Amanda 组织的会议，但 Daniela，他们已禁用策略设置，并且 John 是外部用户，无法录制 Amanda 组织的会议。</span><span class="sxs-lookup"><span data-stu-id="b88c9-232">Meetings organized by Amanda can be recorded, however,  Daniela, who has the policy setting disabled and John who is an external user, can't record meetings organized by Amanda.</span></span>

<span data-ttu-id="b88c9-233">若要了解有关云会议录制的详细信息，请参阅[团队云会议录制](cloud-recording.md)。</span><span class="sxs-lookup"><span data-stu-id="b88c9-233">To learn more about cloud meeting recording, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

### <a name="allow-ip-video"></a><span data-ttu-id="b88c9-234">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="b88c9-234">Allow IP video</span></span>

<span data-ttu-id="b88c9-235">这是每个组织单位和每用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="b88c9-235">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="b88c9-236">视频是会议的关键组件。</span><span class="sxs-lookup"><span data-stu-id="b88c9-236">Video is a key component to meetings.</span></span> <span data-ttu-id="b88c9-237">在某些组织中，管理员可能希望更好地控制哪些用户的会议有视频。</span><span class="sxs-lookup"><span data-stu-id="b88c9-237">In some organizations, admins might want more control over which users’ meetings have video.</span></span> <span data-ttu-id="b88c9-238">此设置控制是否可以在用户托管的会议中以及用户开始的1:1 呼叫和组通话中打开视频。</span><span class="sxs-lookup"><span data-stu-id="b88c9-238">This setting controls whether video can be turned on in meetings hosted by a user and in 1:1 calls and group calls started by a user.</span></span> <span data-ttu-id="b88c9-239">已启用此策略的用户组织的会议，如果会议参与者也启用了该策略，则会议参与者允许会议中的视频共享。</span><span class="sxs-lookup"><span data-stu-id="b88c9-239">Meetings organized by a user who has this policy enabled, allow video sharing in the meeting by the meeting participants, if the meeting participants also have the policy enabled.</span></span> <span data-ttu-id="b88c9-240">未分配任何策略的会议参与者（如匿名和联盟参与者）将继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="b88c9-240">Meeting participants who don't have any policies assigned (for example, anonymous and federated participants) inherit the policy of the meeting organizer.</span></span>

![显示带有音频和视频设置的会议的屏幕截图](media/meeting-policies-audio-video-settings.png)

<span data-ttu-id="b88c9-242">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="b88c9-242">Let's look at the following example.</span></span>

|<span data-ttu-id="b88c9-243">用户</span><span class="sxs-lookup"><span data-stu-id="b88c9-243">User</span></span> |<span data-ttu-id="b88c9-244">会议策略</span><span class="sxs-lookup"><span data-stu-id="b88c9-244">Meeting policy</span></span>  |<span data-ttu-id="b88c9-245">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="b88c9-245">Allow IP Video</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b88c9-246">Daniela</span><span class="sxs-lookup"><span data-stu-id="b88c9-246">Daniela</span></span>   | <span data-ttu-id="b88c9-247">全局</span><span class="sxs-lookup"><span data-stu-id="b88c9-247">Global</span></span>   | <span data-ttu-id="b88c9-248">True</span><span class="sxs-lookup"><span data-stu-id="b88c9-248">True</span></span>        |
|<span data-ttu-id="b88c9-249">Amanda</span><span class="sxs-lookup"><span data-stu-id="b88c9-249">Amanda</span></span>    | <span data-ttu-id="b88c9-250">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="b88c9-250">Location1MeetingPolicy</span></span>        | <span data-ttu-id="b88c9-251">False</span><span class="sxs-lookup"><span data-stu-id="b88c9-251">False</span></span>      |

<span data-ttu-id="b88c9-252">通过 Daniela 托管的会议允许打开视频。</span><span class="sxs-lookup"><span data-stu-id="b88c9-252">Meetings hosted by Daniela allow video to be turned on.</span></span> <span data-ttu-id="b88c9-253">Daniela 可以加入会议并打开视频。</span><span class="sxs-lookup"><span data-stu-id="b88c9-253">Daniela can join the meeting and turn on video.</span></span> <span data-ttu-id="b88c9-254">Amanda 无法在 Daniela 的会议中启用视频，因为 Amanda 的策略设置为 "不允许视频"。</span><span class="sxs-lookup"><span data-stu-id="b88c9-254">Amanda can't turn on video in Daniela's meeting because Amanda’s policy is set to not allow video.</span></span> <span data-ttu-id="b88c9-255">Amanda 可以查看会议中其他参与者共享的视频。</span><span class="sxs-lookup"><span data-stu-id="b88c9-255">Amanda can see videos shared by other participants in the meeting.</span></span>

<span data-ttu-id="b88c9-256">在 Amanda 托管的会议中，无论分配给他们的视频策略如何，任何人都无法打开视频。</span><span class="sxs-lookup"><span data-stu-id="b88c9-256">In meetings hosted by Amanda, no one can turn on video, regardless of the video policy assigned to them.</span></span> <span data-ttu-id="b88c9-257">这意味着 Daniela 无法在 Amanda 的会议中打开视频。</span><span class="sxs-lookup"><span data-stu-id="b88c9-257">This means Daniela can't turn on video in Amanda’s meetings.</span></span>  

<span data-ttu-id="b88c9-258">如果 Daniela 通过视频 Amanda 调用，Amanda 只能通过音频应答呼叫。</span><span class="sxs-lookup"><span data-stu-id="b88c9-258">If Daniela calls Amanda with video on, Amanda can answer the call with audio only.</span></span>  <span data-ttu-id="b88c9-259">当呼叫连接时，Amanda 可以看到 Daniela 的视频，但无法打开视频。</span><span class="sxs-lookup"><span data-stu-id="b88c9-259">When the call is connected, Amanda can see Daniela’s video, but can't turn on video.</span></span> <span data-ttu-id="b88c9-260">如果 Amanda 呼叫 Daniela，Daniela 可以通过视频和音频接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="b88c9-260">If Amanda calls Daniela, Daniela can answer the call with video and audio.</span></span> <span data-ttu-id="b88c9-261">通话接通后，Daniela 可以根据需要打开或关闭她的视频。</span><span class="sxs-lookup"><span data-stu-id="b88c9-261">When the call is connected, Daniela can turn on or turn off her video, as needed.</span></span>

### <a name="media-bit-rate-kbs"></a><span data-ttu-id="b88c9-262">媒体比特率（KBs）</span><span class="sxs-lookup"><span data-stu-id="b88c9-262">Media bit rate (KBs)</span></span>

<span data-ttu-id="b88c9-263">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="b88c9-263">This is a per-user policy.</span></span> <span data-ttu-id="b88c9-264">此设置确定用户的通话和会议中音频、视频和基于视频的应用共享传输的媒体比特率。</span><span class="sxs-lookup"><span data-stu-id="b88c9-264">This setting determines the media bit rate for audio, video, and video-based app sharing transmissions in calls and meetings for the user.</span></span> <span data-ttu-id="b88c9-265">它同时应用于呼叫或会议中用户的上行媒体和下行媒体遍历。</span><span class="sxs-lookup"><span data-stu-id="b88c9-265">It's applied to both the uplink and downlink media traversal for users in the call or meeting.</span></span> <span data-ttu-id="b88c9-266">此设置使你能够更细致地控制组织中的带宽管理。</span><span class="sxs-lookup"><span data-stu-id="b88c9-266">This setting gives you granular control over managing bandwidth in your organization.</span></span> <span data-ttu-id="b88c9-267">根据用户所需的会议方案，我们建议有足够的带宽来实现优质体验。</span><span class="sxs-lookup"><span data-stu-id="b88c9-267">Depending on the meetings scenarios required by users, we recommend having enough bandwidth in place for a good quality experience.</span></span> <span data-ttu-id="b88c9-268">最小值为 30 Kbps，最大值取决于会议方案。</span><span class="sxs-lookup"><span data-stu-id="b88c9-268">The minimum value is 30 Kbps and the maximum value depends on the meeting scenario.</span></span> <span data-ttu-id="b88c9-269">若要了解更多有关建议的最小带宽以供团队的优质会议、通话和实时活动，请参阅[带宽要求](prepare-network.md#bandwidth-requirements)。</span><span class="sxs-lookup"><span data-stu-id="b88c9-269">To learn more about the minimum recommended bandwidth for good quality meetings, calls, and live events in Teams, see [Bandwidth requirements](prepare-network.md#bandwidth-requirements).</span></span>

<span data-ttu-id="b88c9-270">如果会议带宽不足，参与者会看到指示网络质量不佳的消息。</span><span class="sxs-lookup"><span data-stu-id="b88c9-270">If there isn’t enough bandwidth for a meeting, participants see a message that indicates poor network quality.</span></span>

<span data-ttu-id="b88c9-271">对于需要最高质量视频体验的会议（如 CEO 董事会会议和团队现场活动），我们建议您将带宽设置为 10 Mbps。</span><span class="sxs-lookup"><span data-stu-id="b88c9-271">For meetings that need the highest quality video experience, such as CEO board meetings and Teams live events, we recommend you set the bandwidth to 10 Mbps.</span></span> <span data-ttu-id="b88c9-272">即使设置了最大体验，团队媒体堆栈也会在检测到某些网络条件时适应低带宽条件，具体取决于方案。</span><span class="sxs-lookup"><span data-stu-id="b88c9-272">Even when the maximum experience is set, the Teams media stack adapts to low bandwidth conditions when certain network conditions are detected, depending on the scenario.</span></span> 

## <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="b88c9-273">会议策略设置-内容共享</span><span class="sxs-lookup"><span data-stu-id="b88c9-273">Meeting policy settings - Content sharing</span></span>

- [<span data-ttu-id="b88c9-274">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="b88c9-274">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="b88c9-275">允许参与者授予或请求控制</span><span class="sxs-lookup"><span data-stu-id="b88c9-275">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="b88c9-276">允许外部参与者授予或请求控制</span><span class="sxs-lookup"><span data-stu-id="b88c9-276">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="b88c9-277">允许 PowerPoint 共享</span><span class="sxs-lookup"><span data-stu-id="b88c9-277">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="b88c9-278">允许白板</span><span class="sxs-lookup"><span data-stu-id="b88c9-278">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="b88c9-279">允许共享笔记</span><span class="sxs-lookup"><span data-stu-id="b88c9-279">Allow shared notes</span></span>](#allow-shared-notes)

### <a name="screen-sharing-mode"></a><span data-ttu-id="b88c9-280">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="b88c9-280">Screen sharing mode</span></span>

<span data-ttu-id="b88c9-281">这是每个组织单位和每用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="b88c9-281">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="b88c9-282">此设置控制是否允许在用户的会议中共享桌面和/或窗口共享。</span><span class="sxs-lookup"><span data-stu-id="b88c9-282">This setting controls whether desktop and/or window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="b88c9-283">未分配任何策略的会议参与者（如匿名、来宾、B2B 和联盟参与者）将继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="b88c9-283">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="b88c9-284">设置值</span><span class="sxs-lookup"><span data-stu-id="b88c9-284">Setting value</span></span> |<span data-ttu-id="b88c9-285">行为</span><span class="sxs-lookup"><span data-stu-id="b88c9-285">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="b88c9-286">**整个屏幕**</span><span class="sxs-lookup"><span data-stu-id="b88c9-286">**Entire screen**</span></span>    | <span data-ttu-id="b88c9-287">会议中允许进行完整的桌面共享和应用程序共享</span><span class="sxs-lookup"><span data-stu-id="b88c9-287">Full desktop sharing and application sharing is allowed in the meeting</span></span> |
|<span data-ttu-id="b88c9-288">**单应用程序**</span><span class="sxs-lookup"><span data-stu-id="b88c9-288">**Single application**</span></span>   | <span data-ttu-id="b88c9-289">允许在会议中共享应用程序</span><span class="sxs-lookup"><span data-stu-id="b88c9-289">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="b88c9-290">**已禁用**</span><span class="sxs-lookup"><span data-stu-id="b88c9-290">**Disabled**</span></span>     |<span data-ttu-id="b88c9-291">会议中已关闭屏幕共享和应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="b88c9-291">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="b88c9-292">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="b88c9-292">Let's look at the following example.</span></span>

|<span data-ttu-id="b88c9-293">用户</span><span class="sxs-lookup"><span data-stu-id="b88c9-293">User</span></span> |<span data-ttu-id="b88c9-294">会议策略</span><span class="sxs-lookup"><span data-stu-id="b88c9-294">Meeting policy</span></span> |<span data-ttu-id="b88c9-295">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="b88c9-295">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b88c9-296">Daniela</span><span class="sxs-lookup"><span data-stu-id="b88c9-296">Daniela</span></span>  | <span data-ttu-id="b88c9-297">全局</span><span class="sxs-lookup"><span data-stu-id="b88c9-297">Global</span></span>   | <span data-ttu-id="b88c9-298">整个屏幕</span><span class="sxs-lookup"><span data-stu-id="b88c9-298">Entire screen</span></span> |
|<span data-ttu-id="b88c9-299">Amanda</span><span class="sxs-lookup"><span data-stu-id="b88c9-299">Amanda</span></span>   | <span data-ttu-id="b88c9-300">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="b88c9-300">Location1MeetingPolicy</span></span>  | <span data-ttu-id="b88c9-301">已禁用</span><span class="sxs-lookup"><span data-stu-id="b88c9-301">Disabled</span></span> |

<span data-ttu-id="b88c9-302">由 Daniela 托管的会议允许会议参与者共享其整个屏幕或特定应用程序。</span><span class="sxs-lookup"><span data-stu-id="b88c9-302">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="b88c9-303">如果 Amanda 加入 Daniela 的会议，Amanda 无法共享她的屏幕或特定应用程序，因为她的策略设置已被禁用。</span><span class="sxs-lookup"><span data-stu-id="b88c9-303">If Amanda joins Daniela’s meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="b88c9-304">在 Amanda 托管的会议中，不允许任何人共享其屏幕或单个应用程序，而不管分配给他们的屏幕共享模式策略如何。</span><span class="sxs-lookup"><span data-stu-id="b88c9-304">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span> <span data-ttu-id="b88c9-305">这意味着 Daniela 不能在 Amanda 的会议中共享她的屏幕或单个应用程序。</span><span class="sxs-lookup"><span data-stu-id="b88c9-305">This means that Daniela can't share her screen or a single application in Amanda’s meetings.</span></span>  

<span data-ttu-id="b88c9-306">当前，如果用户使用的是 Google Chrome，则用户无法在团队会议中播放视频或共享其屏幕。</span><span class="sxs-lookup"><span data-stu-id="b88c9-306">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

### <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="b88c9-307">允许参与者授予或请求控制</span><span class="sxs-lookup"><span data-stu-id="b88c9-307">Allow a participant to give or request control</span></span>

<span data-ttu-id="b88c9-308">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="b88c9-308">This is a per-user policy.</span></span> <span data-ttu-id="b88c9-309">此设置控制用户是否可以将共享桌面或窗口的控制权授予其他会议参与者。</span><span class="sxs-lookup"><span data-stu-id="b88c9-309">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="b88c9-310">若要赋予控制权，请将鼠标悬停在屏幕顶部。</span><span class="sxs-lookup"><span data-stu-id="b88c9-310">To give control, hover over the top of the screen.</span></span> 

<span data-ttu-id="b88c9-311">如果为用户启用此设置，则 "**授予控制权**" 选项显示在共享会话的顶部栏中。</span><span class="sxs-lookup"><span data-stu-id="b88c9-311">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span> 

![显示 "提供控制" 选项的屏幕截图](media/meeting-policies-give-control.png)

<span data-ttu-id="b88c9-313">如果用户的设置处于关闭状态，则 "**提供控制**" 选项不可用。</span><span class="sxs-lookup"><span data-stu-id="b88c9-313">If the settings is turned off for the user, the **Give Control** option isn't available.</span></span>

![显示 "提供控件" 选项不可用的屏幕截图](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="b88c9-315">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="b88c9-315">Let's look at the following example.</span></span>

|<span data-ttu-id="b88c9-316">用户</span><span class="sxs-lookup"><span data-stu-id="b88c9-316">User</span></span> |<span data-ttu-id="b88c9-317">会议策略</span><span class="sxs-lookup"><span data-stu-id="b88c9-317">Meeting policy</span></span>  |<span data-ttu-id="b88c9-318">允许参与者授予或请求控制</span><span class="sxs-lookup"><span data-stu-id="b88c9-318">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b88c9-319">Daniela</span><span class="sxs-lookup"><span data-stu-id="b88c9-319">Daniela</span></span>   | <span data-ttu-id="b88c9-320">全局</span><span class="sxs-lookup"><span data-stu-id="b88c9-320">Global</span></span>   | <span data-ttu-id="b88c9-321">True</span><span class="sxs-lookup"><span data-stu-id="b88c9-321">True</span></span>       |
|<span data-ttu-id="b88c9-322">Babek</span><span class="sxs-lookup"><span data-stu-id="b88c9-322">Babek</span></span>    | <span data-ttu-id="b88c9-323">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="b88c9-323">Location1MeetingPolicy</span></span>        | <span data-ttu-id="b88c9-324">False</span><span class="sxs-lookup"><span data-stu-id="b88c9-324">False</span></span>   |

<span data-ttu-id="b88c9-325">Daniela 可以将共享桌面或窗口的控制权交给 Babek 组织的会议中的其他参与者，Babek 无法将控制权授予其他参与者。</span><span class="sxs-lookup"><span data-stu-id="b88c9-325">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek whereas Babek can't give control to other participants.</span></span>

<span data-ttu-id="b88c9-326">若要使用 PowerShell 控制哪些人可以授予控制请求或接受控制请求，请使用 AllowParticipantGiveRequestControl cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b88c9-326">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="b88c9-327">若要在共享期间提供和控制共享内容，双方都必须使用团队桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="b88c9-327">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="b88c9-328">如果任何一方在浏览器中运行 Teams，则不支持控制。</span><span class="sxs-lookup"><span data-stu-id="b88c9-328">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="b88c9-329">这是由我们计划修复的一个技术限制造成。</span><span class="sxs-lookup"><span data-stu-id="b88c9-329">This is due to a technical limitation that we're planning to fix.</span></span> 

### <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="b88c9-330">允许外部参与者授予或请求控制</span><span class="sxs-lookup"><span data-stu-id="b88c9-330">Allow an external participant to give or request control</span></span>

<span data-ttu-id="b88c9-331">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="b88c9-331">This is a per-user policy.</span></span> <span data-ttu-id="b88c9-332">此设置控制会议中的外部参与者是否可以将其共享桌面或窗口的控制权交给会议中的其他参与者。</span><span class="sxs-lookup"><span data-stu-id="b88c9-332">This setting controls whether external participants in a meeting can give control of their shared desktop or window to other participants in the meeting.</span></span> <span data-ttu-id="b88c9-333">团队会议中的外部参与者可以按如下方式进行分类：</span><span class="sxs-lookup"><span data-stu-id="b88c9-333">External participants in Teams meetings can be categorized as follows:</span></span>  

   - <span data-ttu-id="b88c9-334">匿名用户</span><span class="sxs-lookup"><span data-stu-id="b88c9-334">Anonymous user</span></span>
   - <span data-ttu-id="b88c9-335">来宾用户</span><span class="sxs-lookup"><span data-stu-id="b88c9-335">Guest users</span></span>  
   - <span data-ttu-id="b88c9-336">B2B 用户</span><span class="sxs-lookup"><span data-stu-id="b88c9-336">B2B user</span></span>
   - <span data-ttu-id="b88c9-337">联合用户</span><span class="sxs-lookup"><span data-stu-id="b88c9-337">Federated user</span></span>  

<span data-ttu-id="b88c9-338">联盟用户是否可以向外部用户授予控制权，同时共享受允许外部参与者在其组织中**授予或请求控制**设置的控制。</span><span class="sxs-lookup"><span data-stu-id="b88c9-338">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="b88c9-339">若要使用 PowerShell 控制外部参与者是否可以授予控制或接受控制请求，请使用 AllowExternalParticipantGiveRequestControl cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b88c9-339">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="b88c9-340">允许 PowerPoint 共享</span><span class="sxs-lookup"><span data-stu-id="b88c9-340">Allow PowerPoint sharing</span></span>

<span data-ttu-id="b88c9-341">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="b88c9-341">This is a per-user policy.</span></span> <span data-ttu-id="b88c9-342">此设置控制用户是否可以在会议中共享 PowerPoint 幻灯片放映。</span><span class="sxs-lookup"><span data-stu-id="b88c9-342">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="b88c9-343">外部用户（包括匿名用户、来宾和联盟用户）继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="b88c9-343">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="b88c9-344">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="b88c9-344">Let's look at the following example.</span></span>

|<span data-ttu-id="b88c9-345">用户</span><span class="sxs-lookup"><span data-stu-id="b88c9-345">User</span></span> |<span data-ttu-id="b88c9-346">会议策略</span><span class="sxs-lookup"><span data-stu-id="b88c9-346">Meeting policy</span></span>  |<span data-ttu-id="b88c9-347">允许 PowerPoint 共享</span><span class="sxs-lookup"><span data-stu-id="b88c9-347">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b88c9-348">Daniela</span><span class="sxs-lookup"><span data-stu-id="b88c9-348">Daniela</span></span>   | <span data-ttu-id="b88c9-349">全局</span><span class="sxs-lookup"><span data-stu-id="b88c9-349">Global</span></span>   | <span data-ttu-id="b88c9-350">True</span><span class="sxs-lookup"><span data-stu-id="b88c9-350">True</span></span>       |
|<span data-ttu-id="b88c9-351">Amanda</span><span class="sxs-lookup"><span data-stu-id="b88c9-351">Amanda</span></span>   | <span data-ttu-id="b88c9-352">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="b88c9-352">Location1MeetingPolicy</span></span>        | <span data-ttu-id="b88c9-353">False</span><span class="sxs-lookup"><span data-stu-id="b88c9-353">False</span></span>   |

<span data-ttu-id="b88c9-354">Amanda 不能在会议中共享 PowerPoint 幻灯片卡座，即使她是会议组织者也是如此。</span><span class="sxs-lookup"><span data-stu-id="b88c9-354">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="b88c9-355">Daniela 可以共享 PowerPoint 幻灯片放映，即使会议由 Amanda 组织。</span><span class="sxs-lookup"><span data-stu-id="b88c9-355">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="b88c9-356">Amanda 可以查看会议中其他人共享的 PowerPoint 幻灯片卡座，即使她无法共享 PowerPoint 幻灯片放映。</span><span class="sxs-lookup"><span data-stu-id="b88c9-356">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

### <a name="allow-whiteboard"></a><span data-ttu-id="b88c9-357">允许白板</span><span class="sxs-lookup"><span data-stu-id="b88c9-357">Allow whiteboard</span></span>

<span data-ttu-id="b88c9-358">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="b88c9-358">This is a per-user policy.</span></span> <span data-ttu-id="b88c9-359">此设置控制用户是否可以在会议中共享白板。</span><span class="sxs-lookup"><span data-stu-id="b88c9-359">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="b88c9-360">外部用户（包括匿名用户、B2B 和联盟用户）继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="b88c9-360">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> 

<span data-ttu-id="b88c9-361">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="b88c9-361">Let's look at the following example.</span></span>

|<span data-ttu-id="b88c9-362">用户</span><span class="sxs-lookup"><span data-stu-id="b88c9-362">User</span></span> |<span data-ttu-id="b88c9-363">会议策略</span><span class="sxs-lookup"><span data-stu-id="b88c9-363">Meeting policy</span></span>  |<span data-ttu-id="b88c9-364">允许白板</span><span class="sxs-lookup"><span data-stu-id="b88c9-364">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="b88c9-365">Daniela</span><span class="sxs-lookup"><span data-stu-id="b88c9-365">Daniela</span></span>   | <span data-ttu-id="b88c9-366">全局</span><span class="sxs-lookup"><span data-stu-id="b88c9-366">Global</span></span>   | <span data-ttu-id="b88c9-367">True</span><span class="sxs-lookup"><span data-stu-id="b88c9-367">True</span></span>       |
|<span data-ttu-id="b88c9-368">Amanda</span><span class="sxs-lookup"><span data-stu-id="b88c9-368">Amanda</span></span>   | <span data-ttu-id="b88c9-369">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="b88c9-369">Location1MeetingPolicy</span></span>        | <span data-ttu-id="b88c9-370">False</span><span class="sxs-lookup"><span data-stu-id="b88c9-370">False</span></span>   |

<span data-ttu-id="b88c9-371">Amanda 无法在会议中共享白板，即使她是会议组织者也是如此。</span><span class="sxs-lookup"><span data-stu-id="b88c9-371">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="b88c9-372">即使会议是按 Amanda 组织的，Daniela 也可以共享白板。</span><span class="sxs-lookup"><span data-stu-id="b88c9-372">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

### <a name="allow-shared-notes"></a><span data-ttu-id="b88c9-373">允许共享笔记</span><span class="sxs-lookup"><span data-stu-id="b88c9-373">Allow shared notes</span></span>

<span data-ttu-id="b88c9-374">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="b88c9-374">This is a per-user policy.</span></span> <span data-ttu-id="b88c9-375">此设置控制用户是否可以在会议中创建和共享笔记。</span><span class="sxs-lookup"><span data-stu-id="b88c9-375">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="b88c9-376">外部用户（包括匿名用户、B2B 和联盟用户）继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="b88c9-376">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="b88c9-377">"**会议笔记**" 选项卡目前仅在具有少于20个参与者的会议中受支持。</span><span class="sxs-lookup"><span data-stu-id="b88c9-377">The **Meeting Notes** tab is currently only supported in meetings that have less than 20 participants.</span></span> 

<span data-ttu-id="b88c9-378">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="b88c9-378">Let's look at the following example.</span></span>

|<span data-ttu-id="b88c9-379">用户</span><span class="sxs-lookup"><span data-stu-id="b88c9-379">User</span></span> |<span data-ttu-id="b88c9-380">会议策略</span><span class="sxs-lookup"><span data-stu-id="b88c9-380">Meeting policy</span></span>  |<span data-ttu-id="b88c9-381">允许共享笔记</span><span class="sxs-lookup"><span data-stu-id="b88c9-381">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b88c9-382">Daniela</span><span class="sxs-lookup"><span data-stu-id="b88c9-382">Daniela</span></span>   | <span data-ttu-id="b88c9-383">全局</span><span class="sxs-lookup"><span data-stu-id="b88c9-383">Global</span></span>   | <span data-ttu-id="b88c9-384">True</span><span class="sxs-lookup"><span data-stu-id="b88c9-384">True</span></span>       |
|<span data-ttu-id="b88c9-385">Amanda</span><span class="sxs-lookup"><span data-stu-id="b88c9-385">Amanda</span></span>   | <span data-ttu-id="b88c9-386">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="b88c9-386">Location1MeetingPolicy</span></span> | <span data-ttu-id="b88c9-387">False</span><span class="sxs-lookup"><span data-stu-id="b88c9-387">False</span></span> |

<span data-ttu-id="b88c9-388">Daniela 可以在 Amanda 的会议中做笔记，Amanda 不能在任何会议中做笔记。</span><span class="sxs-lookup"><span data-stu-id="b88c9-388">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>

## <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="b88c9-389">会议策略设置-参与者 & 来宾</span><span class="sxs-lookup"><span data-stu-id="b88c9-389">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="b88c9-390">这些设置控制在会议厅中等待的会议参与者，以及他们在会议中允许的参与级别。</span><span class="sxs-lookup"><span data-stu-id="b88c9-390">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="b88c9-391">自动允许人员</span><span class="sxs-lookup"><span data-stu-id="b88c9-391">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="b88c9-392">允许匿名用户启动会议</span><span class="sxs-lookup"><span data-stu-id="b88c9-392">Allow anonymous people to start a meeting</span></span>](#allow-anonymous-people-to-start-a-meeting)
- [<span data-ttu-id="b88c9-393">允许拨入用户绕过大厅</span><span class="sxs-lookup"><span data-stu-id="b88c9-393">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby)
- [<span data-ttu-id="b88c9-394">允许私人开会立即开会</span><span class="sxs-lookup"><span data-stu-id="b88c9-394">Allow private Meet now </span></span>](#allow-private-meet-now)
- [<span data-ttu-id="b88c9-395">启用实时字幕</span><span class="sxs-lookup"><span data-stu-id="b88c9-395">Enable live captions </span></span>](#enable-live-captions)
- [<span data-ttu-id="b88c9-396">允许在会议中聊天</span><span class="sxs-lookup"><span data-stu-id="b88c9-396">Allow chat in meetings </span></span>](#allow-chat-in-meetings)

> [!NOTE]
><span data-ttu-id="b88c9-397">用于加入会议的选项会有所不同，具体取决于每个团队组的设置和连接方法。</span><span class="sxs-lookup"><span data-stu-id="b88c9-397">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="b88c9-398">如果你的组具有音频会议，并使用它进行连接，请参阅[Office 365 中的音频会议](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="b88c9-398">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing in Office 365](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="b88c9-399">如果你的团队组没有音频会议，请参阅[在团队中加入会议](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)。</span><span class="sxs-lookup"><span data-stu-id="b88c9-399">If your Teams group does not have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

### <a name="automatically-admit-people"></a><span data-ttu-id="b88c9-400">自动允许人员</span><span class="sxs-lookup"><span data-stu-id="b88c9-400">Automatically admit people</span></span>

<span data-ttu-id="b88c9-401">这是每个组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="b88c9-401">This is a per-organizer policy.</span></span> <span data-ttu-id="b88c9-402">此设置控制用户是否直接加入会议或在大厅中等待，直到他们被经过身份验证的用户许可。</span><span class="sxs-lookup"><span data-stu-id="b88c9-402">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span>

![显示会议厅中有用户的会议的屏幕截图](media/meeting-policies-lobby.png)

 <span data-ttu-id="b88c9-404">会议组织者可以单击会议邀请中的 "**会议选项**"，为其计划的每个会议更改此设置。</span><span class="sxs-lookup"><span data-stu-id="b88c9-404">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span> <span data-ttu-id="b88c9-405">**（即将推出）**</span><span class="sxs-lookup"><span data-stu-id="b88c9-405">**(coming soon)**</span></span>
  
|<span data-ttu-id="b88c9-406">设置值</span><span class="sxs-lookup"><span data-stu-id="b88c9-406">Setting value</span></span>  |<span data-ttu-id="b88c9-407">联接行为</span><span class="sxs-lookup"><span data-stu-id="b88c9-407">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="b88c9-408">**人均**</span><span class="sxs-lookup"><span data-stu-id="b88c9-408">**Everyone**</span></span>   |<span data-ttu-id="b88c9-409">所有会议参与者都直接加入会议，而无需在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="b88c9-409">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="b88c9-410">这包括经过身份验证的用户、联盟用户、来宾、匿名用户和通过电话拨入的用户。</span><span class="sxs-lookup"><span data-stu-id="b88c9-410">This includes authenticated users, federated users, guests, anonymous users, and people who dial in by phone.</span></span>       |
|<span data-ttu-id="b88c9-411">**组织和联盟组织中的每个人**</span><span class="sxs-lookup"><span data-stu-id="b88c9-411">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="b88c9-412">组织内的经过身份验证的用户，包括来宾用户和联盟组织中的用户，直接加入会议，而无需在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="b88c9-412">Authenticated users within the organization, including guest users and the users from federated organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="b88c9-413">通过电话拨入的匿名用户和用户在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="b88c9-413">Anonymous users and users who dial in by phone wait in the lobby.</span></span>   |
|<span data-ttu-id="b88c9-414">**您的组织中的每个人**</span><span class="sxs-lookup"><span data-stu-id="b88c9-414">**Everyone in your organization**</span></span>    |<span data-ttu-id="b88c9-415">来自组织内部的经过身份验证的用户（包括来宾用户）直接加入会议，而无需在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="b88c9-415">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="b88c9-416">联合用户、匿名用户和通过电话拨入的用户在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="b88c9-416">Federated users, anonymous users, and users who dial in by phone wait in the lobby.</span></span>           |

### <a name="allow-anonymous-people-to-start-a-meeting"></a><span data-ttu-id="b88c9-417">允许匿名用户启动会议</span><span class="sxs-lookup"><span data-stu-id="b88c9-417">Allow anonymous people to start a meeting</span></span>

<span data-ttu-id="b88c9-418">这是每个组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="b88c9-418">This is a per-organizer policy.</span></span> <span data-ttu-id="b88c9-419">此设置控制匿名人员（包括 B2B）和联盟用户是否可以在没有经过身份验证的组织中加入用户的会议。</span><span class="sxs-lookup"><span data-stu-id="b88c9-419">This setting controls whether anonymous people, including B2B, and federated users, can join the user's meeting without an authenticated user from the organization in attendance.</span></span> 

![显示一条消息给正在等待的用户的屏幕截图](media/meeting-policies-anonymous-user-lobby.png)

<span data-ttu-id="b88c9-421">下面是在会议中提供了身份验证用户时匿名用户的加入行为。</span><span class="sxs-lookup"><span data-stu-id="b88c9-421">Here's the join behavior of anonymous people when authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="b88c9-422">允许匿名用户启动会议</span><span class="sxs-lookup"><span data-stu-id="b88c9-422">Allow anonymous people to start a meeting</span></span>  |<span data-ttu-id="b88c9-423">自动允许人员</span><span class="sxs-lookup"><span data-stu-id="b88c9-423">Automatically admit people</span></span> |<span data-ttu-id="b88c9-424">匿名人员的加入行为</span><span class="sxs-lookup"><span data-stu-id="b88c9-424">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b88c9-425">True</span><span class="sxs-lookup"><span data-stu-id="b88c9-425">True</span></span>    | <span data-ttu-id="b88c9-426">人均</span><span class="sxs-lookup"><span data-stu-id="b88c9-426">Everyone</span></span>      | <span data-ttu-id="b88c9-427">直接加入</span><span class="sxs-lookup"><span data-stu-id="b88c9-427">Join directly</span></span>         |
|   | <span data-ttu-id="b88c9-428">您的组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="b88c9-428">Everyone in your organization</span></span>       | <span data-ttu-id="b88c9-429">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="b88c9-429">Wait in lobby</span></span>        |
|   | <span data-ttu-id="b88c9-430">组织和联盟组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="b88c9-430">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="b88c9-431">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="b88c9-431">Wait in lobby</span></span>         |
|<span data-ttu-id="b88c9-432">False</span><span class="sxs-lookup"><span data-stu-id="b88c9-432">False</span></span>    | <span data-ttu-id="b88c9-433">人均</span><span class="sxs-lookup"><span data-stu-id="b88c9-433">Everyone</span></span>        | <span data-ttu-id="b88c9-434">直接加入</span><span class="sxs-lookup"><span data-stu-id="b88c9-434">Join directly</span></span>        |
|   | <span data-ttu-id="b88c9-435">您的组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="b88c9-435">Everyone in your organization</span></span>     | <span data-ttu-id="b88c9-436">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="b88c9-436">Wait in lobby</span></span>        |
|   | <span data-ttu-id="b88c9-437">组织和联盟组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="b88c9-437">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="b88c9-438">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="b88c9-438">Wait in lobby</span></span>         |

<span data-ttu-id="b88c9-439">下面是当会议中没有经过身份验证的用户时匿名用户的加入行为。</span><span class="sxs-lookup"><span data-stu-id="b88c9-439">Here's the join behavior of anonymous people when no authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="b88c9-440">允许匿名用户启动会议</span><span class="sxs-lookup"><span data-stu-id="b88c9-440">Allow anonymous people to start a meeting</span></span> |<span data-ttu-id="b88c9-441">自动允许人员</span><span class="sxs-lookup"><span data-stu-id="b88c9-441">Automatically admit people</span></span>  |<span data-ttu-id="b88c9-442">匿名人员的加入行为</span><span class="sxs-lookup"><span data-stu-id="b88c9-442">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b88c9-443">True</span><span class="sxs-lookup"><span data-stu-id="b88c9-443">True</span></span>    | <span data-ttu-id="b88c9-444">人均</span><span class="sxs-lookup"><span data-stu-id="b88c9-444">Everyone</span></span>      | <span data-ttu-id="b88c9-445">直接加入</span><span class="sxs-lookup"><span data-stu-id="b88c9-445">Join directly</span></span>         |
|   | <span data-ttu-id="b88c9-446">您的组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="b88c9-446">Everyone in your organization</span></span>       | <span data-ttu-id="b88c9-447">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="b88c9-447">Wait in lobby</span></span>        |
|   | <span data-ttu-id="b88c9-448">组织和联盟组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="b88c9-448">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="b88c9-449">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="b88c9-449">Wait in lobby</span></span>         |
|<span data-ttu-id="b88c9-450">False</span><span class="sxs-lookup"><span data-stu-id="b88c9-450">False</span></span>    | <span data-ttu-id="b88c9-451">人均</span><span class="sxs-lookup"><span data-stu-id="b88c9-451">Everyone</span></span>        | <span data-ttu-id="b88c9-452">在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="b88c9-452">Wait in lobby.</span></span> <span data-ttu-id="b88c9-453">当第一个经过身份验证的用户加入会议时，将自动向用户提供许可。</span><span class="sxs-lookup"><span data-stu-id="b88c9-453">Users are automatically admitted when the first authenticated user joins the meeting.</span></span>        |
|   | <span data-ttu-id="b88c9-454">您的组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="b88c9-454">Everyone in your organization</span></span>     |<span data-ttu-id="b88c9-455">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="b88c9-455">Wait in lobby</span></span>         |
|   | <span data-ttu-id="b88c9-456">组织和联盟组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="b88c9-456">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="b88c9-457">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="b88c9-457">Wait in lobby</span></span>         |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a><span data-ttu-id="b88c9-458">允许拨入用户绕过大厅</span><span class="sxs-lookup"><span data-stu-id="b88c9-458">Allow dial-in users to bypass the lobby</span></span>

<span data-ttu-id="b88c9-459">这是每个组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="b88c9-459">This is a per-organizer policy.</span></span> <span data-ttu-id="b88c9-460">此设置控制通过电话拨入的用户是否直接加入会议或在会议厅中等待，而不管 "是否**自动允许人员**" 设置。</span><span class="sxs-lookup"><span data-stu-id="b88c9-460">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span>

<span data-ttu-id="b88c9-461">下面是通过电话拨入的用户的加入行为。</span><span class="sxs-lookup"><span data-stu-id="b88c9-461">Here's the join behavior of people who dial in by phone.</span></span>

|<span data-ttu-id="b88c9-462">允许拨入用户绕过大厅</span><span class="sxs-lookup"><span data-stu-id="b88c9-462">Allow dial-in users to bypass the lobby</span></span>  |<span data-ttu-id="b88c9-463">自动允许用户</span><span class="sxs-lookup"><span data-stu-id="b88c9-463">Automatically admit users</span></span>  |<span data-ttu-id="b88c9-464">拨入的用户的加入行为</span><span class="sxs-lookup"><span data-stu-id="b88c9-464">Join behavior of people who dial in</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b88c9-465">True</span><span class="sxs-lookup"><span data-stu-id="b88c9-465">True</span></span>    | <span data-ttu-id="b88c9-466">人均</span><span class="sxs-lookup"><span data-stu-id="b88c9-466">Everyone</span></span>      | <span data-ttu-id="b88c9-467">直接加入</span><span class="sxs-lookup"><span data-stu-id="b88c9-467">Join directly</span></span>         |
|   | <span data-ttu-id="b88c9-468">您的组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="b88c9-468">Everyone in your organization</span></span>       | <span data-ttu-id="b88c9-469">直接加入</span><span class="sxs-lookup"><span data-stu-id="b88c9-469">Join directly</span></span>        |
|   | <span data-ttu-id="b88c9-470">组织和联盟组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="b88c9-470">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="b88c9-471">直接加入</span><span class="sxs-lookup"><span data-stu-id="b88c9-471">Join directly</span></span>         |
|<span data-ttu-id="b88c9-472">False</span><span class="sxs-lookup"><span data-stu-id="b88c9-472">False</span></span>    | <span data-ttu-id="b88c9-473">人均</span><span class="sxs-lookup"><span data-stu-id="b88c9-473">Everyone</span></span>        | <span data-ttu-id="b88c9-474">直接加入</span><span class="sxs-lookup"><span data-stu-id="b88c9-474">Join directly</span></span>        |
|   | <span data-ttu-id="b88c9-475">您的组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="b88c9-475">Everyone in your organization</span></span>     |<span data-ttu-id="b88c9-476">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="b88c9-476">Wait in lobby</span></span>         |
|   | <span data-ttu-id="b88c9-477">组织和联盟组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="b88c9-477">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="b88c9-478">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="b88c9-478">Wait in lobby</span></span>         |

### <a name="allow-private-meet-now"></a><span data-ttu-id="b88c9-479">允许私人开会立即开会</span><span class="sxs-lookup"><span data-stu-id="b88c9-479">Allow private Meet now</span></span>

<span data-ttu-id="b88c9-480">这是每用户策略，在会议开始之前应用。</span><span class="sxs-lookup"><span data-stu-id="b88c9-480">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="b88c9-481">此设置控制用户是否可以启动 ad hoc 私人会议。</span><span class="sxs-lookup"><span data-stu-id="b88c9-481">This setting controls whether a user can start an ad hoc private meeting.</span></span> 

### <a name="enable-live-captions"></a><span data-ttu-id="b88c9-482">启用实时字幕</span><span class="sxs-lookup"><span data-stu-id="b88c9-482">Enable live captions</span></span>

<span data-ttu-id="b88c9-483">这是每用户策略，在会议期间应用。</span><span class="sxs-lookup"><span data-stu-id="b88c9-483">This is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="b88c9-484">此设置控制用户是否可以使用 "**打开实时标题**" 选项来打开和关闭用户出席的会议中的实时字幕。</span><span class="sxs-lookup"><span data-stu-id="b88c9-484">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![显示 "打开实时字幕" 选项的屏幕截图](media/meeting-policies-live-captions.png)

|<span data-ttu-id="b88c9-486">设置值</span><span class="sxs-lookup"><span data-stu-id="b88c9-486">Setting value</span></span> |<span data-ttu-id="b88c9-487">行为</span><span class="sxs-lookup"><span data-stu-id="b88c9-487">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="b88c9-488">**已禁用，用户可以替代**</span><span class="sxs-lookup"><span data-stu-id="b88c9-488">**Disabled and the user can override**</span></span>     | <span data-ttu-id="b88c9-489">会议期间不会为用户自动打开实时字幕。</span><span class="sxs-lookup"><span data-stu-id="b88c9-489">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="b88c9-490">用户可以在 "溢出（**...**）" 菜单中看到 "**打开实时标题**" 选项以将其打开。</span><span class="sxs-lookup"><span data-stu-id="b88c9-490">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="b88c9-491">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="b88c9-491">This is the default setting.</span></span> |
|<span data-ttu-id="b88c9-492">**已禁用**</span><span class="sxs-lookup"><span data-stu-id="b88c9-492">**Disabled**</span></span>     | <span data-ttu-id="b88c9-493">会议期间，用户已禁用实时字幕。</span><span class="sxs-lookup"><span data-stu-id="b88c9-493">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="b88c9-494">用户不能选择将其打开。</span><span class="sxs-lookup"><span data-stu-id="b88c9-494">The user doesn't have the option to turn them on.</span></span>          |


<span data-ttu-id="b88c9-495"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="b88c9-495"></span></span>

### <a name="allow-chat-in-meetings"></a><span data-ttu-id="b88c9-496">允许在会议中聊天</span><span class="sxs-lookup"><span data-stu-id="b88c9-496">Allow chat in meetings</span></span>

<span data-ttu-id="b88c9-497">这是每个组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="b88c9-497">This is a per-organizer policy.</span></span> <span data-ttu-id="b88c9-498">此设置控制是否允许在用户的会议中使用会议聊天。</span><span class="sxs-lookup"><span data-stu-id="b88c9-498">This setting controls whether meeting chat is allowed in the user's meeting.</span></span> 

<span data-ttu-id="b88c9-499"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="b88c9-499"></span></span>

## <a name="related-topics"></a><span data-ttu-id="b88c9-500">相关主题</span><span class="sxs-lookup"><span data-stu-id="b88c9-500">Related topics</span></span>
[<span data-ttu-id="b88c9-501">团队中的消息传递策略</span><span class="sxs-lookup"><span data-stu-id="b88c9-501">Messaging policies in Teams</span></span>](messaging-policies-in-teams.md)
