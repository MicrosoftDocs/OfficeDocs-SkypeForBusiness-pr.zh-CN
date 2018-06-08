---
title: 请参阅、 更改和重置会议 ID 分配给用户
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: "Learn how to assign a conference ID to a user in Skype for Business and what the conference ID's parameters should be. "
ms.openlocfilehash: eccbcd31add14026d2b5f3a57348ae5d6f1db2a5
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703401"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user"></a><span data-ttu-id="9b12e-103">查看和重置分配给用户的会议 ID</span><span class="sxs-lookup"><span data-stu-id="9b12e-103">View and reset a conference ID assigned to a user</span></span>

<span data-ttu-id="9b12e-104">自动分配给业务或 Microsoft 团队用户 Skype 会议 ID，在为 Office 365 中的音频会议设置并使用 Microsoft 作为音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="9b12e-104">A conferencing ID is automatically assigned to a Skype for Business or Microsoft Teams user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="9b12e-105">安排会议时，将会议邀请中发送分配的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="9b12e-105">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="9b12e-106">将获取每个用户安排的会议分配一个唯一的会议 id。</span><span class="sxs-lookup"><span data-stu-id="9b12e-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="9b12e-107">虽然会议 ID 将自动创建并分配给用户，有时可能时用户不是要使用此并且您希望将其设置为一个特定号码，或当用户忘记或丢失其会议 id。</span><span class="sxs-lookup"><span data-stu-id="9b12e-107">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="9b12e-108">您可以使用**Skype 的业务管理中心**和 Windows PowerShell 查看、 更改和重置用户的会议 id。</span><span class="sxs-lookup"><span data-stu-id="9b12e-108">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="9b12e-109">电子邮件将发送到用户的会议 ID 和默认音频会议的电话号码，或如果重置的会议 ID 将将包括会议 ID，但不是 PIN 发送不同的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9b12e-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="9b12e-110">有关重置会议组织者的 PIN，[转到此处](reset-a-conference-id-for-a-user.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9b12e-110">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="9b12e-111">查看和重置会议 Id</span><span class="sxs-lookup"><span data-stu-id="9b12e-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="9b12e-112">若要查看的会议 ID</span><span class="sxs-lookup"><span data-stu-id="9b12e-112">To view the conference ID</span></span>

<span data-ttu-id="9b12e-113">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="9b12e-113">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="9b12e-114">在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。</span><span class="sxs-lookup"><span data-stu-id="9b12e-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="9b12e-115">在页面的顶部，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="9b12e-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="9b12e-116">在**音频会议**下, 查找下**的会议 ID**。</span><span class="sxs-lookup"><span data-stu-id="9b12e-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="9b12e-117">您可以向中包括的会议 ID 和音频的电话号码，通过单击**发送电子邮件中的会议信息**链接的电子邮件的用户发送的所有会议信息。</span><span class="sxs-lookup"><span data-stu-id="9b12e-117">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info in email** link.</span></span>
  
<span data-ttu-id="9b12e-118">您可以使用 Windows PowerShell 查看用户的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="9b12e-118">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="9b12e-119">为此，请运行：</span><span class="sxs-lookup"><span data-stu-id="9b12e-119">To do so, run:</span></span>
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


<span data-ttu-id="9b12e-120">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="9b12e-120">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="9b12e-121">您可以查看其会议 ID，并将其发送给用户。</span><span class="sxs-lookup"><span data-stu-id="9b12e-121">You can view their conference ID and send it to users.</span></span>
  
1. <span data-ttu-id="9b12e-122">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="9b12e-122">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="9b12e-123">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="9b12e-123">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="9b12e-124">在**业务管理中心的 Skype**> **音频会议** > **用户**选择的用户需要会议 id。</span><span class="sxs-lookup"><span data-stu-id="9b12e-124">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>
    
4. <span data-ttu-id="9b12e-125">在操作页上，在**会议 ID**下查看。</span><span class="sxs-lookup"><span data-stu-id="9b12e-125">In the Action page, look under **Conference ID**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="9b12e-126">您可以向中包括的会议 ID 和音频的电话号码后，通过单击**发送电子邮件的会议信息**链接选择**用户**页上的用户的电子邮件的用户发送的所有会议信息。</span><span class="sxs-lookup"><span data-stu-id="9b12e-126">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="9b12e-127">您可以使用 Windows PowerShell 查看用户的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="9b12e-127">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="9b12e-128">为此，请运行：</span><span class="sxs-lookup"><span data-stu-id="9b12e-128">To do so, run:</span></span>
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="9b12e-129">若要重置的会议 ID</span><span class="sxs-lookup"><span data-stu-id="9b12e-129">To reset the conference ID</span></span>

