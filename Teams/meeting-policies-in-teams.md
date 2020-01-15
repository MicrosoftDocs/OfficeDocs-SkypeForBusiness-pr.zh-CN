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
ms.openlocfilehash: 20382a41ac8d0a78d56ebcb51e852f5302ea74a7
ms.sourcegitcommit: 447c5ffc27c5b0928e033f85914810af56e510ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2020
ms.locfileid: "41120391"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="05a8d-103">管理团队中的会议策略</span><span class="sxs-lookup"><span data-stu-id="05a8d-103">Manage meeting policies in Teams</span></span>

::: zone target="docs"
<span data-ttu-id="05a8d-104">会议策略用于控制会议参与者对由您的组织中的用户安排的会议参与者可用的功能。</span><span class="sxs-lookup"><span data-stu-id="05a8d-104">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="05a8d-105">创建策略并进行更改后，您可以将用户分配到该策略。</span><span class="sxs-lookup"><span data-stu-id="05a8d-105">After you create a policy and make your changes, you can then assign users to the policy.</span></span> <span data-ttu-id="05a8d-106">可在 Microsoft 团队管理中心或通过[使用 PowerShell](teams-powershell-overview.md)管理会议策略。</span><span class="sxs-lookup"><span data-stu-id="05a8d-106">You manage meeting policies in the Microsoft Teams admin center or by [using PowerShell](teams-powershell-overview.md).</span></span>

<span data-ttu-id="05a8d-107">你可以通过以下方式实施策略，这会在会议开始之前、会议期间或会议后影响用户的会议体验。</span><span class="sxs-lookup"><span data-stu-id="05a8d-107">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="05a8d-108">实现类型</span><span class="sxs-lookup"><span data-stu-id="05a8d-108">Implementation type</span></span>  |<span data-ttu-id="05a8d-109">说明</span><span class="sxs-lookup"><span data-stu-id="05a8d-109">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="05a8d-110">每个组织者</span><span class="sxs-lookup"><span data-stu-id="05a8d-110">Per-organizer</span></span>    |<span data-ttu-id="05a8d-111">实施按组织者策略时，所有会议参与者都将继承组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="05a8d-111">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="05a8d-112">例如，**自动允许人员**为每个组织者策略，并控制用户是否直接加入会议，或在会议厅中等待分配了该策略的用户安排的会议。</span><span class="sxs-lookup"><span data-stu-id="05a8d-112">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="05a8d-113">每用户</span><span class="sxs-lookup"><span data-stu-id="05a8d-113">Per-user</span></span>    |<span data-ttu-id="05a8d-114">当你实现每用户策略时，仅应用每用户策略来限制组织者和/或会议参与者的某些功能。</span><span class="sxs-lookup"><span data-stu-id="05a8d-114">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="05a8d-115">例如，"**允许现在开会**" 是每用户策略。</span><span class="sxs-lookup"><span data-stu-id="05a8d-115">For example, **Allow Meet now** is a per-user policy.</span></span>     |
|<span data-ttu-id="05a8d-116">每个组织者和每用户</span><span class="sxs-lookup"><span data-stu-id="05a8d-116">Per-organizer and per-user</span></span>     |<span data-ttu-id="05a8d-117">当你实现每个组织单位和每用户策略的组合时，某些功能将根据其策略和组织者的策略来限制会议参与者。</span><span class="sxs-lookup"><span data-stu-id="05a8d-117">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="05a8d-118">例如，"**允许云录制**" 是基于每个组织者和每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="05a8d-118">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="05a8d-119">启用此设置可允许会议组织者和参与者开始和停止录制。</span><span class="sxs-lookup"><span data-stu-id="05a8d-119">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span> 

<span data-ttu-id="05a8d-120">默认情况下，将创建名为 Global 的策略（组织范围的默认设置）。</span><span class="sxs-lookup"><span data-stu-id="05a8d-120">By default, a policy named Global (org-wide default) is created.</span></span> <span data-ttu-id="05a8d-121">默认情况下，将为组织中的所有用户分配此会议策略。</span><span class="sxs-lookup"><span data-stu-id="05a8d-121">All users in your organization will be assigned this meeting policy by default.</span></span> <span data-ttu-id="05a8d-122">你可以更改此策略，也可以创建一个或多个自定义策略并向其分配用户。</span><span class="sxs-lookup"><span data-stu-id="05a8d-122">You can either make changes to this policy or create one or more custom policies and assign users to them.</span></span> <span data-ttu-id="05a8d-123">创建自定义策略时，你可以允许或阻止你的用户使用某些功能，然后将其分配给将对其应用设置的一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="05a8d-123">When you create a custom policy, you can allow or prevent certain features from being available to your users, and then assign it to one or more users who will have the settings applied to them.</span></span> 

## <a name="change-or-create-a-meeting-policy"></a><span data-ttu-id="05a8d-124">更改或创建会议策略</span><span class="sxs-lookup"><span data-stu-id="05a8d-124">Change or create a meeting policy</span></span>

<span data-ttu-id="05a8d-125">若要更改或创建会议策略，请转到 Microsoft 团队**管理中心 >** > "会议**策略**"。</span><span class="sxs-lookup"><span data-stu-id="05a8d-125">To change or create a meeting policy, go to the Microsoft Teams admin center > **Meetings** > **Meeting policies**.</span></span> <span data-ttu-id="05a8d-126">从列表中选择一个策略，或选择 "**新建策略**"。</span><span class="sxs-lookup"><span data-stu-id="05a8d-126">Select a policy from the list or select **New policy**.</span></span> <span data-ttu-id="05a8d-127">如果要创建新策略，请添加名称和说明。</span><span class="sxs-lookup"><span data-stu-id="05a8d-127">If you're creating a new policy, add a name and description.</span></span> <span data-ttu-id="05a8d-128">名称不能包含特殊字符，也不能超过64个字符。</span><span class="sxs-lookup"><span data-stu-id="05a8d-128">The name can't contain special characters or be longer than 64 characters.</span></span> <span data-ttu-id="05a8d-129">选择您的设置，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="05a8d-129">Choose your settings, and then select **Save**.</span></span>

<span data-ttu-id="05a8d-130">例如，假设你有一组用户，并且想要限制其会议所需的带宽量。</span><span class="sxs-lookup"><span data-stu-id="05a8d-130">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="05a8d-131">您将创建一个名为 "有限带宽" 的新自定义策略，并禁用以下设置：</span><span class="sxs-lookup"><span data-stu-id="05a8d-131">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="05a8d-132">在 "**音频 & 视频**：</span><span class="sxs-lookup"><span data-stu-id="05a8d-132">Under **Audio & video**:</span></span>
- <span data-ttu-id="05a8d-133">关闭云录制</span><span class="sxs-lookup"><span data-stu-id="05a8d-133">Turn off cloud recording</span></span>
- <span data-ttu-id="05a8d-134">关闭 "允许 IP 视频"</span><span class="sxs-lookup"><span data-stu-id="05a8d-134">Turn off Allow IP video</span></span>

<span data-ttu-id="05a8d-135">在 "**内容共享**" 下：</span><span class="sxs-lookup"><span data-stu-id="05a8d-135">Under **Content sharing**:</span></span>
- <span data-ttu-id="05a8d-136">禁用屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="05a8d-136">Disable screen sharing mode</span></span>
- <span data-ttu-id="05a8d-137">关闭白板</span><span class="sxs-lookup"><span data-stu-id="05a8d-137">Turn off whiteboard</span></span>
- <span data-ttu-id="05a8d-138">关闭共享笔记</span><span class="sxs-lookup"><span data-stu-id="05a8d-138">Turn off shared notes</span></span>

<span data-ttu-id="05a8d-139">然后向用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="05a8d-139">Then assign the policy to the users.</span></span>

> [!NOTE] 
> <span data-ttu-id="05a8d-140">一次只能向一个用户分配一个会议策略。</span><span class="sxs-lookup"><span data-stu-id="05a8d-140">A user can be assigned only one meeting policy at a time.</span></span> 

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="05a8d-141">向用户分配会议策略</span><span class="sxs-lookup"><span data-stu-id="05a8d-141">Assign a meeting policy to users</span></span>

