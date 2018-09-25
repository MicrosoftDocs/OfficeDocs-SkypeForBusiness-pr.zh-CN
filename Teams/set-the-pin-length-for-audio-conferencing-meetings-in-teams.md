---
title: 在 Microsoft Teams 中设置音频会议的 PIN 长度
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
description: 了解表示 PIN 的长度和要求的参数，并了解如何在 Microsoft Teams 中设置会议的 PIN 长度。
ms.openlocfilehash: db7c62920dc7440cc8356dd3f5275dd551cdfd78
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014914"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a><span data-ttu-id="5baa1-103">在 Microsoft Teams 中设置音频会议的 PIN 长度</span><span class="sxs-lookup"><span data-stu-id="5baa1-103">Set the PIN length for Audio Conferencing meetings in Microsoft Teams</span></span>

<span data-ttu-id="5baa1-104">当您要设置的 Microsoft 团队音频会议时，您将看到音频会议桥。</span><span class="sxs-lookup"><span data-stu-id="5baa1-104">When you are setting up audio conferencing for Microsoft Teams, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="5baa1-105">会议网桥可以包含一个或多个电话号码。</span><span class="sxs-lookup"><span data-stu-id="5baa1-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="5baa1-106">设置您的电话号码将包含在会议邀请的 Microsoft 团队应用程序。</span><span class="sxs-lookup"><span data-stu-id="5baa1-106">The phone number you set will be included on the meeting invites for the Microsoft Teams app.</span></span>
  
<span data-ttu-id="5baa1-107">音频会议桥的会议使用电话拨入的人员接听电话。</span><span class="sxs-lookup"><span data-stu-id="5baa1-107">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="5baa1-108">其接听呼叫者使用语音提示从自动助理，然后，具体取决于您的设置，可以播放通知以及提出呼叫者在记录其姓名。</span><span class="sxs-lookup"><span data-stu-id="5baa1-108">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="5baa1-109">**Microsoft 桥设置**允许您更改会议通知的设置和会议加入体验，并设置由会议组织者 Pin 长度。</span><span class="sxs-lookup"><span data-stu-id="5baa1-109">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="5baa1-110">会议组织者使用 Pin 启动会议，如果无法加入会议使用 Microsoft 团队应用程序。</span><span class="sxs-lookup"><span data-stu-id="5baa1-110">Meeting organizers use PINs to start meetings if they can't join the meeting using the Microsoft Teams app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="5baa1-111">设置 PIN 长度</span><span class="sxs-lookup"><span data-stu-id="5baa1-111">Setting the PIN length</span></span>

1. <span data-ttu-id="5baa1-112">在左侧导航中，转到“**会议**” > “**会议网桥**”。</span><span class="sxs-lookup"><span data-stu-id="5baa1-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="5baa1-113">在“**会议网桥**”页面顶部，单击“**网桥设置**”。</span><span class="sxs-lookup"><span data-stu-id="5baa1-113">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="5baa1-114">在“**网桥设置**”窗格中的“**PIN 长度**”下，为 PIN 选择所需的位数。</span><span class="sxs-lookup"><span data-stu-id="5baa1-114">In the **Bridge settings** pane, under **PIN length**, select the number of digits you want for the PIN.</span></span>

4. <span data-ttu-id="5baa1-115">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="5baa1-115">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="5baa1-p103">[!注释] PIN 与会议 ID 不同。 会议 ID 由呼叫者在加入会议时使用。 它们用于标识会议。 PIN 用于对作为会议组织者的呼叫者进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="5baa1-p103">A PIN is different from a conference ID. Conference IDs are used by callers when they join the meeting. They are used to identify the meeting. The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="5baa1-120">想要了解有关 PIN 设置的详细信息？</span><span class="sxs-lookup"><span data-stu-id="5baa1-120">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="5baa1-121">旋转中心点到 12 个数字; 可以是从 4默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="5baa1-121">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="5baa1-122">在创建 PIN 时只能使用数字。</span><span class="sxs-lookup"><span data-stu-id="5baa1-122">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="5baa1-123">不能使用字母和特殊字符。</span><span class="sxs-lookup"><span data-stu-id="5baa1-123">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="5baa1-124">PIN，仅当 Microsoft 团队用户已尚未启动会议所需的会议组织者。</span><span class="sxs-lookup"><span data-stu-id="5baa1-124">A PIN is only required for the meeting organizer when a Microsoft Teams user hasn't already started the meeting.</span></span> <span data-ttu-id="5baa1-125">如果每个人都是拨号进入会议，则会议组织者需要 PIN 才能启动会议。</span><span class="sxs-lookup"><span data-stu-id="5baa1-125">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="5baa1-p106">PIN 安全设置适用于与 Microsoft 网桥相关联的所有电话号码。它们将应用于使用与给定网桥相关联的电话号码的所有会议。</span><span class="sxs-lookup"><span data-stu-id="5baa1-p106">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge. They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="5baa1-128">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="5baa1-128">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="5baa1-p107">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="5baa1-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5baa1-132">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="5baa1-132">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="5baa1-133">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="5baa1-133">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="5baa1-134">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="5baa1-134">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="5baa1-135">相关主题</span><span class="sxs-lookup"><span data-stu-id="5baa1-135">Related topics</span></span>

[<span data-ttu-id="5baa1-136">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="5baa1-136">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
