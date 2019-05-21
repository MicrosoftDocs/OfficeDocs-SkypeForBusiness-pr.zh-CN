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
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解如何启用或禁用从 Skype for Business Online 管理中心或使用 PowerShell 脚本参加会议的匿名呼叫者。 '
ms.openlocfilehash: af62ed29ed2bbe835ab811651152b231a85caaf8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302767"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a><span data-ttu-id="b5422-103">通过电话在 Skype for Business Online 开始音频会议而无 PIN</span><span class="sxs-lookup"><span data-stu-id="b5422-103">Start an Audio Conference over the phone without a PIN in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="b5422-104">有关在 Microsoft Teams 无 PIN 启动音频会议的信息，请参阅[通过电话在 Microsoft Teams 中无 PIN 开始音频会议](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="b5422-104">For information about starting an Audio Conference without a PIN in Microsoft Teams, see [Start an Audio Conference over the phone without a PIN  in Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).</span></span>

<span data-ttu-id="b5422-105">由于 Skype for Business 会议组织者尚未启动会议, 因此, 拨入会议的用户可能会感到沮丧, 因为 Skype for Business 会议组织者尚未启动会议。</span><span class="sxs-lookup"><span data-stu-id="b5422-105">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Skype for Business meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="b5422-p101">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting. You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting. You can use the Skype for Business admin center to enable or disable this setting for a single user.</span><span class="sxs-lookup"><span data-stu-id="b5422-p101">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting. You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting. You can use the Skype for Business admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="b5422-109">A PIN isn't required for the meeting organizer if someone has started the meeting from the Skype for Business app.</span><span class="sxs-lookup"><span data-stu-id="b5422-109">A PIN isn't required for the meeting organizer if someone has started the meeting from the Skype for Business app.</span></span> <span data-ttu-id="b5422-110">A PIN is only required when a meeting organizer joins their meeting over a phone.</span><span class="sxs-lookup"><span data-stu-id="b5422-110">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="b5422-111">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span><span class="sxs-lookup"><span data-stu-id="b5422-111">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="b5422-112">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="b5422-112">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="b5422-113">启用或禁用匿名呼叫者加入会议</span><span class="sxs-lookup"><span data-stu-id="b5422-113">Enable or disable anonymous callers from joining a meeting</span></span>
    
1. <span data-ttu-id="b5422-114">在**Skype for business 管理中心**的左侧导航中, 转到 "**音频会议** > **用户**"。</span><span class="sxs-lookup"><span data-stu-id="b5422-114">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**.</span></span> 
    
2. <span data-ttu-id="b5422-115">在列表中, 选择用户, 然后在 "操作" 窗格中单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="b5422-115">In the list, select the user and in the Action pane click **Edit**.</span></span> 
    
3. <span data-ttu-id="b5422-116">在用户的 "属性" 页的 "**会议选项**" 下, 选中或清除 "**允许未经身份验证的呼叫者成为会议中的第一人"。如果不是, 则它们将在大厅中等待, 直到经过身份验证的用户加入**。</span><span class="sxs-lookup"><span data-stu-id="b5422-116">On the user's properties page, under **Meeting options**, select or clear **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
4. <span data-ttu-id="b5422-117">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="b5422-117">Click **Save**.</span></span> 


    
 <span data-ttu-id="b5422-118">**使用 Windows Powershell**</span><span class="sxs-lookup"><span data-stu-id="b5422-118">**Using Windows Powershell**</span></span>
  
- <span data-ttu-id="b5422-119">请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="b5422-119">Run the following:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="b5422-120">你还需了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="b5422-120">What else should you know?</span></span>

- <span data-ttu-id="b5422-121">如果要重置 PIN, 请参阅[重置音频会议 PIN](reset-the-audio-conferencing-pin.md)。</span><span class="sxs-lookup"><span data-stu-id="b5422-121">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
    
- <span data-ttu-id="b5422-122">如果启用匿名访问或不需要 PIN 来启动会议, 则启用:</span><span class="sxs-lookup"><span data-stu-id="b5422-122">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="b5422-123">如果会议尚未启动 (会议中尚无人): 如果是组织者, 则会提示呼叫者;如果他显示 "是", 系统将提示他输入 PIN, 在用户输入 PIN 后, 会议将启动, 并且用户将加入会议。</span><span class="sxs-lookup"><span data-stu-id="b5422-123">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="b5422-124">如果会议已启动（有人已在会议中）：如果呼叫者是组织者，则不会提示您提供 PIN；会议已启动，并将呼叫者将加入。</span><span class="sxs-lookup"><span data-stu-id="b5422-124">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="b5422-125">如果已禁用匿名访问或不需要 PIN 才能启动会议, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="b5422-125">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="b5422-p103">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN. Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span><span class="sxs-lookup"><span data-stu-id="b5422-p103">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN. Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="b5422-128">如果会议已启动（有人已在会议中）：如果呼叫者是组织者，则不会提示您提供 PIN；会议已启动，并将呼叫者将加入。</span><span class="sxs-lookup"><span data-stu-id="b5422-128">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="b5422-129">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="b5422-129">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="b5422-130">为节省时间或为多个用户自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b5422-130">To save time or automate this for more than one user, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
- <span data-ttu-id="b5422-p104">对于 Windows PowerShell，Skype for Business Online 的功能是管理用户以及允许或不允许用户执行的操作。使用 Windows PowerShell，可以通过单点管理来管理 Office 365，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="b5422-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="b5422-134">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="b5422-134">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="b5422-135">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="b5422-135">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="b5422-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span><span class="sxs-lookup"><span data-stu-id="b5422-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="b5422-138">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="b5422-138">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="b5422-139">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b5422-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="b5422-140">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="b5422-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="b5422-p106">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="b5422-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b5422-143">相关主题</span><span class="sxs-lookup"><span data-stu-id="b5422-143">Related topics</span></span>

[<span data-ttu-id="b5422-144">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="b5422-144">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
