---
title: 更改音频会议网桥的设置
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: 更改音频会议桥设置，包括进入和退出通知、播放姓名或电话号码、声音，以及提示呼叫者录制其姓名。
ms.openlocfilehash: 48028ccb3f2a0664f9fa724ec91e1dfc0177326f
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780341"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="a8080-103">更改音频会议网桥的设置</span><span class="sxs-lookup"><span data-stu-id="a8080-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="a8080-p101">当您在 Office 365 中设置音频会议时，您将收到来自 "音频会议桥" 的用户的电话号码。一个会议桥可以包含一个或多个电话号码。当呼叫者拨入会议时，将使用这些电话号码。电话号码包含在 Skype for Business 或 Microsoft 团队会议邀请的底部。</span><span class="sxs-lookup"><span data-stu-id="a8080-p101">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers. These phone numbers are used when callers dial in to a meeting. The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="a8080-p102">会议桥应答呼叫，并使用会议自动助理提示呼叫者提供语音提示，然后根据您的设置，它可以播放通知，让呼叫者录制其姓名，并控制固定设置。当会议组织者未使用 Skype for Business 或 Microsoft 团队应用时，将为会议组织者提供允许他们启动会议的 Pin。</span><span class="sxs-lookup"><span data-stu-id="a8080-p102">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings. PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="a8080-p103">仅当 Skype for Business 或 Microsoft 团队应用用户尚未启动会议时，会议组织者才需要 PIN。如果每个人都在拨入会议，则会议组织者需要 PIN 才能启动会议。</span><span class="sxs-lookup"><span data-stu-id="a8080-p103">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting. If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) <span data-ttu-id="a8080-113">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="a8080-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="a8080-114">在左侧导航中，转到 "**会议** > **桥**"。</span><span class="sxs-lookup"><span data-stu-id="a8080-114">In the left navigation, go to **Meetings** > **Conference bridges**.</span></span> 

