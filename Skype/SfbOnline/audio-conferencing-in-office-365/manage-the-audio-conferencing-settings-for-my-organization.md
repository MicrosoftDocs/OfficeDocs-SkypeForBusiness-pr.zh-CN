---
title: 在 Skype for Business Online 中管理我的组织的音频会议设置
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: '请参阅 Skype for business Online 步骤，将电话拨入式会议许可证和会议 ID 分配给用户以及其他许多电话拨入式会议设置。 '
ms.openlocfilehash: f5597ae2b857569b7890d81577e4fd4252da5106
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962700"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a><span data-ttu-id="d2391-103">在 Skype for Business Online 中管理我的组织的音频会议设置</span><span class="sxs-lookup"><span data-stu-id="d2391-103">Manage the Audio Conferencing settings for my organization in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="d2391-104">如果您要在团队中管理这些设置，请参阅 [在 Microsoft Teams 中管理我的组织的音频会议设置](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams) 。</span><span class="sxs-lookup"><span data-stu-id="d2391-104">If you want to manage these settings in Teams, see [Manage the Audio Conferencing settings for my organization in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span></span>

<span data-ttu-id="d2391-105">您可以更轻松地在一个位置查看 Skype for business 的所有音频会议设置。</span><span class="sxs-lookup"><span data-stu-id="d2391-105">It might be easier for you to see all of the audio conferencing settings for Skype for Business in one place.</span></span>


## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="d2391-106">分配音频会议许可证</span><span class="sxs-lookup"><span data-stu-id="d2391-106">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="d2391-p101">您不能使用**Skype For business 管理中心**分配许可证。您必须使用 Microsoft 365 管理中心。请参阅[分配 Skype For business 许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="d2391-p101">You can't assign licenses using the **Skype for Business admin center**. You must use the Microsoft 365 admin center. See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

 <span data-ttu-id="d2391-110">**为用户分配许可证**</span><span class="sxs-lookup"><span data-stu-id="d2391-110">**To assign a license for a user**</span></span>

1. <span data-ttu-id="d2391-111">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="d2391-111">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="d2391-112">在管理中心的左侧导航中，转到 "**用户** > **活动用户**"，然后从可用的用户列表中选择一个或一组用户。</span><span class="sxs-lookup"><span data-stu-id="d2391-112">In the left navigation of the admin center, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2391-p102">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view. Then click **Edit**, **Next** twice then select the license and click **Submit**. You can also assign licenses to multiple users by using Windows Powershell. For instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="d2391-p102">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view. Then click **Edit**, **Next** twice then select the license and click **Submit**. You can also assign licenses to multiple users by using Windows Powershell. For instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

3. <span data-ttu-id="d2391-117">在"操作"窗格中的" **产品许可证**"下，单击" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="d2391-117">In the Action pane under **Product licenses**, click **Edit**.</span></span>

4. <span data-ttu-id="d2391-p103">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="d2391-p103">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d2391-p104">分配许可证后，Microsoft 可能不会以音频会议提供商的形式最初显示在列表中。如果出现这种情况，请注销管理中心或按 CTRL + F5 刷新浏览器窗口。</span><span class="sxs-lookup"><span data-stu-id="d2391-p104">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the admin center or press CTRL+F5 to refresh the browser window.</span></span>

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="d2391-122">启用或禁用发送给音频会议用户的电子邮件</span><span class="sxs-lookup"><span data-stu-id="d2391-122">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="d2391-123">![](../images/sfb-logo-30x30.png) **使用 skype for business 管理中心**显示 skype for business 徽标的图标</span><span class="sxs-lookup"><span data-stu-id="d2391-123">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="d2391-124">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="d2391-124">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="d2391-125">转到管理中心 > **Skype for** business，然后在左侧导航中，单击 "**音频会议**"。</span><span class="sxs-lookup"><span data-stu-id="d2391-125">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="d2391-126">在  **Microsoft 网桥的设置** 页上，选中或清除 **自动向用户发送电子邮件，如果他们的音频会议设置更改**   。</span><span class="sxs-lookup"><span data-stu-id="d2391-126">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="d2391-127">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="d2391-127">Click **Save**.</span></span>

    <span data-ttu-id="d2391-p105">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**. The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span><span class="sxs-lookup"><span data-stu-id="d2391-p105">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**. The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>

    <span data-ttu-id="d2391-130">请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。</span><span class="sxs-lookup"><span data-stu-id="d2391-130">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="d2391-131">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="d2391-131">**Using Windows PowerShell**</span></span>