<span data-ttu-id="05a8d-142">如果要将策略应用到一个用户，请在左侧导航窗格中选择 "**用户**"，然后单击用户的显示名称。</span><span class="sxs-lookup"><span data-stu-id="05a8d-142">If you're applying the policy to one user, select **Users** on the left navigation pane, and then click the user's display name.</span></span> <span data-ttu-id="05a8d-143">在用户的页面上，在 "**分配的策略**" 旁边，选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="05a8d-143">On the user's page, next to **Assigned policies**, select **Edit**.</span></span> <span data-ttu-id="05a8d-144">然后，在 "**编辑用户策略**" 窗格中的 "**会议策略**" 下，从下拉列表中选择 "会议策略"，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="05a8d-144">Then, in the **Edit user policies** pane, under **Meeting policy**, select the meeting policy from the drop-down list, and then select **Save**.</span></span> <span data-ttu-id="05a8d-145">您还可以从用户列表中分配策略。</span><span class="sxs-lookup"><span data-stu-id="05a8d-145">You can also assign policies from the list of users.</span></span> <span data-ttu-id="05a8d-146">若要执行此操作，请单击用户的显示名称左侧的用户选择用户。</span><span class="sxs-lookup"><span data-stu-id="05a8d-146">To do this, select the user by clicking to the left of the user's display name.</span></span> <span data-ttu-id="05a8d-147">选择 "**编辑设置**"。</span><span class="sxs-lookup"><span data-stu-id="05a8d-147">Select **Edit settings**.</span></span> <span data-ttu-id="05a8d-148">然后，在 "**编辑设置**" 窗格的 "**会议策略**" 下，从下拉列表中选择策略，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="05a8d-148">Then, on the **Edit settings** pane, under **Meeting policy**, select the policy from the drop-down list, and then select **Save**.</span></span> 
 
<span data-ttu-id="05a8d-149">如果要将策略应用于多个用户，请在左侧导航窗格中选择 "**用户**"，然后单击用户名左侧的 "**编辑设置**"，选择每个用户。</span><span class="sxs-lookup"><span data-stu-id="05a8d-149">If you're applying a policy to more than one user, select **Users** on the left navigation pane, and then select each user by clicking to the left of the user name, and then click **Edit settings**.</span></span> <span data-ttu-id="05a8d-150">在 "**编辑设置**" 窗格的 "**会议策略**" 下，从下拉列表中选择策略，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="05a8d-150">On the **Edit Settings** pane, under **Meeting policy**, select the policy from the drop-down list, and then select **Save**.</span></span>
 
<span data-ttu-id="05a8d-151">您还可以将会议策略分配给一个或多个用户，如下所示：</span><span class="sxs-lookup"><span data-stu-id="05a8d-151">You can also assign a meeting policy to one or more users as follows:</span></span>

1. <span data-ttu-id="05a8d-152">转到**Microsoft 团队管理中心** > **会议** > **会议策略**。</span><span class="sxs-lookup"><span data-stu-id="05a8d-152">Go to **Microsoft Teams admin center** > **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="05a8d-153">通过单击策略名称的左侧，选择策略。</span><span class="sxs-lookup"><span data-stu-id="05a8d-153">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="05a8d-154">选择 "**管理用户**"。</span><span class="sxs-lookup"><span data-stu-id="05a8d-154">Select **Manage users**.</span></span>
4. <span data-ttu-id="05a8d-155">在 "**管理用户**" 窗格中，按 "显示名称" 或 "按用户名搜索用户"，选择名称，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="05a8d-155">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="05a8d-156">对要添加的每个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="05a8d-156">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="05a8d-157">添加完用户后，请选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="05a8d-157">When you're finished adding users, select **Save**.</span></span>
 
> [!NOTE] 
> <span data-ttu-id="05a8d-158">如果向用户分配了该策略，则不能删除该策略。</span><span class="sxs-lookup"><span data-stu-id="05a8d-158">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="05a8d-159">必须先为所有受影响的用户分配不同的策略，然后才能删除原始策略。</span><span class="sxs-lookup"><span data-stu-id="05a8d-159">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>
 
## <a name="meeting-policy-settings"></a><span data-ttu-id="05a8d-160">会议策略设置</span><span class="sxs-lookup"><span data-stu-id="05a8d-160">Meeting policy settings</span></span>

