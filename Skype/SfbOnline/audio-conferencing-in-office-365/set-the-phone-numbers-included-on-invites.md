---
title: 设置的电话号码包含在邀请
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. '
ms.openlocfilehash: 5ddc20d1b9166315581a6f894c5d630d9e247881
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568278"
---
# <a name="set-the-phone-numbers-included-on-invites"></a><span data-ttu-id="d1b7c-103">设置的电话号码包含在邀请</span><span class="sxs-lookup"><span data-stu-id="d1b7c-103">Set the phone numbers included on invites</span></span>

<span data-ttu-id="d1b7c-104">Office 365 中的音频会议，组织中的用户创建的业务和 Microsoft 团队会议 Skype，然后允许这些会议使用电话拨入的用户。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-104">Audio Conferencing in Office 365 enables users in your organization to create Skype for Business and Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span> <span data-ttu-id="d1b7c-105">在 Office 365 中，您可以使用 Microsoft 音频会议网桥或位于由已批准的音频会议提供商 (ACP) 的第三方音频会议桥的选择。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-105">In Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d1b7c-106">没有资源包含音频会议的所有拨入号码的列表。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-106">There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing.</span></span> <span data-ttu-id="d1b7c-107">如果您要查找要查看如果电话拨入电话号码中提供了您的区域或国家/地区，使用**业务管理中心的 Skype** > **语音** > **电话号码**，单击**添加**然后**新服务号码**.</span><span class="sxs-lookup"><span data-stu-id="d1b7c-107">If you are looking to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add** then **New Service Numbers**.</span></span> <span data-ttu-id="d1b7c-108">**国家/地区**，**国家/地区使用列表**和**市/县**筛选搜索。 > 此外，如果您要查找免费服务收费电话号码，选择**免费电话**从**国家/地区**列表。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-108">Use the lists for **Country/Region**, **State/Region** and **City** to filter your search.> Also, if you are looking for toll free service numbers, select **Toll-Free** from the **State/Region** list.</span></span>
  
<span data-ttu-id="d1b7c-109">会议桥为您提供了一套电话拨入电话号码为组织。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-109">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="d1b7c-110">所有这些可用于加入会议的会议组织者已创建，但您可以选择将在其会议邀请包括哪些功能。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-110">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d1b7c-111">可以有一个收费和一个免费电话号码的会议组织者，会议邀请上的最大值，但还有位于底部的每个打开的完整列表可用于加入会议的所有电话拨入电话号码的会议邀请的链接。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-111">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a><span data-ttu-id="d1b7c-112">为会议组织者设置的默认电话拨入式电话号码</span><span class="sxs-lookup"><span data-stu-id="d1b7c-112">Set the default dial-in phone number for a meeting organizer</span></span>

<span data-ttu-id="d1b7c-113">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="d1b7c-113">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="d1b7c-114">在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

    ![显示选择的 Microsoft 团队和 Skype 的业务管理中心中的用户](../images/teamsselectusers.png)

2. <span data-ttu-id="d1b7c-116">在页面的顶部，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-116">At the top of the page, click **Edit**.</span></span>

    ![单击编辑中的 Microsoft 团队和 Skype 的业务管理中心](../images/teamsedituser.png)

3. <span data-ttu-id="d1b7c-118">**音频会议**，旁边单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-118">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
    ![单击编辑旁边音频会议](../images/teamseditaudioconf.png)

