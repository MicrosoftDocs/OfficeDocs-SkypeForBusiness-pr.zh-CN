---
title: 在 Microsoft Teams 中查看、更改和重置分配给用户的会议 ID
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解如何在 Microsoft Teams 中为用户分配会议 ID 以及应使用的会议 ID 参数。 '
ms.openlocfilehash: d134a3664a6cee588d08f3d1a33bc6018d97a1fa
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571333"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a><span data-ttu-id="b0981-103">在 Microsoft Teams 中查看和重置分配给用户的会议 ID</span><span class="sxs-lookup"><span data-stu-id="b0981-103">View and reset a conference ID assigned to a user in Microsoft Teams</span></span>

<span data-ttu-id="b0981-104">在 Office 365 中为 Microsoft Teams 用户设置音频会议以及 Microsoft Teams 用户使用 Microsoft 作为音频会议提供商时会自动为其分配会议 ID。</span><span class="sxs-lookup"><span data-stu-id="b0981-104">A conferencing ID is automatically assigned to a Microsoft Teams user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="b0981-105">在安排会议时将在会议邀请中发送分配的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="b0981-105">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="b0981-106">用户安排的每次会议将分配到一个唯一的会议 id。</span><span class="sxs-lookup"><span data-stu-id="b0981-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="b0981-107">虽然会自动创建会议 ID 并将其分配给用户，但有时可能会存在以下情况：用户不希望使用此会议 ID，你希望将其设置为特定号码，或者你的用户记不住或丢失了其会议 ID。</span><span class="sxs-lookup"><span data-stu-id="b0981-107">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="b0981-108">你可以使用 Microsoft Teams 管理中心或 Windows PowerShell 来查看、更改和重置其会议 ID。</span><span class="sxs-lookup"><span data-stu-id="b0981-108">You can use Microsoft Teams admin center or Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="b0981-109">电子邮件将发送到有会议 ID 的用户和默认音频会议电话号码，或者，如果重置的会议 ID，将发送一封不同的电子邮件，其将包括会议 ID，但没有 PIN。</span><span class="sxs-lookup"><span data-stu-id="b0981-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="b0981-110">有关重置会议组织者 PIN 的详细信息，请[转到此处](reset-a-conference-id-for-a-user-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="b0981-110">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user-in-teams.md).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="b0981-111">查看和重置会议 ID</span><span class="sxs-lookup"><span data-stu-id="b0981-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="b0981-112">查看会议 ID</span><span class="sxs-lookup"><span data-stu-id="b0981-112">To view the conference ID</span></span>

<span data-ttu-id="b0981-113">![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标</span><span class="sxs-lookup"><span data-stu-id="b0981-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="b0981-114">在左侧导航中，单击“**用户**”，然后从可用用户列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="b0981-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="b0981-115">在页面顶部，单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="b0981-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="b0981-116">在“**音频会议**”下，查看“**会议 ID**”下方内容。</span><span class="sxs-lookup"><span data-stu-id="b0981-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="b0981-117">你可以单击“**通过电子邮件发送会议信息**”，通过电子邮件向用户发送所有会议信息（包括会议 ID 和音频电话号码）。</span><span class="sxs-lookup"><span data-stu-id="b0981-117">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info in email** link.</span></span>
  
<span data-ttu-id="b0981-118">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="b0981-118">**Using Windows PowerShell**</span></span>

<span data-ttu-id="b0981-119">有关详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。</span><span class="sxs-lookup"><span data-stu-id="b0981-119">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="b0981-120">重置会议 ID</span><span class="sxs-lookup"><span data-stu-id="b0981-120">To reset the conference ID</span></span>

<span data-ttu-id="b0981-121">你可以为用户重置会议 ID（例如，当用户忘记了会议 ID 时）。</span><span class="sxs-lookup"><span data-stu-id="b0981-121">You can reset a conference ID for a user if, for example, they forget it.</span></span>
  
<span data-ttu-id="b0981-122">![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标</span><span class="sxs-lookup"><span data-stu-id="b0981-122">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="b0981-123">在左侧导航中，单击“**用户**”，然后从可用用户列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="b0981-123">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="b0981-124">在页面顶部，单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="b0981-124">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="b0981-125">在“**音频会议**”下，单击“**重置会议 ID**”。</span><span class="sxs-lookup"><span data-stu-id="b0981-125">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="b0981-126">在“**重置会议 ID**”窗口中，单击“**重置**”。</span><span class="sxs-lookup"><span data-stu-id="b0981-126">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="b0981-127">将自动创建一个会议 ID，并向用户发送包含新会议 ID 的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b0981-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
  
<span data-ttu-id="b0981-128">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="b0981-128">**Using Windows PowerShell**</span></span>

<span data-ttu-id="b0981-129">有关详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。</span><span class="sxs-lookup"><span data-stu-id="b0981-129">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="what-else-should-you-know"></a><span data-ttu-id="b0981-130">你还应该了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="b0981-130">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="b0981-131">创建新会议 ID 或重置会议 ID 后，呼叫者不能使用旧会议 ID。</span><span class="sxs-lookup"><span data-stu-id="b0981-131">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="b0981-132">应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。</span><span class="sxs-lookup"><span data-stu-id="b0981-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 
  
    
- <span data-ttu-id="b0981-133">会议 ID 必须符合在音频会议网桥上设置的位数长度。</span><span class="sxs-lookup"><span data-stu-id="b0981-133">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="b0981-134">不能在会议 ID 中使用字母和特殊字符，只能使用数字。</span><span class="sxs-lookup"><span data-stu-id="b0981-134">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
   
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="b0981-135">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="b0981-135">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="b0981-p107">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="b0981-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="b0981-139">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0981-139">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="b0981-140">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="b0981-140">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="b0981-141">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="b0981-141">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="b0981-142">相关主题</span><span class="sxs-lookup"><span data-stu-id="b0981-142">Related topics</span></span>

[<span data-ttu-id="b0981-143">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="b0981-143">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

