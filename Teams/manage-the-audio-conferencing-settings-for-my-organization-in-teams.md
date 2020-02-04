---
title: 在 Microsoft Teams 中管理贵组织的音频会议设置
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '了解为用户分配电话拨入式会议许可证和会议 ID 的 Microsoft Teams 步骤以及许多其他电话拨入式会议设置。 '
ms.openlocfilehash: bd44e80b233f1ffdf572a9eab6e307f30db6867f
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41708648"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="d4690-103">在 Microsoft Teams 中管理贵组织的音频会议设置</span><span class="sxs-lookup"><span data-stu-id="d4690-103">Manage the Audio Conferencing settings for your organization in Microsoft Teams</span></span>

<span data-ttu-id="d4690-104">你可以更轻松地在一个位置查看 Microsoft Teams 的所有音频会议设置。</span><span class="sxs-lookup"><span data-stu-id="d4690-104">It might be easier for you to see all of the audio conferencing settings for Microsoft Teams in one place.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="d4690-105">分配音频会议许可证</span><span class="sxs-lookup"><span data-stu-id="d4690-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="d4690-106">不能使用 Teams 分配许可证。</span><span class="sxs-lookup"><span data-stu-id="d4690-106">You can't assign licenses using Teams.</span></span> <span data-ttu-id="d4690-107">您必须使用 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="d4690-107">You must use the Microsoft 365 admin center.</span></span> <span data-ttu-id="d4690-108">请参阅[分配 Skype for Business 和 Microsoft Teams 许可证](assign-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="d4690-108">See [Assign Skype for Business and Microsoft Teams licenses](assign-teams-licenses.md).</span></span> 
  
 <span data-ttu-id="d4690-109">**为用户分配许可证**</span><span class="sxs-lookup"><span data-stu-id="d4690-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="d4690-110">使用你的工作或学校帐户登录 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="d4690-110">Sign in to Microsoft 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="d4690-111">在**Microsoft 365 管理中心**的左侧导航中，转到 "**用户** > **活动用户**"，然后从可用的用户列表中选择一个或一组用户。</span><span class="sxs-lookup"><span data-stu-id="d4690-111">In the left navigation of the **Microsoft 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d4690-112">[!注释] 如果要同时向多达 20 个用户分配许可证，则可以使用" **选择视图**"下拉列表，然后选择其中一个选项或创建你自己的视图。</span><span class="sxs-lookup"><span data-stu-id="d4690-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="d4690-113">然后单击“**编辑**”，再单击“**下一步**”两次，然后选择许可证并单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="d4690-113">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span>  
  
