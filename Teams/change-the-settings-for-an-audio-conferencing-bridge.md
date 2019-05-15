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
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.audioconferencing.bridgesettings
ms.custom:
- Audio Conferencing
description: '获取所需更改用于提示呼叫者和它们不使用 Skype 业务或 Microsoft 团队的应用程序时收集名称和 pin 的会议组织者的会议桥的设置的步骤。 '
ms.openlocfilehash: 7483a584e3ecd70f9ec34eb5a12d95860c23c36b
ms.sourcegitcommit: 9a99be1365df439f9443f31240aa5311782458df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "33995052"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="1b556-103">更改音频会议网桥的设置</span><span class="sxs-lookup"><span data-stu-id="1b556-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="1b556-104">要设置 Office 365 中的音频会议，您会收到的电话号码为用户从所谓音频会议桥。</span><span class="sxs-lookup"><span data-stu-id="1b556-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="1b556-105">会议网桥可以包含一个或多个电话号码。</span><span class="sxs-lookup"><span data-stu-id="1b556-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="1b556-106">呼叫者拨入会议时，将使用这些电话号码。</span><span class="sxs-lookup"><span data-stu-id="1b556-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="1b556-107">包含业务或 Microsoft 团队的会议邀请的 Skype 底部的电话号码。</span><span class="sxs-lookup"><span data-stu-id="1b556-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="1b556-108">会议桥接听电话，并提示呼叫者使用语音提示使用会议自动助理，然后，具体取决于您的设置，可播放通知、 提出呼叫者在记录其姓名，然后控制 PIN 设置。</span><span class="sxs-lookup"><span data-stu-id="1b556-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="1b556-109">旋转中心点授予对会议组织者允许其开始会议时不使用 Skype 业务或 Microsoft 团队的应用程序。</span><span class="sxs-lookup"><span data-stu-id="1b556-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="1b556-110">PIN 才所需的会议组织者时为业务或 Microsoft 团队的应用程序用户 Skype 不起作用已经启动会议。</span><span class="sxs-lookup"><span data-stu-id="1b556-110">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting.</span></span> <span data-ttu-id="1b556-111">所有人都拨入会议，PIN 需要会议组织者要开始会议。</span><span class="sxs-lookup"><span data-stu-id="1b556-111">If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![团队-徽标-30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="1b556-113">使用 Microsoft 团队管理中心</span><span class="sxs-lookup"><span data-stu-id="1b556-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="1b556-114">在左侧导航窗格中，转到**会议** > **会议桥**。</span><span class="sxs-lookup"><span data-stu-id="1b556-114">In the left navigation, go to **Meetings** > **Conference bridges**.</span></span> 

2. <span data-ttu-id="1b556-115">在**会议桥**页的顶部，单击**网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="1b556-115">At the top of the **Conference bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="1b556-116">在**桥设置**窗格中，选择：</span><span class="sxs-lookup"><span data-stu-id="1b556-116">In the **Bridge settings** pane, select:</span></span> 
   - <span data-ttu-id="1b556-117">**会议条目和退出通知**如果您关闭此操作，在某人进入或离开会议时，不会通知已加入会议的用户。</span><span class="sxs-lookup"><span data-stu-id="1b556-117">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
     <span data-ttu-id="1b556-118">当您打开**会议进入和退出通知**时，您可以选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="1b556-118">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
   - <span data-ttu-id="1b556-119">**姓名或电话号码**当用户拨入会议时，当用户加入它时将播放其电话号码。</span><span class="sxs-lookup"><span data-stu-id="1b556-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="1b556-120">**音**当用户拨入会议时，当用户加入它时将播放音频音。</span><span class="sxs-lookup"><span data-stu-id="1b556-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
   - <span data-ttu-id="1b556-121">**Ask 呼叫者在记录其姓名之前加入会议**如果您关闭此操作，呼叫者不需要记录其姓名，他们加入会议之前。</span><span class="sxs-lookup"><span data-stu-id="1b556-121">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="1b556-122">若要设置会议的 PIN 长度，选择您希望在**PIN 长度**列表的 PIN 的位数。</span><span class="sxs-lookup"><span data-stu-id="1b556-122">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="1b556-123">若要指定是否向用户发送电子邮件，启用或禁用**自动发送电子邮件发送给用户，如果其音频会议配置更改**。</span><span class="sxs-lookup"><span data-stu-id="1b556-123">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="1b556-124">有关详细信息，请参阅[电子邮件自动发送给用户的 Microsoft 团队中更改其音频会议设置时](emails-sent-to-users-when-their-settings-change-in-teams.md)或[电子邮件发送给用户时其设置业务 online Skype 中发生更改](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change)。</span><span class="sxs-lookup"><span data-stu-id="1b556-124">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
 
6. <span data-ttu-id="1b556-125">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="1b556-125">Click **Save**.</span></span> 


## <a name="sfb-logo-30x30pngmediasfb-logo-30x30png--using-the-skype-for-business-admin-center"></a>![sfb-logo-30x30.png](media/sfb-logo-30x30.png)  <span data-ttu-id="1b556-127">使用 Skype for Business 管理中心</span><span class="sxs-lookup"><span data-stu-id="1b556-127">Using the Skype for Business admin center</span></span>

 <span data-ttu-id="1b556-128">**呼叫者加入会议时设置的会议体验**</span><span class="sxs-lookup"><span data-stu-id="1b556-128">**Set up the meeting experience when callers join a meeting**</span></span>
    
