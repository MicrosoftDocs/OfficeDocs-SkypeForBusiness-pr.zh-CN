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
description: '了解如何在 Skype for Business Online 中向用户分配会议 ID，以及会议 ID 参数应是什么。 '
ms.openlocfilehash: f12982298903485d93582fae3a4f39aaed49170c
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237048"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="4bf98-103">查看和重置 Skype for Business Online​  中分配给用户的会议 ID</span><span class="sxs-lookup"><span data-stu-id="4bf98-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> <span data-ttu-id="4bf98-104">有关用户在 Microsoft Teams 会议 ID 的信息，请参阅在 Microsoft Teams 中查看和重置分配给[用户Microsoft Teams。](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)</span><span class="sxs-lookup"><span data-stu-id="4bf98-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="4bf98-105">在 Microsoft 365 或 Office 365 中为音频会议设置 Skype for Business 用户并将 Microsoft 用作音频会议提供商时，会议 ID 会自动分配给他们。</span><span class="sxs-lookup"><span data-stu-id="4bf98-105">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Microsoft 365 or Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="4bf98-106">安排会议时，将在会议邀请中发送分配的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="4bf98-106">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="4bf98-107">用户安排的每次会议将分配到一个唯一的会议 id。</span><span class="sxs-lookup"><span data-stu-id="4bf98-107">Each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="4bf98-108">尽管会议 ID 将自动创建并分配给用户，但有时用户可能不想使用此 ID，而你想要将其设置为特定号码，或者用户记不起来或已丢失其会议 ID。</span><span class="sxs-lookup"><span data-stu-id="4bf98-108">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="4bf98-109">可以使用 **Skype for Business 管理中心** 和 Windows PowerShell 来查看、更改和重置其会议 ID。</span><span class="sxs-lookup"><span data-stu-id="4bf98-109">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="4bf98-110">电子邮件将发送到有会议 ID 的用户和默认音频会议电话号码，或者，如果重置的会议 ID，将发送一封不同的电子邮件，其将包括会议 ID，但没有 PIN。</span><span class="sxs-lookup"><span data-stu-id="4bf98-110">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="4bf98-111">有关重置会议组织者 PIN 的详细信息，请[转到此处](reset-a-conference-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="4bf98-111">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="4bf98-112">查看和重置会议 ID</span><span class="sxs-lookup"><span data-stu-id="4bf98-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="4bf98-113">查看会议 ID</span><span class="sxs-lookup"><span data-stu-id="4bf98-113">To view the conference ID</span></span>

