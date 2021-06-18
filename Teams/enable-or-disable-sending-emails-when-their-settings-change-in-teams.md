---
title: 音频会议设置更改时的电子邮件选项
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: '了解如何启用或禁用Skype固定更改或会议号码更改等设置时向用户发送电子邮件Microsoft Teams。 '
ms.openlocfilehash: 17c2864703eafa2c70709da0381f870abba58ad0
ms.sourcegitcommit: 8c2093f7a048a9a56b36e4a3b4c48ae1206c52f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2021
ms.locfileid: "53004164"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a><span data-ttu-id="773df-103">在 Microsoft Teams 中启用或禁用在音频会议设置更改时发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="773df-103">Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams</span></span>

<span data-ttu-id="773df-104">要在 Microsoft Teams 中启用或禁用发送电子邮件，请参阅 Microsoft Teams 音频会议设置发生更改时启用或禁用发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="773df-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="773df-105">但是，有时可能需要减少发送给用户的电子邮件Microsoft Teams数量。</span><span class="sxs-lookup"><span data-stu-id="773df-105">There may be times, however, when you want to reduce the number of emails that are sent to Microsoft Teams users.</span></span> <span data-ttu-id="773df-106">在这种情况下，您可以禁用发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="773df-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="773df-107">如果禁用发送电子邮件，音频会议电子邮件不会发送给用户，包括为音频会议启用或禁用用户、重置其 PIN 的时间以及会议 ID 和默认会议电话号码更改时的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="773df-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="773df-108">下面是为用户启用音频会议时发送给用户的电子邮件示例：</span><span class="sxs-lookup"><span data-stu-id="773df-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![音频会议电子邮件的示例](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="773df-110">什么时候向用户发送电子邮件？</span><span class="sxs-lookup"><span data-stu-id="773df-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="773df-111">启用音频会议后，会向贵组织的用户发送多封电子邮件：</span><span class="sxs-lookup"><span data-stu-id="773df-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="773df-112">向其分配 **音频会议** 许可证时。</span><span class="sxs-lookup"><span data-stu-id="773df-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="773df-113">手动重置用户的音频会议 PIN 时。</span><span class="sxs-lookup"><span data-stu-id="773df-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="773df-114">当你手动重置用户的会议 ID 时。</span><span class="sxs-lookup"><span data-stu-id="773df-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="773df-115">删除其 **音频会议** 许可证时。</span><span class="sxs-lookup"><span data-stu-id="773df-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="773df-116">当用户的音频会议提供商从 Microsoft 更改为其他提供商或"无 **"时**。</span><span class="sxs-lookup"><span data-stu-id="773df-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="773df-117">当用户的音频会议提供商更改为 Microsoft 时。</span><span class="sxs-lookup"><span data-stu-id="773df-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="773df-118">启用或禁用向用户发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="773df-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="773df-119">可以使用 Microsoft Teams 或 Windows PowerShell 来启用或禁用发送给用户的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="773df-119">You can use Microsoft Teams or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="773df-120">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="773df-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="773df-121">在左侧导航中，转到“**会议**” > “**会议网桥**”。</span><span class="sxs-lookup"><span data-stu-id="773df-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="773df-122">在"会议网桥"**页面顶部**，单击"**网桥设置"。**</span><span class="sxs-lookup"><span data-stu-id="773df-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="773df-123">在"**网桥设置"** 窗格中，启用或禁用"如果用户的拨入 **设置更改时自动发送电子邮件"。**</span><span class="sxs-lookup"><span data-stu-id="773df-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="773df-124">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="773df-124">Click **Save**.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="773df-125">**使用Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="773df-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="773df-126">也可使用 PowerShell Microsoft Teams并运行：</span><span class="sxs-lookup"><span data-stu-id="773df-126">You can also use the Microsoft Teams PowerShell module and run:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

<span data-ttu-id="773df-127">可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) 管理组织的其他设置，包括电子邮件。</span><span class="sxs-lookup"><span data-stu-id="773df-127">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) to manage other settings for your organization, including email.</span></span>

<span data-ttu-id="773df-128">有关详细信息[，Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps)参考。</span><span class="sxs-lookup"><span data-stu-id="773df-128">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>

    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="773df-129">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="773df-129">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="773df-130">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="773df-130">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="773df-131">使用Windows PowerShell，可以使用Microsoft 365管理Office 365管理点，在有多个任务需要执行时简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="773df-131">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="773df-132">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="773df-132">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="773df-133">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="773df-133">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="773df-134">[使用 Windows PowerShell 管理 Office 365 的最佳方式](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="773df-134">[Best ways to manage Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="773df-135">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="773df-135">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="773df-136">相关主题</span><span class="sxs-lookup"><span data-stu-id="773df-136">Related topics</span></span>

[<span data-ttu-id="773df-137">当用户的音频会议设置更改时发送给用户的电子邮件</span><span class="sxs-lookup"><span data-stu-id="773df-137">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change-in-teams.md)

[<span data-ttu-id="773df-138">对其音频会议信息的用户发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="773df-138">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
