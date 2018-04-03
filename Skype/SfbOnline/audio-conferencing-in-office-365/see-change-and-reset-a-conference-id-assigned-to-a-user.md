---
title: 请参阅、 更改和重置会议 ID 分配给用户
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
description: "Learn how to assign a conference ID to a user in Skype for Business and what the conference ID's parameters should be. "
ms.openlocfilehash: 12fe2b0f425f58dca8272f5f0536ba5393b2f76c
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2018
---
# <a name="see-change-and-reset-a-conference-id-assigned-to-a-user"></a><span data-ttu-id="666eb-103">请参阅、 更改和重置会议 ID 分配给用户</span><span class="sxs-lookup"><span data-stu-id="666eb-103">See, change, and reset a conference ID assigned to a user</span></span>

<span data-ttu-id="666eb-104">会议 ID 自动分配给为业务或 Microsoft 小组的用户 Skype 为 Office 365 中的音频会议设置并使用 Microsoft 作为音频会议提供商时。</span><span class="sxs-lookup"><span data-stu-id="666eb-104">A conferencing ID is automatically assigned to a Skype for Business or Microsoft Teams user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="666eb-105">指定的会议 ID 可以是静态或动态，以及时安排的会议，在会议邀请中发送。</span><span class="sxs-lookup"><span data-stu-id="666eb-105">The conference ID assigned can be either static or dynamic and is sent in the meeting invite when the meeting is scheduled.</span></span>
  
