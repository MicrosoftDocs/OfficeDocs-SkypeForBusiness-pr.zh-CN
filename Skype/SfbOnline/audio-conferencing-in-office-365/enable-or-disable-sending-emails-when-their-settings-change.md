---
title: 启用或禁用发送电子邮件，音频会议设置更改 Skype 中的业务联机时
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: 4d52603fb0d2701cbebd58644cd002dbc94baf89
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490582"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a><span data-ttu-id="eb023-103">启用或禁用发送电子邮件，音频会议设置更改 Skype 中的业务联机时</span><span class="sxs-lookup"><span data-stu-id="eb023-103">Enable or disable sending emails when Audio Conferencing settings change in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="eb023-104">如果您想要启用或禁用中的 Microsoft 团队发送电子邮件，请参阅[启用或禁用发送电子邮件时要进行音频会议设置中的 Microsoft 团队发生更改](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="eb023-104">If you want to enable or disable sending emails in Microsoft Teams, see [Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="eb023-105">他们启用音频会议时，将自动通过电子邮件通知用户。</span><span class="sxs-lookup"><span data-stu-id="eb023-105">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="eb023-106">有时可能，但是，当您想要减少的电子邮件发送到 Skype 业务用户的数量。</span><span class="sxs-lookup"><span data-stu-id="eb023-106">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business users.</span></span> <span data-ttu-id="eb023-107">在这种情况下，您可以禁用发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="eb023-107">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="eb023-108">如果您禁用发送电子邮件，就不会音频会议电子邮件发送给用户，当用户处于启用或禁用音频会议以及会议 ID 和默认会议电话号码的更改时重置其 PIN，包括电子邮件.</span><span class="sxs-lookup"><span data-stu-id="eb023-108">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="eb023-109">下面是他们启用音频会议时，向用户发送的电子邮件的示例：</span><span class="sxs-lookup"><span data-stu-id="eb023-109">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![音频会议电子邮件](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="eb023-111">什么时候向用户发送电子邮件？</span><span class="sxs-lookup"><span data-stu-id="eb023-111">When are emails being sent to your users?</span></span>

- <span data-ttu-id="eb023-112">有多个电子邮件发送给组织中的用户启用了后为音频会议：</span><span class="sxs-lookup"><span data-stu-id="eb023-112">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="eb023-113">当**音频会议**许可证分配给它们。</span><span class="sxs-lookup"><span data-stu-id="eb023-113">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="eb023-114">当您手动重置用户的音频会议 PIN。</span><span class="sxs-lookup"><span data-stu-id="eb023-114">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="eb023-115">当你手动重置用户的会议 ID 时。</span><span class="sxs-lookup"><span data-stu-id="eb023-115">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="eb023-116">当**音频会议**许可证已从它们。</span><span class="sxs-lookup"><span data-stu-id="eb023-116">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="eb023-117">当用户的音频会议提供商从 Microsoft 更改为其他提供程序或**无**。</span><span class="sxs-lookup"><span data-stu-id="eb023-117">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="eb023-118">向 Microsoft 更改时用户的音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="eb023-118">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="eb023-119">启用或禁用从发送给用户的电子邮件</span><span class="sxs-lookup"><span data-stu-id="eb023-119">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="eb023-120">您可以使用业务管理中心的 Skype 或 Windows PowerShell 启用或禁用电子邮件发送给用户。</span><span class="sxs-lookup"><span data-stu-id="eb023-120">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>

 
<span data-ttu-id="eb023-121">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="eb023-121">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="eb023-122">在**业务管理中心的 Skype**，在左侧导航窗格中，单击**音频会议**。</span><span class="sxs-lookup"><span data-stu-id="eb023-122">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="eb023-123">在**Microsoft 网桥的设置**页上，选中或清除**自动发送电子邮件发送给用户，如果其音频会议设置更改**。</span><span class="sxs-lookup"><span data-stu-id="eb023-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="eb023-124">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="eb023-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="eb023-125">您还可以发送电子邮件向用户使用音频会议设置，转到**音频会议** > **用户**，选择用户，并单击**发送电子邮件的会议信息**。</span><span class="sxs-lookup"><span data-stu-id="eb023-125">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="eb023-126">如果执行此操作时，将仅包含会议 ID 和会议电话号码，但不是 PIN 发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="eb023-126">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="eb023-127">有关详细信息，请参阅[发送对其进行音频会议信息的用户电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。</span><span class="sxs-lookup"><span data-stu-id="eb023-127">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="eb023-128">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="eb023-128">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="eb023-129">运行以下命令以禁用发送电子邮件：</span><span class="sxs-lookup"><span data-stu-id="eb023-129">Run the following to disable sending emails:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="eb023-130">此 cmdlet 的帮助，请参阅[设置 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)。</span><span class="sxs-lookup"><span data-stu-id="eb023-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="eb023-131">你还需了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="eb023-131">What else should you know?</span></span>

- <span data-ttu-id="eb023-132">禁用自动电子邮件后，您可以仍手动触发发送电子邮件与业务管理中心的使用 Skype 的会议 ID 和电话号码。</span><span class="sxs-lookup"><span data-stu-id="eb023-132">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="eb023-133">但是，如果执行此操作时，将不会包含 PIN。</span><span class="sxs-lookup"><span data-stu-id="eb023-133">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="eb023-134">如果您要重置 PIN 的音频会议和发送电子邮件被禁用，您需要向用户发送中另一种方法。</span><span class="sxs-lookup"><span data-stu-id="eb023-134">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="eb023-135">可以使用 Skype for Business 管理中心或 Windows PowerShell 禁用向用户发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="eb023-135">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="eb023-136">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="eb023-136">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="eb023-137">可以使用这些 cmdlet 来节省时间或自动此操作。</span><span class="sxs-lookup"><span data-stu-id="eb023-137">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="eb023-138">Get CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="eb023-138">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [<span data-ttu-id="eb023-139">删除 CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="eb023-139">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [<span data-ttu-id="eb023-140">Get CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="eb023-140">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [<span data-ttu-id="eb023-141">Get CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="eb023-141">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  <span data-ttu-id="eb023-p104">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="eb023-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="eb023-145">为什么您需要使用 Office 365 PowerShell 中</span><span class="sxs-lookup"><span data-stu-id="eb023-145">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="eb023-146">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="eb023-146">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="eb023-147">Windows PowerShell 具有很多好处中快速、 简便起见和生产力通过只使用 Office 365 管理中心中的，如时要进行设置更改多个用户一次。</span><span class="sxs-lookup"><span data-stu-id="eb023-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="eb023-148">请在以下主题中了解这些优点：</span><span class="sxs-lookup"><span data-stu-id="eb023-148">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="eb023-149">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="eb023-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="eb023-150">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="eb023-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="eb023-151">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="eb023-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="eb023-p106">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="eb023-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="eb023-154">相关主题</span><span class="sxs-lookup"><span data-stu-id="eb023-154">Related topics</span></span>

[<span data-ttu-id="eb023-155">其音频会议设置更改时向用户发送的电子邮件</span><span class="sxs-lookup"><span data-stu-id="eb023-155">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="eb023-156">对其音频会议信息的用户发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="eb023-156">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)


