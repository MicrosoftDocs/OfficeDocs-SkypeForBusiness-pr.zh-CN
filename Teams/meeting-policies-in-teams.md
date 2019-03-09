---
title: 管理会议策略
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.date: 03/01/2019
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
ms.openlocfilehash: f8f7e4bbf18fa96ebc8de3fd219945a06c05c0b3
ms.sourcegitcommit: f3b41e7abafc84571bd9e8267d41decc0fe78e4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2019
ms.locfileid: "30494082"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="29b78-103">管理团队中的会议策略</span><span class="sxs-lookup"><span data-stu-id="29b78-103">Manage meeting policies in Teams</span></span>

::: zone target="docs"
<span data-ttu-id="29b78-104">会议策略用于控制对会议的组织中的用户安排的会议的参与者可用的功能。</span><span class="sxs-lookup"><span data-stu-id="29b78-104">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="29b78-105">在创建策略，并进行更改后，然后，您可以分配给策略使用。</span><span class="sxs-lookup"><span data-stu-id="29b78-105">After you create a policy and make your changes, you can then assign uses to the policy.</span></span> 

<span data-ttu-id="29b78-106">默认情况下，创建名为全局 （组织范围内默认值） 的策略。</span><span class="sxs-lookup"><span data-stu-id="29b78-106">By default, a policy named Global (org-wide default) is created.</span></span> <span data-ttu-id="29b78-107">默认情况下，您的组织中的所有用户将都分配此会议策略。</span><span class="sxs-lookup"><span data-stu-id="29b78-107">All users in your organization will be assigned this meeting policy by default.</span></span> <span data-ttu-id="29b78-108">可以更改此策略，或创建一个或多个自定义策略并向其分配用户。</span><span class="sxs-lookup"><span data-stu-id="29b78-108">You can either make changes to this policy or create one or more custom policies and assign users to them.</span></span> <span data-ttu-id="29b78-109">创建自定义策略时，可以允许或阻止某些功能对用户可用，然后将其分配给一个或多个用户拥有应用于它们的设置。</span><span class="sxs-lookup"><span data-stu-id="29b78-109">When you create a custom policy, you can allow or prevent certain features from being available to your users and then assign it to one or more users who will have the settings applied to them.</span></span> 

## <a name="change-or-create-a-meeting-policy"></a><span data-ttu-id="29b78-110">更改或创建的会议策略</span><span class="sxs-lookup"><span data-stu-id="29b78-110">Change or create a meeting policy</span></span>

<span data-ttu-id="29b78-111">要更改或创建的会议策略，请转到**Microsoft 团队管理中心** > **会议** > **会议策略**。</span><span class="sxs-lookup"><span data-stu-id="29b78-111">To change or create a meeting policy, go to **Microsoft Teams admin center** > **Meetings** > **Meeting policies**.</span></span> <span data-ttu-id="29b78-112">从列表中，选择一个策略，或选择**新策略**。</span><span class="sxs-lookup"><span data-stu-id="29b78-112">Select a policy from the list, or select **New policy**.</span></span> <span data-ttu-id="29b78-113">选择您的设置，然后选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="29b78-113">Choose your settings, and then select **Save**.</span></span>

<span data-ttu-id="29b78-114">例如，假设您有大量的用户，并且想要限制其会议将需要的带宽量。</span><span class="sxs-lookup"><span data-stu-id="29b78-114">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="29b78-115">您可以创建名为"带宽有限"的新自定义策略，并禁用以下设置：</span><span class="sxs-lookup"><span data-stu-id="29b78-115">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="29b78-116">在**音频 & 视频**: 下</span><span class="sxs-lookup"><span data-stu-id="29b78-116">Under **Audio & video**:</span></span>
- <span data-ttu-id="29b78-117">关闭云录制</span><span class="sxs-lookup"><span data-stu-id="29b78-117">Turn off cloud recording</span></span>
- <span data-ttu-id="29b78-118">关闭允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="29b78-118">Turn off Allow IP video</span></span>

<span data-ttu-id="29b78-119">在**内容共享**: 下</span><span class="sxs-lookup"><span data-stu-id="29b78-119">Under **Content sharing**:</span></span>
- <span data-ttu-id="29b78-120">禁用屏幕共享模式</span><span class="sxs-lookup"><span data-stu-id="29b78-120">Disable screen sharing mode</span></span>
- <span data-ttu-id="29b78-121">关闭白板</span><span class="sxs-lookup"><span data-stu-id="29b78-121">Turn off whiteboard</span></span>
- <span data-ttu-id="29b78-122">关闭共享便笺</span><span class="sxs-lookup"><span data-stu-id="29b78-122">Turn off shared notes</span></span>

<span data-ttu-id="29b78-123">然后将策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="29b78-123">Then assign the policy to the users.</span></span>

