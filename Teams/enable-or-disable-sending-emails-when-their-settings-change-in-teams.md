---
title: 启用或禁用发送电子邮件中的 Microsoft 团队的音频会议设置更改时
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
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解如何启用或禁用 Skype 向用户设置 pin 如发生更改时或 Microsoft 团队中的默认会议号码更改发送电子邮件。 '
ms.openlocfilehash: a59553f26ee39e042fa28d9e58e7f5ae2aae21be
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23892499"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a><span data-ttu-id="60c84-103">启用或禁用发送电子邮件中的 Microsoft 团队的音频会议设置更改时</span><span class="sxs-lookup"><span data-stu-id="60c84-103">Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams</span></span>

<span data-ttu-id="60c84-104">|||UNTRANSLATED_CONTENT_START|||Users are automatically notified by email when they are enabled for Audio Conferencing.|||UNTRANSLATED_CONTENT_END|||</span><span class="sxs-lookup"><span data-stu-id="60c84-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="60c84-105">有时可能，但是，当您想要减少发送给 Microsoft 团队用户的电子邮件数。</span><span class="sxs-lookup"><span data-stu-id="60c84-105">There may be times, however, when you want to reduce the number of emails that are sent to Microsoft Teams users.</span></span> <span data-ttu-id="60c84-106">在这种情况下，您可以禁用发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="60c84-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="60c84-107">如果您禁用发送电子邮件，就不会音频会议电子邮件发送给用户，当用户处于启用或禁用音频会议以及会议 ID 和默认会议电话号码的更改时重置其 PIN，包括电子邮件.</span><span class="sxs-lookup"><span data-stu-id="60c84-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="60c84-108">下面是他们启用音频会议时，向用户发送的电子邮件的示例：</span><span class="sxs-lookup"><span data-stu-id="60c84-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![音频会议电子邮件](media/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="60c84-110">什么时候向用户发送电子邮件？</span><span class="sxs-lookup"><span data-stu-id="60c84-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="60c84-111">有多个电子邮件发送给组织中的用户启用了后为音频会议：</span><span class="sxs-lookup"><span data-stu-id="60c84-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="60c84-112">向其分配**音频会议**许可证时。</span><span class="sxs-lookup"><span data-stu-id="60c84-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="60c84-113">当您手动重置用户的音频会议 PIN。</span><span class="sxs-lookup"><span data-stu-id="60c84-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="60c84-114">当你手动重置用户的会议 ID 时。</span><span class="sxs-lookup"><span data-stu-id="60c84-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="60c84-115">删除其**音频会议**许可证时。</span><span class="sxs-lookup"><span data-stu-id="60c84-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="60c84-116">当用户的音频会议提供商从 Microsoft 更改为其他提供程序或**无**。</span><span class="sxs-lookup"><span data-stu-id="60c84-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="60c84-117">向 Microsoft 更改时用户的音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="60c84-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="60c84-118">启用或禁用从发送给用户的电子邮件</span><span class="sxs-lookup"><span data-stu-id="60c84-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="60c84-119">您可以使用的 Microsoft 团队或 Windows PowerShell 启用或禁用电子邮件发送给用户。</span><span class="sxs-lookup"><span data-stu-id="60c84-119">You can use Microsoft Teams or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="60c84-120">![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="60c84-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>
1. <span data-ttu-id="60c84-121">在左侧导航窗格中，转到**会议** > **会议桥**。</span><span class="sxs-lookup"><span data-stu-id="60c84-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="60c84-122">在**会议桥**页的顶部，单击**网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="60c84-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="60c84-123">在**桥设置**窗格中，启用或禁用**自动发送电子邮件发送给用户，如果其电话拨入式设置更改**。</span><span class="sxs-lookup"><span data-stu-id="60c84-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="60c84-124">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="60c84-124">Click **Save**.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="60c84-125">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="60c84-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="60c84-126">请参阅[Microsoft 团队 PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)（英文） 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="60c84-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="60c84-127">要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="60c84-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="60c84-p102">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="60c84-p102">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="60c84-131">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="60c84-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="60c84-132">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="60c84-132">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="60c84-133">有关 Windows PowerShell 的详细信息，请参阅[Microsoft 团队 PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)（英文） 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="60c84-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="60c84-134">相关主题</span><span class="sxs-lookup"><span data-stu-id="60c84-134">Related topics</span></span>

[<span data-ttu-id="60c84-135">其音频会议设置更改时向用户发送的电子邮件</span><span class="sxs-lookup"><span data-stu-id="60c84-135">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change-in-teams.md)

[<span data-ttu-id="60c84-136">对其音频会议信息的用户发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="60c84-136">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


