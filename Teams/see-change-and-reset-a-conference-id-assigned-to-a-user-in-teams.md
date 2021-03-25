---
title: 查看、更改和重置用户的会议 ID
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: 了解如何在 Microsoft Teams 中向用户分配会议 ID，以及会议 ID 参数应是什么。
ms.openlocfilehash: b57a419266ceca09a73fc4bf75bb12153e41ea91
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117205"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a><span data-ttu-id="f30d3-103">在 Microsoft Teams 中查看和重置分配给用户的会议 ID</span><span class="sxs-lookup"><span data-stu-id="f30d3-103">View and reset a conference ID assigned to a user in Microsoft Teams</span></span>

<span data-ttu-id="f30d3-104">在 Microsoft 365 或 Office 365 中为音频会议设置并使用 Microsoft 作为音频会议提供商时，会议 ID 会自动分配给 Microsoft Teams 用户。</span><span class="sxs-lookup"><span data-stu-id="f30d3-104">A conferencing ID is automatically assigned to a Microsoft Teams user when they are set up for Audio Conferencing in Microsoft 365 or Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="f30d3-105">安排会议时，将在会议邀请中发送分配的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="f30d3-105">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="f30d3-106">用户安排的每次会议将分配到一个唯一的会议 id。</span><span class="sxs-lookup"><span data-stu-id="f30d3-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="f30d3-107">尽管会议 ID 将自动创建并分配给用户，但有时用户可能不想使用此 ID，而你想要将其设置为特定号码，或者用户记不起来或已丢失其会议 ID。</span><span class="sxs-lookup"><span data-stu-id="f30d3-107">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="f30d3-108">可以使用 Microsoft Teams 管理中心或Windows PowerShell查看、更改和重置其会议 ID。</span><span class="sxs-lookup"><span data-stu-id="f30d3-108">You can use Microsoft Teams admin center or Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="f30d3-109">电子邮件将发送到有会议 ID 的用户和默认音频会议电话号码，或者，如果重置的会议 ID，将发送一封不同的电子邮件，其将包括会议 ID，但没有 PIN。</span><span class="sxs-lookup"><span data-stu-id="f30d3-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="f30d3-110">请参阅 [在 Microsoft Teams 中](reset-a-conference-id-for-a-user-in-teams.md) 重置用户的会议 ID，详细了解如何重置会议组织者的 PIN。</span><span class="sxs-lookup"><span data-stu-id="f30d3-110">See [Reset a conference ID for a user in Microsoft Teams](reset-a-conference-id-for-a-user-in-teams.md) for more information about how to reset a conference organizer's PIN.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="f30d3-111">查看和重置会议 ID</span><span class="sxs-lookup"><span data-stu-id="f30d3-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="f30d3-112">查看会议 ID</span><span class="sxs-lookup"><span data-stu-id="f30d3-112">To view the conference ID</span></span>

<span data-ttu-id="f30d3-113">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="f30d3-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="f30d3-114">在左侧导航栏中， **单击"用户**"，然后从可用用户列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="f30d3-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="f30d3-115">在页面的顶部，单击 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="f30d3-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="f30d3-116">在 **"音频会议"下**，查看"会议 **ID"下**。</span><span class="sxs-lookup"><span data-stu-id="f30d3-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="f30d3-117">您可以通过单击"在电子邮件中发送会议信息"链接，在包含会议 ID 和音频电话号码的电子邮件中向用户 **发送所有会议** 信息。</span><span class="sxs-lookup"><span data-stu-id="f30d3-117">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info in email** link.</span></span>
  
<span data-ttu-id="f30d3-118">**使用Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f30d3-118">**Using Windows PowerShell**</span></span>

<span data-ttu-id="f30d3-119">有关详细信息， [请参阅 Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) 参考。</span><span class="sxs-lookup"><span data-stu-id="f30d3-119">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="f30d3-120">重置会议 ID</span><span class="sxs-lookup"><span data-stu-id="f30d3-120">To reset the conference ID</span></span>

<span data-ttu-id="f30d3-121">例如，如果用户忘记了密码，你可以为其重置会议 ID。</span><span class="sxs-lookup"><span data-stu-id="f30d3-121">You can reset a conference ID for a user if, for example, they forget it.</span></span>
  
<span data-ttu-id="f30d3-122">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="f30d3-122">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="f30d3-123">在左侧导航栏中， **单击"用户**"，然后从可用用户列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="f30d3-123">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="f30d3-124">在页面的顶部，单击 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="f30d3-124">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="f30d3-125">在 **"音频会议"下**，单击"**重置会议 ID"。**</span><span class="sxs-lookup"><span data-stu-id="f30d3-125">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="f30d3-126">在"**重置会议 ID"窗口中**，单击"重置 **"。**</span><span class="sxs-lookup"><span data-stu-id="f30d3-126">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="f30d3-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="f30d3-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
  
<span data-ttu-id="f30d3-128">**使用Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f30d3-128">**Using Windows PowerShell**</span></span>

<span data-ttu-id="f30d3-129">有关详细信息， [请参阅 Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) 参考。</span><span class="sxs-lookup"><span data-stu-id="f30d3-129">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="what-else-should-you-know"></a><span data-ttu-id="f30d3-130">你还需了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="f30d3-130">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="f30d3-131">新建会议 ID 或重置会议 ID 后，呼叫者将不能使用旧会议 ID。</span><span class="sxs-lookup"><span data-stu-id="f30d3-131">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="f30d3-132">应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。</span><span class="sxs-lookup"><span data-stu-id="f30d3-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 
  
    
- <span data-ttu-id="f30d3-133">会议 ID 必须符合音频会议网桥上设置的位数长度。</span><span class="sxs-lookup"><span data-stu-id="f30d3-133">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="f30d3-134">不能对会议 ID 使用字母或特殊字符;只能使用数字。</span><span class="sxs-lookup"><span data-stu-id="f30d3-134">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
   
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="f30d3-135">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="f30d3-135">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="f30d3-136">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="f30d3-136">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="f30d3-137">使用 Windows PowerShell，您可以使用单点管理来管理 Microsoft 365 或 Office 365，当您有多个任务需要执行时，可以简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="f30d3-137">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="f30d3-138">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="f30d3-138">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f30d3-139">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="f30d3-139">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="f30d3-140">[使用 Office 365 管理 Microsoft 365 或 Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="f30d3-140">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="f30d3-141">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="f30d3-141">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="f30d3-142">相关主题</span><span class="sxs-lookup"><span data-stu-id="f30d3-142">Related topics</span></span>

[<span data-ttu-id="f30d3-143">在 Microsoft 365 或 Office 365 中试用或购买音频会议</span><span class="sxs-lookup"><span data-stu-id="f30d3-143">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)