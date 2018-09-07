---
title: 在 Skype for Business Online 中设置音频会议的 PIN 长度
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
description: 了解 PIN 的长度和要求的参数，并参阅如何在 Skype for Business 中设置会议的长度。
ms.openlocfilehash: 0714a55add1d3a4840d5868d0e09f0a3dc4b8561
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23861720"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a><span data-ttu-id="6251f-103">在 Skype for Business Online 中设置音频会议的 PIN 长度</span><span class="sxs-lookup"><span data-stu-id="6251f-103">Set the PIN length for Audio Conferencing meetings in Skype for Business Online</span></span>


> [!NOTE]
> <span data-ttu-id="6251f-104">有关在 Microsoft Teams 中设置 PIN 长度的信息，请参阅[在 Microsoft Teams 中设置音频会议的 PIN 长度](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="6251f-104">For information about setting the PIN length in Microsoft Teams, see [Set the PIN length for Audio Conferencing meetings in Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).</span></span>

<span data-ttu-id="6251f-105">为 Skype for Business 设置音频会议时，你将看到音频会议网桥。</span><span class="sxs-lookup"><span data-stu-id="6251f-105">When you are setting up audio conferencing for Skype for Business, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="6251f-106">会议网桥可以包含一个或多个电话号码。</span><span class="sxs-lookup"><span data-stu-id="6251f-106">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="6251f-107">你设置的电话号码将包括在 Skype for Business 应用的会议邀请中。</span><span class="sxs-lookup"><span data-stu-id="6251f-107">The phone number you set will be included on the meeting invites for the Skype for Business app.</span></span>
  
<span data-ttu-id="6251f-108">音频会议网桥负责应答使用电话拨入会议的人员的呼叫。</span><span class="sxs-lookup"><span data-stu-id="6251f-108">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="6251f-109">它通过来自自动助理的语音提示应答呼叫者，然后根据你的设置，会议网桥可以播放通知并让呼叫者录制其姓名。</span><span class="sxs-lookup"><span data-stu-id="6251f-109">It answers the caller with voice prompts from a system auto attendant and then depending on your settings can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="6251f-110">**Microsoft 桥接设置**允许你更改会议通知和会议加入体验的设置，并设置会议组织者使用的 PIN 的长度。</span><span class="sxs-lookup"><span data-stu-id="6251f-110">Skype for Business Online Microsoft bridge settings allows you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="6251f-111">如果会议组织者无法使用 Skype for Business 应用加入会议，则会使用 PIN 来启动会议。</span><span class="sxs-lookup"><span data-stu-id="6251f-111">Meeting organizers use PINs to start meetings if they can't join the meeting using the Skype for Business app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="6251f-112">设置 PIN 长度</span><span class="sxs-lookup"><span data-stu-id="6251f-112">Setting the PIN length</span></span>
 
1. <span data-ttu-id="6251f-113">在 **Skype for Business 管理中心**中的左侧导航中，转到**音频会议** > **Microsoft 桥接设置**。</span><span class="sxs-lookup"><span data-stu-id="6251f-113">In the **Skype for Business admin center**, in the left navigation go to **Dial-in conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="6251f-114">在**安全**下 > **PIN 长度**，选择你想要的 PIN 的位数，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="6251f-114">Under **Security** > **PIN length** > enter the number of digits you want for the PIN and then click **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6251f-p103">[!注释] PIN 与会议 ID 不同。 会议 ID 由呼叫者在加入会议时使用。 它们用于标识会议。 PIN 用于对作为会议组织者的呼叫者进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="6251f-p103">A PIN is different from a conference ID. Conference IDs are used by callers when they join the meeting. They are used to identify the meeting. The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="6251f-119">需要了解有关 PIN 设置的更多信息？</span><span class="sxs-lookup"><span data-stu-id="6251f-119">Want to more about PIN settings?</span></span>

- <span data-ttu-id="6251f-120">PIN 可以包含 4 至 12 个数字，默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="6251f-120">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="6251f-121">在创建 PIN 时只能使用数字。</span><span class="sxs-lookup"><span data-stu-id="6251f-121">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="6251f-122">不能使用字母和特殊字符。</span><span class="sxs-lookup"><span data-stu-id="6251f-122">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="6251f-123">只有当 Skype for Business 用户尚未启动会议时，会议组织者才需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="6251f-123">A PIN is only required for the meeting organizer when a Skype for Business client user hasn't already started the meeting.</span></span> <span data-ttu-id="6251f-124">如果每个人都是拨号进入会议，则会议组织者需要 PIN 才能启动会议。</span><span class="sxs-lookup"><span data-stu-id="6251f-124">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="6251f-p106">PIN 安全设置适用于与 Microsoft 网桥相关联的所有电话号码。它们将应用于使用与给定网桥相关联的电话号码的所有会议。</span><span class="sxs-lookup"><span data-stu-id="6251f-p106">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge. They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="6251f-127">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="6251f-127">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="6251f-128">为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6251f-128">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
- <span data-ttu-id="6251f-129">若要将 PIN 的数字位数设置为 8：  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span><span class="sxs-lookup"><span data-stu-id="6251f-129">To set the number of digits in the PIN to 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span></span>
    
- <span data-ttu-id="6251f-p107">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="6251f-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="6251f-133">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="6251f-133">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="6251f-134">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="6251f-134">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="6251f-135">Windows PowerShell 在速度、简单性和生产率方面有许多优点，仅限于使用 Office 365 管理中心，例如当您同时为许多用户进行设置更改时。</span><span class="sxs-lookup"><span data-stu-id="6251f-135">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="6251f-136">请在以下主题中了解这些优点：</span><span class="sxs-lookup"><span data-stu-id="6251f-136">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="6251f-137">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="6251f-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="6251f-138">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6251f-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [<span data-ttu-id="6251f-139">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6251f-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="6251f-140">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="6251f-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="6251f-p109">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="6251f-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6251f-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6251f-143">See also</span></span>

[<span data-ttu-id="6251f-144">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="6251f-144">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
