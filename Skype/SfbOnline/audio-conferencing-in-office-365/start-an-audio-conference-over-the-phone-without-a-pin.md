---
title: 通过电话的 PIN 不开始音频会议
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to enable or disable anonymous callers from joining a meeting from the Skype for Business admin center or using a PowerShell script. '
ms.openlocfilehash: 8abdd9bcd61c55c7d55d896feef36afed22b312f
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703471"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin"></a><span data-ttu-id="3e61b-103">通过电话的 PIN 不开始音频会议</span><span class="sxs-lookup"><span data-stu-id="3e61b-103">Start an Audio Conference over the phone without a PIN</span></span>

<span data-ttu-id="3e61b-104">可能会干扰拨入会议以将其保留在收听音乐，因为业务或 Microsoft 团队会议组织者的 Skype 尚未启动会议的会议的会议厅中的用户。</span><span class="sxs-lookup"><span data-stu-id="3e61b-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Skype for Business or Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="3e61b-105">如果会议组织者在调用会议，默认情况下，启动会议需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="3e61b-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="3e61b-106">您可以将它设置以便任何人都可以拨号加入会议并不会提示输入 PIN 才能启动会议。</span><span class="sxs-lookup"><span data-stu-id="3e61b-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="3e61b-107">你可以使用 Skype for Business 管理中心为单个用户启用或禁用此设置。</span><span class="sxs-lookup"><span data-stu-id="3e61b-107">You can use the Skype for Business admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="3e61b-108">PIN 不需要会议组织者，如果某人已从业务或 Microsoft 团队应用程序的 Skype 开始会议。</span><span class="sxs-lookup"><span data-stu-id="3e61b-108">A PIN isn't required for the meeting organizer if someone has started the meeting from a Skype for Business or Microsoft Teams app.</span></span> <span data-ttu-id="3e61b-109">只有当会议组织者通过电话加入会议时，才需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="3e61b-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="3e61b-110">已分配的**音频会议**许可证并启用了音频会议时，将向音频用户发送会议的 PIN。</span><span class="sxs-lookup"><span data-stu-id="3e61b-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="3e61b-111">请参阅[发送对其进行音频会议信息的用户电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)和[自动发送给其音频会议设置更改时的用户的电子邮件](emails-sent-to-users-when-their-settings-change.md)。</span><span class="sxs-lookup"><span data-stu-id="3e61b-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="3e61b-112">启用或禁用匿名呼叫者加入会议</span><span class="sxs-lookup"><span data-stu-id="3e61b-112">Enable or disable anonymous callers from joining a meeting</span></span>

<span data-ttu-id="3e61b-113">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="3e61b-113">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="3e61b-114">在左侧导航窗格中，单击**用户**。</span><span class="sxs-lookup"><span data-stu-id="3e61b-114">In the left navigation, click **Users**.</span></span> 

2. <span data-ttu-id="3e61b-115">在列表中，选择一个用户，然后单击页面顶部的**编辑**。</span><span class="sxs-lookup"><span data-stu-id="3e61b-115">Select a user in the list, and then click **Edit** at the top of the page.</span></span> 

3. <span data-ttu-id="3e61b-116">单击**会议网桥**，旁边的菜单，然后单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="3e61b-116">Click the menu next to **Conference Bridges**, and then click **Edit**.</span></span>

4. <span data-ttu-id="3e61b-117">在**会议桥提供程序**窗格中，启用或禁用**允许未经身份验证的呼叫者在会议中的第一个人。如果不需要，然后他们将在会议厅中等待直至经过身份验证的用户加入**。</span><span class="sxs-lookup"><span data-stu-id="3e61b-117">In the **Conference bridge provider** pane, enable or disable **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
4. <span data-ttu-id="3e61b-118">单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="3e61b-118">Click **Apply**.</span></span> 

<span data-ttu-id="3e61b-119">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="3e61b-119">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="3e61b-120">在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议** > **用户**。</span><span class="sxs-lookup"><span data-stu-id="3e61b-120">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**.</span></span> 
    
2. <span data-ttu-id="3e61b-121">在列表中，选择用户，然后在操作窗格中，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="3e61b-121">In the list, select the user and in the Action pane click **Edit**.</span></span> 
    
