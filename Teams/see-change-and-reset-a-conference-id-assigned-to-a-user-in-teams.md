---
title: 请参阅、 更改和重置分配给用户的 Microsoft 团队中的会议 ID
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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解如何向 Microsoft 团队中的用户分配的会议 ID 和哪些会议 ID 参数应为。 '
ms.openlocfilehash: aa69788e86689fb393684bfb9367152269cfa457
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850938"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a><span data-ttu-id="a94ca-103">查看和重置分配给用户的 Microsoft 团队中的会议 ID</span><span class="sxs-lookup"><span data-stu-id="a94ca-103">View and reset a conference ID assigned to a user in Microsoft Teams</span></span>

<span data-ttu-id="a94ca-104">自动分配给 Microsoft 团队用户会议 ID，在为 Office 365 中的音频会议设置并使用 Microsoft 作为音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="a94ca-104">A conferencing ID is automatically assigned to a Microsoft Teams user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="a94ca-105">安排会议时，将会议邀请中发送分配的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="a94ca-105">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="a94ca-106">用户安排的每次会议将分配到一个唯一的会议 id。</span><span class="sxs-lookup"><span data-stu-id="a94ca-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="a94ca-107">虽然会议 ID 将自动创建并分配给用户，有时可能时用户不是要使用此并且您希望将其设置为一个特定号码，或当用户忘记或丢失其会议 id。</span><span class="sxs-lookup"><span data-stu-id="a94ca-107">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="a94ca-108">您可以使用的 Microsoft 团队管理中心或 Windows PowerShell 查看、 更改和重置用户的会议 id。</span><span class="sxs-lookup"><span data-stu-id="a94ca-108">You can use Microsoft Teams admin center or Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="a94ca-109">电子邮件将发送到有会议 ID 的用户和默认音频会议电话号码，或者，如果重置的会议 ID，将发送一封不同的电子邮件，其将包括会议 ID，但没有 PIN。</span><span class="sxs-lookup"><span data-stu-id="a94ca-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="a94ca-110">有关重置会议组织者 PIN 的详细信息，请[转到此处](reset-a-conference-id-for-a-user-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="a94ca-110">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user-in-teams.md).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="a94ca-111">查看和重置会议 ID</span><span class="sxs-lookup"><span data-stu-id="a94ca-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="a94ca-112">若要查看的会议 ID</span><span class="sxs-lookup"><span data-stu-id="a94ca-112">To view the conference ID</span></span>

<span data-ttu-id="a94ca-113">![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="a94ca-113">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="a94ca-114">在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。</span><span class="sxs-lookup"><span data-stu-id="a94ca-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="a94ca-115">在页面的顶部，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="a94ca-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="a94ca-116">在**音频会议**下, 查找下**的会议 ID**。</span><span class="sxs-lookup"><span data-stu-id="a94ca-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="a94ca-117">您可以向中包括的会议 ID 和音频的电话号码，通过单击**发送电子邮件中的会议信息**链接的电子邮件的用户发送的所有会议信息。</span><span class="sxs-lookup"><span data-stu-id="a94ca-117">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info in email** link.</span></span>
  
<span data-ttu-id="a94ca-118">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a94ca-118">**Using Windows PowerShell**</span></span>

<span data-ttu-id="a94ca-119">请参阅[Microsoft 团队 PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)（英文） 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a94ca-119">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="a94ca-120">若要重置的会议 ID</span><span class="sxs-lookup"><span data-stu-id="a94ca-120">To reset the conference ID</span></span>

<span data-ttu-id="a94ca-121">例如，如果用户忘记了密码，你可以为其重置会议 ID。</span><span class="sxs-lookup"><span data-stu-id="a94ca-121">You can reset a conference ID for a user if, for example, they forget it.</span></span>
  
<span data-ttu-id="a94ca-122">![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="a94ca-122">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="a94ca-123">在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。</span><span class="sxs-lookup"><span data-stu-id="a94ca-123">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="a94ca-124">在页面的顶部，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="a94ca-124">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="a94ca-125">在**音频会议**，下单击**重置会议 ID**。</span><span class="sxs-lookup"><span data-stu-id="a94ca-125">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="a94ca-126">在**重置的会议 ID**窗口中，单击**重置**。</span><span class="sxs-lookup"><span data-stu-id="a94ca-126">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="a94ca-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="a94ca-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
  
<span data-ttu-id="a94ca-128">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a94ca-128">**Using Windows PowerShell**</span></span>

<span data-ttu-id="a94ca-129">请参阅[Microsoft 团队 PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)（英文） 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a94ca-129">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="what-else-should-you-know"></a><span data-ttu-id="a94ca-130">你还需了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="a94ca-130">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="a94ca-131">创建新的会议 ID 或一个将重置之后，呼叫者不能使用旧的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="a94ca-131">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="a94ca-132">应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。</span><span class="sxs-lookup"><span data-stu-id="a94ca-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 
  
    
- <span data-ttu-id="a94ca-133">会议 ID 必须满足的长度，以设置音频会议桥的数字。</span><span class="sxs-lookup"><span data-stu-id="a94ca-133">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="a94ca-134">会议 Id; 不能使用字母或特殊字符可以使用只有数字。</span><span class="sxs-lookup"><span data-stu-id="a94ca-134">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
    
- <span data-ttu-id="a94ca-135">所有音频会议用户的会议 ID 将 7 位数字，默认情况下，并且不能更改的位数。</span><span class="sxs-lookup"><span data-stu-id="a94ca-135">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>
    
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="a94ca-136">要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="a94ca-136">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="a94ca-p107">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="a94ca-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="a94ca-140">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="a94ca-140">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="a94ca-141">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="a94ca-141">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="a94ca-142">有关 Windows PowerShell 的详细信息，请参阅[Microsoft 团队 PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)（英文） 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a94ca-142">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="a94ca-143">相关主题</span><span class="sxs-lookup"><span data-stu-id="a94ca-143">Related topics</span></span>

[<span data-ttu-id="a94ca-144">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="a94ca-144">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