1. <span data-ttu-id="1b556-129">在**Skype 业务管理中心的**中，在左侧导航中转到**音频会议** > **Microsoft 网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="1b556-129">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="1b556-130">在**Microsoft 桥设置**页上，在**会议加入体验**，下选择：</span><span class="sxs-lookup"><span data-stu-id="1b556-130">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span></span>
    
   - <span data-ttu-id="1b556-131">" **启用会议进入和退出通知**"此选项默认情况下选中。</span><span class="sxs-lookup"><span data-stu-id="1b556-131">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="1b556-132">如果清除该复选框，某人进入或离开会议时，已加入会议的用户不会收到通知。</span><span class="sxs-lookup"><span data-stu-id="1b556-132">If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
   - <span data-ttu-id="1b556-133">当选择了**启用会议进入和退出通知，以打开**时，您可以从**项/退出通知类型**列表选择这些选项：</span><span class="sxs-lookup"><span data-stu-id="1b556-133">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span></span>
    
   - <span data-ttu-id="1b556-134">**姓名或电话号码**当用户拨入会议时，当用户加入它时将播放其电话号码。</span><span class="sxs-lookup"><span data-stu-id="1b556-134">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="1b556-135">**音**当用户拨入会议时，当用户加入它时将播放音频音。</span><span class="sxs-lookup"><span data-stu-id="1b556-135">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
  
   - <span data-ttu-id="1b556-136">" **要求呼叫者在加入会议之前录制其名称**"此选项默认情况下选中。</span><span class="sxs-lookup"><span data-stu-id="1b556-136">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="1b556-137">如果清除该复选框，呼叫者不需要记录其姓名，他们加入会议之前。</span><span class="sxs-lookup"><span data-stu-id="1b556-137">If you clear the check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
3. <span data-ttu-id="1b556-138">完成更改后，单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="1b556-138">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="1b556-139">**设置会议的 PIN 长度**</span><span class="sxs-lookup"><span data-stu-id="1b556-139">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="1b556-140">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="1b556-140">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="1b556-141">转到**Microsoft 365 管理中心** > **for Business 的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="1b556-141">Go to the **Microsoft 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="1b556-142">在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议** > **Microsoft 网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="1b556-142">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="1b556-143">在**Microsoft 网桥的设置**页上的在**安全**下，输入您希望在**PIN 长度**列表中，PIN 的位数，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="1b556-143">On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1b556-144">PIN 必须介于4到12位之间。</span><span class="sxs-lookup"><span data-stu-id="1b556-144">The PIN must be between 4 and 12 digits.</span></span> 
  
<span data-ttu-id="1b556-145">**选择是否向用户发送电子邮件**</span><span class="sxs-lookup"><span data-stu-id="1b556-145">**Select whether to send email to your users**</span></span>
  
1. <span data-ttu-id="1b556-146">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="1b556-146">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="1b556-147">转到**Microsoft 365 管理中心** > **for Business 的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="1b556-147">Go to the **Microsoft 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="1b556-148">在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议** > **Microsoft 网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="1b556-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="1b556-149">在**Microsoft 网桥的设置**页上，选择或清除**其电话拨入式信息改变时自动发送给用户的电子邮件**，，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="1b556-149">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their dial-in information changes**, and then click **Save**.</span></span>
    
    <span data-ttu-id="1b556-150">有关详细信息，请参阅[电子邮件自动发送给用户的 Microsoft 团队中更改其音频会议设置时](emails-sent-to-users-when-their-settings-change-in-teams.md)或[电子邮件发送给用户时其设置业务 online Skype 中发生更改](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change)。</span><span class="sxs-lookup"><span data-stu-id="1b556-150">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="1b556-151">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="1b556-151">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="1b556-152">要保存时间或自动执行此过程，您可以使用[集 CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1b556-152">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) cmdlet.</span></span>
    
- <span data-ttu-id="1b556-p107">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="1b556-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="1b556-156">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b556-156">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="1b556-157">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="1b556-157">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="1b556-158">Windows PowerShell 具有很多好处中快速、 简便起见和生产力通过仅使用 Microsoft 365 管理中心中的，如时要进行设置更改多个用户一次。</span><span class="sxs-lookup"><span data-stu-id="1b556-158">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="1b556-159">请在以下主题中了解这些优点：</span><span class="sxs-lookup"><span data-stu-id="1b556-159">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="1b556-160">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="1b556-160">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="1b556-161">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1b556-161">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="1b556-162">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="1b556-162">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="1b556-p109">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="1b556-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="1b556-165">相关主题</span><span class="sxs-lookup"><span data-stu-id="1b556-165">Related topics</span></span>

[<span data-ttu-id="1b556-166">设置 Microsoft Teams 的音频会议</span><span class="sxs-lookup"><span data-stu-id="1b556-166">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

[<span data-ttu-id="1b556-167">为 Skype 的音频会议设置业务 online</span><span class="sxs-lookup"><span data-stu-id="1b556-167">Set up Audio Conferencing for Skype for Business Online</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
