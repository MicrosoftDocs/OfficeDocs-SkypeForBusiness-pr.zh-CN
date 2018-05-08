---
title: 管理我的组织的音频会议设置
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
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
description: 'See steps to assign a dial-in conferencing license and conference ID to a user, set up a third party conferencing provider, and many other dial-in conferencing settings. '
ms.openlocfilehash: b2759e4ee1f8e8cac2f753eb5afecbf13642abb0
ms.sourcegitcommit: 2c084358844f02fbf7953f2ea49ed6d710cbf06f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2018
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a><span data-ttu-id="84cac-103">管理我的组织的音频会议设置</span><span class="sxs-lookup"><span data-stu-id="84cac-103">Manage the Audio Conferencing settings for my organization</span></span>

<span data-ttu-id="84cac-104">可能是您更轻松地查看所有业务和在一个位置的 Microsoft 团队 Skype 的音频会议设置。</span><span class="sxs-lookup"><span data-stu-id="84cac-104">It might be easier for you to see all of the audio conferencing settings for Skype for Business and Microsoft Teams in one place.</span></span> 
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="84cac-105">分配音频会议许可</span><span class="sxs-lookup"><span data-stu-id="84cac-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="84cac-106">无法分配使用**的业务管理中心 Skype**的许可证。</span><span class="sxs-lookup"><span data-stu-id="84cac-106">You can't assign licenses using the **Skype for Business admin center**.</span></span> <span data-ttu-id="84cac-107">您必须使用 Office 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="84cac-107">You must use the Office 365 admin center.</span></span> <span data-ttu-id="84cac-108">请参阅[业务和 Microsoft 团队许可证分配 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="84cac-108">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
 <span data-ttu-id="84cac-109">**分配用户许可证**</span><span class="sxs-lookup"><span data-stu-id="84cac-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="84cac-110">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="84cac-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="84cac-111">在**Office 365 管理中心**的左侧导航窗格中，转到**用户** > **活动用户**，然后从可用的用户列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="84cac-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="84cac-112">[!注释] 如果要同时向多达 20 个用户分配许可证，则可以使用" **选择视图**"下拉列表，然后选择其中一个选项或创建你自己的视图。</span><span class="sxs-lookup"><span data-stu-id="84cac-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="84cac-113">然后单击" **编辑**"，单击 **下一步**两次，然后选择许可证并单击" **提交**"。</span><span class="sxs-lookup"><span data-stu-id="84cac-113">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span> <span data-ttu-id="84cac-114">你也可以使用 Windows Powershell 向多个用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="84cac-114">You can also assign licenses to multiple users by using Windows Powershell.</span></span> <span data-ttu-id="84cac-115">有关说明和示例 PowerShell 脚本，请参阅[业务和 Microsoft 团队许可证分配 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="84cac-115">For instructions and sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
3. <span data-ttu-id="84cac-116">在"操作"窗格中的" **产品许可证**"下，单击" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="84cac-116">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="84cac-117">在**产品许可证**页上，打开**要进行音频会议**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="84cac-117">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="84cac-118">有关许可的详细信息，请参阅[业务和 Microsoft 团队授权加载项的 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="84cac-118">For more on licensing, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="84cac-119">分配许可证后，Microsoft 可能不作为最初在列表中的音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="84cac-119">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider.</span></span> <span data-ttu-id="84cac-120">如果发生这种情况，请退出 Office 365 管理中心或按 Ctrl+F5 刷新浏览器窗口。</span><span class="sxs-lookup"><span data-stu-id="84cac-120">If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="assign-a-conference-id-for-a-user"></a><span data-ttu-id="84cac-121">为用户分配会议 ID</span><span class="sxs-lookup"><span data-stu-id="84cac-121">Assign a conference ID for a user</span></span>

<span data-ttu-id="84cac-122">设置为使用 Microsoft 作为音频会议提供商的音频会议时，会议 ID 自动分配给用户。</span><span class="sxs-lookup"><span data-stu-id="84cac-122">A conference ID is automatically assigned to a user when they are set up for audio conferencing using Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="84cac-123">安排会议时，将会议邀请中发送的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="84cac-123">The conference ID is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="84cac-124">将获取每个用户安排的会议分配一个唯一的会议 id。</span><span class="sxs-lookup"><span data-stu-id="84cac-124">Each meeting that a user schedules will get assigned a unique conference ID.</span></span>
  
<span data-ttu-id="84cac-125">不能使用 Skype for Business 管理中心来向用户分配会议 ID，但你可以使用 Windows PowerShell cmdlet 来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="84cac-125">The Skype for Business admin center can't be used to assign a conference ID to a user, but you can use the Windows PowerShell cmdlet to do this.</span></span>
  
<span data-ttu-id="84cac-126">若要为用户设置会议 ID，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="84cac-126">To set the conference ID for a user, run:</span></span>
  
```
Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964 
```

> [!IMPORTANT]
> <span data-ttu-id="84cac-127">会议 ID 必须包含 7 位，并且不能在 Skype 业务管理中心或使用 Windows PowerShell 中进行更改。</span><span class="sxs-lookup"><span data-stu-id="84cac-127">A conference ID must contain 7 digits, and you can't change it in the Skype for Business admin center or by using Windows PowerShell.</span></span> 
  
<span data-ttu-id="84cac-128">请参阅 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) 以了解有关 cmdlet 的更多信息。</span><span class="sxs-lookup"><span data-stu-id="84cac-128">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="84cac-129">[!重要信息]  创建新会议 ID 后，呼叫者不能再使用旧会议 ID。</span><span class="sxs-lookup"><span data-stu-id="84cac-129">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="84cac-130">应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。</span><span class="sxs-lookup"><span data-stu-id="84cac-130">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="84cac-131">用户可以使用业务会议迁移工具的 Skype 更新其现有会议。</span><span class="sxs-lookup"><span data-stu-id="84cac-131">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="84cac-132">若要查看如何下载、 安装和运行 Skype 业务会议更新工具，请参阅： [Skype 商业和 Lync 会议更新工具](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)、[业务 online，会议迁移工具 （64 位） 的 Skype](http://go.microsoft.com/fwlink/?LinkID=626047)和[Skype 业务 online 会议迁移工具 （32 位）](https://www.microsoft.com/en-us/download/details.aspx?id=54079)。</span><span class="sxs-lookup"><span data-stu-id="84cac-132">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="84cac-133">请参阅[请参阅、 更改和重置会议 ID 分配给用户](see-change-and-reset-a-conference-id-assigned-to-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="84cac-133">See [See, change, and reset a conference ID assigned to a user](see-change-and-reset-a-conference-id-assigned-to-a-user.md).</span></span>
    
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="84cac-134">启用或禁用发送到音频会议用户的电子邮件</span><span class="sxs-lookup"><span data-stu-id="84cac-134">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="84cac-135">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="84cac-135">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="84cac-136">在左侧导航窗格中，转到**会议** > **会议桥**。</span><span class="sxs-lookup"><span data-stu-id="84cac-136">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="84cac-137">在**会议桥**页的顶部，单击**网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="84cac-137">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="84cac-138">在**桥设置**窗格中，启用或禁用**自动发送电子邮件发送给用户，如果其电话拨入式设置更改**。</span><span class="sxs-lookup"><span data-stu-id="84cac-138">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="84cac-139">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="84cac-139">Click **Save**.</span></span>

<span data-ttu-id="84cac-140">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="84cac-140">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="84cac-141">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="84cac-141">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="84cac-142">转到**Office 365 管理中心** > **for Business 的 Skype** ，在左侧导航窗格中，单击**音频会议**。</span><span class="sxs-lookup"><span data-stu-id="84cac-142">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="84cac-143">在**Microsoft 网桥的设置**页上，选中或清除**自动发送电子邮件发送给用户，如果其音频会议设置更改**。</span><span class="sxs-lookup"><span data-stu-id="84cac-143">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="84cac-144">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="84cac-144">Click **Save**.</span></span>
    
    <span data-ttu-id="84cac-145">您还可以发送电子邮件向用户使用音频会议设置转到用户的音频会议属性，单击**发送会议信息通过电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="84cac-145">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span> <span data-ttu-id="84cac-146">会议邀请，但不是 PIN 包含会议 ID 和默认音频会议电话号码。</span><span class="sxs-lookup"><span data-stu-id="84cac-146">The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>
    
    <span data-ttu-id="84cac-147">请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。</span><span class="sxs-lookup"><span data-stu-id="84cac-147">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
 <span data-ttu-id="84cac-148">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="84cac-148">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="84cac-149">你还可以使用 Windows PowerShell 并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="84cac-149">You can also use the Windows PowerShell and run:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="84cac-150">[设置 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285)可用于管理您的组织，包括电子邮件的其他设置。</span><span class="sxs-lookup"><span data-stu-id="84cac-150">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) to manage other settings for your organization, including email.</span></span>
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="84cac-151">更改发件人发送给用户的电子邮件中的联系人信息</span><span class="sxs-lookup"><span data-stu-id="84cac-151">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="84cac-152">您可以对自动发送给用户，包括的实际的电子邮件地址和发件人的联系人信息的显示名称的电子邮件进行更改。</span><span class="sxs-lookup"><span data-stu-id="84cac-152">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="84cac-153">默认情况下，电子邮件发件人是 Office 365 中，但您可以更改电子邮件地址和显示名称使用 Windows PowerShell 和[设置 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="84cac-153">By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span> <span data-ttu-id="84cac-154">若要更改向用户发送电子邮件的电子邮件地址，您必须：</span><span class="sxs-lookup"><span data-stu-id="84cac-154">To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="84cac-155">_SendEmailFromAddress_参数中输入的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="84cac-155">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="84cac-156">在  _SendEmailFromDisplayName_ 参数中输入电子邮件的显示名称。</span><span class="sxs-lookup"><span data-stu-id="84cac-156">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="84cac-157">_SendEmailOverride_参数设置为_True_。</span><span class="sxs-lookup"><span data-stu-id="84cac-157">Set the _SendEmailOverride_ parameter to _True_.</span></span>
    
<span data-ttu-id="84cac-158">你可以运行如下命令，更改发送给用户的电子邮件，例如电子邮件的发件人电子邮件地址，或者电子邮件的显示名称：</span><span class="sxs-lookup"><span data-stu-id="84cac-158">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="84cac-159">如果要更改电子邮件地址信息，你需要确保你的组织的入站电子邮件策略允许来自自定义电子邮件地址的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="84cac-159">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>
  
<span data-ttu-id="84cac-160">[设置 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet 可用于管理您的组织，包括电子邮件的其他设置。</span><span class="sxs-lookup"><span data-stu-id="84cac-160">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
<span data-ttu-id="84cac-161">请参阅[自动发送给其音频会议设置更改时的用户的电子邮件](emails-sent-to-users-when-their-settings-change.md)。</span><span class="sxs-lookup"><span data-stu-id="84cac-161">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="84cac-162">重置会议 ID</span><span class="sxs-lookup"><span data-stu-id="84cac-162">Reset the meeting conference ID</span></span>

<span data-ttu-id="84cac-163">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="84cac-163">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="84cac-164">在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。</span><span class="sxs-lookup"><span data-stu-id="84cac-164">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="84cac-165">在页面的顶部，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="84cac-165">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="84cac-166">在**音频会议**，下单击**重置会议 ID**。</span><span class="sxs-lookup"><span data-stu-id="84cac-166">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

4. <span data-ttu-id="84cac-167">在**重置的会议 ID？**窗口中，单击**重置**。</span><span class="sxs-lookup"><span data-stu-id="84cac-167">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="84cac-168">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span><span class="sxs-lookup"><span data-stu-id="84cac-168">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="84cac-169">It's enabled by default.</span><span class="sxs-lookup"><span data-stu-id="84cac-169">It's enabled by default.</span></span>

<span data-ttu-id="84cac-170">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="84cac-170">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>  

1. <span data-ttu-id="84cac-171">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="84cac-171">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="84cac-172">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="84cac-172">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="84cac-173">在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议**，并在**会议 ID**下的操作窗格中，单击**重置**。</span><span class="sxs-lookup"><span data-stu-id="84cac-173">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="84cac-174">在**重置的会议 ID？**窗口中，单击**是**。</span><span class="sxs-lookup"><span data-stu-id="84cac-174">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="84cac-175">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span><span class="sxs-lookup"><span data-stu-id="84cac-175">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="84cac-176">It's enabled by default.</span><span class="sxs-lookup"><span data-stu-id="84cac-176">It's enabled by default.</span></span>
    
    > [!IMPORTANT]
    >  <span data-ttu-id="84cac-177">[!重要信息] 创建新会议 ID 后，呼叫者不能再使用旧会议 ID。</span><span class="sxs-lookup"><span data-stu-id="84cac-177">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="84cac-178">应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。</span><span class="sxs-lookup"><span data-stu-id="84cac-178">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="84cac-179">用户可以使用业务会议迁移工具的 Skype 更新其现有会议。</span><span class="sxs-lookup"><span data-stu-id="84cac-179">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="84cac-180">若要查看如何下载、 安装和运行 Skype 业务会议更新工具，请参阅： [Skype 商业和 Lync 会议更新工具](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)、[业务 online，会议迁移工具 （64 位） 的 Skype](http://go.microsoft.com/fwlink/?LinkID=626047)和[Skype 业务 online 会议迁移工具 （32 位）](https://www.microsoft.com/en-us/download/details.aspx?id=54079)。</span><span class="sxs-lookup"><span data-stu-id="84cac-180">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="84cac-181">请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="84cac-181">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="84cac-182">重置会议组织者的 PIN</span><span class="sxs-lookup"><span data-stu-id="84cac-182">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="84cac-183">将获取每个用户安排的会议分配一个唯一的会议 id。</span><span class="sxs-lookup"><span data-stu-id="84cac-183">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="84cac-184">虽然会议 ID 将自动创建并分配给用户，有时可能时用户不是要使用此和您想要将其设置为一个特定号码，或您的用户不记得丢失其会议 id。</span><span class="sxs-lookup"><span data-stu-id="84cac-184">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="84cac-185">您可用于业务管理中心的 Skype 和 Windows PowerShell 查看、 更改和重置用户的会议 id。</span><span class="sxs-lookup"><span data-stu-id="84cac-185">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="84cac-186">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="84cac-186">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="84cac-187">在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。</span><span class="sxs-lookup"><span data-stu-id="84cac-187">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="84cac-188">在页面的顶部，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="84cac-188">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="84cac-189">在**音频会议**，下单击**重置 PIN**，，然后单击**重置**。</span><span class="sxs-lookup"><span data-stu-id="84cac-189">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
<span data-ttu-id="84cac-190">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="84cac-190">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 

1. <span data-ttu-id="84cac-191">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="84cac-191">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="84cac-192">转到**Office 365 管理中心** > **for Business 的 Skype** ，在左侧导航窗格中，单击**音频会议**。</span><span class="sxs-lookup"><span data-stu-id="84cac-192">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="84cac-193">单击**用户**，然后选择您要重置 PIN 的用户。</span><span class="sxs-lookup"><span data-stu-id="84cac-193">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="84cac-194">在操作窗格中，在**PIN**下单击**重置**。</span><span class="sxs-lookup"><span data-stu-id="84cac-194">In the Action pane, under **PIN**, click **Reset**.</span></span>
    
<span data-ttu-id="84cac-195">当他们正在启用音频会议或 PIN 重置时，用户将收到电子邮件与他们的 PIN。</span><span class="sxs-lookup"><span data-stu-id="84cac-195">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="84cac-196">但如果您已禁用自动发送电子邮件，将不会发送的 PIN 重置电子邮件和必须手动发送给用户的 PIN。</span><span class="sxs-lookup"><span data-stu-id="84cac-196">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="84cac-197">PIN 将仅在重置后显示一次。</span><span class="sxs-lookup"><span data-stu-id="84cac-197">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="84cac-198">正在重置之后显示后，不会再显示 PIN 用户属性;而是 \*\*\* 将显示。</span><span class="sxs-lookup"><span data-stu-id="84cac-198">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="84cac-199">请参阅[重置 PIN 的音频会议](reset-the-audio-conferencing-pin.md)。</span><span class="sxs-lookup"><span data-stu-id="84cac-199">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="84cac-200">向用户发送电子邮件与音频会议信息</span><span class="sxs-lookup"><span data-stu-id="84cac-200">Send an email with Audio Conferencing information to a user</span></span>

<span data-ttu-id="84cac-201">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="84cac-201">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="84cac-202">在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。</span><span class="sxs-lookup"><span data-stu-id="84cac-202">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="84cac-203">在页面的顶部，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="84cac-203">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="84cac-204">在**音频会议**，单击**发送电子邮件中的会议信息**。</span><span class="sxs-lookup"><span data-stu-id="84cac-204">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="84cac-205">当执行此操作时，音频会议 PIN 不发送给用户。</span><span class="sxs-lookup"><span data-stu-id="84cac-205">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 

<span data-ttu-id="84cac-206">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="84cac-206">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>  

1. <span data-ttu-id="84cac-207">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="84cac-207">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="84cac-208">转到**Office 365 管理中心** > **for Business 的 Skype** ，在左侧导航窗格中，单击**音频会议**。</span><span class="sxs-lookup"><span data-stu-id="84cac-208">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="84cac-209">单击**用户**，然后选择您要重置 PIN 的用户。</span><span class="sxs-lookup"><span data-stu-id="84cac-209">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="84cac-210">在操作窗格中，单击" **通过电子邮件发送会议信息**"。</span><span class="sxs-lookup"><span data-stu-id="84cac-210">In the Action pane, click **Send conference info via email**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="84cac-211">当执行此操作时，音频会议 PIN 不发送给用户。</span><span class="sxs-lookup"><span data-stu-id="84cac-211">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 
  
<span data-ttu-id="84cac-212">请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。</span><span class="sxs-lookup"><span data-stu-id="84cac-212">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
  
## <a name="setting-the-default-audio-conferencing-phone-number-for-meeting-organizers"></a><span data-ttu-id="84cac-213">为会议组织者设置的默认音频会议电话号码</span><span class="sxs-lookup"><span data-stu-id="84cac-213">Setting the default audio conferencing phone number for meeting organizers</span></span>

 <span data-ttu-id="84cac-214">**若要为会议组织者，您将为用户启用音频会议时设置默认音频会议电话号码**</span><span class="sxs-lookup"><span data-stu-id="84cac-214">**To set the default audio conferencing phone number for meeting organizers when you are enabling a user for Audio Conferencing**</span></span>
  
1. <span data-ttu-id="84cac-215">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="84cac-215">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="84cac-216">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="84cac-216">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="84cac-217">在左侧导航窗格中，转到**音频会议** > **用户**。</span><span class="sxs-lookup"><span data-stu-id="84cac-217">In the left navigation, go to **Audio conferencing** > **Users**.</span></span> <span data-ttu-id="84cac-218">选择您想要启用音频会议的用户。</span><span class="sxs-lookup"><span data-stu-id="84cac-218">Select the user that you want to enable for Audio Conferencing.</span></span>
    
4. <span data-ttu-id="84cac-219">在操作窗格中，在用户属性中，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="84cac-219">In the Action pane, in the user's properties, click **Edit**.</span></span>
    
5. <span data-ttu-id="84cac-220">在**属性**页上，在**提供程序名称**下使用下拉列表选择音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="84cac-220">On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.</span></span>
    
  - <span data-ttu-id="84cac-221">如果选择 Microsoft 作为音频会议提供商，您可以从列表中选择默认音频会议的电话号码。</span><span class="sxs-lookup"><span data-stu-id="84cac-221">If you select Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.</span></span>  
    
  - <span data-ttu-id="84cac-222">如果您选择第三方 ACP 作为音频会议提供商，您将需要手动输入收费电话和如果需要，免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="84cac-222">If you select a third-party ACP as the audio conferencing provider, you will need to manually enter the Toll and if required, the Toll-free phone number.</span></span> <span data-ttu-id="84cac-223">这些电话号码将作为默认电话号码。</span><span class="sxs-lookup"><span data-stu-id="84cac-223">These phone numbers will be the default phone number.</span></span>
    
    <span data-ttu-id="84cac-224">用户的默认音频会议电话号码是他们安排会议时，会议邀请显示的号码。</span><span class="sxs-lookup"><span data-stu-id="84cac-224">The default audio conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span></span>
    
6. <span data-ttu-id="84cac-225">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="84cac-225">Click **Save**.</span></span> 
    
<span data-ttu-id="84cac-226">请参阅[设置的电话号码包含在邀请](set-the-phone-numbers-included-on-invites.md)。</span><span class="sxs-lookup"><span data-stu-id="84cac-226">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
 <span data-ttu-id="84cac-227">**若要为启用音频会议用户后，会议组织者设置的默认音频会议电话号码**</span><span class="sxs-lookup"><span data-stu-id="84cac-227">**To set the default audio conferencing phone number for meeting organizers after you have enabled a user for audio conferencing**</span></span>
  
1. <span data-ttu-id="84cac-228">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="84cac-228">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="84cac-229">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="84cac-229">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="84cac-230">在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议** > **用户**，选择所需的用户，并在操作页上，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="84cac-230">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, select the user you want, and in the Action page, click **Edit**.</span></span>
    
4. <span data-ttu-id="84cac-231">在**属性**页上，在**提供程序名称**下使用下拉列表选择音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="84cac-231">On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.</span></span>
    
  - <span data-ttu-id="84cac-232">如果用户使用 Microsoft 为音频会议提供商，您可以从列表中选择默认音频会议的电话号码。</span><span class="sxs-lookup"><span data-stu-id="84cac-232">If the user uses Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.</span></span>  
    
  - <span data-ttu-id="84cac-233">如果用户使用第三方 ACP 作为音频会议提供商，您将需要手动输入收费电话和如果需要，免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="84cac-233">If the user uses a third-party ACP as the audio conferencing provider, you will need to manually enter the Toll and if required, the Toll-free phone number.</span></span>
    
    <span data-ttu-id="84cac-234">用户的默认音频会议电话号码是他们安排会议时，会议邀请显示的号码。</span><span class="sxs-lookup"><span data-stu-id="84cac-234">The default audio conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span></span>
    
5. <span data-ttu-id="84cac-235">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="84cac-235">Click **Save**.</span></span> 
    
<span data-ttu-id="84cac-236">请参阅[设置的电话号码包含在邀请](set-the-phone-numbers-included-on-invites.md)。</span><span class="sxs-lookup"><span data-stu-id="84cac-236">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="84cac-237">选择音频会议网桥的设置</span><span class="sxs-lookup"><span data-stu-id="84cac-237">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="84cac-238">**呼叫者加入会议时设置的会议体验**</span><span class="sxs-lookup"><span data-stu-id="84cac-238">**Set the meeting experience when callers join a meeting**</span></span>

 <span data-ttu-id="84cac-239">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="84cac-239">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="84cac-240">在左侧导航窗格中，转到**会议** > **会议桥**。</span><span class="sxs-lookup"><span data-stu-id="84cac-240">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="84cac-241">在**会议桥**页的顶部，单击**网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="84cac-241">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="84cac-242">在**桥设置**窗格中，启用或禁用**会议项和退出通知**。</span><span class="sxs-lookup"><span data-stu-id="84cac-242">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="84cac-243">默认情况下启用。</span><span class="sxs-lookup"><span data-stu-id="84cac-243">This is enabled by default.</span></span> <span data-ttu-id="84cac-244">如果您禁用此选项，某人进入或离开会议时，默认情况下已加入会议的用户不会将收到通知。</span><span class="sxs-lookup"><span data-stu-id="84cac-244">If you disable this option, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="84cac-245">在**项/退出通知类型**下选择**音**或**姓名或电话号码**。</span><span class="sxs-lookup"><span data-stu-id="84cac-245">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="84cac-246">如果您选择**姓名或电话号码**，可以选择启用或禁用**Ask 呼叫者在记录其姓名之前加入会议**。</span><span class="sxs-lookup"><span data-stu-id="84cac-246">If you choose **Names or phone numbers**, you can also choose to enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 

1. <span data-ttu-id="84cac-247">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="84cac-247">Click **Save**.</span></span>

<span data-ttu-id="84cac-248">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="84cac-248">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 
  
1. <span data-ttu-id="84cac-249">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="84cac-249">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="84cac-250">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="84cac-250">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="84cac-251">在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议** > **Microsoft 网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="84cac-251">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="84cac-252">在**会议加入体验**，下选择下列操作：</span><span class="sxs-lookup"><span data-stu-id="84cac-252">Under **Meeting join experience**, select the following actions:</span></span>
    
  - <span data-ttu-id="84cac-253">" **启用会议进入和退出通知**"此选项默认情况下选中。</span><span class="sxs-lookup"><span data-stu-id="84cac-253">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="84cac-254">如果清除此复选框，某人进入或离开会议时，默认情况下已加入会议的用户不会收到通知。</span><span class="sxs-lookup"><span data-stu-id="84cac-254">If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="84cac-255">用户加入会议的业务或 Microsoft 团队应用程序使用 Skype 和它们修改的 Skype 会议或 Microsoft 团队**选项**菜单中的**公告时人员进入或离开**设置时，可以逐个会议逐个设置此会议。</span><span class="sxs-lookup"><span data-stu-id="84cac-255">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business or Microsoft Teams app and they modify the **Announce when people enter or leave** setting in the Skype Meeting or Microsoft Teams **Options** menu of the meeting.</span></span>
    
  - <span data-ttu-id="84cac-256">" **要求呼叫者在加入会议之前录制其名称**"此选项默认情况下选中。</span><span class="sxs-lookup"><span data-stu-id="84cac-256">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="84cac-257">如果清除此复选框，呼叫者不需要记录其姓名，他们加入会议之前。</span><span class="sxs-lookup"><span data-stu-id="84cac-257">If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
5. <span data-ttu-id="84cac-258">完成更改后，单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="84cac-258">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="84cac-259">请参阅[更改现有音频会议桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="84cac-259">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="84cac-260">**设置会议的 PIN 长度**</span><span class="sxs-lookup"><span data-stu-id="84cac-260">**Set the PIN length for meetings**</span></span>

 <span data-ttu-id="84cac-261">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="84cac-261">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="84cac-262">在左侧导航窗格中，转到**会议** > **会议桥**。</span><span class="sxs-lookup"><span data-stu-id="84cac-262">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="84cac-263">在**会议桥**页的顶部，单击**网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="84cac-263">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="84cac-264">在**桥设置**窗格中，输入您希望在**PIN 长度**列表中，PIN 的位数，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="84cac-264">In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="84cac-265">PIN 必须在 4 到 12 位之间。</span><span class="sxs-lookup"><span data-stu-id="84cac-265">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="84cac-266">默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="84cac-266">The default is 5.</span></span>

<span data-ttu-id="84cac-267">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="84cac-267">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 
  
1. <span data-ttu-id="84cac-268">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="84cac-268">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="84cac-269">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="84cac-269">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="84cac-270">在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议** > **Microsoft 网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="84cac-270">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="84cac-271">在**安全**下输入您希望在**PIN 长度**列表中，PIN 的位数，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="84cac-271">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    <span data-ttu-id="84cac-272">PIN 必须在 4 到 12 位之间。</span><span class="sxs-lookup"><span data-stu-id="84cac-272">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="84cac-273">默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="84cac-273">The default is 5.</span></span>
    
<span data-ttu-id="84cac-274">请参阅[更改现有音频会议桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="84cac-274">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="84cac-275">**启用或禁用从发送给音频的用户的电子邮件**</span><span class="sxs-lookup"><span data-stu-id="84cac-275">**Enable or disable email from being sent to audio users**</span></span>

 <span data-ttu-id="84cac-276">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="84cac-276">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="84cac-277">在左侧导航窗格中，转到**会议** > **会议桥**。</span><span class="sxs-lookup"><span data-stu-id="84cac-277">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="84cac-278">在**会议桥**页的顶部，单击**网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="84cac-278">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="84cac-279">在**桥设置**窗格中，启用或禁用**自动发送电子邮件发送给用户，如果其音频会议设置更改**。</span><span class="sxs-lookup"><span data-stu-id="84cac-279">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="84cac-280">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="84cac-280">Click **Save**.</span></span> 
 
    <span data-ttu-id="84cac-281">您还可以发送电子邮件向用户音频会议设置后，转到用户的音频会议属性，单击**发送电子邮件中的会议信息**。</span><span class="sxs-lookup"><span data-stu-id="84cac-281">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info in email**.</span></span>
    
    <span data-ttu-id="84cac-282">如果执行此操作，则将发送仅包括会议 ID 和会议电话号码的电子邮件，但不包括 PIN。</span><span class="sxs-lookup"><span data-stu-id="84cac-282">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="84cac-283">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="84cac-283">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 
  
1. <span data-ttu-id="84cac-284">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="84cac-284">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="84cac-285">转到**Office 365 管理中心** > **for Business 的 Skype** ，在左侧导航窗格中，单击**音频会议**。</span><span class="sxs-lookup"><span data-stu-id="84cac-285">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="84cac-286">在**Microsoft 网桥的设置**页上，选中或清除**自动发送电子邮件发送给用户，如果其音频会议设置更改**。</span><span class="sxs-lookup"><span data-stu-id="84cac-286">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="84cac-287">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="84cac-287">Click **Save**.</span></span>
    
    <span data-ttu-id="84cac-288">您还可以发送电子邮件向用户音频会议设置后，转到用户的音频会议属性，单击**发送会议信息通过电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="84cac-288">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>
    
    <span data-ttu-id="84cac-289">如果执行此操作，则将发送仅包括会议 ID 和会议电话号码的电子邮件，但不包括 PIN。</span><span class="sxs-lookup"><span data-stu-id="84cac-289">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>
    
    <span data-ttu-id="84cac-290">请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。</span><span class="sxs-lookup"><span data-stu-id="84cac-290">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="84cac-291">请参阅和上一个音频会议网桥设置主 （默认值） 和辅助 （备用） 语言</span><span class="sxs-lookup"><span data-stu-id="84cac-291">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>

 <span data-ttu-id="84cac-292">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="84cac-292">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="84cac-293">在左侧导航窗格中，转到**会议** > **会议桥**。</span><span class="sxs-lookup"><span data-stu-id="84cac-293">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="84cac-294">从列表中选择一个电话号码，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="84cac-294">Select a phone number from the list and click **Edit**.</span></span>

3. <span data-ttu-id="84cac-295">选择**默认语言**和**（可选） 的备用语言**下所需的语言。</span><span class="sxs-lookup"><span data-stu-id="84cac-295">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>

<span data-ttu-id="84cac-296">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="84cac-296">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 

1. <span data-ttu-id="84cac-297">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="84cac-297">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="84cac-298">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="84cac-298">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="84cac-299">在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议**，然后单击**Microsoft 桥**。</span><span class="sxs-lookup"><span data-stu-id="84cac-299">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
4. <span data-ttu-id="84cac-300">从列表中选择一个电话号码，单击操作窗格中中的**设置语言**，然后在**设置语言**页上，单击使用**主要语言**列表，以查看受支持的语言的完整列表。</span><span class="sxs-lookup"><span data-stu-id="84cac-300">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>
    
    <span data-ttu-id="84cac-301">您还可以设置时选择 Microsoft 作为音频会议提供商支持的主要和辅助语言。</span><span class="sxs-lookup"><span data-stu-id="84cac-301">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="84cac-302">在列表中选择的顺序是相同的顺序在其中将向呼叫者显示语言。</span><span class="sxs-lookup"><span data-stu-id="84cac-302">The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>
    
<span data-ttu-id="84cac-303">请参阅[设置音频会议自动助理语言](set-auto-attendant-languages-for-audio-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="84cac-303">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>
  
## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png--see-audio-conferencing-dial-in-numbers"></a>![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png)  <span data-ttu-id="84cac-305">请参阅音频会议拨入号码</span><span class="sxs-lookup"><span data-stu-id="84cac-305">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="84cac-306">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="84cac-306">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="84cac-307">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="84cac-307">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="84cac-308">在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议** > **Microsoft 桥**。</span><span class="sxs-lookup"><span data-stu-id="84cac-308">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="84cac-309">此处可以：</span><span class="sxs-lookup"><span data-stu-id="84cac-309">Here you can:</span></span>
    
  - <span data-ttu-id="84cac-310">查看 Office 365 设置要用于音频会议的电话号码。</span><span class="sxs-lookup"><span data-stu-id="84cac-310">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
  - <span data-ttu-id="84cac-311">查看位置和主要和辅助语言，将使用的音频会议自动助理。</span><span class="sxs-lookup"><span data-stu-id="84cac-311">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>
    
  - <span data-ttu-id="84cac-312">选择它们启用音频会议时，将向用户提供的默认电话号码。</span><span class="sxs-lookup"><span data-stu-id="84cac-312">Select the default phone number that will be given to users when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="84cac-313">但是，如果音频会议桥的默认电话号码发生更改，都不会更改现有用户的默认电话号码。</span><span class="sxs-lookup"><span data-stu-id="84cac-313">However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>
    
<span data-ttu-id="84cac-314">您可以转到**音频会议** > **用户**和用户的属性更改默认的数字的用户通过从您的组织中提供的号码的列表中选择新号码的选择。</span><span class="sxs-lookup"><span data-stu-id="84cac-314">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>
  
<span data-ttu-id="84cac-315">请参阅[音频会议号码的列表，请参阅](see-a-list-of-audio-conferencing-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="84cac-315">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>
  
## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-see-a-list-of-users-that-are-enabled"></a>![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) <span data-ttu-id="84cac-317">查看启用的用户的列表</span><span class="sxs-lookup"><span data-stu-id="84cac-317">See a list of users that are enabled</span></span>

1. <span data-ttu-id="84cac-318">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="84cac-318">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="84cac-319">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="84cac-319">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="84cac-320">在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议**>，然后**用户**。</span><span class="sxs-lookup"><span data-stu-id="84cac-320">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>
    
<span data-ttu-id="84cac-321">请参阅[请参阅启用了音频会议的用户列表](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="84cac-321">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="84cac-322">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="84cac-322">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="84cac-323">有几种您可以使用 Windows PowerShell 的组织级别管理的设置。</span><span class="sxs-lookup"><span data-stu-id="84cac-323">There are several settings that you can manage at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="84cac-324">这便于将设置应用于所有用户。</span><span class="sxs-lookup"><span data-stu-id="84cac-324">This makes it easy to apply settings to all of your users.</span></span> 
    
<span data-ttu-id="84cac-325">要获得有关每个 cmdlet 的更多帮助，请参阅 [Skype for Business Online cmdlet](https://go.microsoft.com/fwlink/?LinkId=627324)。</span><span class="sxs-lookup"><span data-stu-id="84cac-325">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="84cac-326">下面是组织级别设置：</span><span class="sxs-lookup"><span data-stu-id="84cac-326">Here are the organization-level settings:</span></span> 
> 
- <span data-ttu-id="84cac-327">**设置条目/退出通知**默认值为 _$true_。</span><span class="sxs-lookup"><span data-stu-id="84cac-327">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false 
  ```

- <span data-ttu-id="84cac-328">**设置名称录制**默认值为 _$true_。</span><span class="sxs-lookup"><span data-stu-id="84cac-328">**Setting name recording** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="84cac-329">**设置 PIN 长度**默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="84cac-329">**Setting the PIN length** The default is 5.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="84cac-330">**设置仅电话拨入式会议从电话**默认 _$false_。</span><span class="sxs-lookup"><span data-stu-id="84cac-330">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="84cac-331">**设置是否向用户发送电子邮件**默认值为 _$true_。</span><span class="sxs-lookup"><span data-stu-id="84cac-331">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="84cac-332">**设置是否发送电子邮件从不同的帐户**默认值为 _$false_。</span><span class="sxs-lookup"><span data-stu-id="84cac-332">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="84cac-333">**设置在发送给用户的电子邮件发件人地址**默认值为 _$null_。</span><span class="sxs-lookup"><span data-stu-id="84cac-333">**Setting the From address on email that is sent to users** The default is _$null_.</span></span> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="84cac-334">**设置电子邮件发送给用户的显示名称**默认值为 _$null_。</span><span class="sxs-lookup"><span data-stu-id="84cac-334">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="84cac-335">想要了解有关 Windows PowerShell 的详细信息</span><span class="sxs-lookup"><span data-stu-id="84cac-335">Want to know more about Windows PowerShell</span></span>   
- <span data-ttu-id="84cac-p125">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="84cac-p125">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="84cac-339">为什么您需要使用 Office 365 PowerShell 中</span><span class="sxs-lookup"><span data-stu-id="84cac-339">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="84cac-340">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="84cac-340">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="84cac-341">Windows PowerShell 具有很多好处中快速、 简便起见和生产力通过只使用 Office 365 管理中心中的，如时要进行设置更改多个用户一次。</span><span class="sxs-lookup"><span data-stu-id="84cac-341">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="84cac-342">请在以下主题中了解这些优点：</span><span class="sxs-lookup"><span data-stu-id="84cac-342">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="84cac-343">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="84cac-343">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="84cac-344">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="84cac-344">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="84cac-345">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="84cac-345">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    <span data-ttu-id="84cac-p127">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="84cac-p127">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="84cac-348">相关主题</span><span class="sxs-lookup"><span data-stu-id="84cac-348">Related topics</span></span>

[<span data-ttu-id="84cac-349">管理用户的音频会议设置</span><span class="sxs-lookup"><span data-stu-id="84cac-349">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)