<span data-ttu-id="4bf98-114">![显示 Skype for Business 徽标的图标](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**</span><span class="sxs-lookup"><span data-stu-id="4bf98-114">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="4bf98-115">可以查看他们的会议 ID，并将其发送给用户。</span><span class="sxs-lookup"><span data-stu-id="4bf98-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="4bf98-116">使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="4bf98-116">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="4bf98-117">转到管理中心 **> Skype for Business。**</span><span class="sxs-lookup"><span data-stu-id="4bf98-117">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="4bf98-118">在 **Skype for Business 管理中心**> **音频会议** > **用户**，选择需要会议 ID 的用户。</span><span class="sxs-lookup"><span data-stu-id="4bf98-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="4bf98-119">在操作页面，查看 **会议 ID** 下方。</span><span class="sxs-lookup"><span data-stu-id="4bf98-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="4bf98-120">在"用户"页面上选择用户后，您可以通过单击"通过电子邮件发送会议信息"链接，在包含会议 ID 和音频电话号码的电子邮件中向用户发送所有 **会议信息。**</span><span class="sxs-lookup"><span data-stu-id="4bf98-120">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="4bf98-121">**使用Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="4bf98-121">**Using Windows PowerShell**</span></span>

<span data-ttu-id="4bf98-122">可以使用 Windows PowerShell 来查看用户的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="4bf98-122">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="4bf98-123">为此，请运行：</span><span class="sxs-lookup"><span data-stu-id="4bf98-123">To do so, run:</span></span>

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

<span data-ttu-id="4bf98-124">若要详细了解 cmdlet，请参阅[Get-CsOnlineDialInConferencingUser。](/powershell/module/skype/Get-CsOnlineDialInConferencingUser)</span><span class="sxs-lookup"><span data-stu-id="4bf98-124">See [Get-CsOnlineDialInConferencingUser](/powershell/module/skype/Get-CsOnlineDialInConferencingUser) to learn more about the cmdlet.</span></span>


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="4bf98-125">重置会议 ID</span><span class="sxs-lookup"><span data-stu-id="4bf98-125">To reset the conference ID</span></span>

<span data-ttu-id="4bf98-126">例如，如果用户忘记了密码，你可以为其重置会议 ID。</span><span class="sxs-lookup"><span data-stu-id="4bf98-126">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="4bf98-127">![显示 Skype for Business 徽标的图标](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**</span><span class="sxs-lookup"><span data-stu-id="4bf98-127">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="4bf98-128">使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="4bf98-128">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="4bf98-129">转到管理中心 **> Skype for Business。**</span><span class="sxs-lookup"><span data-stu-id="4bf98-129">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="4bf98-130">在Skype for Business **管理中心**"音频会议用户"中，在"会议 ID"下的"操作" >    >  **窗格中**，单击"重置 **"。**</span><span class="sxs-lookup"><span data-stu-id="4bf98-130">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="4bf98-131">在"**重置会议 ID？"** 窗口中，单击"**是"。**</span><span class="sxs-lookup"><span data-stu-id="4bf98-131">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="4bf98-132">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="4bf98-132">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="4bf98-133">**使用Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="4bf98-133">**Using Windows PowerShell**</span></span>

<span data-ttu-id="4bf98-134">可以通过使用 Windows PowerShell 重置用户的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="4bf98-134">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="4bf98-135">为此，请运行：</span><span class="sxs-lookup"><span data-stu-id="4bf98-135">To do this, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="4bf98-136">你还需了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="4bf98-136">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="4bf98-137">新建会议 ID 或重置会议 ID 后，呼叫者将不能使用旧会议 ID。</span><span class="sxs-lookup"><span data-stu-id="4bf98-137">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="4bf98-138">应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。</span><span class="sxs-lookup"><span data-stu-id="4bf98-138">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="4bf98-139">用户可以使用会议Skype for Business工具来更新其现有会议。</span><span class="sxs-lookup"><span data-stu-id="4bf98-139">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="4bf98-140">若要了解如何下载、安装和运行该工具，请参阅：适用于 Skype for Business 和[Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)的会议更新工具[、Skype for Business Online、会议迁移工具 (64](https://go.microsoft.com/fwlink/?LinkID=626047)位) 和 Skype for Business Online、会议迁移工具 ([32](https://www.microsoft.com/download/details.aspx?id=54079)位) 。</span><span class="sxs-lookup"><span data-stu-id="4bf98-140">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/download/details.aspx?id=54079).</span></span>

- <span data-ttu-id="4bf98-141">请参阅 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) 以了解有关 cmdlet 的更多信息。</span><span class="sxs-lookup"><span data-stu-id="4bf98-141">See [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="4bf98-142">会议 ID 必须符合音频会议网桥上设置的位数长度。</span><span class="sxs-lookup"><span data-stu-id="4bf98-142">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="4bf98-143">不能对会议 ID 使用字母或特殊字符;只能使用数字。</span><span class="sxs-lookup"><span data-stu-id="4bf98-143">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>

- <span data-ttu-id="4bf98-144">默认情况下，所有音频会议用户的会议 ID 将为 9 位，不能更改位数。</span><span class="sxs-lookup"><span data-stu-id="4bf98-144">The conference ID for all of your audio conferencing users will be 9 digits by default, and the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="4bf98-145">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="4bf98-145">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="4bf98-146">对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。</span><span class="sxs-lookup"><span data-stu-id="4bf98-146">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="4bf98-147">使用 Windows PowerShell，Microsoft 365管理Office 365 Skype for Business管理点，可在有多个任务需要执行时简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="4bf98-147">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="4bf98-148">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="4bf98-148">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="4bf98-149">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="4bf98-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="4bf98-150">为何需要将 Microsoft 365 或 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="4bf98-150">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- <span data-ttu-id="4bf98-151">Windows PowerShell管理中心相比，Microsoft 365在速度、简单性和工作效率方面具有许多优势，例如，一次对许多用户进行设置更改时。</span><span class="sxs-lookup"><span data-stu-id="4bf98-151">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="4bf98-152">通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="4bf98-152">Learn about these advantages in the following topics:</span></span>

  - <span data-ttu-id="4bf98-153">[使用 Microsoft 365 Office 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="4bf98-153">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

  - [<span data-ttu-id="4bf98-154">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4bf98-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="4bf98-155">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="4bf98-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a><span data-ttu-id="4bf98-156">相关主题</span><span class="sxs-lookup"><span data-stu-id="4bf98-156">Related topics</span></span>

[<span data-ttu-id="4bf98-157">尝试或购买音频会议Microsoft 365或Office 365</span><span class="sxs-lookup"><span data-stu-id="4bf98-157">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
