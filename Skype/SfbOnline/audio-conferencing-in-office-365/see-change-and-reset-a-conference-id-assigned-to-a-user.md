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
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解如何在 Skype for Business Online 中向用户分配会议 ID, 以及会议 Id 参数应该是什么。 '
ms.openlocfilehash: 28d18b6a12fdfcb40fa43904b8cc8a0461977c38
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298918"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="a4865-103">查看和重置 Skype for Business Online​  中分配给用户的会议 ID</span><span class="sxs-lookup"><span data-stu-id="a4865-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="a4865-104">如需了解有关 Microsoft Teams 中用户会议 ID 的信息，请参阅[查看和重置 Microsoft Teasms  中分配给用户的会议 ID](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="a4865-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teasms](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="a4865-p101">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider. The conference ID assigned is sent in the meeting invite when the meeting is scheduled. Each meeting that a user schedules will get assigned a unique conference ID.</span><span class="sxs-lookup"><span data-stu-id="a4865-p101">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider. The conference ID assigned is sent in the meeting invite when the meeting is scheduled. Each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="a4865-p102">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span><span class="sxs-lookup"><span data-stu-id="a4865-p102">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="a4865-p103">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN. For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="a4865-p103">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN. For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="a4865-112">查看和重置会议 ID</span><span class="sxs-lookup"><span data-stu-id="a4865-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="a4865-113">查看会议 ID</span><span class="sxs-lookup"><span data-stu-id="a4865-113">To view the conference ID</span></span>

<span data-ttu-id="a4865-114">![](../images/sfb-logo-30x30.png) **使用 Skype for business 管理中心**sfb-logo-30x30</span><span class="sxs-lookup"><span data-stu-id="a4865-114">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="a4865-115">可以查看他们的会议 ID，并将其发送给用户。</span><span class="sxs-lookup"><span data-stu-id="a4865-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="a4865-116">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="a4865-116">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="a4865-117">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="a4865-117">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="a4865-118">在 **Skype for Business 管理中心**> **音频会议** > **用户**，选择需要会议 ID 的用户。</span><span class="sxs-lookup"><span data-stu-id="a4865-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="a4865-119">在操作页面，查看**会议 ID** 下方。</span><span class="sxs-lookup"><span data-stu-id="a4865-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="a4865-120">在 "**用户**" 页面上选择用户后, 通过单击 "**通过电子邮件发送会议信息**" 链接, 可以在包含会议 ID 和音频电话号码的电子邮件中向用户发送所有会议信息。</span><span class="sxs-lookup"><span data-stu-id="a4865-120">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="a4865-121">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a4865-121">**Using Windows PowerShell**</span></span>

<span data-ttu-id="a4865-p104">You can use Windows PowerShell to view the conference ID for a user. To do so, run:</span><span class="sxs-lookup"><span data-stu-id="a4865-p104">You can use Windows PowerShell to view the conference ID for a user. To do so, run:</span></span>

  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="a4865-124">重置会议 ID</span><span class="sxs-lookup"><span data-stu-id="a4865-124">To reset the conference ID</span></span>

<span data-ttu-id="a4865-125">例如，如果用户忘记了密码，你可以为其重置会议 ID。</span><span class="sxs-lookup"><span data-stu-id="a4865-125">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="a4865-126">![](../images/sfb-logo-30x30.png) **使用 Skype for business 管理中心**sfb-logo-30x30</span><span class="sxs-lookup"><span data-stu-id="a4865-126">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="a4865-127">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="a4865-127">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="a4865-128">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="a4865-128">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="a4865-129">在**Skype for business 管理中心**> **音频会议** > **用户**的 "操作" 窗格中的 "**会议 ID**" 下, 单击 "**重置**"。</span><span class="sxs-lookup"><span data-stu-id="a4865-129">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="a4865-p105">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="a4865-p105">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="a4865-132">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a4865-132">**Using Windows PowerShell**</span></span>

<span data-ttu-id="a4865-p106">You can reset the conference ID for a user by using the Windows PowerShell. To do this, run:</span><span class="sxs-lookup"><span data-stu-id="a4865-p106">You can reset the conference ID for a user by using the Windows PowerShell. To do this, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="a4865-135">你还需了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="a4865-135">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="a4865-p107">After a new conference ID is created or one is reset, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="a4865-p107">After a new conference ID is created or one is reset, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>

- <span data-ttu-id="a4865-140">请参阅 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) 以了解有关 cmdlet 的更多信息。</span><span class="sxs-lookup"><span data-stu-id="a4865-140">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="a4865-p108">The conference ID must meet the length in digits set on the audio conferencing bridge. You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span><span class="sxs-lookup"><span data-stu-id="a4865-p108">The conference ID must meet the length in digits set on the audio conferencing bridge. You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>

- <span data-ttu-id="a4865-143">默认情况下, 所有音频会议用户的会议 ID 都是7位数字, 并且位数不能更改。</span><span class="sxs-lookup"><span data-stu-id="a4865-143">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="a4865-144">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="a4865-144">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="a4865-p109">对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="a4865-p109">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="a4865-148">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="a4865-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="a4865-149">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="a4865-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="a4865-p110">例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="a4865-p110">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="a4865-152">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="a4865-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="a4865-153">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a4865-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="a4865-154">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="a4865-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="a4865-155">相关主题</span><span class="sxs-lookup"><span data-stu-id="a4865-155">Related topics</span></span>

[<span data-ttu-id="a4865-156">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="a4865-156">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

