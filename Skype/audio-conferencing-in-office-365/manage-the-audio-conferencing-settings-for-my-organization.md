---
title: "管理我的组织的音频会议设置"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'See steps to assign a dial-in conferencing license and conference ID to a user, set up a third party conferencing provider, and many other dial-in conferencing settings. '
ms.openlocfilehash: 6bca89f60c5ee4e9b840d2094500077cfa972902
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2017
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a><span data-ttu-id="198fa-103">管理我的组织的音频会议设置</span><span class="sxs-lookup"><span data-stu-id="198fa-103">Manage the Audio Conferencing settings for my organization</span></span>

<span data-ttu-id="198fa-104">它可能是便于您查看所有业务和 Microsoft 小组在一个位置对 Skype 的音频会议设置。</span><span class="sxs-lookup"><span data-stu-id="198fa-104">It might be easier for you to see all of the audio conferencing settings for Skype for Business and Microsoft Teams in one place.</span></span> 
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="198fa-105">指定音频会议许可证</span><span class="sxs-lookup"><span data-stu-id="198fa-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="198fa-106">不能分配许可证使用**Skype 的业务管理中心**。</span><span class="sxs-lookup"><span data-stu-id="198fa-106">You can't assign licenses using the **Skype for Business admin center**.</span></span> <span data-ttu-id="198fa-107">您必须使用 Office 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="198fa-107">You must use the Office 365 admin center.</span></span> <span data-ttu-id="198fa-108">请参阅[指派的 Skype 业务和 Microsoft 小组的许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="198fa-108">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
 <span data-ttu-id="198fa-109">**若要指定用户的许可证**</span><span class="sxs-lookup"><span data-stu-id="198fa-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="198fa-110">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="198fa-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="198fa-111">在**Office 365 管理中心**左侧导航，请转到**用户** > **活动用户**，然后从可用用户列表中选择的用户。</span><span class="sxs-lookup"><span data-stu-id="198fa-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="198fa-112">如果您要在同一时间分配到最多 20 个用户许可证，可以使用**选择视图**下拉列表，然后选择其中一个选项或创建自己的视图。</span><span class="sxs-lookup"><span data-stu-id="198fa-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="198fa-113">然后单击**编辑****下一步**两次，然后选择的许可证并单击**提交**。</span><span class="sxs-lookup"><span data-stu-id="198fa-113">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span> <span data-ttu-id="198fa-114">此外可以将许可证分配给多个用户，通过使用 Windows Powershell。</span><span class="sxs-lookup"><span data-stu-id="198fa-114">You can also assign licenses to multiple users by using Windows Powershell.</span></span> <span data-ttu-id="198fa-115">有关说明和示例 PowerShell 脚本，请参阅[分配的 Skype 业务和 Microsoft 小组的许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="198fa-115">For instructions and sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
3. <span data-ttu-id="198fa-116">在"操作"窗格中的" **产品许可证**"下，单击" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="198fa-116">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="198fa-117">在**产品许可证**页上，打开**音频会议**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="198fa-117">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="198fa-118">有关授权的详细信息，请参阅[附加业务和 Microsoft 小组授权的 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="198fa-118">For more on licensing, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="198fa-119">指定许可证后，Microsoft 可能不会初始显示在列表中为音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="198fa-119">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider.</span></span> <span data-ttu-id="198fa-120">如果发生这种情况，从 Office 365 管理中心注销或者按 CTRL + F5 来刷新浏览器窗口。</span><span class="sxs-lookup"><span data-stu-id="198fa-120">If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="assign-a-conference-id-for-a-user"></a><span data-ttu-id="198fa-121">为用户分配会议 ID</span><span class="sxs-lookup"><span data-stu-id="198fa-121">Assign a conference ID for a user</span></span>

<span data-ttu-id="198fa-122">当设置为作为音频会议提供商使用 Microsoft 的音频会议，会议 ID 自动分配给用户。</span><span class="sxs-lookup"><span data-stu-id="198fa-122">A conference ID is automatically assigned to a user when they are set up for audio conferencing using Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="198fa-123">指定的会议 ID 可以是静态或动态，以及时安排的会议，在会议邀请中发送。</span><span class="sxs-lookup"><span data-stu-id="198fa-123">The conference ID assigned can be either static or dynamic and is sent in the meeting invite when the meeting is scheduled.</span></span> 
  
<span data-ttu-id="198fa-124">当您组织中的人不想记得的随机数; 使用静态标识符他们可以选择一定数量或选择一个容易记住。</span><span class="sxs-lookup"><span data-stu-id="198fa-124">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or choose one that's easy to remember.</span></span> <span data-ttu-id="198fa-125">当使用动态会议 Id 时，每个会议用户计划将获得分配唯一的会议 id。</span><span class="sxs-lookup"><span data-stu-id="198fa-125">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="198fa-126">如果您想要分配动态而非静态的会议 Id，请参阅[使用音频会议动态 Id，您的组织中](using-audio-conferencing-dynamic-ids-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="198fa-126">If you want to assign dynamic rather than static conference IDs, see [Using Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="198fa-127">不能使用 Skype for Business 管理中心来向用户分配会议 ID，但你可以使用 Windows PowerShell cmdlet 来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="198fa-127">The Skype for Business admin center can't be used to assign a conference ID to a user, but you can use the Windows PowerShell cmdlet to do this.</span></span>
  
<span data-ttu-id="198fa-128">若要为用户设置会议 ID，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="198fa-128">To set the conference ID for a user, run:</span></span>
  
```
Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964 
```

> [!IMPORTANT]
> <span data-ttu-id="198fa-129">会议 ID 必须包含 7 位数字，并不能在 Skype 业务管理中心或使用 Windows PowerShell 中进行更改。</span><span class="sxs-lookup"><span data-stu-id="198fa-129">A conference ID must contain 7 digits, and you can't change it in the Skype for Business admin center or by using Windows PowerShell.</span></span> 
  
<span data-ttu-id="198fa-130">请参阅 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) 以了解有关 cmdlet 的更多信息。</span><span class="sxs-lookup"><span data-stu-id="198fa-130">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="198fa-131">创建一个新的会议 ID 后，调用方不能使用旧的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="198fa-131">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="198fa-132">应通知用户重新安排现有会议，以确保新的会议 ID 添加到邀请的邀请。</span><span class="sxs-lookup"><span data-stu-id="198fa-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="198fa-133">用户可以使用 Skype 业务会议迁移工具来更新其现有的会议。</span><span class="sxs-lookup"><span data-stu-id="198fa-133">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="198fa-134">若要了解如何下载、 安装和运行 Skype 业务会议更新工具，请参阅：[为业务和 Lync Skype 会议更新工具](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)、 [Skype 业务在线，会议迁移工具 （64 位）](http://go.microsoft.com/fwlink/?LinkID=626047)和[Skype 的在线业务会议迁移工具 （32 位）](https://www.microsoft.com/en-us/download/details.aspx?id=54079)。</span><span class="sxs-lookup"><span data-stu-id="198fa-134">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="198fa-135">请参阅[请参阅、 更改和重置会议 ID 分配给用户](see-change-and-reset-a-conference-id-assigned-to-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="198fa-135">See [See, change, and reset a conference ID assigned to a user](see-change-and-reset-a-conference-id-assigned-to-a-user.md).</span></span>
  