4. <span data-ttu-id="d1b7c-120">使用**收费电话号码**或**免费电话号码**字段，用户输入的数字。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-120">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="d1b7c-121">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="d1b7c-121">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="d1b7c-122">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-122">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="d1b7c-123">Choose **Admin centers** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="d1b7c-123">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="d1b7c-124">选择" **用户**"。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-124">Choose **Users**.</span></span>
    
    ![业务管理中心的 Skype 中选择用户的显示](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. <span data-ttu-id="d1b7c-126">选择您想要编辑的用户：</span><span class="sxs-lookup"><span data-stu-id="d1b7c-126">Choose the users you want to edit:</span></span>
    
  - <span data-ttu-id="d1b7c-127">要选择单个用户，请选择该用户的名称。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-127">To select a single user, select the user's name.</span></span>
    
  - <span data-ttu-id="d1b7c-128">要选择页面上的所有用户，请都选择列表顶部的**显示名称**旁边的框。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-128">To select all users on the page, select the box next to **Display name** at the top of the list.</span></span>
    
  - <span data-ttu-id="d1b7c-129">要选择多个用户，请选择每个用户的名称旁边的框。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-129">To select multiple users, select the box next to each user's name.</span></span>
    
5. <span data-ttu-id="d1b7c-130">在右窗格中，选择" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-130">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="d1b7c-132">选择**音频会议**。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-132">Choose **Audio conferencing**.</span></span>
    
7. <span data-ttu-id="d1b7c-133">在**属性**页上的**提供程序名称**列表中，选择为用户提供程序。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-133">On the **Properties** page, in the **Provider name** list, choose the provider for the user.</span></span> <span data-ttu-id="d1b7c-134">具体取决于提供程序，填写下列框。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-134">Depending on the provider, complete the following boxes.</span></span>
    
  - <span data-ttu-id="d1b7c-135">**Microsoft 是提供程序**： 使用**默认收费电话号码**和**默认免费电话号码**列表选择用户的默认号码。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-135">**Microsoft is the provider**: Use the **Default toll number** and **Default toll-free number** lists to select the default numbers for the user.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d1b7c-136">它可以设置为默认免费电话号码的用户之前，必须为至少一个免费电话号码分配到您的会议桥。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-136">At least one toll-free number must be assigned to your conferencing bridge before it can be set as the default toll-free number of a user.</span></span> <span data-ttu-id="d1b7c-137">若要获取免费电话号码，请参阅[业务和 Microsoft 团队的 Skype 获取服务电话号码](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-137">To get a toll-free number, see [Getting service phone numbers for Skype for Business and Microsoft Teams](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span></span> 
  
  - <span data-ttu-id="d1b7c-138">**第三方是提供程序**： 使用**收费电话号码**和**免费电话号码**字段，用户输入的数字。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-138">**A third-party is the provider**: Use the **Toll number** and **Toll-free number** fields to enter the numbers for the user.</span></span>


## <a name="change-the-audio-conferencing-phone-number-for-users"></a><span data-ttu-id="d1b7c-139">更改用户的音频会议电话号码</span><span class="sxs-lookup"><span data-stu-id="d1b7c-139">Change the audio conferencing phone number for users</span></span>

<span data-ttu-id="d1b7c-140">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="d1b7c-140">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="d1b7c-141">在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-141">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="d1b7c-142">在页面的顶部，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-142">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="d1b7c-143">**音频会议**，旁边单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-143">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="d1b7c-144">使用**收费电话号码**或**免费电话号码**字段，用户输入的数字。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-144">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>

## <a name="reset-audio-conferencing-phone-numbers"></a><span data-ttu-id="d1b7c-145">重置音频会议的电话号码</span><span class="sxs-lookup"><span data-stu-id="d1b7c-145">Reset audio conferencing phone numbers</span></span>

<span data-ttu-id="d1b7c-146">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="d1b7c-146">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="d1b7c-147">在**Skype 业务管理中心的**中，选择**要进行音频会议**。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-147">In the **Skype for Business admin center**, choose **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="d1b7c-148">在页面顶部，选择**用户**。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-148">At the top of the page, choose **Users**.</span></span>
    
3. <span data-ttu-id="d1b7c-149">选择您要重置的用户，然后单击在操作窗格的**清除**。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-149">Choose the users you want to reset, and then in the Action pane, click **Clear**.</span></span>
    
<span data-ttu-id="d1b7c-150">默认情况下，当您更改用户的会议设置电子邮件发送给用户。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-150">By default, when you change a user's conferencing settings, an email is sent to the user.</span></span> <span data-ttu-id="d1b7c-151">若要更改此设置，请参阅[启用或禁用发送电子邮件时要进行音频会议设置更改](enable-or-disable-sending-emails-when-their-settings-change.md)。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-151">To change this, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d1b7c-152">更改用户的音频会议设置时，必须更新定期和将来的 Skype，业务和 Microsoft 团队的会议，并将其发送给与会者中。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-152">When you change a user's audio conferencing settings, recurring and future Skype for Business and Microsoft Teams meetings must be updated and sent to attendees.</span></span> 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="d1b7c-153">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="d1b7c-153">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="d1b7c-154">为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-154">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet.</span></span>
    
- <span data-ttu-id="d1b7c-155">使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet 可更改特定用户的默认收费电话号码或免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-155">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>
    
    <span data-ttu-id="d1b7c-156">若要更改用户的默认免费电话号码，请运行：</span><span class="sxs-lookup"><span data-stu-id="d1b7c-156">To change the default toll-free number for a user, run:</span></span>
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- <span data-ttu-id="d1b7c-157">使用 **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet 可基于用户的原始默认电话号码或位置来更改其默认收费电话号码或免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-157">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d1b7c-158">若要查找 BridgeID，使用**Get-CsOnlineDialInConferencingBridge** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d1b7c-158">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge** cmdlet.</span></span>
  
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - <span data-ttu-id="d1b7c-159">若要不向 +18005551234 的所有用户设置默认免费电话号码，请运行：</span><span class="sxs-lookup"><span data-stu-id="d1b7c-159">To set the default toll-free number for all users without one to +18005551234, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - <span data-ttu-id="d1b7c-160">若要更改的所有用户的已为其默认免费电话号码与 +18005551239 +18005551234 默认免费电话号码，请运行：</span><span class="sxs-lookup"><span data-stu-id="d1b7c-160">To change the default toll-free number of all users that have +18005551234 as their default toll-free number to +18005551239, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="d1b7c-161">若要设置的位于到 +18005551234 美国的所有用户的默认免费电话号码，请运行：</span><span class="sxs-lookup"><span data-stu-id="d1b7c-161">To set the default toll-free number of all users located in the U.S. to +18005551234, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
## <a name="want-to-learn-more-about-windows-powershell"></a><span data-ttu-id="d1b7c-162">要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="d1b7c-162">Want to learn more about Windows PowerShell?</span></span>
- <span data-ttu-id="d1b7c-p107">对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="d1b7c-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d1b7c-166">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="d1b7c-166">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="d1b7c-167">为什么您需要使用 Office 365 PowerShell 中</span><span class="sxs-lookup"><span data-stu-id="d1b7c-167">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="d1b7c-p108">例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="d1b7c-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="d1b7c-170">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="d1b7c-170">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="d1b7c-171">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d1b7c-171">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="d1b7c-172">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="d1b7c-172">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="d1b7c-173">相关主题</span><span class="sxs-lookup"><span data-stu-id="d1b7c-173">Related topics</span></span>

[<span data-ttu-id="d1b7c-174">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="d1b7c-174">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