> [!NOTE] 
> <span data-ttu-id="29b78-124">用户可以一次只能有一个会议策略分配。</span><span class="sxs-lookup"><span data-stu-id="29b78-124">A user can be assigned only one meeting policy at a time.</span></span> 

## <a name="assign-a-meeting-policy-to-a-user"></a><span data-ttu-id="29b78-125">为用户分配的会议策略</span><span class="sxs-lookup"><span data-stu-id="29b78-125">Assign a meeting policy to a user</span></span>

<span data-ttu-id="29b78-126">要分配策略，请转到**Microsoft 团队管理中心** > **用户**。</span><span class="sxs-lookup"><span data-stu-id="29b78-126">To assign a policy, go to **Microsoft Teams admin center** > **Users**.</span></span> 
 
<span data-ttu-id="29b78-127">如果您将策略应用于一个用户，选择用户的显示名称。</span><span class="sxs-lookup"><span data-stu-id="29b78-127">If you are applying the policy to one user, select the user's display name.</span></span> <span data-ttu-id="29b78-128">选择**分配策略**、 旁边的**编辑**。</span><span class="sxs-lookup"><span data-stu-id="29b78-128">Next to **Assigned policies**, select **Edit**.</span></span> <span data-ttu-id="29b78-129">然后，在**编辑用户策略**窗格中的**会议策略**，下，从下拉列表中，选择会议策略，并选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="29b78-129">Then, in the **Edit user policies** pane, under **Meeting policy**, select the meeting policy from the drop-down list, and select **Save**.</span></span> <span data-ttu-id="29b78-130">您还可以编辑的用户列表中的设置。</span><span class="sxs-lookup"><span data-stu-id="29b78-130">You can also edit settings from the list of users.</span></span> <span data-ttu-id="29b78-131">若要执行此操作，请通过单击左侧的用户的显示名称选择用户。</span><span class="sxs-lookup"><span data-stu-id="29b78-131">To do this, select the user by clicking to the left of the user's display name.</span></span> <span data-ttu-id="29b78-132">选择**编辑设置**。</span><span class="sxs-lookup"><span data-stu-id="29b78-132">Select **Edit settings**.</span></span> <span data-ttu-id="29b78-133">然后，**编辑设置**窗格中的**会议策略**，下，从下拉列表中选择策略，然后选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="29b78-133">Then, on the **Edit settings** pane, under **Meeting policy**, select the policy from the drop-down list and then select **Save**.</span></span> 
 
<span data-ttu-id="29b78-134">如果您要向多个用户应用策略，通过单击左侧的用户名称，选择每个用户，然后单击**编辑设置**。</span><span class="sxs-lookup"><span data-stu-id="29b78-134">If you are applying a policy to more than one user, select each of the users by clicking to the left of the user name, and then click **Edit settings**.</span></span> <span data-ttu-id="29b78-135">在**编辑设置**窗格中，**会议策略**，下从下拉列表中选择策略，然后选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="29b78-135">On the **Edit Settings** pane, under **Meeting policy**, select the policy from the drop-down list and then select **Save**.</span></span>
 
<span data-ttu-id="29b78-136">也可以执行此操作，转到**Microsoft 团队管理中心** > **会议** >  **会议策略**。</span><span class="sxs-lookup"><span data-stu-id="29b78-136">You can also do this by going to **Microsoft Teams admin center** > **Meetings** >  **Meeting policies**.</span></span> <span data-ttu-id="29b78-137">选择策略，然后选择**管理用户**。</span><span class="sxs-lookup"><span data-stu-id="29b78-137">Select the policy and then select **Manage users**.</span></span> <span data-ttu-id="29b78-138">在**管理用户**窗格中，请按显示区或用户名称中搜索用户。</span><span class="sxs-lookup"><span data-stu-id="29b78-138">In the **Manage users** pane, search for the user by display or user name.</span></span> <span data-ttu-id="29b78-139">选择的名称并选择**添加**。</span><span class="sxs-lookup"><span data-stu-id="29b78-139">Select the name and select **Add**.</span></span> <span data-ttu-id="29b78-140">添加完用户后，选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="29b78-140">When you are finished adding users, select **Save**.</span></span>

> [!NOTE] 
> <span data-ttu-id="29b78-141">不能删除策略，如果用户已分配给它。</span><span class="sxs-lookup"><span data-stu-id="29b78-141">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="29b78-142">您必须首先将不同的策略分配给所有受影响的用户，然后可以删除原始的策略。</span><span class="sxs-lookup"><span data-stu-id="29b78-142">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>
 
 
## <a name="user-policy-settings"></a><span data-ttu-id="29b78-143">用户策略设置</span><span class="sxs-lookup"><span data-stu-id="29b78-143">User policy settings</span></span>