3. <span data-ttu-id="d4690-114">在“操作”窗格中的“**产品许可证**”下，单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="d4690-114">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="d4690-115">在“**产品许可证**”页面上，开启“**音频会议**”，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="d4690-115">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="d4690-116">有关许可的详细信息，请参阅[Microsoft 团队加载项许可](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="d4690-116">For more on licensing, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="d4690-117">在分配许可证后，Microsoft 最初可能不会作为音频会议提供商显示在下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="d4690-117">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider.</span></span> <span data-ttu-id="d4690-118">如果出现这种情况，请注销管理中心或按 CTRL + F5 刷新浏览器窗口。</span><span class="sxs-lookup"><span data-stu-id="d4690-118">If this happens, either log out of the admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="d4690-119">启用或禁用向音频会议用户发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="d4690-119">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="d4690-120">![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标</span><span class="sxs-lookup"><span data-stu-id="d4690-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="d4690-121">在左侧导航中，转到“**会议**” > “**会议网桥**”。</span><span class="sxs-lookup"><span data-stu-id="d4690-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="d4690-122">在“**会议网桥**”页面顶部，单击“**网桥设置**”。</span><span class="sxs-lookup"><span data-stu-id="d4690-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="d4690-123">在“**网桥设置**”窗格中，启用或禁用“**当用户的拨入设置更改时自动向用户发送电子邮件**”。</span><span class="sxs-lookup"><span data-stu-id="d4690-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="d4690-124">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="d4690-124">Click **Save**.</span></span>

    
<span data-ttu-id="d4690-125">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="d4690-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="d4690-126">有关详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。</span><span class="sxs-lookup"><span data-stu-id="d4690-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="d4690-127">重置会议 ID</span><span class="sxs-lookup"><span data-stu-id="d4690-127">Reset the meeting conference ID</span></span>

<span data-ttu-id="d4690-128">![](media/teams-logo-30x30.png) **使用 Microsoft 团队管理中心**显示团队徽标的图标</span><span class="sxs-lookup"><span data-stu-id="d4690-128">![An icon showing the Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="d4690-129">在左侧导航中，单击 "**用户**"，然后从可用用户列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="d4690-129">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="d4690-130">在 "**音频会议**" 下，单击 "**重置会议 ID**"。</span><span class="sxs-lookup"><span data-stu-id="d4690-130">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

3. <span data-ttu-id="d4690-131">在 "**重置会议 ID"** 窗口中，单击 "**重置**"。</span><span class="sxs-lookup"><span data-stu-id="d4690-131">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="d4690-132">如果启用了将电子邮件发送给用户，将自动创建会议 ID 并使用新的会议 ID 向用户发送邮件。</span><span class="sxs-lookup"><span data-stu-id="d4690-132">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="d4690-133">默认情况下启用它。</span><span class="sxs-lookup"><span data-stu-id="d4690-133">It's enabled by default.</span></span>

<span data-ttu-id="d4690-134">请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="d4690-134">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="d4690-135">重置会议组织者的 PIN</span><span class="sxs-lookup"><span data-stu-id="d4690-135">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="d4690-136">用户安排的每次会议将分配到一个唯一的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="d4690-136">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="d4690-137">尽管将自动创建会议 ID 并将其分配给用户，但有时用户不希望使用此 ID，并且您想要将其设置为特定的号码，或者您的用户忘记或丢失了其会议 ID。</span><span class="sxs-lookup"><span data-stu-id="d4690-137">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> 

<span data-ttu-id="d4690-138">![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标</span><span class="sxs-lookup"><span data-stu-id="d4690-138">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="d4690-139">在左侧导航中，单击 "**用户**"，然后从可用用户列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="d4690-139">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="d4690-140">在 "**音频会议**" 下，单击 "**重置 PIN**"，然后单击 "**重置**"。</span><span class="sxs-lookup"><span data-stu-id="d4690-140">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
<span data-ttu-id="d4690-141">当启用音频会议或 PIN 重置时，用户将收到其 PIN 的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d4690-141">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="d4690-142">但是，如果您已禁用自动发送电子邮件，则不会发送 PIN 重置电子邮件，您必须手动将 PIN 发送给用户。</span><span class="sxs-lookup"><span data-stu-id="d4690-142">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="d4690-143">PIN 将仅在重置后显示一次。</span><span class="sxs-lookup"><span data-stu-id="d4690-143">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="d4690-144">在重置后，该 PIN 将不再显示在用户的属性上，而是将不再显示。此时将显示 \* \* \* \* \* \*。</span><span class="sxs-lookup"><span data-stu-id="d4690-144">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="d4690-145">请参阅[重置音频会议 PIN 码](reset-the-audio-conferencing-pin-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="d4690-145">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="d4690-146">向用户发送包含音频会议信息的电子邮件</span><span class="sxs-lookup"><span data-stu-id="d4690-146">Send an email with Audio Conferencing information to a user</span></span>

<span data-ttu-id="d4690-147">![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标</span><span class="sxs-lookup"><span data-stu-id="d4690-147">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="d4690-148">在左侧导航中，单击 "**用户**"，然后从可用用户列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="d4690-148">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="d4690-149">在 "**音频会议**" 下，单击 "**通过电子邮件发送会议信息**"。</span><span class="sxs-lookup"><span data-stu-id="d4690-149">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="d4690-150">执行此操作时，音频会议 PIN 不会发送给用户。</span><span class="sxs-lookup"><span data-stu-id="d4690-150">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 

<span data-ttu-id="d4690-151">请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="d4690-151">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
  
## <a name="set-the-phone-numbers-included-on-invites"></a><span data-ttu-id="d4690-152">设置包含在邀请中的电话号码</span><span class="sxs-lookup"><span data-stu-id="d4690-152">Set the phone numbers included on invites</span></span>

<span data-ttu-id="d4690-153">![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标</span><span class="sxs-lookup"><span data-stu-id="d4690-153">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="d4690-154">在左侧导航中，单击 "**用户**"，然后从可用用户列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="d4690-154">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="d4690-155">在**音频会议**旁边，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="d4690-155">Next to **Audio Conferencing**, click **Edit**.</span></span>
 
3. <span data-ttu-id="d4690-156">在 "**音频会议**" 窗格中，您可以设置**收费号码**，如果允许，还可以设置免费**电话号码**。</span><span class="sxs-lookup"><span data-stu-id="d4690-156">In the **Audio Conferencing** pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

4. <span data-ttu-id="d4690-157">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="d4690-157">Click **Save**.</span></span>
    
<span data-ttu-id="d4690-158">请参阅[设置邀请附带的电话号码](set-the-phone-numbers-included-on-invites-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="d4690-158">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a><span data-ttu-id="d4690-159">选择 "音频会议桥" 设置</span><span class="sxs-lookup"><span data-stu-id="d4690-159">Choose audio conferencing bridge settings</span></span>

<span data-ttu-id="d4690-160">**设置呼叫者加入会议时的会议体验**</span><span class="sxs-lookup"><span data-stu-id="d4690-160">**Set the meeting experience when callers join a meeting**</span></span>

<span data-ttu-id="d4690-161">![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标</span><span class="sxs-lookup"><span data-stu-id="d4690-161">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="d4690-162">在左侧导航中，转到“**会议**” > “**会议网桥**”。</span><span class="sxs-lookup"><span data-stu-id="d4690-162">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="d4690-163">在 "**会议桥**" 页面顶部，单击 "**桥接设置**"。</span><span class="sxs-lookup"><span data-stu-id="d4690-163">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="d4690-164">在“**网桥设置**”窗格中，启用或禁用“**会议进入和退出通知**”。</span><span class="sxs-lookup"><span data-stu-id="d4690-164">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="d4690-165">默认情况下，此功能处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="d4690-165">This is enabled by default.</span></span> <span data-ttu-id="d4690-166">如果禁用此选项，当有人进入或离开会议时，已加入会议的用户不会收到通知。</span><span class="sxs-lookup"><span data-stu-id="d4690-166">If you disable this option, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="d4690-167">在 "**输入/退出通知类型**" 下，选择 "**声音**" 或 "姓名"**或 "电话号码**"。</span><span class="sxs-lookup"><span data-stu-id="d4690-167">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="d4690-168">如果选择 "**姓名" 或 "电话号码**"，还可以选择在**加入会议之前启用或禁用 Ask 呼叫者录制其姓名**。</span><span class="sxs-lookup"><span data-stu-id="d4690-168">If you choose **Names or phone numbers**, you can also choose to enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 

5. <span data-ttu-id="d4690-169">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="d4690-169">Click **Save**.</span></span>

    
<span data-ttu-id="d4690-170">请参阅[更改音频会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="d4690-170">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="d4690-171">**设置会议的 PIN 长度**</span><span class="sxs-lookup"><span data-stu-id="d4690-171">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="d4690-172">在左侧导航中，转到“**会议**” > “**会议网桥**”。</span><span class="sxs-lookup"><span data-stu-id="d4690-172">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="d4690-173">在 "**会议桥**" 页面顶部，单击 "**桥接设置**"。</span><span class="sxs-lookup"><span data-stu-id="d4690-173">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="d4690-174">在 "**桥设置**" 窗格中，在 " **pin 长度**" 列表中输入 pin 所需的位数，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="d4690-174">In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="d4690-175">PIN 必须介于4到12位之间。</span><span class="sxs-lookup"><span data-stu-id="d4690-175">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="d4690-176">默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="d4690-176">The default is 5.</span></span>

    
<span data-ttu-id="d4690-177">请参阅[更改音频会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="d4690-177">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="d4690-178">**启用或禁用向音频用户发送电子邮件**</span><span class="sxs-lookup"><span data-stu-id="d4690-178">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="d4690-179">在左侧导航中，转到“**会议**” > “**会议网桥**”。</span><span class="sxs-lookup"><span data-stu-id="d4690-179">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="d4690-180">在 "**会议桥**" 页面顶部，单击 "**桥接设置**"。</span><span class="sxs-lookup"><span data-stu-id="d4690-180">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="d4690-181">在 "**桥设置**" 窗格中，**如果用户的音频会议设置发生更改**，则启用或禁用 "自动向用户发送电子邮件"。</span><span class="sxs-lookup"><span data-stu-id="d4690-181">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="d4690-182">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="d4690-182">Click **Save**.</span></span> 
 
    <span data-ttu-id="d4690-183">您还可以通过音频会议设置向用户发送电子邮件，方法是转到用户的音频会议属性，然后单击 **"在电子邮件中发送会议信息**"。</span><span class="sxs-lookup"><span data-stu-id="d4690-183">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info in email**.</span></span>
    
    <span data-ttu-id="d4690-184">如果执行此操作，则将发送仅包括会议 ID 和会议电话号码的电子邮件，但不包括 PIN。</span><span class="sxs-lookup"><span data-stu-id="d4690-184">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="d4690-185">请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="d4690-185">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="d4690-186">在音频会议桥处查看和设置主要（默认）和辅助（备用）语言</span><span class="sxs-lookup"><span data-stu-id="d4690-186">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>

<span data-ttu-id="d4690-187">![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标</span><span class="sxs-lookup"><span data-stu-id="d4690-187">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="d4690-188">在左侧导航中，转到“**会议**” > “**会议网桥**”。</span><span class="sxs-lookup"><span data-stu-id="d4690-188">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="d4690-189">从列表中选择电话号码，然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="d4690-189">Select a phone number from the list and click **Edit**.</span></span>

3. <span data-ttu-id="d4690-190">选择 "**默认语言**" 和 "**备用语言（可选）**" 下所需的语言。</span><span class="sxs-lookup"><span data-stu-id="d4690-190">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>

4. <span data-ttu-id="d4690-191">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="d4690-191">Click **Save**.</span></span>


<span data-ttu-id="d4690-192">请参阅[设置音频会议自动助理语言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="d4690-192">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="d4690-193">请参阅音频会议拨入号码</span><span class="sxs-lookup"><span data-stu-id="d4690-193">See audio conferencing dial-in numbers</span></span>

<span data-ttu-id="d4690-194">![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标</span><span class="sxs-lookup"><span data-stu-id="d4690-194">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="d4690-195">在左侧导航中，转到“**会议**” > “**会议网桥**”。</span><span class="sxs-lookup"><span data-stu-id="d4690-195">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="d4690-196">从列表中选择电话号码，然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="d4690-196">Select a phone number from the list and click **Edit**.</span></span> <span data-ttu-id="d4690-197">可在此处执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d4690-197">Here you can:</span></span>
    
   - <span data-ttu-id="d4690-198">查看由 Office 365 设置用于音频会议的电话号码。</span><span class="sxs-lookup"><span data-stu-id="d4690-198">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
   - <span data-ttu-id="d4690-199">查看音频会议自动助理将使用的位置和主要语言。</span><span class="sxs-lookup"><span data-stu-id="d4690-199">View the location, and the primary language, that will be used by the Audio Conferencing auto attendant.</span></span>

  
<span data-ttu-id="d4690-200">请参阅[音频会议号码列表](see-a-list-of-audio-conferencing-numbers-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="d4690-200">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>
  

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="d4690-201">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="d4690-201">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="d4690-p111">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="d4690-p111">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d4690-205">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4690-205">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="d4690-206">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="d4690-206">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="d4690-207">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="d4690-207">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
    
## <a name="related-topics"></a><span data-ttu-id="d4690-208">相关主题</span><span class="sxs-lookup"><span data-stu-id="d4690-208">Related topics</span></span>

[<span data-ttu-id="d4690-209">管理用户的音频会议设置</span><span class="sxs-lookup"><span data-stu-id="d4690-209">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


