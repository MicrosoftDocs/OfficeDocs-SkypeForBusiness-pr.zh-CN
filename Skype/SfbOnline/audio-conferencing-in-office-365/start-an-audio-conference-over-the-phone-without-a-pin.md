---
title: 开始音频会议通过 PIN 没有电话
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to enable or disable anonymous callers from joining a meeting from the Skype for Business admin center or using a PowerShell script. '
ms.openlocfilehash: b4244647674f25a10b6ca447a6ee8b4d23b36a9f
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2018
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin"></a><span data-ttu-id="cc4e3-103">开始音频会议通过 PIN 没有电话</span><span class="sxs-lookup"><span data-stu-id="cc4e3-103">Start an Audio Conference over the phone without a PIN</span></span>

<span data-ttu-id="cc4e3-104">它可能是令人沮丧的用户拨入的在会议厅中听音乐，因为 Skype 的业务或 Microsoft 小组会议的组织者尚未启动会议召开的会议。</span><span class="sxs-lookup"><span data-stu-id="cc4e3-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Skype for Business or Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="cc4e3-105">如果会议组织者调用参加会议时，默认情况下，启动会议需要一个 PIN。</span><span class="sxs-lookup"><span data-stu-id="cc4e3-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="cc4e3-106">您可以设置它，以便任何人都可以拨号加入会议并不会提示输入 PIN 开始举行会议。</span><span class="sxs-lookup"><span data-stu-id="cc4e3-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="cc4e3-107">你可以使用 Skype for Business 管理中心为单个用户启用或禁用此设置。</span><span class="sxs-lookup"><span data-stu-id="cc4e3-107">You can use the Skype for Business admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="cc4e3-108">PIN 不需为会议组织者，如果有人从 Skype 业务或 Microsoft 小组应用程序的启动会议。</span><span class="sxs-lookup"><span data-stu-id="cc4e3-108">A PIN isn't required for the meeting organizer if someone has started the meeting from a Skype for Business or Microsoft Teams app.</span></span> <span data-ttu-id="cc4e3-109">只有当会议组织者通过电话加入会议时，才需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="cc4e3-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="cc4e3-110">当它们被分配**音频会议**许可并启用了音频会议会议的引出发给音频的用户。</span><span class="sxs-lookup"><span data-stu-id="cc4e3-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="cc4e3-111">请参阅[发送给用户，并他们的音频会议信息的电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)和[电子邮件自动发送给用户的音频会议设置更改时](emails-sent-to-users-when-their-settings-change.md)。</span><span class="sxs-lookup"><span data-stu-id="cc4e3-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="cc4e3-112">启用或禁用匿名呼叫者加入会议</span><span class="sxs-lookup"><span data-stu-id="cc4e3-112">Enable or disable anonymous callers from joining a meeting</span></span>

1. <span data-ttu-id="cc4e3-113">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="cc4e3-113">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="cc4e3-114">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="cc4e3-114">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="cc4e3-115">在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议** > **用户**。</span><span class="sxs-lookup"><span data-stu-id="cc4e3-115">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**.</span></span> 
    
4. <span data-ttu-id="cc4e3-116">在列表中，选择该用户并在操作窗格中单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="cc4e3-116">In the list, select the user and in the Action pane click **Edit**.</span></span> 
    
5. <span data-ttu-id="cc4e3-117">在用户的属性页，在**会议选项**中，选中或清除**允许未经身份验证的调用方将在会议中的第一人。如果不是，然后他们将等到在休息室已经过身份验证的用户加入**。</span><span class="sxs-lookup"><span data-stu-id="cc4e3-117">On the user's properties page, under **Meeting options**, select or clear **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
6. <span data-ttu-id="cc4e3-118">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="cc4e3-118">Click **Save**.</span></span> 
    
 <span data-ttu-id="cc4e3-119">**若要启用或禁用对所有用户的会议使用 Windows Powershell 的匿名呼叫者**</span><span class="sxs-lookup"><span data-stu-id="cc4e3-119">**To enable or disable anonymous callers to all of your user's meetings using Windows Powershell**</span></span>
  
- <span data-ttu-id="cc4e3-120">请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="cc4e3-120">Run the following:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="cc4e3-121">你还需了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="cc4e3-121">What else should you know?</span></span>

- <span data-ttu-id="cc4e3-122">如果要重置 PIN，请参阅[重置用户的音频会议 PIN](reset-the-audio-conferencing-pin-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="cc4e3-122">If you want to reset the PIN, see [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin-for-a-user.md).</span></span>
    
- <span data-ttu-id="cc4e3-123">如果启用了匿名访问，或如果不要求 PIN 来召开会议：</span><span class="sxs-lookup"><span data-stu-id="cc4e3-123">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="cc4e3-124">如果尚未启动会议 （没有任何人在会议中尚未）： 呼叫者将会提示您，如果他是组织者;如果他说是，他将会提示您为自己的 PIN，并他输入 PIN 后，会议将开始用户将加入会议。</span><span class="sxs-lookup"><span data-stu-id="cc4e3-124">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="cc4e3-125">如果此时会议已启动 （其他人已在会议中）： 呼叫者不会提示，如果他是组织者，他将永远不会被提示针;此时会议已启动，并调用方将加入它。</span><span class="sxs-lookup"><span data-stu-id="cc4e3-125">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="cc4e3-126">如果禁用匿名访问，或如果不要求 PIN 来召开会议时，则：</span><span class="sxs-lookup"><span data-stu-id="cc4e3-126">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="cc4e3-127">如果尚未启动会议 （没有任何人在会议中尚未）： 如果她是组织者，而且她将永远不会提示您输入 PIN，将不提示调用方。</span><span class="sxs-lookup"><span data-stu-id="cc4e3-127">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="cc4e3-128">管理器的设置被设置为 off，因为会议的开始和匿名呼叫者将参加会议。</span><span class="sxs-lookup"><span data-stu-id="cc4e3-128">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="cc4e3-129">如果此时会议已启动 （其他人已在会议中）： 呼叫者将不会提示您，如果她是组织者，而且她将永远不会提示您输入 PIN，; 此时会议已启动，并调用方将加入它。</span><span class="sxs-lookup"><span data-stu-id="cc4e3-129">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="cc4e3-130">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="cc4e3-130">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="cc4e3-131">为节省时间或为多个用户自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cc4e3-131">To save time or automate this for more than one user, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
-  <span data-ttu-id="cc4e3-p104">对于 Windows PowerShell，Skype for Business Online 的功能是管理用户以及允许或不允许用户执行的操作。 使用 Windows PowerShell，可以通过单点管理来管理 Office 365，这样做可在有多个任务需要执行时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="cc4e3-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="cc4e3-135">为什么需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc4e3-135">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="cc4e3-136">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="cc4e3-136">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="cc4e3-137">Windows PowerShell 许多相比具有的优势在速度、 简易性和生产率仅使用 Office 365 管理中心，例如当您所更改的设置对于许多用户一次。</span><span class="sxs-lookup"><span data-stu-id="cc4e3-137">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="cc4e3-138">请在以下主题中了解这些优点：</span><span class="sxs-lookup"><span data-stu-id="cc4e3-138">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="cc4e3-139">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="cc4e3-139">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="cc4e3-140">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="cc4e3-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="cc4e3-141">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="cc4e3-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="cc4e3-p106">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="cc4e3-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="cc4e3-144">相关主题</span><span class="sxs-lookup"><span data-stu-id="cc4e3-144">Related topics</span></span>

[<span data-ttu-id="cc4e3-145">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="cc4e3-145">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
