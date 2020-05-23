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
ms.openlocfilehash: 2f6a88276a2b5d3214b89555d0008e2b58cf1aa2
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2020
ms.locfileid: "44349556"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="2284d-103">管理团队中的会议策略</span><span class="sxs-lookup"><span data-stu-id="2284d-103">Manage meeting policies in Teams</span></span>

::: zone target="docs"
<span data-ttu-id="2284d-104">会议策略Meeting policies用于控制组织中用户安排的会议的与会者可用的功能。</span><span class="sxs-lookup"><span data-stu-id="2284d-104">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="2284d-105">创建策略并进行更改后，即可以将用户分配到策略。</span><span class="sxs-lookup"><span data-stu-id="2284d-105">After you create a policy and make your changes, you can then assign users to the policy.</span></span> <span data-ttu-id="2284d-106">可在 Microsoft 团队管理中心或通过使用[PowerShell](teams-powershell-overview.md)管理会议策略。</span><span class="sxs-lookup"><span data-stu-id="2284d-106">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

<span data-ttu-id="2284d-107">你可以通过以下方式实施策略，这会在会议开始之前、会议期间或会议后影响用户的会议体验。</span><span class="sxs-lookup"><span data-stu-id="2284d-107">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="2284d-108">实现类型</span><span class="sxs-lookup"><span data-stu-id="2284d-108">Implementation type</span></span>  |<span data-ttu-id="2284d-109">说明</span><span class="sxs-lookup"><span data-stu-id="2284d-109">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="2284d-110">每个组织者</span><span class="sxs-lookup"><span data-stu-id="2284d-110">Per-organizer</span></span>    |<span data-ttu-id="2284d-111">实施按组织者策略时，所有会议参与者都将继承组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="2284d-111">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="2284d-112">例如，**自动允许人员**为每个组织者策略，并控制用户是否直接加入会议，或在会议厅中等待分配了该策略的用户安排的会议。</span><span class="sxs-lookup"><span data-stu-id="2284d-112">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="2284d-113">每用户</span><span class="sxs-lookup"><span data-stu-id="2284d-113">Per-user</span></span>    |<span data-ttu-id="2284d-114">当你实现每用户策略时，仅应用每用户策略来限制组织者和/或会议参与者的某些功能。</span><span class="sxs-lookup"><span data-stu-id="2284d-114">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="2284d-115">例如，"**允许在频道中立即开会**" 是每用户策略。</span><span class="sxs-lookup"><span data-stu-id="2284d-115">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="2284d-116">每个组织者和每用户</span><span class="sxs-lookup"><span data-stu-id="2284d-116">Per-organizer and per-user</span></span>     |<span data-ttu-id="2284d-117">当你实现每个组织单位和每用户策略的组合时，某些功能将根据其策略和组织者的策略来限制会议参与者。</span><span class="sxs-lookup"><span data-stu-id="2284d-117">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="2284d-118">例如，"**允许云录制**" 是基于每个组织者和每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="2284d-118">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="2284d-119">启用此设置可允许会议组织者和参与者开始和停止录制。</span><span class="sxs-lookup"><span data-stu-id="2284d-119">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span>

<span data-ttu-id="2284d-120">默认情况下，将创建名为 Global 的策略（组织范围的默认设置）。</span><span class="sxs-lookup"><span data-stu-id="2284d-120">By default, a policy named Global (Org-wide default) is created.</span></span> <span data-ttu-id="2284d-121">默认情况下，组织中的所有用户都分配有 "全局会议策略"。</span><span class="sxs-lookup"><span data-stu-id="2284d-121">All users in your organization are assigned the Global meeting policy by default.</span></span> <span data-ttu-id="2284d-122">你可以对其进行更改或创建一个或多个自定义策略，并向其分配用户。</span><span class="sxs-lookup"><span data-stu-id="2284d-122">You can either make changes to it or create one or more custom policies and assign users to them.</span></span> <span data-ttu-id="2284d-123">除非你创建和分配自定义策略，否则用户将获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="2284d-123">Users will get the Global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="2284d-124">创建自定义策略时，你可以允许或阻止你的用户使用某些功能，然后将其分配给将对其应用设置的一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="2284d-124">When you create a custom policy, you can allow or prevent certain features from being available to your users, and then assign it to one or more users who will have the settings applied to them.</span></span>

> [!NOTE]
> <span data-ttu-id="2284d-125">"会议详细信息" 按钮在用户启用音频会议许可证或用户允许音频会议的情况下可用时，会议详细信息将不可用。</span><span class="sxs-lookup"><span data-stu-id="2284d-125">Meeting details button will be available if a user has the audio conference licenses enabled or the user is allow for audio conferencing, if not, the meeting details will not be available.</span></span>

## <a name="change-or-create-a-meeting-policy"></a><span data-ttu-id="2284d-126">更改或创建会议策略</span><span class="sxs-lookup"><span data-stu-id="2284d-126">Change or create a meeting policy</span></span>

<span data-ttu-id="2284d-127">若要更改或创建会议策略，请转到 Microsoft Teams 管理中心 >“**会议**” > “**会议策略**”。</span><span class="sxs-lookup"><span data-stu-id="2284d-127">To change or create a meeting policy, go to the Microsoft Teams admin center > **Meetings** > **Meeting policies**.</span></span> <span data-ttu-id="2284d-128">从列表中选择一个策略，或者选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="2284d-128">Select a policy from the list or select **Add**.</span></span> <span data-ttu-id="2284d-129">若正在创建新策略，则添加名称和说明。</span><span class="sxs-lookup"><span data-stu-id="2284d-129">If you're creating a new policy, add a name and description.</span></span> <span data-ttu-id="2284d-130">名称不能包含特殊字符或超过 64 个字符。</span><span class="sxs-lookup"><span data-stu-id="2284d-130">The name can't contain special characters or be longer than 64 characters.</span></span> <span data-ttu-id="2284d-131">选择您的设置，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="2284d-131">Choose your settings, and then select **Save**.</span></span>

<span data-ttu-id="2284d-132">例如，假设你有一组用户并且你想要限制这组用户的会议所需的带宽量。</span><span class="sxs-lookup"><span data-stu-id="2284d-132">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="2284d-133">你要创建新的自定义策略并命名为“带宽限制”，然后禁用以下设置：</span><span class="sxs-lookup"><span data-stu-id="2284d-133">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="2284d-134">在“音频和视频”中：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2284d-134">Under **Audio & video**:</span></span>
- <span data-ttu-id="2284d-135">禁用“允许云录制”。</span><span class="sxs-lookup"><span data-stu-id="2284d-135">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="2284d-136">禁用“允许 IP 视频”。</span><span class="sxs-lookup"><span data-stu-id="2284d-136">Turn off Allow IP video.</span></span>

<span data-ttu-id="2284d-137">在“内容共享”中：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2284d-137">Under **Content sharing**:</span></span>
- <span data-ttu-id="2284d-138">禁用屏幕共享模式。</span><span class="sxs-lookup"><span data-stu-id="2284d-138">Disable screen sharing mode.</span></span>
- <span data-ttu-id="2284d-139">禁用“允许白板”。</span><span class="sxs-lookup"><span data-stu-id="2284d-139">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="2284d-140">禁用“允许共享笔记”。</span><span class="sxs-lookup"><span data-stu-id="2284d-140">Turn off Allow shared notes.</span></span>

<span data-ttu-id="2284d-141">然后将此策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="2284d-141">Then assign the policy to the users.</span></span>

> [!NOTE]
> <span data-ttu-id="2284d-142">一次只能向一个用户分配一个会议策略。</span><span class="sxs-lookup"><span data-stu-id="2284d-142">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="2284d-143">将会议策略分配给用户</span><span class="sxs-lookup"><span data-stu-id="2284d-143">Assign a meeting policy to users</span></span>

<span data-ttu-id="2284d-144">若要向一个用户分配会议策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2284d-144">To assign a meeting policy to one user:</span></span>

1. <span data-ttu-id="2284d-145">在 Microsoft Teams 管理员中心的左侧导航中，转到“用户”，然后单击相应的用户。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2284d-145">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="2284d-146">单击用户名的左侧以选择用户，然后单击“编辑设置”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2284d-146">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="2284d-147">在“会议策略”中，选择想要分配的策略，然后单击“应用”。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2284d-147">Under **Meeting policy**, select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="2284d-148">要一次为多个用户分配策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2284d-148">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="2284d-149">在 Microsoft 团队管理中心的左侧导航中，转到 "**用户**"，然后搜索用户或筛选视图以显示所需的用户。</span><span class="sxs-lookup"><span data-stu-id="2284d-149">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="2284d-150">在 " **&#x2713;** " （复选标记）列中，选择用户。</span><span class="sxs-lookup"><span data-stu-id="2284d-150">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="2284d-151">若要选择 "所有用户"，请单击表格顶部的 "&#x2713;" （复选标记）。</span><span class="sxs-lookup"><span data-stu-id="2284d-151">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="2284d-152">单击 "**编辑设置**"，进行所需的更改，然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="2284d-152">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="2284d-153">或者，您也可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2284d-153">Or, you can also do the following:</span></span>

