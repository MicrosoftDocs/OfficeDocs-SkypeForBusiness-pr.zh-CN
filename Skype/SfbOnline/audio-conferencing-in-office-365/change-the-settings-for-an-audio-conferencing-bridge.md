---
title: 更改音频会议桥的设置
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: '了解您需要更改用来提示的调用方，并收集名称和会议组织者的针脚时他们正在用于业务或 Microsoft 团队的应用程序不使用 Skype 会议桥的设置步骤。 '
ms.openlocfilehash: 1ab6f5f82d8282f9062439f875ea15d2ab6d7fd5
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="5c4a1-103">更改音频会议桥的设置</span><span class="sxs-lookup"><span data-stu-id="5c4a1-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="5c4a1-104">要设置 Office 365 中的音频会议，将为您的用户从所谓的音频会议网桥收到电话号码。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="5c4a1-105">会议网桥可以包含一个或多个电话号码。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="5c4a1-106">调用方拨号加入会议时，将使用这些电话号码。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="5c4a1-107">电话号码是包含在业务或 Microsoft 小组会议邀请的 Skype 的底部。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="5c4a1-108">会议桥应答呼叫，并提示调用方通过语音提示使用会议自动助理，然后根据您的设置，它可以播放通知，要求调用方来记录他们的姓名，并控制 PIN 设置。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="5c4a1-109">针脚提供给会议组织者，使他们开始会议时不使用 Skype 业务或 Microsoft 团队的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="5c4a1-110">PIN 只是对于会议组织者时为业务或 Microsoft 小组应用程序用户 Skype 已经没有启动会议是必需的。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-110">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting.</span></span> <span data-ttu-id="5c4a1-111">每个人都拨号进入会议，针需要为会议组织者开始举行会议。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-111">If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

> [!CAUTION]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="using-the-microsoft-teams-and-skype-for-business-admin-center"></a><span data-ttu-id="5c4a1-112">使用 Microsoft 小组和 Skype 业务管理中心</span><span class="sxs-lookup"><span data-stu-id="5c4a1-112">Using the Microsoft Teams and Skype for Business Admin Center</span></span>

1. <span data-ttu-id="5c4a1-113">在左侧的导航中，转到**会议** > **会议桥**。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-113">In the left navigation, go to **Meetings** > **Conference bridges**.</span></span> 

2. <span data-ttu-id="5c4a1-114">在**会议桥**页的顶部，单击**桥接器设置**。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-114">At the top of the **Conference bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="5c4a1-115">在**桥接器设置**窗格中，选择：</span><span class="sxs-lookup"><span data-stu-id="5c4a1-115">In the **Bridge settings** pane, select:</span></span> 
  - <span data-ttu-id="5c4a1-116">**会议项，然后退出通知**如果关闭此操作，当有人进入或离开会议，不会通知用户已加入会议。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-116">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="5c4a1-117">当您打开**会议进入和退出的通知**时，您可以选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="5c4a1-117">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
  - <span data-ttu-id="5c4a1-118">**姓名或电话号码**当用户拨号加入会议时，在他们加入时将播放他们的电话号码。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-118">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
  - <span data-ttu-id="5c4a1-119">**拨号音**当用户拨号加入会议时，将它加入后播放音频音调。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-119">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
  - <span data-ttu-id="5c4a1-120">**提出调用方来记录他们的姓名之前加入会议**如果关闭此操作，调用方不需要之前他们加入会议记录他们的姓名。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-120">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="5c4a1-121">若要设置会议的针长度，选择的数字位数的 pin**针长度**列表中所需。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-121">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="5c4a1-122">若要指定是否要将电子邮件发送给您的用户，请启用或禁用**其音频会议配置改变时自动发送电子邮件发送给用户**。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-122">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="5c4a1-123">有关详细信息，请参阅[电子邮件自动发送给用户的音频会议设置更改时](emails-sent-to-users-when-their-settings-change.md)。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-123">See [Emails automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md) for more information.</span></span>
 
6. <span data-ttu-id="5c4a1-124">单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-124">Click **Apply**.</span></span> 

## <a name="using-skype-for-business-admin-center"></a><span data-ttu-id="5c4a1-125">使用 Skype 业务管理中心</span><span class="sxs-lookup"><span data-stu-id="5c4a1-125">Using Skype for Business admin center</span></span>

 <span data-ttu-id="5c4a1-126">**当调用方加入会议设置会议经验**</span><span class="sxs-lookup"><span data-stu-id="5c4a1-126">**Set up the meeting experience when callers join a meeting**</span></span>
    
