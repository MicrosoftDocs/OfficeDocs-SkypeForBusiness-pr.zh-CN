---
title: 他们设置更改时，向用户发送电子邮件
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
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
description: 'Learn about what information is sent automatically to users by email when their dial-in conferencing settings change. '
ms.openlocfilehash: 0cf1eabd25a6be5d6104c2593e5bc286d15d59f0
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/05/2018
---
# <a name="emails-sent-to-users-when-their-settings-change"></a><span data-ttu-id="a5cf4-103">他们设置更改时，向用户发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="a5cf4-103">Emails sent to users when their settings change</span></span>

<span data-ttu-id="a5cf4-104">电子邮件将自动发送给[启用音频会议](set-up-audio-conferencing.md)的用户通过音频会议提供商作为 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-104">Emails will be automatically sent to users who are [enabled for Audio Conferencing](set-up-audio-conferencing.md) using Microsoft as the audio conferencing provider.</span></span>
  
<span data-ttu-id="a5cf4-105">默认情况下，有四种类型的电子邮件将发送给您的用户启用了音频会议。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-105">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="a5cf4-106">但是，如果要限制向用户发送的电子邮件数，你可以将其关闭。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-106">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="a5cf4-107">Office 365 中的音频会议会将电子邮件发送到用户的电子邮件时：</span><span class="sxs-lookup"><span data-stu-id="a5cf4-107">Audio Conferencing in Office 365 will send email to your users' email when:</span></span>
  
