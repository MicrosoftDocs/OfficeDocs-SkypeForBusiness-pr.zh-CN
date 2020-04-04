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
description: 了解 PIN 长度和要求的参数，了解如何在 Microsoft 团队中设置会议的长度。
ms.openlocfilehash: f8d225728854e1bb7609264eecfd1230de2f919b
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140885"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a><span data-ttu-id="56840-103">在 Microsoft Teams 中设置音频会议的 PIN 长度</span><span class="sxs-lookup"><span data-stu-id="56840-103">Set the PIN length for Audio Conferencing meetings in Microsoft Teams</span></span>

<span data-ttu-id="56840-104">当你为 Microsoft Teams 设置音频会议时，你将获得一个音频会议网桥。</span><span class="sxs-lookup"><span data-stu-id="56840-104">When you are setting up audio conferencing for Microsoft Teams, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="56840-105">会议网桥可以包含一个或多个电话号码。</span><span class="sxs-lookup"><span data-stu-id="56840-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="56840-106">你设置的电话号码将包含在 Microsoft Teams 应用的会议邀请中。</span><span class="sxs-lookup"><span data-stu-id="56840-106">The phone number you set will be included on the meeting invites for the Microsoft Teams app.</span></span>
  
<span data-ttu-id="56840-107">会议网桥负责应答使用电话拨入会议的人员的呼叫。</span><span class="sxs-lookup"><span data-stu-id="56840-107">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="56840-108">它通过来自自动助理的语音提示应答呼叫者，然后根据你的设置，可以播放通知并让呼叫者录制其姓名。</span><span class="sxs-lookup"><span data-stu-id="56840-108">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="56840-109">在 **Microsoft 网桥设置**中，你可以更改会议通知和会议加入体验的设置，并设置会议组织者使用的 PIN 的长度。</span><span class="sxs-lookup"><span data-stu-id="56840-109">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="56840-110">如果会议组织者无法使用 Microsoft Teams 应用加入会议，可使用 PIN 启动会议。</span><span class="sxs-lookup"><span data-stu-id="56840-110">Meeting organizers use PINs to start meetings if they can't join the meeting using the Microsoft Teams app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="56840-111">设置 PIN 长度</span><span class="sxs-lookup"><span data-stu-id="56840-111">Setting the PIN length</span></span>

<span data-ttu-id="56840-112">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="56840-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="56840-113">在左侧导航中，转到“**会议**” > “**会议网桥**”。</span><span class="sxs-lookup"><span data-stu-id="56840-113">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="56840-114">在“**会议网桥**”页面顶部，单击“**网桥设置**”。</span><span class="sxs-lookup"><span data-stu-id="56840-114">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="56840-115">在 "**桥设置**" 窗格中的 " **PIN 长度**" 下，选择要用于 pin 的数字位数。</span><span class="sxs-lookup"><span data-stu-id="56840-115">In the **Bridge settings** pane, under **PIN length**, select the number of digits you want for the PIN.</span></span>

4. <span data-ttu-id="56840-116">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="56840-116">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="56840-p103">[!注释] PIN 与会议 ID 不同。 会议 ID 由呼叫者在加入会议时使用。 它们用于标识会议。 PIN 用于对作为会议组织者的呼叫者进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="56840-p103">A PIN is different from a conference ID. Conference IDs are used by callers when they join the meeting. They are used to identify the meeting. The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="56840-121">想要了解有关 PIN 设置的详细信息？</span><span class="sxs-lookup"><span data-stu-id="56840-121">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="56840-122">引脚可以是4到12位数字;默认值为5。</span><span class="sxs-lookup"><span data-stu-id="56840-122">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="56840-123">在创建 PIN 时只能使用数字。</span><span class="sxs-lookup"><span data-stu-id="56840-123">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="56840-124">不能使用字母和特殊字符。</span><span class="sxs-lookup"><span data-stu-id="56840-124">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="56840-125">只有当 Microsoft 团队用户尚未启动会议时，会议组织者才需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="56840-125">A PIN is only required for the meeting organizer when a Microsoft Teams user hasn't already started the meeting.</span></span> <span data-ttu-id="56840-126">如果每个人都是拨号进入会议，则会议组织者需要 PIN 才能启动会议。</span><span class="sxs-lookup"><span data-stu-id="56840-126">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="56840-p106">PIN 安全设置适用于与 Microsoft 网桥相关联的所有电话号码。它们将应用于使用与给定网桥相关联的电话号码的所有会议。</span><span class="sxs-lookup"><span data-stu-id="56840-p106">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge. They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="56840-129">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="56840-129">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="56840-p107">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="56840-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="56840-133">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="56840-133">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="56840-134">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="56840-134">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="56840-135">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="56840-135">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="56840-136">相关主题</span><span class="sxs-lookup"><span data-stu-id="56840-136">Related topics</span></span>

[<span data-ttu-id="56840-137">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="56840-137">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
