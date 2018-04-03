---
title: 将的电话号码包括在邀请
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
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
description: 'Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. '
ms.openlocfilehash: 59ebd95f5b7f7ee546ab272596adf353b2a7adbc
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2018
---
# <a name="set-the-phone-numbers-included-on-invites"></a><span data-ttu-id="38944-103">将的电话号码包括在邀请</span><span class="sxs-lookup"><span data-stu-id="38944-103">Set the phone numbers included on invites</span></span>

<span data-ttu-id="38944-104">Office 365 中的音频会议使组织中的用户创建 Skype 业务和 Microsoft 小组会议，然后允许用户拨入到那些使用电话的会议。</span><span class="sxs-lookup"><span data-stu-id="38944-104">Audio Conferencing in Office 365 enables users in your organization to create Skype for Business and Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span> <span data-ttu-id="38944-105">Office 365 中您可以使用 Microsoft 音频会议桥或由经认可的音频会议提供商 (ACP) 承载第三方音频会议桥的选择。</span><span class="sxs-lookup"><span data-stu-id="38944-105">In Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
> [!NOTE]
> <span data-ttu-id="38944-106">没有资源包含音频会议的所有拨入号码的列表。</span><span class="sxs-lookup"><span data-stu-id="38944-106">There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing.</span></span> <span data-ttu-id="38944-107">如果您希望看到如果有可用的拨入电话号码在您的区域或国家/地区，使用**Skype 业务管理中心的** > **语音** > **的电话号码**，单击**添加**，然后**新的服务编号**.</span><span class="sxs-lookup"><span data-stu-id="38944-107">If you are looking to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add** then **New Service Numbers**.</span></span> <span data-ttu-id="38944-108">对于**国家/地区**，请**国家/地区中使用的列表**和**城市**筛选 > 而且，如果您正在寻找免费服务收费电话号码，选择**免费**从**国家/地区**列表。</span><span class="sxs-lookup"><span data-stu-id="38944-108">Use the lists for **Country/Region**, **State/Region** and **City** to filter your search.> Also, if you are looking for toll free service numbers, select **Toll-Free** from the **State/Region** list.</span></span>
  
<span data-ttu-id="38944-109">会议桥提供为您的组织的拨入电话号码组。</span><span class="sxs-lookup"><span data-stu-id="38944-109">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="38944-110">所有这些可以用来参加会议，会议组织者创建，但是您可以选择哪些文件将包括在其会议的邀请。</span><span class="sxs-lookup"><span data-stu-id="38944-110">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="38944-111">可以有一个免费电话和邀请的会议组织者，在一个免费电话号码的最多，但还有底部打开的完整列表，可用于参加会议的所有拨入电话号码中的每个会议邀请中的链接。</span><span class="sxs-lookup"><span data-stu-id="38944-111">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 
  
## <a name="setting-the-default-dial-in-phone-number-for-a-meeting-organizer"></a><span data-ttu-id="38944-112">会议组织者设置的默认拨入电话号码</span><span class="sxs-lookup"><span data-stu-id="38944-112">Setting the default dial-in phone number for a meeting organizer</span></span>

