---
title: "重置用户的会议 ID"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn the steps to reset a user''s meeting conference ID, and get links to meeting update and migration tools. '
ms.openlocfilehash: 2f2cbd6efa61e05defb17ef05f86fd9a228987ac
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2017
---
# <a name="reset-a-conference-id-for-a-user"></a><span data-ttu-id="623d4-103">重置用户的会议 ID</span><span class="sxs-lookup"><span data-stu-id="623d4-103">Reset a conference ID for a user</span></span>

<span data-ttu-id="623d4-104">您的组织尚未为动态会议 Id 已启用，Skype 为业务或 Microsoft 小组的用户启用了使用 Microsoft 提供的音频会议时，将自动创建一个静态的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="623d4-104">When your organizations hasn't been enabled for dynamic conference IDs, a static conference ID is automatically created when a Skype for Business or Microsoft Teams user is enabled for Audio Conferencing using Microsoft as the provider.</span></span> <span data-ttu-id="623d4-105">此会议 ID 将包括底部的会议邀请以及调用方可以用于对会议所拨入的电话号码。</span><span class="sxs-lookup"><span data-stu-id="623d4-105">This conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="623d4-106">当用户拨打的电话号码时，自动助理会议会要求调用方输入此会议 ID，这样他们可以参加会议。</span><span class="sxs-lookup"><span data-stu-id="623d4-106">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="623d4-107">如果是您的会议提供商，默认情况下用户的会议 Id 设置为仅动态中。</span><span class="sxs-lookup"><span data-stu-id="623d4-107">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="623d4-108">遗憾的是，您不能将业务管理中心或使用 Windows Powershell Skype。</span><span class="sxs-lookup"><span data-stu-id="623d4-108">Unfortunately, you won't be able to change it in the Skype for Business Admin Center or using Windows Powershell.</span></span> <span data-ttu-id="623d4-109">您将需要与 Microsoft 支持部门联系。</span><span class="sxs-lookup"><span data-stu-id="623d4-109">You will have to contact Microsoft support.</span></span> 
  
