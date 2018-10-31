---
title: Skype for Business Online 中的音频会议设置更改时启用或禁用发送电子邮件
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解 Skype 在 pin 或默认会议数等设置发生更改时如何启用或禁用向用户发送的电子邮件。 '
ms.openlocfilehash: 7c9c768dfc8bb01bdcbc8e9f20bec1bd980b1e0d
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23864312"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a><span data-ttu-id="5cc76-103">Skype for Business Online 中的音频会议设置更改时启用或禁用发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="5cc76-103">Enable or disable sending emails when Audio Conferencing settings change in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="5cc76-104">如果您想要启用或禁用中的 Microsoft 团队发送电子邮件，请参阅 [Microsoft Teams 中的音频会议设置发生更改时启用或禁用发送电子邮件](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="5cc76-104">If you want to enable or disable sending emails in Microsoft Teams, see [Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="5cc76-105">要在 Microsoft Teams 中启用或禁用发送电子邮件，请参阅 Microsoft Teams 音频会议设置发生更改时启用或禁用发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="5cc76-105">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="5cc76-106">但是有时候，可能你想要减少发送到 Skype for Business 用户的电子邮件数量。</span><span class="sxs-lookup"><span data-stu-id="5cc76-106">There may be times though when you want to reduce the number of emails that are sent to users, and in that case you can disable this.</span></span> <span data-ttu-id="5cc76-107">在这种情况下，您可以禁用发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5cc76-107">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="5cc76-108">如果禁用发送电子邮件，音频会议电子邮件不会发送给你的用户，包括以下情况的电子邮件：当用户启用或禁用音频会议时、重置其 PIN 时以及当会议 ID 和默认会议电话号码发生更改时。</span><span class="sxs-lookup"><span data-stu-id="5cc76-108">If you disable sending emails, all dial-in conferencing emails won't be sent to your users including emails for when users are enabled or disabled for dial-in conferencing, when their PIN is reset, when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="5cc76-109">下面是他们启用音频会议时，向用户发送的电子邮件的示例：</span><span class="sxs-lookup"><span data-stu-id="5cc76-109">Here is an example of the email that is sent to users that are enabled for dial-in conferencing:</span></span>
  