1. <span data-ttu-id="38944-113">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="38944-113">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="38944-114">Choose **Admin centers** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="38944-114">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="38944-115">选择" **用户**"。</span><span class="sxs-lookup"><span data-stu-id="38944-115">Choose **Users**.</span></span>
    
    ![显示业务管理中心为 Skype 中选择用户](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. <span data-ttu-id="38944-117">选择您要编辑的用户：</span><span class="sxs-lookup"><span data-stu-id="38944-117">Choose the users you want to edit:</span></span>
    
  - <span data-ttu-id="38944-118">若要选择单个用户，请选择用户的名称。</span><span class="sxs-lookup"><span data-stu-id="38944-118">To select a single user, select the user's name.</span></span>
    
  - <span data-ttu-id="38944-119">要选择该页上的所有用户，请都选择位于列表的顶部**显示名称**旁边的框。</span><span class="sxs-lookup"><span data-stu-id="38944-119">To select all users on the page, select the box next to **Display name** at the top of the list.</span></span>
    
  - <span data-ttu-id="38944-120">若要选择多个用户，请选择每个用户的名称旁边的框。</span><span class="sxs-lookup"><span data-stu-id="38944-120">To select multiple users, select the box next to each user's name.</span></span>
    
5. <span data-ttu-id="38944-121">在右窗格中，选择" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="38944-121">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="38944-123">选择**音频会议**。</span><span class="sxs-lookup"><span data-stu-id="38944-123">Choose **Audio conferencing**.</span></span>
    
7. <span data-ttu-id="38944-124">在**属性**页的**提供程序名称**列表中，选择为用户提供。</span><span class="sxs-lookup"><span data-stu-id="38944-124">On the **Properties** page, in the **Provider name** list, choose the provider for the user.</span></span> <span data-ttu-id="38944-125">根据提供商中，填写以下框。</span><span class="sxs-lookup"><span data-stu-id="38944-125">Depending on the provider, complete the following boxes.</span></span>
    
  - <span data-ttu-id="38944-126">**Microsoft 将提供程序**： 使用**默认收费电话号码**和**免费电话号码的默认**列表选择用户的默认数字。</span><span class="sxs-lookup"><span data-stu-id="38944-126">**Microsoft is the provider**: Use the **Default toll number** and **Default toll-free number** lists to select the default numbers for the user.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="38944-127">至少一个免费电话号码必须分配给会议桥前它可以设置为用户的默认免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="38944-127">At least one toll-free number must be assigned to your conferencing bridge before it can be set as the default toll-free number of a user.</span></span> <span data-ttu-id="38944-128">若要获取免费电话号码，请参阅[获得 Skype 业务和 Microsoft 团队的服务电话号码](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="38944-128">To get a toll-free number, see [Getting service phone numbers for Skype for Business and Microsoft Teams](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span></span> 
  
  - <span data-ttu-id="38944-129">**第三方为提供程序**： 使用**收费电话号码**和**免费电话号码**字段，用户输入的数字。</span><span class="sxs-lookup"><span data-stu-id="38944-129">**A third-party is the provider**: Use the **Toll number** and **Toll-free number** fields to enter the numbers for the user.</span></span>
    
## <a name="reset-audio-conferencing-phone-numbers"></a><span data-ttu-id="38944-130">重置音频会议电话号码</span><span class="sxs-lookup"><span data-stu-id="38944-130">Reset audio conferencing phone numbers</span></span>

1. <span data-ttu-id="38944-131">在**Skype 的业务管理中心**，选择**音频会议**。</span><span class="sxs-lookup"><span data-stu-id="38944-131">In the **Skype for Business admin center**, choose **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="38944-132">在页面的顶部，选择**用户**。</span><span class="sxs-lookup"><span data-stu-id="38944-132">At the top of the page, choose **Users**.</span></span>
    
3. <span data-ttu-id="38944-133">选择您要重置，的用户，然后在操作窗格中，单击**清除**。</span><span class="sxs-lookup"><span data-stu-id="38944-133">Choose the users you want to reset, and then in the Action pane, click **Clear**.</span></span>
    
<span data-ttu-id="38944-134">默认情况下，当您更改用户的会议设置，电子邮件发送给用户。</span><span class="sxs-lookup"><span data-stu-id="38944-134">By default, when you change a user's conferencing settings, an email is sent to the user.</span></span> <span data-ttu-id="38944-135">若要更改此设置，请参阅[启用或禁用音频会议设置更改时发送的电子邮件](enable-or-disable-sending-emails-when-their-settings-change.md)。</span><span class="sxs-lookup"><span data-stu-id="38944-135">To change this, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="38944-136">更改用户的音频会议设置时，必须更新定期和未来 Skype 业务和 Microsoft 小组会议，并发送给与会者。</span><span class="sxs-lookup"><span data-stu-id="38944-136">When you change a user's audio conferencing settings, recurring and future Skype for Business and Microsoft Teams meetings must be updated and sent to attendees.</span></span> 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="38944-137">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="38944-137">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="38944-138">为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="38944-138">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet.</span></span>
    
- <span data-ttu-id="38944-139">使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet 可更改特定用户的默认收费电话号码或免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="38944-139">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>
    
    <span data-ttu-id="38944-140">若要更改用户的默认免费电话号码，请运行：</span><span class="sxs-lookup"><span data-stu-id="38944-140">To change the default toll-free number for a user, run:</span></span>
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- <span data-ttu-id="38944-141">使用 **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet 可基于用户的原始默认电话号码或位置来更改其默认收费电话号码或免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="38944-141">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="38944-142">若要查找 BridgeID，使用**Get CsOnlineDialInConferencingBridge**。</span><span class="sxs-lookup"><span data-stu-id="38944-142">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>
  
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - <span data-ttu-id="38944-143">若要设置默认的免费电话号码没有 1 到 +18005551234 的所有用户，请运行：</span><span class="sxs-lookup"><span data-stu-id="38944-143">To set the default toll-free number for all users without one to +18005551234, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - <span data-ttu-id="38944-144">若要更改默认的 +18005551234 作为其默认免费电话号码为 +18005551239 的所有用户的免费电话号码，请运行：</span><span class="sxs-lookup"><span data-stu-id="38944-144">To change the default toll-free number of all users that have +18005551234 as their default toll-free number to +18005551239, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="38944-145">若要设置默认的 （美国） 到 +18005551234 中的所有用户的免费电话号码，请运行：</span><span class="sxs-lookup"><span data-stu-id="38944-145">To set the default toll-free number of all users located in the U.S. to +18005551234, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
## <a name="want-to-learn-more-about-windows-powershell"></a><span data-ttu-id="38944-146">要了解有关 Windows PowerShell？</span><span class="sxs-lookup"><span data-stu-id="38944-146">Want to learn more about Windows PowerShell?</span></span>
- <span data-ttu-id="38944-p107">对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="38944-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="38944-150">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="38944-150">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="38944-151">为什么需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="38944-151">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="38944-p108">例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="38944-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="38944-154">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="38944-154">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="38944-155">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="38944-155">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="38944-156">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="38944-156">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="38944-157">相关主题</span><span class="sxs-lookup"><span data-stu-id="38944-157">Related topics</span></span>

[<span data-ttu-id="38944-158">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="38944-158">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
