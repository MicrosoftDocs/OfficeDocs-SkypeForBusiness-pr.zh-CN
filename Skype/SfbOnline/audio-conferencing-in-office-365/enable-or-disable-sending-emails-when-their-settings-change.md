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
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解 Skype 在 pin 或默认会议数等设置发生更改时如何启用或禁用向用户发送的电子邮件。 '
ms.openlocfilehash: a9100de01fc835916af54d08b84dbd03a06ec1d6
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370870"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a><span data-ttu-id="ed731-103">Skype for Business Online 中的音频会议设置更改时启用或禁用发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="ed731-103">Enable or disable sending emails when Audio Conferencing settings change in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="ed731-104">如果您想要启用或禁用中的 Microsoft 团队发送电子邮件，请参阅 [Microsoft Teams 中的音频会议设置发生更改时启用或禁用发送电子邮件](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="ed731-104">If you want to enable or disable sending emails in Microsoft Teams, see [Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="ed731-p101">Users are automatically notified by email when they are enabled for Audio Conferencing. There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business users. In such cases, you can disable sending email.</span><span class="sxs-lookup"><span data-stu-id="ed731-p101">Users are automatically notified by email when they are enabled for Audio Conferencing. There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business users. In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="ed731-108">如果您禁用发送电子邮件，就不会音频会议电子邮件发送给用户，当用户处于启用或禁用音频会议以及会议 ID 和默认会议电话号码的更改时重置其 PIN，包括电子邮件.</span><span class="sxs-lookup"><span data-stu-id="ed731-108">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="ed731-109">下面是他们启用音频会议时，向用户发送的电子邮件的示例：</span><span class="sxs-lookup"><span data-stu-id="ed731-109">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![音频会议电子邮件](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="ed731-111">什么时候向用户发送电子邮件？</span><span class="sxs-lookup"><span data-stu-id="ed731-111">When are emails being sent to your users?</span></span>

- <span data-ttu-id="ed731-112">有多个电子邮件发送给组织中的用户启用了后为音频会议：</span><span class="sxs-lookup"><span data-stu-id="ed731-112">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="ed731-113">向其分配**音频会议**许可证时。</span><span class="sxs-lookup"><span data-stu-id="ed731-113">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="ed731-114">当您手动重置用户的音频会议 PIN。</span><span class="sxs-lookup"><span data-stu-id="ed731-114">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="ed731-115">当你手动重置用户的会议 ID 时。</span><span class="sxs-lookup"><span data-stu-id="ed731-115">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="ed731-116">删除其**音频会议**许可证时。</span><span class="sxs-lookup"><span data-stu-id="ed731-116">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="ed731-117">当用户的音频会议提供商从 Microsoft 更改为其他提供程序或**无**。</span><span class="sxs-lookup"><span data-stu-id="ed731-117">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="ed731-118">向 Microsoft 更改时用户的音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="ed731-118">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="ed731-119">启用或禁用从发送给用户的电子邮件</span><span class="sxs-lookup"><span data-stu-id="ed731-119">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="ed731-120">您可以使用业务管理中心的 Skype 或 Windows PowerShell 启用或禁用电子邮件发送给用户。</span><span class="sxs-lookup"><span data-stu-id="ed731-120">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>

 
<span data-ttu-id="ed731-121">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="ed731-121">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="ed731-122">在**业务管理中心的 Skype**，在左侧导航窗格中，单击**音频会议**。</span><span class="sxs-lookup"><span data-stu-id="ed731-122">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="ed731-123">在 **Microsoft 网桥的设置** 页上，选中或清除 **自动向用户发送电子邮件，如果他们的音频会议设置更改**　。</span><span class="sxs-lookup"><span data-stu-id="ed731-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="ed731-124">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="ed731-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="ed731-p102">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.  If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.  See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span><span class="sxs-lookup"><span data-stu-id="ed731-p102">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.  If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.  See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="ed731-128">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ed731-128">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="ed731-129">运行以下命令以禁用发送电子邮件：</span><span class="sxs-lookup"><span data-stu-id="ed731-129">Run the following to disable sending emails:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="ed731-130"> 要获取此 cmdlet 的帮助，请参阅 [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)。</span><span class="sxs-lookup"><span data-stu-id="ed731-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="ed731-131">你还需了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="ed731-131">What else should you know?</span></span>

- <span data-ttu-id="ed731-p103">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center. However, if you do this, the PIN won't be included. If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span><span class="sxs-lookup"><span data-stu-id="ed731-p103">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center. However, if you do this, the PIN won't be included. If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="ed731-135">可以使用 Skype for Business 管理中心或 Windows PowerShell 禁用向用户发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ed731-135">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="ed731-136">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="ed731-136">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="ed731-137">可以使用这些 cmdlet 来节省时间或自动执行此操作。</span><span class="sxs-lookup"><span data-stu-id="ed731-137">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="ed731-138">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="ed731-138">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [<span data-ttu-id="ed731-139">Remove-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="ed731-139">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [<span data-ttu-id="ed731-140">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="ed731-140">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [<span data-ttu-id="ed731-141">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="ed731-141">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
- <span data-ttu-id="ed731-p104">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="ed731-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ed731-145">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed731-145">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="ed731-146">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="ed731-146">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="ed731-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span><span class="sxs-lookup"><span data-stu-id="ed731-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="ed731-149">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="ed731-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="ed731-150">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ed731-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="ed731-151">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="ed731-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="ed731-p106">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="ed731-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="ed731-154">相关主题</span><span class="sxs-lookup"><span data-stu-id="ed731-154">Related topics</span></span>

[<span data-ttu-id="ed731-155">其音频会议设置更改时向用户发送的电子邮件</span><span class="sxs-lookup"><span data-stu-id="ed731-155">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="ed731-156">对其音频会议信息的用户发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="ed731-156">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)