<span data-ttu-id="05a8d-161">在 "**会议策略**" 页面上选择现有策略或选择 "**新建策略**" 以添加新策略时，可以为以下项配置设置。</span><span class="sxs-lookup"><span data-stu-id="05a8d-161">When you select an existing policy on the **Meeting policies** page or select **New policy** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="05a8d-162">常规</span><span class="sxs-lookup"><span data-stu-id="05a8d-162">General</span></span>](#meeting-policy-settings---general)
- [<span data-ttu-id="05a8d-163">音频 & 视频</span><span class="sxs-lookup"><span data-stu-id="05a8d-163">Audio & video</span></span>](#meeting-policy-settings---audio--video)
- [<span data-ttu-id="05a8d-164">内容共享</span><span class="sxs-lookup"><span data-stu-id="05a8d-164">Content sharing</span></span>](#meeting-policy-settings---content-sharing)
- [<span data-ttu-id="05a8d-165">参与者 & 来宾</span><span class="sxs-lookup"><span data-stu-id="05a8d-165">Participants & guests</span></span>](#meeting-policy-settings---participants--guests)

::: zone-end 

<span data-ttu-id="05a8d-166"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="05a8d-166"></span></span>

## <a name="meeting-policy-settings---general"></a><span data-ttu-id="05a8d-167">会议策略设置-常规</span><span class="sxs-lookup"><span data-stu-id="05a8d-167">Meeting policy settings - General</span></span>

- [<span data-ttu-id="05a8d-168">允许在频道中立即开会</span><span class="sxs-lookup"><span data-stu-id="05a8d-168">Allow Meet now in channels</span></span>](#allow-meet-now-in-channels)
- [<span data-ttu-id="05a8d-169">允许私人开会立即开会</span><span class="sxs-lookup"><span data-stu-id="05a8d-169">Allow private Meet now</span></span>](#allow-private-meet-now)
- [<span data-ttu-id="05a8d-170">允许 Outlook 加载项</span><span class="sxs-lookup"><span data-stu-id="05a8d-170">Allow the Outlook add-in</span></span>](#allow-the-outlook-add-in)
- [<span data-ttu-id="05a8d-171">允许频道会议安排</span><span class="sxs-lookup"><span data-stu-id="05a8d-171">Allow channel meeting scheduling</span></span>](#allow-channel-meeting-scheduling)
- [<span data-ttu-id="05a8d-172">允许安排私人会议</span><span class="sxs-lookup"><span data-stu-id="05a8d-172">Allow scheduling private meetings</span></span>](#allow-scheduling-private-meetings)

### <a name="allow-meet-now-in-channels"></a><span data-ttu-id="05a8d-173">允许在频道中立即开会</span><span class="sxs-lookup"><span data-stu-id="05a8d-173">Allow Meet now in channels</span></span>

<span data-ttu-id="05a8d-174">这是每用户策略，在会议开始之前应用。</span><span class="sxs-lookup"><span data-stu-id="05a8d-174">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="05a8d-175">此设置控制用户是否可以在团队频道中启动临时会议。</span><span class="sxs-lookup"><span data-stu-id="05a8d-175">This setting controls whether a user can start an ad hoc meeting in a Teams channel.</span></span> <span data-ttu-id="05a8d-176">如果启用此操作，当用户在团队频道中发布消息时，用户可以单击 "撰写" 框下方的 "**立即开会**" 以在频道中启动临时会议。</span><span class="sxs-lookup"><span data-stu-id="05a8d-176">If you turn this on, when a user posts a message in a Teams channel, the user can click **Meet now** beneath the compose box to start an ad hoc meeting in the channel.</span></span>

![显示邮件下方的 "立即开会" 图标的屏幕截图](media/meeting-policies-meet-now.png)

### <a name="allow-private-meet-now"></a><span data-ttu-id="05a8d-178">允许私人开会立即开会</span><span class="sxs-lookup"><span data-stu-id="05a8d-178">Allow private Meet now</span></span>

<span data-ttu-id="05a8d-179">这是每用户策略，在会议开始之前应用。</span><span class="sxs-lookup"><span data-stu-id="05a8d-179">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="05a8d-180">此设置控制用户是否可以启动 ad hoc 私人会议。</span><span class="sxs-lookup"><span data-stu-id="05a8d-180">This setting controls whether a user can start an ad hoc private meeting.</span></span>  

### <a name="allow-the-outlook-add-in"></a><span data-ttu-id="05a8d-181">允许 Outlook 加载项</span><span class="sxs-lookup"><span data-stu-id="05a8d-181">Allow the Outlook add-in</span></span>

<span data-ttu-id="05a8d-182">这是每用户策略，在会议开始之前应用。</span><span class="sxs-lookup"><span data-stu-id="05a8d-182">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="05a8d-183">此设置控制是否可以从 Outlook （Windows、Mac、web 和手机）内安排团队会议。</span><span class="sxs-lookup"><span data-stu-id="05a8d-183">This setting controls whether Teams meetings can be scheduled from within Outlook (Windows, Mac, web, and mobile).</span></span>

![显示安排新会议的功能的屏幕截图](media/meeting-policies-outlook-add-in.png)

<span data-ttu-id="05a8d-185">如果关闭此功能，用户在 Outlook 中创建新会议时，无法安排团队会议。</span><span class="sxs-lookup"><span data-stu-id="05a8d-185">If you turn this off, users are unable to schedule Teams meetings when they create a new meeting in Outlook.</span></span> <span data-ttu-id="05a8d-186">例如，在 Windows 上的 Outlook 中，"**新建团队会议**" 选项不会显示在功能区中。</span><span class="sxs-lookup"><span data-stu-id="05a8d-186">For example, in Outlook on Windows, the **New Teams Meeting** option won't show up in the ribbon.</span></span>

### <a name="allow-channel-meeting-scheduling"></a><span data-ttu-id="05a8d-187">允许频道会议安排</span><span class="sxs-lookup"><span data-stu-id="05a8d-187">Allow channel meeting scheduling</span></span>

<span data-ttu-id="05a8d-188">这是每用户策略，在会议开始之前应用。</span><span class="sxs-lookup"><span data-stu-id="05a8d-188">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="05a8d-189">此设置控制用户是否可以在团队频道中安排会议。</span><span class="sxs-lookup"><span data-stu-id="05a8d-189">This setting controls whether users can schedule a meeting in a Teams channel.</span></span>  <span data-ttu-id="05a8d-190">如果关闭此功能，则当用户在团队频道中启动会议，并且为团队中的用户禁用 "**添加频道**" 选项时，"**安排会议**" 选项将不可用。</span><span class="sxs-lookup"><span data-stu-id="05a8d-190">If you turn this off, the **Schedule a meeting** option won't be available to the user when they start a meeting in a Teams channel and the **Add a channel** option is disabled for users in Teams.</span></span>

![显示团队中的 "安排会议" 选项的屏幕截图](media/meeting-policies-schedule-a-meeting.png)

![显示 "选择要开会的频道" 选项的屏幕截图](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a><span data-ttu-id="05a8d-193">允许安排私人会议</span><span class="sxs-lookup"><span data-stu-id="05a8d-193">Allow scheduling private meetings</span></span>

<span data-ttu-id="05a8d-194">这是每用户策略，在会议开始之前应用。</span><span class="sxs-lookup"><span data-stu-id="05a8d-194">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="05a8d-195">此设置控制用户是否可以在团队中安排私人会议。</span><span class="sxs-lookup"><span data-stu-id="05a8d-195">This setting controls whether users can schedule private meetings in Teams.</span></span> <span data-ttu-id="05a8d-196">当会议未发布到团队中的频道时，它是私有的。</span><span class="sxs-lookup"><span data-stu-id="05a8d-196">A meeting is private when it's not published to a channel in a team.</span></span>

<span data-ttu-id="05a8d-197">请注意，如果关闭 "**允许安排私人会议**" 和 "**允许频道会议计划**"，则会为团队中的用户禁用 "**添加必需与会者**" 和 "**添加频道**" 选项。</span><span class="sxs-lookup"><span data-stu-id="05a8d-197">Note that if you turn off **Allow scheduling private meetings** and **Allow channel meeting scheduling**,  the **Add required attendees** and **Add channel** options are disabled for users in Teams.</span></span>

<span data-ttu-id="05a8d-198"><a name="bkaudioandvideo"> </a></span><span class="sxs-lookup"><span data-stu-id="05a8d-198"></span></span>

## <a name="meeting-policy-settings---audio--video"></a><span data-ttu-id="05a8d-199">会议策略设置-音频 & 视频</span><span class="sxs-lookup"><span data-stu-id="05a8d-199">Meeting policy settings - Audio & video</span></span>

- [<span data-ttu-id="05a8d-200">允许脚本</span><span class="sxs-lookup"><span data-stu-id="05a8d-200">Allow transcription</span></span>](#allow-transcription)
- [<span data-ttu-id="05a8d-201">允许云录制</span><span class="sxs-lookup"><span data-stu-id="05a8d-201">Allow cloud recording</span></span>](#allow-cloud-recording)
- [<span data-ttu-id="05a8d-202">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="05a8d-202">Allow IP video</span></span>](#allow-ip-video)
- [<span data-ttu-id="05a8d-203">媒体比特率（KBs）</span><span class="sxs-lookup"><span data-stu-id="05a8d-203">Media bit rate (KBs)</span></span>](#media-bit-rate-kbs)
- [<span data-ttu-id="05a8d-204">启用实时字幕（预览）</span><span class="sxs-lookup"><span data-stu-id="05a8d-204">Enable live captions (preview)</span></span>](#enable-live-captions-preview)

### <a name="allow-transcription"></a><span data-ttu-id="05a8d-205">允许脚本</span><span class="sxs-lookup"><span data-stu-id="05a8d-205">Allow transcription</span></span>

<span data-ttu-id="05a8d-206">这是每个组织单位和每用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="05a8d-206">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="05a8d-207">此设置控制播放会议录制期间是否提供字幕和脚本功能。</span><span class="sxs-lookup"><span data-stu-id="05a8d-207">This setting controls whether captions and transcription features are available during playback of meeting recordings.</span></span> <span data-ttu-id="05a8d-208">如果关闭此功能，在播放会议录制的过程中，"**搜索**" 和 **"抄送**" 选项将不可用。</span><span class="sxs-lookup"><span data-stu-id="05a8d-208">If you turn this off, the **Search** and **CC** options won't be available during playback of a meeting recording.</span></span> <span data-ttu-id="05a8d-209">启动录制的人员需要启用此设置，以便录制还包括脚本。</span><span class="sxs-lookup"><span data-stu-id="05a8d-209">The person who started the recording needs this setting turned on so that the recording also includes transcription.</span></span> 

<span data-ttu-id="05a8d-210">请注意，当前只有在团队中将语言设置为英语且在会议中朗读英语的用户才支持使用录制的会议。</span><span class="sxs-lookup"><span data-stu-id="05a8d-210">Note that transcription for recorded meetings is currently only supported for users who have the language in Teams set to English and when English is spoken in the meeting.</span></span>

![显示会议中的脚本选项的屏幕截图](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a><span data-ttu-id="05a8d-212">允许云录制</span><span class="sxs-lookup"><span data-stu-id="05a8d-212">Allow cloud recording</span></span>

<span data-ttu-id="05a8d-213">这是每个组织单位和每用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="05a8d-213">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="05a8d-214">此设置控制是否可以录制此用户的会议。</span><span class="sxs-lookup"><span data-stu-id="05a8d-214">This setting controls whether this user's meetings can be recorded.</span></span> <span data-ttu-id="05a8d-215">录制可以由会议组织者或其他会议参与者启动（如果为参与者启用了该策略设置，并且他们是来自同一组织的经过身份验证的用户）。</span><span class="sxs-lookup"><span data-stu-id="05a8d-215">The recording can be started by the meeting organizer or by another meeting participant if the policy setting is turned on for the participant and if they're an authenticated user from the same organization.</span></span>

<span data-ttu-id="05a8d-216">组织外部的人员（如联盟用户和匿名用户）无法启动录制。</span><span class="sxs-lookup"><span data-stu-id="05a8d-216">People outside your organization, such as federated and anonymous users, can't start the recording.</span></span> <span data-ttu-id="05a8d-217">来宾用户无法启动或停止录制。</span><span class="sxs-lookup"><span data-stu-id="05a8d-217">Guest users can't start or stop the recording.</span></span> 

![显示录制选项的屏幕截图](media/meeting-policies-recording.png)

<span data-ttu-id="05a8d-219">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="05a8d-219">Let's look at the following example.</span></span>

|<span data-ttu-id="05a8d-220">用户</span><span class="sxs-lookup"><span data-stu-id="05a8d-220">User</span></span> |<span data-ttu-id="05a8d-221">会议策略</span><span class="sxs-lookup"><span data-stu-id="05a8d-221">Meeting policy</span></span>  |<span data-ttu-id="05a8d-222">允许云录制</span><span class="sxs-lookup"><span data-stu-id="05a8d-222">Allow cloud recording</span></span> |
|---------|---------|---------|
|<span data-ttu-id="05a8d-223">Daniela</span><span class="sxs-lookup"><span data-stu-id="05a8d-223">Daniela</span></span> | <span data-ttu-id="05a8d-224">全局</span><span class="sxs-lookup"><span data-stu-id="05a8d-224">Global</span></span>   | <span data-ttu-id="05a8d-225">False</span><span class="sxs-lookup"><span data-stu-id="05a8d-225">False</span></span> |
|<span data-ttu-id="05a8d-226">Amanda</span><span class="sxs-lookup"><span data-stu-id="05a8d-226">Amanda</span></span> | <span data-ttu-id="05a8d-227">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="05a8d-227">Location1MeetingPolicy</span></span> | <span data-ttu-id="05a8d-228">True</span><span class="sxs-lookup"><span data-stu-id="05a8d-228">True</span></span>|
|<span data-ttu-id="05a8d-229">John （外部用户）</span><span class="sxs-lookup"><span data-stu-id="05a8d-229">John (external user)</span></span> | <span data-ttu-id="05a8d-230">不适用</span><span class="sxs-lookup"><span data-stu-id="05a8d-230">Not applicable</span></span> | <span data-ttu-id="05a8d-231">不适用</span><span class="sxs-lookup"><span data-stu-id="05a8d-231">Not applicable</span></span>|

<span data-ttu-id="05a8d-232">按 Daniela 组织的会议无法录制，并且 Amanda 已启用策略设置，无法录制 Daniela 组织的会议。</span><span class="sxs-lookup"><span data-stu-id="05a8d-232">Meetings organized by Daniela can't be recorded and Amanda, who has the policy setting enabled, can't record meetings organized by Daniela.</span></span> <span data-ttu-id="05a8d-233">可记录由 Amanda 组织的会议，但 Daniela，他们已禁用策略设置，并且 John 是外部用户，无法录制 Amanda 组织的会议。</span><span class="sxs-lookup"><span data-stu-id="05a8d-233">Meetings organized by Amanda can be recorded, however,  Daniela, who has the policy setting disabled and John who is an external user, can't record meetings organized by Amanda.</span></span>

<span data-ttu-id="05a8d-234">若要了解有关云会议录制的详细信息，请参阅[团队云会议录制](cloud-recording.md)。</span><span class="sxs-lookup"><span data-stu-id="05a8d-234">To learn more about cloud meeting recording, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

### <a name="allow-ip-video"></a><span data-ttu-id="05a8d-235">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="05a8d-235">Allow IP video</span></span>

<span data-ttu-id="05a8d-236">这是每个组织单位和每用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="05a8d-236">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="05a8d-237">视频是会议的关键组件。</span><span class="sxs-lookup"><span data-stu-id="05a8d-237">Video is a key component to meetings.</span></span> <span data-ttu-id="05a8d-238">在某些组织中，管理员可能希望更好地控制哪些用户的会议有视频。</span><span class="sxs-lookup"><span data-stu-id="05a8d-238">In some organizations, admins might want more control over which users’ meetings have video.</span></span> <span data-ttu-id="05a8d-239">此设置控制是否可以在用户托管的会议中以及用户开始的1:1 呼叫和组通话中打开视频。</span><span class="sxs-lookup"><span data-stu-id="05a8d-239">This setting controls whether video can be turned on in meetings hosted by a user and in 1:1 calls and group calls started by a user.</span></span> <span data-ttu-id="05a8d-240">已启用此策略的用户组织的会议，如果会议参与者也启用了该策略，则会议参与者允许会议中的视频共享。</span><span class="sxs-lookup"><span data-stu-id="05a8d-240">Meetings organized by a user who has this policy enabled, allow video sharing in the meeting by the meeting participants, if the meeting participants also have the policy enabled.</span></span> <span data-ttu-id="05a8d-241">未分配任何策略的会议参与者（如匿名和联盟参与者）将继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="05a8d-241">Meeting participants who don't have any policies assigned (for example, anonymous and federated participants) inherit the policy of the meeting organizer.</span></span>

![显示带有音频和视频设置的会议的屏幕截图](media/meeting-policies-audio-video-settings.png)

<span data-ttu-id="05a8d-243">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="05a8d-243">Let's look at the following example.</span></span>

|<span data-ttu-id="05a8d-244">用户</span><span class="sxs-lookup"><span data-stu-id="05a8d-244">User</span></span> |<span data-ttu-id="05a8d-245">会议策略</span><span class="sxs-lookup"><span data-stu-id="05a8d-245">Meeting policy</span></span>  |<span data-ttu-id="05a8d-246">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="05a8d-246">Allow IP Video</span></span> |
|---------|---------|---------|
|<span data-ttu-id="05a8d-247">Daniela</span><span class="sxs-lookup"><span data-stu-id="05a8d-247">Daniela</span></span>   | <span data-ttu-id="05a8d-248">全局</span><span class="sxs-lookup"><span data-stu-id="05a8d-248">Global</span></span>   | <span data-ttu-id="05a8d-249">True</span><span class="sxs-lookup"><span data-stu-id="05a8d-249">True</span></span>        |
|<span data-ttu-id="05a8d-250">Amanda</span><span class="sxs-lookup"><span data-stu-id="05a8d-250">Amanda</span></span>    | <span data-ttu-id="05a8d-251">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="05a8d-251">Location1MeetingPolicy</span></span>        | <span data-ttu-id="05a8d-252">False</span><span class="sxs-lookup"><span data-stu-id="05a8d-252">False</span></span>      |

<span data-ttu-id="05a8d-253">通过 Daniela 托管的会议允许打开视频。</span><span class="sxs-lookup"><span data-stu-id="05a8d-253">Meetings hosted by Daniela allow video to be turned on.</span></span> <span data-ttu-id="05a8d-254">Daniela 可以加入会议并打开视频。</span><span class="sxs-lookup"><span data-stu-id="05a8d-254">Daniela can join the meeting and turn on video.</span></span> <span data-ttu-id="05a8d-255">Amanda 无法在 Daniela 的会议中启用视频，因为 Amanda 的策略设置为 "不允许视频"。</span><span class="sxs-lookup"><span data-stu-id="05a8d-255">Amanda can't turn on video in Daniela's meeting because Amanda’s policy is set to not allow video.</span></span> <span data-ttu-id="05a8d-256">Amanda 可以查看会议中其他参与者共享的视频。</span><span class="sxs-lookup"><span data-stu-id="05a8d-256">Amanda can see videos shared by other participants in the meeting.</span></span>

<span data-ttu-id="05a8d-257">在 Amanda 托管的会议中，无论分配给他们的视频策略如何，任何人都无法打开视频。</span><span class="sxs-lookup"><span data-stu-id="05a8d-257">In meetings hosted by Amanda, no one can turn on video, regardless of the video policy assigned to them.</span></span> <span data-ttu-id="05a8d-258">这意味着 Daniela 无法在 Amanda 的会议中打开视频。</span><span class="sxs-lookup"><span data-stu-id="05a8d-258">This means Daniela can't turn on video in Amanda’s meetings.</span></span>  

<span data-ttu-id="05a8d-259">如果 Daniela 通过视频 Amanda 调用，Amanda 只能通过音频应答呼叫。</span><span class="sxs-lookup"><span data-stu-id="05a8d-259">If Daniela calls Amanda with video on, Amanda can answer the call with audio only.</span></span>  <span data-ttu-id="05a8d-260">当呼叫连接时，Amanda 可以看到 Daniela 的视频，但无法打开视频。</span><span class="sxs-lookup"><span data-stu-id="05a8d-260">When the call is connected, Amanda can see Daniela’s video, but can't turn on video.</span></span> <span data-ttu-id="05a8d-261">如果 Amanda 呼叫 Daniela，Daniela 可以通过视频和音频接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="05a8d-261">If Amanda calls Daniela, Daniela can answer the call with video and audio.</span></span> <span data-ttu-id="05a8d-262">通话接通后，Daniela 可以根据需要打开或关闭她的视频。</span><span class="sxs-lookup"><span data-stu-id="05a8d-262">When the call is connected, Daniela can turn on or turn off her video, as needed.</span></span>

### <a name="media-bit-rate-kbs"></a><span data-ttu-id="05a8d-263">媒体比特率（KBs）</span><span class="sxs-lookup"><span data-stu-id="05a8d-263">Media bit rate (KBs)</span></span>

<span data-ttu-id="05a8d-264">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="05a8d-264">This is a per-user policy.</span></span> <span data-ttu-id="05a8d-265">此设置确定用户的通话和会议中音频、视频和基于视频的应用共享传输的媒体比特率。</span><span class="sxs-lookup"><span data-stu-id="05a8d-265">This setting determines the media bit rate for audio, video, and video-based app sharing transmissions in calls and meetings for the user.</span></span> <span data-ttu-id="05a8d-266">它同时应用于呼叫或会议中用户的上行媒体和下行媒体遍历。</span><span class="sxs-lookup"><span data-stu-id="05a8d-266">It's applied to both the uplink and downlink media traversal for users in the call or meeting.</span></span> <span data-ttu-id="05a8d-267">此设置使你能够更细致地控制组织中的带宽管理。</span><span class="sxs-lookup"><span data-stu-id="05a8d-267">This setting gives you granular control over managing bandwidth in your organization.</span></span> <span data-ttu-id="05a8d-268">根据用户所需的会议方案，我们建议有足够的带宽来实现优质体验。</span><span class="sxs-lookup"><span data-stu-id="05a8d-268">Depending on the meetings scenarios required by users, we recommend having enough bandwidth in place for a good quality experience.</span></span> <span data-ttu-id="05a8d-269">最小值为 30 Kbps，最大值取决于会议方案。</span><span class="sxs-lookup"><span data-stu-id="05a8d-269">The minimum value is 30 Kbps and the maximum value depends on the meeting scenario.</span></span> <span data-ttu-id="05a8d-270">若要了解更多有关建议的最小带宽以供团队的优质会议、通话和实时活动，请参阅[带宽要求](prepare-network.md#bandwidth-requirements)。</span><span class="sxs-lookup"><span data-stu-id="05a8d-270">To learn more about the minimum recommended bandwidth for good quality meetings, calls, and live events in Teams, see [Bandwidth requirements](prepare-network.md#bandwidth-requirements).</span></span>

<span data-ttu-id="05a8d-271">如果会议带宽不足，参与者会看到指示网络质量不佳的消息。</span><span class="sxs-lookup"><span data-stu-id="05a8d-271">If there isn’t enough bandwidth for a meeting, participants see a message that indicates poor network quality.</span></span>

<span data-ttu-id="05a8d-272">对于需要最高质量视频体验的会议（如 CEO 董事会会议和团队现场活动），我们建议您将带宽设置为 10 Mbps。</span><span class="sxs-lookup"><span data-stu-id="05a8d-272">For meetings that need the highest quality video experience, such as CEO board meetings and Teams live events, we recommend you set the bandwidth to 10 Mbps.</span></span> <span data-ttu-id="05a8d-273">即使设置了最大体验，团队媒体堆栈也会在检测到某些网络条件时适应低带宽条件，具体取决于方案。</span><span class="sxs-lookup"><span data-stu-id="05a8d-273">Even when the maximum experience is set, the Teams media stack adapts to low bandwidth conditions when certain network conditions are detected, depending on the scenario.</span></span> 

### <a name="enable-live-captions-preview"></a><span data-ttu-id="05a8d-274">启用实时字幕（预览）</span><span class="sxs-lookup"><span data-stu-id="05a8d-274">Enable live captions (preview)</span></span>

<span data-ttu-id="05a8d-275">这是每用户策略，在会议期间应用。</span><span class="sxs-lookup"><span data-stu-id="05a8d-275">This is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="05a8d-276">此设置控制用户是否可以使用 "**打开实时标题**" 选项来打开和关闭用户出席的会议中的实时字幕。</span><span class="sxs-lookup"><span data-stu-id="05a8d-276">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![显示 "打开实时字幕" 选项的屏幕截图](media/meeting-policies-live-captions.png)

|<span data-ttu-id="05a8d-278">设置值</span><span class="sxs-lookup"><span data-stu-id="05a8d-278">Setting value</span></span> |<span data-ttu-id="05a8d-279">行为</span><span class="sxs-lookup"><span data-stu-id="05a8d-279">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="05a8d-280">**已禁用，用户可以替代**</span><span class="sxs-lookup"><span data-stu-id="05a8d-280">**Disabled and the user can override**</span></span>     | <span data-ttu-id="05a8d-281">会议期间不会为用户自动打开实时字幕。</span><span class="sxs-lookup"><span data-stu-id="05a8d-281">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="05a8d-282">用户可以在 "溢出（**...**）" 菜单中看到 "**打开实时标题**" 选项以将其打开。</span><span class="sxs-lookup"><span data-stu-id="05a8d-282">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="05a8d-283">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="05a8d-283">This is the default setting.</span></span> |
|<span data-ttu-id="05a8d-284">**已禁用**</span><span class="sxs-lookup"><span data-stu-id="05a8d-284">**Disabled**</span></span>     | <span data-ttu-id="05a8d-285">会议期间，用户已禁用实时字幕。</span><span class="sxs-lookup"><span data-stu-id="05a8d-285">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="05a8d-286">用户不能选择将其打开。</span><span class="sxs-lookup"><span data-stu-id="05a8d-286">The user doesn't have the option to turn them on.</span></span>          |


<span data-ttu-id="05a8d-287"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="05a8d-287"></span></span>

## <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="05a8d-288">会议策略设置-内容共享</span><span class="sxs-lookup"><span data-stu-id="05a8d-288">Meeting policy settings - Content sharing</span></span>

- [<span data-ttu-id="05a8d-289">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="05a8d-289">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="05a8d-290">允许参与者授予或请求控制</span><span class="sxs-lookup"><span data-stu-id="05a8d-290">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="05a8d-291">允许外部参与者授予或请求控制</span><span class="sxs-lookup"><span data-stu-id="05a8d-291">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="05a8d-292">允许 PowerPoint 共享</span><span class="sxs-lookup"><span data-stu-id="05a8d-292">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="05a8d-293">允许白板</span><span class="sxs-lookup"><span data-stu-id="05a8d-293">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="05a8d-294">允许共享笔记</span><span class="sxs-lookup"><span data-stu-id="05a8d-294">Allow shared notes</span></span>](#allow-shared-notes)
- [<span data-ttu-id="05a8d-295">允许在会议中聊天（即将推出）</span><span class="sxs-lookup"><span data-stu-id="05a8d-295">Allow chat in meetings (coming soon)</span></span>](#allow-chat-in-meetings-coming-soon)

### <a name="screen-sharing-mode"></a><span data-ttu-id="05a8d-296">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="05a8d-296">Screen sharing mode</span></span>

<span data-ttu-id="05a8d-297">这是每个组织单位和每用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="05a8d-297">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="05a8d-298">此设置控制是否允许在用户的会议中共享桌面和/或窗口共享。</span><span class="sxs-lookup"><span data-stu-id="05a8d-298">This setting controls whether desktop and/or window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="05a8d-299">未分配任何策略的会议参与者（如匿名、来宾、B2B 和联盟参与者）将继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="05a8d-299">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="05a8d-300">设置值</span><span class="sxs-lookup"><span data-stu-id="05a8d-300">Setting value</span></span> |<span data-ttu-id="05a8d-301">行为</span><span class="sxs-lookup"><span data-stu-id="05a8d-301">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="05a8d-302">**整个屏幕**</span><span class="sxs-lookup"><span data-stu-id="05a8d-302">**Entire screen**</span></span>    | <span data-ttu-id="05a8d-303">会议中允许进行完整的桌面共享和应用程序共享</span><span class="sxs-lookup"><span data-stu-id="05a8d-303">Full desktop sharing and application sharing is allowed in the meeting</span></span> |
|<span data-ttu-id="05a8d-304">**单应用程序**</span><span class="sxs-lookup"><span data-stu-id="05a8d-304">**Single application**</span></span>   | <span data-ttu-id="05a8d-305">允许在会议中共享应用程序</span><span class="sxs-lookup"><span data-stu-id="05a8d-305">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="05a8d-306">**已禁用**</span><span class="sxs-lookup"><span data-stu-id="05a8d-306">**Disabled**</span></span>     |<span data-ttu-id="05a8d-307">会议中已关闭屏幕共享和应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="05a8d-307">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="05a8d-308">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="05a8d-308">Let's look at the following example.</span></span>

|<span data-ttu-id="05a8d-309">用户</span><span class="sxs-lookup"><span data-stu-id="05a8d-309">User</span></span> |<span data-ttu-id="05a8d-310">会议策略</span><span class="sxs-lookup"><span data-stu-id="05a8d-310">Meeting policy</span></span> |<span data-ttu-id="05a8d-311">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="05a8d-311">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="05a8d-312">Daniela</span><span class="sxs-lookup"><span data-stu-id="05a8d-312">Daniela</span></span>  | <span data-ttu-id="05a8d-313">全局</span><span class="sxs-lookup"><span data-stu-id="05a8d-313">Global</span></span>   | <span data-ttu-id="05a8d-314">整个屏幕</span><span class="sxs-lookup"><span data-stu-id="05a8d-314">Entire screen</span></span> |
|<span data-ttu-id="05a8d-315">Amanda</span><span class="sxs-lookup"><span data-stu-id="05a8d-315">Amanda</span></span>   | <span data-ttu-id="05a8d-316">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="05a8d-316">Location1MeetingPolicy</span></span>  | <span data-ttu-id="05a8d-317">已禁用</span><span class="sxs-lookup"><span data-stu-id="05a8d-317">Disabled</span></span> |

<span data-ttu-id="05a8d-318">由 Daniela 托管的会议允许会议参与者共享其整个屏幕或特定应用程序。</span><span class="sxs-lookup"><span data-stu-id="05a8d-318">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="05a8d-319">如果 Amanda 加入 Daniela 的会议，Amanda 无法共享她的屏幕或特定应用程序，因为她的策略设置已被禁用。</span><span class="sxs-lookup"><span data-stu-id="05a8d-319">If Amanda joins Daniela’s meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="05a8d-320">在 Amanda 托管的会议中，不允许任何人共享其屏幕或单个应用程序，而不管分配给他们的屏幕共享模式策略如何。</span><span class="sxs-lookup"><span data-stu-id="05a8d-320">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span> <span data-ttu-id="05a8d-321">这意味着 Daniela 不能在 Amanda 的会议中共享她的屏幕或单个应用程序。</span><span class="sxs-lookup"><span data-stu-id="05a8d-321">This means that Daniela can't share her screen or a single application in Amanda’s meetings.</span></span>  

<span data-ttu-id="05a8d-322">当前，如果用户使用的是 Google Chrome，则用户无法在团队会议中播放视频或共享其屏幕。</span><span class="sxs-lookup"><span data-stu-id="05a8d-322">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

### <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="05a8d-323">允许参与者授予或请求控制</span><span class="sxs-lookup"><span data-stu-id="05a8d-323">Allow a participant to give or request control</span></span>

<span data-ttu-id="05a8d-324">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="05a8d-324">This is a per-user policy.</span></span> <span data-ttu-id="05a8d-325">此设置控制用户是否可以将共享桌面或窗口的控制权授予其他会议参与者。</span><span class="sxs-lookup"><span data-stu-id="05a8d-325">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="05a8d-326">若要赋予控制权，请将鼠标悬停在屏幕顶部。</span><span class="sxs-lookup"><span data-stu-id="05a8d-326">To give control, hover over the top of the screen.</span></span> 

<span data-ttu-id="05a8d-327">如果为用户启用此设置，则 "**授予控制权**" 选项显示在共享会话的顶部栏中。</span><span class="sxs-lookup"><span data-stu-id="05a8d-327">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span> 

![显示 "提供控制" 选项的屏幕截图](media/meeting-policies-give-control.png)

<span data-ttu-id="05a8d-329">如果用户的设置处于关闭状态，则 "**提供控制**" 选项不可用。</span><span class="sxs-lookup"><span data-stu-id="05a8d-329">If the settings is turned off for the user, the **Give Control** option isn't available.</span></span>

![显示 "提供控件" 选项不可用的屏幕截图](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="05a8d-331">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="05a8d-331">Let's look at the following example.</span></span>

|<span data-ttu-id="05a8d-332">用户</span><span class="sxs-lookup"><span data-stu-id="05a8d-332">User</span></span> |<span data-ttu-id="05a8d-333">会议策略</span><span class="sxs-lookup"><span data-stu-id="05a8d-333">Meeting policy</span></span>  |<span data-ttu-id="05a8d-334">允许参与者授予或请求控制</span><span class="sxs-lookup"><span data-stu-id="05a8d-334">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="05a8d-335">Daniela</span><span class="sxs-lookup"><span data-stu-id="05a8d-335">Daniela</span></span>   | <span data-ttu-id="05a8d-336">全局</span><span class="sxs-lookup"><span data-stu-id="05a8d-336">Global</span></span>   | <span data-ttu-id="05a8d-337">True</span><span class="sxs-lookup"><span data-stu-id="05a8d-337">True</span></span>       |
|<span data-ttu-id="05a8d-338">Babek</span><span class="sxs-lookup"><span data-stu-id="05a8d-338">Babek</span></span>    | <span data-ttu-id="05a8d-339">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="05a8d-339">Location1MeetingPolicy</span></span>        | <span data-ttu-id="05a8d-340">False</span><span class="sxs-lookup"><span data-stu-id="05a8d-340">False</span></span>   |

<span data-ttu-id="05a8d-341">Daniela 可以将共享桌面或窗口的控制权交给 Babek 组织的会议中的其他参与者，Babek 无法将控制权授予其他参与者。</span><span class="sxs-lookup"><span data-stu-id="05a8d-341">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek whereas Babek can't give control to other participants.</span></span>

<span data-ttu-id="05a8d-342">若要使用 PowerShell 控制哪些人可以授予控制请求或接受控制请求，请使用 AllowParticipantGiveRequestControl cmdlet。</span><span class="sxs-lookup"><span data-stu-id="05a8d-342">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="05a8d-343">若要在共享期间提供和控制共享内容，双方都必须使用团队桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="05a8d-343">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="05a8d-344">如果任何一方在浏览器中运行 Teams，则不支持控制。</span><span class="sxs-lookup"><span data-stu-id="05a8d-344">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="05a8d-345">这是由我们计划修复的一个技术限制造成。</span><span class="sxs-lookup"><span data-stu-id="05a8d-345">This is due to a technical limitation that we're planning to fix.</span></span> 

### <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="05a8d-346">允许外部参与者授予或请求控制</span><span class="sxs-lookup"><span data-stu-id="05a8d-346">Allow an external participant to give or request control</span></span>

<span data-ttu-id="05a8d-347">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="05a8d-347">This is a per-user policy.</span></span> <span data-ttu-id="05a8d-348">此设置控制会议中的外部参与者是否可以将其共享桌面或窗口的控制权交给会议中的其他参与者。</span><span class="sxs-lookup"><span data-stu-id="05a8d-348">This setting controls whether external participants in a meeting can give control of their shared desktop or window to other participants in the meeting.</span></span> <span data-ttu-id="05a8d-349">团队会议中的外部参与者可以按如下方式进行分类：</span><span class="sxs-lookup"><span data-stu-id="05a8d-349">External participants in Teams meetings can be categorized as follows:</span></span>  

   - <span data-ttu-id="05a8d-350">匿名用户</span><span class="sxs-lookup"><span data-stu-id="05a8d-350">Anonymous user</span></span>
   - <span data-ttu-id="05a8d-351">来宾用户</span><span class="sxs-lookup"><span data-stu-id="05a8d-351">Guest users</span></span>  
   - <span data-ttu-id="05a8d-352">B2B 用户</span><span class="sxs-lookup"><span data-stu-id="05a8d-352">B2B user</span></span>
   - <span data-ttu-id="05a8d-353">联合用户</span><span class="sxs-lookup"><span data-stu-id="05a8d-353">Federated user</span></span>  

<span data-ttu-id="05a8d-354">联盟用户是否可以向外部用户授予控制权，同时共享受允许外部参与者在其组织中**授予或请求控制**设置的控制。</span><span class="sxs-lookup"><span data-stu-id="05a8d-354">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="05a8d-355">若要使用 PowerShell 控制外部参与者是否可以授予控制或接受控制请求，请使用 AllowExternalParticipantGiveRequestControl cmdlet。</span><span class="sxs-lookup"><span data-stu-id="05a8d-355">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="05a8d-356">允许 PowerPoint 共享</span><span class="sxs-lookup"><span data-stu-id="05a8d-356">Allow PowerPoint sharing</span></span>

<span data-ttu-id="05a8d-357">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="05a8d-357">This is a per-user policy.</span></span> <span data-ttu-id="05a8d-358">此设置控制用户是否可以在会议中共享 PowerPoint 幻灯片放映。</span><span class="sxs-lookup"><span data-stu-id="05a8d-358">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="05a8d-359">外部用户（包括匿名用户、来宾和联盟用户）继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="05a8d-359">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="05a8d-360">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="05a8d-360">Let's look at the following example.</span></span>

|<span data-ttu-id="05a8d-361">用户</span><span class="sxs-lookup"><span data-stu-id="05a8d-361">User</span></span> |<span data-ttu-id="05a8d-362">会议策略</span><span class="sxs-lookup"><span data-stu-id="05a8d-362">Meeting policy</span></span>  |<span data-ttu-id="05a8d-363">允许 PowerPoint 共享</span><span class="sxs-lookup"><span data-stu-id="05a8d-363">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="05a8d-364">Daniela</span><span class="sxs-lookup"><span data-stu-id="05a8d-364">Daniela</span></span>   | <span data-ttu-id="05a8d-365">全局</span><span class="sxs-lookup"><span data-stu-id="05a8d-365">Global</span></span>   | <span data-ttu-id="05a8d-366">True</span><span class="sxs-lookup"><span data-stu-id="05a8d-366">True</span></span>       |
|<span data-ttu-id="05a8d-367">Amanda</span><span class="sxs-lookup"><span data-stu-id="05a8d-367">Amanda</span></span>   | <span data-ttu-id="05a8d-368">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="05a8d-368">Location1MeetingPolicy</span></span>        | <span data-ttu-id="05a8d-369">False</span><span class="sxs-lookup"><span data-stu-id="05a8d-369">False</span></span>   |

<span data-ttu-id="05a8d-370">Amanda 不能在会议中共享 PowerPoint 幻灯片卡座，即使她是会议组织者也是如此。</span><span class="sxs-lookup"><span data-stu-id="05a8d-370">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="05a8d-371">Daniela 可以共享 PowerPoint 幻灯片放映，即使会议由 Amanda 组织。</span><span class="sxs-lookup"><span data-stu-id="05a8d-371">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="05a8d-372">Amanda 可以查看会议中其他人共享的 PowerPoint 幻灯片卡座，即使她无法共享 PowerPoint 幻灯片放映。</span><span class="sxs-lookup"><span data-stu-id="05a8d-372">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

### <a name="allow-whiteboard"></a><span data-ttu-id="05a8d-373">允许白板</span><span class="sxs-lookup"><span data-stu-id="05a8d-373">Allow whiteboard</span></span>

<span data-ttu-id="05a8d-374">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="05a8d-374">This is a per-user policy.</span></span> <span data-ttu-id="05a8d-375">此设置控制用户是否可以在会议中共享白板。</span><span class="sxs-lookup"><span data-stu-id="05a8d-375">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="05a8d-376">外部用户（包括匿名用户、B2B 和联盟用户）继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="05a8d-376">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> 

<span data-ttu-id="05a8d-377">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="05a8d-377">Let's look at the following example.</span></span>

|<span data-ttu-id="05a8d-378">用户</span><span class="sxs-lookup"><span data-stu-id="05a8d-378">User</span></span> |<span data-ttu-id="05a8d-379">会议策略</span><span class="sxs-lookup"><span data-stu-id="05a8d-379">Meeting policy</span></span>  |<span data-ttu-id="05a8d-380">允许白板</span><span class="sxs-lookup"><span data-stu-id="05a8d-380">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="05a8d-381">Daniela</span><span class="sxs-lookup"><span data-stu-id="05a8d-381">Daniela</span></span>   | <span data-ttu-id="05a8d-382">全局</span><span class="sxs-lookup"><span data-stu-id="05a8d-382">Global</span></span>   | <span data-ttu-id="05a8d-383">True</span><span class="sxs-lookup"><span data-stu-id="05a8d-383">True</span></span>       |
|<span data-ttu-id="05a8d-384">Amanda</span><span class="sxs-lookup"><span data-stu-id="05a8d-384">Amanda</span></span>   | <span data-ttu-id="05a8d-385">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="05a8d-385">Location1MeetingPolicy</span></span>        | <span data-ttu-id="05a8d-386">False</span><span class="sxs-lookup"><span data-stu-id="05a8d-386">False</span></span>   |

<span data-ttu-id="05a8d-387">Amanda 无法在会议中共享白板，即使她是会议组织者也是如此。</span><span class="sxs-lookup"><span data-stu-id="05a8d-387">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="05a8d-388">即使会议是按 Amanda 组织的，Daniela 也可以共享白板。</span><span class="sxs-lookup"><span data-stu-id="05a8d-388">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

### <a name="allow-shared-notes"></a><span data-ttu-id="05a8d-389">允许共享笔记</span><span class="sxs-lookup"><span data-stu-id="05a8d-389">Allow shared notes</span></span>

<span data-ttu-id="05a8d-390">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="05a8d-390">This is a per-user policy.</span></span> <span data-ttu-id="05a8d-391">此设置控制用户是否可以在会议中创建和共享笔记。</span><span class="sxs-lookup"><span data-stu-id="05a8d-391">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="05a8d-392">外部用户（包括匿名用户、B2B 和联盟用户）继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="05a8d-392">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="05a8d-393">"**会议笔记**" 选项卡目前仅在具有少于20个参与者的会议中受支持。</span><span class="sxs-lookup"><span data-stu-id="05a8d-393">The **Meeting Notes** tab is currently only supported in meetings that have less than 20 participants.</span></span> 

<span data-ttu-id="05a8d-394">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="05a8d-394">Let's look at the following example.</span></span>

|<span data-ttu-id="05a8d-395">用户</span><span class="sxs-lookup"><span data-stu-id="05a8d-395">User</span></span> |<span data-ttu-id="05a8d-396">会议策略</span><span class="sxs-lookup"><span data-stu-id="05a8d-396">Meeting policy</span></span>  |<span data-ttu-id="05a8d-397">允许共享笔记</span><span class="sxs-lookup"><span data-stu-id="05a8d-397">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="05a8d-398">Daniela</span><span class="sxs-lookup"><span data-stu-id="05a8d-398">Daniela</span></span>   | <span data-ttu-id="05a8d-399">全局</span><span class="sxs-lookup"><span data-stu-id="05a8d-399">Global</span></span>   | <span data-ttu-id="05a8d-400">True</span><span class="sxs-lookup"><span data-stu-id="05a8d-400">True</span></span>       |
|<span data-ttu-id="05a8d-401">Amanda</span><span class="sxs-lookup"><span data-stu-id="05a8d-401">Amanda</span></span>   | <span data-ttu-id="05a8d-402">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="05a8d-402">Location1MeetingPolicy</span></span> | <span data-ttu-id="05a8d-403">False</span><span class="sxs-lookup"><span data-stu-id="05a8d-403">False</span></span> |

<span data-ttu-id="05a8d-404">Daniela 可以在 Amanda 的会议中做笔记，Amanda 不能在任何会议中做笔记。</span><span class="sxs-lookup"><span data-stu-id="05a8d-404">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>

### <a name="allow-chat-in-meetings-coming-soon"></a><span data-ttu-id="05a8d-405">允许在会议中聊天（即将推出）</span><span class="sxs-lookup"><span data-stu-id="05a8d-405">Allow chat in meetings (coming soon)</span></span>

<span data-ttu-id="05a8d-406">这是每个组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="05a8d-406">This is a per-organizer policy.</span></span> <span data-ttu-id="05a8d-407">此设置控制是否允许在用户的会议中使用会议聊天。</span><span class="sxs-lookup"><span data-stu-id="05a8d-407">This setting controls whether meeting chat is allowed in the user's meeting.</span></span> 

<span data-ttu-id="05a8d-408"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="05a8d-408"></span></span>

## <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="05a8d-409">会议策略设置-参与者 & 来宾</span><span class="sxs-lookup"><span data-stu-id="05a8d-409">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="05a8d-410">这些设置控制在会议厅中等待的会议参与者，以及他们在会议中允许的参与级别。</span><span class="sxs-lookup"><span data-stu-id="05a8d-410">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="05a8d-411">自动允许人员</span><span class="sxs-lookup"><span data-stu-id="05a8d-411">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="05a8d-412">允许匿名用户启动会议</span><span class="sxs-lookup"><span data-stu-id="05a8d-412">Allow anonymous people to start a meeting</span></span>](#allow-anonymous-people-to-start-a-meeting)
- [<span data-ttu-id="05a8d-413">允许拨入用户绕过大厅</span><span class="sxs-lookup"><span data-stu-id="05a8d-413">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby-coming-soon)

> [!NOTE]
><span data-ttu-id="05a8d-414">用于加入会议的选项会有所不同，具体取决于每个团队组的设置和连接方法。</span><span class="sxs-lookup"><span data-stu-id="05a8d-414">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="05a8d-415">如果你的组具有音频会议，并使用它进行连接，请参阅[Office 365 中的音频会议](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="05a8d-415">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing in Office 365](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="05a8d-416">如果你的团队组没有音频会议，请参阅[在团队中加入会议](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)。</span><span class="sxs-lookup"><span data-stu-id="05a8d-416">If your Teams group does not have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

### <a name="automatically-admit-people"></a><span data-ttu-id="05a8d-417">自动允许人员</span><span class="sxs-lookup"><span data-stu-id="05a8d-417">Automatically admit people</span></span>

<span data-ttu-id="05a8d-418">这是每个组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="05a8d-418">This is a per-organizer policy.</span></span> <span data-ttu-id="05a8d-419">此设置控制用户是否直接加入会议或在大厅中等待，直到他们被经过身份验证的用户许可。</span><span class="sxs-lookup"><span data-stu-id="05a8d-419">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span>

![显示会议厅中有用户的会议的屏幕截图](media/meeting-policies-lobby.png)

 <span data-ttu-id="05a8d-421">会议组织者可以单击会议邀请中的 "**会议选项**"，为其计划的每个会议更改此设置。</span><span class="sxs-lookup"><span data-stu-id="05a8d-421">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span> <span data-ttu-id="05a8d-422">**（即将推出）**</span><span class="sxs-lookup"><span data-stu-id="05a8d-422">**(coming soon)**</span></span>
  
|<span data-ttu-id="05a8d-423">设置值</span><span class="sxs-lookup"><span data-stu-id="05a8d-423">Setting value</span></span>  |<span data-ttu-id="05a8d-424">联接行为</span><span class="sxs-lookup"><span data-stu-id="05a8d-424">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="05a8d-425">**人均**</span><span class="sxs-lookup"><span data-stu-id="05a8d-425">**Everyone**</span></span>   |<span data-ttu-id="05a8d-426">所有会议参与者都直接加入会议，而无需在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="05a8d-426">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="05a8d-427">这包括经过身份验证的用户、联盟用户、来宾、匿名用户和通过电话拨入的用户。</span><span class="sxs-lookup"><span data-stu-id="05a8d-427">This includes authenticated users, federated users, guests, anonymous users, and people who dial in by phone.</span></span>       |
|<span data-ttu-id="05a8d-428">**组织和联盟组织中的每个人**</span><span class="sxs-lookup"><span data-stu-id="05a8d-428">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="05a8d-429">组织内的经过身份验证的用户，包括来宾用户和联盟组织中的用户，直接加入会议，而无需在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="05a8d-429">Authenticated users within the organization, including guest users and the users from federated organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="05a8d-430">通过电话拨入的匿名用户和用户在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="05a8d-430">Anonymous users and users who dial in by phone wait in the lobby.</span></span>   |
|<span data-ttu-id="05a8d-431">**您的组织中的每个人**</span><span class="sxs-lookup"><span data-stu-id="05a8d-431">**Everyone in your organization**</span></span>    |<span data-ttu-id="05a8d-432">来自组织内部的经过身份验证的用户（包括来宾用户）直接加入会议，而无需在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="05a8d-432">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="05a8d-433">联合用户、匿名用户和通过电话拨入的用户在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="05a8d-433">Federated users, anonymous users, and users who dial in by phone wait in the lobby.</span></span>           |

### <a name="allow-anonymous-people-to-start-a-meeting"></a><span data-ttu-id="05a8d-434">允许匿名用户启动会议</span><span class="sxs-lookup"><span data-stu-id="05a8d-434">Allow anonymous people to start a meeting</span></span>

<span data-ttu-id="05a8d-435">这是每个组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="05a8d-435">This is a per-organizer policy.</span></span> <span data-ttu-id="05a8d-436">此设置控制匿名人员（包括 B2B）和联盟用户是否可以在没有经过身份验证的组织中加入用户的会议。</span><span class="sxs-lookup"><span data-stu-id="05a8d-436">This setting controls whether anonymous people, including B2B, and federated users, can join the user's meeting without an authenticated user from the organization in attendance.</span></span> 

![显示一条消息给正在等待的用户的屏幕截图](media/meeting-policies-anonymous-user-lobby.png)

<span data-ttu-id="05a8d-438">下面是在会议中提供了身份验证用户时匿名用户的加入行为。</span><span class="sxs-lookup"><span data-stu-id="05a8d-438">Here's the join behavior of anonymous people when authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="05a8d-439">允许匿名用户启动会议</span><span class="sxs-lookup"><span data-stu-id="05a8d-439">Allow anonymous people to start a meeting</span></span>  |<span data-ttu-id="05a8d-440">自动允许人员</span><span class="sxs-lookup"><span data-stu-id="05a8d-440">Automatically admit people</span></span> |<span data-ttu-id="05a8d-441">匿名人员的加入行为</span><span class="sxs-lookup"><span data-stu-id="05a8d-441">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="05a8d-442">True</span><span class="sxs-lookup"><span data-stu-id="05a8d-442">True</span></span>    | <span data-ttu-id="05a8d-443">人均</span><span class="sxs-lookup"><span data-stu-id="05a8d-443">Everyone</span></span>      | <span data-ttu-id="05a8d-444">直接加入</span><span class="sxs-lookup"><span data-stu-id="05a8d-444">Join directly</span></span>         |
|   | <span data-ttu-id="05a8d-445">您的组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="05a8d-445">Everyone in your organization</span></span>       | <span data-ttu-id="05a8d-446">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="05a8d-446">Wait in lobby</span></span>        |
|   | <span data-ttu-id="05a8d-447">组织和联盟组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="05a8d-447">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="05a8d-448">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="05a8d-448">Wait in lobby</span></span>         |
|<span data-ttu-id="05a8d-449">False</span><span class="sxs-lookup"><span data-stu-id="05a8d-449">False</span></span>    | <span data-ttu-id="05a8d-450">人均</span><span class="sxs-lookup"><span data-stu-id="05a8d-450">Everyone</span></span>        | <span data-ttu-id="05a8d-451">直接加入</span><span class="sxs-lookup"><span data-stu-id="05a8d-451">Join directly</span></span>        |
|   | <span data-ttu-id="05a8d-452">您的组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="05a8d-452">Everyone in your organization</span></span>     | <span data-ttu-id="05a8d-453">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="05a8d-453">Wait in lobby</span></span>        |
|   | <span data-ttu-id="05a8d-454">组织和联盟组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="05a8d-454">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="05a8d-455">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="05a8d-455">Wait in lobby</span></span>         |

<span data-ttu-id="05a8d-456">下面是当会议中没有经过身份验证的用户时匿名用户的加入行为。</span><span class="sxs-lookup"><span data-stu-id="05a8d-456">Here's the join behavior of anonymous people when no authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="05a8d-457">允许匿名用户启动会议</span><span class="sxs-lookup"><span data-stu-id="05a8d-457">Allow anonymous people to start a meeting</span></span> |<span data-ttu-id="05a8d-458">自动允许人员</span><span class="sxs-lookup"><span data-stu-id="05a8d-458">Automatically admit people</span></span>  |<span data-ttu-id="05a8d-459">匿名人员的加入行为</span><span class="sxs-lookup"><span data-stu-id="05a8d-459">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="05a8d-460">True</span><span class="sxs-lookup"><span data-stu-id="05a8d-460">True</span></span>    | <span data-ttu-id="05a8d-461">人均</span><span class="sxs-lookup"><span data-stu-id="05a8d-461">Everyone</span></span>      | <span data-ttu-id="05a8d-462">直接加入</span><span class="sxs-lookup"><span data-stu-id="05a8d-462">Join directly</span></span>         |
|   | <span data-ttu-id="05a8d-463">您的组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="05a8d-463">Everyone in your organization</span></span>       | <span data-ttu-id="05a8d-464">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="05a8d-464">Wait in lobby</span></span>        |
|   | <span data-ttu-id="05a8d-465">组织和联盟组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="05a8d-465">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="05a8d-466">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="05a8d-466">Wait in lobby</span></span>         |
|<span data-ttu-id="05a8d-467">False</span><span class="sxs-lookup"><span data-stu-id="05a8d-467">False</span></span>    | <span data-ttu-id="05a8d-468">人均</span><span class="sxs-lookup"><span data-stu-id="05a8d-468">Everyone</span></span>        | <span data-ttu-id="05a8d-469">在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="05a8d-469">Wait in lobby.</span></span> <span data-ttu-id="05a8d-470">当第一个经过身份验证的用户加入会议时，将自动向用户提供许可。</span><span class="sxs-lookup"><span data-stu-id="05a8d-470">Users are automatically admitted when the first authenticated user joins the meeting.</span></span>        |
|   | <span data-ttu-id="05a8d-471">您的组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="05a8d-471">Everyone in your organization</span></span>     |<span data-ttu-id="05a8d-472">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="05a8d-472">Wait in lobby</span></span>         |
|   | <span data-ttu-id="05a8d-473">组织和联盟组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="05a8d-473">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="05a8d-474">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="05a8d-474">Wait in lobby</span></span>         |

### <a name="allow-dial-in-users-to-bypass-the-lobby-coming-soon"></a><span data-ttu-id="05a8d-475">允许拨入用户绕过大厅（即将推出）</span><span class="sxs-lookup"><span data-stu-id="05a8d-475">Allow dial-in users to bypass the lobby (coming soon)</span></span>

<span data-ttu-id="05a8d-476">这是每个组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="05a8d-476">This is a per-organizer policy.</span></span> <span data-ttu-id="05a8d-477">此设置控制通过电话拨入的用户是否直接加入会议或在会议厅中等待，而不管 "是否**自动允许人员**" 设置。</span><span class="sxs-lookup"><span data-stu-id="05a8d-477">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span>

<span data-ttu-id="05a8d-478">下面是通过电话拨入的用户的加入行为。</span><span class="sxs-lookup"><span data-stu-id="05a8d-478">Here's the join behavior of people who dial in by phone.</span></span>

|<span data-ttu-id="05a8d-479">允许拨入用户绕过大厅</span><span class="sxs-lookup"><span data-stu-id="05a8d-479">Allow dial-in users to bypass the lobby</span></span>  |<span data-ttu-id="05a8d-480">自动允许用户</span><span class="sxs-lookup"><span data-stu-id="05a8d-480">Automatically admit users</span></span>  |<span data-ttu-id="05a8d-481">拨入的用户的加入行为</span><span class="sxs-lookup"><span data-stu-id="05a8d-481">Join behavior of people who dial in</span></span> |
|---------|---------|---------|
|<span data-ttu-id="05a8d-482">True</span><span class="sxs-lookup"><span data-stu-id="05a8d-482">True</span></span>    | <span data-ttu-id="05a8d-483">人均</span><span class="sxs-lookup"><span data-stu-id="05a8d-483">Everyone</span></span>      | <span data-ttu-id="05a8d-484">直接加入</span><span class="sxs-lookup"><span data-stu-id="05a8d-484">Join directly</span></span>         |
|   | <span data-ttu-id="05a8d-485">您的组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="05a8d-485">Everyone in your organization</span></span>       | <span data-ttu-id="05a8d-486">直接加入</span><span class="sxs-lookup"><span data-stu-id="05a8d-486">Join directly</span></span>        |
|   | <span data-ttu-id="05a8d-487">组织和联盟组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="05a8d-487">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="05a8d-488">直接加入</span><span class="sxs-lookup"><span data-stu-id="05a8d-488">Join directly</span></span>         |
|<span data-ttu-id="05a8d-489">False</span><span class="sxs-lookup"><span data-stu-id="05a8d-489">False</span></span>    | <span data-ttu-id="05a8d-490">人均</span><span class="sxs-lookup"><span data-stu-id="05a8d-490">Everyone</span></span>        | <span data-ttu-id="05a8d-491">直接加入</span><span class="sxs-lookup"><span data-stu-id="05a8d-491">Join directly</span></span>        |
|   | <span data-ttu-id="05a8d-492">您的组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="05a8d-492">Everyone in your organization</span></span>     |<span data-ttu-id="05a8d-493">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="05a8d-493">Wait in lobby</span></span>         |
|   | <span data-ttu-id="05a8d-494">组织和联盟组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="05a8d-494">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="05a8d-495">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="05a8d-495">Wait in lobby</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="05a8d-496">相关主题</span><span class="sxs-lookup"><span data-stu-id="05a8d-496">Related topics</span></span>
[<span data-ttu-id="05a8d-497">团队中的消息传递策略</span><span class="sxs-lookup"><span data-stu-id="05a8d-497">Messaging policies in Teams</span></span>](messaging-policies-in-teams.md)