![音频会议电子邮件](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="5cc76-111">什么时候向用户发送电子邮件？</span><span class="sxs-lookup"><span data-stu-id="5cc76-111">When are emails being sent to your users?</span></span>

- <span data-ttu-id="5cc76-112">在为你的组织中的用户启用音频会议之后，会向他们发送许多电子邮件：</span><span class="sxs-lookup"><span data-stu-id="5cc76-112">There are several emails that are set to users in your organization after they are enabled for dial-in conferencing:</span></span>
    
  - <span data-ttu-id="5cc76-113">向其分配**音频会议**许可证时。</span><span class="sxs-lookup"><span data-stu-id="5cc76-113">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="5cc76-114">手动重置用户的音频会议 PIN 时。</span><span class="sxs-lookup"><span data-stu-id="5cc76-114">When you manually reset the user's dial-in conferencing PIN.</span></span>
    
  - <span data-ttu-id="5cc76-115">手动重置用户的会议 ID 时。</span><span class="sxs-lookup"><span data-stu-id="5cc76-115">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="5cc76-116">删除其**音频会议**许可证时。</span><span class="sxs-lookup"><span data-stu-id="5cc76-116">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="5cc76-117">用户的音频会议提供商从 Microsoft 更改为另一个提供商或**无**时。</span><span class="sxs-lookup"><span data-stu-id="5cc76-117">When the dial-in conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="5cc76-118">用户的音频会议提供商更改为 Microsoft 时。</span><span class="sxs-lookup"><span data-stu-id="5cc76-118">When the dial-in conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="5cc76-119">启用或禁用向用户发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="5cc76-119">Enable or disable email from being sent to dial-in users</span></span>

<span data-ttu-id="5cc76-120">你可以使用 Skype for Business 管理中心或 Windows PowerShell 启用或禁用向用户发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5cc76-120">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email from being sent to users.</span></span>

 
<span data-ttu-id="5cc76-121">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**</span><span class="sxs-lookup"><span data-stu-id="5cc76-121">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="5cc76-122">在 **Skype for Business 管理中心**的左侧导航中，转到**音频会议**。</span><span class="sxs-lookup"><span data-stu-id="5cc76-122">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under Conference ID, click Reset.</span></span>
    
2. <span data-ttu-id="5cc76-123">在 **Microsoft 网桥的设置** 页上，选中或清除 **如果用户的音频会议设置更改，自动向他们发送电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="5cc76-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="5cc76-124">单击 **保存** 。</span><span class="sxs-lookup"><span data-stu-id="5cc76-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="5cc76-125">你也可以通过电子邮件向用户发送音频会议的设置， 方法是转到**音频会议** > **用户**，选择用户，并单击 **通过电子邮件发送会议信息**。</span><span class="sxs-lookup"><span data-stu-id="5cc76-125">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="5cc76-126">如果执行此操作，则将发送仅包括会议 ID 和会议电话号码的电子邮件，但不包括 PIN。</span><span class="sxs-lookup"><span data-stu-id="5cc76-126">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>  <span data-ttu-id="5cc76-127">请参阅[通过电子邮件向用户发送音频会议信息](send-an-email-to-a-user-with-their-dial-in-information.md)。</span><span class="sxs-lookup"><span data-stu-id="5cc76-127">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="5cc76-128">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="5cc76-128">\*\*\*\* Using Windows PowerShell</span></span>
  
- <span data-ttu-id="5cc76-129">运行以下命令以禁用发送电子邮件：</span><span class="sxs-lookup"><span data-stu-id="5cc76-129">Run the following to disable sending all of your users email:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="5cc76-130"> 要获取此 cmdlet 的帮助，请参阅 [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)。</span><span class="sxs-lookup"><span data-stu-id="5cc76-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="5cc76-131">你还需了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="5cc76-131">What else should you know?</span></span>

- <span data-ttu-id="5cc76-132">当禁用自动电子邮件时，你仍然可以使用 Skype for Busines 管理中心手动触发包含会议 ID 和电话号码的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5cc76-132">When automatic emails are disabled, you can still can manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="5cc76-133">但是，如果执行此操作，则不会包含 PIN。</span><span class="sxs-lookup"><span data-stu-id="5cc76-133">However, if you do this the PIN won't be included.</span></span> <span data-ttu-id="5cc76-134">如果要重置音频会议 PIN 并禁用发送电子邮件，则需要通过另一种方式将其发送给用户。</span><span class="sxs-lookup"><span data-stu-id="5cc76-134">If you want to reset the dial-in conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="5cc76-135">可以使用 Skype for Business 管理中心或 Windows PowerShell 禁用向用户发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5cc76-135">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="5cc76-136">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="5cc76-136">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="5cc76-137">可以使用这些 cmdlet 来节省时间或自动执行此操作。</span><span class="sxs-lookup"><span data-stu-id="5cc76-137">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="5cc76-138">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="5cc76-138">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [<span data-ttu-id="5cc76-139">Remove-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="5cc76-139">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [<span data-ttu-id="5cc76-140">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="5cc76-140">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [<span data-ttu-id="5cc76-141">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="5cc76-141">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  <span data-ttu-id="5cc76-p104">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="5cc76-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5cc76-145">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="5cc76-145">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="5cc76-146">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="5cc76-146">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="5cc76-147">与仅使用 Office 365 管理中心相比，Windows PowerShell 在速度、简化程度和工作效率等方面具有许多优点，例如，当一次更改许多用户的设置时。</span><span class="sxs-lookup"><span data-stu-id="5cc76-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="5cc76-148">请在以下主题中了解这些优点：</span><span class="sxs-lookup"><span data-stu-id="5cc76-148">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="5cc76-149">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="5cc76-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="5cc76-150">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="5cc76-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="5cc76-151">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="5cc76-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="5cc76-p106">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="5cc76-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="5cc76-154">相关主题</span><span class="sxs-lookup"><span data-stu-id="5cc76-154">Related topics</span></span>

[<span data-ttu-id="5cc76-155">用户音频会议设置更改时向其发送的电子邮件</span><span class="sxs-lookup"><span data-stu-id="5cc76-155">Emails sent to users when their settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="5cc76-156">通过电子邮件向用户发送音频会议信息</span><span class="sxs-lookup"><span data-stu-id="5cc76-156">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)


