---
title: 更改音频会议网桥的设置
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: 更改音频会议网桥设置，包括进入和退出通知、播放姓名或电话号码、音调，以及提示呼叫者录制其姓名。
ms.openlocfilehash: 7609ac7639012eb29d6d6cab4b482c1502d27c51
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102638"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="fd0a6-103">更改音频会议网桥的设置</span><span class="sxs-lookup"><span data-stu-id="fd0a6-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="fd0a6-104">在 Microsoft 365 或 Office 365 中设置音频会议时，你将收到来自音频会议网桥的用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="fd0a6-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="fd0a6-105">会议网桥可以包含一个或多个电话号码。</span><span class="sxs-lookup"><span data-stu-id="fd0a6-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="fd0a6-106">呼叫者拨入会议时，将使用这些电话号码。</span><span class="sxs-lookup"><span data-stu-id="fd0a6-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="fd0a6-107">电话号码包含在 Skype for Business 或 Microsoft Teams 会议邀请的底部。</span><span class="sxs-lookup"><span data-stu-id="fd0a6-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="fd0a6-108">会议网桥应答呼叫，然后使用会议自动助理通过语音提示提示呼叫者，然后根据你的设置，它可以播放通知、让呼叫者录制其姓名并控制 PIN 设置。</span><span class="sxs-lookup"><span data-stu-id="fd0a6-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="fd0a6-109">PIN 被赋予会议组织者，以允许他们在没有使用 Skype for Business 或 Microsoft Teams 应用时启动会议。</span><span class="sxs-lookup"><span data-stu-id="fd0a6-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="fd0a6-110">只有当 Skype for Business 或 Microsoft Teams 应用用户尚未启动会议时，会议组织者才需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="fd0a6-110">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting.</span></span> <span data-ttu-id="fd0a6-111">如果每个人都拨入会议，会议组织者需要 PIN 才能启动会议。</span><span class="sxs-lookup"><span data-stu-id="fd0a6-111">If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) <span data-ttu-id="fd0a6-113">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="fd0a6-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="fd0a6-114">在左侧导航栏中，转到"**会议**  >  **会议网桥"。**</span><span class="sxs-lookup"><span data-stu-id="fd0a6-114">In the left navigation, go to **Meetings** > **Conference bridges**.</span></span> 

2. <span data-ttu-id="fd0a6-115">在"会议网桥"**页面顶部**，单击"**网桥设置"。**</span><span class="sxs-lookup"><span data-stu-id="fd0a6-115">At the top of the **Conference bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="fd0a6-116">在" **桥设置"** 窗格中，选择：</span><span class="sxs-lookup"><span data-stu-id="fd0a6-116">In the **Bridge settings** pane, select:</span></span> 
   - <span data-ttu-id="fd0a6-117">**会议进入和退出通知** 如果关闭此功能，则当某人进入或离开会议时，已加入会议的用户不会收到通知。</span><span class="sxs-lookup"><span data-stu-id="fd0a6-117">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
     <span data-ttu-id="fd0a6-118">打开"会议进入和 **退出通知"** 时，可以选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="fd0a6-118">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
   - <span data-ttu-id="fd0a6-119">**姓名或电话号码** 当用户拨入会议时，当他们加入会议时，将播放其电话号码。</span><span class="sxs-lookup"><span data-stu-id="fd0a6-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="fd0a6-120">**音调** 当用户拨入会议时，当他们加入会议时将播放音频音。</span><span class="sxs-lookup"><span data-stu-id="fd0a6-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
   - <span data-ttu-id="fd0a6-121">**要求呼叫者在加入会议之前录制其姓名** 如果关闭此功能，呼叫者在加入会议之前不会要求他们录制其姓名。</span><span class="sxs-lookup"><span data-stu-id="fd0a6-121">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="fd0a6-122">若要设置会议的 PIN 长度，请在"PIN 长度"列表中选择 PIN **的位数** 。</span><span class="sxs-lookup"><span data-stu-id="fd0a6-122">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="fd0a6-123">若要指定是否向用户发送电子邮件，请启用或禁用"如果用户的音频会议配置发生更改时自动 **向用户发送电子邮件"。**</span><span class="sxs-lookup"><span data-stu-id="fd0a6-123">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="fd0a6-124">有关详细信息 [，请参阅](emails-sent-to-users-when-their-settings-change-in-teams.md) 当用户的音频会议设置在 Microsoft Teams 中更改时自动向用户发送的电子邮件或当用户在 [Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) 中的设置更改时发送给用户的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="fd0a6-124">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
 
6. <span data-ttu-id="fd0a6-125">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="fd0a6-125">Click **Save**.</span></span> 

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="fd0a6-126">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="fd0a6-126">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="fd0a6-127">若要节省时间或自动执行此过程，可以使用 [Set-CsDialinConferencingBridge](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fd0a6-127">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge) cmdlet.</span></span>
    
- <span data-ttu-id="fd0a6-128">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="fd0a6-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="fd0a6-129">使用Windows PowerShell，您可以使用单点管理来管理 Microsoft 365 或 Office 365，当您有多个任务需要执行时，可以简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="fd0a6-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="fd0a6-130">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="fd0a6-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="fd0a6-131">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd0a6-131">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="fd0a6-132">[使用 Office 365 管理 Microsoft 365 或 Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="fd0a6-132">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="fd0a6-133">Windows PowerShell比仅使用 Microsoft 365 管理中心具有许多速度、简单性和工作效率优势，例如，一次对多个用户进行设置更改时。</span><span class="sxs-lookup"><span data-stu-id="fd0a6-133">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="fd0a6-134">请在以下主题中了解这些优点：</span><span class="sxs-lookup"><span data-stu-id="fd0a6-134">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="fd0a6-135">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="fd0a6-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [<span data-ttu-id="fd0a6-136">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="fd0a6-136">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [<span data-ttu-id="fd0a6-137">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="fd0a6-137">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > <span data-ttu-id="fd0a6-p107">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="fd0a6-p107">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="fd0a6-140">相关主题</span><span class="sxs-lookup"><span data-stu-id="fd0a6-140">Related topics</span></span>

[<span data-ttu-id="fd0a6-141">设置 Microsoft Teams 的音频会议</span><span class="sxs-lookup"><span data-stu-id="fd0a6-141">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

[<span data-ttu-id="fd0a6-142">为 Skype for Business Online 设置音频会议</span><span class="sxs-lookup"><span data-stu-id="fd0a6-142">Set up Audio Conferencing for Skype for Business Online</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)