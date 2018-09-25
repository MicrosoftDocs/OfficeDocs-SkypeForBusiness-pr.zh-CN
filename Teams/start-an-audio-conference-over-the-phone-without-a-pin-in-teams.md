---
title: 在 Microsoft Teams 中在没有 PIN 的情况下通过电话启动音频会议
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service:
- -msteams
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
description: '了解如何从 Teams 管理中心启用或禁用匿名呼叫者加入会议。 '
ms.openlocfilehash: 4aec566b165385a111162641f233cd1b1e3027f4
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014104"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a><span data-ttu-id="f4d0a-103">在 Microsoft Teams 中在没有 PIN 的情况下通过电话启动音频会议</span><span class="sxs-lookup"><span data-stu-id="f4d0a-103">Start an Audio Conference over the phone without a PIN in Microsoft Teams</span></span>

<span data-ttu-id="f4d0a-104">拨入会议后在会议厅中听音乐等候的用户可能会感到沮丧，因为 Microsoft Teams 会议组织者尚未启动会议。</span><span class="sxs-lookup"><span data-stu-id="f4d0a-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="f4d0a-105">如果会议组织者在调用会议，默认情况下，启动会议需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="f4d0a-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="f4d0a-106">您可以将它设置以便任何人都可以拨号加入会议并不会提示输入 PIN 才能启动会议。</span><span class="sxs-lookup"><span data-stu-id="f4d0a-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="f4d0a-107">您可以使用管理中心启用或禁用此设置为单个用户。</span><span class="sxs-lookup"><span data-stu-id="f4d0a-107">You can use the admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="f4d0a-108">PIN 不需要会议组织者，如果某人具有来自 Microsoft 团队应用程序启动会议。</span><span class="sxs-lookup"><span data-stu-id="f4d0a-108">A PIN isn't required for the meeting organizer if someone has started the meeting from the Microsoft Teams app.</span></span> <span data-ttu-id="f4d0a-109">只有当会议组织者通过电话加入会议时，才需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="f4d0a-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="f4d0a-110">已分配的**音频会议**许可证并启用了音频会议时，将向音频用户发送会议的 PIN。</span><span class="sxs-lookup"><span data-stu-id="f4d0a-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="f4d0a-111">请参阅[发送对其进行音频会议信息的用户电子邮件](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)和[自动发送给其音频会议设置更改时的用户的电子邮件](emails-sent-to-users-when-their-settings-change-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="f4d0a-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change-in-teams.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="f4d0a-112">启用或禁用匿名呼叫者加入会议</span><span class="sxs-lookup"><span data-stu-id="f4d0a-112">Enable or disable anonymous callers from joining a meeting</span></span>

<span data-ttu-id="f4d0a-113">![teams-logo-30x30.png](media/teams-logo-30x30.png) **使用 Microsoft Teams 和 Skype for Business 管理中心：**</span><span class="sxs-lookup"><span data-stu-id="f4d0a-113">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="f4d0a-114">在左侧导航中，单击“**用户**”。</span><span class="sxs-lookup"><span data-stu-id="f4d0a-114">In the left navigation, click **Users**.</span></span> 

2. <span data-ttu-id="f4d0a-115">在列表中选择用户，然后单击页面顶部的“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="f4d0a-115">Select a user in the list, and then click **Edit** at the top of the page.</span></span> 

3. <span data-ttu-id="f4d0a-116">在“**音频会议**”旁边，单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="f4d0a-116">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="f4d0a-117">在“**音频会议**”窗格中，启用或禁用“**未经身份验证的呼叫者可以是第一个参加会议的人**”。</span><span class="sxs-lookup"><span data-stu-id="f4d0a-117">In the **Audio Conferencing** pane, enable or disable **Unauthenticated callers can be the first person in a meeting**.</span></span>
    
4. <span data-ttu-id="f4d0a-118">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="f4d0a-118">Click **Save**.</span></span> 

<span data-ttu-id="f4d0a-119">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f4d0a-119">**Using Windows Powershell**</span></span>
  
<span data-ttu-id="f4d0a-120">有关详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。</span><span class="sxs-lookup"><span data-stu-id="f4d0a-120">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-else-should-you-know"></a><span data-ttu-id="f4d0a-121">你还应该了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="f4d0a-121">What else should you know?</span></span>

- <span data-ttu-id="f4d0a-122">如果要重置 PIN，请参阅[重置音频会议 PIN](reset-the-audio-conferencing-pin-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="f4d0a-122">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
- <span data-ttu-id="f4d0a-123">如果已启用匿名访问或不要求使用 PIN 来启动会议：</span><span class="sxs-lookup"><span data-stu-id="f4d0a-123">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="f4d0a-124">如果会议尚未启动（会议中还没有人）：系统将提示呼叫者确认是否是组织者，如果呼叫者确认是，则系统将提示其输入自己 PIN，在呼叫者输入 PIN 后，会议将启动，用户将加入会议。</span><span class="sxs-lookup"><span data-stu-id="f4d0a-124">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="f4d0a-125">如果会议已启动（有人已在会议中）：如果呼叫者是组织者，则不会提示您提供 PIN；会议已启动，并将呼叫者将加入。</span><span class="sxs-lookup"><span data-stu-id="f4d0a-125">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="f4d0a-126">如果已禁用匿名访问或不要求使用 PIN 来启动会议：</span><span class="sxs-lookup"><span data-stu-id="f4d0a-126">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="f4d0a-127">如果尚未启动会议（还没有会议）：如果呼叫者是组织者，将不会收到提示，并且从不提示她提供 PIN。</span><span class="sxs-lookup"><span data-stu-id="f4d0a-127">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="f4d0a-128">组织者的设置设置为关闭，因为会议将启动，匿名呼叫者将加入会议。</span><span class="sxs-lookup"><span data-stu-id="f4d0a-128">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="f4d0a-129">如果会议已启动（有人已在会议中）：如果呼叫者是组织者，则不会提示您提供 PIN；会议已启动，并将呼叫者将加入。</span><span class="sxs-lookup"><span data-stu-id="f4d0a-129">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="f4d0a-130">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="f4d0a-130">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="f4d0a-p104">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="f4d0a-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f4d0a-134">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4d0a-134">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="f4d0a-135">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="f4d0a-135">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="f4d0a-136">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="f4d0a-136">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f4d0a-137">相关主题</span><span class="sxs-lookup"><span data-stu-id="f4d0a-137">Related topics</span></span>

[<span data-ttu-id="f4d0a-138">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="f4d0a-138">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
