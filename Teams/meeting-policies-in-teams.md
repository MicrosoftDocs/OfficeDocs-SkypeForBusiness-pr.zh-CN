---
title: 管理会议策略
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.date: 05/14/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
f1keywords:
- ms.teamsadmincenter.meetingpolicies.overview
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- ms.teamsadmincenter.meetingpolicies.contentsharing
- ms.teamsadmincenter.meetingpolicies.general
- ms.teamsadmincenter.meetingpolicies.participantandguests
description: 了解如何管理会议团队中的策略设置。
ms.openlocfilehash: 99458e71ae02eb6307b3f363dbf7e060e1b4ed5b
ms.sourcegitcommit: 85b135cf622c9e9eb1857ef953bc618dc2cdb51e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "34036626"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="87eb6-103">管理团队中的会议策略</span><span class="sxs-lookup"><span data-stu-id="87eb6-103">Manage meeting policies in Teams</span></span>

::: zone target="docs"
<span data-ttu-id="87eb6-104">会议策略用于控制对会议的组织中的用户安排的会议的参与者可用的功能。</span><span class="sxs-lookup"><span data-stu-id="87eb6-104">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="87eb6-105">在创建策略，并进行更改后，您可以然后用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="87eb6-105">After you create a policy and make your changes, you can then assign users to the policy.</span></span> <span data-ttu-id="87eb6-106">管理会议策略中的 Microsoft 团队管理中心或使用[PowerShell](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="87eb6-106">You manage meeting policies in the Microsoft Teams admin center or by [using PowerShell](teams-powershell-overview.md).</span></span>

<span data-ttu-id="87eb6-107">您可以按以下方式，这会影响会议开始之前用户的会议体验实施策略开始，在会议期间或之后会议。</span><span class="sxs-lookup"><span data-stu-id="87eb6-107">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span> 

|<span data-ttu-id="87eb6-108">实现类型</span><span class="sxs-lookup"><span data-stu-id="87eb6-108">Implementation type</span></span>  |<span data-ttu-id="87eb6-109">说明</span><span class="sxs-lookup"><span data-stu-id="87eb6-109">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="87eb6-110">每个组织者</span><span class="sxs-lookup"><span data-stu-id="87eb6-110">Per-organizer</span></span>    |<span data-ttu-id="87eb6-111">实现的每个组织者策略时，所有会议参与者都继承的组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="87eb6-111">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="87eb6-112">例如，**自动允许人员加入**是每个组织者策略和控制用户加入会议直接还是在分配策略的用户安排的会议会议厅中等待的选择。</span><span class="sxs-lookup"><span data-stu-id="87eb6-112">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="87eb6-113">每个用户</span><span class="sxs-lookup"><span data-stu-id="87eb6-113">Per-user</span></span>    |<span data-ttu-id="87eb6-114">实现的每用户策略时，仅将每用户策略应用于限制为组织者和/或会议参与者的某些功能。</span><span class="sxs-lookup"><span data-stu-id="87eb6-114">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="87eb6-115">例如，**允许立即开会**为每用户策略。</span><span class="sxs-lookup"><span data-stu-id="87eb6-115">For example, **Allow Meet now** is a per-user policy.</span></span>     |
|<span data-ttu-id="87eb6-116">每个组织者和每个用户</span><span class="sxs-lookup"><span data-stu-id="87eb6-116">Per-organizer and per-user</span></span>     |<span data-ttu-id="87eb6-117">当实现的每个组织者和每用户策略的组合时，则某些功能将限制会议参与者基于其策略和组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="87eb6-117">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="87eb6-118">例如，**允许云录制**是每个组织者和每用户策略。</span><span class="sxs-lookup"><span data-stu-id="87eb6-118">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="87eb6-119">启用此设置，以允许会议组织者和参与者启动和停止录制。</span><span class="sxs-lookup"><span data-stu-id="87eb6-119">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span> 

<span data-ttu-id="87eb6-120">默认情况下，创建名为全局 （组织范围内默认值） 的策略。</span><span class="sxs-lookup"><span data-stu-id="87eb6-120">By default, a policy named Global (org-wide default) is created.</span></span> <span data-ttu-id="87eb6-121">默认情况下，您的组织中的所有用户将都分配此会议策略。</span><span class="sxs-lookup"><span data-stu-id="87eb6-121">All users in your organization will be assigned this meeting policy by default.</span></span> <span data-ttu-id="87eb6-122">可以更改此策略，或创建一个或多个自定义策略并向其分配用户。</span><span class="sxs-lookup"><span data-stu-id="87eb6-122">You can either make changes to this policy or create one or more custom policies and assign users to them.</span></span> <span data-ttu-id="87eb6-123">创建自定义策略时，可以允许或防止某些功能提供给用户，然后将其分配给一个或多个用户拥有应用于它们的设置。</span><span class="sxs-lookup"><span data-stu-id="87eb6-123">When you create a custom policy, you can allow or prevent certain features from being available to your users, and then assign it to one or more users who will have the settings applied to them.</span></span> 

## <a name="change-or-create-a-meeting-policy"></a><span data-ttu-id="87eb6-124">更改或创建的会议策略</span><span class="sxs-lookup"><span data-stu-id="87eb6-124">Change or create a meeting policy</span></span>

<span data-ttu-id="87eb6-125">若要更改或创建的会议策略，请转到 Microsoft 团队管理中心 >**会议** > **会议策略**。</span><span class="sxs-lookup"><span data-stu-id="87eb6-125">To change or create a meeting policy, go to the Microsoft Teams admin center > **Meetings** > **Meeting policies**.</span></span> <span data-ttu-id="87eb6-126">从列表中选择一个策略，或选择**新策略**。</span><span class="sxs-lookup"><span data-stu-id="87eb6-126">Select a policy from the list or select **New policy**.</span></span> <span data-ttu-id="87eb6-127">如果您正在创建新策略，将添加的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="87eb6-127">If you're creating a new policy, add a name and description.</span></span> <span data-ttu-id="87eb6-128">名称不能包含特殊字符也能超过 64 个字符。</span><span class="sxs-lookup"><span data-stu-id="87eb6-128">The name can't contain special characters or be longer than 64 characters.</span></span> <span data-ttu-id="87eb6-129">选择您的设置，然后选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="87eb6-129">Choose your settings, and then select **Save**.</span></span>

<span data-ttu-id="87eb6-130">例如，假设您有大量的用户，并且想要限制其会议将需要的带宽量。</span><span class="sxs-lookup"><span data-stu-id="87eb6-130">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="87eb6-131">您可以创建名为"带宽有限"的新自定义策略，并禁用以下设置：</span><span class="sxs-lookup"><span data-stu-id="87eb6-131">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="87eb6-132">在**音频 & 视频**: 下</span><span class="sxs-lookup"><span data-stu-id="87eb6-132">Under **Audio & video**:</span></span>
- <span data-ttu-id="87eb6-133">关闭云录制</span><span class="sxs-lookup"><span data-stu-id="87eb6-133">Turn off cloud recording</span></span>
- <span data-ttu-id="87eb6-134">关闭允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="87eb6-134">Turn off Allow IP video</span></span>

<span data-ttu-id="87eb6-135">在**内容共享**: 下</span><span class="sxs-lookup"><span data-stu-id="87eb6-135">Under **Content sharing**:</span></span>
- <span data-ttu-id="87eb6-136">禁用屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="87eb6-136">Disable screen sharing mode</span></span>
- <span data-ttu-id="87eb6-137">关闭白板</span><span class="sxs-lookup"><span data-stu-id="87eb6-137">Turn off whiteboard</span></span>
- <span data-ttu-id="87eb6-138">关闭共享便笺</span><span class="sxs-lookup"><span data-stu-id="87eb6-138">Turn off shared notes</span></span>

<span data-ttu-id="87eb6-139">然后将策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="87eb6-139">Then assign the policy to the users.</span></span>

> [!NOTE] 
> <span data-ttu-id="87eb6-140">用户可以一次只能有一个会议策略分配。</span><span class="sxs-lookup"><span data-stu-id="87eb6-140">A user can be assigned only one meeting policy at a time.</span></span> 

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="87eb6-141">向用户分配的会议策略</span><span class="sxs-lookup"><span data-stu-id="87eb6-141">Assign a meeting policy to users</span></span>

<span data-ttu-id="87eb6-142">如果要将策略应用于一个用户，在左侧的导航窗格中，选择**用户**，然后单击用户的显示名称。</span><span class="sxs-lookup"><span data-stu-id="87eb6-142">If you're applying the policy to one user, select **Users** on the left navigation pane, and then click the user's display name.</span></span> <span data-ttu-id="87eb6-143">选择用户的页上，单击**分配策略**，旁边的**编辑**。</span><span class="sxs-lookup"><span data-stu-id="87eb6-143">On the user's page, next to **Assigned policies**, select **Edit**.</span></span> <span data-ttu-id="87eb6-144">然后，在**编辑用户策略**窗格中的**会议策略**，下，从下拉列表中，选择会议策略，然后选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="87eb6-144">Then, in the **Edit user policies** pane, under **Meeting policy**, select the meeting policy from the drop-down list, and then select **Save**.</span></span> <span data-ttu-id="87eb6-145">您可以从用户的列表来分配策略。</span><span class="sxs-lookup"><span data-stu-id="87eb6-145">You can also assign policies from the list of users.</span></span> <span data-ttu-id="87eb6-146">若要执行此操作，请通过单击左侧的用户的显示名称选择用户。</span><span class="sxs-lookup"><span data-stu-id="87eb6-146">To do this, select the user by clicking to the left of the user's display name.</span></span> <span data-ttu-id="87eb6-147">选择**编辑设置**。</span><span class="sxs-lookup"><span data-stu-id="87eb6-147">Select **Edit settings**.</span></span> <span data-ttu-id="87eb6-148">然后，**编辑设置**窗格中的**会议策略**，下，从下拉列表中，选择的策略，然后选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="87eb6-148">Then, on the **Edit settings** pane, under **Meeting policy**, select the policy from the drop-down list, and then select **Save**.</span></span> 
 
<span data-ttu-id="87eb6-149">如果要将策略应用于多个用户，在左侧的导航窗格中，选择**用户**，然后通过单击左侧的用户名称，选择每个用户，然后单击**编辑设置**。</span><span class="sxs-lookup"><span data-stu-id="87eb6-149">If you're applying a policy to more than one user, select **Users** on the left navigation pane, and then select each user by clicking to the left of the user name, and then click **Edit settings**.</span></span> <span data-ttu-id="87eb6-150">在**编辑设置**窗格中，**会议策略**，下从下拉列表中，选择策略，然后选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="87eb6-150">On the **Edit Settings** pane, under **Meeting policy**, select the policy from the drop-down list, and then select **Save**.</span></span>
 
<span data-ttu-id="87eb6-151">按如下方式向一个或多个用户还可以分配的会议策略：</span><span class="sxs-lookup"><span data-stu-id="87eb6-151">You can also assign a meeting policy to one or more users as follows:</span></span>

1. <span data-ttu-id="87eb6-152">转到**Microsoft 团队管理中心** > **会议** > **会议策略**。</span><span class="sxs-lookup"><span data-stu-id="87eb6-152">Go to **Microsoft Teams admin center** > **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="87eb6-153">通过单击左侧的策略名称选择的策略。</span><span class="sxs-lookup"><span data-stu-id="87eb6-153">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="87eb6-154">选择**管理用户**。</span><span class="sxs-lookup"><span data-stu-id="87eb6-154">Select **Manage users**.</span></span>
4. <span data-ttu-id="87eb6-155">在**管理用户**窗格中，搜索用户按显示名称或用户名称，选择名称，然后选择**添加**。</span><span class="sxs-lookup"><span data-stu-id="87eb6-155">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="87eb6-156">要添加的每个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="87eb6-156">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="87eb6-157">完成添加用户时，选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="87eb6-157">When you're finished adding users, select **Save**.</span></span>
 
> [!NOTE] 
> <span data-ttu-id="87eb6-158">不能删除策略，如果用户已分配给它。</span><span class="sxs-lookup"><span data-stu-id="87eb6-158">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="87eb6-159">您必须首先将不同的策略分配给所有受影响的用户，然后可以删除原始的策略。</span><span class="sxs-lookup"><span data-stu-id="87eb6-159">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>
 
## <a name="meeting-policy-settings"></a><span data-ttu-id="87eb6-160">会议策略设置</span><span class="sxs-lookup"><span data-stu-id="87eb6-160">Meeting policy settings</span></span>

<span data-ttu-id="87eb6-161">当您选择**会议策略**页上的现有策略，或选择要添加新的策略的**新策略**时，您可以配置以下设置。</span><span class="sxs-lookup"><span data-stu-id="87eb6-161">When you select an existing policy on the **Meeting policies** page or select **New policy** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="87eb6-162">常规</span><span class="sxs-lookup"><span data-stu-id="87eb6-162">General</span></span>](#meeting-policy-settings---general)
- [<span data-ttu-id="87eb6-163">音频 & 视频</span><span class="sxs-lookup"><span data-stu-id="87eb6-163">Audio & video</span></span>](#meeting-policy-settings---audio--video)
- [<span data-ttu-id="87eb6-164">内容共享</span><span class="sxs-lookup"><span data-stu-id="87eb6-164">Content sharing</span></span>](#meeting-policy-settings---content-sharing)
- [<span data-ttu-id="87eb6-165">参与者 & 来宾</span><span class="sxs-lookup"><span data-stu-id="87eb6-165">Participants & guests</span></span>](#meeting-policy-settings---participants--guests)

::: zone-end 

<span data-ttu-id="87eb6-166"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="87eb6-166"></span></span>

## <a name="meeting-policy-settings---general"></a><span data-ttu-id="87eb6-167">会议策略设置-常规</span><span class="sxs-lookup"><span data-stu-id="87eb6-167">Meeting policy settings - General</span></span>

- [<span data-ttu-id="87eb6-168">在通道允许立即开会</span><span class="sxs-lookup"><span data-stu-id="87eb6-168">Allow Meet now in channels</span></span>](#allow-meet-now-in-channels)
- [<span data-ttu-id="87eb6-169">允许专用立即开会 （即将推出）</span><span class="sxs-lookup"><span data-stu-id="87eb6-169">Allow private Meet now (coming soon)</span></span>](#allow-private-meet-now-coming-soon)
- [<span data-ttu-id="87eb6-170">允许 Outlook 外接程序</span><span class="sxs-lookup"><span data-stu-id="87eb6-170">Allow the Outlook add-in</span></span>](#allow-the-outlook-add-in)
- [<span data-ttu-id="87eb6-171">允许通道会议日程安排</span><span class="sxs-lookup"><span data-stu-id="87eb6-171">Allow channel meeting scheduling</span></span>](#allow-channel-meeting-scheduling)
- [<span data-ttu-id="87eb6-172">允许安排专用会议</span><span class="sxs-lookup"><span data-stu-id="87eb6-172">Allow scheduling private meetings</span></span>](#allow-scheduling-private-meetings)

### <a name="allow-meet-now-in-channels"></a><span data-ttu-id="87eb6-173">在通道允许立即开会</span><span class="sxs-lookup"><span data-stu-id="87eb6-173">Allow Meet now in channels</span></span>

<span data-ttu-id="87eb6-174">这是一个每用户策略，并将应用会议之前启动。</span><span class="sxs-lookup"><span data-stu-id="87eb6-174">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="87eb6-175">此设置控制用户是否可以在工作组通道中启动临时会议。</span><span class="sxs-lookup"><span data-stu-id="87eb6-175">This setting controls whether a user can start an ad-hoc meeting in a Teams channel.</span></span> <span data-ttu-id="87eb6-176">如果您关闭此上，当用户在工作组频道发布一条消息，用户可以单击**立即开会**下方撰写框以在该频道中启动临时会议。</span><span class="sxs-lookup"><span data-stu-id="87eb6-176">If you turn this on, when a user posts a message in a Teams channel, the user can click **Meet now** beneath the compose box to start an ad-hoc meeting in the channel.</span></span>

![会议策略开会会议 now.png](media/meeting-policies-meet-now.png)

### <a name="allow-private-meet-now-coming-soon"></a><span data-ttu-id="87eb6-178">允许专用立即开会 （即将推出）</span><span class="sxs-lookup"><span data-stu-id="87eb6-178">Allow private Meet now (coming soon)</span></span>

<span data-ttu-id="87eb6-179">这是一个每用户策略，并将应用会议之前启动。</span><span class="sxs-lookup"><span data-stu-id="87eb6-179">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="87eb6-180">此设置控制用户是否可以开始临时专用会议。</span><span class="sxs-lookup"><span data-stu-id="87eb6-180">This setting controls whether a user can start an ad hoc private meeting.</span></span>  

### <a name="allow-the-outlook-add-in"></a><span data-ttu-id="87eb6-181">允许 Outlook 外接程序</span><span class="sxs-lookup"><span data-stu-id="87eb6-181">Allow the Outlook add-in</span></span>

<span data-ttu-id="87eb6-182">这是一个每用户策略，并将应用会议之前启动。</span><span class="sxs-lookup"><span data-stu-id="87eb6-182">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="87eb6-183">此设置控制是否可以在 Outlook （Windows、 Mac、 web 和移动） 从计划团队会议。</span><span class="sxs-lookup"><span data-stu-id="87eb6-183">This setting controls whether Teams meetings can be scheduled from within Outlook (Windows, Mac, web, and mobile).</span></span>

![会议的策略-outlook-添加-in.png](media/meeting-policies-outlook-add-in.png)

<span data-ttu-id="87eb6-185">如果您关闭此操作，用户将无法在 Outlook 中创建新的会议时安排团队会议。</span><span class="sxs-lookup"><span data-stu-id="87eb6-185">If you turn this off, users are unable to schedule Teams meetings when they create a new meeting in Outlook.</span></span> <span data-ttu-id="87eb6-186">例如，在 Windows 上的 Outlook 中，**新团队会议**选项不会显示在功能区中。</span><span class="sxs-lookup"><span data-stu-id="87eb6-186">For example, in Outlook on Windows, the **New Teams Meeting** option won't show up in the ribbon.</span></span>

### <a name="allow-channel-meeting-scheduling"></a><span data-ttu-id="87eb6-187">允许通道会议日程安排</span><span class="sxs-lookup"><span data-stu-id="87eb6-187">Allow channel meeting scheduling</span></span>

<span data-ttu-id="87eb6-188">这是一个每用户策略，并将应用会议之前启动。</span><span class="sxs-lookup"><span data-stu-id="87eb6-188">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="87eb6-189">此设置控制用户是否可以安排会议中的团队通道。</span><span class="sxs-lookup"><span data-stu-id="87eb6-189">This setting controls whether users can schedule a meeting in a Teams channel.</span></span>  <span data-ttu-id="87eb6-190">如果您关闭此操作，**计划会议**选项将不可用向用户，当他们团队通道中启动会议并他们安排会议在工作组中从会议时，**选择要满足通道**选项不会对用户可用。</span><span class="sxs-lookup"><span data-stu-id="87eb6-190">If you turn this off, the **Schedule a meeting** option won't be available to the user when they start a meeting in a Teams channel and the **Select a channel to meet** option won't be available to the user when they schedule a meeting from Meetings in Teams.</span></span>

![会议的策略-计划-a-meeting.png](media/meeting-policies-schedule-a-meeting.png)

![meeting-policies-select-a-channel-to-meet-in.png](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a><span data-ttu-id="87eb6-193">允许安排专用会议</span><span class="sxs-lookup"><span data-stu-id="87eb6-193">Allow scheduling private meetings</span></span>

<span data-ttu-id="87eb6-194">这是一个每用户策略，并将应用会议之前启动。</span><span class="sxs-lookup"><span data-stu-id="87eb6-194">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="87eb6-195">此设置控制用户是否可以安排团队中的专用会议。</span><span class="sxs-lookup"><span data-stu-id="87eb6-195">This setting controls whether users can schedule private meetings in Teams.</span></span> <span data-ttu-id="87eb6-196">不将其发布到团队中的通道时，会议是专用。</span><span class="sxs-lookup"><span data-stu-id="87eb6-196">A meeting is private when it's not published to a channel in a team.</span></span>

<span data-ttu-id="87eb6-197">请注意，如果您关闭**允许安排专用会议**和**允许通道会议日程安排\*\*\*\*计划会议**选项将不可用，用户将无法在工作组中安排会议。</span><span class="sxs-lookup"><span data-stu-id="87eb6-197">Note that if you turn off **Allow scheduling private meetings** and **Allow channel meeting scheduling**,  the **Schedule a meeting** option won't be available and users will be unable to schedule meetings in Teams.</span></span>

<span data-ttu-id="87eb6-198"><a name="bkaudioandvideo"> </a></span><span class="sxs-lookup"><span data-stu-id="87eb6-198"></span></span>

## <a name="meeting-policy-settings---audio--video"></a><span data-ttu-id="87eb6-199">会议策略设置-音频 & 视频</span><span class="sxs-lookup"><span data-stu-id="87eb6-199">Meeting policy settings - Audio & video</span></span>

- [<span data-ttu-id="87eb6-200">允许转录</span><span class="sxs-lookup"><span data-stu-id="87eb6-200">Allow transcription</span></span>](#allow-transcription)
- [<span data-ttu-id="87eb6-201">允许云录制</span><span class="sxs-lookup"><span data-stu-id="87eb6-201">Allow cloud recording</span></span>](#allow-cloud-recording)
- [<span data-ttu-id="87eb6-202">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="87eb6-202">Allow IP video</span></span>](#allow-ip-video)
- [<span data-ttu-id="87eb6-203">媒体比特率 (Kb)</span><span class="sxs-lookup"><span data-stu-id="87eb6-203">Media bit rate (KBs)</span></span>](#media-bit-rate-kbs)
- [<span data-ttu-id="87eb6-204">启用 live 标题 （即将推出）</span><span class="sxs-lookup"><span data-stu-id="87eb6-204">Enable live captions (coming soon)</span></span>](#enable-live-captions-coming-soon)

### <a name="allow-transcription"></a><span data-ttu-id="87eb6-205">允许转录</span><span class="sxs-lookup"><span data-stu-id="87eb6-205">Allow transcription</span></span>

<span data-ttu-id="87eb6-206">这是每个组织者和每用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="87eb6-206">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="87eb6-207">此设置控制标题和转录功能是否可用播放会议录制过程。</span><span class="sxs-lookup"><span data-stu-id="87eb6-207">This setting controls whether captions and transcription features are available during playback of meeting recordings.</span></span> <span data-ttu-id="87eb6-208">如果您关闭此操作，**搜索**和**抄送**选项将不可用播放会议录制过程。</span><span class="sxs-lookup"><span data-stu-id="87eb6-208">If you turn this off, the **Search** and **CC** options won't be available during playback of a meeting recording.</span></span> <span data-ttu-id="87eb6-209">启动录制的人员需要该设置，以便录制还包括转录开启。</span><span class="sxs-lookup"><span data-stu-id="87eb6-209">The person who started the recording needs this setting turned on so that the recording also includes transcription.</span></span> 

<span data-ttu-id="87eb6-210">请注意，录制的会议的转录目前仅支持用户拥有语言中设置为英语的团队和时将英语朗读会议中。</span><span class="sxs-lookup"><span data-stu-id="87eb6-210">Note that transcription for recorded meetings is currently only supported for users who have the language in Teams set to English and when English is spoken in the meeting.</span></span>

![会议的策略-transcription.png](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a><span data-ttu-id="87eb6-212">允许云录制</span><span class="sxs-lookup"><span data-stu-id="87eb6-212">Allow cloud recording</span></span>

<span data-ttu-id="87eb6-213">这是每个组织者和每用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="87eb6-213">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="87eb6-214">此设置控制是否可以记录此用户的会议。</span><span class="sxs-lookup"><span data-stu-id="87eb6-214">This setting controls whether this user's meetings can be recorded.</span></span> <span data-ttu-id="87eb6-215">录制可以启动由会议组织者或另一个会议参与者如果参与者为打开的策略设置，并且它们从同一组织身份验证的用户。</span><span class="sxs-lookup"><span data-stu-id="87eb6-215">The recording can be started by the meeting organizer or by another meeting participant if the policy setting is turned on for the participant and if they're an authenticated user from the same organization.</span></span>

<span data-ttu-id="87eb6-216">联盟和匿名用户，如组织外部的人员无法开始录制。</span><span class="sxs-lookup"><span data-stu-id="87eb6-216">People outside your organization, such as federated and anonymous users, can't start the recording.</span></span> <span data-ttu-id="87eb6-217">来宾用户无法启动或停止录制。</span><span class="sxs-lookup"><span data-stu-id="87eb6-217">Guest users can't start or stop the recording.</span></span> 

![会议的策略-recording.png](media/meeting-policies-recording.png)

<span data-ttu-id="87eb6-219">让我们看一下下面的示例。</span><span class="sxs-lookup"><span data-stu-id="87eb6-219">Let's look at the following example.</span></span>

|<span data-ttu-id="87eb6-220">用户</span><span class="sxs-lookup"><span data-stu-id="87eb6-220">User</span></span> |<span data-ttu-id="87eb6-221">会议策略</span><span class="sxs-lookup"><span data-stu-id="87eb6-221">Meeting policy</span></span>  |<span data-ttu-id="87eb6-222">允许云录制</span><span class="sxs-lookup"><span data-stu-id="87eb6-222">Allow cloud recording</span></span> |
|---------|---------|---------|
|<span data-ttu-id="87eb6-223">Daniela</span><span class="sxs-lookup"><span data-stu-id="87eb6-223">Daniela</span></span> | <span data-ttu-id="87eb6-224">全局</span><span class="sxs-lookup"><span data-stu-id="87eb6-224">Global</span></span>   | <span data-ttu-id="87eb6-225">False</span><span class="sxs-lookup"><span data-stu-id="87eb6-225">False</span></span> |
|<span data-ttu-id="87eb6-226">Amanda</span><span class="sxs-lookup"><span data-stu-id="87eb6-226">Amanda</span></span> | <span data-ttu-id="87eb6-227">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="87eb6-227">Location1MeetingPolicy</span></span> | <span data-ttu-id="87eb6-228">True</span><span class="sxs-lookup"><span data-stu-id="87eb6-228">True</span></span>|
|<span data-ttu-id="87eb6-229">John （外部用户）</span><span class="sxs-lookup"><span data-stu-id="87eb6-229">John (external user)</span></span> | <span data-ttu-id="87eb6-230">不适用</span><span class="sxs-lookup"><span data-stu-id="87eb6-230">Not applicable</span></span> | <span data-ttu-id="87eb6-231">不适用</span><span class="sxs-lookup"><span data-stu-id="87eb6-231">Not applicable</span></span>|

<span data-ttu-id="87eb6-232">无法录制 Daniela 由组织的会议并 Amanda，拥有启用此策略设置，无法记录由 Daniela 组织的会议。</span><span class="sxs-lookup"><span data-stu-id="87eb6-232">Meetings organized by Daniela can't be recorded and Amanda, who has the policy setting enabled, can't record meetings organized by Daniela.</span></span> <span data-ttu-id="87eb6-233">可以记录由 Amanda 组织的会议，但是，Daniela，拥有禁用此策略设置和 John 属于外部用户，无法记录由 Amanda 组织的会议。</span><span class="sxs-lookup"><span data-stu-id="87eb6-233">Meetings organized by Amanda can be recorded, however,  Daniela, who has the policy setting disabled and John who is an external user, can't record meetings organized by Amanda.</span></span>

<span data-ttu-id="87eb6-234">若要详细了解云会议录制，请参阅[团队云会议录制](cloud-recording.md)。</span><span class="sxs-lookup"><span data-stu-id="87eb6-234">To learn more about cloud meeting recording, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

### <a name="allow-ip-video"></a><span data-ttu-id="87eb6-235">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="87eb6-235">Allow IP video</span></span>

<span data-ttu-id="87eb6-236">这是每个组织者和每用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="87eb6-236">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="87eb6-237">视频会议的关键组件。</span><span class="sxs-lookup"><span data-stu-id="87eb6-237">Video is a key component to meetings.</span></span> <span data-ttu-id="87eb6-238">在某些组织中，管理员可能需要更多控制哪些用户的会议有视频。</span><span class="sxs-lookup"><span data-stu-id="87eb6-238">In some organizations, admins might want more control over which users’ meetings have video.</span></span> <span data-ttu-id="87eb6-239">此设置控制是否视频可以打开和 1:1 中由用户托管的会议呼叫和由用户启动的组呼叫。</span><span class="sxs-lookup"><span data-stu-id="87eb6-239">This setting controls whether video can be turned on in meetings hosted by a user and in 1:1 calls and group calls started by a user.</span></span> <span data-ttu-id="87eb6-240">已启用，此策略的用户组织的会议允许会议参与者，在会议中的视频共享如果会议参与者还可以启用的策略。</span><span class="sxs-lookup"><span data-stu-id="87eb6-240">Meetings organized by a user who has this policy enabled, allow video sharing in the meeting by the meeting participants, if the meeting participants also have the policy enabled.</span></span> <span data-ttu-id="87eb6-241">会议参与者未分配的任何策略 （例如，匿名和联盟参与者） 继承的会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="87eb6-241">Meeting participants who don't have any policies assigned (for example, anonymous and federated participants) inherit the policy of the meeting organizer.</span></span>

![会议的策略-音频-视频-settings.png](media/meeting-policies-audio-video-settings.png)

<span data-ttu-id="87eb6-243">让我们看一下下面的示例。</span><span class="sxs-lookup"><span data-stu-id="87eb6-243">Let's look at the following example.</span></span>

|<span data-ttu-id="87eb6-244">用户</span><span class="sxs-lookup"><span data-stu-id="87eb6-244">User</span></span> |<span data-ttu-id="87eb6-245">会议策略</span><span class="sxs-lookup"><span data-stu-id="87eb6-245">Meeting policy</span></span>  |<span data-ttu-id="87eb6-246">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="87eb6-246">Allow IP Video</span></span> |
|---------|---------|---------|
|<span data-ttu-id="87eb6-247">Daniela</span><span class="sxs-lookup"><span data-stu-id="87eb6-247">Daniela</span></span>   | <span data-ttu-id="87eb6-248">全局</span><span class="sxs-lookup"><span data-stu-id="87eb6-248">Global</span></span>   | <span data-ttu-id="87eb6-249">True</span><span class="sxs-lookup"><span data-stu-id="87eb6-249">True</span></span>        |
|<span data-ttu-id="87eb6-250">Amanda</span><span class="sxs-lookup"><span data-stu-id="87eb6-250">Amanda</span></span>    | <span data-ttu-id="87eb6-251">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="87eb6-251">Location1MeetingPolicy</span></span>        | <span data-ttu-id="87eb6-252">False</span><span class="sxs-lookup"><span data-stu-id="87eb6-252">False</span></span>      |

<span data-ttu-id="87eb6-253">允许视频以打开由 Daniela 承载的会议。</span><span class="sxs-lookup"><span data-stu-id="87eb6-253">Meetings hosted by Daniela allow video to be turned on.</span></span> <span data-ttu-id="87eb6-254">Daniela 可以加入会议，然后打开视频。</span><span class="sxs-lookup"><span data-stu-id="87eb6-254">Daniela can join the meeting and turn on video.</span></span> <span data-ttu-id="87eb6-255">Amanda 无法打开在 Daniela 的会议，因为 Amanda 的策略设置为不允许视频会议的视频。</span><span class="sxs-lookup"><span data-stu-id="87eb6-255">Amanda can't turn on video in Daniela's meeting because Amanda’s policy is set to not allow video.</span></span> <span data-ttu-id="87eb6-256">Amanda 可以看到视频会议中的其他参与者共享。</span><span class="sxs-lookup"><span data-stu-id="87eb6-256">Amanda can see videos shared by other participants in the meeting.</span></span>

<span data-ttu-id="87eb6-257">由 Amanda 承载的会议，没有人可以打开视频，无论视频的策略分配给它们。</span><span class="sxs-lookup"><span data-stu-id="87eb6-257">In meetings hosted by Amanda, no one can turn on video, regardless of the video policy assigned to them.</span></span> <span data-ttu-id="87eb6-258">这意味着 Daniela 无法打开在 Amanda 的会议中的视频。</span><span class="sxs-lookup"><span data-stu-id="87eb6-258">This means Daniela can't turn on video in Amanda’s meetings.</span></span>  

<span data-ttu-id="87eb6-259">如果 Daniela 上使用视频呼叫 Amanda，Amanda 可以应答呼叫以纯音频形式。</span><span class="sxs-lookup"><span data-stu-id="87eb6-259">If Daniela calls Amanda with video on, Amanda can answer the call with audio only.</span></span>  <span data-ttu-id="87eb6-260">当连接呼叫时，Amanda 可以看到 Daniela 的视频，但无法打开视频。</span><span class="sxs-lookup"><span data-stu-id="87eb6-260">When the call is connected, Amanda can see Daniela’s video, but can't turn on video.</span></span> <span data-ttu-id="87eb6-261">如果 Amanda 调用 Daniela，Daniela 可以应答的呼叫的视频和音频。</span><span class="sxs-lookup"><span data-stu-id="87eb6-261">If Amanda calls Daniela, Daniela can answer the call with video and audio.</span></span> <span data-ttu-id="87eb6-262">当连接呼叫时，Daniela 可以打开或关闭其视频中，根据需要。</span><span class="sxs-lookup"><span data-stu-id="87eb6-262">When the call is connected, Daniela can turn on or turn off her video, as needed.</span></span>

### <a name="media-bit-rate-kbs"></a><span data-ttu-id="87eb6-263">媒体比特率 (Kb)</span><span class="sxs-lookup"><span data-stu-id="87eb6-263">Media bit rate (KBs)</span></span>

<span data-ttu-id="87eb6-264">这是每个管理器策略。</span><span class="sxs-lookup"><span data-stu-id="87eb6-264">This is a per-organizer policy.</span></span> <span data-ttu-id="87eb6-265">此设置确定音频、 视频和视频基于应用程序共享呼叫和用户的会议中传输媒体比特率。</span><span class="sxs-lookup"><span data-stu-id="87eb6-265">This setting determines the media bit rate for audio, video, and video-based app sharing transmissions in calls and meetings for the user.</span></span> <span data-ttu-id="87eb6-266">其应用于的上行和下行媒体可以遍历呼叫或会议中的用户。</span><span class="sxs-lookup"><span data-stu-id="87eb6-266">It's applied to both the uplink and downlink media traversal for users in the call or meeting.</span></span> <span data-ttu-id="87eb6-267">此设置为您提供了管理组织中的带宽精细的控制。</span><span class="sxs-lookup"><span data-stu-id="87eb6-267">This setting gives you granular control over managing bandwidth in your organization.</span></span> <span data-ttu-id="87eb6-268">根据所需的用户的会议方案，建议您拥有足够带宽就地良好质量体验。</span><span class="sxs-lookup"><span data-stu-id="87eb6-268">Depending on the meetings scenarios required by users, we recommend having enough bandwidth in place for a good quality experience.</span></span> <span data-ttu-id="87eb6-269">最小值是 30 Kbps，最大值取决于会议方案。</span><span class="sxs-lookup"><span data-stu-id="87eb6-269">The minimum value is 30 Kbps and the maximum value depends on the meeting scenario.</span></span> <span data-ttu-id="87eb6-270">若要了解有关推荐带宽良好质量会议、 通话和团队中的实时事件的最小的详细信息，请参阅[带宽要求](prepare-network.md#bandwidth-requirements)。</span><span class="sxs-lookup"><span data-stu-id="87eb6-270">To learn more about the minimum recommended bandwidth for good quality meetings, calls, and live events in Teams, see [Bandwidth requirements](prepare-network.md#bandwidth-requirements).</span></span>

<span data-ttu-id="87eb6-271">如果没有足够带宽，会议，参与者将看到一条消息，指示网络质量不佳。</span><span class="sxs-lookup"><span data-stu-id="87eb6-271">If there isn’t enough bandwidth for a meeting, participants see a message that indicates poor network quality.</span></span>

<span data-ttu-id="87eb6-272">对于需要最高质量视频体验的会议，如 CEO 板会议和团队 live 事件，我们建议您将带宽设置为 10 Mbps。</span><span class="sxs-lookup"><span data-stu-id="87eb6-272">For meetings that need the highest quality video experience, such as CEO board meetings and Teams live events, we recommend you set the bandwidth to 10 Mbps.</span></span> <span data-ttu-id="87eb6-273">设置的最大的体验，即使团队媒体堆栈会适应低带宽的条件时检测到某些网络条件，具体取决于该方案。</span><span class="sxs-lookup"><span data-stu-id="87eb6-273">Even when the maximum experience is set, the Teams media stack adapts to low bandwidth conditions when certain network conditions are detected, depending on the scenario.</span></span> 

### <a name="enable-live-captions-coming-soon"></a><span data-ttu-id="87eb6-274">启用 live 标题 （即将推出）</span><span class="sxs-lookup"><span data-stu-id="87eb6-274">Enable live captions (coming soon)</span></span>

<span data-ttu-id="87eb6-275">这是一个每用户策略，并在会议期间适用。</span><span class="sxs-lookup"><span data-stu-id="87eb6-275">This is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="87eb6-276">如果在此设置，用户会看到一个选项，在会议期间显示标题。</span><span class="sxs-lookup"><span data-stu-id="87eb6-276">If this setting is on, the user sees an option to display captions during a meeting.</span></span>

<span data-ttu-id="87eb6-277"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="87eb6-277"></span></span>

## <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="87eb6-278">会议策略设置的内容共享</span><span class="sxs-lookup"><span data-stu-id="87eb6-278">Meeting policy settings - Content sharing</span></span>

- [<span data-ttu-id="87eb6-279">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="87eb6-279">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="87eb6-280">允许参与者授予或请求控制权</span><span class="sxs-lookup"><span data-stu-id="87eb6-280">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="87eb6-281">允许外部参与者授予或请求控制权</span><span class="sxs-lookup"><span data-stu-id="87eb6-281">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="87eb6-282">允许 PowerPoint 共享</span><span class="sxs-lookup"><span data-stu-id="87eb6-282">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="87eb6-283">允许白板</span><span class="sxs-lookup"><span data-stu-id="87eb6-283">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="87eb6-284">允许共享的便笺</span><span class="sxs-lookup"><span data-stu-id="87eb6-284">Allow shared notes</span></span>](#allow-shared-notes)
- [<span data-ttu-id="87eb6-285">（即将推出） 的会议中允许聊天</span><span class="sxs-lookup"><span data-stu-id="87eb6-285">Allow chat in meetings (coming soon)</span></span>](#allow-chat-in-meetings-coming-soon)

### <a name="screen-sharing-mode"></a><span data-ttu-id="87eb6-286">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="87eb6-286">Screen sharing mode</span></span>

<span data-ttu-id="87eb6-287">这是每个组织者和每用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="87eb6-287">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="87eb6-288">此设置控制是否桌面和/或窗口共享用户的会议中允许。</span><span class="sxs-lookup"><span data-stu-id="87eb6-288">This setting controls whether desktop and/or window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="87eb6-289">会议参与者未分配的任何策略 （的示例中，匿名、 来宾、 B2B 和联盟的参与者） 继承的会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="87eb6-289">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="87eb6-290">设置值</span><span class="sxs-lookup"><span data-stu-id="87eb6-290">Setting value</span></span> |<span data-ttu-id="87eb6-291">行为</span><span class="sxs-lookup"><span data-stu-id="87eb6-291">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="87eb6-292">**整个屏幕**</span><span class="sxs-lookup"><span data-stu-id="87eb6-292">**Entire screen**</span></span>    | <span data-ttu-id="87eb6-293">在会议中允许的完整桌面共享和应用程序共享</span><span class="sxs-lookup"><span data-stu-id="87eb6-293">Full desktop sharing and application sharing is allowed in the meeting</span></span> |
|<span data-ttu-id="87eb6-294">**单个应用程序**</span><span class="sxs-lookup"><span data-stu-id="87eb6-294">**Single application**</span></span>   | <span data-ttu-id="87eb6-295">在会议中允许，应用程序共享</span><span class="sxs-lookup"><span data-stu-id="87eb6-295">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="87eb6-296">**已禁用**</span><span class="sxs-lookup"><span data-stu-id="87eb6-296">**Disabled**</span></span>     |<span data-ttu-id="87eb6-297">屏幕共享和应用程序共享关闭会议中。</span><span class="sxs-lookup"><span data-stu-id="87eb6-297">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="87eb6-298">让我们看一下下面的示例。</span><span class="sxs-lookup"><span data-stu-id="87eb6-298">Let's look at the following example.</span></span>

|<span data-ttu-id="87eb6-299">用户</span><span class="sxs-lookup"><span data-stu-id="87eb6-299">User</span></span> |<span data-ttu-id="87eb6-300">会议策略</span><span class="sxs-lookup"><span data-stu-id="87eb6-300">Meeting policy</span></span> |<span data-ttu-id="87eb6-301">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="87eb6-301">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="87eb6-302">Daniela</span><span class="sxs-lookup"><span data-stu-id="87eb6-302">Daniela</span></span>  | <span data-ttu-id="87eb6-303">全局</span><span class="sxs-lookup"><span data-stu-id="87eb6-303">Global</span></span>   | <span data-ttu-id="87eb6-304">整个屏幕</span><span class="sxs-lookup"><span data-stu-id="87eb6-304">Entire screen</span></span> |
|<span data-ttu-id="87eb6-305">Amanda</span><span class="sxs-lookup"><span data-stu-id="87eb6-305">Amanda</span></span>   | <span data-ttu-id="87eb6-306">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="87eb6-306">Location1MeetingPolicy</span></span>  | <span data-ttu-id="87eb6-307">已禁用</span><span class="sxs-lookup"><span data-stu-id="87eb6-307">Disabled</span></span> |

<span data-ttu-id="87eb6-308">由 Daniela 承载的会议允许会议参与者共享其整个屏幕或特定应用程序。</span><span class="sxs-lookup"><span data-stu-id="87eb6-308">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="87eb6-309">如果 Amanda 加入 Daniela 的会议，Amanda 也不能共享其屏幕或特定应用程序，这是因为其策略设置已禁用。</span><span class="sxs-lookup"><span data-stu-id="87eb6-309">If Amanda joins Daniela’s meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="87eb6-310">由 Amanda 承载的会议中, 不允许任何人共享其屏幕或单个应用程序，无论屏幕共享模式策略分配给它们。</span><span class="sxs-lookup"><span data-stu-id="87eb6-310">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span> <span data-ttu-id="87eb6-311">这意味着 Daniela 不能共享其屏幕或 Amanda 的会议中的单个应用程序。</span><span class="sxs-lookup"><span data-stu-id="87eb6-311">This means that Daniela can't share her screen or a single application in Amanda’s meetings.</span></span>  

<span data-ttu-id="87eb6-312">目前，用户无法播放视频或共享其屏幕团队会议中的，如果他们正在使用 Google Chrome。</span><span class="sxs-lookup"><span data-stu-id="87eb6-312">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

### <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="87eb6-313">允许参与者授予或请求控制权</span><span class="sxs-lookup"><span data-stu-id="87eb6-313">Allow a participant to give or request control</span></span>

<span data-ttu-id="87eb6-314">这是一个每用户策略。</span><span class="sxs-lookup"><span data-stu-id="87eb6-314">This is a per-user policy.</span></span> <span data-ttu-id="87eb6-315">此设置控制用户是否可以共享的桌面或窗口的控制权移交给其他与会者。</span><span class="sxs-lookup"><span data-stu-id="87eb6-315">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="87eb6-316">要授予控制权，悬停在屏幕顶部。</span><span class="sxs-lookup"><span data-stu-id="87eb6-316">To give control, hover over the top of the screen.</span></span> 

<span data-ttu-id="87eb6-317">如果启用此设置是用户，**授予控制权**选项顶栏中显示在共享会话中。</span><span class="sxs-lookup"><span data-stu-id="87eb6-317">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span> 

![会议策略授予 control.png](media/meeting-policies-give-control.png)

<span data-ttu-id="87eb6-319">如果设置为用户已关闭，**授予控制权**选项不可用。</span><span class="sxs-lookup"><span data-stu-id="87eb6-319">If the settings is turned off for the user, the **Give Control** option isn't available.</span></span>

![meeting-policies-give-control-not-available.png](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="87eb6-321">让我们看一下下面的示例。</span><span class="sxs-lookup"><span data-stu-id="87eb6-321">Let's look at the following example.</span></span>

|<span data-ttu-id="87eb6-322">用户</span><span class="sxs-lookup"><span data-stu-id="87eb6-322">User</span></span> |<span data-ttu-id="87eb6-323">会议策略</span><span class="sxs-lookup"><span data-stu-id="87eb6-323">Meeting policy</span></span>  |<span data-ttu-id="87eb6-324">允许参与者授予或请求控制权</span><span class="sxs-lookup"><span data-stu-id="87eb6-324">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="87eb6-325">Daniela</span><span class="sxs-lookup"><span data-stu-id="87eb6-325">Daniela</span></span>   | <span data-ttu-id="87eb6-326">全局</span><span class="sxs-lookup"><span data-stu-id="87eb6-326">Global</span></span>   | <span data-ttu-id="87eb6-327">True</span><span class="sxs-lookup"><span data-stu-id="87eb6-327">True</span></span>       |
|<span data-ttu-id="87eb6-328">Babek</span><span class="sxs-lookup"><span data-stu-id="87eb6-328">Babek</span></span>    | <span data-ttu-id="87eb6-329">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="87eb6-329">Location1MeetingPolicy</span></span>        | <span data-ttu-id="87eb6-330">False</span><span class="sxs-lookup"><span data-stu-id="87eb6-330">False</span></span>   |

<span data-ttu-id="87eb6-331">Daniela 可以共享的桌面或窗口的控制权移交给其他中按 Babek 而 Babek 无法向其他参与者授予控制权的参与者。</span><span class="sxs-lookup"><span data-stu-id="87eb6-331">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek whereas Babek can't give control to other participants.</span></span>

### <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="87eb6-332">允许外部参与者授予或请求控制权</span><span class="sxs-lookup"><span data-stu-id="87eb6-332">Allow an external participant to give or request control</span></span>

<span data-ttu-id="87eb6-333">这是一个每用户策略。</span><span class="sxs-lookup"><span data-stu-id="87eb6-333">This is a per-user policy.</span></span> <span data-ttu-id="87eb6-334">此设置控制是否在会议中的外部参与者可以与其共享的桌面或窗口的控制权移交给其他参与者在会议中。</span><span class="sxs-lookup"><span data-stu-id="87eb6-334">This setting controls whether external participants in a meeting can give control of their shared desktop or window to other participants in the meeting.</span></span> <span data-ttu-id="87eb6-335">团队会议中的外部参与者可进行分类，如下所示：</span><span class="sxs-lookup"><span data-stu-id="87eb6-335">External participants in Teams meetings can be categorized as follows:</span></span>  

   - <span data-ttu-id="87eb6-336">匿名用户</span><span class="sxs-lookup"><span data-stu-id="87eb6-336">Anonymous user</span></span>
   - <span data-ttu-id="87eb6-337">来宾用户</span><span class="sxs-lookup"><span data-stu-id="87eb6-337">Guest users</span></span>  
   - <span data-ttu-id="87eb6-338">B2B 用户</span><span class="sxs-lookup"><span data-stu-id="87eb6-338">B2B user</span></span>
   - <span data-ttu-id="87eb6-339">联盟的用户</span><span class="sxs-lookup"><span data-stu-id="87eb6-339">Federated user</span></span>  

<span data-ttu-id="87eb6-340">由组织中的**允许外部参与者授予或请求控制**设置控制是否联盟的用户可以控制权移交给外部用户共享时。</span><span class="sxs-lookup"><span data-stu-id="87eb6-340">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="87eb6-341">允许 PowerPoint 共享</span><span class="sxs-lookup"><span data-stu-id="87eb6-341">Allow PowerPoint sharing</span></span>

<span data-ttu-id="87eb6-342">这是一个每用户策略。</span><span class="sxs-lookup"><span data-stu-id="87eb6-342">This is a per-user policy.</span></span> <span data-ttu-id="87eb6-343">此设置控制用户是否可以共享在会议中的 PowerPoint 幻灯片背面图案。</span><span class="sxs-lookup"><span data-stu-id="87eb6-343">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="87eb6-344">外部用户，其中包括匿名、 来宾，和联盟用户继承的会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="87eb6-344">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="87eb6-345">让我们看一下下面的示例。</span><span class="sxs-lookup"><span data-stu-id="87eb6-345">Let's look at the following example.</span></span>

|<span data-ttu-id="87eb6-346">用户</span><span class="sxs-lookup"><span data-stu-id="87eb6-346">User</span></span> |<span data-ttu-id="87eb6-347">会议策略</span><span class="sxs-lookup"><span data-stu-id="87eb6-347">Meeting policy</span></span>  |<span data-ttu-id="87eb6-348">允许 PowerPoint 共享</span><span class="sxs-lookup"><span data-stu-id="87eb6-348">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="87eb6-349">Daniela</span><span class="sxs-lookup"><span data-stu-id="87eb6-349">Daniela</span></span>   | <span data-ttu-id="87eb6-350">全局</span><span class="sxs-lookup"><span data-stu-id="87eb6-350">Global</span></span>   | <span data-ttu-id="87eb6-351">True</span><span class="sxs-lookup"><span data-stu-id="87eb6-351">True</span></span>       |
|<span data-ttu-id="87eb6-352">Amanda</span><span class="sxs-lookup"><span data-stu-id="87eb6-352">Amanda</span></span>   | <span data-ttu-id="87eb6-353">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="87eb6-353">Location1MeetingPolicy</span></span>        | <span data-ttu-id="87eb6-354">False</span><span class="sxs-lookup"><span data-stu-id="87eb6-354">False</span></span>   |

<span data-ttu-id="87eb6-355">Amanda 无法共享在会议中的 PowerPoint 幻灯片背面图案，即使她是会议组织者。</span><span class="sxs-lookup"><span data-stu-id="87eb6-355">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="87eb6-356">即使会议按 Amanda，Daniela 可以共享 PowerPoint 幻灯片背面图案。</span><span class="sxs-lookup"><span data-stu-id="87eb6-356">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="87eb6-357">Amanda 可以查看在会议中，由其他人共享 PowerPoint 幻灯片背面图案，即使她不能共享 PowerPoint 幻灯片背面图案。</span><span class="sxs-lookup"><span data-stu-id="87eb6-357">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

### <a name="allow-whiteboard"></a><span data-ttu-id="87eb6-358">允许白板</span><span class="sxs-lookup"><span data-stu-id="87eb6-358">Allow whiteboard</span></span>

<span data-ttu-id="87eb6-359">这是一个每用户策略。</span><span class="sxs-lookup"><span data-stu-id="87eb6-359">This is a per-user policy.</span></span> <span data-ttu-id="87eb6-360">此设置控制用户是否可以共享在会议中的白板。</span><span class="sxs-lookup"><span data-stu-id="87eb6-360">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="87eb6-361">外部用户，其中包括匿名、 B2B 和联盟的用户，继承的会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="87eb6-361">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> 

<span data-ttu-id="87eb6-362">让我们看一下下面的示例。</span><span class="sxs-lookup"><span data-stu-id="87eb6-362">Let's look at the following example.</span></span>

|<span data-ttu-id="87eb6-363">用户</span><span class="sxs-lookup"><span data-stu-id="87eb6-363">User</span></span> |<span data-ttu-id="87eb6-364">会议策略</span><span class="sxs-lookup"><span data-stu-id="87eb6-364">Meeting policy</span></span>  |<span data-ttu-id="87eb6-365">允许白板</span><span class="sxs-lookup"><span data-stu-id="87eb6-365">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="87eb6-366">Daniela</span><span class="sxs-lookup"><span data-stu-id="87eb6-366">Daniela</span></span>   | <span data-ttu-id="87eb6-367">全局</span><span class="sxs-lookup"><span data-stu-id="87eb6-367">Global</span></span>   | <span data-ttu-id="87eb6-368">True</span><span class="sxs-lookup"><span data-stu-id="87eb6-368">True</span></span>       |
|<span data-ttu-id="87eb6-369">Amanda</span><span class="sxs-lookup"><span data-stu-id="87eb6-369">Amanda</span></span>   | <span data-ttu-id="87eb6-370">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="87eb6-370">Location1MeetingPolicy</span></span>        | <span data-ttu-id="87eb6-371">False</span><span class="sxs-lookup"><span data-stu-id="87eb6-371">False</span></span>   |

<span data-ttu-id="87eb6-372">即使她是会议组织者，Amanda 无法共享在会议中的白板。</span><span class="sxs-lookup"><span data-stu-id="87eb6-372">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="87eb6-373">即使 Amanda 由组织会议时，Daniela 可以共享在白板。</span><span class="sxs-lookup"><span data-stu-id="87eb6-373">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

### <a name="allow-shared-notes"></a><span data-ttu-id="87eb6-374">允许共享的便笺</span><span class="sxs-lookup"><span data-stu-id="87eb6-374">Allow shared notes</span></span>

<span data-ttu-id="87eb6-375">这是一个每用户策略。</span><span class="sxs-lookup"><span data-stu-id="87eb6-375">This is a per-user policy.</span></span> <span data-ttu-id="87eb6-376">此设置控制用户是否可以创建和共享在会议中的注释。</span><span class="sxs-lookup"><span data-stu-id="87eb6-376">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="87eb6-377">外部用户，其中包括匿名、 B2B 和联盟的用户，继承的会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="87eb6-377">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="87eb6-378">**会议笔记**选项卡目前少于 20 个参与者仅中支持的会议。</span><span class="sxs-lookup"><span data-stu-id="87eb6-378">The **Meeting Notes** tab is currently only supported in meetings that have less than 20 participants.</span></span> 

<span data-ttu-id="87eb6-379">让我们看一下下面的示例。</span><span class="sxs-lookup"><span data-stu-id="87eb6-379">Let's look at the following example.</span></span>

|<span data-ttu-id="87eb6-380">用户</span><span class="sxs-lookup"><span data-stu-id="87eb6-380">User</span></span> |<span data-ttu-id="87eb6-381">会议策略</span><span class="sxs-lookup"><span data-stu-id="87eb6-381">Meeting policy</span></span>  |<span data-ttu-id="87eb6-382">允许共享的便笺</span><span class="sxs-lookup"><span data-stu-id="87eb6-382">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="87eb6-383">Daniela</span><span class="sxs-lookup"><span data-stu-id="87eb6-383">Daniela</span></span>   | <span data-ttu-id="87eb6-384">全局</span><span class="sxs-lookup"><span data-stu-id="87eb6-384">Global</span></span>   | <span data-ttu-id="87eb6-385">True</span><span class="sxs-lookup"><span data-stu-id="87eb6-385">True</span></span>       |
|<span data-ttu-id="87eb6-386">Amanda</span><span class="sxs-lookup"><span data-stu-id="87eb6-386">Amanda</span></span>   | <span data-ttu-id="87eb6-387">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="87eb6-387">Location1MeetingPolicy</span></span> | <span data-ttu-id="87eb6-388">False</span><span class="sxs-lookup"><span data-stu-id="87eb6-388">False</span></span> |

<span data-ttu-id="87eb6-389">Daniela 可以 Amanda 的会议中添加注释和 Amanda 不能在任何会议中添加注释。</span><span class="sxs-lookup"><span data-stu-id="87eb6-389">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>

### <a name="allow-chat-in-meetings-coming-soon"></a><span data-ttu-id="87eb6-390">（即将推出） 的会议中允许聊天</span><span class="sxs-lookup"><span data-stu-id="87eb6-390">Allow chat in meetings (coming soon)</span></span>

<span data-ttu-id="87eb6-391">这是每个管理器策略。</span><span class="sxs-lookup"><span data-stu-id="87eb6-391">This is a per-organizer policy.</span></span> <span data-ttu-id="87eb6-392">此设置控制是否在用户的会议中允许 meeting 聊天。</span><span class="sxs-lookup"><span data-stu-id="87eb6-392">This setting controls whether meeting chat is allowed in the user's meeting.</span></span> 

<span data-ttu-id="87eb6-393"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="87eb6-393"></span></span>

## <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="87eb6-394">会议策略设置-参与者 & 来宾</span><span class="sxs-lookup"><span data-stu-id="87eb6-394">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="87eb6-395">他们允许会议中的会议参与者等待之前加入会议并参与的级别对会议厅中这些设置控制。</span><span class="sxs-lookup"><span data-stu-id="87eb6-395">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="87eb6-396">自动允许人员加入</span><span class="sxs-lookup"><span data-stu-id="87eb6-396">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="87eb6-397">允许匿名用户开始会议</span><span class="sxs-lookup"><span data-stu-id="87eb6-397">Allow anonymous people to start a meeting</span></span>](#allow-anonymous-people-to-start-a-meeting)
- [<span data-ttu-id="87eb6-398">允许电话拨入式用户绕过大厅</span><span class="sxs-lookup"><span data-stu-id="87eb6-398">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby-coming-soon)
- [<span data-ttu-id="87eb6-399">允许组织者覆盖会议厅设置</span><span class="sxs-lookup"><span data-stu-id="87eb6-399">Allow organizers to override lobby settings</span></span>](#allow-organizers-to-override-lobby-settings-coming-soon)

### <a name="automatically-admit-people"></a><span data-ttu-id="87eb6-400">自动允许人员加入</span><span class="sxs-lookup"><span data-stu-id="87eb6-400">Automatically admit people</span></span>

<span data-ttu-id="87eb6-401">这是每个管理器策略。</span><span class="sxs-lookup"><span data-stu-id="87eb6-401">This is a per-organizer policy.</span></span> <span data-ttu-id="87eb6-402">此设置控制是否人员加入会议直接或通过身份验证的用户获准加入会议之前，在会议厅等待。</span><span class="sxs-lookup"><span data-stu-id="87eb6-402">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span>

![会议的策略-lobby.png](media/meeting-policies-lobby.png)

 <span data-ttu-id="87eb6-404">会议组织者可以单击更改此设置为他们安排每个会议的会议邀请中**会议选项**。</span><span class="sxs-lookup"><span data-stu-id="87eb6-404">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span> <span data-ttu-id="87eb6-405">**（即将推出）**</span><span class="sxs-lookup"><span data-stu-id="87eb6-405">**(coming soon)**</span></span>
  
|<span data-ttu-id="87eb6-406">设置值</span><span class="sxs-lookup"><span data-stu-id="87eb6-406">Setting value</span></span>  |<span data-ttu-id="87eb6-407">加入行为</span><span class="sxs-lookup"><span data-stu-id="87eb6-407">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="87eb6-408">**所有人**</span><span class="sxs-lookup"><span data-stu-id="87eb6-408">**Everyone**</span></span>   |<span data-ttu-id="87eb6-409">所有会议参与者都加入会议直接而不需要在会议厅等待。</span><span class="sxs-lookup"><span data-stu-id="87eb6-409">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="87eb6-410">这包括经过身份验证的用户、 联盟的用户、 来宾、 匿名用户和通过电话拨入的人员。</span><span class="sxs-lookup"><span data-stu-id="87eb6-410">This includes authenticated users, federated users, guests, anonymous users, and people who dial in by phone.</span></span>       |
|<span data-ttu-id="87eb6-411">**您的组织和联盟的组织中的所有人**</span><span class="sxs-lookup"><span data-stu-id="87eb6-411">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="87eb6-412">组织，包括来宾用户和联盟组织内的经过身份验证的用户加入会议直接而不需要在会议厅等待。</span><span class="sxs-lookup"><span data-stu-id="87eb6-412">Authenticated users within the organization, including guest users and the users from federated organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="87eb6-413">匿名用户和通过电话拨入用户在会议厅等待。</span><span class="sxs-lookup"><span data-stu-id="87eb6-413">Anonymous users and users who dial in by phone wait in the lobby.</span></span>   |
|<span data-ttu-id="87eb6-414">**您的组织中的所有人**</span><span class="sxs-lookup"><span data-stu-id="87eb6-414">**Everyone in your organization**</span></span>    |<span data-ttu-id="87eb6-415">从内组织，包括来宾用户的经过身份验证的用户加入会议直接而不需要在会议厅等待。</span><span class="sxs-lookup"><span data-stu-id="87eb6-415">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="87eb6-416">联盟的用户和匿名用户通过电话拨入的用户在会议厅等待。</span><span class="sxs-lookup"><span data-stu-id="87eb6-416">Federated users, anonymous users, and users who dial in by phone wait in the lobby.</span></span>           |

### <a name="allow-anonymous-people-to-start-a-meeting"></a><span data-ttu-id="87eb6-417">允许匿名用户开始会议</span><span class="sxs-lookup"><span data-stu-id="87eb6-417">Allow anonymous people to start a meeting</span></span>

<span data-ttu-id="87eb6-418">这是每个管理器策略。</span><span class="sxs-lookup"><span data-stu-id="87eb6-418">This is a per-organizer policy.</span></span> <span data-ttu-id="87eb6-419">此设置控制匿名的人员，包括 B2B 和联盟的用户是否可以参加加入经过身份验证的用户从组织的情况下的用户的会议。</span><span class="sxs-lookup"><span data-stu-id="87eb6-419">This setting controls whether anonymous people, including B2B, and federated users, can join the user's meeting without an authenticated user from the organization in attendance.</span></span> 

![会议的策略-匿名-用户-lobby.png](media/meeting-policies-anonymous-user-lobby.png)

<span data-ttu-id="87eb6-421">在会议中存在经过身份验证的用户时，下面是人员的匿名加入行为。</span><span class="sxs-lookup"><span data-stu-id="87eb6-421">Here's the join behavior of anonymous people when authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="87eb6-422">允许匿名用户开始会议</span><span class="sxs-lookup"><span data-stu-id="87eb6-422">Allow anonymous people to start a meeting</span></span>  |<span data-ttu-id="87eb6-423">自动允许人员加入</span><span class="sxs-lookup"><span data-stu-id="87eb6-423">Automatically admit people</span></span> |<span data-ttu-id="87eb6-424">加入匿名用户的行为</span><span class="sxs-lookup"><span data-stu-id="87eb6-424">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="87eb6-425">True</span><span class="sxs-lookup"><span data-stu-id="87eb6-425">True</span></span>    | <span data-ttu-id="87eb6-426">所有人</span><span class="sxs-lookup"><span data-stu-id="87eb6-426">Everyone</span></span>      | <span data-ttu-id="87eb6-427">直接加入</span><span class="sxs-lookup"><span data-stu-id="87eb6-427">Join directly</span></span>         |
|   | <span data-ttu-id="87eb6-428">您的组织中的所有人</span><span class="sxs-lookup"><span data-stu-id="87eb6-428">Everyone in your organization</span></span>       | <span data-ttu-id="87eb6-429">在会议厅中等待</span><span class="sxs-lookup"><span data-stu-id="87eb6-429">Wait in lobby</span></span>        |
|   | <span data-ttu-id="87eb6-430">您的组织和联盟的组织中的所有人</span><span class="sxs-lookup"><span data-stu-id="87eb6-430">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="87eb6-431">在会议厅中等待</span><span class="sxs-lookup"><span data-stu-id="87eb6-431">Wait in lobby</span></span>         |
|<span data-ttu-id="87eb6-432">False</span><span class="sxs-lookup"><span data-stu-id="87eb6-432">False</span></span>    | <span data-ttu-id="87eb6-433">所有人</span><span class="sxs-lookup"><span data-stu-id="87eb6-433">Everyone</span></span>        | <span data-ttu-id="87eb6-434">直接加入</span><span class="sxs-lookup"><span data-stu-id="87eb6-434">Join directly</span></span>        |
|   | <span data-ttu-id="87eb6-435">您的组织中的所有人</span><span class="sxs-lookup"><span data-stu-id="87eb6-435">Everyone in your organization</span></span>     | <span data-ttu-id="87eb6-436">在会议厅中等待</span><span class="sxs-lookup"><span data-stu-id="87eb6-436">Wait in lobby</span></span>        |
|   | <span data-ttu-id="87eb6-437">您的组织和联盟的组织中的所有人</span><span class="sxs-lookup"><span data-stu-id="87eb6-437">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="87eb6-438">在会议厅中等待</span><span class="sxs-lookup"><span data-stu-id="87eb6-438">Wait in lobby</span></span>         |

<span data-ttu-id="87eb6-439">存在于会议中没有经过身份验证的用户时，下面是人员的匿名加入行为。</span><span class="sxs-lookup"><span data-stu-id="87eb6-439">Here's the join behavior of anonymous people when no authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="87eb6-440">允许匿名用户开始会议</span><span class="sxs-lookup"><span data-stu-id="87eb6-440">Allow anonymous people to start a meeting</span></span> |<span data-ttu-id="87eb6-441">自动允许人员加入</span><span class="sxs-lookup"><span data-stu-id="87eb6-441">Automatically admit people</span></span>  |<span data-ttu-id="87eb6-442">加入匿名用户的行为</span><span class="sxs-lookup"><span data-stu-id="87eb6-442">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="87eb6-443">True</span><span class="sxs-lookup"><span data-stu-id="87eb6-443">True</span></span>    | <span data-ttu-id="87eb6-444">所有人</span><span class="sxs-lookup"><span data-stu-id="87eb6-444">Everyone</span></span>      | <span data-ttu-id="87eb6-445">直接加入</span><span class="sxs-lookup"><span data-stu-id="87eb6-445">Join directly</span></span>         |
|   | <span data-ttu-id="87eb6-446">您的组织中的所有人</span><span class="sxs-lookup"><span data-stu-id="87eb6-446">Everyone in your organization</span></span>       | <span data-ttu-id="87eb6-447">在会议厅中等待</span><span class="sxs-lookup"><span data-stu-id="87eb6-447">Wait in lobby</span></span>        |
|   | <span data-ttu-id="87eb6-448">您的组织和联盟的组织中的所有人</span><span class="sxs-lookup"><span data-stu-id="87eb6-448">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="87eb6-449">在会议厅中等待</span><span class="sxs-lookup"><span data-stu-id="87eb6-449">Wait in lobby</span></span>         |
|<span data-ttu-id="87eb6-450">False</span><span class="sxs-lookup"><span data-stu-id="87eb6-450">False</span></span>    | <span data-ttu-id="87eb6-451">所有人</span><span class="sxs-lookup"><span data-stu-id="87eb6-451">Everyone</span></span>        | <span data-ttu-id="87eb6-452">在会议厅中等待。</span><span class="sxs-lookup"><span data-stu-id="87eb6-452">Wait in lobby.</span></span> <span data-ttu-id="87eb6-453">第一个经过身份验证的用户加入会议时，用户自动获准加入会议。</span><span class="sxs-lookup"><span data-stu-id="87eb6-453">Users are automatically admitted when the first authenticated user joins the meeting.</span></span>        |
|   | <span data-ttu-id="87eb6-454">您的组织中的所有人</span><span class="sxs-lookup"><span data-stu-id="87eb6-454">Everyone in your organization</span></span>     |<span data-ttu-id="87eb6-455">在会议厅中等待</span><span class="sxs-lookup"><span data-stu-id="87eb6-455">Wait in lobby</span></span>         |
|   | <span data-ttu-id="87eb6-456">您的组织和联盟的组织中的所有人</span><span class="sxs-lookup"><span data-stu-id="87eb6-456">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="87eb6-457">在会议厅中等待</span><span class="sxs-lookup"><span data-stu-id="87eb6-457">Wait in lobby</span></span>         |

### <a name="allow-dial-in-users-to-bypass-the-lobby-coming-soon"></a><span data-ttu-id="87eb6-458">允许电话拨入式用户绕过大厅 （即将推出）</span><span class="sxs-lookup"><span data-stu-id="87eb6-458">Allow dial-in users to bypass the lobby (coming soon)</span></span>

<span data-ttu-id="87eb6-459">这是每个管理器策略。</span><span class="sxs-lookup"><span data-stu-id="87eb6-459">This is a per-organizer policy.</span></span> <span data-ttu-id="87eb6-460">此设置控制是否通过电话拨入的人员加入会议直接或**自动允许人员加入**设置无论会议厅中等待。</span><span class="sxs-lookup"><span data-stu-id="87eb6-460">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span>

<span data-ttu-id="87eb6-461">下面是人员的通过电话拨入加入行为。</span><span class="sxs-lookup"><span data-stu-id="87eb6-461">Here's the join behavior of people who dial in by phone.</span></span>

|<span data-ttu-id="87eb6-462">允许电话拨入式用户绕过大厅</span><span class="sxs-lookup"><span data-stu-id="87eb6-462">Allow dial-in users to bypass the lobby</span></span>  |<span data-ttu-id="87eb6-463">自动允许的用户</span><span class="sxs-lookup"><span data-stu-id="87eb6-463">Automatically admit users</span></span>  |<span data-ttu-id="87eb6-464">加入的拨入的人员的行为</span><span class="sxs-lookup"><span data-stu-id="87eb6-464">Join behavior of people who dial in</span></span> |
|---------|---------|---------|
|<span data-ttu-id="87eb6-465">True</span><span class="sxs-lookup"><span data-stu-id="87eb6-465">True</span></span>    | <span data-ttu-id="87eb6-466">所有人</span><span class="sxs-lookup"><span data-stu-id="87eb6-466">Everyone</span></span>      | <span data-ttu-id="87eb6-467">直接加入</span><span class="sxs-lookup"><span data-stu-id="87eb6-467">Join directly</span></span>         |
|   | <span data-ttu-id="87eb6-468">您的组织中的所有人</span><span class="sxs-lookup"><span data-stu-id="87eb6-468">Everyone in your organization</span></span>       | <span data-ttu-id="87eb6-469">直接加入</span><span class="sxs-lookup"><span data-stu-id="87eb6-469">Join directly</span></span>        |
|   | <span data-ttu-id="87eb6-470">您的组织和联盟的组织中的所有人</span><span class="sxs-lookup"><span data-stu-id="87eb6-470">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="87eb6-471">直接加入</span><span class="sxs-lookup"><span data-stu-id="87eb6-471">Join directly</span></span>         |
|<span data-ttu-id="87eb6-472">False</span><span class="sxs-lookup"><span data-stu-id="87eb6-472">False</span></span>    | <span data-ttu-id="87eb6-473">所有人</span><span class="sxs-lookup"><span data-stu-id="87eb6-473">Everyone</span></span>        | <span data-ttu-id="87eb6-474">直接加入</span><span class="sxs-lookup"><span data-stu-id="87eb6-474">Join directly</span></span>        |
|   | <span data-ttu-id="87eb6-475">您的组织中的所有人</span><span class="sxs-lookup"><span data-stu-id="87eb6-475">Everyone in your organization</span></span>     |<span data-ttu-id="87eb6-476">在会议厅中等待</span><span class="sxs-lookup"><span data-stu-id="87eb6-476">Wait in lobby</span></span>         |
|   | <span data-ttu-id="87eb6-477">您的组织和联盟的组织中的所有人</span><span class="sxs-lookup"><span data-stu-id="87eb6-477">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="87eb6-478">在会议厅中等待</span><span class="sxs-lookup"><span data-stu-id="87eb6-478">Wait in lobby</span></span>         |

### <a name="allow-organizers-to-override-lobby-settings-coming-soon"></a><span data-ttu-id="87eb6-479">允许组织者覆盖会议厅设置 （即将推出）</span><span class="sxs-lookup"><span data-stu-id="87eb6-479">Allow organizers to override lobby settings (coming soon)</span></span>

<span data-ttu-id="87eb6-480">这是每个管理器策略。</span><span class="sxs-lookup"><span data-stu-id="87eb6-480">This is a per-organizer policy.</span></span> <span data-ttu-id="87eb6-481">此设置控制会议组织者可以重写他们安排新的会议时，**自动允许人员加入**和**允许电话拨入式用户绕过大厅**中设置管理会议厅设置。</span><span class="sxs-lookup"><span data-stu-id="87eb6-481">This setting controls whether the meeting organizer can override the lobby settings that an admin set in **Automatically admit people** and **Allow dial-in users to bypass the lobby** when they schedule a new meeting.</span></span> 

<span data-ttu-id="87eb6-482">会议组织者可以单击更改会议厅设置为他们安排每个会议的会议邀请中**会议选项**。</span><span class="sxs-lookup"><span data-stu-id="87eb6-482">Meeting organizers can click **Meeting Options** in the meeting invitation to change lobby settings for each meeting they schedule.</span></span> 

<span data-ttu-id="87eb6-483">下面是此设置如何影响是否会议组织者可以更改**自动允许人员加入**设置每个会议组织者计划。</span><span class="sxs-lookup"><span data-stu-id="87eb6-483">Here's how this setting affects whether the meeting organizer can change the **Automatically admit people** setting for each meeting the organizer schedules.</span></span>

|<span data-ttu-id="87eb6-484">允许组织者覆盖会议厅设置</span><span class="sxs-lookup"><span data-stu-id="87eb6-484">Allow organizers to override lobby settings</span></span>  |<span data-ttu-id="87eb6-485">自动允许人员加入</span><span class="sxs-lookup"><span data-stu-id="87eb6-485">Automatically admit people</span></span>  |<span data-ttu-id="87eb6-486">行为</span><span class="sxs-lookup"><span data-stu-id="87eb6-486">Behavior</span></span> |
|---------|---------|---------|
|<span data-ttu-id="87eb6-487">True</span><span class="sxs-lookup"><span data-stu-id="87eb6-487">True</span></span>    | <span data-ttu-id="87eb6-488">所有人</span><span class="sxs-lookup"><span data-stu-id="87eb6-488">Everyone</span></span>      | <span data-ttu-id="87eb6-489">组织者可以将设置更改任何其他值。</span><span class="sxs-lookup"><span data-stu-id="87eb6-489">Organizer can change the setting to any other value.</span></span> |
|   | <span data-ttu-id="87eb6-490">您的组织中的所有人</span><span class="sxs-lookup"><span data-stu-id="87eb6-490">Everyone in your organization</span></span>       | <span data-ttu-id="87eb6-491">组织者可以将设置更改任何其他值。</span><span class="sxs-lookup"><span data-stu-id="87eb6-491">Organizer can change the setting to any other value.</span></span>|
|   | <span data-ttu-id="87eb6-492">您的组织和联盟的组织中的所有人</span><span class="sxs-lookup"><span data-stu-id="87eb6-492">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="87eb6-493">组织者可以更改此为其他任何值。</span><span class="sxs-lookup"><span data-stu-id="87eb6-493">Organizer can change this to any other value.</span></span>         |
|<span data-ttu-id="87eb6-494">False</span><span class="sxs-lookup"><span data-stu-id="87eb6-494">False</span></span>    | <span data-ttu-id="87eb6-495">所有人</span><span class="sxs-lookup"><span data-stu-id="87eb6-495">Everyone</span></span>        | <span data-ttu-id="87eb6-496">组织者可以将设置更改任何其他值。</span><span class="sxs-lookup"><span data-stu-id="87eb6-496">Organizer can change the setting to any other value.</span></span>|
|   | <span data-ttu-id="87eb6-497">您的组织中的所有人</span><span class="sxs-lookup"><span data-stu-id="87eb6-497">Everyone in your organization</span></span>     |<span data-ttu-id="87eb6-498">组织者可以设置更改为**您的组织中的每个人**。</span><span class="sxs-lookup"><span data-stu-id="87eb6-498">Organizer can change the setting to **Everyone in your organization**.</span></span> |
|   | <span data-ttu-id="87eb6-499">您的组织和联盟的组织中的所有人</span><span class="sxs-lookup"><span data-stu-id="87eb6-499">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="87eb6-500">组织者无法覆盖会议厅设置。</span><span class="sxs-lookup"><span data-stu-id="87eb6-500">Organizer can't override the lobby setting.</span></span> |

<span data-ttu-id="87eb6-501">下面是此设置如何影响是否会议组织者可以更改的每个会议组织者计划**允许将绕过大厅电话拨入式用户**设置。</span><span class="sxs-lookup"><span data-stu-id="87eb6-501">Here's how this setting affects whether the meeting organizer can change the **Allow dial-in users to bypass the lobby** setting for each meeting the organizer schedules.</span></span>
    
|<span data-ttu-id="87eb6-502">允许组织者覆盖会议厅设置</span><span class="sxs-lookup"><span data-stu-id="87eb6-502">Allow organizers to override lobby settings</span></span>  |<span data-ttu-id="87eb6-503">允许电话拨入式用户绕过大厅</span><span class="sxs-lookup"><span data-stu-id="87eb6-503">Allow dial-in users to bypass the lobby</span></span>  |<span data-ttu-id="87eb6-504">行为</span><span class="sxs-lookup"><span data-stu-id="87eb6-504">Behavior</span></span> |
|---------|---------|---------|
|<span data-ttu-id="87eb6-505">True</span><span class="sxs-lookup"><span data-stu-id="87eb6-505">True</span></span>    |  <span data-ttu-id="87eb6-506">True</span><span class="sxs-lookup"><span data-stu-id="87eb6-506">True</span></span>        | <span data-ttu-id="87eb6-507">组织者可以更改该设置为 False。</span><span class="sxs-lookup"><span data-stu-id="87eb6-507">Organizer can change the setting to False.</span></span>       |
|<span data-ttu-id="87eb6-508">True</span><span class="sxs-lookup"><span data-stu-id="87eb6-508">True</span></span>      | <span data-ttu-id="87eb6-509">False</span><span class="sxs-lookup"><span data-stu-id="87eb6-509">False</span></span>         | <span data-ttu-id="87eb6-510">组织者可以更改该设置为 True。</span><span class="sxs-lookup"><span data-stu-id="87eb6-510">Organizer can change the setting to True.</span></span>        |
|<span data-ttu-id="87eb6-511">False</span><span class="sxs-lookup"><span data-stu-id="87eb6-511">False</span></span>     | <span data-ttu-id="87eb6-512">True</span><span class="sxs-lookup"><span data-stu-id="87eb6-512">True</span></span>        |<span data-ttu-id="87eb6-513">组织者可以更改该设置为 False。</span><span class="sxs-lookup"><span data-stu-id="87eb6-513">Organizer can change the setting to False.</span></span>         |
|<span data-ttu-id="87eb6-514">False</span><span class="sxs-lookup"><span data-stu-id="87eb6-514">False</span></span>      |<span data-ttu-id="87eb6-515">False</span><span class="sxs-lookup"><span data-stu-id="87eb6-515">False</span></span>          |<span data-ttu-id="87eb6-516">组织者不能覆盖会议厅设置，并不能允许电话拨入式用户绕过大厅会议中。</span><span class="sxs-lookup"><span data-stu-id="87eb6-516">Organizer can't override the lobby setting and can't allow dial-in users to bypass the lobby in the meeting.</span></span>        |

[<span data-ttu-id="87eb6-517">完整的文章</span><span class="sxs-lookup"><span data-stu-id="87eb6-517">Full article</span></span>](meeting-policies-in-teams.md)

## <a name="related-topics"></a><span data-ttu-id="87eb6-518">相关主题</span><span class="sxs-lookup"><span data-stu-id="87eb6-518">Related topics</span></span>
[<span data-ttu-id="87eb6-519">团队中的邮件策略</span><span class="sxs-lookup"><span data-stu-id="87eb6-519">Messaging policies in Teams</span></span>](messaging-policies-in-teams.md)