## <a name="change-the-audio-conferencing-provider-from-microsoft-to-a-third-party-provider"></a><span data-ttu-id="198fa-136">更改音频会议提供商从 Microsoft 给第三方提供商</span><span class="sxs-lookup"><span data-stu-id="198fa-136">Change the audio conferencing provider from Microsoft to a third-party provider</span></span>

1. <span data-ttu-id="198fa-137">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="198fa-137">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="198fa-138">请转到**Office 365 管理中心** > **业务的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="198fa-138">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="198fa-139">在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议** > **用户**，然后选择您想要更改的音频会议提供商的用户。</span><span class="sxs-lookup"><span data-stu-id="198fa-139">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then and select the user you want to change the audio conferencing provider for.</span></span>
    
4. <span data-ttu-id="198fa-140">在"操作"窗格中，单击" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="198fa-140">In the Action pane, click **Edit**.</span></span> 
    
5. <span data-ttu-id="198fa-141">在**属性**页上，在**提供程序的名称**，选择音频会议提供商的用户。</span><span class="sxs-lookup"><span data-stu-id="198fa-141">On the **Properties** page, under **Provider name**, choose the audio conferencing provider for the user.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="198fa-142">如果选择了多个用户，您可以只选择音频会议提供商或**无**作为 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="198fa-142">You can only select Microsoft as the audio conferencing provider or **None** if you have selected multiple users.</span></span>
  
