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
description: '了解如何在 Microsoft Teams 中启用或禁用 Skype 在 PIN 等设置更改或默认会议号码更改时向用户发送电子邮件。 '
ms.openlocfilehash: 36c7e9dce17de1e6f9bbf8b812d62ddd91bc6ffe
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691598"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a><span data-ttu-id="a6d92-103">在 Microsoft Teams 中启用或禁用在音频会议设置更改时发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="a6d92-103">Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams</span></span>

<span data-ttu-id="a6d92-104">为用户启用了音频会议时，会自动通过电子邮件向其发送通知。</span><span class="sxs-lookup"><span data-stu-id="a6d92-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="a6d92-105">但是，有时候你可能希望减少向 Microsoft Teams 用户发送的电子邮件数量。</span><span class="sxs-lookup"><span data-stu-id="a6d92-105">There may be times, however, when you want to reduce the number of emails that are sent to Microsoft Teams users.</span></span> <span data-ttu-id="a6d92-106">在这种情况下，你可以禁用发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a6d92-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="a6d92-107">如果禁用发送电子邮件，则不会向用户发送音频会议电子邮件，包括以下情况的电子邮件：为用户启用或禁用了音频会议时、重置其 PIN 时以及当会议 ID 和默认会议电话号码更改时。</span><span class="sxs-lookup"><span data-stu-id="a6d92-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="a6d92-108">下面是为用户启用了音频会议时向用户发送的电子邮件示例：</span><span class="sxs-lookup"><span data-stu-id="a6d92-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![音频会议电子邮件示例](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="a6d92-110">什么时候向用户发送电子邮件？</span><span class="sxs-lookup"><span data-stu-id="a6d92-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="a6d92-111">在为贵组织中的用户启用了音频会议后，会向他们发送多封电子邮件：</span><span class="sxs-lookup"><span data-stu-id="a6d92-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="a6d92-112">向其分配**音频会议**许可证时。</span><span class="sxs-lookup"><span data-stu-id="a6d92-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="a6d92-113">当你手动重置用户的音频会议 PIN 时。</span><span class="sxs-lookup"><span data-stu-id="a6d92-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="a6d92-114">当你手动重置用户的会议 ID 时。</span><span class="sxs-lookup"><span data-stu-id="a6d92-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="a6d92-115">删除其**音频会议**许可证时。</span><span class="sxs-lookup"><span data-stu-id="a6d92-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="a6d92-116">当用户的音频会议提供商从 Microsoft 更改为另一个提供商或“**无**”时。</span><span class="sxs-lookup"><span data-stu-id="a6d92-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="a6d92-117">当用户的音频会议提供商更改为 Microsoft 时。</span><span class="sxs-lookup"><span data-stu-id="a6d92-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="a6d92-118">启用或禁用向用户发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="a6d92-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="a6d92-119">你可以使用 Microsoft Teams 或 Windows PowerShell 启用或禁用向用户发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a6d92-119">You can use Microsoft Teams or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="a6d92-120">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="a6d92-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="a6d92-121">在左侧导航中，转到“**会议**” > “**会议网桥**”。</span><span class="sxs-lookup"><span data-stu-id="a6d92-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="a6d92-122">在“**会议网桥**”页面顶部，单击“**网桥设置**”。</span><span class="sxs-lookup"><span data-stu-id="a6d92-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="a6d92-123">在“**网桥设置**”窗格中，启用或禁用“**当用户的拨入设置更改时自动向用户发送电子邮件**”。</span><span class="sxs-lookup"><span data-stu-id="a6d92-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="a6d92-124">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a6d92-124">Click **Save**.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="a6d92-125">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a6d92-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="a6d92-126">有关详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。</span><span class="sxs-lookup"><span data-stu-id="a6d92-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="a6d92-127">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="a6d92-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="a6d92-p102">Windows PowerShell 全部用于管理用户以及允许或禁止用户执行的操作。使用 Windows PowerShell，你可以使用单一的管理点管理 Microsoft 365 或 Office 365，这可以在你有多个任务时简化日常工作。若要开始使用 Windows PowerShell，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="a6d92-p102">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="a6d92-131">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6d92-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="a6d92-132">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="a6d92-132">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="a6d92-133">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="a6d92-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="a6d92-134">相关主题</span><span class="sxs-lookup"><span data-stu-id="a6d92-134">Related topics</span></span>

[<span data-ttu-id="a6d92-135">用户的音频会议设置更改时向其发送的电子邮件</span><span class="sxs-lookup"><span data-stu-id="a6d92-135">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change-in-teams.md)

[<span data-ttu-id="a6d92-136">向用户发送包含其音频会议信息的电子邮件</span><span class="sxs-lookup"><span data-stu-id="a6d92-136">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