- <span data-ttu-id="d2391-132">你还可以使用 Windows PowerShell 并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d2391-132">You can also use the Windows PowerShell and run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="d2391-133">你可以使用[set-csonlinedialinconferencingtenantsettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)管理组织的其他设置，包括电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d2391-133">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) to manage other settings for your organization, including email.</span></span>

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="d2391-134">更改发送给用户的电子邮件中的发件人的联系人信息</span><span class="sxs-lookup"><span data-stu-id="d2391-134">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="d2391-p106">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information. By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet. To make changes to the email address that is sending the email to the users, you must:</span><span class="sxs-lookup"><span data-stu-id="d2391-p106">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information. By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet. To make changes to the email address that is sending the email to the users, you must:</span></span>

- <span data-ttu-id="d2391-138">在_SendEmailFromAddress_参数中输入电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="d2391-138">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>

- <span data-ttu-id="d2391-139">在  _SendEmailFromDisplayName_ 参数中输入电子邮件的显示名称。</span><span class="sxs-lookup"><span data-stu-id="d2391-139">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>

- <span data-ttu-id="d2391-140">将_SendEmailOverride_参数设置为 _True_。</span><span class="sxs-lookup"><span data-stu-id="d2391-140">Set the _SendEmailOverride_ parameter to _True_.</span></span>

<span data-ttu-id="d2391-141">你可以运行如下命令，更改发送给用户的电子邮件，例如电子邮件的发件人电子邮件地址，或者电子邮件的显示名称：</span><span class="sxs-lookup"><span data-stu-id="d2391-141">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="d2391-142">如果要更改电子邮件地址信息，你需要确保你的组织的入站电子邮件策略允许来自自定义电子邮件地址的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d2391-142">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>

