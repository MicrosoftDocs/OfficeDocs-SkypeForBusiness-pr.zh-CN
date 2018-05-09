---
title: 重置用户的会议 ID
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
description: "Learn the steps to reset a user's meeting conference ID, and get links to meeting update and migration tools. "
ms.openlocfilehash: eb827cff5bdfbc86bf85aab63a8f29165a91f034
ms.sourcegitcommit: b93d1a0012aacb164d700db0143683cb6f276bf4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2018
---
# <a name="reset-a-conference-id-for-a-user"></a><span data-ttu-id="62143-103">重置用户的会议 ID</span><span class="sxs-lookup"><span data-stu-id="62143-103">Reset a conference ID for a user</span></span>

<span data-ttu-id="62143-104">底部的会议邀请以及的拨入电话号码的呼叫者可用于向会议呼叫中包含动态的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="62143-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="62143-105">当用户拨打的电话号码时，会议自动助理会要求呼叫者输入此会议 ID，以便他们可以参加会议。</span><span class="sxs-lookup"><span data-stu-id="62143-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="62143-106">如果您的会议提供商是 Microsoft，默认情况下用户的会议 Id 设置为仅动态中。</span><span class="sxs-lookup"><span data-stu-id="62143-106">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="62143-107">遗憾的是，它不能更改业务管理中心或使用 Windows Powershell 成为静态的因为这是现在 Skype 中不受支持。</span><span class="sxs-lookup"><span data-stu-id="62143-107">Unfortunately, there's no ability to change it in the Skype for Business Admin Center or using Windows Powershell to become static, as this is now unsupported.</span></span>
<span data-ttu-id="62143-108">仅为业务和 Microsoft 团队为启用的用户进行音频会议的 Skype 仅自动设置会议 Id。</span><span class="sxs-lookup"><span data-stu-id="62143-108">Conference IDs are only automatically set only for Skype for Business and Microsoft Teams users enabled for Audio Conferencing.</span></span> 
  
## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="62143-109">重置用户的会议 ID</span><span class="sxs-lookup"><span data-stu-id="62143-109">Resetting the conference ID for a user</span></span>

<span data-ttu-id="62143-110">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="62143-110">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="62143-111">在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。</span><span class="sxs-lookup"><span data-stu-id="62143-111">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="62143-112">在页面的顶部，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="62143-112">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="62143-113">单击**会议网桥**，旁边的菜单，然后单击下拉列表中的**重置的会议 id** 。</span><span class="sxs-lookup"><span data-stu-id="62143-113">Click the menu next to **Conference Bridges**, and then click **Reset conference id** in the drop-down list.</span></span>

2. <span data-ttu-id="62143-114">在**重置的会议 id**窗口中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="62143-114">In the **Reset conference id** window, click **Ok**.</span></span> <span data-ttu-id="62143-115">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="62143-115">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="62143-116">默认情况下电子邮件发送给用户，但这可以关闭。</span><span class="sxs-lookup"><span data-stu-id="62143-116">By default, emails are sent to users, but this can be turned off.</span></span>   

<span data-ttu-id="62143-117">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="62143-117">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="62143-118">中的**Skype 业务管理中心的**中，单击**音频会议** > **用户**，选择一个用户，，，然后单击下**的会议 ID**操作窗格中的**重置**。</span><span class="sxs-lookup"><span data-stu-id="62143-118">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
2. <span data-ttu-id="62143-119">在**重置的会议 ID？**窗口中，单击**是**。</span><span class="sxs-lookup"><span data-stu-id="62143-119">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="62143-120">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="62143-120">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="62143-121">默认情况下电子邮件发送给用户，但这可以关闭。</span><span class="sxs-lookup"><span data-stu-id="62143-121">By default, emails are sent to users, but this can be turned off.</span></span>
    
> [!NOTE]
> <span data-ttu-id="62143-p105">[!注释] 重置会议 ID 后，会向用户发送包含新会议 ID 的电子邮件。此电子邮件将发送到主电子邮件地址，大多数情况下是其 Office 365 邮箱。电子邮件中包含新的会议 ID、默认拨入电话号码以及使用 Skype for Business 会议更新工具更新现有会议的说明。</span><span class="sxs-lookup"><span data-stu-id="62143-p105">After you reset the conference ID, an email with the new conference ID will be sent to the user. This email will be sent to the primary email address, in many cases, their Office 365 mailbox. The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="62143-125">我还需了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="62143-125">What else should I know?</span></span>

- <span data-ttu-id="62143-126">您可以向中包括会议 ID 和电话拨入电话号码，通过单击**发送电子邮件的会议信息**的操作窗格中的用户的电子邮件的用户发送的所有会议信息。</span><span class="sxs-lookup"><span data-stu-id="62143-126">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane.</span></span> <span data-ttu-id="62143-127">它不会发送 PIN。</span><span class="sxs-lookup"><span data-stu-id="62143-127">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="62143-128">会议 ID 将包含 7 位数字，并且您无法更改它 Skype 业务管理中心或使用 Windows PowerShell 中的长度。</span><span class="sxs-lookup"><span data-stu-id="62143-128">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="62143-129">重置之后，你可以看到新会议 ID 列在" **会议 ID**"下方。</span><span class="sxs-lookup"><span data-stu-id="62143-129">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="62143-130">如果您选择**用户**页上的用户可以查看为音频会议用户的会议 ID 底部的操作窗格下**音频会议**。</span><span class="sxs-lookup"><span data-stu-id="62143-130">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="62143-131">创建新会议 ID 后，呼叫者不能再使用旧会议 ID。</span><span class="sxs-lookup"><span data-stu-id="62143-131">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="62143-132">应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。</span><span class="sxs-lookup"><span data-stu-id="62143-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="62143-133">用户可以使用 Skype 业务会议工具更新其现有会议。</span><span class="sxs-lookup"><span data-stu-id="62143-133">The users can use Skype for Business Meeting Tool to update their existing meetings.</span></span> <span data-ttu-id="62143-134">若要查看如何下载、 安装和运行 Skype 业务会议更新工具，请参阅：</span><span class="sxs-lookup"><span data-stu-id="62143-134">To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="62143-135">Skype for Business 和 Lync 的会议更新工具</span><span class="sxs-lookup"><span data-stu-id="62143-135">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="62143-136">Skype for Business Online、会议迁移工具（64 位）</span><span class="sxs-lookup"><span data-stu-id="62143-136">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="62143-137">Skype for Business Online、会议迁移工具（32 位）</span><span class="sxs-lookup"><span data-stu-id="62143-137">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="62143-138">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="62143-138">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="62143-p108">对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="62143-p108">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="62143-142">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="62143-142">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="62143-143">为什么您需要使用 Office 365 PowerShell 中</span><span class="sxs-lookup"><span data-stu-id="62143-143">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="62143-p109">例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="62143-p109">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="62143-146">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="62143-146">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="62143-147">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="62143-147">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="62143-148">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="62143-148">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="62143-149">相关主题</span><span class="sxs-lookup"><span data-stu-id="62143-149">Related topics</span></span>

[<span data-ttu-id="62143-150">重置 PIN 的音频会议</span><span class="sxs-lookup"><span data-stu-id="62143-150">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin.md)