- <span data-ttu-id="a5cf4-108">**音频会议许可分配给他们，或向 Microsoft 更改音频会议提供商时。**</span><span class="sxs-lookup"><span data-stu-id="a5cf4-108">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>
    
     <span data-ttu-id="a5cf4-109">此电子邮件包含会议 ID、 会议、 音频会议针的用户，以及链接说明用于 Skype 业务在线会议更新工具，用来更新现有的会议默认会议电话号码用户。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-109">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="a5cf4-110">请参阅[有关业务和 Microsoft 小组许可证分配 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)或[作为音频会议提供商指定的 Microsoft](assign-microsoft-as-the-audio-conferencing-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-110">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a5cf4-111">[!注释] 如果你的组织已启用动态会议 ID，用户安排的所有会议将具有唯一的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-111">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="a5cf4-112">您可以设置[您的组织中的音频会议动态 Id](using-audio-conferencing-dynamic-ids-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-112">You can set up [Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
    <span data-ttu-id="a5cf4-113">下面是此电子邮件的一个示例：</span><span class="sxs-lookup"><span data-stu-id="a5cf4-113">Here is an example of this email:</span></span>
    
     ![Skype for Business 验证许可证](../images/audio-conferencing-user-enabled.png)
  
    <span data-ttu-id="a5cf4-115">您可以了解更多关于 Skype 业务授权通过查看[附加业务和 Microsoft 小组授权的 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-115">You can find out more about Skype for Business licensing by seeing [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
- <span data-ttu-id="a5cf4-116">**会议 ID 或用户默认会议电话号码更改。**</span><span class="sxs-lookup"><span data-stu-id="a5cf4-116">**The conference ID or default conference phone number of a user changes.**</span></span>
    
    <span data-ttu-id="a5cf4-117">此电子邮件包括会议 ID、默认会议电话号码以及使用 Skype for Business Online 会议更新工具为用户更新现有会议的说明和链接。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-117">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="a5cf4-118">但这封电子邮件中不包含用户的音频会议针。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-118">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="a5cf4-119">请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-119">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a5cf4-120">[!注释] 如果你的组织已启用动态会议 ID，用户安排的所有会议将具有唯一的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-120">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="a5cf4-121">您可以设置[您的组织中的音频会议动态 Id](using-audio-conferencing-dynamic-ids-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-121">You can set up [Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
    <span data-ttu-id="a5cf4-122">下面是此电子邮件的一个示例：</span><span class="sxs-lookup"><span data-stu-id="a5cf4-122">Here is an example of this email:</span></span>
    
     ![电话拨入式会议信息已更改。](../images/audio-conferencing-info-change.png)
  
- <span data-ttu-id="a5cf4-124">**音频会议针的用户将被重置。**</span><span class="sxs-lookup"><span data-stu-id="a5cf4-124">**The audio conferencing PIN of a user is reset.**</span></span>
    
    <span data-ttu-id="a5cf4-125">此电子邮件包含了组织者的音频会议针、 现有会议 ID 和默认为用户的会议电话号码。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-125">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="a5cf4-126">请参阅[重置用户的音频会议 PIN](reset-the-audio-conferencing-pin-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-126">See [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin-for-a-user.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a5cf4-127">[!注释] 如果你的组织已启用动态会议 ID，用户安排的所有会议将具有唯一的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-127">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="a5cf4-128">您可以设置[您的组织中的音频会议动态 Id](using-audio-conferencing-dynamic-ids-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-128">You can set up [Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
    <span data-ttu-id="a5cf4-129">下面是此电子邮件的一个示例：</span><span class="sxs-lookup"><span data-stu-id="a5cf4-129">Here is an example of this email:</span></span>
    
     ![电话拨入式会议 PIN 已更改。](../images/audio-conferencing-pin-has-changed.png)
  
- <span data-ttu-id="a5cf4-131">**移除用户的许可证更改时或音频会议提供商从 Microsoft 与其他提供者或无。**</span><span class="sxs-lookup"><span data-stu-id="a5cf4-131">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>
    
    <span data-ttu-id="a5cf4-132">**音频会议**许可删除后从用户从 Microsoft 更改用户的音频会议提供商，为第三方音频会议提供商时或为**无**设置提供程序时，将发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-132">This happens when the **Audio Conferencing** license is removed from a user or when changing the audio conferencing provider of a user from Microsoft to a third-party audio conferencing provider or when setting the provider to **None**.</span></span> <span data-ttu-id="a5cf4-133">此电子邮件包含的指令和信息，为用户使用业务联机会议更新工具 Skype 来删除音频会议的特定信息，例如默认会议电话号码或会议 id。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-133">This email contains the instructions and information for the user to use the Skype for Business Online Meeting Update Tool to remove audio conferencing specific information, such as the default conference phone number or conference ID.</span></span>
    
    <span data-ttu-id="a5cf4-134">请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-134">See [Assign or remove licenses for Office 365 for business](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
    
    <span data-ttu-id="a5cf4-135">下面是此电子邮件的一个示例：</span><span class="sxs-lookup"><span data-stu-id="a5cf4-135">Here is an example of this email:</span></span>
    
     ![电话拨入式会议已关闭。](../images/audio-conferencing-turned-off.png)
  
## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="a5cf4-137">更改发送给用户的电子邮件</span><span class="sxs-lookup"><span data-stu-id="a5cf4-137">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="a5cf4-138">您可以对电子邮件自动发送给用户的电子邮件地址，并在*从*联系人信息中包含显示名称包括进行更改。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-138">You can make changes to the email that is automatically sent to users including the email address and the display name that is included in the *From* contact information.</span></span> <span data-ttu-id="a5cf4-139">默认情况下，电子邮件的发件人将从 Office 365，但您可以更改的电子邮件地址和显示名称使用 Windows PowerShell 和[一组 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-139">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span> <span data-ttu-id="a5cf4-140">若要将电子邮件发送到用户的电子邮件地址进行更改，您必须：</span><span class="sxs-lookup"><span data-stu-id="a5cf4-140">To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="a5cf4-141">在  _SendEmailFromAddress_ 参数中输入电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-141">Enter the email address in the  _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="a5cf4-142">在  _SendEmailFromDisplayName_ 参数中输入电子邮件的显示名称。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-142">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="a5cf4-143">将_SendEmailOverride_参数设置为_True_。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-143">Set the  _SendEmailOverride_ parameter to  _True_.</span></span>
    
<span data-ttu-id="a5cf4-144">您可以更改发送给用户，如发送电子邮件的电子邮件地址和电子邮件，显示名称通过运行的电子邮件：</span><span class="sxs-lookup"><span data-stu-id="a5cf4-144">You can make changes to the email sent to users, such as the email address that the email is sent from and the display name for the email, by running:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  <span data-ttu-id="a5cf4-145">如果您想要更改的电子邮件地址信息，您需要确保您的环境的入站电子邮件策略允许来自指定发件人地址的自定义的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-145">If you want to change the email address information, you need to make sure that the inbound email policies of your environment allow emails that come from the custom specified from address.</span></span> <span data-ttu-id="a5cf4-146">如果您决定重写*从*联系人信息，则应验证电子邮件将正常发送给用户。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-146">If you decide to override the *From* contact information, you should verify that the emails are correctly sent to users.</span></span> <span data-ttu-id="a5cf4-147">您可以使用您的组织中的一个用户测试这这样做。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-147">You can do this by testing this with one user in your organization.</span></span>
  
<span data-ttu-id="a5cf4-148">可以使用[一组 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet 来管理您的组织，包括电子邮件的其他设置。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-148">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="a5cf4-149">如果不想向用户发送电子邮件，又该怎样做？</span><span class="sxs-lookup"><span data-stu-id="a5cf4-149">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="a5cf4-150">当禁用电子邮件发送给用户时，即使用户拥有分配的许可证，也不会向其发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-150">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="a5cf4-151">在此情况下，会议 ID 中，默认的会议电话号码，并且，更重要的是，不会向用户发送其音频会议针。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-151">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="a5cf4-152">发生这种情况时，你必须通过向用户发送单独的电子邮件或呼叫他们进行通知。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-152">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>
  
<span data-ttu-id="a5cf4-153">默认情况下，电子邮件将发送给您的用户，但如果您想要防止它们被用于音频会议接收电子邮件，可以使用 Microsoft 小组、 Skype 业务管理中心，或 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-153">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use Microsoft Teams, the Skype for Business admin center, or Windows PowerShell.</span></span> 

<span data-ttu-id="a5cf4-154">**使用 Microsoft 小组和 Skype 业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="a5cf4-154">**Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="a5cf4-155">在左侧的导航中，转到**会议** > **会议桥**。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-155">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="a5cf4-156">在**会议桥**页的顶部，单击**桥接器设置**。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-156">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="a5cf4-157">**网桥的设置**窗格中启用或禁用**自动发送电子邮件发送给用户，如果他们拨入设置更改**。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-157">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="a5cf4-158">单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-158">Click **Apply**.</span></span>
  
<span data-ttu-id="a5cf4-159">**使用 Skype 业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="a5cf4-159">**Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="a5cf4-160">在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议** > **Microsoft 网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-160">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="a5cf4-161">在**Microsoft 桥设置**页上，选中或清除**自动发送电子邮件发送给用户，如果他们的音频会议设置更改**。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-161">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their audio conferencing settings change**.</span></span> 
    
3. <span data-ttu-id="a5cf4-162">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-162">Click **Save**.</span></span> 
    
<span data-ttu-id="a5cf4-163">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a5cf4-163">**Using Windows PowerShell**</span></span>
  
1. <span data-ttu-id="a5cf4-164">运行以下操作以禁用向你的用户发送所有电子邮件：</span><span class="sxs-lookup"><span data-stu-id="a5cf4-164">Run the following to disable sending all of your users email:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

<span data-ttu-id="a5cf4-165">可以使用[一组 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet 来管理您的组织，包括电子邮件的其他设置。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-165">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="a5cf4-166">此电子邮件的其他须知事项。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-166">What else should you know about this email?</span></span>

- <span data-ttu-id="a5cf4-167">有关如何启用和禁用自动向用户发送电子邮件的更多信息，请参阅[启用或禁用发送电子邮件时更改音频会议设置](enable-or-disable-sending-emails-when-their-settings-change.md)。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-167">For more on enabling and disabling automatically sending email to your users, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
    
- <span data-ttu-id="a5cf4-168">有时用户丢失其音频信息，您需要能够发送他们的所有音频信息给他们。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-168">Sometimes users lose their audio information and you need to be able to send them all of their audio information to them.</span></span> <span data-ttu-id="a5cf4-169">要做到这一点对于业务管理中心使用 Skype 和用户的音频会议属性下，单击**将会议信息通过电子邮件发送**。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-169">You can do this by using the Skype for Business admin center and clicking **Send conference info via email** under the audio conferencing properties for a user.</span></span> <span data-ttu-id="a5cf4-170">请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-170">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span> <span data-ttu-id="a5cf4-171">但是，此信息不包括音频会议针。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-171">However, this information doesn't include the audio conferencing PIN.</span></span>
    
    <span data-ttu-id="a5cf4-172">下面是将发送给用户的电子邮件的一个示例：</span><span class="sxs-lookup"><span data-stu-id="a5cf4-172">Here is an example of this email that will be sent to them:</span></span>
    
     ![电话拨入式会议电子邮件](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="a5cf4-174">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="a5cf4-174">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="a5cf4-175">默认情况下，电子邮件的发件人将从 Office 365，但您可以更改的电子邮件地址和显示名称使用 Windows PowerShell 和[一组 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-175">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span>
    
- <span data-ttu-id="a5cf4-p113">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="a5cf4-p113">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="a5cf4-179">为什么需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="a5cf4-179">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="a5cf4-180">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="a5cf4-180">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="a5cf4-181">Windows PowerShell 许多相比具有的优势在速度、 简易性和生产率仅使用 Office 365 管理中心，例如，当将设置更改为许多用户一次。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-181">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="a5cf4-182">请在以下主题中了解这些优点：</span><span class="sxs-lookup"><span data-stu-id="a5cf4-182">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="a5cf4-183">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="a5cf4-183">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="a5cf4-184">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a5cf4-184">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="a5cf4-185">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="a5cf4-185">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="a5cf4-p115">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="a5cf4-p115">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="a5cf4-188">相关主题</span><span class="sxs-lookup"><span data-stu-id="a5cf4-188">Related topics</span></span>

[<span data-ttu-id="a5cf4-189">启用或禁用发送电子邮件时更改音频会议设置</span><span class="sxs-lookup"><span data-stu-id="a5cf4-189">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[<span data-ttu-id="a5cf4-190">对其音频会议信息的用户发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="a5cf4-190">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)