3. <span data-ttu-id="3e61b-122">在用户的属性页上，在**会议选项**中，选中或清除**允许未经身份验证的呼叫者在会议中的第一个人。如果不需要，然后他们将在会议厅中等待直至经过身份验证的用户加入**。</span><span class="sxs-lookup"><span data-stu-id="3e61b-122">On the user's properties page, under **Meeting options**, select or clear **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
4. <span data-ttu-id="3e61b-123">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="3e61b-123">Click **Save**.</span></span> 


    
 <span data-ttu-id="3e61b-124">**使用 Windows Powershell**</span><span class="sxs-lookup"><span data-stu-id="3e61b-124">**Using Windows Powershell**</span></span>
  
- <span data-ttu-id="3e61b-125">请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="3e61b-125">Run the following:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="3e61b-126">你还需了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="3e61b-126">What else should you know?</span></span>

- <span data-ttu-id="3e61b-127">如果您想要重置 PIN，请参阅[重置的音频会议 PIN](reset-the-audio-conferencing-pin.md)。</span><span class="sxs-lookup"><span data-stu-id="3e61b-127">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
    
- <span data-ttu-id="3e61b-128">如果启用了匿名访问，或不需要 PIN 才能启动会议时，:</span><span class="sxs-lookup"><span data-stu-id="3e61b-128">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="3e61b-129">如果尚未启动会议 （没有一种-会议尚未）： 将提示呼叫者，如果他是组织者;如果他说是时，他将提示您为其 PIN，他输入 PIN 之后，会议的开始和用户将加入会议。</span><span class="sxs-lookup"><span data-stu-id="3e61b-129">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="3e61b-130">如果会议已启动 （人已在会议中）： 如果他是组织者和他将永远不会提示您提供 PIN; 不会提示呼叫者会议已启动，并将呼叫者将对其进行联接。</span><span class="sxs-lookup"><span data-stu-id="3e61b-130">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="3e61b-131">如果禁用匿名访问，或不需要 PIN 才能开始会议，则：</span><span class="sxs-lookup"><span data-stu-id="3e61b-131">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="3e61b-132">如果尚未启动会议 （没有一种-会议尚未）： 如果她是组织者，并且用户将从不提示您提供 PIN，不会提示呼叫者。</span><span class="sxs-lookup"><span data-stu-id="3e61b-132">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="3e61b-133">组织者的设置设置为关闭，因为会议将启动，匿名呼叫者将加入会议。</span><span class="sxs-lookup"><span data-stu-id="3e61b-133">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="3e61b-134">如果会议已启动 （人已在会议中）： 如果她是组织者，并且用户将从不提示您的 PIN，将不提示呼叫者; 会议已启动，并呼叫者将对其进行联接。</span><span class="sxs-lookup"><span data-stu-id="3e61b-134">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="3e61b-135">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="3e61b-135">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="3e61b-136">为节省时间或为多个用户自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3e61b-136">To save time or automate this for more than one user, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
-  <span data-ttu-id="3e61b-p104">对于 Windows PowerShell，Skype for Business Online 的功能是管理用户以及允许或不允许用户执行的操作。 使用 Windows PowerShell，可以通过单点管理来管理 Office 365，这样做可在有多个任务需要执行时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="3e61b-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="3e61b-140">为什么您需要使用 Office 365 PowerShell 中</span><span class="sxs-lookup"><span data-stu-id="3e61b-140">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="3e61b-141">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="3e61b-141">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="3e61b-142">Windows PowerShell 具有很多好处中快速、 简便起见和生产力通过只使用 Office 365 管理中心中的，如时要进行设置更改多个用户一次。</span><span class="sxs-lookup"><span data-stu-id="3e61b-142">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="3e61b-143">请在以下主题中了解这些优点：</span><span class="sxs-lookup"><span data-stu-id="3e61b-143">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="3e61b-144">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="3e61b-144">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="3e61b-145">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3e61b-145">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="3e61b-146">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="3e61b-146">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="3e61b-p106">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="3e61b-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="3e61b-149">相关主题</span><span class="sxs-lookup"><span data-stu-id="3e61b-149">Related topics</span></span>

[<span data-ttu-id="3e61b-150">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="3e61b-150">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
