---
title: 通过电话在 Skype for Business Online 开始音频会议而无 PIN
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '了解如何启用或禁用从 Skype for Business Online 管理中心或使用 PowerShell 脚本参加会议的匿名呼叫者。 '
ms.openlocfilehash: 655f61c449554a9044095a5b8ef8bd8ef2940bc4
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237588"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a><span data-ttu-id="a3539-103">通过电话在 Skype for Business Online 开始音频会议而无 PIN</span><span class="sxs-lookup"><span data-stu-id="a3539-103">Start an Audio Conference over the phone without a PIN in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> <span data-ttu-id="a3539-104">有关在 Microsoft Teams 无 PIN 启动音频会议的信息，请参阅[通过电话在 Microsoft Teams 中无 PIN 开始音频会议](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="a3539-104">For information about starting an Audio Conference without a PIN in Microsoft Teams, see [Start an Audio Conference over the phone without a PIN  in Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).</span></span>

<span data-ttu-id="a3539-105">拨入会议的用户在会议大厅中收听音乐可能令人沮丧，因为会议组织者Skype for Business会议尚未启动。</span><span class="sxs-lookup"><span data-stu-id="a3539-105">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Skype for Business meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="a3539-106">默认情况下，如果会议组织者呼叫呼叫会议，则启动会议需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="a3539-106">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="a3539-107">您可以设置它，以便任何人都可以拨入会议，并且系统不会提示输入 PIN 以启动会议。</span><span class="sxs-lookup"><span data-stu-id="a3539-107">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="a3539-108">你可以使用 Skype for Business 管理中心为单个用户启用或禁用此设置。</span><span class="sxs-lookup"><span data-stu-id="a3539-108">You can use the Skype for Business admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="a3539-109">如果有人从会议组织者的应用启动会议，会议组织者Skype for Business PIN。</span><span class="sxs-lookup"><span data-stu-id="a3539-109">A PIN isn't required for the meeting organizer if someone has started the meeting from the Skype for Business app.</span></span> <span data-ttu-id="a3539-110">只有当会议组织者通过电话加入会议时，才需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="a3539-110">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="a3539-111">为音频用户分配音频会议许可证并启用音频会议时，会议 PIN将发送给音频用户。</span><span class="sxs-lookup"><span data-stu-id="a3539-111">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="a3539-112">请参阅 [向用户发送](send-an-email-to-a-user-with-their-dial-in-information.md) 包含其音频会议信息的电子邮件，以及当用户的音频会议设置更改时 [自动发送给用户的电子邮件](emails-sent-to-users-when-their-settings-change.md)。</span><span class="sxs-lookup"><span data-stu-id="a3539-112">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="a3539-113">启用或禁用匿名呼叫者加入会议</span><span class="sxs-lookup"><span data-stu-id="a3539-113">Enable or disable anonymous callers from joining a meeting</span></span>
    
1. <span data-ttu-id="a3539-114">在 **Skype for Business管理** 中心的 左侧导航中，转到"**音频会议用户**  >  **"。**</span><span class="sxs-lookup"><span data-stu-id="a3539-114">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**.</span></span> 
    
2. <span data-ttu-id="a3539-115">在列表中选择用户，在"操作"窗格中单击"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="a3539-115">In the list, select the user and in the Action pane click **Edit**.</span></span> 
    
3. <span data-ttu-id="a3539-116">在用户的属性页面上的"会议选项"下，选择或清除"允许未经身份验证的呼叫者成为 **会议的第一人"。如果没有，则他们将在大厅中等待，直到经过身份验证的用户加入**。</span><span class="sxs-lookup"><span data-stu-id="a3539-116">On the user's properties page, under **Meeting options**, select or clear **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
4. <span data-ttu-id="a3539-117">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a3539-117">Click **Save**.</span></span> 


    
 <span data-ttu-id="a3539-118">**使用 Windows Powershell**</span><span class="sxs-lookup"><span data-stu-id="a3539-118">**Using Windows Powershell**</span></span>
  
- <span data-ttu-id="a3539-119">请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="a3539-119">Run the following:</span></span> 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="a3539-120">你还需了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="a3539-120">What else should you know?</span></span>

- <span data-ttu-id="a3539-121">如果要重置 PIN，请参阅[重置音频会议 PIN。](reset-the-audio-conferencing-pin.md)</span><span class="sxs-lookup"><span data-stu-id="a3539-121">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
    
- <span data-ttu-id="a3539-122">如果禁用了匿名访问，或者不需要 PIN 来启动会议：</span><span class="sxs-lookup"><span data-stu-id="a3539-122">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="a3539-123">如果会议尚未开始 (则会议中还没有人) ：如果呼叫者是组织者，则系统将会提示呼叫者;如果说"是"，系统会提示他输入 PIN，输入 PIN 后，会议将开始，用户将加入会议。</span><span class="sxs-lookup"><span data-stu-id="a3539-123">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="a3539-124">如果会议已启动（有人已在会议中）：如果呼叫者是组织者，则不会提示您提供 PIN；会议已启动，并将呼叫者将加入。</span><span class="sxs-lookup"><span data-stu-id="a3539-124">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="a3539-125">如果启用了匿名访问，或者不需要 PIN 来启动会议：</span><span class="sxs-lookup"><span data-stu-id="a3539-125">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="a3539-126">如果尚未启动会议（还没有会议）：如果呼叫者是组织者，将不会收到提示，并且从不提示她提供 PIN。</span><span class="sxs-lookup"><span data-stu-id="a3539-126">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="a3539-127">由于组织者的设置设置为"关"，会议将开始，匿名呼叫者将加入会议。</span><span class="sxs-lookup"><span data-stu-id="a3539-127">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="a3539-128">如果会议已启动（有人已在会议中）：如果呼叫者是组织者，则不会提示您提供 PIN；会议已启动，并将呼叫者将加入。</span><span class="sxs-lookup"><span data-stu-id="a3539-128">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="a3539-129">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="a3539-129">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="a3539-130">为节省时间或为多个用户自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a3539-130">To save time or automate this for more than one user, you can use the [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet.</span></span>
    
- <span data-ttu-id="a3539-131">对于 Windows PowerShell，Skype for Business Online 的功能是管理用户以及允许或不允许用户执行的操作。</span><span class="sxs-lookup"><span data-stu-id="a3539-131">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="a3539-132">使用Windows PowerShell，可以使用Microsoft 365管理Office 365管理点，在有多个任务需要执行时简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="a3539-132">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="a3539-133">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="a3539-133">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="a3539-134">为何需要将 Microsoft 365 或 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3539-134">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="a3539-135">[使用 Microsoft 365 Office 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="a3539-135">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="a3539-136">Windows PowerShell管理中心相比，Microsoft 365在速度、简单性和工作效率方面具有许多优势，例如，一次为许多用户更改设置时。</span><span class="sxs-lookup"><span data-stu-id="a3539-136">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="a3539-137">请在以下主题中了解这些优点：</span><span class="sxs-lookup"><span data-stu-id="a3539-137">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="a3539-138">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="a3539-138">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [<span data-ttu-id="a3539-139">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a3539-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="a3539-140">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="a3539-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="a3539-p106">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="a3539-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="a3539-143">相关主题</span><span class="sxs-lookup"><span data-stu-id="a3539-143">Related topics</span></span>

[<span data-ttu-id="a3539-144">尝试或购买音频会议Microsoft 365或Office 365</span><span class="sxs-lookup"><span data-stu-id="a3539-144">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