2. <span data-ttu-id="a8080-115">在 "**会议桥**" 页面顶部，单击 "**桥接设置**"。</span><span class="sxs-lookup"><span data-stu-id="a8080-115">At the top of the **Conference bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="a8080-116">在 "**桥设置**" 窗格中，选择：</span><span class="sxs-lookup"><span data-stu-id="a8080-116">In the **Bridge settings** pane, select:</span></span> 
   - <span data-ttu-id="a8080-117">**会议进入和退出通知**如果关闭此功能，当有人进入或离开会议时，已加入会议的用户不会收到通知。</span><span class="sxs-lookup"><span data-stu-id="a8080-117">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
     <span data-ttu-id="a8080-118">打开**会议进入和退出通知**时，可以选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="a8080-118">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
   - <span data-ttu-id="a8080-119">**姓名或电话号码**当用户拨入会议时，将在加入会议时播放其电话号码。</span><span class="sxs-lookup"><span data-stu-id="a8080-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="a8080-120">**声音**当用户拨入会议时，将在加入会议时播放音频音调。</span><span class="sxs-lookup"><span data-stu-id="a8080-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
   - <span data-ttu-id="a8080-121">**邀请呼叫者在加入会议之前录制其姓名**如果关闭此功能，则不会要求呼叫者在加入会议之前记录其名称。</span><span class="sxs-lookup"><span data-stu-id="a8080-121">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="a8080-122">若要设置会议的 PIN 长度，请在 " **pin 长度**" 列表中选择要用于 pin 的数字位数。</span><span class="sxs-lookup"><span data-stu-id="a8080-122">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="a8080-123">若要指定是否向用户发送电子邮件，请启用或禁用**如果用户的音频会议配置发生更改，则自动向用户发送电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="a8080-123">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="a8080-124">当用户在[Skype For Business Online 中的设置发生更改时](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change)，请参阅[自动向用户发送的电子邮件的语音会议设置](emails-sent-to-users-when-their-settings-change-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="a8080-124">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
 
6. <span data-ttu-id="a8080-125">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a8080-125">Click **Save**.</span></span> 


## <a name="an-icon-showing-the-skype-for-business-logo--using-the-skype-for-business-admin-center"></a>![显示 Skype for Business 徽标的图标](media/sfb-logo-30x30.png)  <span data-ttu-id="a8080-127">使用 Skype for Business 管理中心</span><span class="sxs-lookup"><span data-stu-id="a8080-127">Using the Skype for Business admin center</span></span>

 <span data-ttu-id="a8080-128">**在呼叫者加入会议时设置会议体验**</span><span class="sxs-lookup"><span data-stu-id="a8080-128">**Set up the meeting experience when callers join a meeting**</span></span>
    
1. <span data-ttu-id="a8080-129">在**Skype for business 管理中心**的左侧导航中，转到 "**音频会议** > **Microsoft 网桥设置**"。</span><span class="sxs-lookup"><span data-stu-id="a8080-129">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="a8080-130">在 " **Microsoft bridge 设置**" 页面上的 "**会议加入体验**" 下，选择：</span><span class="sxs-lookup"><span data-stu-id="a8080-130">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span></span>
    
   - <span data-ttu-id="a8080-131">" **启用会议进入和退出通知**"此选项默认情况下选中。</span><span class="sxs-lookup"><span data-stu-id="a8080-131">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="a8080-132">如果清除该复选框，当有人进入或离开会议时，已加入会议的用户不会收到通知。</span><span class="sxs-lookup"><span data-stu-id="a8080-132">If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
   - <span data-ttu-id="a8080-133">如果选择 "**启用会议进入和退出通知**"，则可以从 "**输入/退出通知类型**" 列表中选择这些选项：</span><span class="sxs-lookup"><span data-stu-id="a8080-133">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span></span>
    
   - <span data-ttu-id="a8080-134">**姓名或电话号码**当用户拨入会议时，将在加入会议时播放其电话号码。</span><span class="sxs-lookup"><span data-stu-id="a8080-134">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="a8080-135">**声音**当用户拨入会议时，将在加入会议时播放音频音调。</span><span class="sxs-lookup"><span data-stu-id="a8080-135">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
  
   - <span data-ttu-id="a8080-136">" **要求呼叫者在加入会议之前录制其名称**"此选项默认情况下选中。</span><span class="sxs-lookup"><span data-stu-id="a8080-136">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="a8080-137">如果清除此复选框，则不会要求呼叫者在加入会议之前录制其名称。</span><span class="sxs-lookup"><span data-stu-id="a8080-137">If you clear the check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
3. <span data-ttu-id="a8080-138">完成更改后，单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="a8080-138">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="a8080-139">**设置会议的 PIN 长度**</span><span class="sxs-lookup"><span data-stu-id="a8080-139">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="a8080-140">使用你的工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="a8080-140">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="a8080-141">转到**Microsoft 365 管理中心** > **Skype for business**。</span><span class="sxs-lookup"><span data-stu-id="a8080-141">Go to the **Microsoft 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="a8080-142">在**Skype for business 管理中心**的左侧导航中，转到 "**音频会议** > **Microsoft 网桥设置**"。</span><span class="sxs-lookup"><span data-stu-id="a8080-142">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="a8080-143">在 " **Microsoft 网桥设置**" 页面上的 "**安全**" 下，在 " **pin 长度**" 列表中输入 pin 所需的数字位数，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="a8080-143">On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a8080-144">PIN 必须介于4到12位之间。</span><span class="sxs-lookup"><span data-stu-id="a8080-144">The PIN must be between 4 and 12 digits.</span></span> 
  
<span data-ttu-id="a8080-145">**选择是否向你的用户发送电子邮件**</span><span class="sxs-lookup"><span data-stu-id="a8080-145">**Select whether to send email to your users**</span></span>
  
1. <span data-ttu-id="a8080-146">使用你的工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="a8080-146">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="a8080-147">转到**Microsoft 365 管理中心** > **Skype for business**。</span><span class="sxs-lookup"><span data-stu-id="a8080-147">Go to the **Microsoft 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="a8080-148">在**Skype for business 管理中心**的左侧导航中，转到 "**音频会议** > **Microsoft 网桥设置**"。</span><span class="sxs-lookup"><span data-stu-id="a8080-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="a8080-149">在 " **Microsoft 网桥设置**" 页面上，选中或清除 "**如果其拨入信息更改，则自动向用户发送电子邮件**"，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="a8080-149">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their dial-in information changes**, and then click **Save**.</span></span>
    
    <span data-ttu-id="a8080-150">当用户在[Skype For Business Online 中的设置发生更改时](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change)，请参阅[自动向用户发送的电子邮件的语音会议设置](emails-sent-to-users-when-their-settings-change-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="a8080-150">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="a8080-151">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="a8080-151">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="a8080-152">若要节省时间或自动执行此过程，你可以使用[CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a8080-152">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) cmdlet.</span></span>
    
- <span data-ttu-id="a8080-p107">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="a8080-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="a8080-156">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="a8080-156">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="a8080-157">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="a8080-157">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="a8080-158">Windows PowerShell 在速度、简洁性和效率方面具有许多优势，仅限于使用 Microsoft 365 管理中心，例如当你为多个用户同时进行设置更改时。</span><span class="sxs-lookup"><span data-stu-id="a8080-158">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="a8080-159">请在以下主题中了解这些优点：</span><span class="sxs-lookup"><span data-stu-id="a8080-159">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="a8080-160">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="a8080-160">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="a8080-161">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a8080-161">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="a8080-162">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="a8080-162">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="a8080-p109">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="a8080-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="a8080-165">相关主题</span><span class="sxs-lookup"><span data-stu-id="a8080-165">Related topics</span></span>

[<span data-ttu-id="a8080-166">设置 Microsoft Teams 的音频会议</span><span class="sxs-lookup"><span data-stu-id="a8080-166">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

[<span data-ttu-id="a8080-167">为 Skype for business Online 设置音频会议</span><span class="sxs-lookup"><span data-stu-id="a8080-167">Set up Audio Conferencing for Skype for Business Online</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