<span data-ttu-id="623d4-110">当您组织中的人不想记得的随机数; 使用静态标识符他们可以选择一定数量或使用一个容易记住。</span><span class="sxs-lookup"><span data-stu-id="623d4-110">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember.</span></span> <span data-ttu-id="623d4-111">当使用动态会议 Id 时，每个会议用户计划将获得分配唯一的会议 id。</span><span class="sxs-lookup"><span data-stu-id="623d4-111">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="623d4-112">如果您想要分配动态而非静态的会议 Id，[转到此处](using-audio-conferencing-dynamic-ids-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="623d4-112">If you want to assign dynamic rather than static conference IDs, [go here](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="623d4-113">会议 Id 只能自动设置只能用于 Skype 业务和 Microsoft 小组为启用的用户的音频会议作为其音频会议提供商使用 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="623d4-113">Conference IDs are only automatically set only for Skype for Business and Microsoft Teams users enabled for Audio Conferencing using Microsoft as their audio conferencing provider.</span></span> <span data-ttu-id="623d4-114">如果您需要重置用户正在使用第三方音频会议提供商 (ACP) 的会议 ID，您需要为该用户在属性页上手动输入会议 ID。</span><span class="sxs-lookup"><span data-stu-id="623d4-114">If you need to reset a conference ID for a user who is using a third-party audio conferencing provider (ACP), you will need to manually enter a conference ID on the properties page for the user.</span></span>
  
## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="623d4-115">重置用户的会议 ID</span><span class="sxs-lookup"><span data-stu-id="623d4-115">Resetting the conference ID for a user</span></span>

1. <span data-ttu-id="623d4-116">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="623d4-116">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="623d4-117">请转到**Office 365 管理中心** > **业务的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="623d4-117">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="623d4-118">在**Skype 的业务管理中心**，单击**音频会议** > **用户**选择一个用户，然后在**会议 ID**下的操作窗格中单击**重置**。</span><span class="sxs-lookup"><span data-stu-id="623d4-118">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
4. <span data-ttu-id="623d4-119">在**会议 ID 重置？**窗口中，单击**是**。</span><span class="sxs-lookup"><span data-stu-id="623d4-119">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="623d4-120">会议 ID 将自动创建和电子邮件发送给用户提供最新的会议 id。</span><span class="sxs-lookup"><span data-stu-id="623d4-120">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="623d4-121">默认情况下，电子邮件将发送给用户，但这可以被关闭。</span><span class="sxs-lookup"><span data-stu-id="623d4-121">By default, emails are sent to users, but this can be turned off.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="623d4-p106">[!注释] 重置会议 ID 后，会向用户发送包含新会议 ID 的电子邮件。此电子邮件将发送到主电子邮件地址，大多数情况下是其 Office 365 邮箱。电子邮件中包含新的会议 ID、默认拨入电话号码以及使用 Skype for Business 会议更新工具更新现有会议的说明。</span><span class="sxs-lookup"><span data-stu-id="623d4-p106">After you reset the conference ID, an email with the new conference ID will be sent to the user. This email will be sent to the primary email address, in many cases, their Office 365 mailbox. The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
## <a name="what-else-should-i-know"></a><span data-ttu-id="623d4-125">我还需了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="623d4-125">What else should I know?</span></span>

- <span data-ttu-id="623d4-126">可以在电子邮件的用户在操作窗格中单击**将会议信息通过电子邮件发送**包含会议 ID 和拨入电话号码向用户发送的所有会议信息。</span><span class="sxs-lookup"><span data-stu-id="623d4-126">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane.</span></span> <span data-ttu-id="623d4-127">它不会发送 PIN。</span><span class="sxs-lookup"><span data-stu-id="623d4-127">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="623d4-128">会议 ID 将包含 7 位数字，并且您无法更改其长度在 Skype 业务管理中心或使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="623d4-128">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="623d4-129">重置之后，你可以看到新会议 ID 列在" **会议 ID**"下方。</span><span class="sxs-lookup"><span data-stu-id="623d4-129">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="623d4-130">当您选择**用户**页上的用户可以查看用户的音频会议的会议 ID 底部的操作窗格下**音频会议**。</span><span class="sxs-lookup"><span data-stu-id="623d4-130">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="623d4-131">创建一个新的会议 ID 后，调用方不能使用旧的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="623d4-131">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="623d4-132">应通知用户重新安排现有会议，以确保新的会议 ID 添加到邀请的邀请。</span><span class="sxs-lookup"><span data-stu-id="623d4-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="623d4-133">用户可以使用 Skype 业务会议工具，以更新其现有的会议。</span><span class="sxs-lookup"><span data-stu-id="623d4-133">The users can use Skype for Business Meeting Tool to update their existing meetings.</span></span> <span data-ttu-id="623d4-134">若要了解如何下载、 安装和运行 Skype 业务会议更新工具，请参阅：</span><span class="sxs-lookup"><span data-stu-id="623d4-134">To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="623d4-135">Skype for Business 和 Lync 的会议更新工具</span><span class="sxs-lookup"><span data-stu-id="623d4-135">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="623d4-136">Skype for Business Online、会议迁移工具（64 位）</span><span class="sxs-lookup"><span data-stu-id="623d4-136">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="623d4-137">Skype for Business Online、会议迁移工具（32 位）</span><span class="sxs-lookup"><span data-stu-id="623d4-137">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="623d4-138">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="623d4-138">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="623d4-p109">对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="623d4-p109">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="623d4-142">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="623d4-142">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="623d4-143">为什么需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="623d4-143">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="623d4-p110">例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="623d4-p110">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="623d4-146">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="623d4-146">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="623d4-147">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="623d4-147">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="623d4-148">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="623d4-148">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="623d4-149">相关主题</span><span class="sxs-lookup"><span data-stu-id="623d4-149">Related topics</span></span>

[<span data-ttu-id="623d4-150">重置用户的音频会议 PIN</span><span class="sxs-lookup"><span data-stu-id="623d4-150">Reset the Audio Conferencing PIN for a user</span></span>](reset-the-audio-conferencing-pin-for-a-user.md)
