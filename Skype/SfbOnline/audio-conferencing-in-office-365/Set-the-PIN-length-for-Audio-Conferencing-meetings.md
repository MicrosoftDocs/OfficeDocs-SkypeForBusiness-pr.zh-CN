---
title: 为业务 Online Skype 中设置对音频会议的 PIN 长度
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
description: Learn the parameters for the length and requirements of a PIN and see how to set the length for meetings in Skype for Business.
ms.openlocfilehash: 54ee8e70972a7033a9a759f8df37647ba5a2b700
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490562"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a><span data-ttu-id="bca8a-103">为业务 Online Skype 中设置对音频会议的 PIN 长度</span><span class="sxs-lookup"><span data-stu-id="bca8a-103">Set the PIN length for Audio Conferencing meetings in Skype for Business Online</span></span>


> [!NOTE]
> <span data-ttu-id="bca8a-104">有关设置 PIN 长度的 Microsoft 团队中的信息，请参阅[设置音频会议中的 Microsoft 团队的 PIN 长度](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="bca8a-104">For information about setting the PIN length in Microsoft Teams, see [Set the PIN length for Audio Conferencing meetings in Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).</span></span>

<span data-ttu-id="bca8a-105">当您要设置为 for Business 的 Skype 音频会议时，您将看到音频会议桥。</span><span class="sxs-lookup"><span data-stu-id="bca8a-105">When you are setting up audio conferencing for Skype for Business, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="bca8a-106">会议网桥可以包含一个或多个电话号码。</span><span class="sxs-lookup"><span data-stu-id="bca8a-106">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="bca8a-107">将在会议邀请的业务应用程序的 Skype 包括您设置的电话号码。</span><span class="sxs-lookup"><span data-stu-id="bca8a-107">The phone number you set will be included on the meeting invites for the Skype for Business app.</span></span>
  
<span data-ttu-id="bca8a-108">音频会议桥的会议使用电话拨入的人员接听电话。</span><span class="sxs-lookup"><span data-stu-id="bca8a-108">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="bca8a-109">其接听呼叫者使用语音提示从自动助理，然后，具体取决于您的设置，可以播放通知以及提出呼叫者在记录其姓名。</span><span class="sxs-lookup"><span data-stu-id="bca8a-109">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="bca8a-110">**Microsoft 桥设置**允许您更改会议通知的设置和会议加入体验，并设置由会议组织者 Pin 长度。</span><span class="sxs-lookup"><span data-stu-id="bca8a-110">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="bca8a-111">会议组织者使用 Pin 如果无法加入会议的企业应用程序使用 Skype 启动会议。</span><span class="sxs-lookup"><span data-stu-id="bca8a-111">Meeting organizers use PINs to start meetings if they can't join the meeting using the Skype for Business app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="bca8a-112">设置 PIN 长度</span><span class="sxs-lookup"><span data-stu-id="bca8a-112">Setting the PIN length</span></span>
 
1. <span data-ttu-id="bca8a-113">在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议** > **Microsoft 网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="bca8a-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="bca8a-114">在**安全**下 > **PIN 长度**，选择 PIN，所需的位数，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="bca8a-114">Under **Security** > **PIN length**, select the number of digits you want for the PIN, and then click **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="bca8a-p103">[!注释] PIN 与会议 ID 不同。 会议 ID 由呼叫者在加入会议时使用。 它们用于标识会议。 PIN 用于对作为会议组织者的呼叫者进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="bca8a-p103">A PIN is different from a conference ID. Conference IDs are used by callers when they join the meeting. They are used to identify the meeting. The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="bca8a-119">想知道 PIN 设置的详细信息吗？</span><span class="sxs-lookup"><span data-stu-id="bca8a-119">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="bca8a-120">旋转中心点到 12 个数字; 可以是从 4默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="bca8a-120">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="bca8a-121">在创建 PIN 时只能使用数字。</span><span class="sxs-lookup"><span data-stu-id="bca8a-121">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="bca8a-122">不能使用字母和特殊字符。</span><span class="sxs-lookup"><span data-stu-id="bca8a-122">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="bca8a-123">PIN 才所需的会议组织者时业务用户 Skype 不起作用已经启动会议。</span><span class="sxs-lookup"><span data-stu-id="bca8a-123">A PIN is only required for the meeting organizer when a Skype for Business user hasn't already started the meeting.</span></span> <span data-ttu-id="bca8a-124">如果每个人都是拨号进入会议，则会议组织者需要 PIN 才能启动会议。</span><span class="sxs-lookup"><span data-stu-id="bca8a-124">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="bca8a-p106">PIN 安全设置适用于与 Microsoft 网桥相关联的所有电话号码。它们将应用于使用与给定网桥相关联的电话号码的所有会议。</span><span class="sxs-lookup"><span data-stu-id="bca8a-p106">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge. They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="bca8a-127">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="bca8a-127">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="bca8a-128">为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bca8a-128">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
- <span data-ttu-id="bca8a-129">若要将 PIN 的数字位数设置为 8： `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span><span class="sxs-lookup"><span data-stu-id="bca8a-129">To set the number of digits in the PIN to 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span></span>
    
- <span data-ttu-id="bca8a-p107">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="bca8a-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="bca8a-133">为什么您需要使用 Office 365 PowerShell 中</span><span class="sxs-lookup"><span data-stu-id="bca8a-133">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="bca8a-134">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="bca8a-134">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="bca8a-135">Windows PowerShell 具有很多好处中快速、 简便起见和生产力通过只使用 Office 365 管理中心中的，如时要进行设置更改多个用户一次。</span><span class="sxs-lookup"><span data-stu-id="bca8a-135">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="bca8a-136">请在以下主题中了解这些优点：</span><span class="sxs-lookup"><span data-stu-id="bca8a-136">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="bca8a-137">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="bca8a-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="bca8a-138">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="bca8a-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [<span data-ttu-id="bca8a-139">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="bca8a-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="bca8a-140">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="bca8a-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="bca8a-p109">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="bca8a-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bca8a-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bca8a-143">See also</span></span>

[<span data-ttu-id="bca8a-144">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="bca8a-144">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
