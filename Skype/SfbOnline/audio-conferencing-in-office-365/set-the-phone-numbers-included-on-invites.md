---
title: 设置包含在 Skype for Business Online 邀请中的电话号码
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. '
ms.openlocfilehash: cb808cb8271cfb32174106e2692793aa41a64d50
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882110"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a><span data-ttu-id="47b8a-103">设置包含在 Skype for Business Online 邀请中的电话号码</span><span class="sxs-lookup"><span data-stu-id="47b8a-103">Set the phone numbers included on invites in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="47b8a-104">有关 Microsoft Teams 中的会议邀请电话号码的信息，请参阅[设置 Microsoft Teams 中包含的电话号码](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="47b8a-104">For information about meeting invite phone numbers in Microsoft Teams, see [Set the phone numbers included on invites in Microsoft Teams](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).</span></span>

<span data-ttu-id="47b8a-105">Office 365 中的音频会议使组织中的用户能够创建 Skype for Business 会议，然后允许用户使用电话拨入到这些会议。</span><span class="sxs-lookup"><span data-stu-id="47b8a-105">Audio Conferencing in Office 365 enables users in your organization to create Skype for Business meetings, and then allow users to dial in to those meetings using a phone.</span></span> <span data-ttu-id="47b8a-106">在 Office 365 中，您可以使用 Microsoft 音频会议网桥或位于由已批准的音频会议提供商 (ACP) 的第三方音频会议桥的选择。</span><span class="sxs-lookup"><span data-stu-id="47b8a-106">In Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
> [!NOTE]
> <span data-ttu-id="47b8a-107">没有资源包含音频会议的所有拨入号码的列表。</span><span class="sxs-lookup"><span data-stu-id="47b8a-107">There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing.</span></span> <span data-ttu-id="47b8a-108">如果您要查找要查看如果电话拨入电话号码中提供了您的区域或国家/地区，使用**业务管理中心的 Skype** > **语音** > **电话号码**，单击**添加**然后**新服务号码**.</span><span class="sxs-lookup"><span data-stu-id="47b8a-108">If you are looking to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add** then **New Service Numbers**.</span></span> <span data-ttu-id="47b8a-109">使用**国家/地区**、\*\* 州/地区**和**城市**列表筛选搜索。 此外，如果要查找免费服务电话号码，从** 国家/地区**列表中选择**免费电话\*\*。</span><span class="sxs-lookup"><span data-stu-id="47b8a-109">Use the lists for **Country/Region**, **State/Region** and **City** to filter your search.> Also, if you are looking for toll free service numbers, select **Toll-Free** from the **State/Region** list.</span></span>
  
<span data-ttu-id="47b8a-110">会议桥为你的组织提供了一套拨入电话号码。</span><span class="sxs-lookup"><span data-stu-id="47b8a-110">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="47b8a-111">它们都可用于加入会议组织者已创建的会议，但你可以选择在其会议邀请中包括哪些号码。</span><span class="sxs-lookup"><span data-stu-id="47b8a-111">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="47b8a-112">会议组织者的会议邀请中最多可以有一个收费和一个免费电话号码，但每个会议邀请的底部还有一个链接，用于打开用来可加入会议的所有拨入电话号码的完整列表。</span><span class="sxs-lookup"><span data-stu-id="47b8a-112">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a><span data-ttu-id="47b8a-113">为会议组织者设置默认的拨入电话号码</span><span class="sxs-lookup"><span data-stu-id="47b8a-113">Set the default dial-in phone number for a meeting organizer</span></span>