<span data-ttu-id="29b78-144">当您选择**会议策略**页上的现有策略，或选择要添加新的策略的**新策略**时，您可以配置以下设置。</span><span class="sxs-lookup"><span data-stu-id="29b78-144">When you select an existing policy on the **Meeting policies** page or select **New policy** to add a new policy, you can configure the following settings.</span></span>

### <a name="new-meeting-policy-name-and-description"></a><span data-ttu-id="29b78-145">新会议策略名称和说明</span><span class="sxs-lookup"><span data-stu-id="29b78-145">New meeting policy name and description</span></span>
   - <span data-ttu-id="29b78-146">**名称**这是策略的将出现在**会议策略**页的名称。</span><span class="sxs-lookup"><span data-stu-id="29b78-146">**Name** This is the name of the policy that will appear on the **Meeting policies** page.</span></span> <span data-ttu-id="29b78-147">它不能包含特殊字符或能超过 64 个字符。</span><span class="sxs-lookup"><span data-stu-id="29b78-147">It can't contain special characters or be longer than 64 characters.</span></span> <span data-ttu-id="29b78-148">请注意，不能更改现有的策略的名称。</span><span class="sxs-lookup"><span data-stu-id="29b78-148">Note that you can't change an existing policy's name.</span></span>
   - <span data-ttu-id="29b78-149">**说明**您可以将放在您创建的策略的友好说明。</span><span class="sxs-lookup"><span data-stu-id="29b78-149">**Description** You can put in a friendly description for the policy you create.</span></span> <span data-ttu-id="29b78-150">这将非常有用，如果您想要将策略分配到一组用户。</span><span class="sxs-lookup"><span data-stu-id="29b78-150">This will be helpful if you want to assign a policy to a group of users.</span></span>
::: zone-end 

<span data-ttu-id="29b78-151"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="29b78-151"></span></span>
### <a name="general"></a><span data-ttu-id="29b78-152">常规</span><span class="sxs-lookup"><span data-stu-id="29b78-152">General</span></span>
   - <span data-ttu-id="29b78-153">**允许立即开会**打开： 将允许立即开会功能可加入会议的用户。</span><span class="sxs-lookup"><span data-stu-id="29b78-153">**Allow Meet Now** Turning this on will allow the Meet Now feature to be available to users that join meetings.</span></span>
   - <span data-ttu-id="29b78-154">**允许 Outlook 外接程序**打开将让他们安排会议时，Outlook 外接程序提供已分配给策略的用户。</span><span class="sxs-lookup"><span data-stu-id="29b78-154">**Allow the Outlook add-in** Turning this on will let users assigned to the policy have the Outlook add-in available when they schedule meetings.</span></span>
   - <span data-ttu-id="29b78-155">**允许通道会议日程安排**打开： 将允许通道会议安排。</span><span class="sxs-lookup"><span data-stu-id="29b78-155">**Allow Channel meeting scheduling** Turning this on will allow Channel Meeting scheduling.</span></span>
   - <span data-ttu-id="29b78-156">**允许安排专用会议**打开： 将允许用户加入会议安排专用会议。</span><span class="sxs-lookup"><span data-stu-id="29b78-156">**Allow scheduling private meetings** Turning this on will allow users that join a meeting to schedule private meetings.</span></span>

<span data-ttu-id="29b78-157"><a name="bkaudioandvideo"> </a></span><span class="sxs-lookup"><span data-stu-id="29b78-157"></span></span>

### <a name="audio--video"></a><span data-ttu-id="29b78-158">音频 & 视频</span><span class="sxs-lookup"><span data-stu-id="29b78-158">Audio & video</span></span>
   - <span data-ttu-id="29b78-159">**允许转录**如果您关闭此，会议的转录将对用户可用。</span><span class="sxs-lookup"><span data-stu-id="29b78-159">**Allow transcription** If you turn this on, transcription of the meeting will be available to users.</span></span>
   - <span data-ttu-id="29b78-160">**允许云录制**打开： 将允许在云中保存录制内容。</span><span class="sxs-lookup"><span data-stu-id="29b78-160">**Allow cloud recording** Turning this on will allow recordings to be saved in the cloud.</span></span>
   - <span data-ttu-id="29b78-161">**允许的 IP 视频**打开： 将允许 IP 视频会议期间。</span><span class="sxs-lookup"><span data-stu-id="29b78-161">**Allow IP video** Turning this on will allow IP videos during meetings.</span></span>
   - <span data-ttu-id="29b78-162">**媒体比特率 (Kb)** 您可以设置会议的比特率。</span><span class="sxs-lookup"><span data-stu-id="29b78-162">**Media bit rate (KBs)** You can set the bit rate for meetings.</span></span> <span data-ttu-id="29b78-163">默认为 50 MB。</span><span class="sxs-lookup"><span data-stu-id="29b78-163">The default is 50 MB.</span></span>