<span data-ttu-id="666eb-106">当您组织中的人不想记得的随机数; 使用静态标识符他们可以选择一定数量或使用一个容易记住。</span><span class="sxs-lookup"><span data-stu-id="666eb-106">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember.</span></span> <span data-ttu-id="666eb-107">当使用动态会议 Id 时，每个会议用户计划将获得分配唯一的会议 id。</span><span class="sxs-lookup"><span data-stu-id="666eb-107">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="666eb-108">如果您想要分配动态而非静态的会议 Id，[转到此处](using-audio-conferencing-dynamic-ids-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="666eb-108">If you want to assign dynamic rather than static conference IDs, [go here](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="666eb-109">一个静态的会议 ID 将自动创建并指派给用户，尽管有时可能当用户不想使用它并且想要将其设置为某个数字、 或当用户忘记或丢失了他们的会议 id。</span><span class="sxs-lookup"><span data-stu-id="666eb-109">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="666eb-110">您可以使用**业务管理中心的 Skype**和 Windows PowerShell 查看、 更改和重置其会议 id。</span><span class="sxs-lookup"><span data-stu-id="666eb-110">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="666eb-111">电子邮件将被发送到用户的会议 ID 和默认音频会议电话号码，或如果您重置会议 ID 将会包含会议 ID，但不是一个 PIN 发送不同的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="666eb-111">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span>
  
## <a name="view-and-change-conference-ids"></a><span data-ttu-id="666eb-112">查看和更改会议 Id</span><span class="sxs-lookup"><span data-stu-id="666eb-112">View and change conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="666eb-113">若要查看会议 ID</span><span class="sxs-lookup"><span data-stu-id="666eb-113">To view the conference ID</span></span>

<span data-ttu-id="666eb-114">您可以查看其会议 ID 并将其发送给用户。</span><span class="sxs-lookup"><span data-stu-id="666eb-114">You can view their conference ID and send it to users.</span></span>
  
1. <span data-ttu-id="666eb-115">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="666eb-115">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="666eb-116">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="666eb-116">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="666eb-117">在**Skype 的业务管理中心**> **音频会议** > **用户**，选择的用户的需求会议 id。</span><span class="sxs-lookup"><span data-stu-id="666eb-117">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>
    
4. <span data-ttu-id="666eb-118">在操作页上，查看在**会议 ID**下。</span><span class="sxs-lookup"><span data-stu-id="666eb-118">In the Action page, look under **Conference ID**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="666eb-119">可以在包含会议 ID 和音频的电话号码后，通过单击**将会议信息通过电子邮件发送**链接选择**用户**页上的用户的电子邮件向用户发送所有会议信息。</span><span class="sxs-lookup"><span data-stu-id="666eb-119">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>
  
    <span data-ttu-id="666eb-120">您可以使用 Windows PowerShell 来查看用户的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="666eb-120">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="666eb-121">为此，请运行：</span><span class="sxs-lookup"><span data-stu-id="666eb-121">To do so, run:</span></span>
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    <span data-ttu-id="666eb-122">请参阅[获取 CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 )以了解有关该 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="666eb-122">See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.</span></span>
    
### <a name="to-assign-or-change-the-conference-id"></a><span data-ttu-id="666eb-123">若要分配或更改会议 ID</span><span class="sxs-lookup"><span data-stu-id="666eb-123">To assign or change the conference ID</span></span>

<span data-ttu-id="666eb-124">您可以分配或更改用户的会议 ID，如果，例如，某人想很容易记住一个会议 ID。</span><span class="sxs-lookup"><span data-stu-id="666eb-124">You can assign or change a conference ID for a user if, for example, someone wants a conference ID that's easy to remember.</span></span>

  > [!NOTE]
  > <span data-ttu-id="666eb-125">业务管理中心为 Skype 不能用于编辑自动创建后，一个会议 ID，但您可以使用 Windows PowerShell 编辑或更改已设置一个会议 ID。</span><span class="sxs-lookup"><span data-stu-id="666eb-125">The Skype for Business admin center can't be used to edit a conference ID that has been automatically created, but you can use Windows PowerShell to edit or change a conference ID that you have set.</span></span> 
     
<span data-ttu-id="666eb-126">若要编辑或更改用户的会议 ID，请运行：</span><span class="sxs-lookup"><span data-stu-id="666eb-126">To edit or change the conference ID for a user, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964
  ```

  > [!TIP]
  > <span data-ttu-id="666eb-127">会议 ID 必须包含 7 位数字，并不能在 Skype 业务管理中心或使用 Windows PowerShell 中进行更改。</span><span class="sxs-lookup"><span data-stu-id="666eb-127">A conference ID must contain 7 digits, and you can't change it in the Skype for Business admin center or by using Windows PowerShell.</span></span> 
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="666eb-128">若要重置的会议 ID</span><span class="sxs-lookup"><span data-stu-id="666eb-128">To reset the conference ID</span></span>

<span data-ttu-id="666eb-129">您可以重置用户的会议 ID 如果，例如，如果他们忘记了。</span><span class="sxs-lookup"><span data-stu-id="666eb-129">You can reset a conference ID for a user if, for example, if they forget it.</span></span>
  
1. <span data-ttu-id="666eb-130">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="666eb-130">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="666eb-131">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="666eb-131">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="666eb-132">在**Skype 的业务管理中心**> **音频会议** > **用户**，在**会议 ID**、 操作窗格中单击**重置**。</span><span class="sxs-lookup"><span data-stu-id="666eb-132">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="666eb-133">在**会议 ID 重置？**窗口中，单击**是**。</span><span class="sxs-lookup"><span data-stu-id="666eb-133">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="666eb-134">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="666eb-134">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
    
    <span data-ttu-id="666eb-135">可以通过使用 Windows PowerShell 重置用户的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="666eb-135">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="666eb-136">若要执行此操作，请运行：</span><span class="sxs-lookup"><span data-stu-id="666eb-136">To do this, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetLeaderPIN 8271964
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="666eb-137">你还需了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="666eb-137">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="666eb-138">创建新的会议 ID 或其中一个将被重置后，调用方不能使用旧的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="666eb-138">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="666eb-139">应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。</span><span class="sxs-lookup"><span data-stu-id="666eb-139">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="666eb-140">用户可以使用 Skype 业务会议迁移工具来更新其现有的会议。</span><span class="sxs-lookup"><span data-stu-id="666eb-140">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="666eb-141">若要了解如何下载、 安装和运行该工具，请参阅：[为业务和 Lync Skype 会议更新工具](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)、 [Skype 业务在线，会议迁移工具 （64 位）](http://go.microsoft.com/fwlink/?LinkID=626047)和[Skype 的业务联机，会议迁移工具 （32 位）](https://www.microsoft.com/en-us/download/details.aspx?id=54079)。</span><span class="sxs-lookup"><span data-stu-id="666eb-141">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
- <span data-ttu-id="666eb-142">请参阅 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) 以了解有关 cmdlet 的更多信息。</span><span class="sxs-lookup"><span data-stu-id="666eb-142">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>
    
- <span data-ttu-id="666eb-143">会议 ID 必须满足中位数设置音频会议桥的长度。</span><span class="sxs-lookup"><span data-stu-id="666eb-143">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="666eb-144">不能使用字母或特殊字符在会议 Id;可以使用数字。</span><span class="sxs-lookup"><span data-stu-id="666eb-144">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
    
- <span data-ttu-id="666eb-145">会议 ID 的所有音频会议用户将默认情况下，7 位，不能更改的数字位数。</span><span class="sxs-lookup"><span data-stu-id="666eb-145">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>
    
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="666eb-146">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="666eb-146">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="666eb-p109">对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="666eb-p109">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="666eb-150">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="666eb-150">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="666eb-151">为什么需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="666eb-151">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="666eb-p110">例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="666eb-p110">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="666eb-154">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="666eb-154">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="666eb-155">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="666eb-155">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="666eb-156">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="666eb-156">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="666eb-157">相关主题</span><span class="sxs-lookup"><span data-stu-id="666eb-157">Related topics</span></span>

[<span data-ttu-id="666eb-158">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="666eb-158">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