1. <span data-ttu-id="2284d-154">在 Microsoft 团队管理中心的左侧导航中，转到 "**会议**  >  **会议策略**"。</span><span class="sxs-lookup"><span data-stu-id="2284d-154">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="2284d-155">单击策略名称的左侧以选择该策略。</span><span class="sxs-lookup"><span data-stu-id="2284d-155">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="2284d-156">选择“管理用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2284d-156">Select **Manage users**.</span></span>
4. <span data-ttu-id="2284d-157">在“**管理用户**”窗格中，按显示名称或用户名搜索用户，选择用户名，然后选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="2284d-157">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="2284d-158">对想要添加的每一个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="2284d-158">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="2284d-159">添加完用户后，选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="2284d-159">After you finish adding users, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="2284d-160">如果向用户分配了该策略，则不能删除该策略。</span><span class="sxs-lookup"><span data-stu-id="2284d-160">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="2284d-161">必须先为所有受影响的用户分配不同的策略，然后才能删除原始策略。</span><span class="sxs-lookup"><span data-stu-id="2284d-161">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="2284d-162">会议策略设置</span><span class="sxs-lookup"><span data-stu-id="2284d-162">Meeting policy settings</span></span>

<span data-ttu-id="2284d-163">在 "**会议策略**" 页面上选择现有策略或选择 "**添加**" 以添加新策略时，可以为以下项配置设置。</span><span class="sxs-lookup"><span data-stu-id="2284d-163">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="2284d-164">常规</span><span class="sxs-lookup"><span data-stu-id="2284d-164">General</span></span>](#meeting-policy-settings---general)
- [<span data-ttu-id="2284d-165">音频 & 视频</span><span class="sxs-lookup"><span data-stu-id="2284d-165">Audio & video</span></span>](#meeting-policy-settings---audio--video)
- [<span data-ttu-id="2284d-166">内容共享</span><span class="sxs-lookup"><span data-stu-id="2284d-166">Content sharing</span></span>](#meeting-policy-settings---content-sharing)
- [<span data-ttu-id="2284d-167">参与者 & 来宾</span><span class="sxs-lookup"><span data-stu-id="2284d-167">Participants & guests</span></span>](#meeting-policy-settings---participants--guests)

::: zone-end 

<span data-ttu-id="2284d-168"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="2284d-168"><a name="bkgeneral"> </a></span></span>

## <a name="meeting-policy-settings---general"></a><span data-ttu-id="2284d-169">会议策略设置-常规</span><span class="sxs-lookup"><span data-stu-id="2284d-169">Meeting policy settings - General</span></span>

- [<span data-ttu-id="2284d-170">允许在频道中立即开会</span><span class="sxs-lookup"><span data-stu-id="2284d-170">Allow Meet now in channels</span></span>](#allow-meet-now-in-channels)
- [<span data-ttu-id="2284d-171">允许 Outlook 加载项</span><span class="sxs-lookup"><span data-stu-id="2284d-171">Allow the Outlook add-in</span></span>](#allow-the-outlook-add-in)
- [<span data-ttu-id="2284d-172">允许频道会议安排</span><span class="sxs-lookup"><span data-stu-id="2284d-172">Allow channel meeting scheduling</span></span>](#allow-channel-meeting-scheduling)
- [<span data-ttu-id="2284d-173">允许安排私人会议</span><span class="sxs-lookup"><span data-stu-id="2284d-173">Allow scheduling private meetings</span></span>](#allow-scheduling-private-meetings)
- [<span data-ttu-id="2284d-174">允许在私人会议中立即开会</span><span class="sxs-lookup"><span data-stu-id="2284d-174">Allow Meet now in private meetings</span></span>](#allow-meet-now-in-private-meetings)

### <a name="allow-meet-now-in-channels"></a><span data-ttu-id="2284d-175">允许在频道中立即开会</span><span class="sxs-lookup"><span data-stu-id="2284d-175">Allow Meet now in channels</span></span>

<span data-ttu-id="2284d-176">这是每用户策略，在会议开始之前应用。</span><span class="sxs-lookup"><span data-stu-id="2284d-176">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="2284d-177">此设置控制用户是否可以在团队频道中启动临时会议。</span><span class="sxs-lookup"><span data-stu-id="2284d-177">This setting controls whether a user can start an ad hoc meeting in a Teams channel.</span></span> <span data-ttu-id="2284d-178">如果启用此操作，当用户在团队频道中发布消息时，用户可以单击 "撰写" 框下的 "**立即开会**" 以在频道中启动临时会议。</span><span class="sxs-lookup"><span data-stu-id="2284d-178">If you turn this on, when a user posts a message in a Teams channel, the user can click **Meet now** under the compose box to start an ad hoc meeting in the channel.</span></span> <span data-ttu-id="2284d-179">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="2284d-179">The default value is True.</span></span>

![显示邮件下方的 "立即开会" 图标的屏幕截图](media/meeting-policies-meet-now.png)

### <a name="allow-the-outlook-add-in"></a><span data-ttu-id="2284d-181">允许 Outlook 加载项</span><span class="sxs-lookup"><span data-stu-id="2284d-181">Allow the Outlook add-in</span></span>

<span data-ttu-id="2284d-182">这是每用户策略，在会议开始之前应用。</span><span class="sxs-lookup"><span data-stu-id="2284d-182">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="2284d-183">此设置控制是否可以从 Outlook （Windows、Mac、web 和手机）内安排团队会议。</span><span class="sxs-lookup"><span data-stu-id="2284d-183">This setting controls whether Teams meetings can be scheduled from within Outlook (Windows, Mac, web, and mobile).</span></span>

![显示安排新会议的功能的屏幕截图](media/meeting-policies-outlook-add-in.png)

<span data-ttu-id="2284d-185">如果关闭此功能，用户在 Outlook 中创建新会议时，无法安排团队会议。</span><span class="sxs-lookup"><span data-stu-id="2284d-185">If you turn this off, users are unable to schedule Teams meetings when they create a new meeting in Outlook.</span></span> <span data-ttu-id="2284d-186">例如，在 Windows 上的 Outlook 中，"**新建团队会议**" 选项不会显示在功能区中。</span><span class="sxs-lookup"><span data-stu-id="2284d-186">For example, in Outlook on Windows, the **New Teams Meeting** option won't show up in the ribbon.</span></span>

### <a name="allow-channel-meeting-scheduling"></a><span data-ttu-id="2284d-187">允许频道会议安排</span><span class="sxs-lookup"><span data-stu-id="2284d-187">Allow channel meeting scheduling</span></span>

<span data-ttu-id="2284d-188">这是每用户策略，在会议开始之前应用。</span><span class="sxs-lookup"><span data-stu-id="2284d-188">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="2284d-189">此设置控制用户是否可以在团队频道中安排会议。</span><span class="sxs-lookup"><span data-stu-id="2284d-189">This setting controls whether users can schedule a meeting in a Teams channel.</span></span>  <span data-ttu-id="2284d-190">如果关闭此功能，则当用户在团队频道中启动会议，并且为团队中的用户禁用 "**添加频道**" 选项时，"**安排会议**" 选项将不可用。</span><span class="sxs-lookup"><span data-stu-id="2284d-190">If you turn this off, the **Schedule a meeting** option won't be available to the user when they start a meeting in a Teams channel and the **Add channel** option is disabled for users in Teams.</span></span> <span data-ttu-id="2284d-191">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="2284d-191">The default value is True.</span></span>

![显示团队中的 "安排会议" 选项的屏幕截图](media/meeting-policies-schedule-a-meeting.png)

![显示 "选择要开会的频道" 选项的屏幕截图](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a><span data-ttu-id="2284d-194">允许安排私人会议</span><span class="sxs-lookup"><span data-stu-id="2284d-194">Allow scheduling private meetings</span></span>

<span data-ttu-id="2284d-195">这是每用户策略，在会议开始之前应用。</span><span class="sxs-lookup"><span data-stu-id="2284d-195">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="2284d-196">此设置控制用户是否可以在团队中安排私人会议。</span><span class="sxs-lookup"><span data-stu-id="2284d-196">This setting controls whether users can schedule private meetings in Teams.</span></span> <span data-ttu-id="2284d-197">当会议未发布到团队中的频道时，它是私有的。</span><span class="sxs-lookup"><span data-stu-id="2284d-197">A meeting is private when it's not published to a channel in a team.</span></span>

<span data-ttu-id="2284d-198">请注意，如果关闭 "**允许安排私人会议**" 和 "**允许频道会议计划**"，则会为团队中的用户禁用 "**添加必需与会者**" 和 "**添加频道**" 选项。</span><span class="sxs-lookup"><span data-stu-id="2284d-198">Note that if you turn off **Allow scheduling private meetings** and **Allow channel meeting scheduling**,  the **Add required attendees** and **Add channel** options are disabled for users in Teams.</span></span> <span data-ttu-id="2284d-199">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="2284d-199">The default value is True.</span></span>

### <a name="allow-meet-now-in-private-meetings"></a><span data-ttu-id="2284d-200">允许在私人会议中立即开会</span><span class="sxs-lookup"><span data-stu-id="2284d-200">Allow Meet now in private meetings</span></span>

<span data-ttu-id="2284d-201">这是每用户策略，在会议开始之前应用。</span><span class="sxs-lookup"><span data-stu-id="2284d-201">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="2284d-202">此设置控制用户是否可以启动 ad hoc 私人会议。</span><span class="sxs-lookup"><span data-stu-id="2284d-202">This setting controls whether a user can start an ad hoc private meeting.</span></span>  <span data-ttu-id="2284d-203">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="2284d-203">The default value is True.</span></span>

<span data-ttu-id="2284d-204"><a name="bkaudioandvideo"> </a></span><span class="sxs-lookup"><span data-stu-id="2284d-204"><a name="bkaudioandvideo"> </a></span></span>

## <a name="meeting-policy-settings---audio--video"></a><span data-ttu-id="2284d-205">会议策略设置-音频 & 视频</span><span class="sxs-lookup"><span data-stu-id="2284d-205">Meeting policy settings - Audio & video</span></span>

- [<span data-ttu-id="2284d-206">允许脚本</span><span class="sxs-lookup"><span data-stu-id="2284d-206">Allow transcription</span></span>](#allow-transcription)
- [<span data-ttu-id="2284d-207">允许云录制</span><span class="sxs-lookup"><span data-stu-id="2284d-207">Allow cloud recording</span></span>](#allow-cloud-recording)
- [<span data-ttu-id="2284d-208">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="2284d-208">Allow IP video</span></span>](#allow-ip-video)
- [<span data-ttu-id="2284d-209">媒体比特率（Kbs）</span><span class="sxs-lookup"><span data-stu-id="2284d-209">Media bit rate (Kbs)</span></span>](#media-bit-rate-kbs)

### <a name="allow-transcription"></a><span data-ttu-id="2284d-210">允许脚本</span><span class="sxs-lookup"><span data-stu-id="2284d-210">Allow transcription</span></span>

<span data-ttu-id="2284d-211">这是每个组织单位和每用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="2284d-211">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="2284d-212">此设置控制播放会议录制期间是否提供字幕和脚本功能。</span><span class="sxs-lookup"><span data-stu-id="2284d-212">This setting controls whether captions and transcription features are available during playback of meeting recordings.</span></span> <span data-ttu-id="2284d-213">如果关闭此功能，在播放会议录制的过程中，"**搜索**" 和 **"抄送**" 选项将不可用。</span><span class="sxs-lookup"><span data-stu-id="2284d-213">If you turn this off, the **Search** and **CC** options won't be available during playback of a meeting recording.</span></span> <span data-ttu-id="2284d-214">启动录制的人员需要启用此设置，以便录制还包括脚本。</span><span class="sxs-lookup"><span data-stu-id="2284d-214">The person who started the recording needs this setting turned on so that the recording also includes transcription.</span></span> 

<span data-ttu-id="2284d-215">请注意，当前只有在团队中将语言设置为英语且在会议中朗读英语的用户才支持使用录制的会议。</span><span class="sxs-lookup"><span data-stu-id="2284d-215">Note that transcription for recorded meetings is currently only supported for users who have the language in Teams set to English and when English is spoken in the meeting.</span></span>

![显示会议中的脚本选项的屏幕截图](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a><span data-ttu-id="2284d-217">允许云录制</span><span class="sxs-lookup"><span data-stu-id="2284d-217">Allow cloud recording</span></span>

<span data-ttu-id="2284d-218">这是每个组织单位和每用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="2284d-218">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="2284d-219">此设置控制是否可以录制此用户的会议。</span><span class="sxs-lookup"><span data-stu-id="2284d-219">This setting controls whether this user's meetings can be recorded.</span></span> <span data-ttu-id="2284d-220">录制可以由会议组织者或其他会议参与者启动（如果为参与者启用了该策略设置，并且他们是来自同一组织的经过身份验证的用户）。</span><span class="sxs-lookup"><span data-stu-id="2284d-220">The recording can be started by the meeting organizer or by another meeting participant if the policy setting is turned on for the participant and if they're an authenticated user from the same organization.</span></span>

<span data-ttu-id="2284d-221">组织外部的人员（如联盟用户和匿名用户）无法启动录制。</span><span class="sxs-lookup"><span data-stu-id="2284d-221">People outside your organization, such as federated and anonymous users, can't start the recording.</span></span> <span data-ttu-id="2284d-222">来宾用户无法启动或停止录制。</span><span class="sxs-lookup"><span data-stu-id="2284d-222">Guest users can't start or stop the recording.</span></span> 

![显示录制选项的屏幕截图](media/meeting-policies-recording.png)

<span data-ttu-id="2284d-224">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="2284d-224">Let's look at the following example.</span></span>

|<span data-ttu-id="2284d-225">用户</span><span class="sxs-lookup"><span data-stu-id="2284d-225">User</span></span> |<span data-ttu-id="2284d-226">会议策略</span><span class="sxs-lookup"><span data-stu-id="2284d-226">Meeting policy</span></span>  |<span data-ttu-id="2284d-227">允许云录制</span><span class="sxs-lookup"><span data-stu-id="2284d-227">Allow cloud recording</span></span> |
|---------|---------|---------|
|<span data-ttu-id="2284d-228">Daniela</span><span class="sxs-lookup"><span data-stu-id="2284d-228">Daniela</span></span> | <span data-ttu-id="2284d-229">全局</span><span class="sxs-lookup"><span data-stu-id="2284d-229">Global</span></span>   | <span data-ttu-id="2284d-230">False</span><span class="sxs-lookup"><span data-stu-id="2284d-230">False</span></span> |
|<span data-ttu-id="2284d-231">Amanda</span><span class="sxs-lookup"><span data-stu-id="2284d-231">Amanda</span></span> | <span data-ttu-id="2284d-232">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="2284d-232">Location1MeetingPolicy</span></span> | <span data-ttu-id="2284d-233">True</span><span class="sxs-lookup"><span data-stu-id="2284d-233">True</span></span>|
|<span data-ttu-id="2284d-234">John （外部用户）</span><span class="sxs-lookup"><span data-stu-id="2284d-234">John (external user)</span></span> | <span data-ttu-id="2284d-235">不适用</span><span class="sxs-lookup"><span data-stu-id="2284d-235">Not applicable</span></span> | <span data-ttu-id="2284d-236">不适用</span><span class="sxs-lookup"><span data-stu-id="2284d-236">Not applicable</span></span>|

<span data-ttu-id="2284d-237">按 Daniela 组织的会议无法录制，并且 Amanda 已启用策略设置，无法录制 Daniela 组织的会议。</span><span class="sxs-lookup"><span data-stu-id="2284d-237">Meetings organized by Daniela can't be recorded and Amanda, who has the policy setting enabled, can't record meetings organized by Daniela.</span></span> <span data-ttu-id="2284d-238">可记录由 Amanda 组织的会议，但 Daniela，他们已禁用策略设置，并且 John 是外部用户，无法录制 Amanda 组织的会议。</span><span class="sxs-lookup"><span data-stu-id="2284d-238">Meetings organized by Amanda can be recorded, however,  Daniela, who has the policy setting disabled and John who is an external user, can't record meetings organized by Amanda.</span></span>

<span data-ttu-id="2284d-239">若要了解有关云会议录制的详细信息，请参阅[团队云会议录制](cloud-recording.md)。</span><span class="sxs-lookup"><span data-stu-id="2284d-239">To learn more about cloud meeting recording, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

### <a name="allow-ip-video"></a><span data-ttu-id="2284d-240">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="2284d-240">Allow IP video</span></span>

<span data-ttu-id="2284d-241">这是每个组织单位和每用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="2284d-241">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="2284d-242">视频是会议的关键组件。</span><span class="sxs-lookup"><span data-stu-id="2284d-242">Video is a key component to meetings.</span></span> <span data-ttu-id="2284d-243">在某些组织中，管理员可能希望更好地控制哪些用户的会议有视频。</span><span class="sxs-lookup"><span data-stu-id="2284d-243">In some organizations, admins might want more control over which users' meetings have video.</span></span> <span data-ttu-id="2284d-244">此设置控制是否可以在用户托管的会议中以及用户开始的1:1 呼叫和组通话中打开视频。</span><span class="sxs-lookup"><span data-stu-id="2284d-244">This setting controls whether video can be turned on in meetings hosted by a user and in 1:1 calls and group calls started by a user.</span></span> <span data-ttu-id="2284d-245">已启用此策略的用户组织的会议，如果会议参与者也启用了该策略，则会议参与者允许会议中的视频共享。</span><span class="sxs-lookup"><span data-stu-id="2284d-245">Meetings organized by a user who has this policy enabled, allow video sharing in the meeting by the meeting participants, if the meeting participants also have the policy enabled.</span></span> <span data-ttu-id="2284d-246">未分配任何策略的会议参与者（如匿名和联盟参与者）将继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="2284d-246">Meeting participants who don't have any policies assigned (for example, anonymous and federated participants) inherit the policy of the meeting organizer.</span></span>

![显示带有音频和视频设置的会议的屏幕截图](media/meeting-policies-audio-video-settings.png)

<span data-ttu-id="2284d-248">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="2284d-248">Let's look at the following example.</span></span>

|<span data-ttu-id="2284d-249">用户</span><span class="sxs-lookup"><span data-stu-id="2284d-249">User</span></span> |<span data-ttu-id="2284d-250">会议策略</span><span class="sxs-lookup"><span data-stu-id="2284d-250">Meeting policy</span></span>  |<span data-ttu-id="2284d-251">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="2284d-251">Allow IP Video</span></span> |
|---------|---------|---------|
|<span data-ttu-id="2284d-252">Daniela</span><span class="sxs-lookup"><span data-stu-id="2284d-252">Daniela</span></span>   | <span data-ttu-id="2284d-253">全局</span><span class="sxs-lookup"><span data-stu-id="2284d-253">Global</span></span>   | <span data-ttu-id="2284d-254">True</span><span class="sxs-lookup"><span data-stu-id="2284d-254">True</span></span>        |
|<span data-ttu-id="2284d-255">Amanda</span><span class="sxs-lookup"><span data-stu-id="2284d-255">Amanda</span></span>    | <span data-ttu-id="2284d-256">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="2284d-256">Location1MeetingPolicy</span></span>        | <span data-ttu-id="2284d-257">False</span><span class="sxs-lookup"><span data-stu-id="2284d-257">False</span></span>      |

<span data-ttu-id="2284d-258">通过 Daniela 托管的会议允许打开视频。</span><span class="sxs-lookup"><span data-stu-id="2284d-258">Meetings hosted by Daniela allow video to be turned on.</span></span> <span data-ttu-id="2284d-259">Daniela 可以加入会议并打开视频。</span><span class="sxs-lookup"><span data-stu-id="2284d-259">Daniela can join the meeting and turn on video.</span></span> <span data-ttu-id="2284d-260">Amanda 无法在 Daniela 的会议中启用视频，因为 Amanda 的策略设置为 "不允许视频"。</span><span class="sxs-lookup"><span data-stu-id="2284d-260">Amanda can't turn on video in Daniela's meeting because Amanda's policy is set to not allow video.</span></span> <span data-ttu-id="2284d-261">Amanda 可以查看会议中其他参与者共享的视频。</span><span class="sxs-lookup"><span data-stu-id="2284d-261">Amanda can see videos shared by other participants in the meeting.</span></span>

<span data-ttu-id="2284d-262">在 Amanda 托管的会议中，无论分配给他们的视频策略如何，任何人都无法打开视频。</span><span class="sxs-lookup"><span data-stu-id="2284d-262">In meetings hosted by Amanda, no one can turn on video, regardless of the video policy assigned to them.</span></span> <span data-ttu-id="2284d-263">这意味着 Daniela 无法在 Amanda 的会议中打开视频。</span><span class="sxs-lookup"><span data-stu-id="2284d-263">This means Daniela can't turn on video in Amanda's meetings.</span></span>  

<span data-ttu-id="2284d-264">如果 Daniela 通过视频 Amanda 调用，Amanda 只能通过音频应答呼叫。</span><span class="sxs-lookup"><span data-stu-id="2284d-264">If Daniela calls Amanda with video on, Amanda can answer the call with audio only.</span></span>  <span data-ttu-id="2284d-265">当呼叫连接时，Amanda 可以看到 Daniela 的视频，但无法打开视频。</span><span class="sxs-lookup"><span data-stu-id="2284d-265">When the call is connected, Amanda can see Daniela's video, but can't turn on video.</span></span> <span data-ttu-id="2284d-266">如果 Amanda 呼叫 Daniela，Daniela 可以通过视频和音频接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="2284d-266">If Amanda calls Daniela, Daniela can answer the call with video and audio.</span></span> <span data-ttu-id="2284d-267">通话接通后，Daniela 可以根据需要打开或关闭她的视频。</span><span class="sxs-lookup"><span data-stu-id="2284d-267">When the call is connected, Daniela can turn on or turn off her video, as needed.</span></span>

### <a name="media-bit-rate-kbs"></a><span data-ttu-id="2284d-268">媒体比特率（Kbs）</span><span class="sxs-lookup"><span data-stu-id="2284d-268">Media bit rate (Kbs)</span></span>

<span data-ttu-id="2284d-269">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="2284d-269">This is a per-user policy.</span></span> <span data-ttu-id="2284d-270">此设置确定用户的通话和会议中音频、视频和基于视频的应用共享传输的媒体比特率。</span><span class="sxs-lookup"><span data-stu-id="2284d-270">This setting determines the media bit rate for audio, video, and video-based app sharing transmissions in calls and meetings for the user.</span></span> <span data-ttu-id="2284d-271">它同时应用于呼叫或会议中用户的上行媒体和下行媒体遍历。</span><span class="sxs-lookup"><span data-stu-id="2284d-271">It's applied to both the uplink and downlink media traversal for users in the call or meeting.</span></span> <span data-ttu-id="2284d-272">此设置使你能够更细致地控制组织中的带宽管理。</span><span class="sxs-lookup"><span data-stu-id="2284d-272">This setting gives you granular control over managing bandwidth in your organization.</span></span> <span data-ttu-id="2284d-273">根据用户所需的会议方案，我们建议有足够的带宽来实现优质体验。</span><span class="sxs-lookup"><span data-stu-id="2284d-273">Depending on the meetings scenarios required by users, we recommend having enough bandwidth in place for a good quality experience.</span></span> <span data-ttu-id="2284d-274">最小值为 30 Kbps，最大值取决于会议方案。</span><span class="sxs-lookup"><span data-stu-id="2284d-274">The minimum value is 30 Kbps and the maximum value depends on the meeting scenario.</span></span> <span data-ttu-id="2284d-275">若要了解更多有关建议的最小带宽以供团队的优质会议、通话和实时活动，请参阅[带宽要求](prepare-network.md#bandwidth-requirements)。</span><span class="sxs-lookup"><span data-stu-id="2284d-275">To learn more about the minimum recommended bandwidth for good quality meetings, calls, and live events in Teams, see [Bandwidth requirements](prepare-network.md#bandwidth-requirements).</span></span>

<span data-ttu-id="2284d-276">如果会议带宽不足，参与者会看到指示网络质量不佳的消息。</span><span class="sxs-lookup"><span data-stu-id="2284d-276">If there isn't enough bandwidth for a meeting, participants see a message that indicates poor network quality.</span></span>

<span data-ttu-id="2284d-277">对于需要最高质量视频体验的会议（如 CEO 董事会会议和团队现场活动），我们建议您将带宽设置为 10 Mbps。</span><span class="sxs-lookup"><span data-stu-id="2284d-277">For meetings that need the highest quality video experience, such as CEO board meetings and Teams live events, we recommend you set the bandwidth to 10 Mbps.</span></span> <span data-ttu-id="2284d-278">即使设置了最大体验，团队媒体堆栈也会在检测到某些网络条件时适应低带宽条件，具体取决于方案。</span><span class="sxs-lookup"><span data-stu-id="2284d-278">Even when the maximum experience is set, the Teams media stack adapts to low bandwidth conditions when certain network conditions are detected, depending on the scenario.</span></span> 

## <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="2284d-279">会议策略设置-内容共享</span><span class="sxs-lookup"><span data-stu-id="2284d-279">Meeting policy settings - Content sharing</span></span>

- [<span data-ttu-id="2284d-280">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="2284d-280">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="2284d-281">允许参与者授予或请求控制</span><span class="sxs-lookup"><span data-stu-id="2284d-281">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="2284d-282">允许外部参与者授予或请求控制</span><span class="sxs-lookup"><span data-stu-id="2284d-282">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="2284d-283">允许 PowerPoint 共享</span><span class="sxs-lookup"><span data-stu-id="2284d-283">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="2284d-284">允许白板</span><span class="sxs-lookup"><span data-stu-id="2284d-284">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="2284d-285">允许共享笔记</span><span class="sxs-lookup"><span data-stu-id="2284d-285">Allow shared notes</span></span>](#allow-shared-notes)

### <a name="screen-sharing-mode"></a><span data-ttu-id="2284d-286">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="2284d-286">Screen sharing mode</span></span>

<span data-ttu-id="2284d-287">这是每个组织单位和每用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="2284d-287">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="2284d-288">此设置控制是否允许在用户的会议中共享桌面和/或窗口共享。</span><span class="sxs-lookup"><span data-stu-id="2284d-288">This setting controls whether desktop and/or window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="2284d-289">未分配任何策略的会议参与者（如匿名、来宾、B2B 和联盟参与者）将继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="2284d-289">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="2284d-290">设置值</span><span class="sxs-lookup"><span data-stu-id="2284d-290">Setting value</span></span> |<span data-ttu-id="2284d-291">行为</span><span class="sxs-lookup"><span data-stu-id="2284d-291">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="2284d-292">**整个屏幕**</span><span class="sxs-lookup"><span data-stu-id="2284d-292">**Entire screen**</span></span>    | <span data-ttu-id="2284d-293">会议中允许进行完整的桌面共享和应用程序共享</span><span class="sxs-lookup"><span data-stu-id="2284d-293">Full desktop sharing and application sharing is allowed in the meeting</span></span> |
|<span data-ttu-id="2284d-294">**单应用程序**</span><span class="sxs-lookup"><span data-stu-id="2284d-294">**Single application**</span></span>   | <span data-ttu-id="2284d-295">允许在会议中共享应用程序</span><span class="sxs-lookup"><span data-stu-id="2284d-295">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="2284d-296">**已禁用**</span><span class="sxs-lookup"><span data-stu-id="2284d-296">**Disabled**</span></span>     |<span data-ttu-id="2284d-297">会议中已关闭屏幕共享和应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="2284d-297">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="2284d-298">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="2284d-298">Let's look at the following example.</span></span>

|<span data-ttu-id="2284d-299">用户</span><span class="sxs-lookup"><span data-stu-id="2284d-299">User</span></span> |<span data-ttu-id="2284d-300">会议策略</span><span class="sxs-lookup"><span data-stu-id="2284d-300">Meeting policy</span></span> |<span data-ttu-id="2284d-301">屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="2284d-301">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="2284d-302">Daniela</span><span class="sxs-lookup"><span data-stu-id="2284d-302">Daniela</span></span>  | <span data-ttu-id="2284d-303">全局</span><span class="sxs-lookup"><span data-stu-id="2284d-303">Global</span></span>   | <span data-ttu-id="2284d-304">整个屏幕</span><span class="sxs-lookup"><span data-stu-id="2284d-304">Entire screen</span></span> |
|<span data-ttu-id="2284d-305">Amanda</span><span class="sxs-lookup"><span data-stu-id="2284d-305">Amanda</span></span>   | <span data-ttu-id="2284d-306">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="2284d-306">Location1MeetingPolicy</span></span>  | <span data-ttu-id="2284d-307">已禁用</span><span class="sxs-lookup"><span data-stu-id="2284d-307">Disabled</span></span> |

<span data-ttu-id="2284d-308">由 Daniela 托管的会议允许会议参与者共享其整个屏幕或特定应用程序。</span><span class="sxs-lookup"><span data-stu-id="2284d-308">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="2284d-309">如果 Amanda 加入 Daniela 的会议，Amanda 无法共享她的屏幕或特定应用程序，因为她的策略设置已被禁用。</span><span class="sxs-lookup"><span data-stu-id="2284d-309">If Amanda joins Daniela's meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="2284d-310">在 Amanda 托管的会议中，不允许任何人共享其屏幕或单个应用程序，而不管分配给他们的屏幕共享模式策略如何。</span><span class="sxs-lookup"><span data-stu-id="2284d-310">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span> <span data-ttu-id="2284d-311">这意味着 Daniela 不能在 Amanda 的会议中共享她的屏幕或单个应用程序。</span><span class="sxs-lookup"><span data-stu-id="2284d-311">This means that Daniela can't share her screen or a single application in Amanda's meetings.</span></span>  

<span data-ttu-id="2284d-312">当前，如果用户使用的是 Google Chrome，则用户无法在团队会议中播放视频或共享其屏幕。</span><span class="sxs-lookup"><span data-stu-id="2284d-312">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

### <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="2284d-313">允许参与者授予或请求控制</span><span class="sxs-lookup"><span data-stu-id="2284d-313">Allow a participant to give or request control</span></span>

<span data-ttu-id="2284d-314">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="2284d-314">This is a per-user policy.</span></span> <span data-ttu-id="2284d-315">此设置控制用户是否可以将共享桌面或窗口的控制权授予其他会议参与者。</span><span class="sxs-lookup"><span data-stu-id="2284d-315">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="2284d-316">若要赋予控制权，请将鼠标悬停在屏幕顶部。</span><span class="sxs-lookup"><span data-stu-id="2284d-316">To give control, hover over the top of the screen.</span></span> 

<span data-ttu-id="2284d-317">如果为用户启用此设置，则 "**授予控制权**" 选项显示在共享会话的顶部栏中。</span><span class="sxs-lookup"><span data-stu-id="2284d-317">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span> 

![显示 "提供控制" 选项的屏幕截图](media/meeting-policies-give-control.png)

<span data-ttu-id="2284d-319">如果用户的设置处于关闭状态，则 "**提供控制**" 选项不可用。</span><span class="sxs-lookup"><span data-stu-id="2284d-319">If the settings is turned off for the user, the **Give Control** option isn't available.</span></span>

![显示 "提供控件" 选项不可用的屏幕截图](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="2284d-321">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="2284d-321">Let's look at the following example.</span></span>

|<span data-ttu-id="2284d-322">用户</span><span class="sxs-lookup"><span data-stu-id="2284d-322">User</span></span> |<span data-ttu-id="2284d-323">会议策略</span><span class="sxs-lookup"><span data-stu-id="2284d-323">Meeting policy</span></span>  |<span data-ttu-id="2284d-324">允许参与者授予或请求控制</span><span class="sxs-lookup"><span data-stu-id="2284d-324">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="2284d-325">Daniela</span><span class="sxs-lookup"><span data-stu-id="2284d-325">Daniela</span></span>   | <span data-ttu-id="2284d-326">全局</span><span class="sxs-lookup"><span data-stu-id="2284d-326">Global</span></span>   | <span data-ttu-id="2284d-327">True</span><span class="sxs-lookup"><span data-stu-id="2284d-327">True</span></span>       |
|<span data-ttu-id="2284d-328">Babek</span><span class="sxs-lookup"><span data-stu-id="2284d-328">Babek</span></span>    | <span data-ttu-id="2284d-329">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="2284d-329">Location1MeetingPolicy</span></span>        | <span data-ttu-id="2284d-330">False</span><span class="sxs-lookup"><span data-stu-id="2284d-330">False</span></span>   |

<span data-ttu-id="2284d-331">Daniela 可以将共享桌面或窗口的控制权交给 Babek 组织的会议中的其他参与者，Babek 无法将控制权授予其他参与者。</span><span class="sxs-lookup"><span data-stu-id="2284d-331">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek whereas Babek can't give control to other participants.</span></span>

<span data-ttu-id="2284d-332">若要使用 PowerShell 控制哪些人可以授予控制请求或接受控制请求，请使用 AllowParticipantGiveRequestControl cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2284d-332">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="2284d-333">若要在共享期间提供和控制共享内容，双方都必须使用团队桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="2284d-333">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="2284d-334">如果任何一方在浏览器中运行 Teams，则不支持控制。</span><span class="sxs-lookup"><span data-stu-id="2284d-334">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="2284d-335">这是由我们计划修复的一个技术限制造成。</span><span class="sxs-lookup"><span data-stu-id="2284d-335">This is due to a technical limitation that we're planning to fix.</span></span> 

### <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="2284d-336">允许外部参与者授予或请求控制</span><span class="sxs-lookup"><span data-stu-id="2284d-336">Allow an external participant to give or request control</span></span>

<span data-ttu-id="2284d-337">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="2284d-337">This is a per-user policy.</span></span> <span data-ttu-id="2284d-338">此设置控制会议中的外部参与者是否可以将其共享桌面或窗口的控制权交给会议中的其他参与者。</span><span class="sxs-lookup"><span data-stu-id="2284d-338">This setting controls whether external participants in a meeting can give control of their shared desktop or window to other participants in the meeting.</span></span> <span data-ttu-id="2284d-339">团队会议中的外部参与者可以按如下方式进行分类：</span><span class="sxs-lookup"><span data-stu-id="2284d-339">External participants in Teams meetings can be categorized as follows:</span></span>  

- <span data-ttu-id="2284d-340">匿名用户</span><span class="sxs-lookup"><span data-stu-id="2284d-340">Anonymous user</span></span>
- <span data-ttu-id="2284d-341">来宾用户</span><span class="sxs-lookup"><span data-stu-id="2284d-341">Guest users</span></span>  
- <span data-ttu-id="2284d-342">B2B 用户</span><span class="sxs-lookup"><span data-stu-id="2284d-342">B2B user</span></span>
- <span data-ttu-id="2284d-343">联合用户</span><span class="sxs-lookup"><span data-stu-id="2284d-343">Federated user</span></span>  

<span data-ttu-id="2284d-344">联盟用户是否可以向外部用户授予控制权，同时共享受允许外部参与者在其组织中**授予或请求控制**设置的控制。</span><span class="sxs-lookup"><span data-stu-id="2284d-344">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="2284d-345">若要使用 PowerShell 控制外部参与者是否可以授予控制或接受控制请求，请使用 AllowExternalParticipantGiveRequestControl cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2284d-345">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="2284d-346">允许 PowerPoint 共享</span><span class="sxs-lookup"><span data-stu-id="2284d-346">Allow PowerPoint sharing</span></span>

<span data-ttu-id="2284d-347">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="2284d-347">This is a per-user policy.</span></span> <span data-ttu-id="2284d-348">此设置控制用户是否可以在会议中共享 PowerPoint 幻灯片放映。</span><span class="sxs-lookup"><span data-stu-id="2284d-348">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="2284d-349">外部用户（包括匿名用户、来宾和联盟用户）继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="2284d-349">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="2284d-350">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="2284d-350">Let's look at the following example.</span></span>

|<span data-ttu-id="2284d-351">用户</span><span class="sxs-lookup"><span data-stu-id="2284d-351">User</span></span> |<span data-ttu-id="2284d-352">会议策略</span><span class="sxs-lookup"><span data-stu-id="2284d-352">Meeting policy</span></span>  |<span data-ttu-id="2284d-353">允许 PowerPoint 共享</span><span class="sxs-lookup"><span data-stu-id="2284d-353">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="2284d-354">Daniela</span><span class="sxs-lookup"><span data-stu-id="2284d-354">Daniela</span></span>   | <span data-ttu-id="2284d-355">全局</span><span class="sxs-lookup"><span data-stu-id="2284d-355">Global</span></span>   | <span data-ttu-id="2284d-356">True</span><span class="sxs-lookup"><span data-stu-id="2284d-356">True</span></span>       |
|<span data-ttu-id="2284d-357">Amanda</span><span class="sxs-lookup"><span data-stu-id="2284d-357">Amanda</span></span>   | <span data-ttu-id="2284d-358">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="2284d-358">Location1MeetingPolicy</span></span>        | <span data-ttu-id="2284d-359">False</span><span class="sxs-lookup"><span data-stu-id="2284d-359">False</span></span>   |

<span data-ttu-id="2284d-360">Amanda 不能在会议中共享 PowerPoint 幻灯片卡座，即使她是会议组织者也是如此。</span><span class="sxs-lookup"><span data-stu-id="2284d-360">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="2284d-361">Daniela 可以共享 PowerPoint 幻灯片放映，即使会议由 Amanda 组织。</span><span class="sxs-lookup"><span data-stu-id="2284d-361">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="2284d-362">Amanda 可以查看会议中其他人共享的 PowerPoint 幻灯片卡座，即使她无法共享 PowerPoint 幻灯片放映。</span><span class="sxs-lookup"><span data-stu-id="2284d-362">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

### <a name="allow-whiteboard"></a><span data-ttu-id="2284d-363">允许白板</span><span class="sxs-lookup"><span data-stu-id="2284d-363">Allow whiteboard</span></span>

<span data-ttu-id="2284d-364">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="2284d-364">This is a per-user policy.</span></span> <span data-ttu-id="2284d-365">此设置控制用户是否可以在会议中共享白板。</span><span class="sxs-lookup"><span data-stu-id="2284d-365">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="2284d-366">外部用户（包括匿名用户、B2B 和联盟用户）继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="2284d-366">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> 

<span data-ttu-id="2284d-367">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="2284d-367">Let's look at the following example.</span></span>

|<span data-ttu-id="2284d-368">用户</span><span class="sxs-lookup"><span data-stu-id="2284d-368">User</span></span> |<span data-ttu-id="2284d-369">会议策略</span><span class="sxs-lookup"><span data-stu-id="2284d-369">Meeting policy</span></span>  |<span data-ttu-id="2284d-370">允许白板</span><span class="sxs-lookup"><span data-stu-id="2284d-370">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="2284d-371">Daniela</span><span class="sxs-lookup"><span data-stu-id="2284d-371">Daniela</span></span>   | <span data-ttu-id="2284d-372">全局</span><span class="sxs-lookup"><span data-stu-id="2284d-372">Global</span></span>   | <span data-ttu-id="2284d-373">True</span><span class="sxs-lookup"><span data-stu-id="2284d-373">True</span></span>       |
|<span data-ttu-id="2284d-374">Amanda</span><span class="sxs-lookup"><span data-stu-id="2284d-374">Amanda</span></span>   | <span data-ttu-id="2284d-375">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="2284d-375">Location1MeetingPolicy</span></span>        | <span data-ttu-id="2284d-376">False</span><span class="sxs-lookup"><span data-stu-id="2284d-376">False</span></span>   |

<span data-ttu-id="2284d-377">Amanda 无法在会议中共享白板，即使她是会议组织者也是如此。</span><span class="sxs-lookup"><span data-stu-id="2284d-377">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="2284d-378">即使会议是按 Amanda 组织的，Daniela 也可以共享白板。</span><span class="sxs-lookup"><span data-stu-id="2284d-378">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

### <a name="allow-shared-notes"></a><span data-ttu-id="2284d-379">允许共享笔记</span><span class="sxs-lookup"><span data-stu-id="2284d-379">Allow shared notes</span></span>

<span data-ttu-id="2284d-380">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="2284d-380">This is a per-user policy.</span></span> <span data-ttu-id="2284d-381">此设置控制用户是否可以在会议中创建和共享笔记。</span><span class="sxs-lookup"><span data-stu-id="2284d-381">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="2284d-382">外部用户（包括匿名用户、B2B 和联盟用户）继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="2284d-382">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="2284d-383">"**会议笔记**" 选项卡目前仅在具有少于20个参与者的会议中受支持。</span><span class="sxs-lookup"><span data-stu-id="2284d-383">The **Meeting Notes** tab is currently only supported in meetings that have less than 20 participants.</span></span>

<span data-ttu-id="2284d-384">我们来看看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="2284d-384">Let's look at the following example.</span></span>

|<span data-ttu-id="2284d-385">用户</span><span class="sxs-lookup"><span data-stu-id="2284d-385">User</span></span> |<span data-ttu-id="2284d-386">会议策略</span><span class="sxs-lookup"><span data-stu-id="2284d-386">Meeting policy</span></span>  |<span data-ttu-id="2284d-387">允许共享笔记</span><span class="sxs-lookup"><span data-stu-id="2284d-387">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="2284d-388">Daniela</span><span class="sxs-lookup"><span data-stu-id="2284d-388">Daniela</span></span>   | <span data-ttu-id="2284d-389">全局</span><span class="sxs-lookup"><span data-stu-id="2284d-389">Global</span></span>   | <span data-ttu-id="2284d-390">True</span><span class="sxs-lookup"><span data-stu-id="2284d-390">True</span></span>       |
|<span data-ttu-id="2284d-391">Amanda</span><span class="sxs-lookup"><span data-stu-id="2284d-391">Amanda</span></span>   | <span data-ttu-id="2284d-392">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="2284d-392">Location1MeetingPolicy</span></span> | <span data-ttu-id="2284d-393">False</span><span class="sxs-lookup"><span data-stu-id="2284d-393">False</span></span> |

<span data-ttu-id="2284d-394">Daniela 可以在 Amanda 的会议中做笔记，Amanda 不能在任何会议中做笔记。</span><span class="sxs-lookup"><span data-stu-id="2284d-394">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>

## <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="2284d-395">会议策略设置-参与者 & 来宾</span><span class="sxs-lookup"><span data-stu-id="2284d-395">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="2284d-396">这些设置控制在会议厅中等待的会议参与者，以及他们在会议中允许的参与级别。</span><span class="sxs-lookup"><span data-stu-id="2284d-396">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="2284d-397">让匿名人员开始会议</span><span class="sxs-lookup"><span data-stu-id="2284d-397">Let anonymous people start a meeting</span></span>](#let-anonymous-people-start-a-meeting)
- [<span data-ttu-id="2284d-398">自动允许人员</span><span class="sxs-lookup"><span data-stu-id="2284d-398">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="2284d-399">允许拨入用户绕过大厅</span><span class="sxs-lookup"><span data-stu-id="2284d-399">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby)
- [<span data-ttu-id="2284d-400">启用实时字幕</span><span class="sxs-lookup"><span data-stu-id="2284d-400">Enable live captions </span></span>](#enable-live-captions)
- [<span data-ttu-id="2284d-401">允许在会议中聊天</span><span class="sxs-lookup"><span data-stu-id="2284d-401">Allow chat in meetings </span></span>](#allow-chat-in-meetings)

> [!NOTE]
><span data-ttu-id="2284d-402">用于加入会议的选项会有所不同，具体取决于每个团队组的设置和连接方法。</span><span class="sxs-lookup"><span data-stu-id="2284d-402">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="2284d-403">如果你的组具有音频会议，并使用它进行连接，请参阅[Office 365 中的音频会议](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="2284d-403">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing in Office 365](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="2284d-404">如果你的团队组没有音频会议，请参阅[在团队中加入会议](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)。</span><span class="sxs-lookup"><span data-stu-id="2284d-404">If your Teams group does not have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

### <a name="let-anonymous-people-start-a-meeting"></a><span data-ttu-id="2284d-405">让匿名人员开始会议</span><span class="sxs-lookup"><span data-stu-id="2284d-405">Let anonymous people start a meeting</span></span>

<span data-ttu-id="2284d-406">这是每个组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="2284d-406">This is a per-organizer policy.</span></span> <span data-ttu-id="2284d-407">此设置控制匿名人员（包括 B2B）和联盟用户是否可以在没有经过身份验证的组织中加入用户的会议。</span><span class="sxs-lookup"><span data-stu-id="2284d-407">This setting controls whether anonymous people, including B2B, and federated users, can join the user's meeting without an authenticated user from the organization in attendance.</span></span> <span data-ttu-id="2284d-408">默认值为 False。</span><span class="sxs-lookup"><span data-stu-id="2284d-408">The default value is False.</span></span>

![显示一条消息给正在等待的用户的屏幕截图](media/meeting-policies-anonymous-user-lobby.png)

<span data-ttu-id="2284d-410">下面是在会议中提供了身份验证用户时匿名用户的加入行为。</span><span class="sxs-lookup"><span data-stu-id="2284d-410">Here's the join behavior of anonymous people when authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="2284d-411">让匿名人员开始会议</span><span class="sxs-lookup"><span data-stu-id="2284d-411">Let anonymous people start a meeting</span></span>  |<span data-ttu-id="2284d-412">自动允许人员</span><span class="sxs-lookup"><span data-stu-id="2284d-412">Automatically admit people</span></span> |<span data-ttu-id="2284d-413">匿名人员的加入行为</span><span class="sxs-lookup"><span data-stu-id="2284d-413">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="2284d-414">True</span><span class="sxs-lookup"><span data-stu-id="2284d-414">True</span></span>    | <span data-ttu-id="2284d-415">所有人</span><span class="sxs-lookup"><span data-stu-id="2284d-415">Everyone</span></span>      | <span data-ttu-id="2284d-416">直接加入</span><span class="sxs-lookup"><span data-stu-id="2284d-416">Join directly</span></span>         |
|   | <span data-ttu-id="2284d-417">您的组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="2284d-417">Everyone in your organization</span></span>       | <span data-ttu-id="2284d-418">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="2284d-418">Wait in lobby</span></span>        |
|   | <span data-ttu-id="2284d-419">组织和联盟组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="2284d-419">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="2284d-420">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="2284d-420">Wait in lobby</span></span>         |
|<span data-ttu-id="2284d-421">False</span><span class="sxs-lookup"><span data-stu-id="2284d-421">False</span></span>    | <span data-ttu-id="2284d-422">所有人</span><span class="sxs-lookup"><span data-stu-id="2284d-422">Everyone</span></span>        | <span data-ttu-id="2284d-423">直接加入</span><span class="sxs-lookup"><span data-stu-id="2284d-423">Join directly</span></span>        |
|   | <span data-ttu-id="2284d-424">您的组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="2284d-424">Everyone in your organization</span></span>     | <span data-ttu-id="2284d-425">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="2284d-425">Wait in lobby</span></span>        |
|   | <span data-ttu-id="2284d-426">组织和联盟组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="2284d-426">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="2284d-427">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="2284d-427">Wait in lobby</span></span>         |

<span data-ttu-id="2284d-428">下面是当会议中没有经过身份验证的用户时匿名用户的加入行为。</span><span class="sxs-lookup"><span data-stu-id="2284d-428">Here's the join behavior of anonymous people when no authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="2284d-429">让匿名人员开始会议</span><span class="sxs-lookup"><span data-stu-id="2284d-429">Let anonymous people start a meeting</span></span> |<span data-ttu-id="2284d-430">自动允许人员</span><span class="sxs-lookup"><span data-stu-id="2284d-430">Automatically admit people</span></span>  |<span data-ttu-id="2284d-431">匿名人员的加入行为</span><span class="sxs-lookup"><span data-stu-id="2284d-431">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="2284d-432">True</span><span class="sxs-lookup"><span data-stu-id="2284d-432">True</span></span>    | <span data-ttu-id="2284d-433">所有人</span><span class="sxs-lookup"><span data-stu-id="2284d-433">Everyone</span></span>      | <span data-ttu-id="2284d-434">直接加入</span><span class="sxs-lookup"><span data-stu-id="2284d-434">Join directly</span></span>         |
|   | <span data-ttu-id="2284d-435">您的组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="2284d-435">Everyone in your organization</span></span>       | <span data-ttu-id="2284d-436">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="2284d-436">Wait in lobby</span></span>        |
|   | <span data-ttu-id="2284d-437">组织和联盟组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="2284d-437">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="2284d-438">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="2284d-438">Wait in lobby</span></span>         |
|<span data-ttu-id="2284d-439">False</span><span class="sxs-lookup"><span data-stu-id="2284d-439">False</span></span>    | <span data-ttu-id="2284d-440">所有人</span><span class="sxs-lookup"><span data-stu-id="2284d-440">Everyone</span></span>        | <span data-ttu-id="2284d-441">在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="2284d-441">Wait in lobby.</span></span> <span data-ttu-id="2284d-442">当第一个经过身份验证的用户加入会议时，将自动向用户提供许可。</span><span class="sxs-lookup"><span data-stu-id="2284d-442">Users are automatically admitted when the first authenticated user joins the meeting.</span></span>        |
|   | <span data-ttu-id="2284d-443">您的组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="2284d-443">Everyone in your organization</span></span>     |<span data-ttu-id="2284d-444">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="2284d-444">Wait in lobby</span></span>         |
|   | <span data-ttu-id="2284d-445">组织和联盟组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="2284d-445">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="2284d-446">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="2284d-446">Wait in lobby</span></span>         |

### <a name="automatically-admit-people"></a><span data-ttu-id="2284d-447">自动允许人员</span><span class="sxs-lookup"><span data-stu-id="2284d-447">Automatically admit people</span></span>

<span data-ttu-id="2284d-448">这是每个组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="2284d-448">This is a per-organizer policy.</span></span> <span data-ttu-id="2284d-449">此设置控制用户是否直接加入会议或在大厅中等待，直到他们被经过身份验证的用户许可。</span><span class="sxs-lookup"><span data-stu-id="2284d-449">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span>

![显示会议厅中有用户的会议的屏幕截图](media/meeting-policies-lobby.png)

 <span data-ttu-id="2284d-451">会议组织者可以单击会议邀请中的 "**会议选项**"，为其计划的每个会议更改此设置。</span><span class="sxs-lookup"><span data-stu-id="2284d-451">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span>
  
|<span data-ttu-id="2284d-452">设置值</span><span class="sxs-lookup"><span data-stu-id="2284d-452">Setting value</span></span>  |<span data-ttu-id="2284d-453">联接行为</span><span class="sxs-lookup"><span data-stu-id="2284d-453">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="2284d-454">**所有人**</span><span class="sxs-lookup"><span data-stu-id="2284d-454">**Everyone**</span></span>   |<span data-ttu-id="2284d-455">所有会议参与者都直接加入会议，而无需在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="2284d-455">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="2284d-456">这包括经过身份验证的用户、联盟用户、来宾、匿名用户和通过电话拨入的用户。</span><span class="sxs-lookup"><span data-stu-id="2284d-456">This includes authenticated users, federated users, guests, anonymous users, and people who dial in by phone.</span></span>       |
|<span data-ttu-id="2284d-457">**组织和联盟组织中的每个人**</span><span class="sxs-lookup"><span data-stu-id="2284d-457">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="2284d-458">组织内的经过身份验证的用户，包括来宾用户和联盟组织中的用户，直接加入会议，而无需在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="2284d-458">Authenticated users within the organization, including guest users and the users from federated organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="2284d-459">通过电话拨入的匿名用户和用户在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="2284d-459">Anonymous users and users who dial in by phone wait in the lobby.</span></span>   |
|<span data-ttu-id="2284d-460">**您的组织中的每个人**</span><span class="sxs-lookup"><span data-stu-id="2284d-460">**Everyone in your organization**</span></span>    |<span data-ttu-id="2284d-461">来自组织内部的经过身份验证的用户（包括来宾用户）直接加入会议，而无需在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="2284d-461">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="2284d-462">联合用户、匿名用户和通过电话拨入的用户在大厅中等待。</span><span class="sxs-lookup"><span data-stu-id="2284d-462">Federated users, anonymous users, and users who dial in by phone wait in the lobby.</span></span> <span data-ttu-id="2284d-463">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="2284d-463">This is the default setting.</span></span>           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a><span data-ttu-id="2284d-464">允许拨入用户绕过大厅</span><span class="sxs-lookup"><span data-stu-id="2284d-464">Allow dial-in users to bypass the lobby</span></span>

<span data-ttu-id="2284d-465">这是每个组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="2284d-465">This is a per-organizer policy.</span></span> <span data-ttu-id="2284d-466">此设置控制通过电话拨入的用户是否直接加入会议或在会议厅中等待，而不管 "是否**自动允许人员**" 设置。</span><span class="sxs-lookup"><span data-stu-id="2284d-466">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span> <span data-ttu-id="2284d-467">默认值为 False。</span><span class="sxs-lookup"><span data-stu-id="2284d-467">The default value is False.</span></span>

<span data-ttu-id="2284d-468">下面是通过电话拨入的用户的加入行为。</span><span class="sxs-lookup"><span data-stu-id="2284d-468">Here's the join behavior of people who dial in by phone.</span></span>

|<span data-ttu-id="2284d-469">允许拨入用户绕过大厅</span><span class="sxs-lookup"><span data-stu-id="2284d-469">Allow dial-in users to bypass the lobby</span></span>  |<span data-ttu-id="2284d-470">自动允许人员</span><span class="sxs-lookup"><span data-stu-id="2284d-470">Automatically admit people</span></span>  |<span data-ttu-id="2284d-471">拨入的用户的加入行为</span><span class="sxs-lookup"><span data-stu-id="2284d-471">Join behavior of people who dial in</span></span> |
|---------|---------|---------|
|<span data-ttu-id="2284d-472">True</span><span class="sxs-lookup"><span data-stu-id="2284d-472">True</span></span>    | <span data-ttu-id="2284d-473">所有人</span><span class="sxs-lookup"><span data-stu-id="2284d-473">Everyone</span></span>      | <span data-ttu-id="2284d-474">直接加入</span><span class="sxs-lookup"><span data-stu-id="2284d-474">Join directly</span></span>         |
|   | <span data-ttu-id="2284d-475">您的组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="2284d-475">Everyone in your organization</span></span>       | <span data-ttu-id="2284d-476">直接加入</span><span class="sxs-lookup"><span data-stu-id="2284d-476">Join directly</span></span>        |
|   | <span data-ttu-id="2284d-477">组织和联盟组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="2284d-477">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="2284d-478">直接加入</span><span class="sxs-lookup"><span data-stu-id="2284d-478">Join directly</span></span>         |
|<span data-ttu-id="2284d-479">False</span><span class="sxs-lookup"><span data-stu-id="2284d-479">False</span></span>    | <span data-ttu-id="2284d-480">所有人</span><span class="sxs-lookup"><span data-stu-id="2284d-480">Everyone</span></span>        | <span data-ttu-id="2284d-481">直接加入</span><span class="sxs-lookup"><span data-stu-id="2284d-481">Join directly</span></span>        |
|   | <span data-ttu-id="2284d-482">您的组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="2284d-482">Everyone in your organization</span></span>     |<span data-ttu-id="2284d-483">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="2284d-483">Wait in lobby</span></span>         |
|   | <span data-ttu-id="2284d-484">组织和联盟组织中的每个人</span><span class="sxs-lookup"><span data-stu-id="2284d-484">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="2284d-485">在大厅中等待</span><span class="sxs-lookup"><span data-stu-id="2284d-485">Wait in lobby</span></span>         |


### <a name="enable-live-captions"></a><span data-ttu-id="2284d-486">启用实时字幕</span><span class="sxs-lookup"><span data-stu-id="2284d-486">Enable live captions</span></span>

<span data-ttu-id="2284d-487">这是每用户策略，在会议期间应用。</span><span class="sxs-lookup"><span data-stu-id="2284d-487">This is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="2284d-488">此设置控制用户是否可以使用 "**打开实时标题**" 选项来打开和关闭用户出席的会议中的实时字幕。</span><span class="sxs-lookup"><span data-stu-id="2284d-488">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![显示 "打开实时字幕" 选项的屏幕截图](media/meeting-policies-live-captions.png)

|<span data-ttu-id="2284d-490">设置值</span><span class="sxs-lookup"><span data-stu-id="2284d-490">Setting value</span></span> |<span data-ttu-id="2284d-491">行为</span><span class="sxs-lookup"><span data-stu-id="2284d-491">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="2284d-492">**已禁用，但用户可以替代**</span><span class="sxs-lookup"><span data-stu-id="2284d-492">**Disabled but the user can override**</span></span>     | <span data-ttu-id="2284d-493">会议期间不会为用户自动打开实时字幕。</span><span class="sxs-lookup"><span data-stu-id="2284d-493">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="2284d-494">用户可以在 "溢出（**...**）" 菜单中看到 "**打开实时标题**" 选项以将其打开。</span><span class="sxs-lookup"><span data-stu-id="2284d-494">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="2284d-495">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="2284d-495">This is the default setting.</span></span> |
|<span data-ttu-id="2284d-496">**已禁用**</span><span class="sxs-lookup"><span data-stu-id="2284d-496">**Disabled**</span></span>     | <span data-ttu-id="2284d-497">会议期间，用户已禁用实时字幕。</span><span class="sxs-lookup"><span data-stu-id="2284d-497">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="2284d-498">用户不能选择将其打开。</span><span class="sxs-lookup"><span data-stu-id="2284d-498">The user doesn't have the option to turn them on.</span></span>          |

<span data-ttu-id="2284d-499"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="2284d-499"><a name="bkcontentsharing"> </a></span></span>

### <a name="allow-chat-in-meetings"></a><span data-ttu-id="2284d-500">允许在会议中聊天</span><span class="sxs-lookup"><span data-stu-id="2284d-500">Allow chat in meetings</span></span>

<span data-ttu-id="2284d-501">这是每个组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="2284d-501">This is a per-organizer policy.</span></span> <span data-ttu-id="2284d-502">此设置控制是否允许在用户的会议中使用会议聊天。</span><span class="sxs-lookup"><span data-stu-id="2284d-502">This setting controls whether meeting chat is allowed in the user's meeting.</span></span>

<span data-ttu-id="2284d-503"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="2284d-503"><a name="bkparticipantsandguests"> </a></span></span>

## <a name="meeting-policy-settings---designated-presenter-role-mode"></a><span data-ttu-id="2284d-504">会议策略设置-指定的演示者角色模式</span><span class="sxs-lookup"><span data-stu-id="2284d-504">Meeting policy settings - Designated presenter role mode</span></span>

<span data-ttu-id="2284d-505">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="2284d-505">This is a per-user policy.</span></span> <span data-ttu-id="2284d-506">此设置允许你更改团队客户端的 "**会议选项**" 中的 "**可以显示的人员**" 的默认值。</span><span class="sxs-lookup"><span data-stu-id="2284d-506">This setting lets you change the default value of the **Who can present?** setting in **Meeting options** in the Teams client.</span></span> <span data-ttu-id="2284d-507">此策略设置影响所有会议，包括 "立即开会" 会议。</span><span class="sxs-lookup"><span data-stu-id="2284d-507">This policy setting affects all meetings, including Meet Now meetings.</span></span>

<span data-ttu-id="2284d-508">"**可以显示的人员**" 设置让会议组织者可以选择哪些人可以在会议中成为演示者。</span><span class="sxs-lookup"><span data-stu-id="2284d-508">The **Who can present?** setting lets meeting organizers choose who can be presenters in a meeting.</span></span> <span data-ttu-id="2284d-509">若要了解详细信息，请参阅更改[团队会议中](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)团队会议和角色的[参与者设置](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e)。</span><span class="sxs-lookup"><span data-stu-id="2284d-509">To learn more, see [Change participant settings for a Teams meeting](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) and [Roles in a Teams meeting](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).</span></span>

<span data-ttu-id="2284d-510">目前，您只能使用 PowerShell 配置此策略设置。</span><span class="sxs-lookup"><span data-stu-id="2284d-510">Currently, you can only use PowerShell to configure this policy setting.</span></span> <span data-ttu-id="2284d-511">你可以使用[CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有团队会议策略。</span><span class="sxs-lookup"><span data-stu-id="2284d-511">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="2284d-512">或者，使用 CsTeamsMeetingPolicy cmdlet 创建新[的](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy)团队会议策略，并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="2284d-512">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="2284d-513">若要指定**可显示的人员**的默认值？在团队中设置，请将**DesignatedPresenterRoleMode**参数设置为下列之一：</span><span class="sxs-lookup"><span data-stu-id="2284d-513">To specify the default value of the **Who can present?** setting in Teams, set the **DesignatedPresenterRoleMode** parameter to one of the following:</span></span>

- <span data-ttu-id="2284d-514">**EveryoneUserOverride**：所有会议参与者都可以是演示者。</span><span class="sxs-lookup"><span data-stu-id="2284d-514">**EveryoneUserOverride**:  All meeting participants can be presenters.</span></span> <span data-ttu-id="2284d-515">此值为默认值。</span><span class="sxs-lookup"><span data-stu-id="2284d-515">This is the default value.</span></span> <span data-ttu-id="2284d-516">此参数对应于团队中的 "**所有人**" 设置。</span><span class="sxs-lookup"><span data-stu-id="2284d-516">This parameter corresponds to the **Everyone** setting in Teams.</span></span>
- <span data-ttu-id="2284d-517">**EveryoneInCompanyUserOverride**：组织中的经过身份验证的用户（包括来宾用户）可以是演示者。</span><span class="sxs-lookup"><span data-stu-id="2284d-517">**EveryoneInCompanyUserOverride**: Authenticated users in the organization, including guest users, can be presenters.</span></span> <span data-ttu-id="2284d-518">此参数对应于团队中的 "**我的组织**" 设置中的人员。</span><span class="sxs-lookup"><span data-stu-id="2284d-518">This parameter corresponds to the **People in my organization** setting in Teams.</span></span>
- <span data-ttu-id="2284d-519">**EveryoneInSameAndFederatedCompanyUserOverride**：组织中的经过身份验证的用户（包括来自联盟组织的来宾用户和用户）可以是演示者。</span><span class="sxs-lookup"><span data-stu-id="2284d-519">**EveryoneInSameAndFederatedCompanyUserOverride**:  Authenticated users in the organization, including guest users and users from federated organizations, can be presenters.</span></span> <span data-ttu-id="2284d-520">此参数对应于 "**我的组织中的人员和团队中的受信任组织**" 设置。</span><span class="sxs-lookup"><span data-stu-id="2284d-520">This parameter corresponds to the **People in my organization and trusted organizations** setting in Teams.</span></span>
- <span data-ttu-id="2284d-521">**OrganizerOnlyUserOverride**：只有会议组织者可以是演示者，并且所有会议参与者都指定为 "与会者"。</span><span class="sxs-lookup"><span data-stu-id="2284d-521">**OrganizerOnlyUserOverride**: Only the meeting organizer can be a presenter and all meeting participants are designated as attendees.</span></span> <span data-ttu-id="2284d-522">此参数对应于 "团队" 中的 "**仅我**" 设置。</span><span class="sxs-lookup"><span data-stu-id="2284d-522">This parameter corresponds to the **Only me** setting in Teams.</span></span>

<span data-ttu-id="2284d-523">请记住，在设置默认值后，会议组织者仍可以在团队中更改此设置，并选择哪些人可以在他们计划的会议中显示。</span><span class="sxs-lookup"><span data-stu-id="2284d-523">Keep in mind that after you set the default value, meeting organizers can still change this setting in Teams and choose who can present in the meetings that they schedule.</span></span>

## <a name="meeting-policy-settings---meeting-attendance-report"></a><span data-ttu-id="2284d-524">会议策略设置-会议出席情况报告</span><span class="sxs-lookup"><span data-stu-id="2284d-524">Meeting policy settings - Meeting attendance report</span></span>

<span data-ttu-id="2284d-525">这是每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="2284d-525">This is a per-user policy.</span></span> <span data-ttu-id="2284d-526">此设置控制会议组织者是否可以下载[会议出席报告](teams-analytics-and-reports/meeting-attendance-report.md)。</span><span class="sxs-lookup"><span data-stu-id="2284d-526">This setting controls whether meeting organizers can download the [meeting attendance report](teams-analytics-and-reports/meeting-attendance-report.md).</span></span>

<span data-ttu-id="2284d-527">目前，您只能使用 PowerShell 配置此策略设置。</span><span class="sxs-lookup"><span data-stu-id="2284d-527">Currently, you can only use PowerShell to configure this policy setting.</span></span> <span data-ttu-id="2284d-528">你可以使用[CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有团队会议策略。</span><span class="sxs-lookup"><span data-stu-id="2284d-528">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="2284d-529">或者，使用 CsTeamsMeetingPolicy cmdlet 创建新[的](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy)团队会议策略，并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="2284d-529">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="2284d-530">若要使会议组织者能够下载会议出席报告，请将**AllowEngagementReport**参数设置为 "**已启用**"。</span><span class="sxs-lookup"><span data-stu-id="2284d-530">To enable a meeting organizer to download the meeting attendance report, set the **AllowEngagementReport** parameter  to **Enabled**.</span></span> <span data-ttu-id="2284d-531">启用后，用于下载报告的选项将显示在 "**参与者**" 窗格中。</span><span class="sxs-lookup"><span data-stu-id="2284d-531">When enabled, the option to download the report is displayed in the **Participants** pane.</span></span>

<span data-ttu-id="2284d-532">若要阻止会议组织者下载报表，请将该参数设置为 "**已禁用**"。</span><span class="sxs-lookup"><span data-stu-id="2284d-532">To prevent a meeting organizer from downloading the report, set the parameter to **Disabled**.</span></span> <span data-ttu-id="2284d-533">默认情况下，此设置处于禁用状态，无法使用下载报表的选项。</span><span class="sxs-lookup"><span data-stu-id="2284d-533">By default, this setting is disabled and the option to download the report isn't available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2284d-534">相关主题</span><span class="sxs-lookup"><span data-stu-id="2284d-534">Related topics</span></span>

- [<span data-ttu-id="2284d-535">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="2284d-535">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="2284d-536">向团队中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="2284d-536">Assign policies to your users in Teams</span></span>](assign-policies.md)
