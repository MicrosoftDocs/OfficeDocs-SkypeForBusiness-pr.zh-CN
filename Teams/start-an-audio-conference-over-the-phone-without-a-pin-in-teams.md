---
title: 开始音频会议中的 Microsoft 团队 PIN 不电话
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
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
description: '了解如何启用或禁用匿名呼叫者加入会议从团队管理中心。 '
ms.openlocfilehash: c68e3a0bd9992eb53811941113a30e9362c78227
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882996"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a><span data-ttu-id="ebd32-103">开始音频会议中的 Microsoft 团队 PIN 不电话</span><span class="sxs-lookup"><span data-stu-id="ebd32-103">Start an Audio Conference over the phone without a PIN in Microsoft Teams</span></span>

<span data-ttu-id="ebd32-104">可能会干扰拨入会议以将其保留在收听音乐，因为 Microsoft 团队会议组织者尚未启动会议的会议的会议厅中的用户。</span><span class="sxs-lookup"><span data-stu-id="ebd32-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="ebd32-105">如果会议组织者在调用会议，默认情况下，启动会议需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="ebd32-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="ebd32-106">您可以将它设置以便任何人都可以拨号加入会议并不会提示输入 PIN 才能启动会议。</span><span class="sxs-lookup"><span data-stu-id="ebd32-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="ebd32-107">您可以使用管理中心启用或禁用此设置为单个用户。</span><span class="sxs-lookup"><span data-stu-id="ebd32-107">You can use the admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="ebd32-108">PIN 不需要会议组织者，如果某人具有来自 Microsoft 团队应用程序启动会议。</span><span class="sxs-lookup"><span data-stu-id="ebd32-108">A PIN isn't required for the meeting organizer if someone has started the meeting from the Microsoft Teams app.</span></span> <span data-ttu-id="ebd32-109">只有当会议组织者通过电话加入会议时，才需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="ebd32-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="ebd32-110">已分配的**音频会议**许可证并启用了音频会议时，将向音频用户发送会议的 PIN。</span><span class="sxs-lookup"><span data-stu-id="ebd32-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="ebd32-111">请参阅[发送对其进行音频会议信息的用户电子邮件](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)和[自动发送给其音频会议设置更改时的用户的电子邮件](emails-sent-to-users-when-their-settings-change-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="ebd32-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change-in-teams.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="ebd32-112">启用或禁用匿名呼叫者加入会议</span><span class="sxs-lookup"><span data-stu-id="ebd32-112">Enable or disable anonymous callers from joining a meeting</span></span>

<span data-ttu-id="ebd32-113">![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="ebd32-113">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="ebd32-114">在左侧导航窗格中，单击**用户**。</span><span class="sxs-lookup"><span data-stu-id="ebd32-114">In the left navigation, click **Users**.</span></span> 

2. <span data-ttu-id="ebd32-115">在列表中，选择一个用户，然后单击页面顶部的**编辑**。</span><span class="sxs-lookup"><span data-stu-id="ebd32-115">Select a user in the list, and then click **Edit** at the top of the page.</span></span> 

3. <span data-ttu-id="ebd32-116">在**音频会议**旁边，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="ebd32-116">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="ebd32-117">在**音频会议**窗格中，启用或禁用**未经身份验证的呼叫者可以在会议中的第一个人**。</span><span class="sxs-lookup"><span data-stu-id="ebd32-117">In the **Audio Conferencing** pane, enable or disable **Unauthenticated callers can be the first person in a meeting**.</span></span>
    
4. <span data-ttu-id="ebd32-118">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="ebd32-118">Click **Save**.</span></span> 

<span data-ttu-id="ebd32-119">**使用 Windows Powershell**</span><span class="sxs-lookup"><span data-stu-id="ebd32-119">**Using Windows Powershell**</span></span>
  
<span data-ttu-id="ebd32-120">请参阅[Microsoft 团队 PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)（英文） 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ebd32-120">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-else-should-you-know"></a><span data-ttu-id="ebd32-121">你还需了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="ebd32-121">What else should you know?</span></span>

- <span data-ttu-id="ebd32-122">如果您想要重置 PIN，请参阅[重置的音频会议 PIN](reset-the-audio-conferencing-pin-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="ebd32-122">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
- <span data-ttu-id="ebd32-123">如果启用了匿名访问，或不需要 PIN 才能启动会议时，:</span><span class="sxs-lookup"><span data-stu-id="ebd32-123">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="ebd32-124">如果尚未启动会议 （没有一种-会议尚未）： 将提示呼叫者，如果他是组织者;如果他说是时，他将提示您为其 PIN，他输入 PIN 之后，会议的开始和用户将加入会议。</span><span class="sxs-lookup"><span data-stu-id="ebd32-124">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="ebd32-125">如果会议已启动（有人已在会议中）：如果呼叫者是组织者，则不会提示您提供 PIN；会议已启动，并将呼叫者将加入。</span><span class="sxs-lookup"><span data-stu-id="ebd32-125">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="ebd32-126">如果禁用匿名访问，或不需要 PIN 才能开始会议，则：</span><span class="sxs-lookup"><span data-stu-id="ebd32-126">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="ebd32-127">如果尚未启动会议（还没有会议）：如果呼叫者是组织者，将不会收到提示，并且从不提示她提供 PIN。</span><span class="sxs-lookup"><span data-stu-id="ebd32-127">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="ebd32-128">组织者的设置设置为关闭，因为会议将启动，匿名呼叫者将加入会议。</span><span class="sxs-lookup"><span data-stu-id="ebd32-128">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="ebd32-129">如果会议已启动（有人已在会议中）：如果呼叫者是组织者，则不会提示您提供 PIN；会议已启动，并将呼叫者将加入。</span><span class="sxs-lookup"><span data-stu-id="ebd32-129">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="ebd32-130">要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="ebd32-130">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="ebd32-p104">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="ebd32-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ebd32-134">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ebd32-134">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="ebd32-135">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="ebd32-135">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="ebd32-136">有关 Windows PowerShell 的详细信息，请参阅[Microsoft 团队 PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)（英文） 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ebd32-136">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="ebd32-137">相关主题</span><span class="sxs-lookup"><span data-stu-id="ebd32-137">Related topics</span></span>

[<span data-ttu-id="ebd32-138">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="ebd32-138">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
