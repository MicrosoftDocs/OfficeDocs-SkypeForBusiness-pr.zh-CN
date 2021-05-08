---
title: 设置音频会议的 PIN 长度
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
- M365-voice
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
description: 了解 PIN 的长度和要求的参数，并了解如何在 Microsoft Teams 中设置会议长度。
ms.openlocfilehash: 68dc1f3ea5508dc88bc168a5f3fbed837bbee04f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117160"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a><span data-ttu-id="6b61b-103">在 Microsoft Teams 中设置音频会议的 PIN 长度</span><span class="sxs-lookup"><span data-stu-id="6b61b-103">Set the PIN length for Audio Conferencing meetings in Microsoft Teams</span></span>

<span data-ttu-id="6b61b-104">当你为会议设置音频会议Microsoft Teams，你将获得音频会议网桥。</span><span class="sxs-lookup"><span data-stu-id="6b61b-104">When you are setting up audio conferencing for Microsoft Teams, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="6b61b-105">会议网桥可以包含一个或多个电话号码。</span><span class="sxs-lookup"><span data-stu-id="6b61b-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="6b61b-106">你设置的电话号码将包含在会议邀请中，Microsoft Teams应用。</span><span class="sxs-lookup"><span data-stu-id="6b61b-106">The phone number you set will be included on the meeting invites for the Microsoft Teams app.</span></span>
  
<span data-ttu-id="6b61b-107">音频会议网桥负责应答使用电话拨入会议的用户的呼叫。</span><span class="sxs-lookup"><span data-stu-id="6b61b-107">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="6b61b-108">它通过自动助理的语音提示应答呼叫者，然后根据你的设置，可以播放通知并要求呼叫者录制其姓名。</span><span class="sxs-lookup"><span data-stu-id="6b61b-108">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="6b61b-109">**Microsoft 网桥** 设置允许您更改会议通知和会议加入体验的设置，并设置会议组织者使用的 PIN 的长度。</span><span class="sxs-lookup"><span data-stu-id="6b61b-109">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="6b61b-110">如果会议组织者无法通过 Microsoft Teams 应用加入会议，会议组织者将使用 PIN 启动会议。</span><span class="sxs-lookup"><span data-stu-id="6b61b-110">Meeting organizers use PINs to start meetings if they can't join the meeting using the Microsoft Teams app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="6b61b-111">设置 PIN 长度</span><span class="sxs-lookup"><span data-stu-id="6b61b-111">Setting the PIN length</span></span>

<span data-ttu-id="6b61b-112">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="6b61b-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="6b61b-113">在左侧导航中，转到“**会议**” > “**会议网桥**”。</span><span class="sxs-lookup"><span data-stu-id="6b61b-113">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="6b61b-114">在“**会议网桥**”页面顶部，单击“**网桥设置**”。</span><span class="sxs-lookup"><span data-stu-id="6b61b-114">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="6b61b-115">在" **网桥设置"** 窗格中的 **"PIN** 长度"下，选择 PIN 的位数。</span><span class="sxs-lookup"><span data-stu-id="6b61b-115">In the **Bridge settings** pane, under **PIN length**, select the number of digits you want for the PIN.</span></span>

4. <span data-ttu-id="6b61b-116">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="6b61b-116">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="6b61b-p103">[!注释] PIN 与会议 ID 不同。 会议 ID 由呼叫者在加入会议时使用。 它们用于标识会议。 PIN 用于对作为会议组织者的呼叫者进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="6b61b-p103">A PIN is different from a conference ID. Conference IDs are used by callers when they join the meeting. They are used to identify the meeting. The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="6b61b-121">想要了解有关 PIN 设置的信息？</span><span class="sxs-lookup"><span data-stu-id="6b61b-121">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="6b61b-122">PIN 可以是 4 到 12 个数字;默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="6b61b-122">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="6b61b-123">在创建 PIN 时只能使用数字。</span><span class="sxs-lookup"><span data-stu-id="6b61b-123">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="6b61b-124">不能使用字母和特殊字符。</span><span class="sxs-lookup"><span data-stu-id="6b61b-124">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="6b61b-125">只有当用户尚未启动会议时，Microsoft Teams组织者才需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="6b61b-125">A PIN is only required for the meeting organizer when a Microsoft Teams user hasn't already started the meeting.</span></span> <span data-ttu-id="6b61b-126">如果每个人都是拨号进入会议，则会议组织者需要 PIN 才能启动会议。</span><span class="sxs-lookup"><span data-stu-id="6b61b-126">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="6b61b-p106">PIN 安全设置适用于与 Microsoft 网桥相关联的所有电话号码。它们将应用于使用与给定网桥相关联的电话号码的所有会议。</span><span class="sxs-lookup"><span data-stu-id="6b61b-p106">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge. They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="6b61b-129">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="6b61b-129">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="6b61b-130">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="6b61b-130">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="6b61b-131">使用Windows PowerShell，Microsoft 365管理Office 365管理点，可在有多个任务需要执行时简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="6b61b-131">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="6b61b-132">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="6b61b-132">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="6b61b-133">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="6b61b-133">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="6b61b-134">[使用 Microsoft 365 Office 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="6b61b-134">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="6b61b-135">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="6b61b-135">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="6b61b-136">相关主题</span><span class="sxs-lookup"><span data-stu-id="6b61b-136">Related topics</span></span>

[<span data-ttu-id="6b61b-137">尝试或购买音频会议Microsoft 365或Office 365</span><span class="sxs-lookup"><span data-stu-id="6b61b-137">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)