1. <span data-ttu-id="47b8a-114">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="47b8a-114">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="47b8a-115">选择 **管理中心** > **Skype for Business** 。</span><span class="sxs-lookup"><span data-stu-id="47b8a-115">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="47b8a-116">选择" **用户**"。</span><span class="sxs-lookup"><span data-stu-id="47b8a-116">Choose **Users**.</span></span>
    
    ![在 Skype for Business 管理中心显示选择用户](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. <span data-ttu-id="47b8a-118">选择您想要编辑的用户：</span><span class="sxs-lookup"><span data-stu-id="47b8a-118">Choose the users you want to edit:</span></span>
    
  - <span data-ttu-id="47b8a-119">要选择单个用户，请选择该用户的名称。</span><span class="sxs-lookup"><span data-stu-id="47b8a-119">To select a single user, select the user's name.</span></span>
    
  - <span data-ttu-id="47b8a-120">要选择页面上的所有用户，请都选择列表顶部**显示名称**旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="47b8a-120">To select all users on the page, select the box next to **Display name** at the top of the list.</span></span>
    
  - <span data-ttu-id="47b8a-121">要选择多个用户，请选择每个用户名称旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="47b8a-121">To select multiple users, select the box next to each user's name.</span></span>
    
5. <span data-ttu-id="47b8a-122">在右窗格中，选择" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="47b8a-122">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="47b8a-124">选择**音频会议**。</span><span class="sxs-lookup"><span data-stu-id="47b8a-124">Choose **Audio conferencing**.</span></span>
    
7. <span data-ttu-id="47b8a-125">在**属性**页上的**提供商名称**列表中，为用户选择提供商。</span><span class="sxs-lookup"><span data-stu-id="47b8a-125">On the **Properties** page, in the **Provider name** list, choose the provider for the user.</span></span> <span data-ttu-id="47b8a-126">根据提供商填写下列方框。</span><span class="sxs-lookup"><span data-stu-id="47b8a-126">Depending on the provider, complete the following boxes.</span></span>
    
  - <span data-ttu-id="47b8a-127">**Microsoft 是提供商**：使用**默认收费电话号码**和**默认免费电话号码**列表选择用户的默认号码。</span><span class="sxs-lookup"><span data-stu-id="47b8a-127">**Microsoft is the provider**: Use the **Default toll number** and **Default toll-free number** lists to select the default numbers for the user.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="47b8a-128">在将电话号码设置为用户的默认免费电话号码之前，必须为至少向会议桥分配一个免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="47b8a-128">At least one toll-free number must be assigned to your conferencing bridge before it can be set as the default toll-free number of a user.</span></span> <span data-ttu-id="47b8a-129">若要获取免费电话号码，请参阅[入门 Skype for Business 服务电话号码](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="47b8a-129">To get a toll-free number, see [Getting service phone numbers for Skype for Business](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span></span> 
  
  - <span data-ttu-id="47b8a-130">**第三方是提供商**：使用**收费电话号码**和**免费电话号码**字段，为用户输入号码。</span><span class="sxs-lookup"><span data-stu-id="47b8a-130">**A third-party is the provider**: Use the **Toll number** and **Toll-free number** fields to enter the numbers for the user.</span></span>


## <a name="reset-audio-conferencing-phone-numbers"></a><span data-ttu-id="47b8a-131">重置音频会议的电话号码</span><span class="sxs-lookup"><span data-stu-id="47b8a-131">Reset audio conferencing phone numbers</span></span>

1. <span data-ttu-id="47b8a-132">在**Skype 业务管理中心的**中，选择**要进行音频会议**。</span><span class="sxs-lookup"><span data-stu-id="47b8a-132">In the **Skype for Business admin center**, choose **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="47b8a-133">在页面顶部，选择**用户**。</span><span class="sxs-lookup"><span data-stu-id="47b8a-133">At the top of the page, choose **Users**.</span></span>
    
3. <span data-ttu-id="47b8a-134">选择要重置的用户，然后在操作窗格单击**清除**。</span><span class="sxs-lookup"><span data-stu-id="47b8a-134">Choose the users you want to reset, and then in the Action pane, click **Clear**.</span></span>
    
<span data-ttu-id="47b8a-135">默认情况下，更改用户的会议设置时会给用户发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="47b8a-135">By default, when you change a user's conferencing settings, an email is sent to the user.</span></span> <span data-ttu-id="47b8a-136">若要更改此设置，请参阅[启用或禁用发送电子邮件时要进行音频会议设置更改](enable-or-disable-sending-emails-when-their-settings-change.md)。</span><span class="sxs-lookup"><span data-stu-id="47b8a-136">To change this, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="47b8a-137">更改用户的音频会议设置时，必须更新定期和将来的 Skype for Business 会议，并将其发送给与会者。</span><span class="sxs-lookup"><span data-stu-id="47b8a-137">When you change a user's audio conferencing settings, recurring and future Skype for Business meetings must be updated and sent to attendees.</span></span> 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="47b8a-138">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="47b8a-138">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="47b8a-139">为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="47b8a-139">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet.</span></span>
    
- <span data-ttu-id="47b8a-140">使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet 可更改特定用户的默认收费电话号码或免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="47b8a-140">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>
    
    <span data-ttu-id="47b8a-141">若要更改用户的默认免费电话号码，请运行：</span><span class="sxs-lookup"><span data-stu-id="47b8a-141">To change the default toll-free number for a user, run:</span></span>
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- <span data-ttu-id="47b8a-142">使用 **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet 可基于用户的原始默认电话号码或位置来更改其默认收费电话号码或免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="47b8a-142">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="47b8a-143">若要查找 BridgeID，使用**Get-CsOnlineDialInConferencingBridge** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="47b8a-143">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge** cmdlet.</span></span>
  
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - <span data-ttu-id="47b8a-144">若要不向 +18005551234 的所有用户设置默认免费电话号码，请运行：</span><span class="sxs-lookup"><span data-stu-id="47b8a-144">To set the default toll-free number for all users without one to +18005551234, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - <span data-ttu-id="47b8a-145">若要更改的所有用户的已为其默认免费电话号码与 +18005551239 +18005551234 默认免费电话号码，请运行：</span><span class="sxs-lookup"><span data-stu-id="47b8a-145">To change the default toll-free number of all users that have +18005551234 as their default toll-free number to +18005551239, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="47b8a-146">若要设置的位于到 +18005551234 美国的所有用户的默认免费电话号码，请运行：</span><span class="sxs-lookup"><span data-stu-id="47b8a-146">To set the default toll-free number of all users located in the U.S. to +18005551234, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
## <a name="want-to-learn-more-about-windows-powershell"></a><span data-ttu-id="47b8a-147">要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="47b8a-147">Want to learn more about Windows PowerShell?</span></span>
- <span data-ttu-id="47b8a-p107">对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="47b8a-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="47b8a-151">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="47b8a-151">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="47b8a-152">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="47b8a-152">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="47b8a-p108">例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="47b8a-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="47b8a-155">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="47b8a-155">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="47b8a-156">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="47b8a-156">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="47b8a-157">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="47b8a-157">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="47b8a-158">相关主题</span><span class="sxs-lookup"><span data-stu-id="47b8a-158">Related topics</span></span>

[<span data-ttu-id="47b8a-159">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="47b8a-159">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
