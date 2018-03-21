---
title: "设置音频会议的会议的针长度"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: Learn the parameters for the length and requirements of a PIN and see how to set the length for meetings in Skype for Business.
ms.openlocfilehash: 308bce9196f085c1f9473e74746bccd2f0ca96c5
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2018
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings"></a><span data-ttu-id="d2f14-103">设置音频会议的会议的针长度</span><span class="sxs-lookup"><span data-stu-id="d2f14-103">Set the PIN length for Audio Conferencing meetings</span></span>

<span data-ttu-id="d2f14-104">当您设置中的音频会议为 Skype 业务或 Microsoft 小组时，您将看到音频会议桥。</span><span class="sxs-lookup"><span data-stu-id="d2f14-104">When you are setting up audio conferencing in for Skype for Business or Microsoft Teams, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="d2f14-105">会议网桥可以包含一个或多个电话号码。</span><span class="sxs-lookup"><span data-stu-id="d2f14-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="d2f14-106">您设置的电话号码将包括在会议邀请的 Skype 业务和 Microsoft 小组应用程序。</span><span class="sxs-lookup"><span data-stu-id="d2f14-106">The phone number you set will be included on the meeting invites for Skype for Business and Microsoft Teams apps.</span></span>
  
<span data-ttu-id="d2f14-107">音频会议桥的拨入会议使用电话的人应答呼叫。</span><span class="sxs-lookup"><span data-stu-id="d2f14-107">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="d2f14-108">从自动助理，然后根据您的设置，它会回答带语音提示的调用方，可以播放通知并要求调用方来记录他们的姓名。</span><span class="sxs-lookup"><span data-stu-id="d2f14-108">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="d2f14-109">**Microsoft 网桥的设置**允许您更改的设置会议通知和会议加入体验，并将由会议组织者的针脚长度设置。</span><span class="sxs-lookup"><span data-stu-id="d2f14-109">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="d2f14-110">会议组织者使用针脚来启动会议，如果他们不能参加会议的业务或 Microsoft 小组应用程序使用 Skype。</span><span class="sxs-lookup"><span data-stu-id="d2f14-110">Meeting organizers use PINs to start meetings if they can't join the meeting using the Skype for Business or Microsoft Teams app.</span></span>
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="d2f14-111">设置 PIN 长度</span><span class="sxs-lookup"><span data-stu-id="d2f14-111">Setting the PIN length</span></span>

1. <span data-ttu-id="d2f14-112">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="d2f14-112">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="d2f14-113">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="d2f14-113">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="d2f14-114">在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议** > **Microsoft 网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="d2f14-114">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="d2f14-115">在**安全**下 > **针长度**，选择的针，所需的位数，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="d2f14-115">Under **Security** > **PIN length**, select the number of digits you want for the PIN, and then click **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d2f14-p103">[!注释] PIN 与会议 ID 不同。 会议 ID 由呼叫者在加入会议时使用。 它们用于标识会议。 PIN 用于对作为会议组织者的呼叫者进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="d2f14-p103">A PIN is different from a conference ID. Conference IDs are used by callers when they join the meeting. They are used to identify the meeting. The PIN is used to authenticate a caller as the meeting organizer.</span></span> 
  
## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="d2f14-120">想知道更多有关 PIN 设置？</span><span class="sxs-lookup"><span data-stu-id="d2f14-120">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="d2f14-121">针脚可以从 4 到 12 位数字;默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="d2f14-121">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="d2f14-122">在创建 PIN 时只能使用数字。</span><span class="sxs-lookup"><span data-stu-id="d2f14-122">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="d2f14-123">不能使用字母和特殊字符。</span><span class="sxs-lookup"><span data-stu-id="d2f14-123">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="d2f14-124">PIN 只是对于会议组织者在为业务或 Microsoft 小组的用户 Skype 时没有已启动会议是必需的。</span><span class="sxs-lookup"><span data-stu-id="d2f14-124">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams user hasn't already started the meeting.</span></span> <span data-ttu-id="d2f14-125">如果每个人都是拨号进入会议，则会议组织者需要 PIN 才能启动会议。</span><span class="sxs-lookup"><span data-stu-id="d2f14-125">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="d2f14-p106">PIN 安全设置适用于与 Microsoft 网桥相关联的所有电话号码。它们将应用于使用与给定网桥相关联的电话号码的所有会议。</span><span class="sxs-lookup"><span data-stu-id="d2f14-p106">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge. They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="d2f14-128">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="d2f14-128">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="d2f14-129">为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d2f14-129">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
- <span data-ttu-id="d2f14-130">若要将 PIN 的数字位数设置为 8： `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span><span class="sxs-lookup"><span data-stu-id="d2f14-130">To set the number of digits in the PIN to 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span></span>
    
- <span data-ttu-id="d2f14-p107">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="d2f14-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d2f14-134">为什么需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="d2f14-134">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="d2f14-135">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="d2f14-135">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="d2f14-136">Windows PowerShell 许多相比具有的优势在速度、 简易性和生产率仅使用 Office 365 管理中心，例如当您所更改的设置对于许多用户一次。</span><span class="sxs-lookup"><span data-stu-id="d2f14-136">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="d2f14-137">请在以下主题中了解这些优点：</span><span class="sxs-lookup"><span data-stu-id="d2f14-137">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="d2f14-138">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="d2f14-138">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="d2f14-139">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d2f14-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [<span data-ttu-id="d2f14-140">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d2f14-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="d2f14-141">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="d2f14-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="d2f14-p109">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="d2f14-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d2f14-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d2f14-144">See also</span></span>

[<span data-ttu-id="d2f14-145">设置 Skype for Business 和 Microsoft Teams 音频会议</span><span class="sxs-lookup"><span data-stu-id="d2f14-145">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)

