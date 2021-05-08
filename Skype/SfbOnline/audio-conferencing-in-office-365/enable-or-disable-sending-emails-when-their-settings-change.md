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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '了解 Skype 在 pin 或默认会议数等设置发生更改时如何启用或禁用向用户发送的电子邮件。 '
ms.openlocfilehash: f6596e3e5c52dd82f4f61ad176ae4d656a5f146c
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237318"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a><span data-ttu-id="77572-103">Skype for Business Online 中的音频会议设置更改时启用或禁用发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="77572-103">Enable or disable sending emails when Audio Conferencing settings change in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> <span data-ttu-id="77572-104">如果您想要启用或禁用中的 Microsoft 团队发送电子邮件，请参阅 [Microsoft Teams 中的音频会议设置发生更改时启用或禁用发送电子邮件](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="77572-104">If you want to enable or disable sending emails in Microsoft Teams, see [Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="77572-105">要在 Microsoft Teams 中启用或禁用发送电子邮件，请参阅 Microsoft Teams 音频会议设置发生更改时启用或禁用发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="77572-105">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="77572-106">但是，有时可能需要减少发送给用户的电子邮件Skype for Business数量。</span><span class="sxs-lookup"><span data-stu-id="77572-106">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business users.</span></span> <span data-ttu-id="77572-107">在这种情况下，您可以禁用发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="77572-107">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="77572-108">如果禁用发送电子邮件，音频会议电子邮件不会发送给用户，包括为音频会议启用或禁用用户、重置其 PIN 的时间以及会议 ID 和默认会议电话号码更改时的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="77572-108">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="77572-109">下面是为用户启用音频会议时发送给用户的电子邮件示例：</span><span class="sxs-lookup"><span data-stu-id="77572-109">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![音频会议电子邮件](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="77572-111">什么时候向用户发送电子邮件？</span><span class="sxs-lookup"><span data-stu-id="77572-111">When are emails being sent to your users?</span></span>

- <span data-ttu-id="77572-112">启用音频会议后，会向贵组织的用户发送多封电子邮件：</span><span class="sxs-lookup"><span data-stu-id="77572-112">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="77572-113">向其分配 **音频会议** 许可证时。</span><span class="sxs-lookup"><span data-stu-id="77572-113">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="77572-114">手动重置用户的音频会议 PIN 时。</span><span class="sxs-lookup"><span data-stu-id="77572-114">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="77572-115">当你手动重置用户的会议 ID 时。</span><span class="sxs-lookup"><span data-stu-id="77572-115">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="77572-116">删除其 **音频会议** 许可证时。</span><span class="sxs-lookup"><span data-stu-id="77572-116">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="77572-117">当用户的音频会议提供商从 Microsoft 更改为其他提供商或"无 **"时**。</span><span class="sxs-lookup"><span data-stu-id="77572-117">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="77572-118">当用户的音频会议提供商更改为 Microsoft 时。</span><span class="sxs-lookup"><span data-stu-id="77572-118">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="77572-119">启用或禁用向用户发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="77572-119">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="77572-120">可以使用管理Skype for Business或Windows PowerShell来启用或禁用发送给用户的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="77572-120">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>

 
<span data-ttu-id="77572-121">![显示 Skype for Business 徽标的图标](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**</span><span class="sxs-lookup"><span data-stu-id="77572-121">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="77572-122">在 Skype for Business **管理中心的** 左侧导航中，单击"**音频会议"。**</span><span class="sxs-lookup"><span data-stu-id="77572-122">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="77572-123">在 **Microsoft 网桥的设置** 页上，选中或清除 **自动向用户发送电子邮件，如果他们的音频会议设置更改**　。</span><span class="sxs-lookup"><span data-stu-id="77572-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="77572-124">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="77572-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="77572-125">你也可以通过电子邮件向用户发送音频会议的设置， 方法是转到 **音频会议** > **用户**，选择用户，并单击 **通过电子邮件发送会议信息**。</span><span class="sxs-lookup"><span data-stu-id="77572-125">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="77572-126">如果这样做，将发送一封电子邮件，其中仅包括会议 ID 和会议电话号码，但不包括 PIN。</span><span class="sxs-lookup"><span data-stu-id="77572-126">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="77572-127">有关详细信息 [，请参阅向用户发送包含其音频会议信息](send-an-email-to-a-user-with-their-dial-in-information.md) 的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="77572-127">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="77572-128">**使用Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="77572-128">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="77572-129">运行以下代码以禁用发送电子邮件：</span><span class="sxs-lookup"><span data-stu-id="77572-129">Run the following to disable sending emails:</span></span> 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="77572-130"> 要获取此 cmdlet 的帮助，请参阅 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings)。</span><span class="sxs-lookup"><span data-stu-id="77572-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="77572-131">你还需了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="77572-131">What else should you know?</span></span>

- <span data-ttu-id="77572-132">禁用自动电子邮件后，仍可以使用会议管理中心手动触发Skype for Business会议 ID 和电话号码的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="77572-132">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="77572-133">但是，如果这样做，不会包含 PIN。</span><span class="sxs-lookup"><span data-stu-id="77572-133">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="77572-134">如果要重置音频会议 PIN 并禁用发送电子邮件，则需要以其他方式将其发送给用户。</span><span class="sxs-lookup"><span data-stu-id="77572-134">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="77572-135">可以使用 Skype for Business 管理中心或 Windows PowerShell 禁用向用户发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="77572-135">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="77572-136">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="77572-136">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="77572-137">可以使用这些 cmdlet 来节省时间或自动执行此操作。</span><span class="sxs-lookup"><span data-stu-id="77572-137">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="77572-138">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="77572-138">Get-CsOnlineDialInConferencingTenantSettings</span></span>](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
  - [<span data-ttu-id="77572-139">Remove-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="77572-139">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](/powershell/module/skype/Remove-CsOnlineDialInConferencingTenantSettings)
    
  - [<span data-ttu-id="77572-140">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="77572-140">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](/powershell/module/skype/Get-CsOnlineDialinConferencingTenantConfiguration)
    
  - [<span data-ttu-id="77572-141">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="77572-141">Get-CsOnlineDialInConferencingTenantSettings</span></span>](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
- <span data-ttu-id="77572-142">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="77572-142">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="77572-143">使用Windows PowerShell，可以使用Microsoft 365管理Office 365管理点，在有多个任务需要执行时简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="77572-143">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="77572-144">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="77572-144">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="77572-145">为何需要将 Microsoft 365 或 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="77572-145">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="77572-146">[使用 Microsoft 365 Office 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="77572-146">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="77572-147">Windows PowerShell比仅使用 Microsoft 365 管理中心在速度、简单性和工作效率方面具有许多优势，例如，一次对多个用户进行设置更改时。</span><span class="sxs-lookup"><span data-stu-id="77572-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="77572-148">请在以下主题中了解这些优点：</span><span class="sxs-lookup"><span data-stu-id="77572-148">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="77572-149">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="77572-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="77572-150">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="77572-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="77572-151">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="77572-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="77572-p106">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="77572-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="77572-154">相关主题</span><span class="sxs-lookup"><span data-stu-id="77572-154">Related topics</span></span>

[<span data-ttu-id="77572-155">当用户的音频会议设置更改时发送给用户的电子邮件</span><span class="sxs-lookup"><span data-stu-id="77572-155">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="77572-156">对其音频会议信息的用户发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="77572-156">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)