<span data-ttu-id="29b78-164"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="29b78-164"></span></span>

### <a name="content-sharing"></a><span data-ttu-id="29b78-165">内容共享</span><span class="sxs-lookup"><span data-stu-id="29b78-165">Content sharing</span></span>
   - <span data-ttu-id="29b78-166">**屏幕共享模式**您可以选择屏幕共享模式。</span><span class="sxs-lookup"><span data-stu-id="29b78-166">**Screen sharing mode** You can select the screen sharing mode.</span></span> <span data-ttu-id="29b78-167">这将在屏幕上将策略分配的用户可以使用会议期间使用的大小。</span><span class="sxs-lookup"><span data-stu-id="29b78-167">This will be the size of the screen that will be used during a meeting that a user assigned with the policy can use.</span></span>
   - <span data-ttu-id="29b78-168">**允许参与者授予或请求控制权**这样，所有参与者在会议中提供和请求的屏幕共享控制权。</span><span class="sxs-lookup"><span data-stu-id="29b78-168">**Allow a participant to give or request control** This allows all participants in a meeting to give and request control of screen sharing.</span></span>
   - <span data-ttu-id="29b78-169">**允许外部参与者授予或请求控制权**这样，外部 （某人不是您组织的一部分） 参与者授予和共享屏幕时请求的会议控制权。</span><span class="sxs-lookup"><span data-stu-id="29b78-169">**Allow an external participant to give or request control** This allows an external (someone not part of your organziation) participant to give and request control of a meeting when the screen is being shared.</span></span>
   - <span data-ttu-id="29b78-170">**允许 PowerPoint 共享**如果您启用此，请安排会议的用户可以在会议期间共享 PowerPoint 幻灯片背面图案。</span><span class="sxs-lookup"><span data-stu-id="29b78-170">**Allow PowerPoint sharing** If you turn this on, users that schedule meetings can share PowerPoint slide decks during a meeting.</span></span>
   - <span data-ttu-id="29b78-171">**允许白板**如果关闭此，在白板将可供会议参与者在会议期间。</span><span class="sxs-lookup"><span data-stu-id="29b78-171">**Allow whiteboard** If you turn this on, the whiteboard will be available to meeting participants during a meeting.</span></span>
   - <span data-ttu-id="29b78-172">**允许共享的便笺**如果您关闭此，将供会议参与者在会议期间共享的便笺。</span><span class="sxs-lookup"><span data-stu-id="29b78-172">**Allow shared notes** If you turn this on, shared notes will be available to meeting participants during a meeting.</span></span>

<span data-ttu-id="29b78-173"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="29b78-173"></span></span>

### <a name="participants--guests"></a><span data-ttu-id="29b78-174">参与者 & 来宾</span><span class="sxs-lookup"><span data-stu-id="29b78-174">Participants & guests</span></span>
   - <span data-ttu-id="29b78-175">**允许匿名用户开始会议**如果此设置处于关闭状态，只有已经过身份验证的团队应用程序与会议的人可以开始会议。</span><span class="sxs-lookup"><span data-stu-id="29b78-175">**Allow anonymous users to start meetings** If this setting is off, then only someone who has been authenticated to the meeting with a Teams app can start the meeting.</span></span> <span data-ttu-id="29b78-176">如果是任何人都可以开始会议。</span><span class="sxs-lookup"><span data-stu-id="29b78-176">If it's on, then anyone can start the meeting.</span></span>
   - <span data-ttu-id="29b78-177">**自动允许的用户**如果您关闭此操作，然后会议参与者处于会议厅直到有人开始会议。</span><span class="sxs-lookup"><span data-stu-id="29b78-177">**Automatically admit users** If you turn this off, then meeting participants will be left in the lobby until someone starts the meeting.</span></span> <span data-ttu-id="29b78-178">如果是会议参与者将允许加入会议自动。</span><span class="sxs-lookup"><span data-stu-id="29b78-178">If it's on, meeting participants will be allowed to join the meeting automatically.</span></span>

[<span data-ttu-id="29b78-179">完整的文章</span><span class="sxs-lookup"><span data-stu-id="29b78-179">Full article</span></span>](meeting-policies-in-teams.md)

### <a name="related-topics"></a><span data-ttu-id="29b78-180">相关主题</span><span class="sxs-lookup"><span data-stu-id="29b78-180">Related topics</span></span>
[<span data-ttu-id="29b78-181">团队中的邮件策略</span><span class="sxs-lookup"><span data-stu-id="29b78-181">Messaging policies in Teams</span></span>](messaging-policies-in-teams.md)