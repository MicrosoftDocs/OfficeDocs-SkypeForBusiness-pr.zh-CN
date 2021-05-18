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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 了解 PIN 的长度和要求的参数，并参阅如何在 Skype for Business 中设置会议的长度。
ms.openlocfilehash: 2e4e1d087ad6e0f91d034c6a5abe513e8b3aab01
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238597"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a><span data-ttu-id="5b600-103">在 Skype for Business Online 中设置音频会议的 PIN 长度</span><span class="sxs-lookup"><span data-stu-id="5b600-103">Set the PIN length for Audio Conferencing meetings in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


> [!NOTE]
> <span data-ttu-id="5b600-104">有关在 Microsoft Teams 中设置 PIN 长度的信息，请参阅[在 Microsoft Teams 中设置音频会议的 PIN 长度](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="5b600-104">For information about setting the PIN length in Microsoft Teams, see [Set the PIN length for Audio Conferencing meetings in Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).</span></span>

<span data-ttu-id="5b600-105">为 Skype for Business 设置音频会议时，你将看到音频会议网桥。</span><span class="sxs-lookup"><span data-stu-id="5b600-105">When you are setting up audio conferencing for Skype for Business, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="5b600-106">会议网桥可以包含一个或多个电话号码。</span><span class="sxs-lookup"><span data-stu-id="5b600-106">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="5b600-107">你设置的电话号码将包括在 Skype for Business 应用的会议邀请中。</span><span class="sxs-lookup"><span data-stu-id="5b600-107">The phone number you set will be included on the meeting invites for the Skype for Business app.</span></span>
  
<span data-ttu-id="5b600-108">音频会议网桥负责应答使用电话拨入会议的用户的呼叫。</span><span class="sxs-lookup"><span data-stu-id="5b600-108">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="5b600-109">它通过自动助理的语音提示应答呼叫者，然后根据你的设置，可以播放通知并要求呼叫者录制其姓名。</span><span class="sxs-lookup"><span data-stu-id="5b600-109">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="5b600-110">**Microsoft 网桥** 设置允许您更改会议通知和会议加入体验的设置，并设置会议组织者使用的 PIN 的长度。</span><span class="sxs-lookup"><span data-stu-id="5b600-110">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="5b600-111">如果会议组织者无法使用 Skype for Business 应用加入会议，则会使用 PIN 来启动会议。</span><span class="sxs-lookup"><span data-stu-id="5b600-111">Meeting organizers use PINs to start meetings if they can't join the meeting using the Skype for Business app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="5b600-112">设置 PIN 长度</span><span class="sxs-lookup"><span data-stu-id="5b600-112">Setting the PIN length</span></span>
 
1. <span data-ttu-id="5b600-113">在 **Skype for Business管理** 中心的 左侧导航中，转到"**音频会议**  >  **Microsoft 网桥设置"。**</span><span class="sxs-lookup"><span data-stu-id="5b600-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="5b600-114">在 **"安全** PIN 长度"下，选择 PIN 的位数，然后单击  >  "保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="5b600-114">Under **Security** > **PIN length**, select the number of digits you want for the PIN, and then click **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5b600-p103">[!注释] PIN 与会议 ID 不同。 会议 ID 由呼叫者在加入会议时使用。 它们用于标识会议。 PIN 用于对作为会议组织者的呼叫者进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="5b600-p103">A PIN is different from a conference ID. Conference IDs are used by callers when they join the meeting. They are used to identify the meeting. The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="5b600-119">想要了解有关 PIN 设置的信息？</span><span class="sxs-lookup"><span data-stu-id="5b600-119">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="5b600-120">PIN 可以是 4 到 12 个数字;默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="5b600-120">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="5b600-121">在创建 PIN 时只能使用数字。</span><span class="sxs-lookup"><span data-stu-id="5b600-121">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="5b600-122">不能使用字母和特殊字符。</span><span class="sxs-lookup"><span data-stu-id="5b600-122">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="5b600-123">只有当用户尚未启动会议时，Skype for Business才需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="5b600-123">A PIN is only required for the meeting organizer when a Skype for Business user hasn't already started the meeting.</span></span> <span data-ttu-id="5b600-124">如果每个人都是拨号进入会议，则会议组织者需要 PIN 才能启动会议。</span><span class="sxs-lookup"><span data-stu-id="5b600-124">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="5b600-p106">PIN 安全设置适用于与 Microsoft 网桥相关联的所有电话号码。它们将应用于使用与给定网桥相关联的电话号码的所有会议。</span><span class="sxs-lookup"><span data-stu-id="5b600-p106">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge. They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="5b600-127">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="5b600-127">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="5b600-128">为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5b600-128">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) cmdlet.</span></span>
    
- <span data-ttu-id="5b600-129">若要将 PIN 的数字位数设置为 8： `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span><span class="sxs-lookup"><span data-stu-id="5b600-129">To set the number of digits in the PIN to 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span></span>
    
- <span data-ttu-id="5b600-130">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="5b600-130">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="5b600-131">使用Windows PowerShell，可以使用Microsoft 365管理Office 365管理点，在有多个任务需要执行时简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="5b600-131">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="5b600-132">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="5b600-132">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5b600-133">为何需要将 Microsoft 365 或 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="5b600-133">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="5b600-134">[使用 Microsoft 365 Office 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="5b600-134">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="5b600-135">Windows PowerShell管理中心相比，Microsoft 365在速度、简单性和工作效率方面具有许多优势，例如，一次为许多用户更改设置时。</span><span class="sxs-lookup"><span data-stu-id="5b600-135">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="5b600-136">请在以下主题中了解这些优点：</span><span class="sxs-lookup"><span data-stu-id="5b600-136">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="5b600-137">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="5b600-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="5b600-138">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="5b600-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [<span data-ttu-id="5b600-139">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="5b600-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="5b600-140">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="5b600-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="5b600-p109">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="5b600-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5b600-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b600-143">See also</span></span>

[<span data-ttu-id="5b600-144">尝试或购买音频会议Microsoft 365或Office 365</span><span class="sxs-lookup"><span data-stu-id="5b600-144">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
