---
title: 在 Skype for Business Online 中查看、更改和重置分配给用户的会议 ID
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
description: '了解如何在 Skype for Business Online 中向用户分配会议 ID，以及会议 Id 参数应该是什么。 '
ms.openlocfilehash: 10acf425db0230dd90f8c125b0d871e07dd69728
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888061"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="d7b22-103">查看和重置 Skype for Business Online​  中分配给用户的会议 ID</span><span class="sxs-lookup"><span data-stu-id="d7b22-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="d7b22-104">有关 Microsoft 团队中的用户会议 Id 的信息，请参阅[查看和重置 Microsoft 团队中分配给用户的会议 ID](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="d7b22-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="d7b22-p101">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider. The conference ID assigned is sent in the meeting invite when the meeting is scheduled. Each meeting that a user schedules will get assigned a unique conference ID.</span><span class="sxs-lookup"><span data-stu-id="d7b22-p101">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider. The conference ID assigned is sent in the meeting invite when the meeting is scheduled. Each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="d7b22-p102">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span><span class="sxs-lookup"><span data-stu-id="d7b22-p102">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="d7b22-p103">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN. For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="d7b22-p103">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN. For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="d7b22-112">查看和重置会议 ID</span><span class="sxs-lookup"><span data-stu-id="d7b22-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="d7b22-113">查看会议 ID</span><span class="sxs-lookup"><span data-stu-id="d7b22-113">To view the conference ID</span></span>

<span data-ttu-id="d7b22-114">![](../images/sfb-logo-30x30.png) **使用 skype for business 管理中心**显示 skype for business 徽标的图标</span><span class="sxs-lookup"><span data-stu-id="d7b22-114">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="d7b22-115">可以查看他们的会议 ID，并将其发送给用户。</span><span class="sxs-lookup"><span data-stu-id="d7b22-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="d7b22-116">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="d7b22-116">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="d7b22-117">转到管理中心 > **Skype For business**。</span><span class="sxs-lookup"><span data-stu-id="d7b22-117">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="d7b22-118">在 **Skype for Business 管理中心**> **音频会议** > **用户**，选择需要会议 ID 的用户。</span><span class="sxs-lookup"><span data-stu-id="d7b22-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="d7b22-119">在操作页面，查看**会议 ID** 下方。</span><span class="sxs-lookup"><span data-stu-id="d7b22-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="d7b22-120">在 "**用户**" 页面上选择用户后，通过单击 "**通过电子邮件发送会议信息**" 链接，可以在包含会议 ID 和音频电话号码的电子邮件中向用户发送所有会议信息。</span><span class="sxs-lookup"><span data-stu-id="d7b22-120">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="d7b22-121">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="d7b22-121">**Using Windows PowerShell**</span></span>

<span data-ttu-id="d7b22-p104">You can use Windows PowerShell to view the conference ID for a user. To do so, run:</span><span class="sxs-lookup"><span data-stu-id="d7b22-p104">You can use Windows PowerShell to view the conference ID for a user. To do so, run:</span></span>

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

<span data-ttu-id="d7b22-124">请参阅[get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617693 )以了解有关 cmdlet 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d7b22-124">See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.</span></span>


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="d7b22-125">重置会议 ID</span><span class="sxs-lookup"><span data-stu-id="d7b22-125">To reset the conference ID</span></span>

<span data-ttu-id="d7b22-126">例如，如果用户忘记了密码，你可以为其重置会议 ID。</span><span class="sxs-lookup"><span data-stu-id="d7b22-126">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="d7b22-127">![](../images/sfb-logo-30x30.png) **使用 skype for business 管理中心**显示 skype for business 徽标的图标</span><span class="sxs-lookup"><span data-stu-id="d7b22-127">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="d7b22-128">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="d7b22-128">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="d7b22-129">转到管理中心 > **Skype For business**。</span><span class="sxs-lookup"><span data-stu-id="d7b22-129">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="d7b22-130">在**Skype for business 管理中心**> **音频会议** > **用户**的 "操作" 窗格中的 "**会议 ID**" 下，单击 "**重置**"。</span><span class="sxs-lookup"><span data-stu-id="d7b22-130">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="d7b22-131">在 "**重置会议 ID？** " 窗口中，单击 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="d7b22-131">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="d7b22-132">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="d7b22-132">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="d7b22-133">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="d7b22-133">**Using Windows PowerShell**</span></span>

<span data-ttu-id="d7b22-134">可以通过使用 Windows PowerShell 重置用户的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="d7b22-134">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="d7b22-135">若要执行此操作，请运行：</span><span class="sxs-lookup"><span data-stu-id="d7b22-135">To do this, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="d7b22-136">你还需了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="d7b22-136">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="d7b22-137">在创建新的会议 ID 或重置一个会议 ID 后，呼叫者无法使用旧的会议 id。</span><span class="sxs-lookup"><span data-stu-id="d7b22-137">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="d7b22-138">应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。</span><span class="sxs-lookup"><span data-stu-id="d7b22-138">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="d7b22-139">用户可以使用 Skype for Business 会议迁移工具更新其现有会议。</span><span class="sxs-lookup"><span data-stu-id="d7b22-139">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="d7b22-140">若要了解如何下载、安装和运行该工具，请参阅：[适用于 skype for business 和 Lync 的会议更新工具](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)、skype For business [Online、会议迁移工具（64位）](https://go.microsoft.com/fwlink/?LinkID=626047)和[Skype For Business online、会议迁移工具（32位）](https://www.microsoft.com/en-us/download/details.aspx?id=54079)。</span><span class="sxs-lookup"><span data-stu-id="d7b22-140">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>

- <span data-ttu-id="d7b22-141">请参阅 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) 以了解有关 cmdlet 的更多信息。</span><span class="sxs-lookup"><span data-stu-id="d7b22-141">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="d7b22-142">会议 ID 必须满足在音频会议网桥上设置的数字长度。</span><span class="sxs-lookup"><span data-stu-id="d7b22-142">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="d7b22-143">您不能在会议 Id 中使用字母或特殊字符;只能使用数字。</span><span class="sxs-lookup"><span data-stu-id="d7b22-143">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>

- <span data-ttu-id="d7b22-144">默认情况下，所有音频会议用户的会议 ID 都是7位数字，并且位数不能更改。</span><span class="sxs-lookup"><span data-stu-id="d7b22-144">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="d7b22-145">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="d7b22-145">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="d7b22-p109">对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="d7b22-p109">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="d7b22-149">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="d7b22-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="d7b22-150">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="d7b22-150">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="d7b22-151">Windows PowerShell 在速度、简洁性和效率方面具有许多优势，仅限于使用 Microsoft 365 管理中心，例如当你同时为多个用户设置更改时。</span><span class="sxs-lookup"><span data-stu-id="d7b22-151">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="d7b22-152">通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="d7b22-152">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="d7b22-153">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="d7b22-153">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="d7b22-154">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d7b22-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="d7b22-155">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="d7b22-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="d7b22-156">相关主题</span><span class="sxs-lookup"><span data-stu-id="d7b22-156">Related topics</span></span>

[<span data-ttu-id="d7b22-157">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="d7b22-157">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