<span data-ttu-id="9b12e-130">您可以重置用户的会议 ID if，例如，如果他们忘记了。</span><span class="sxs-lookup"><span data-stu-id="9b12e-130">You can reset a conference ID for a user if, for example, if they forget it.</span></span>
  
<span data-ttu-id="9b12e-131">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="9b12e-131">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="9b12e-132">在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。</span><span class="sxs-lookup"><span data-stu-id="9b12e-132">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="9b12e-133">在页面的顶部，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="9b12e-133">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="9b12e-134">在**音频会议**，下单击**重置会议 ID**。</span><span class="sxs-lookup"><span data-stu-id="9b12e-134">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="9b12e-135">在**重置的会议 ID**窗口中，单击**重置**。</span><span class="sxs-lookup"><span data-stu-id="9b12e-135">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="9b12e-136">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="9b12e-136">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
    
    <span data-ttu-id="9b12e-137">您可以通过使用 Windows PowerShell 重置用户的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="9b12e-137">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="9b12e-138">若要执行此操作，请运行：</span><span class="sxs-lookup"><span data-stu-id="9b12e-138">To do this, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

<span data-ttu-id="9b12e-139">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="9b12e-139">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="9b12e-140">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="9b12e-140">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="9b12e-141">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="9b12e-141">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="9b12e-142">在**业务管理中心的 Skype**> **音频会议** > **用户**，在**会议 ID**下的操作窗格中单击**重置**。</span><span class="sxs-lookup"><span data-stu-id="9b12e-142">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="9b12e-143">在**重置的会议 ID？** 窗口中，单击**是**。</span><span class="sxs-lookup"><span data-stu-id="9b12e-143">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="9b12e-144">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="9b12e-144">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
    
    <span data-ttu-id="9b12e-145">您可以通过使用 Windows PowerShell 重置用户的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="9b12e-145">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="9b12e-146">若要执行此操作，请运行：</span><span class="sxs-lookup"><span data-stu-id="9b12e-146">To do this, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="9b12e-147">你还需了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="9b12e-147">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="9b12e-148">创建新的会议 ID 或一个将重置之后，呼叫者不能使用旧的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="9b12e-148">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="9b12e-149">应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。</span><span class="sxs-lookup"><span data-stu-id="9b12e-149">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="9b12e-150">用户可以使用业务会议迁移工具的 Skype 更新其现有会议。</span><span class="sxs-lookup"><span data-stu-id="9b12e-150">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="9b12e-151">若要查看如何下载、 安装和运行该工具，请参阅： [Skype 商业和 Lync 会议更新工具](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)、[业务 online，会议迁移工具 （64 位） 的 Skype](http://go.microsoft.com/fwlink/?LinkID=626047)和[Skype 业务 online，会议迁移工具 （32 位）](https://www.microsoft.com/en-us/download/details.aspx?id=54079)。</span><span class="sxs-lookup"><span data-stu-id="9b12e-151">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
- <span data-ttu-id="9b12e-152">请参阅 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) 以了解有关 cmdlet 的更多信息。</span><span class="sxs-lookup"><span data-stu-id="9b12e-152">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>
    
- <span data-ttu-id="9b12e-153">会议 ID 必须满足的长度，以设置音频会议桥的数字。</span><span class="sxs-lookup"><span data-stu-id="9b12e-153">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="9b12e-154">会议 Id; 不能使用字母或特殊字符可以使用只有数字。</span><span class="sxs-lookup"><span data-stu-id="9b12e-154">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
    
- <span data-ttu-id="9b12e-155">所有音频会议用户的会议 ID 将 7 位数字，默认情况下，并且不能更改的位数。</span><span class="sxs-lookup"><span data-stu-id="9b12e-155">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>
    
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="9b12e-156">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="9b12e-156">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="9b12e-p112">对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="9b12e-p112">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="9b12e-160">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="9b12e-160">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="9b12e-161">为什么您需要使用 Office 365 PowerShell 中</span><span class="sxs-lookup"><span data-stu-id="9b12e-161">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="9b12e-p113">例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="9b12e-p113">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="9b12e-164">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="9b12e-164">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="9b12e-165">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="9b12e-165">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="9b12e-166">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="9b12e-166">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="9b12e-167">相关主题</span><span class="sxs-lookup"><span data-stu-id="9b12e-167">Related topics</span></span>

[<span data-ttu-id="9b12e-168">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="9b12e-168">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

