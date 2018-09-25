---
title: 在 Microsoft Teams 中启用或禁用在音频会议设置更改时发送电子邮件
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
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解如何在 Microsoft Teams 中启用或禁用 Skype 在 PIN 等设置更改或默认会议号码更改时向用户发送电子邮件。 '
ms.openlocfilehash: 2c082410f7acf000473e001f46587025edd6e9c7
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25015538"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a><span data-ttu-id="ec049-103">在 Microsoft Teams 中启用或禁用在音频会议设置更改时发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="ec049-103">Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams</span></span>

<span data-ttu-id="ec049-104">|||UNTRANSLATED_CONTENT_START|||Users are automatically notified by email when they are enabled for Audio Conferencing.|||UNTRANSLATED_CONTENT_END|||</span><span class="sxs-lookup"><span data-stu-id="ec049-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="ec049-105">有时可能，但是，当您想要减少发送给 Microsoft 团队用户的电子邮件数。</span><span class="sxs-lookup"><span data-stu-id="ec049-105">There may be times, however, when you want to reduce the number of emails that are sent to Microsoft Teams users.</span></span> <span data-ttu-id="ec049-106">在这种情况下，您可以禁用发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ec049-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="ec049-107">如果禁用发送电子邮件，则不会向用户发送音频会议电子邮件，包括以下情况的电子邮件：为用户启用或禁用了音频会议时、重置其 PIN 时以及当会议 ID 和默认会议电话号码更改时。</span><span class="sxs-lookup"><span data-stu-id="ec049-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="ec049-108">下面是为用户启用了音频会议时向用户发送的电子邮件示例：</span><span class="sxs-lookup"><span data-stu-id="ec049-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![音频会议电子邮件](media/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="ec049-110">什么时候向用户发送电子邮件？</span><span class="sxs-lookup"><span data-stu-id="ec049-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="ec049-111">在为贵组织中的用户启用了音频会议后，会向他们发送多封电子邮件：</span><span class="sxs-lookup"><span data-stu-id="ec049-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="ec049-112">向其分配**音频会议**许可证时。</span><span class="sxs-lookup"><span data-stu-id="ec049-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="ec049-113">当你手动重置用户的音频会议 PIN 时。</span><span class="sxs-lookup"><span data-stu-id="ec049-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="ec049-114">当你手动重置用户的会议 ID 时。</span><span class="sxs-lookup"><span data-stu-id="ec049-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="ec049-115">删除其**音频会议**许可证时。</span><span class="sxs-lookup"><span data-stu-id="ec049-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="ec049-116">当用户的音频会议提供商从 Microsoft 更改为另一个提供商或“**无**”时。</span><span class="sxs-lookup"><span data-stu-id="ec049-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="ec049-117">当用户的音频会议提供商更改为 Microsoft 时。</span><span class="sxs-lookup"><span data-stu-id="ec049-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="ec049-118">启用或禁用向用户发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="ec049-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="ec049-119">你可以使用 Microsoft Teams 或 Windows PowerShell 启用或禁用向用户发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ec049-119">You can use Microsoft Teams or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="ec049-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **使用 Microsoft Teams 和 Skype for Business 管理中心：**</span><span class="sxs-lookup"><span data-stu-id="ec049-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>
1. <span data-ttu-id="ec049-121">在左侧导航中，转到“**会议**” > “**会议网桥**”。</span><span class="sxs-lookup"><span data-stu-id="ec049-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="ec049-122">在“**会议网桥**”页面顶部，单击“**网桥设置**”。</span><span class="sxs-lookup"><span data-stu-id="ec049-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="ec049-123">在“**网桥设置**”窗格中，启用或禁用“**当用户的拨入设置更改时自动向用户发送电子邮件**”。</span><span class="sxs-lookup"><span data-stu-id="ec049-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="ec049-124">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="ec049-124">Click **Save**.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="ec049-125">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ec049-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="ec049-126">有关详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。</span><span class="sxs-lookup"><span data-stu-id="ec049-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="ec049-127">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="ec049-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="ec049-p102">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="ec049-p102">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ec049-131">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ec049-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="ec049-132">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="ec049-132">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="ec049-133">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="ec049-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="ec049-134">相关主题</span><span class="sxs-lookup"><span data-stu-id="ec049-134">Related topics</span></span>

[<span data-ttu-id="ec049-135">用户的音频会议设置更改时向其发送的电子邮件</span><span class="sxs-lookup"><span data-stu-id="ec049-135">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change-in-teams.md)

[<span data-ttu-id="ec049-136">向用户发送包含其音频会议信息的电子邮件</span><span class="sxs-lookup"><span data-stu-id="ec049-136">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


