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
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Learn the steps to reset a user's meeting conference ID, and get links to meeting update and migration tools. "
ms.openlocfilehash: 3c40c4bb59dd6628730542f73d8bdbddae7b9ad7
ms.sourcegitcommit: a72a1b71a8ef8e9581038503130c2c1a58a4abdb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
---
# <a name="reset-a-conference-id-for-a-user"></a><span data-ttu-id="cc375-103">重置用户的会议 ID</span><span class="sxs-lookup"><span data-stu-id="cc375-103">Reset a conference ID for a user</span></span>

<span data-ttu-id="cc375-104">包含底部的会议可由调用方调用中的会议所拨入的电话号码以及邀请是一个动态的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="cc375-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="cc375-105">当用户拨打的电话号码时，自动助理会议会要求调用方输入此会议 ID，这样他们可以参加会议。</span><span class="sxs-lookup"><span data-stu-id="cc375-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cc375-106">如果是您的会议提供商，默认情况下用户的会议 Id 设置为仅动态中。</span><span class="sxs-lookup"><span data-stu-id="cc375-106">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="cc375-107">遗憾的是，它不能将业务管理中心或使用 Windows Powershell 成为静态的因为这是现在 Skype 不受支持。</span><span class="sxs-lookup"><span data-stu-id="cc375-107">Unfortunately, there's no ability to change it in the Skype for Business Admin Center or using Windows Powershell to become static, as this is now unsupported.</span></span>
<span data-ttu-id="cc375-108">会议 Id 只能自动设置只能用于 Skype 业务和 Microsoft 小组为启用的用户的音频会议。</span><span class="sxs-lookup"><span data-stu-id="cc375-108">Conference IDs are only automatically set only for Skype for Business and Microsoft Teams users enabled for Audio Conferencing.</span></span> 
  
## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="cc375-109">重置用户的会议 ID</span><span class="sxs-lookup"><span data-stu-id="cc375-109">Resetting the conference ID for a user</span></span>

<span data-ttu-id="cc375-110">**使用 Microsoft 小组和 Skype 业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="cc375-110">**Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="cc375-111">在左侧的导航中，单击**用户**，然后从可用的用户列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="cc375-111">In the left navigation, click **Users**, and then select the user from teh list of available users.</span></span>

2. <span data-ttu-id="cc375-112">在页面的顶部，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="cc375-112">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="cc375-113">单击**会议桥**边上的菜单，然后单击下拉列表中的**重置会议 id** 。</span><span class="sxs-lookup"><span data-stu-id="cc375-113">Click the menu next to **Conference Bridges**, and then click **Reset conference id** in the drop-down list.</span></span>

2. <span data-ttu-id="cc375-114">在**重置会议 id**窗口中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="cc375-114">In the **Reset conference id** window, click **Ok**.</span></span> <span data-ttu-id="cc375-115">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="cc375-115">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="cc375-116">默认情况下，电子邮件将发送给用户，但这可以被关闭。</span><span class="sxs-lookup"><span data-stu-id="cc375-116">By default, emails are sent to users, but this can be turned off.</span></span>   

<span data-ttu-id="cc375-117">**使用 Skype 业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="cc375-117">**Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="cc375-118">在**Skype 的业务管理中心**，单击**音频会议** > **用户**选择一个用户，然后在**会议 ID**下的操作窗格中单击**重置**。</span><span class="sxs-lookup"><span data-stu-id="cc375-118">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
2. <span data-ttu-id="cc375-119">在**会议 ID 重置？**窗口中，单击**是**。</span><span class="sxs-lookup"><span data-stu-id="cc375-119">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="cc375-120">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="cc375-120">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="cc375-121">默认情况下，电子邮件将发送给用户，但这可以被关闭。</span><span class="sxs-lookup"><span data-stu-id="cc375-121">By default, emails are sent to users, but this can be turned off.</span></span>
    
> [!NOTE]
> <span data-ttu-id="cc375-p105">[!注释] 重置会议 ID 后，会向用户发送包含新会议 ID 的电子邮件。此电子邮件将发送到主电子邮件地址，大多数情况下是其 Office 365 邮箱。电子邮件中包含新的会议 ID、默认拨入电话号码以及使用 Skype for Business 会议更新工具更新现有会议的说明。</span><span class="sxs-lookup"><span data-stu-id="cc375-p105">After you reset the conference ID, an email with the new conference ID will be sent to the user. This email will be sent to the primary email address, in many cases, their Office 365 mailbox. The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
## <a name="what-else-should-i-know"></a><span data-ttu-id="cc375-125">我还需了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="cc375-125">What else should I know?</span></span>

- <span data-ttu-id="cc375-126">可以在电子邮件的用户在操作窗格中单击**将会议信息通过电子邮件发送**包含会议 ID 和拨入电话号码向用户发送的所有会议信息。</span><span class="sxs-lookup"><span data-stu-id="cc375-126">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane.</span></span> <span data-ttu-id="cc375-127">它不会发送 PIN。</span><span class="sxs-lookup"><span data-stu-id="cc375-127">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="cc375-128">会议 ID 将包含 7 位数字，并且您无法更改其长度在 Skype 业务管理中心或使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="cc375-128">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="cc375-129">重置之后，你可以看到新会议 ID 列在" **会议 ID**"下方。</span><span class="sxs-lookup"><span data-stu-id="cc375-129">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="cc375-130">当您选择**用户**页上的用户可以查看用户的音频会议的会议 ID 底部的操作窗格下**音频会议**。</span><span class="sxs-lookup"><span data-stu-id="cc375-130">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="cc375-131">创建新会议 ID 后，呼叫者不能再使用旧会议 ID。</span><span class="sxs-lookup"><span data-stu-id="cc375-131">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="cc375-132">应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。</span><span class="sxs-lookup"><span data-stu-id="cc375-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="cc375-133">用户可以使用 Skype 业务会议工具，以更新其现有的会议。</span><span class="sxs-lookup"><span data-stu-id="cc375-133">The users can use Skype for Business Meeting Tool to update their existing meetings.</span></span> <span data-ttu-id="cc375-134">若要了解如何下载、 安装和运行 Skype 业务会议更新工具，请参阅：</span><span class="sxs-lookup"><span data-stu-id="cc375-134">To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="cc375-135">Skype for Business 和 Lync 的会议更新工具</span><span class="sxs-lookup"><span data-stu-id="cc375-135">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="cc375-136">Skype for Business Online、会议迁移工具（64 位）</span><span class="sxs-lookup"><span data-stu-id="cc375-136">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="cc375-137">Skype for Business Online、会议迁移工具（32 位）</span><span class="sxs-lookup"><span data-stu-id="cc375-137">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="cc375-138">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="cc375-138">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="cc375-p108">对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="cc375-p108">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="cc375-142">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="cc375-142">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="cc375-143">为什么需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc375-143">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="cc375-p109">例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="cc375-p109">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="cc375-146">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="cc375-146">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="cc375-147">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="cc375-147">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="cc375-148">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="cc375-148">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="cc375-149">相关主题</span><span class="sxs-lookup"><span data-stu-id="cc375-149">Related topics</span></span>

[<span data-ttu-id="cc375-150">重置用户的音频会议 PIN</span><span class="sxs-lookup"><span data-stu-id="cc375-150">Reset the Audio Conferencing PIN for a user</span></span>](reset-the-audio-conferencing-pin-for-a-user.md)
