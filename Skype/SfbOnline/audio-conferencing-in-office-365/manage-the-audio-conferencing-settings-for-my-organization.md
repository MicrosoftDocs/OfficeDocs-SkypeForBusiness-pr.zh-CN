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
description: '请参阅步骤将电话拨入式会议许可和会议 ID 分配给用户和许多其他电话拨入式会议设置。 '
ms.openlocfilehash: 7a5f82a827049f591d012af7f752e26ac4f9d87b
ms.sourcegitcommit: b93d1a0012aacb164d700db0143683cb6f276bf4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2018
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a><span data-ttu-id="c0374-103">管理我的组织的音频会议设置</span><span class="sxs-lookup"><span data-stu-id="c0374-103">Manage the Audio Conferencing settings for my organization</span></span>

<span data-ttu-id="c0374-104">可能是您更轻松地查看所有业务和在一个位置的 Microsoft 团队 Skype 的音频会议设置。</span><span class="sxs-lookup"><span data-stu-id="c0374-104">It might be easier for you to see all of the audio conferencing settings for Skype for Business and Microsoft Teams in one place.</span></span> 
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="c0374-105">分配音频会议许可</span><span class="sxs-lookup"><span data-stu-id="c0374-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="c0374-106">无法分配使用**的业务管理中心 Skype**的许可证。</span><span class="sxs-lookup"><span data-stu-id="c0374-106">You can't assign licenses using the **Skype for Business admin center**.</span></span> <span data-ttu-id="c0374-107">您必须使用 Office 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="c0374-107">You must use the Office 365 admin center.</span></span> <span data-ttu-id="c0374-108">请参阅[业务和 Microsoft 团队许可证分配 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="c0374-108">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
 <span data-ttu-id="c0374-109">**分配用户许可证**</span><span class="sxs-lookup"><span data-stu-id="c0374-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="c0374-110">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c0374-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c0374-111">在**Office 365 管理中心**的左侧导航窗格中，转到**用户** > **活动用户**，然后从可用的用户列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="c0374-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c0374-112">[!注释] 如果要同时向多达 20 个用户分配许可证，则可以使用" **选择视图**"下拉列表，然后选择其中一个选项或创建你自己的视图。</span><span class="sxs-lookup"><span data-stu-id="c0374-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="c0374-113">然后单击" **编辑**"，单击 **下一步**两次，然后选择许可证并单击" **提交**"。</span><span class="sxs-lookup"><span data-stu-id="c0374-113">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span> <span data-ttu-id="c0374-114">你也可以使用 Windows Powershell 向多个用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="c0374-114">You can also assign licenses to multiple users by using Windows Powershell.</span></span> <span data-ttu-id="c0374-115">有关说明和示例 PowerShell 脚本，请参阅[业务和 Microsoft 团队许可证分配 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="c0374-115">For instructions and sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
3. <span data-ttu-id="c0374-116">在"操作"窗格中的" **产品许可证**"下，单击" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="c0374-116">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="c0374-117">在**产品许可证**页上，打开**要进行音频会议**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="c0374-117">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="c0374-118">有关许可的详细信息，请参阅[业务和 Microsoft 团队授权加载项的 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="c0374-118">For more on licensing, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="c0374-119">分配许可证后，Microsoft 可能不作为最初在列表中的音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="c0374-119">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider.</span></span> <span data-ttu-id="c0374-120">如果发生这种情况，请退出 Office 365 管理中心或按 Ctrl+F5 刷新浏览器窗口。</span><span class="sxs-lookup"><span data-stu-id="c0374-120">If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="c0374-121">启用或禁用发送到音频会议用户的电子邮件</span><span class="sxs-lookup"><span data-stu-id="c0374-121">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="c0374-122">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="c0374-122">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="c0374-123">在左侧导航窗格中，转到**会议** > **会议桥**。</span><span class="sxs-lookup"><span data-stu-id="c0374-123">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="c0374-124">在**会议桥**页的顶部，单击**网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="c0374-124">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="c0374-125">在**桥设置**窗格中，启用或禁用**自动发送电子邮件发送给用户，如果其电话拨入式设置更改**。</span><span class="sxs-lookup"><span data-stu-id="c0374-125">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="c0374-126">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="c0374-126">Click **Save**.</span></span>

