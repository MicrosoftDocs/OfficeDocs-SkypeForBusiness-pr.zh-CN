---
title: 在 Microsoft Teams 中设置音频会议的 PIN 长度
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
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 了解表示 PIN 的长度和要求的参数，并了解如何在 Microsoft Teams 中设置会议的 PIN 长度。
ms.openlocfilehash: 0300bba9139bdf98315b8af4200dd729ff6e70a1
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882988"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a><span data-ttu-id="e82cc-103">在 Microsoft Teams 中设置音频会议的 PIN 长度</span><span class="sxs-lookup"><span data-stu-id="e82cc-103">For information about setting the PIN length in Microsoft Teams, see Set the PIN length for Audio Conferencing meetings in Microsoft Teams.</span></span>

<span data-ttu-id="e82cc-104">当你为 Microsoft Teams 设置音频会议时，你将获得一个音频会议网桥。</span><span class="sxs-lookup"><span data-stu-id="e82cc-104">When you are setting up audio conferencing for Skype for Business, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="e82cc-105">会议网桥可以包含一个或多个电话号码。</span><span class="sxs-lookup"><span data-stu-id="e82cc-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="e82cc-106">你设置的电话号码将包含在 Microsoft Teams 应用的会议邀请中。</span><span class="sxs-lookup"><span data-stu-id="e82cc-106">The phone number you set will be included on the meeting invites for the Skype for Business app.</span></span>
  
<span data-ttu-id="e82cc-107">会议网桥负责应答使用电话拨入会议的人员的呼叫。</span><span class="sxs-lookup"><span data-stu-id="e82cc-107">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="e82cc-108">它通过来自自动助理的语音提示应答呼叫者，然后根据你的设置，可以播放通知并让呼叫者录制其姓名。</span><span class="sxs-lookup"><span data-stu-id="e82cc-108">It answers the caller with voice prompts from a system auto attendant and then depending on your settings can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="e82cc-109">在 **Microsoft 网桥设置**中，你可以更改会议通知和会议加入体验的设置，并设置会议组织者使用的 PIN 的长度。</span><span class="sxs-lookup"><span data-stu-id="e82cc-109">Skype for Business Online Microsoft bridge settings allows you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="e82cc-110">如果会议组织者无法使用 Microsoft Teams 应用加入会议，可使用 PIN 启动会议。</span><span class="sxs-lookup"><span data-stu-id="e82cc-110">Meeting organizers use PINs to start meetings if they can't join the meeting using the Skype for Business app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="e82cc-111">设置 PIN 长度</span><span class="sxs-lookup"><span data-stu-id="e82cc-111">Setting the PIN length</span></span>

1. <span data-ttu-id="e82cc-112">在左侧导航中，转到“**会议**” > “**会议网桥**”。</span><span class="sxs-lookup"><span data-stu-id="e82cc-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="e82cc-113">在“**会议网桥**”页面顶部，单击“**网桥设置**”。</span><span class="sxs-lookup"><span data-stu-id="e82cc-113">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="e82cc-114">在“**网桥设置**”窗格中的“**PIN 长度**”下，为 PIN 选择所需的位数。</span><span class="sxs-lookup"><span data-stu-id="e82cc-114">In the **Bridge settings** pane, under **PIN length**, select the number of digits you want for the PIN.</span></span>

4. <span data-ttu-id="e82cc-115">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="e82cc-115">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="e82cc-p103">[!注释] PIN 与会议 ID 不同。 会议 ID 由呼叫者在加入会议时使用。 它们用于标识会议。 PIN 用于对作为会议组织者的呼叫者进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="e82cc-p103">A PIN is different from a conference ID. Conference IDs are used by callers when they join the meeting. They are used to identify the meeting. The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="e82cc-120">想要了解有关 PIN 设置的详细信息？</span><span class="sxs-lookup"><span data-stu-id="e82cc-120">Want to more about PIN settings?</span></span>

- <span data-ttu-id="e82cc-121">PIN 可以为 4 至 12 位数，默认为 5 位。</span><span class="sxs-lookup"><span data-stu-id="e82cc-121">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="e82cc-122">创建 PIN 时只能使用数字。</span><span class="sxs-lookup"><span data-stu-id="e82cc-122">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="e82cc-123">不能使用字母和特殊字符。</span><span class="sxs-lookup"><span data-stu-id="e82cc-123">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="e82cc-124">只有当 Microsoft Teams 用户尚未启动会议时，会议组织者才需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="e82cc-124">A PIN is only required for the meeting organizer when a Skype for Business client user hasn't already started the meeting.</span></span> <span data-ttu-id="e82cc-125">如果所有人都是拨入会议，则会议组织者需要 PIN 才能启动会议。</span><span class="sxs-lookup"><span data-stu-id="e82cc-125">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="e82cc-p106">PIN 安全设置适用于与 Microsoft 网桥相关联的所有电话号码。它们将应用于使用与给定网桥相关联的电话号码的所有会议。</span><span class="sxs-lookup"><span data-stu-id="e82cc-p106">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge. They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="e82cc-128">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="e82cc-128">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="e82cc-p107">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="e82cc-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e82cc-132">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e82cc-132">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="e82cc-133">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="e82cc-133">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="e82cc-134">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="e82cc-134">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="e82cc-135">相关主题</span><span class="sxs-lookup"><span data-stu-id="e82cc-135">Related topics</span></span>

[<span data-ttu-id="e82cc-136">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="e82cc-136">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
