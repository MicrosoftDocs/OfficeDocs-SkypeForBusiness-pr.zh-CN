---
title: Enable or disable sending emails when their settings change
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
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
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: 4138ed08ef05cc1947131dab22d5470e52eda6c5
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change"></a><span data-ttu-id="53039-103">启用或禁用发送电子邮件时更改音频会议设置</span><span class="sxs-lookup"><span data-stu-id="53039-103">Enable or disable sending emails when Audio Conferencing settings change</span></span>

<span data-ttu-id="53039-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span><span class="sxs-lookup"><span data-stu-id="53039-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="53039-105">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business and Microsoft Teams user.</span><span class="sxs-lookup"><span data-stu-id="53039-105">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business and Microsoft Teams user.</span></span> <span data-ttu-id="53039-106">In such cases, you can disable sending email.</span><span class="sxs-lookup"><span data-stu-id="53039-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="53039-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span><span class="sxs-lookup"><span data-stu-id="53039-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="53039-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span><span class="sxs-lookup"><span data-stu-id="53039-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Audio Conferencing email](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="53039-110">什么时候向用户发送电子邮件？</span><span class="sxs-lookup"><span data-stu-id="53039-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="53039-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span><span class="sxs-lookup"><span data-stu-id="53039-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="53039-112">When an **Audio Conferencing** license is assigned to them.</span><span class="sxs-lookup"><span data-stu-id="53039-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="53039-113">When you manually reset the user's audio conferencing PIN.</span><span class="sxs-lookup"><span data-stu-id="53039-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="53039-114">当你手动重置用户的会议 ID 时。</span><span class="sxs-lookup"><span data-stu-id="53039-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="53039-115">When the **Audio Conferencing** license is removed from them.</span><span class="sxs-lookup"><span data-stu-id="53039-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="53039-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span><span class="sxs-lookup"><span data-stu-id="53039-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="53039-117">When the audio conferencing provider of a user is changed to Microsoft.</span><span class="sxs-lookup"><span data-stu-id="53039-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>
    
## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="53039-118">Enable or disable email from being sent to users</span><span class="sxs-lookup"><span data-stu-id="53039-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="53039-119">You can use Microsoft Teams, the Skype for Business admin center, or Windows PowerShell to enable or disable email sent to users.</span><span class="sxs-lookup"><span data-stu-id="53039-119">You can use Microsoft Teams, the Skype for Business admin center, or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="53039-120">**Using the Microsoft Teams and Skype for Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="53039-120">**Using the Microsoft Teams and Skype for Business Admin Center**</span></span>
1. <span data-ttu-id="53039-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span><span class="sxs-lookup"><span data-stu-id="53039-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="53039-122">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span><span class="sxs-lookup"><span data-stu-id="53039-122">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="53039-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span><span class="sxs-lookup"><span data-stu-id="53039-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="53039-124">单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="53039-124">Click **Apply**.</span></span>
  
<span data-ttu-id="53039-125">**Using the Skype for Business admin center**</span><span class="sxs-lookup"><span data-stu-id="53039-125">**Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="53039-126">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span><span class="sxs-lookup"><span data-stu-id="53039-126">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="53039-127">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span><span class="sxs-lookup"><span data-stu-id="53039-127">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="53039-128">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="53039-128">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="53039-129">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span><span class="sxs-lookup"><span data-stu-id="53039-129">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="53039-130">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span><span class="sxs-lookup"><span data-stu-id="53039-130">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="53039-131">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span><span class="sxs-lookup"><span data-stu-id="53039-131">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
<span data-ttu-id="53039-132">**Using Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="53039-132">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="53039-133">Run the following to disable sending emails:</span><span class="sxs-lookup"><span data-stu-id="53039-133">Run the following to disable sending emails:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="53039-134">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span><span class="sxs-lookup"><span data-stu-id="53039-134">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="53039-135">你还需了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="53039-135">What else should you know?</span></span>

- <span data-ttu-id="53039-136">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span><span class="sxs-lookup"><span data-stu-id="53039-136">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="53039-137">However, if you do this, the PIN won't be included.</span><span class="sxs-lookup"><span data-stu-id="53039-137">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="53039-138">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span><span class="sxs-lookup"><span data-stu-id="53039-138">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="53039-139">可以使用 Skype for Business 管理中心或 Windows PowerShell 禁用向用户发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="53039-139">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="53039-140">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="53039-140">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="53039-141">You can use these cmdlets to save time or automate this.</span><span class="sxs-lookup"><span data-stu-id="53039-141">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="53039-142">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="53039-142">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [<span data-ttu-id="53039-143">Remove-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="53039-143">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [<span data-ttu-id="53039-144">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="53039-144">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [<span data-ttu-id="53039-145">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="53039-145">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  <span data-ttu-id="53039-p104">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="53039-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="53039-149">Why you need to use Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="53039-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="53039-150">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="53039-150">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="53039-151">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time.</span><span class="sxs-lookup"><span data-stu-id="53039-151">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="53039-152">请在以下主题中了解这些优点：</span><span class="sxs-lookup"><span data-stu-id="53039-152">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="53039-153">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="53039-153">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="53039-154">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="53039-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="53039-155">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="53039-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="53039-p106">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="53039-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="53039-158">相关主题</span><span class="sxs-lookup"><span data-stu-id="53039-158">Related topics</span></span>

[<span data-ttu-id="53039-159">Emails sent to users when their Audio Conferencing settings change</span><span class="sxs-lookup"><span data-stu-id="53039-159">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="53039-160">对其音频会议信息的用户发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="53039-160">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)