<span data-ttu-id="d2391-143">你可以使用[set-csonlinedialinconferencingtenantsettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet 管理你的组织的其他设置，包括电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d2391-143">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to manage other settings for your organization, including email.</span></span>

<span data-ttu-id="d2391-144">请参阅[在用户的音频会议设置更改时自动发送给用户的电子邮件](emails-sent-to-users-when-their-settings-change.md)。</span><span class="sxs-lookup"><span data-stu-id="d2391-144">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="d2391-145">重置会议 ID</span><span class="sxs-lookup"><span data-stu-id="d2391-145">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="d2391-146">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="d2391-146">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="d2391-147">转到管理中心 > **Skype For business**。</span><span class="sxs-lookup"><span data-stu-id="d2391-147">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="d2391-148">在**Skype for Business 管理中心**，在左侧导航窗格中，转到 **音频会议**，并在 **会议 ID**下的操作窗格中，单击 **重置**。</span><span class="sxs-lookup"><span data-stu-id="d2391-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="d2391-p107">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.</span><span class="sxs-lookup"><span data-stu-id="d2391-p107">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="d2391-p108">After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="d2391-p108">After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>

<span data-ttu-id="d2391-156">请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="d2391-156">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>

## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="d2391-157">重置会议组织者的 PIN</span><span class="sxs-lookup"><span data-stu-id="d2391-157">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="d2391-p109">Each meeting that a user schedules will get assigned a unique conference ID. Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID. You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span><span class="sxs-lookup"><span data-stu-id="d2391-p109">Each meeting that a user schedules will get assigned a unique conference ID. Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID. You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>


1. <span data-ttu-id="d2391-161">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="d2391-161">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="d2391-162">转到管理中心 > **Skype for** business，然后在左侧导航中，单击 "**音频会议**"。</span><span class="sxs-lookup"><span data-stu-id="d2391-162">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="d2391-163">单击 "**用户**"，然后选择要为其重置 PIN 的用户。</span><span class="sxs-lookup"><span data-stu-id="d2391-163">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="d2391-164">在操作窗格中的 "**固定**" 下，单击 "**重置**"。</span><span class="sxs-lookup"><span data-stu-id="d2391-164">In the Action pane, under **PIN**, click **Reset**.</span></span>

<span data-ttu-id="d2391-p110">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span><span class="sxs-lookup"><span data-stu-id="d2391-p110">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span>

<span data-ttu-id="d2391-169">请参阅[重置音频会议 PIN 码](reset-the-audio-conferencing-pin.md)。</span><span class="sxs-lookup"><span data-stu-id="d2391-169">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="d2391-170">向用户发送包含音频会议信息的电子邮件</span><span class="sxs-lookup"><span data-stu-id="d2391-170">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="d2391-171">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="d2391-171">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="d2391-172">转到管理中心 > **Skype for** business，然后在左侧导航中，单击 "**音频会议**"。</span><span class="sxs-lookup"><span data-stu-id="d2391-172">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="d2391-173">单击 "**用户**"，然后选择要为其重置 PIN 的用户。</span><span class="sxs-lookup"><span data-stu-id="d2391-173">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="d2391-174">在操作窗格中，单击" **通过电子邮件发送会议信息**"。</span><span class="sxs-lookup"><span data-stu-id="d2391-174">In the Action pane, click **Send conference info via email**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2391-175">执行此操作时，音频会议 PIN 不会发送给用户。</span><span class="sxs-lookup"><span data-stu-id="d2391-175">When you do this, the audio conferencing PIN isn't sent to the user.</span></span>

<span data-ttu-id="d2391-176">请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。</span><span class="sxs-lookup"><span data-stu-id="d2391-176">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="d2391-177">设置邀请中包含的电话号码</span><span class="sxs-lookup"><span data-stu-id="d2391-177">Setting the phone numbers included on invites</span></span>

1. <span data-ttu-id="d2391-178">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="d2391-178">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="d2391-179">转到管理中心 > **Skype For business**。</span><span class="sxs-lookup"><span data-stu-id="d2391-179">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="d2391-p111">In the left navigation, go to **Audio conferencing** > **Users**. Select the user that you want to enable for Audio Conferencing.</span><span class="sxs-lookup"><span data-stu-id="d2391-p111">In the left navigation, go to **Audio conferencing** > **Users**. Select the user that you want to enable for Audio Conferencing.</span></span>

4. <span data-ttu-id="d2391-182">在操作窗格中，您可以设置 　**收费电话号码**　，如果允许， **免费电话号码**　。</span><span class="sxs-lookup"><span data-stu-id="d2391-182">In the Action pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

5. <span data-ttu-id="d2391-183">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="d2391-183">Click **Save**.</span></span>

<span data-ttu-id="d2391-184">请参阅[设置邀请附带的电话号码](set-the-phone-numbers-included-on-invites.md)。</span><span class="sxs-lookup"><span data-stu-id="d2391-184">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>


## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="d2391-185">选择音频会议网桥的设置</span><span class="sxs-lookup"><span data-stu-id="d2391-185">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="d2391-186">**设置呼叫者加入会议时的会议体验**</span><span class="sxs-lookup"><span data-stu-id="d2391-186">**Set the meeting experience when callers join a meeting**</span></span>


1. <span data-ttu-id="d2391-187">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="d2391-187">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="d2391-188">转到管理中心 > **Skype For business**。</span><span class="sxs-lookup"><span data-stu-id="d2391-188">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="d2391-189">在**Skype for business 管理中心**的左侧导航中，转到 "**音频会议** > **Microsoft 网桥设置**"。</span><span class="sxs-lookup"><span data-stu-id="d2391-189">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="d2391-190">在 "**会议加入体验**" 下，选择以下操作：</span><span class="sxs-lookup"><span data-stu-id="d2391-190">Under **Meeting join experience**, select the following actions:</span></span>

   - <span data-ttu-id="d2391-p112">**Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span><span class="sxs-lookup"><span data-stu-id="d2391-p112">**Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

     <span data-ttu-id="d2391-193">当用户使用 Skype for Business 应用加入会议，并且他们在会议的 "Skype 会议**选项**" 菜单中修改 "**当用户进入或离开时通知**" 设置时，可以按会议进行设置。</span><span class="sxs-lookup"><span data-stu-id="d2391-193">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business app and they modify the **Announce when people enter or leave** setting in the Skype Meeting **Options** menu of the meeting.</span></span>

   - <span data-ttu-id="d2391-p113">**Ask callers to record their name before joining the meeting** This is selected by default. If you clear this check box, callers won't be asked to record their name before they join a meeting.</span><span class="sxs-lookup"><span data-stu-id="d2391-p113">**Ask callers to record their name before joining the meeting** This is selected by default. If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>

5. <span data-ttu-id="d2391-196">完成更改后，单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="d2391-196">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="d2391-197">请参阅[更改音频会议网桥的设置](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="d2391-197">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="d2391-198">**设置会议的 PIN 长度**</span><span class="sxs-lookup"><span data-stu-id="d2391-198">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="d2391-199">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="d2391-199">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="d2391-200">转到管理中心 > **Skype For business**。</span><span class="sxs-lookup"><span data-stu-id="d2391-200">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="d2391-201">在**Skype for business 管理中心**的左侧导航中，转到 "**音频会议** > **Microsoft 网桥设置**"。</span><span class="sxs-lookup"><span data-stu-id="d2391-201">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="d2391-202">在 "**安全**" 下，在 " **pin 长度**" 列表中输入您希望的 pin 位数，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="d2391-202">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="d2391-p114">The PIN must be between 4 and 12 digits. The default is 5.</span><span class="sxs-lookup"><span data-stu-id="d2391-p114">The PIN must be between 4 and 12 digits. The default is 5.</span></span>
    
<span data-ttu-id="d2391-205">请参阅[更改音频会议网桥的设置](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="d2391-205">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="d2391-206">**启用或禁用向音频用户发送电子邮件**</span><span class="sxs-lookup"><span data-stu-id="d2391-206">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="d2391-207">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="d2391-207">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="d2391-208">转到管理中心 > **Skype for** business，然后在左侧导航中，单击 "**音频会议**"。</span><span class="sxs-lookup"><span data-stu-id="d2391-208">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="d2391-209">在 **Microsoft 网桥的设置** 页上，选中或清除 **自动向用户发送电子邮件，如果他们的音频会议设置更改**　。</span><span class="sxs-lookup"><span data-stu-id="d2391-209">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="d2391-210">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="d2391-210">Click **Save**.</span></span>

    <span data-ttu-id="d2391-211">您还可以通过音频会议设置向用户发送电子邮件，方法是转到用户的音频会议属性，然后单击 "**通过电子邮件发送会议信息**"。</span><span class="sxs-lookup"><span data-stu-id="d2391-211">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>

    <span data-ttu-id="d2391-212">如果执行此操作，则将发送仅包括会议 ID 和会议电话号码的电子邮件，但不包括 PIN。</span><span class="sxs-lookup"><span data-stu-id="d2391-212">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

    <span data-ttu-id="d2391-213">请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。</span><span class="sxs-lookup"><span data-stu-id="d2391-213">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="d2391-214">在音频会议桥处查看和设置主要（默认）和辅助（备用）语言</span><span class="sxs-lookup"><span data-stu-id="d2391-214">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>


1. <span data-ttu-id="d2391-215">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="d2391-215">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="d2391-216">转到管理中心 > **Skype For business**。</span><span class="sxs-lookup"><span data-stu-id="d2391-216">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="d2391-217">在**Skype For business 管理中心**的左侧导航中，转到 "**音频会议**"，然后单击 " **Microsoft bridge**"。</span><span class="sxs-lookup"><span data-stu-id="d2391-217">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>

4. <span data-ttu-id="d2391-218">从列表中选择电话号码，在 "操作" 窗格中单击 "**设置语言**"，然后在 "**设置语言**" 页面上，单击 "使用**主要语言**列表" 查看受支持语言的完整列表。</span><span class="sxs-lookup"><span data-stu-id="d2391-218">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>

    <span data-ttu-id="d2391-p115">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider. The order that you select in the lists is the same order in which languages will be presented to callers.</span><span class="sxs-lookup"><span data-stu-id="d2391-p115">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider. The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>

<span data-ttu-id="d2391-221">请参阅[设置音频会议自动助理语言](set-auto-attendant-languages-for-audio-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="d2391-221">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>

## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="d2391-222">请参阅音频会议拨入号码</span><span class="sxs-lookup"><span data-stu-id="d2391-222">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="d2391-223">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="d2391-223">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="d2391-224">转到管理中心 > **Skype For business**。</span><span class="sxs-lookup"><span data-stu-id="d2391-224">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="d2391-p116">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**. Here you can:</span><span class="sxs-lookup"><span data-stu-id="d2391-p116">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**. Here you can:</span></span>

   - <span data-ttu-id="d2391-227">查看由 Office 365 设置用于音频会议的电话号码。</span><span class="sxs-lookup"><span data-stu-id="d2391-227">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span>

   - <span data-ttu-id="d2391-228">查看音频会议自动助理将使用的位置以及主要和辅助语言。</span><span class="sxs-lookup"><span data-stu-id="d2391-228">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>

   - <span data-ttu-id="d2391-p117">Select the default phone number that will be given to users when they are enabled for Audio Conferencing. However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span><span class="sxs-lookup"><span data-stu-id="d2391-p117">Select the default phone number that will be given to users when they are enabled for Audio Conferencing. However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>

<span data-ttu-id="d2391-231">您可以转到**音频会议** > **用户**并选择用户的属性以更改用户的默认号码，方法是从您的组织中可用的号码列表中选择新号码。</span><span class="sxs-lookup"><span data-stu-id="d2391-231">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>

<span data-ttu-id="d2391-232">请参阅[音频会议号码列表](see-a-list-of-audio-conferencing-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="d2391-232">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>

## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="d2391-233">查看启用的用户的列表</span><span class="sxs-lookup"><span data-stu-id="d2391-233">See a list of users that are enabled</span></span>

1. <span data-ttu-id="d2391-234">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="d2391-234">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="d2391-235">转到管理中心 > **Skype For business**。</span><span class="sxs-lookup"><span data-stu-id="d2391-235">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="d2391-236">在**Skype For business 管理中心**的左侧导航中，转到 "**音频会议**>" 和 "**用户**"。</span><span class="sxs-lookup"><span data-stu-id="d2391-236">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>

<span data-ttu-id="d2391-237">请参阅[请参阅启用了音频会议的用户列表](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="d2391-237">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="d2391-238">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="d2391-238">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="d2391-p118">There are several settings that you can manage at the organization level using Windows PowerShell. This makes it easy to apply settings to all of your users.</span><span class="sxs-lookup"><span data-stu-id="d2391-p118">There are several settings that you can manage at the organization level using Windows PowerShell. This makes it easy to apply settings to all of your users.</span></span>

<span data-ttu-id="d2391-241">要获得有关每个 cmdlet 的更多帮助，请参阅 [Skype for Business Online cmdlet](https://go.microsoft.com/fwlink/?LinkId=627324)。</span><span class="sxs-lookup"><span data-stu-id="d2391-241">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="d2391-242">下面是组织级设置：</span><span class="sxs-lookup"><span data-stu-id="d2391-242">Here are the organization-level settings:</span></span>

- <span data-ttu-id="d2391-243">**设置输入/退出通知** 默认值为 _$true_ 。</span><span class="sxs-lookup"><span data-stu-id="d2391-243">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- <span data-ttu-id="d2391-244">**设置名称录制** 默认值为 _$true_ 。</span><span class="sxs-lookup"><span data-stu-id="d2391-244">**Setting name recording** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="d2391-245">**设置 PIN 长度** 默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="d2391-245">**Setting the PIN length** The default is 5.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="d2391-246">**仅从电话中设置拨入会议**默认 _$false_。</span><span class="sxs-lookup"><span data-stu-id="d2391-246">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="d2391-247">**设置是否向用户发送电子邮件**默认值为 _$true_。</span><span class="sxs-lookup"><span data-stu-id="d2391-247">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="d2391-248">**设置是否从不同的帐户发送电子邮件** 默认值为 _$false_ 。</span><span class="sxs-lookup"><span data-stu-id="d2391-248">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="d2391-249">**在发送给用户的电子邮件中设置发件地址** 默认值为 _$null_。</span><span class="sxs-lookup"><span data-stu-id="d2391-249">**Setting the From address on email that is sent to users** The default is _$null_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="d2391-250">**为发送给用户的电子邮件设置显示名称**默认值为 _$null_。</span><span class="sxs-lookup"><span data-stu-id="d2391-250">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

  ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="d2391-251">希望了解有关 Windows PowerShell 的详细信息</span><span class="sxs-lookup"><span data-stu-id="d2391-251">Want to know more about Windows PowerShell</span></span>
- <span data-ttu-id="d2391-p119">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="d2391-p119">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="d2391-255">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="d2391-255">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [<span data-ttu-id="d2391-256">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="d2391-256">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

- <span data-ttu-id="d2391-p120">Windows PowerShell 在速度、简洁性和效率方面具有许多优势，仅限于使用管理中心，例如当你为多个用户同时进行设置更改时。了解以下主题中的这些优势：</span><span class="sxs-lookup"><span data-stu-id="d2391-p120">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="d2391-259">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="d2391-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="d2391-260">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d2391-260">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="d2391-261">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="d2391-261">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

    <span data-ttu-id="d2391-p121">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="d2391-p121">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>

## <a name="related-topics"></a><span data-ttu-id="d2391-264">相关主题</span><span class="sxs-lookup"><span data-stu-id="d2391-264">Related topics</span></span>

[<span data-ttu-id="d2391-265">管理用户的音频会议设置</span><span class="sxs-lookup"><span data-stu-id="d2391-265">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)