1. <span data-ttu-id="5c4a1-127">在**业务管理中心的 Skype**，在左边的导航转到**音频会议** > **Microsoft 网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-127">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="5c4a1-128">在下**会议连接体验**， **Microsoft 网桥的设置**页，请选择：</span><span class="sxs-lookup"><span data-stu-id="5c4a1-128">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span></span>
    
  - <span data-ttu-id="5c4a1-129">" **启用会议进入和退出通知**"此选项默认情况下选中。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-129">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="5c4a1-130">如果清除复选框，当有人进入或离开会议，不会通知用户已加入会议。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-130">If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="5c4a1-131">**启用会议进入和退出通知以打开**选择时，您可以从**入口/出口公告类型**列表中选择这些选项：</span><span class="sxs-lookup"><span data-stu-id="5c4a1-131">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span></span>
    
  - <span data-ttu-id="5c4a1-132">**姓名或电话号码**当用户拨号加入会议时，在他们加入时将播放他们的电话号码。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-132">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
  - <span data-ttu-id="5c4a1-133">**拨号音**当用户拨号加入会议时，将它加入后播放音频音调。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-133">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
  
  - <span data-ttu-id="5c4a1-134">" **要求呼叫者在加入会议之前录制其名称**"此选项默认情况下选中。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-134">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="5c4a1-135">如果清除复选框，将不要求调用方之前他们加入会议记录他们的姓名。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-135">If you clear the check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
3. <span data-ttu-id="5c4a1-136">完成更改后，单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-136">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="5c4a1-137">**设置会议的针长度**</span><span class="sxs-lookup"><span data-stu-id="5c4a1-137">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="5c4a1-138">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-138">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="5c4a1-139">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="5c4a1-139">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="5c4a1-140">在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议** > **Microsoft 网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-140">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="5c4a1-141">在**Microsoft 桥设置**页上，在**安全**下，输入 PIN**针长度**列表中，为所需的位数，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-141">On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5c4a1-142">PIN 必须介于 4 到 12 位。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-142">The PIN must be between 4 and 12 digits.</span></span> 
  
<span data-ttu-id="5c4a1-143">**选择是否要将电子邮件发送给您的用户**</span><span class="sxs-lookup"><span data-stu-id="5c4a1-143">**Select whether to send email to your users**</span></span>
  
1. <span data-ttu-id="5c4a1-144">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-144">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="5c4a1-145">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="5c4a1-145">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="5c4a1-146">在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议** > **Microsoft 网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-146">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="5c4a1-147">在**Microsoft 桥设置**页上，选择或清除**其拨入信息改变时自动发送电子邮件发送给用户**，，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-147">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their dial-in information changes**, and then click **Save**.</span></span>
    
    <span data-ttu-id="5c4a1-148">有关详细信息，请参阅[电子邮件自动发送给用户的音频会议设置更改时](emails-sent-to-users-when-their-settings-change.md)。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-148">See [Emails automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md) for more information.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="5c4a1-149">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="5c4a1-149">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="5c4a1-150">若要节省时间或自动执行此过程，您可以使用[一组 CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-150">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet.</span></span>
    
- <span data-ttu-id="5c4a1-p107">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="5c4a1-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5c4a1-154">为什么需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="5c4a1-154">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="5c4a1-155">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="5c4a1-155">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="5c4a1-156">Windows PowerShell 许多相比具有的优势在速度、 简易性和生产率仅使用 Office 365 管理中心，例如，当将设置更改为许多用户一次。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-156">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="5c4a1-157">请在以下主题中了解这些优点：</span><span class="sxs-lookup"><span data-stu-id="5c4a1-157">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="5c4a1-158">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="5c4a1-158">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="5c4a1-159">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="5c4a1-159">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="5c4a1-160">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="5c4a1-160">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="5c4a1-p109">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="5c4a1-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="5c4a1-163">相关主题</span><span class="sxs-lookup"><span data-stu-id="5c4a1-163">Related topics</span></span>

[<span data-ttu-id="5c4a1-164">设置音频会议</span><span class="sxs-lookup"><span data-stu-id="5c4a1-164">Set up Audio Conferencing</span></span>](set-up-audio-conferencing.md)
