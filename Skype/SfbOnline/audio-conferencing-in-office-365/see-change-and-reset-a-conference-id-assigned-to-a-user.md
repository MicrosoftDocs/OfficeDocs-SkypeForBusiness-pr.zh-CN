---
title: 查看、更改和重置 Skype for Business Online​  中分配给用户的会议 ID
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解如何在 Skype for Business 中将会议 ID 分配给用户，以及会议 ID 的参数应该是什么。 '
ms.openlocfilehash: 472f3b007a584979e029aade593c7b6c93ea1565
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23252305"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="0607a-103">查看和重置 Skype for Business Online​  中分配给用户的会议 ID</span><span class="sxs-lookup"><span data-stu-id="0607a-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="0607a-104">如需了解有关 Microsoft Teams 中用户会议 ID 的信息，请参阅[查看和重置 Microsoft Teasms  中分配给用户的会议 ID](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="0607a-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teasms](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="0607a-105">在为 Office 365 中的音频会议设置用户并使用 Microsoft 作为音频会议提供商时，将向 Skype for Business 用户自动分配会议 ID。</span><span class="sxs-lookup"><span data-stu-id="0607a-105">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="0607a-106">分配的会议 ID 在安排会议时在会议邀请中发送。</span><span class="sxs-lookup"><span data-stu-id="0607a-106">The conference ID assigned can be either a static or dynamic and is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="0607a-107">用户安排的每次会议将分配到一个唯一的会议 id。</span><span class="sxs-lookup"><span data-stu-id="0607a-107">Each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="0607a-108">虽然会议 ID 是自动创建并分配给用户的，但是有时用户不希望使用此会议 ID，你又希望将它设置为特定号码，或者你的用户无法记住或者已忘掉了其会议 ID。</span><span class="sxs-lookup"><span data-stu-id="0607a-108">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number or if your users can't remember or have lost their conference ID, you can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span> <span data-ttu-id="0607a-109">可以使用 **Skype for Business 管理中心**和 Windows PowerShell 来查看、更改和重置其会议 ID。</span><span class="sxs-lookup"><span data-stu-id="0607a-109">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="0607a-110">电子邮件将发送到有会议 ID 的用户和默认音频会议电话号码，或者，如果重置的会议 ID，将发送一封不同的电子邮件，其将包括会议 ID，但没有 PIN。</span><span class="sxs-lookup"><span data-stu-id="0607a-110">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="0607a-111">有关重置会议组织者 PIN 的详细信息，请[转到此处](reset-a-conference-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="0607a-111">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="0607a-112">查看和重置会议 ID</span><span class="sxs-lookup"><span data-stu-id="0607a-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="0607a-113">若要查看的会议 ID</span><span class="sxs-lookup"><span data-stu-id="0607a-113">To reset the meeting conference ID</span></span>

<span data-ttu-id="0607a-114">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**</span><span class="sxs-lookup"><span data-stu-id="0607a-114">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

<span data-ttu-id="0607a-115">可以查看他们的会议 ID，并将其发送给用户。</span><span class="sxs-lookup"><span data-stu-id="0607a-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="0607a-116">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0607a-116">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="0607a-117">转到 **Office 365 管理中心** > **Skype for Business**。</span><span class="sxs-lookup"><span data-stu-id="0607a-117">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="0607a-118">在 **Skype for Business 管理中心**> **音频会议** > **用户**，选择需要会议 ID 的用户。</span><span class="sxs-lookup"><span data-stu-id="0607a-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="0607a-119">在操作页面，查看**会议 ID** 下方。</span><span class="sxs-lookup"><span data-stu-id="0607a-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="0607a-120">可单击**通过电子邮件发送会议信息**链接，在选择了**用户** 页面上的用户后，将全部会议信息在一封电子邮件中发送给用户，其中包括会议 ID 和音频电话号码。</span><span class="sxs-lookup"><span data-stu-id="0607a-120">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking the **Send conference info via email**. It doesn't send the PIN.</span></span>

<span data-ttu-id="0607a-121">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="0607a-121">**** Using Windows PowerShell</span></span>

<span data-ttu-id="0607a-122">可以使用 Windows PowerShell 来查看用户的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="0607a-122">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="0607a-123">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0607a-123">To do so:</span></span>

  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="0607a-124">重置会议 ID</span><span class="sxs-lookup"><span data-stu-id="0607a-124">To reset the meeting conference ID</span></span>

<span data-ttu-id="0607a-125">例如，如果用户忘记了密码，你可以为其重置会议 ID。</span><span class="sxs-lookup"><span data-stu-id="0607a-125">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="0607a-126">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**</span><span class="sxs-lookup"><span data-stu-id="0607a-126">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="0607a-127">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0607a-127">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="0607a-128">转到 **Office 365 管理中心** > **Skype for Business**。</span><span class="sxs-lookup"><span data-stu-id="0607a-128">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="0607a-129">在 **Skype for Business 管理中心**> **音频会议** > **用户**，在 **会议 ID** 下的操作窗格中单击 **重置**。</span><span class="sxs-lookup"><span data-stu-id="0607a-129">In the **Skype for Business admin center**> **Dial-in conferencing**, in the Action page under **Conference ID** click **Reset**.</span></span>

4. <span data-ttu-id="0607a-130">在**重置会议 ID？** 窗口，单击**是**。</span><span class="sxs-lookup"><span data-stu-id="0607a-130">In the ** Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="0607a-131">会议 ID 将自动创建，将有一封含有新会议 ID 的电子邮件发送给用户。</span><span class="sxs-lookup"><span data-stu-id="0607a-131">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="0607a-132">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="0607a-132">**** Using Windows PowerShell</span></span>

<span data-ttu-id="0607a-133">可以通过使用 Windows PowerShell 重置用户的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="0607a-133">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="0607a-134">要执行此操作，请运行：</span><span class="sxs-lookup"><span data-stu-id="0607a-134">To do this run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="0607a-135">你还需了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="0607a-135">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="0607a-136">创建或重置新会议 ID 后，呼叫者不能再使用旧会议 ID。</span><span class="sxs-lookup"><span data-stu-id="0607a-136">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="0607a-137">应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。</span><span class="sxs-lookup"><span data-stu-id="0607a-137">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="0607a-138">用户可以使用 Skype for Business 会议迁移工具来更新其现有会议。</span><span class="sxs-lookup"><span data-stu-id="0607a-138">The users can use Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="0607a-139">要了解如何下载、安装和运行 工具，请参阅：[Skype for Business 和 Lync 的会议更新工具](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)、[Skype for Business Online、会议迁移工具（64 位）](https://go.microsoft.com/fwlink/?LinkID=626047)和  [Skype for Business Online、会议迁移工具（32 位）](https://www.microsoft.com/en-us/download/details.aspx?id=54079)。</span><span class="sxs-lookup"><span data-stu-id="0607a-139">To see how to download, install and run the Lync Meeting Update Tool, see:> Meeting Update Tool for Skype for Business and Lync  Skype for Business Online, Meeting Migration Tool (64-bit)  Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>

- <span data-ttu-id="0607a-140">请参阅 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) 以了解有关 cmdlet 的更多信息。</span><span class="sxs-lookup"><span data-stu-id="0607a-140">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="0607a-141">会议 ID 必须符合在音频式会议网桥上设置的长度位数。</span><span class="sxs-lookup"><span data-stu-id="0607a-141">The conference ID must meet the length in digits set on the dial-in conferencing bridge.</span></span> <span data-ttu-id="0607a-142">不能在会议 ID 中使用字母和特殊字符，只能使用数字。</span><span class="sxs-lookup"><span data-stu-id="0607a-142">You can't use Alphabetic and special characters in conference IDs only numbers can be used.</span></span>

- <span data-ttu-id="0607a-143">所有音频会议用户的会议 ID 默认情况下将是 7 位数。位数不可更改。</span><span class="sxs-lookup"><span data-stu-id="0607a-143">The conference ID for all of your dial-in conferencing users will be 7 digits by default. And the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="0607a-144">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="0607a-144">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="0607a-p109">对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="0607a-p109">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="0607a-148">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="0607a-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="0607a-149">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="0607a-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="0607a-p110">例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="0607a-p110">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="0607a-152">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="0607a-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="0607a-153">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="0607a-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="0607a-154">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="0607a-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="0607a-155">相关主题</span><span class="sxs-lookup"><span data-stu-id="0607a-155">Related topics</span></span>

[<span data-ttu-id="0607a-156">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="0607a-156">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