6. <span data-ttu-id="198fa-143">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="198fa-143">Click **Save**.</span></span> 
    
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="198fa-144">启用或禁用音频会议的用户发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="198fa-144">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="198fa-145">可以使用业务管理中心为 Skype 或 Windows PowerShell 启用或禁用电子邮件发送给用户。</span><span class="sxs-lookup"><span data-stu-id="198fa-145">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>
  
 <span data-ttu-id="198fa-146">**使用 Skype 业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="198fa-146">**Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="198fa-147">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="198fa-147">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="198fa-148">请转到**Office 365 管理中心** > **Skype 业务**并在左边的导航，请单击**音频会议**。</span><span class="sxs-lookup"><span data-stu-id="198fa-148">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="198fa-149">在**Microsoft 桥设置**页上，选中或清除**自动发送电子邮件发送给用户，如果他们的音频会议设置更改**。</span><span class="sxs-lookup"><span data-stu-id="198fa-149">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="198fa-150">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="198fa-150">Click **Save**.</span></span>
    
    <span data-ttu-id="198fa-151">您还可以发送电子邮件给用户使用音频会议设置通过转到用户的音频会议属性并单击**将会议信息通过电子邮件发送**。</span><span class="sxs-lookup"><span data-stu-id="198fa-151">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span> <span data-ttu-id="198fa-152">会议邀请但不是插针上包含会议 ID 和默认音频会议电话号码。</span><span class="sxs-lookup"><span data-stu-id="198fa-152">The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>
    
    <span data-ttu-id="198fa-153">请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。</span><span class="sxs-lookup"><span data-stu-id="198fa-153">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
 <span data-ttu-id="198fa-154">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="198fa-154">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="198fa-155">你还可以使用 Windows PowerShell 并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="198fa-155">You can also use the Windows PowerShell and run:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="198fa-156">[一组 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285)可用于管理您的组织，包括电子邮件的其他设置。</span><span class="sxs-lookup"><span data-stu-id="198fa-156">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) to manage other settings for your organization, including email.</span></span>
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="198fa-157">更改发送给用户的电子邮件中的发件人的联系人信息</span><span class="sxs-lookup"><span data-stu-id="198fa-157">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="198fa-158">您可以对电子邮件自动发送给您的用户，包括实际的电子邮件地址和发件人的联系人信息的显示名称进行更改。</span><span class="sxs-lookup"><span data-stu-id="198fa-158">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="198fa-159">默认情况下，电子邮件的发件人是 Office 365，但您可以更改的电子邮件地址和显示名称使用 Windows PowerShell 和[一组 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="198fa-159">By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span> <span data-ttu-id="198fa-160">若要将电子邮件发送到用户的电子邮件地址进行更改，您必须：</span><span class="sxs-lookup"><span data-stu-id="198fa-160">To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="198fa-161">在_SendEmailFromAddress_参数中输入电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="198fa-161">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="198fa-162">在  _SendEmailFromDisplayName_ 参数中输入电子邮件的显示名称。</span><span class="sxs-lookup"><span data-stu-id="198fa-162">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="198fa-163">将_SendEmailOverride_参数设置为_True_。</span><span class="sxs-lookup"><span data-stu-id="198fa-163">Set the _SendEmailOverride_ parameter to _True_.</span></span>
    
<span data-ttu-id="198fa-164">你可以运行如下命令，更改发送给用户的电子邮件，例如电子邮件的发件人电子邮件地址，或者电子邮件的显示名称：</span><span class="sxs-lookup"><span data-stu-id="198fa-164">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="198fa-165">如果要更改电子邮件地址信息，你需要确保你的组织的入站电子邮件策略允许来自自定义电子邮件地址的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="198fa-165">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>
  
<span data-ttu-id="198fa-166">可以使用[一组 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet 来管理您的组织，包括电子邮件的其他设置。</span><span class="sxs-lookup"><span data-stu-id="198fa-166">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
<span data-ttu-id="198fa-167">[电子邮件自动发送给用户的音频会议设置更改时](emails-sent-to-users-when-their-settings-change.md)，请参阅。</span><span class="sxs-lookup"><span data-stu-id="198fa-167">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="198fa-168">重置会议 ID</span><span class="sxs-lookup"><span data-stu-id="198fa-168">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="198fa-169">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="198fa-169">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="198fa-170">请转到**Office 365 管理中心** > **业务的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="198fa-170">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="198fa-171">在**业务管理中心的 Skype**，在左边的导航，转到**音频会议**，然后在**会议 ID**下的操作窗格中，请单击**重置**。</span><span class="sxs-lookup"><span data-stu-id="198fa-171">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="198fa-172">在**会议 ID 重置？**窗口中，单击**是**。</span><span class="sxs-lookup"><span data-stu-id="198fa-172">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="198fa-173">将自动创建一个会议 ID，并将电子邮件发送给您的用户是否已启用的新的会议 ID 向该用户发送的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="198fa-173">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="198fa-174">它是默认启用的。</span><span class="sxs-lookup"><span data-stu-id="198fa-174">It's enabled by default.</span></span>
    
    > [!IMPORTANT]
    >  <span data-ttu-id="198fa-175">创建一个新的会议 ID 后，调用方不能使用旧的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="198fa-175">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="198fa-176">应通知用户重新安排现有会议，以确保新的会议 ID 添加到邀请的邀请。</span><span class="sxs-lookup"><span data-stu-id="198fa-176">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="198fa-177">用户可以使用 Skype 业务会议迁移工具来更新其现有的会议。</span><span class="sxs-lookup"><span data-stu-id="198fa-177">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="198fa-178">若要了解如何下载、 安装和运行 Skype 业务会议更新工具，请参阅: [会议更新工具 Skype 业务和 Lync] ((https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4) [Skype 的在线业务会议迁移工具 （64 位）](http://go.microsoft.com/fwlink/?LinkID=626047)，和[Skype 的在线业务、 会议迁移工具 （32 位）](https://www.microsoft.com/en-us/download/details.aspx?id=54079)。</span><span class="sxs-lookup"><span data-stu-id="198fa-178">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync]((https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="198fa-179">请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="198fa-179">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="198fa-180">重置会议组织者的 PIN</span><span class="sxs-lookup"><span data-stu-id="198fa-180">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="198fa-181">当您组织中的人不想记得的随机数; 使用静态标识符他们可以选择一定数量或使用一个容易记住。</span><span class="sxs-lookup"><span data-stu-id="198fa-181">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember.</span></span> <span data-ttu-id="198fa-182">当使用动态会议 Id 时，每个会议用户计划将获得分配唯一的会议 id。</span><span class="sxs-lookup"><span data-stu-id="198fa-182">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="198fa-183">如果您想要分配动态而非静态会议 Id，[使用音频会议动态 Id，您的组织中](using-audio-conferencing-dynamic-ids-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="198fa-183">If you want to assign dynamic rather than static conference IDs, [Using Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="198fa-184">虽然静态会议 ID 将自动创建并指派给用户，可能的时间当用户不想使用此一并想要将其设置为某个数字、 或您的用户忘记或丢失了他们的会议 id。</span><span class="sxs-lookup"><span data-stu-id="198fa-184">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="198fa-185">可以使用业务管理中心为 Skype 和 Windows PowerShell 来查看、 更改和重置其会议 id。</span><span class="sxs-lookup"><span data-stu-id="198fa-185">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
1. <span data-ttu-id="198fa-186">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="198fa-186">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="198fa-187">请转到**Office 365 管理中心** > **Skype 业务**并在左边的导航，请单击**音频会议**。</span><span class="sxs-lookup"><span data-stu-id="198fa-187">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="198fa-188">单击**用户**，然后选择您要重置 pin 码以进行用户。</span><span class="sxs-lookup"><span data-stu-id="198fa-188">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="198fa-189">在操作窗格中下**针**，单击**重置**。</span><span class="sxs-lookup"><span data-stu-id="198fa-189">In the Action pane, under **PIN**, click **Reset**.</span></span>
    
<span data-ttu-id="198fa-190">当他们正在启用音频会议或 PIN 重置时，用户将收到一封电子邮件与他们的 PIN。</span><span class="sxs-lookup"><span data-stu-id="198fa-190">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="198fa-191">但如果禁用了自动发送电子邮件、 PIN 重置电子邮件就不会发送，您将不得不手动发送给用户的 PIN。</span><span class="sxs-lookup"><span data-stu-id="198fa-191">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="198fa-192">PIN，才会显示一次后已被重置。</span><span class="sxs-lookup"><span data-stu-id="198fa-192">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="198fa-193">PIN 重置后显示之后，不不再会显示在用户属性;相反，\*\*\* 将显示。</span><span class="sxs-lookup"><span data-stu-id="198fa-193">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="198fa-194">请参阅[重置用户的音频会议 PIN](reset-the-audio-conferencing-pin-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="198fa-194">See [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin-for-a-user.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="198fa-195">使用音频会议信息的电子邮件发送给用户</span><span class="sxs-lookup"><span data-stu-id="198fa-195">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="198fa-196">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="198fa-196">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="198fa-197">请转到**Office 365 管理中心** > **Skype 业务**并在左边的导航，请单击**音频会议**。</span><span class="sxs-lookup"><span data-stu-id="198fa-197">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="198fa-198">单击**用户**，然后选择您要重置 pin 码以进行用户。</span><span class="sxs-lookup"><span data-stu-id="198fa-198">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="198fa-199">在操作窗格中，单击" **通过电子邮件发送会议信息**"。</span><span class="sxs-lookup"><span data-stu-id="198fa-199">In the Action pane, click **Send conference info via email**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="198fa-200">执行此操作时，音频会议针不是发送给用户。</span><span class="sxs-lookup"><span data-stu-id="198fa-200">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 
  
<span data-ttu-id="198fa-201">请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。</span><span class="sxs-lookup"><span data-stu-id="198fa-201">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
  
## <a name="setting-the-default-audio-conferencing-phone-number-for-meeting-organizers"></a><span data-ttu-id="198fa-202">会议组织者设置的默认音频会议电话号码</span><span class="sxs-lookup"><span data-stu-id="198fa-202">Setting the default audio conferencing phone number for meeting organizers</span></span>

 <span data-ttu-id="198fa-203">**对于会议组织者，如果您已经在音频会议启用用户设置的默认音频会议电话号码**</span><span class="sxs-lookup"><span data-stu-id="198fa-203">**To set the default audio conferencing phone number for meeting organizers when you are enabling a user for Audio Conferencing**</span></span>
  
1. <span data-ttu-id="198fa-204">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="198fa-204">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="198fa-205">请转到**Office 365 管理中心** > **业务的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="198fa-205">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="198fa-206">在左侧的导航中，转到**音频会议** > **用户**。</span><span class="sxs-lookup"><span data-stu-id="198fa-206">In the left navigation, go to **Audio conferencing** > **Users**.</span></span> <span data-ttu-id="198fa-207">选择您想要启用音频会议的用户。</span><span class="sxs-lookup"><span data-stu-id="198fa-207">Select the user that you want to enable for Audio Conferencing.</span></span>
    
4. <span data-ttu-id="198fa-208">在操作窗格中，在用户的属性中，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="198fa-208">In the Action pane, in the user's properties, click **Edit**.</span></span>
    
5. <span data-ttu-id="198fa-209">在**属性**页上，在**提供程序的名称**，使用下拉列表选择音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="198fa-209">On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.</span></span>
    
  - <span data-ttu-id="198fa-210">如果选择 Microsoft 作为音频会议提供商，您可以从列表中选择默认的音频会议电话号码。</span><span class="sxs-lookup"><span data-stu-id="198fa-210">If you select Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.</span></span>  
    
  - <span data-ttu-id="198fa-211">如果您选择第三方 ACP 作为音频会议提供商，您将需要手动输入的收费，如有必要，免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="198fa-211">If you select a third-party ACP as the audio conferencing provider, you will need to manually enter the Toll and if required, the Toll-free phone number.</span></span> <span data-ttu-id="198fa-212">这些电话号码将是默认的电话号码。</span><span class="sxs-lookup"><span data-stu-id="198fa-212">These phone numbers will be the default phone number.</span></span>
    
    <span data-ttu-id="198fa-213">用户的默认音频会议电话号码是他们安排会议时在会议邀请中显示数字。</span><span class="sxs-lookup"><span data-stu-id="198fa-213">The default audio conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span></span>
    
6. <span data-ttu-id="198fa-214">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="198fa-214">Click **Save**.</span></span> 
    
<span data-ttu-id="198fa-215">请参阅[设置数字包括在邀请电话](set-the-phone-numbers-included-on-invites.md)。</span><span class="sxs-lookup"><span data-stu-id="198fa-215">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
 <span data-ttu-id="198fa-216">**若要设置默认的音频会议电话号码启用用户输入音频会议后，会议组织者**</span><span class="sxs-lookup"><span data-stu-id="198fa-216">**To set the default audio conferencing phone number for meeting organizers after you have enabled a user for audio conferencing**</span></span>
  
1. <span data-ttu-id="198fa-217">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="198fa-217">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="198fa-218">请转到**Office 365 管理中心** > **业务的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="198fa-218">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="198fa-219">在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议** > **用户**，选择的用户所需，并在操作页中，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="198fa-219">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, select the user you want, and in the Action page, click **Edit**.</span></span>
    
4. <span data-ttu-id="198fa-220">在**属性**页上，在**提供程序的名称**，使用下拉列表选择音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="198fa-220">On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.</span></span>
    
  - <span data-ttu-id="198fa-221">如果用户使用 Microsoft 作为音频会议提供商，您可以从列表中选择默认的音频会议电话号码。</span><span class="sxs-lookup"><span data-stu-id="198fa-221">If the user uses Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.</span></span>  
    
  - <span data-ttu-id="198fa-222">如果用户使用第三方 ACP 作为音频会议提供商，您将需要手动输入的收费，如有必要，免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="198fa-222">If the user uses a third-party ACP as the audio conferencing provider, you will need to manually enter the Toll and if required, the Toll-free phone number.</span></span>
    
    <span data-ttu-id="198fa-223">用户的默认音频会议电话号码是他们安排会议时在会议邀请中显示数字。</span><span class="sxs-lookup"><span data-stu-id="198fa-223">The default audio conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span></span>
    
5. <span data-ttu-id="198fa-224">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="198fa-224">Click **Save**.</span></span> 
    
<span data-ttu-id="198fa-225">请参阅[设置数字包括在邀请电话](set-the-phone-numbers-included-on-invites.md)。</span><span class="sxs-lookup"><span data-stu-id="198fa-225">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
## <a name="setting-audio-conferencing-bridge-settings"></a><span data-ttu-id="198fa-226">设置音频会议桥</span><span class="sxs-lookup"><span data-stu-id="198fa-226">Setting audio conferencing bridge settings</span></span>

 <span data-ttu-id="198fa-227">**当调用方加入会议设置会议经验**</span><span class="sxs-lookup"><span data-stu-id="198fa-227">**Set the meeting experience when callers join a meeting**</span></span>
  
1. <span data-ttu-id="198fa-228">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="198fa-228">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="198fa-229">请转到**Office 365 管理中心** > **业务的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="198fa-229">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="198fa-230">在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议** > **Microsoft 网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="198fa-230">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="198fa-231">下**会议连接体验**，请选择下列操作：</span><span class="sxs-lookup"><span data-stu-id="198fa-231">Under **Meeting join experience**, select the following actions:</span></span>
    
  - <span data-ttu-id="198fa-232">**启用会议进入和退出通知以打开**默认情况下选择此选项。</span><span class="sxs-lookup"><span data-stu-id="198fa-232">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="198fa-233">如果清除此复选框，当有人进入或离开会议，将不会通知用户，默认情况下已加入会议。</span><span class="sxs-lookup"><span data-stu-id="198fa-233">If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="198fa-234">当用户加入会议的业务或 Microsoft 小组应用程序使用 Skype 和它们修改**公布当人进入或离开时**设置的 Skype 会议或 Microsoft 小组**选项**菜单中可以在逐个会议的基础上设置此会议。</span><span class="sxs-lookup"><span data-stu-id="198fa-234">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business or Microsoft Teams app and they modify the **Announce when people enter or leave** setting in the Skype Meeting or Microsoft Teams **Options** menu of the meeting.</span></span>
    
  - <span data-ttu-id="198fa-235">**提出调用方来记录他们的姓名之前加入会议**默认情况下选择此选项。</span><span class="sxs-lookup"><span data-stu-id="198fa-235">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="198fa-236">如果清除此复选框，将不要求调用方之前他们加入会议记录他们的姓名。</span><span class="sxs-lookup"><span data-stu-id="198fa-236">If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
5. <span data-ttu-id="198fa-237">完成更改后，单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="198fa-237">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="198fa-238">请参见[更改音频会议桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="198fa-238">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="198fa-239">**设置会议的针长度**</span><span class="sxs-lookup"><span data-stu-id="198fa-239">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="198fa-240">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="198fa-240">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="198fa-241">请转到**Office 365 管理中心** > **业务的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="198fa-241">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="198fa-242">在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议** > **Microsoft 网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="198fa-242">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="198fa-243">在**安全**下，输入 PIN**针长度**列表中，为所需的位数，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="198fa-243">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    <span data-ttu-id="198fa-244">PIN 必须介于 4 到 12 位。</span><span class="sxs-lookup"><span data-stu-id="198fa-244">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="198fa-245">默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="198fa-245">The default is 5.</span></span>
    
<span data-ttu-id="198fa-246">请参见[更改音频会议桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="198fa-246">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="198fa-247">**启用或禁用音频的用户发送电子邮件**</span><span class="sxs-lookup"><span data-stu-id="198fa-247">**Enable or disable email from being sent to audio users**</span></span>
  
1. <span data-ttu-id="198fa-248">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="198fa-248">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="198fa-249">请转到**Office 365 管理中心** > **Skype 业务**并在左边的导航，请单击**音频会议**。</span><span class="sxs-lookup"><span data-stu-id="198fa-249">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="198fa-250">在**Microsoft 桥设置**页上，选中或清除**自动发送电子邮件发送给用户，如果他们的音频会议设置更改**。</span><span class="sxs-lookup"><span data-stu-id="198fa-250">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="198fa-251">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="198fa-251">Click **Save**.</span></span>
    
    <span data-ttu-id="198fa-252">您还可以发送电子邮件给用户使用音频会议设置，转到该用户的音频会议属性并单击**将会议信息通过电子邮件发送**。</span><span class="sxs-lookup"><span data-stu-id="198fa-252">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>
    
    <span data-ttu-id="198fa-253">如果执行此操作，则将发送仅包括会议 ID 和会议电话号码的电子邮件，但不包括 PIN。</span><span class="sxs-lookup"><span data-stu-id="198fa-253">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>
    
    <span data-ttu-id="198fa-254">请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。</span><span class="sxs-lookup"><span data-stu-id="198fa-254">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
## <a name="see-and-set-the-primary-and-secondary-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="198fa-255">查看和设置音频会议桥的主要和次要语言</span><span class="sxs-lookup"><span data-stu-id="198fa-255">See and set the primary and secondary languages on an audio conferencing bridge</span></span>

1. <span data-ttu-id="198fa-256">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="198fa-256">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="198fa-257">请转到**Office 365 管理中心** > **业务的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="198fa-257">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="198fa-258">在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议**，然后单击**Microsoft 桥**。</span><span class="sxs-lookup"><span data-stu-id="198fa-258">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
4. <span data-ttu-id="198fa-259">从列表中选择一个电话号码，单击**设置语言**中的操作窗格中，然后在**设置语言**页中，单击使用的**主要语言**列表以查看受支持的语言的完整列表。</span><span class="sxs-lookup"><span data-stu-id="198fa-259">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>
    
    <span data-ttu-id="198fa-260">您还可以设置时选择 Microsoft 作为音频会议提供商支持的主要和辅助语言。</span><span class="sxs-lookup"><span data-stu-id="198fa-260">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="198fa-261">您的列表中选择的顺序是语言将显示为调用方的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="198fa-261">The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>
    
<span data-ttu-id="198fa-262">请参阅[设置音频会议自动助理语言](set-auto-attendant-languages-for-audio-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="198fa-262">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="198fa-263">请参阅音频会议拨入号码</span><span class="sxs-lookup"><span data-stu-id="198fa-263">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="198fa-264">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="198fa-264">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="198fa-265">请转到**Office 365 管理中心** > **业务的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="198fa-265">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="198fa-266">在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议** > **Microsoft 桥**。</span><span class="sxs-lookup"><span data-stu-id="198fa-266">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="198fa-267">在此处，您可以：</span><span class="sxs-lookup"><span data-stu-id="198fa-267">Here you can:</span></span>
    
  - <span data-ttu-id="198fa-268">查看 Office 365 集用于音频电话会议的电话号码。</span><span class="sxs-lookup"><span data-stu-id="198fa-268">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
  - <span data-ttu-id="198fa-269">查看位置和主要和次要的语言，将使用音频会议自动助理。</span><span class="sxs-lookup"><span data-stu-id="198fa-269">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>
    
  - <span data-ttu-id="198fa-270">选择已启用音频会议时为用户分配默认电话号码。</span><span class="sxs-lookup"><span data-stu-id="198fa-270">Select the default phone number that will be given to users when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="198fa-271">但是，如果更改了默认的音频会议桥的电话号码，不会更改现有用户的默认电话号码。</span><span class="sxs-lookup"><span data-stu-id="198fa-271">However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>
    
<span data-ttu-id="198fa-272">您可以转到**音频会议** > **用户**和用户的属性来更改默认值从数字在您的组织中可用的列表中选择新的号号用户的选择。</span><span class="sxs-lookup"><span data-stu-id="198fa-272">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>
  
<span data-ttu-id="198fa-273">请参阅[音频会议号码的列表，请参阅](see-a-list-of-audio-conferencing-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="198fa-273">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>
  
## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="198fa-274">查看启用的用户的列表</span><span class="sxs-lookup"><span data-stu-id="198fa-274">See a list of users that are enabled</span></span>

1. <span data-ttu-id="198fa-275">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="198fa-275">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="198fa-276">请转到**Office 365 管理中心** > **业务的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="198fa-276">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="198fa-277">在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议**>，然后**用户**。</span><span class="sxs-lookup"><span data-stu-id="198fa-277">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>
    
<span data-ttu-id="198fa-278">请参阅[请参阅启用了音频会议的用户列表](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="198fa-278">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="198fa-279">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="198fa-279">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="198fa-280">有几种可以在组织级别使用 Windows PowerShell 管理的设置。</span><span class="sxs-lookup"><span data-stu-id="198fa-280">There are several settings that you can manage at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="198fa-281">这样就轻松地将设置应用于所有用户。</span><span class="sxs-lookup"><span data-stu-id="198fa-281">This makes it easy to apply settings to all of your users.</span></span> 
    
<span data-ttu-id="198fa-282">要获得有关每个 cmdlet 的更多帮助，请参阅 [Skype for Business Online cmdlet](https://go.microsoft.com/fwlink/?LinkId=627324)。</span><span class="sxs-lookup"><span data-stu-id="198fa-282">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="198fa-283">以下是组织级设置：</span><span class="sxs-lookup"><span data-stu-id="198fa-283">Here are the organization-level settings:</span></span> 
> 
- <span data-ttu-id="198fa-284">**设置入口/出口通知**默认值为_$true_。</span><span class="sxs-lookup"><span data-stu-id="198fa-284">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false 
  ```

- <span data-ttu-id="198fa-285">**设置名称记录**默认值为_$true_。</span><span class="sxs-lookup"><span data-stu-id="198fa-285">**Setting name recording** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="198fa-286">**设置 PIN 长度**默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="198fa-286">**Setting the PIN length** The default is 5.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="198fa-287">**设置仅拨入会议从电话**默认值_$false_。</span><span class="sxs-lookup"><span data-stu-id="198fa-287">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="198fa-288">**设置是否将发送给用户的电子邮件**默认值为_$true_。</span><span class="sxs-lookup"><span data-stu-id="198fa-288">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="198fa-289">**设置是否将来自不同帐户的电子邮件发送**默认值为_$false_。</span><span class="sxs-lookup"><span data-stu-id="198fa-289">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="198fa-290">**设置发送给用户的电子邮件中的开始地址**默认值为_$null_。</span><span class="sxs-lookup"><span data-stu-id="198fa-290">**Setting the From address on email that is sent to users** The default is _$null_.</span></span> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="198fa-291">**设置电子邮件发送给用户显示名称**默认值为_$null_。</span><span class="sxs-lookup"><span data-stu-id="198fa-291">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="198fa-292">想要了解有关 Windows PowerShell 的详细信息</span><span class="sxs-lookup"><span data-stu-id="198fa-292">Want to know more about Windows PowerShell</span></span>   
- <span data-ttu-id="198fa-p124">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="198fa-p124">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="198fa-296">为什么需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="198fa-296">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="198fa-297">使用 Windows PowerShell 管理 Office 365 的最佳方法</span><span class="sxs-lookup"><span data-stu-id="198fa-297">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="198fa-298">Windows PowerShell 许多相比具有的优势在速度、 简易性和生产率仅使用 Office 365 管理中心，例如当您所更改的设置对于许多用户一次。</span><span class="sxs-lookup"><span data-stu-id="198fa-298">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="198fa-299">了解这些优势中的以下主题：</span><span class="sxs-lookup"><span data-stu-id="198fa-299">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="198fa-300">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="198fa-300">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="198fa-301">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="198fa-301">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="198fa-302">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="198fa-302">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    <span data-ttu-id="198fa-p126">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="198fa-p126">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="198fa-305">相关主题</span><span class="sxs-lookup"><span data-stu-id="198fa-305">Related topics</span></span>

[<span data-ttu-id="198fa-306">管理用户的音频会议设置</span><span class="sxs-lookup"><span data-stu-id="198fa-306">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)

[<span data-ttu-id="198fa-307">设置 Skype for Business 和 Microsoft Teams 音频会议</span><span class="sxs-lookup"><span data-stu-id="198fa-307">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)