<span data-ttu-id="c0374-127">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="c0374-127">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="c0374-128">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c0374-128">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c0374-129">转到**Office 365 管理中心** > **for Business 的 Skype** ，在左侧导航窗格中，单击**音频会议**。</span><span class="sxs-lookup"><span data-stu-id="c0374-129">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="c0374-130">在**Microsoft 网桥的设置**页上，选中或清除**自动发送电子邮件发送给用户，如果其音频会议设置更改**。</span><span class="sxs-lookup"><span data-stu-id="c0374-130">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="c0374-131">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="c0374-131">Click **Save**.</span></span>
    
    <span data-ttu-id="c0374-132">您还可以发送电子邮件向用户使用音频会议设置转到用户的音频会议属性，单击**发送会议信息通过电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="c0374-132">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span> <span data-ttu-id="c0374-133">会议邀请，但不是 PIN 包含会议 ID 和默认音频会议电话号码。</span><span class="sxs-lookup"><span data-stu-id="c0374-133">The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>
    
    <span data-ttu-id="c0374-134">请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。</span><span class="sxs-lookup"><span data-stu-id="c0374-134">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
 <span data-ttu-id="c0374-135">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c0374-135">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="c0374-136">你还可以使用 Windows PowerShell 并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c0374-136">You can also use the Windows PowerShell and run:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="c0374-137">[设置 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285)可用于管理您的组织，包括电子邮件的其他设置。</span><span class="sxs-lookup"><span data-stu-id="c0374-137">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) to manage other settings for your organization, including email.</span></span>
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="c0374-138">更改发件人发送给用户的电子邮件中的联系人信息</span><span class="sxs-lookup"><span data-stu-id="c0374-138">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="c0374-139">您可以对自动发送给用户，包括的实际的电子邮件地址和发件人的联系人信息的显示名称的电子邮件进行更改。</span><span class="sxs-lookup"><span data-stu-id="c0374-139">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="c0374-140">默认情况下，电子邮件发件人是 Office 365 中，但您可以更改电子邮件地址和显示名称使用 Windows PowerShell 和[设置 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c0374-140">By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span> <span data-ttu-id="c0374-141">若要更改向用户发送电子邮件的电子邮件地址，您必须：</span><span class="sxs-lookup"><span data-stu-id="c0374-141">To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="c0374-142">_SendEmailFromAddress_参数中输入的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="c0374-142">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="c0374-143">在  _SendEmailFromDisplayName_ 参数中输入电子邮件的显示名称。</span><span class="sxs-lookup"><span data-stu-id="c0374-143">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="c0374-144">_SendEmailOverride_参数设置为_True_。</span><span class="sxs-lookup"><span data-stu-id="c0374-144">Set the _SendEmailOverride_ parameter to _True_.</span></span>
    
<span data-ttu-id="c0374-145">你可以运行如下命令，更改发送给用户的电子邮件，例如电子邮件的发件人电子邮件地址，或者电子邮件的显示名称：</span><span class="sxs-lookup"><span data-stu-id="c0374-145">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="c0374-146">如果要更改电子邮件地址信息，你需要确保你的组织的入站电子邮件策略允许来自自定义电子邮件地址的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="c0374-146">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>
  
<span data-ttu-id="c0374-147">[设置 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet 可用于管理您的组织，包括电子邮件的其他设置。</span><span class="sxs-lookup"><span data-stu-id="c0374-147">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
<span data-ttu-id="c0374-148">请参阅[自动发送给其音频会议设置更改时的用户的电子邮件](emails-sent-to-users-when-their-settings-change.md)。</span><span class="sxs-lookup"><span data-stu-id="c0374-148">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="c0374-149">重置会议 ID</span><span class="sxs-lookup"><span data-stu-id="c0374-149">Reset the meeting conference ID</span></span>

<span data-ttu-id="c0374-150">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="c0374-150">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="c0374-151">在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。</span><span class="sxs-lookup"><span data-stu-id="c0374-151">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="c0374-152">在页面的顶部，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="c0374-152">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="c0374-153">在**音频会议**，下单击**重置会议 ID**。</span><span class="sxs-lookup"><span data-stu-id="c0374-153">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

4. <span data-ttu-id="c0374-154">在**重置的会议 ID？**窗口中，单击**重置**。</span><span class="sxs-lookup"><span data-stu-id="c0374-154">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="c0374-155">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span><span class="sxs-lookup"><span data-stu-id="c0374-155">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="c0374-156">It's enabled by default.</span><span class="sxs-lookup"><span data-stu-id="c0374-156">It's enabled by default.</span></span>

<span data-ttu-id="c0374-157">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="c0374-157">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>  

1. <span data-ttu-id="c0374-158">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c0374-158">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c0374-159">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="c0374-159">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="c0374-160">在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议**，并在**会议 ID**下的操作窗格中，单击**重置**。</span><span class="sxs-lookup"><span data-stu-id="c0374-160">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="c0374-161">在**重置的会议 ID？**窗口中，单击**是**。</span><span class="sxs-lookup"><span data-stu-id="c0374-161">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="c0374-162">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span><span class="sxs-lookup"><span data-stu-id="c0374-162">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="c0374-163">It's enabled by default.</span><span class="sxs-lookup"><span data-stu-id="c0374-163">It's enabled by default.</span></span>
    
    > [!IMPORTANT]
    >  <span data-ttu-id="c0374-164">[!重要信息] 创建新会议 ID 后，呼叫者不能再使用旧会议 ID。</span><span class="sxs-lookup"><span data-stu-id="c0374-164">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="c0374-165">应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。</span><span class="sxs-lookup"><span data-stu-id="c0374-165">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="c0374-166">用户可以使用业务会议迁移工具的 Skype 更新其现有会议。</span><span class="sxs-lookup"><span data-stu-id="c0374-166">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="c0374-167">若要查看如何下载、 安装和运行 Skype 业务会议更新工具，请参阅： [Skype 商业和 Lync 会议更新工具](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)、[业务 online，会议迁移工具 （64 位） 的 Skype](http://go.microsoft.com/fwlink/?LinkID=626047)和[Skype 业务 online 会议迁移工具 （32 位）](https://www.microsoft.com/en-us/download/details.aspx?id=54079)。</span><span class="sxs-lookup"><span data-stu-id="c0374-167">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="c0374-168">请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="c0374-168">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="c0374-169">重置会议组织者的 PIN</span><span class="sxs-lookup"><span data-stu-id="c0374-169">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="c0374-170">将获取每个用户安排的会议分配一个唯一的会议 id。</span><span class="sxs-lookup"><span data-stu-id="c0374-170">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="c0374-171">虽然会议 ID 将自动创建并分配给用户，有时可能时用户不是要使用此和您想要将其设置为一个特定号码，或您的用户不记得丢失其会议 id。</span><span class="sxs-lookup"><span data-stu-id="c0374-171">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="c0374-172">您可用于业务管理中心的 Skype 和 Windows PowerShell 查看、 更改和重置用户的会议 id。</span><span class="sxs-lookup"><span data-stu-id="c0374-172">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="c0374-173">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="c0374-173">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="c0374-174">在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。</span><span class="sxs-lookup"><span data-stu-id="c0374-174">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="c0374-175">在页面的顶部，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="c0374-175">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="c0374-176">在**音频会议**，下单击**重置 PIN**，，然后单击**重置**。</span><span class="sxs-lookup"><span data-stu-id="c0374-176">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
<span data-ttu-id="c0374-177">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="c0374-177">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 

1. <span data-ttu-id="c0374-178">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c0374-178">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c0374-179">转到**Office 365 管理中心** > **for Business 的 Skype** ，在左侧导航窗格中，单击**音频会议**。</span><span class="sxs-lookup"><span data-stu-id="c0374-179">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="c0374-180">单击**用户**，然后选择您要重置 PIN 的用户。</span><span class="sxs-lookup"><span data-stu-id="c0374-180">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="c0374-181">在操作窗格中，在**PIN**下单击**重置**。</span><span class="sxs-lookup"><span data-stu-id="c0374-181">In the Action pane, under **PIN**, click **Reset**.</span></span>
    
<span data-ttu-id="c0374-182">当他们正在启用音频会议或 PIN 重置时，用户将收到电子邮件与他们的 PIN。</span><span class="sxs-lookup"><span data-stu-id="c0374-182">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="c0374-183">但如果您已禁用自动发送电子邮件，将不会发送的 PIN 重置电子邮件和必须手动发送给用户的 PIN。</span><span class="sxs-lookup"><span data-stu-id="c0374-183">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="c0374-184">PIN 将仅在重置后显示一次。</span><span class="sxs-lookup"><span data-stu-id="c0374-184">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="c0374-185">正在重置之后显示后，不会再显示 PIN 用户属性;而是 \*\*\* 将显示。</span><span class="sxs-lookup"><span data-stu-id="c0374-185">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="c0374-186">请参阅[重置 PIN 的音频会议](reset-the-audio-conferencing-pin.md)。</span><span class="sxs-lookup"><span data-stu-id="c0374-186">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="c0374-187">向用户发送电子邮件与音频会议信息</span><span class="sxs-lookup"><span data-stu-id="c0374-187">Send an email with Audio Conferencing information to a user</span></span>

<span data-ttu-id="c0374-188">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="c0374-188">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="c0374-189">在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。</span><span class="sxs-lookup"><span data-stu-id="c0374-189">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="c0374-190">在页面的顶部，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="c0374-190">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="c0374-191">在**音频会议**，单击**发送电子邮件中的会议信息**。</span><span class="sxs-lookup"><span data-stu-id="c0374-191">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="c0374-192">当执行此操作时，音频会议 PIN 不发送给用户。</span><span class="sxs-lookup"><span data-stu-id="c0374-192">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 

<span data-ttu-id="c0374-193">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="c0374-193">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>  

1. <span data-ttu-id="c0374-194">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c0374-194">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c0374-195">转到**Office 365 管理中心** > **for Business 的 Skype** ，在左侧导航窗格中，单击**音频会议**。</span><span class="sxs-lookup"><span data-stu-id="c0374-195">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="c0374-196">单击**用户**，然后选择您要重置 PIN 的用户。</span><span class="sxs-lookup"><span data-stu-id="c0374-196">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="c0374-197">在操作窗格中，单击" **通过电子邮件发送会议信息**"。</span><span class="sxs-lookup"><span data-stu-id="c0374-197">In the Action pane, click **Send conference info via email**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c0374-198">当执行此操作时，音频会议 PIN 不发送给用户。</span><span class="sxs-lookup"><span data-stu-id="c0374-198">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 
  
<span data-ttu-id="c0374-199">请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。</span><span class="sxs-lookup"><span data-stu-id="c0374-199">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
  
## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="c0374-200">设置的电话号码包含在邀请</span><span class="sxs-lookup"><span data-stu-id="c0374-200">Setting the phone numbers included on invites</span></span>

<span data-ttu-id="c0374-201">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="c0374-201">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="c0374-202">在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。</span><span class="sxs-lookup"><span data-stu-id="c0374-202">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="c0374-203">**音频会议**，旁边单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="c0374-203">Next to **Audio Conferencing**, click **Edit**.</span></span>
 
3. <span data-ttu-id="c0374-204">在**音频会议**窗格中，您可以设置**收费电话号码**，如果允许，**免费电话号码**。</span><span class="sxs-lookup"><span data-stu-id="c0374-204">In the **Audio Conferencing** pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

4. <span data-ttu-id="c0374-205">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="c0374-205">Click **Save**.</span></span>

<span data-ttu-id="c0374-206">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="c0374-206">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>  
  
1. <span data-ttu-id="c0374-207">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c0374-207">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c0374-208">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="c0374-208">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="c0374-209">在左侧导航窗格中，转到**音频会议** > **用户**。</span><span class="sxs-lookup"><span data-stu-id="c0374-209">In the left navigation, go to **Audio conferencing** > **Users**.</span></span> <span data-ttu-id="c0374-210">选择您想要启用音频会议的用户。</span><span class="sxs-lookup"><span data-stu-id="c0374-210">Select the user that you want to enable for Audio Conferencing.</span></span>
    
4. <span data-ttu-id="c0374-211">在操作窗格中，您可以设置**收费电话号码**，如果允许，**免费电话号码**。</span><span class="sxs-lookup"><span data-stu-id="c0374-211">In the Action pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

5. <span data-ttu-id="c0374-212">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="c0374-212">Click **Save**.</span></span>
    
<span data-ttu-id="c0374-213">请参阅[设置的电话号码包含在邀请](set-the-phone-numbers-included-on-invites.md)。</span><span class="sxs-lookup"><span data-stu-id="c0374-213">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
  
## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="c0374-214">选择音频会议网桥的设置</span><span class="sxs-lookup"><span data-stu-id="c0374-214">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="c0374-215">**呼叫者加入会议时设置的会议体验**</span><span class="sxs-lookup"><span data-stu-id="c0374-215">**Set the meeting experience when callers join a meeting**</span></span>

 <span data-ttu-id="c0374-216">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="c0374-216">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="c0374-217">在左侧导航窗格中，转到**会议** > **会议桥**。</span><span class="sxs-lookup"><span data-stu-id="c0374-217">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="c0374-218">在**会议桥**页的顶部，单击**网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="c0374-218">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="c0374-219">在**桥设置**窗格中，启用或禁用**会议项和退出通知**。</span><span class="sxs-lookup"><span data-stu-id="c0374-219">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="c0374-220">默认情况下启用。</span><span class="sxs-lookup"><span data-stu-id="c0374-220">This is enabled by default.</span></span> <span data-ttu-id="c0374-221">如果您禁用此选项，某人进入或离开会议时，默认情况下已加入会议的用户不会将收到通知。</span><span class="sxs-lookup"><span data-stu-id="c0374-221">If you disable this option, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="c0374-222">在**项/退出通知类型**下选择**音**或**姓名或电话号码**。</span><span class="sxs-lookup"><span data-stu-id="c0374-222">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="c0374-223">如果您选择**姓名或电话号码**，可以选择启用或禁用**Ask 呼叫者在记录其姓名之前加入会议**。</span><span class="sxs-lookup"><span data-stu-id="c0374-223">If you choose **Names or phone numbers**, you can also choose to enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 

1. <span data-ttu-id="c0374-224">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="c0374-224">Click **Save**.</span></span>

<span data-ttu-id="c0374-225">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="c0374-225">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 
  
1. <span data-ttu-id="c0374-226">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c0374-226">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c0374-227">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="c0374-227">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="c0374-228">在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议** > **Microsoft 网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="c0374-228">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="c0374-229">在**会议加入体验**，下选择下列操作：</span><span class="sxs-lookup"><span data-stu-id="c0374-229">Under **Meeting join experience**, select the following actions:</span></span>
    
  - <span data-ttu-id="c0374-230">" **启用会议进入和退出通知**"此选项默认情况下选中。</span><span class="sxs-lookup"><span data-stu-id="c0374-230">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="c0374-231">如果清除此复选框，某人进入或离开会议时，默认情况下已加入会议的用户不会收到通知。</span><span class="sxs-lookup"><span data-stu-id="c0374-231">If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="c0374-232">用户加入会议的业务或 Microsoft 团队应用程序使用 Skype 和它们修改的 Skype 会议或 Microsoft 团队**选项**菜单中的**公告时人员进入或离开**设置时，可以逐个会议逐个设置此会议。</span><span class="sxs-lookup"><span data-stu-id="c0374-232">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business or Microsoft Teams app and they modify the **Announce when people enter or leave** setting in the Skype Meeting or Microsoft Teams **Options** menu of the meeting.</span></span>
    
  - <span data-ttu-id="c0374-233">" **要求呼叫者在加入会议之前录制其名称**"此选项默认情况下选中。</span><span class="sxs-lookup"><span data-stu-id="c0374-233">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="c0374-234">如果清除此复选框，呼叫者不需要记录其姓名，他们加入会议之前。</span><span class="sxs-lookup"><span data-stu-id="c0374-234">If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
5. <span data-ttu-id="c0374-235">完成更改后，单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="c0374-235">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="c0374-236">请参阅[更改现有音频会议桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="c0374-236">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="c0374-237">**设置会议的 PIN 长度**</span><span class="sxs-lookup"><span data-stu-id="c0374-237">**Set the PIN length for meetings**</span></span>

 <span data-ttu-id="c0374-238">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="c0374-238">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="c0374-239">在左侧导航窗格中，转到**会议** > **会议桥**。</span><span class="sxs-lookup"><span data-stu-id="c0374-239">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="c0374-240">在**会议桥**页的顶部，单击**网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="c0374-240">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="c0374-241">在**桥设置**窗格中，输入您希望在**PIN 长度**列表中，PIN 的位数，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="c0374-241">In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="c0374-242">PIN 必须在 4 到 12 位之间。</span><span class="sxs-lookup"><span data-stu-id="c0374-242">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="c0374-243">默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="c0374-243">The default is 5.</span></span>

<span data-ttu-id="c0374-244">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="c0374-244">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 
  
1. <span data-ttu-id="c0374-245">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c0374-245">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c0374-246">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="c0374-246">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="c0374-247">在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议** > **Microsoft 网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="c0374-247">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="c0374-248">在**安全**下输入您希望在**PIN 长度**列表中，PIN 的位数，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="c0374-248">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    <span data-ttu-id="c0374-249">PIN 必须在 4 到 12 位之间。</span><span class="sxs-lookup"><span data-stu-id="c0374-249">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="c0374-250">默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="c0374-250">The default is 5.</span></span>
    
<span data-ttu-id="c0374-251">请参阅[更改现有音频会议桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="c0374-251">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="c0374-252">**启用或禁用从发送给音频的用户的电子邮件**</span><span class="sxs-lookup"><span data-stu-id="c0374-252">**Enable or disable email from being sent to audio users**</span></span>

 <span data-ttu-id="c0374-253">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="c0374-253">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="c0374-254">在左侧导航窗格中，转到**会议** > **会议桥**。</span><span class="sxs-lookup"><span data-stu-id="c0374-254">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="c0374-255">在**会议桥**页的顶部，单击**网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="c0374-255">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="c0374-256">在**桥设置**窗格中，启用或禁用**自动发送电子邮件发送给用户，如果其音频会议设置更改**。</span><span class="sxs-lookup"><span data-stu-id="c0374-256">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="c0374-257">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="c0374-257">Click **Save**.</span></span> 
 
    <span data-ttu-id="c0374-258">您还可以发送电子邮件向用户音频会议设置后，转到用户的音频会议属性，单击**发送电子邮件中的会议信息**。</span><span class="sxs-lookup"><span data-stu-id="c0374-258">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info in email**.</span></span>
    
    <span data-ttu-id="c0374-259">如果执行此操作，则将发送仅包括会议 ID 和会议电话号码的电子邮件，但不包括 PIN。</span><span class="sxs-lookup"><span data-stu-id="c0374-259">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="c0374-260">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="c0374-260">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 
  
1. <span data-ttu-id="c0374-261">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c0374-261">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c0374-262">转到**Office 365 管理中心** > **for Business 的 Skype** ，在左侧导航窗格中，单击**音频会议**。</span><span class="sxs-lookup"><span data-stu-id="c0374-262">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="c0374-263">在**Microsoft 网桥的设置**页上，选中或清除**自动发送电子邮件发送给用户，如果其音频会议设置更改**。</span><span class="sxs-lookup"><span data-stu-id="c0374-263">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="c0374-264">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="c0374-264">Click **Save**.</span></span>
    
    <span data-ttu-id="c0374-265">您还可以发送电子邮件向用户音频会议设置后，转到用户的音频会议属性，单击**发送会议信息通过电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="c0374-265">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>
    
    <span data-ttu-id="c0374-266">如果执行此操作，则将发送仅包括会议 ID 和会议电话号码的电子邮件，但不包括 PIN。</span><span class="sxs-lookup"><span data-stu-id="c0374-266">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>
    
    <span data-ttu-id="c0374-267">请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。</span><span class="sxs-lookup"><span data-stu-id="c0374-267">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="c0374-268">请参阅和上一个音频会议网桥设置主 （默认值） 和辅助 （备用） 语言</span><span class="sxs-lookup"><span data-stu-id="c0374-268">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>

 <span data-ttu-id="c0374-269">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="c0374-269">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="c0374-270">在左侧导航窗格中，转到**会议** > **会议桥**。</span><span class="sxs-lookup"><span data-stu-id="c0374-270">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="c0374-271">从列表中选择一个电话号码，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="c0374-271">Select a phone number from the list and click **Edit**.</span></span>

3. <span data-ttu-id="c0374-272">选择**默认语言**和**（可选） 的备用语言**下所需的语言。</span><span class="sxs-lookup"><span data-stu-id="c0374-272">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>

<span data-ttu-id="c0374-273">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="c0374-273">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 

1. <span data-ttu-id="c0374-274">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c0374-274">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c0374-275">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="c0374-275">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="c0374-276">在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议**，然后单击**Microsoft 桥**。</span><span class="sxs-lookup"><span data-stu-id="c0374-276">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
4. <span data-ttu-id="c0374-277">从列表中选择一个电话号码，单击操作窗格中中的**设置语言**，然后在**设置语言**页上，单击使用**主要语言**列表，以查看受支持的语言的完整列表。</span><span class="sxs-lookup"><span data-stu-id="c0374-277">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>
    
    <span data-ttu-id="c0374-278">您还可以设置时选择 Microsoft 作为音频会议提供商支持的主要和辅助语言。</span><span class="sxs-lookup"><span data-stu-id="c0374-278">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="c0374-279">在列表中选择的顺序是相同的顺序在其中将向呼叫者显示语言。</span><span class="sxs-lookup"><span data-stu-id="c0374-279">The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>
    
<span data-ttu-id="c0374-280">请参阅[设置音频会议自动助理语言](set-auto-attendant-languages-for-audio-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="c0374-280">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="c0374-281">请参阅音频会议拨入号码</span><span class="sxs-lookup"><span data-stu-id="c0374-281">See audio conferencing dial-in numbers</span></span>

<span data-ttu-id="c0374-282">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="c0374-282">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="c0374-283">在左侧导航窗格中，转到**会议** > **会议桥**。</span><span class="sxs-lookup"><span data-stu-id="c0374-283">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="c0374-284">从列表中选择一个电话号码，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="c0374-284">Select a phone number from the list and click **Edit**.</span></span> <span data-ttu-id="c0374-285">此处可以：</span><span class="sxs-lookup"><span data-stu-id="c0374-285">Here you can:</span></span>
    
  - <span data-ttu-id="c0374-286">查看 Office 365 设置要用于音频会议的电话号码。</span><span class="sxs-lookup"><span data-stu-id="c0374-286">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
  - <span data-ttu-id="c0374-287">查看位置，和主要语言，将使用的音频会议自动助理。</span><span class="sxs-lookup"><span data-stu-id="c0374-287">View the location, and the primary language, that will be used by the Audio Conferencing auto attendant.</span></span>


<span data-ttu-id="c0374-288">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="c0374-288">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>  

1. <span data-ttu-id="c0374-289">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c0374-289">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c0374-290">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="c0374-290">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="c0374-291">在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议** > **Microsoft 桥**。</span><span class="sxs-lookup"><span data-stu-id="c0374-291">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="c0374-292">此处可以：</span><span class="sxs-lookup"><span data-stu-id="c0374-292">Here you can:</span></span>
    
  - <span data-ttu-id="c0374-293">查看 Office 365 设置要用于音频会议的电话号码。</span><span class="sxs-lookup"><span data-stu-id="c0374-293">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
  - <span data-ttu-id="c0374-294">查看位置和主要和辅助语言，将使用的音频会议自动助理。</span><span class="sxs-lookup"><span data-stu-id="c0374-294">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>
    
  - <span data-ttu-id="c0374-295">选择它们启用音频会议时，将向用户提供的默认电话号码。</span><span class="sxs-lookup"><span data-stu-id="c0374-295">Select the default phone number that will be given to users when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="c0374-296">但是，如果音频会议桥的默认电话号码发生更改，都不会更改现有用户的默认电话号码。</span><span class="sxs-lookup"><span data-stu-id="c0374-296">However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>
    
<span data-ttu-id="c0374-297">您可以转到**音频会议** > **用户**和用户的属性更改默认的数字的用户通过从您的组织中提供的号码的列表中选择新号码的选择。</span><span class="sxs-lookup"><span data-stu-id="c0374-297">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>
  
<span data-ttu-id="c0374-298">请参阅[音频会议号码的列表，请参阅](see-a-list-of-audio-conferencing-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="c0374-298">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>
  
## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-see-a-list-of-users-that-are-enabled"></a>![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) <span data-ttu-id="c0374-300">查看启用的用户的列表</span><span class="sxs-lookup"><span data-stu-id="c0374-300">See a list of users that are enabled</span></span>

1. <span data-ttu-id="c0374-301">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c0374-301">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c0374-302">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="c0374-302">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="c0374-303">在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议**>，然后**用户**。</span><span class="sxs-lookup"><span data-stu-id="c0374-303">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>
    
<span data-ttu-id="c0374-304">请参阅[请参阅启用了音频会议的用户列表](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="c0374-304">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="c0374-305">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="c0374-305">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="c0374-306">有几种您可以使用 Windows PowerShell 的组织级别管理的设置。</span><span class="sxs-lookup"><span data-stu-id="c0374-306">There are several settings that you can manage at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="c0374-307">这便于将设置应用于所有用户。</span><span class="sxs-lookup"><span data-stu-id="c0374-307">This makes it easy to apply settings to all of your users.</span></span> 
    
<span data-ttu-id="c0374-308">要获得有关每个 cmdlet 的更多帮助，请参阅 [Skype for Business Online cmdlet](https://go.microsoft.com/fwlink/?LinkId=627324)。</span><span class="sxs-lookup"><span data-stu-id="c0374-308">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="c0374-309">下面是组织级别设置：</span><span class="sxs-lookup"><span data-stu-id="c0374-309">Here are the organization-level settings:</span></span> 
 
- <span data-ttu-id="c0374-310">**设置条目/退出通知**默认值为 _$true_。</span><span class="sxs-lookup"><span data-stu-id="c0374-310">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false 
  ```

- <span data-ttu-id="c0374-311">**设置名称录制**默认值为 _$true_。</span><span class="sxs-lookup"><span data-stu-id="c0374-311">**Setting name recording** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="c0374-312">**设置 PIN 长度**默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="c0374-312">**Setting the PIN length** The default is 5.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="c0374-313">**设置仅电话拨入式会议从电话**默认 _$false_。</span><span class="sxs-lookup"><span data-stu-id="c0374-313">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="c0374-314">**设置是否向用户发送电子邮件**默认值为 _$true_。</span><span class="sxs-lookup"><span data-stu-id="c0374-314">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="c0374-315">**设置是否发送电子邮件从不同的帐户**默认值为 _$false_。</span><span class="sxs-lookup"><span data-stu-id="c0374-315">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="c0374-316">**设置在发送给用户的电子邮件发件人地址**默认值为 _$null_。</span><span class="sxs-lookup"><span data-stu-id="c0374-316">**Setting the From address on email that is sent to users** The default is _$null_.</span></span> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="c0374-317">**设置电子邮件发送给用户的显示名称**默认值为 _$null_。</span><span class="sxs-lookup"><span data-stu-id="c0374-317">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="c0374-318">想要了解有关 Windows PowerShell 的详细信息</span><span class="sxs-lookup"><span data-stu-id="c0374-318">Want to know more about Windows PowerShell</span></span>   
- <span data-ttu-id="c0374-p123">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="c0374-p123">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c0374-322">为什么您需要使用 Office 365 PowerShell 中</span><span class="sxs-lookup"><span data-stu-id="c0374-322">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="c0374-323">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="c0374-323">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="c0374-324">Windows PowerShell 具有很多好处中快速、 简便起见和生产力通过只使用 Office 365 管理中心中的，如时要进行设置更改多个用户一次。</span><span class="sxs-lookup"><span data-stu-id="c0374-324">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="c0374-325">请在以下主题中了解这些优点：</span><span class="sxs-lookup"><span data-stu-id="c0374-325">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="c0374-326">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="c0374-326">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="c0374-327">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c0374-327">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="c0374-328">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="c0374-328">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    <span data-ttu-id="c0374-p125">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="c0374-p125">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="c0374-331">相关主题</span><span class="sxs-lookup"><span data-stu-id="c0374-331">Related topics</span></span>

[<span data-ttu-id="c0374-332">管理用户的音频会议设置</span><span class="sxs-lookup"><span data-stu-id="c0374-332">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)


