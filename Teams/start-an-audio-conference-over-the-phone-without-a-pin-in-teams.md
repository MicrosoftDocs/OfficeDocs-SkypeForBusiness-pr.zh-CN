---
title: 在 Teams 中通过电话在没有 PIN 的情况下启动音频会议
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
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
description: '了解如何启用或禁用匿名呼叫者从 Teams 管理中心加入会议。 '
ms.openlocfilehash: 520bf720a01a686a103748cdbbf26cb8426e94f2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116960"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a><span data-ttu-id="e420b-103">在 Microsoft Teams 中在没有 PIN 的情况下通过电话启动音频会议</span><span class="sxs-lookup"><span data-stu-id="e420b-103">Start an Audio Conference over the phone without a PIN in Microsoft Teams</span></span>

<span data-ttu-id="e420b-104">拨入会议的用户在会议大厅中收听音乐可能令人沮丧，因为 Microsoft Teams 会议组织者尚未启动会议。</span><span class="sxs-lookup"><span data-stu-id="e420b-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="e420b-105">默认情况下，如果会议组织者呼叫呼叫会议，则启动会议需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="e420b-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="e420b-106">您可以设置它，以便任何人都可以拨入会议，并且系统不会提示输入 PIN 以启动会议。</span><span class="sxs-lookup"><span data-stu-id="e420b-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="e420b-107">可以使用管理中心为单个用户启用或禁用此设置。</span><span class="sxs-lookup"><span data-stu-id="e420b-107">You can use the admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="e420b-108">如果有人从 Microsoft Teams 应用启动了会议，会议组织者不需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="e420b-108">A PIN isn't required for the meeting organizer if someone has started the meeting from the Microsoft Teams app.</span></span> <span data-ttu-id="e420b-109">只有当会议组织者通过电话加入会议时，才需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="e420b-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="e420b-110">为音频用户分配音频会议许可证并启用音频会议时，会议 PIN将发送给音频用户。</span><span class="sxs-lookup"><span data-stu-id="e420b-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="e420b-111">请参阅 [向用户发送](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) 包含其音频会议信息的电子邮件，以及当用户的音频会议设置更改时 [自动发送给用户的电子邮件](emails-sent-to-users-when-their-settings-change-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="e420b-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change-in-teams.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="e420b-112">启用或禁用匿名呼叫者加入会议</span><span class="sxs-lookup"><span data-stu-id="e420b-112">Enable or disable anonymous callers from joining a meeting</span></span>

<span data-ttu-id="e420b-113">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="e420b-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="e420b-114">在左侧导航栏中，单击"用户 **"。**</span><span class="sxs-lookup"><span data-stu-id="e420b-114">In the left navigation, click **Users**.</span></span> 

2. <span data-ttu-id="e420b-115">在列表中选择一个用户，然后单击 **页面顶部的"** 编辑"。</span><span class="sxs-lookup"><span data-stu-id="e420b-115">Select a user in the list, and then click **Edit** at the top of the page.</span></span> 

3. <span data-ttu-id="e420b-116">在 **音频会议** 旁边，单击 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="e420b-116">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="e420b-117">在 **"音频会议"** 窗格中，启用或禁用拨入呼叫者可以是 **会议的第一人**。</span><span class="sxs-lookup"><span data-stu-id="e420b-117">In the **Audio Conferencing** pane, enable or disable **Dial-in callers can be the first person in a meeting**.</span></span>
    
4. <span data-ttu-id="e420b-118">单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="e420b-118">Click **Apply**.</span></span> 

<span data-ttu-id="e420b-119">**使用Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="e420b-119">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="e420b-120">有关详细信息， [请参阅 Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) 参考。</span><span class="sxs-lookup"><span data-stu-id="e420b-120">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-else-should-you-know"></a><span data-ttu-id="e420b-121">你还需了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="e420b-121">What else should you know?</span></span>

- <span data-ttu-id="e420b-122">如果要重置 PIN，请参阅[重置音频会议 PIN。](reset-the-audio-conferencing-pin-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="e420b-122">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
- <span data-ttu-id="e420b-123">如果禁用了匿名访问，或者不需要 PIN 来启动会议：</span><span class="sxs-lookup"><span data-stu-id="e420b-123">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="e420b-124">如果会议尚未开始 (则会议中还没有人) ：如果呼叫者是组织者，则系统将会提示呼叫者;如果说"是"，系统会提示他输入 PIN，输入 PIN 后，会议将开始，用户将加入会议。</span><span class="sxs-lookup"><span data-stu-id="e420b-124">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="e420b-125">如果会议已启动（有人已在会议中）：如果呼叫者是组织者，则不会提示您提供 PIN；会议已启动，并将呼叫者将加入。</span><span class="sxs-lookup"><span data-stu-id="e420b-125">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="e420b-126">如果启用了匿名访问，或者不需要 PIN 来启动会议：</span><span class="sxs-lookup"><span data-stu-id="e420b-126">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="e420b-127">如果尚未启动会议（还没有会议）：如果呼叫者是组织者，将不会收到提示，并且从不提示她提供 PIN。</span><span class="sxs-lookup"><span data-stu-id="e420b-127">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="e420b-128">由于组织者的设置设置为"关"，会议将开始，匿名呼叫者将加入会议。</span><span class="sxs-lookup"><span data-stu-id="e420b-128">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="e420b-129">如果会议已启动（有人已在会议中）：如果呼叫者是组织者，则不会提示您提供 PIN；会议已启动，并将呼叫者将加入。</span><span class="sxs-lookup"><span data-stu-id="e420b-129">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="e420b-130">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="e420b-130">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="e420b-131">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="e420b-131">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="e420b-132">使用 Windows PowerShell，您可以使用单点管理来管理 Microsoft 365 或 Office 365，当您有多个任务需要执行时，可以简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="e420b-132">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="e420b-133">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="e420b-133">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e420b-134">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e420b-134">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="e420b-135">[使用 Office 365 管理 Microsoft 365 或 Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="e420b-135">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="e420b-136">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="e420b-136">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e420b-137">相关主题</span><span class="sxs-lookup"><span data-stu-id="e420b-137">Related topics</span></span>

[<span data-ttu-id="e420b-138">在 Microsoft 365 或 Office 365 中试用或购买音频会议</span><span class="sxs-lookup"><span data-stu-id="e420b-138">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)