---
title: 业务 online 中 Skype 更改其设置时，向用户发送的电子邮件
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解有关哪些信息将自动发送给用户通过电子邮件时业务 online 中 Skype 更改其电话拨入式会议设置。 '
ms.openlocfilehash: cfa3e86be0d282e335b20a094e60835df3471358
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490502"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-skype-for-business-online"></a><span data-ttu-id="4bd28-103">业务 online 中 Skype 更改其设置时，向用户发送的电子邮件</span><span class="sxs-lookup"><span data-stu-id="4bd28-103">Emails sent to users when their settings change in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="4bd28-104">如果您正在寻找自动电子邮件中的 Microsoft 团队的信息，请参阅[电子邮件发送给用户的 Microsoft 团队中更改其设置时](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="4bd28-104">If you're looking for automatic email information in Microsoft Teams, see [Emails sent to users when their settings change in Microsoft Teams](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="4bd28-105">电子邮件将自动发送到[启用了音频会议](set-up-audio-conferencing.md)用户使用 Microsoft 作为音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="4bd28-105">Emails will be automatically sent to users who are [enabled for Audio Conferencing](set-up-audio-conferencing.md) using Microsoft as the audio conferencing provider.</span></span>
  
<span data-ttu-id="4bd28-106">默认情况下，有四种类型的电子邮件将发送到您的用户启用了音频会议。</span><span class="sxs-lookup"><span data-stu-id="4bd28-106">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="4bd28-107">但是，如果要限制向用户发送的电子邮件数，你可以将其关闭。</span><span class="sxs-lookup"><span data-stu-id="4bd28-107">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="4bd28-108">Office 365 中的音频会议将向用户发送电子邮件时的电子邮件：</span><span class="sxs-lookup"><span data-stu-id="4bd28-108">Audio Conferencing in Office 365 will send email to your users' email when:</span></span>
  
- <span data-ttu-id="4bd28-109">**音频会议许可证分配给它们或您要更改为 Microsoft 的音频会议提供商。**</span><span class="sxs-lookup"><span data-stu-id="4bd28-109">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>
    
     <span data-ttu-id="4bd28-110">此电子邮件包括会议 ID，会议，音频会议的用户和链接说明要用于业务在线会议更新工具，用来更新现有会议的 Skype 的 PIN 的默认会议电话号码用户。</span><span class="sxs-lookup"><span data-stu-id="4bd28-110">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="4bd28-111">请参阅[业务许可证分配 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)或[分配 Microsoft 作为音频会议提供商](assign-microsoft-as-the-audio-conferencing-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="4bd28-111">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4bd28-112">[!注释] 如果你的组织已启用动态会议 ID，用户安排的所有会议将具有唯一的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="4bd28-112">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="4bd28-113">您可以设置[您的组织中的音频会议动态 Id](using-audio-conferencing-dynamic-ids-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="4bd28-113">You can set up [Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
    <span data-ttu-id="4bd28-114">下面是此电子邮件的一个示例：</span><span class="sxs-lookup"><span data-stu-id="4bd28-114">Here is an example of this email:</span></span>
    
     ![Skype for Business 验证许可证](../images/audio-conferencing-user-enabled.png)
  
    <span data-ttu-id="4bd28-116">你可以通过参阅 [Skype for Business 附加许可](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)了解有关 Skype for Business 许可的更多信息。</span><span class="sxs-lookup"><span data-stu-id="4bd28-116">You can find out more about Skype for Business licensing by seeing [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
- <span data-ttu-id="4bd28-117">**会议 ID 或用户默认会议电话号码更改。**</span><span class="sxs-lookup"><span data-stu-id="4bd28-117">**The conference ID or default conference phone number of a user changes.**</span></span>
    
    <span data-ttu-id="4bd28-118">此电子邮件包括会议 ID、默认会议电话号码以及使用 Skype for Business Online 会议更新工具为用户更新现有会议的说明和链接。</span><span class="sxs-lookup"><span data-stu-id="4bd28-118">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="4bd28-119">但此电子邮件不包括用户的音频会议 PIN。</span><span class="sxs-lookup"><span data-stu-id="4bd28-119">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="4bd28-120">请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="4bd28-120">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4bd28-121">[!注释] 如果你的组织已启用动态会议 ID，用户安排的所有会议将具有唯一的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="4bd28-121">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="4bd28-122">您可以设置[您的组织中的音频会议动态 Id](using-audio-conferencing-dynamic-ids-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="4bd28-122">You can set up [Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
    <span data-ttu-id="4bd28-123">下面是此电子邮件的一个示例：</span><span class="sxs-lookup"><span data-stu-id="4bd28-123">Here is an example of this email:</span></span>
    
     ![电话拨入式会议信息已更改。](../images/audio-conferencing-info-change.png)
  
- <span data-ttu-id="4bd28-125">**音频会议用户的 PIN 重置。**</span><span class="sxs-lookup"><span data-stu-id="4bd28-125">**The audio conferencing PIN of a user is reset.**</span></span>
    
    <span data-ttu-id="4bd28-126">此电子邮件包含组织者的音频会议 PIN、 现有会议 ID 和用户的默认会议电话号码。</span><span class="sxs-lookup"><span data-stu-id="4bd28-126">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="4bd28-127">请参阅[重置 PIN 的音频会议](reset-the-audio-conferencing-pin.md)。</span><span class="sxs-lookup"><span data-stu-id="4bd28-127">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4bd28-128">[!注释] 如果你的组织已启用动态会议 ID，用户安排的所有会议将具有唯一的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="4bd28-128">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="4bd28-129">您可以设置[您的组织中的音频会议动态 Id](using-audio-conferencing-dynamic-ids-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="4bd28-129">You can set up [Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
    <span data-ttu-id="4bd28-130">下面是此电子邮件的一个示例：</span><span class="sxs-lookup"><span data-stu-id="4bd28-130">Here is an example of this email:</span></span>
    
     ![电话拨入式会议 PIN 已更改。](../images/audio-conferencing-pin-has-changed.png)
  
- <span data-ttu-id="4bd28-132">**删除用户的许可证或音频会议提供商更改时 microsoft 到其他提供程序或无。**</span><span class="sxs-lookup"><span data-stu-id="4bd28-132">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>
    
    <span data-ttu-id="4bd28-133">**音频会议**许可证时将删除来自用户或从 Microsoft 更改用户的音频会议提供商，为第三方音频会议提供商时或设置为**无**的提供程序时，将发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="4bd28-133">This happens when the **Audio Conferencing** license is removed from a user or when changing the audio conferencing provider of a user from Microsoft to a third-party audio conferencing provider or when setting the provider to **None**.</span></span> <span data-ttu-id="4bd28-134">此电子邮件包含说明和信息的用户使用的业务联机会议更新工具 Skype 删除音频会议的特定信息，例如默认会议电话号码或会议 id。</span><span class="sxs-lookup"><span data-stu-id="4bd28-134">This email contains the instructions and information for the user to use the Skype for Business Online Meeting Update Tool to remove audio conferencing specific information, such as the default conference phone number or conference ID.</span></span>
    
    <span data-ttu-id="4bd28-135">请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="4bd28-135">See [Assign or remove licenses for Office 365 for business](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
    
    <span data-ttu-id="4bd28-136">下面是此电子邮件的一个示例：</span><span class="sxs-lookup"><span data-stu-id="4bd28-136">Here is an example of this email:</span></span>
    
     ![电话拨入式会议已关闭。](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="4bd28-138">更改发送给用户的电子邮件</span><span class="sxs-lookup"><span data-stu-id="4bd28-138">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="4bd28-139">您可以对会自动向用户的电子邮件地址和*从*联系人信息中包括的显示名称包括发送的电子邮件进行更改。</span><span class="sxs-lookup"><span data-stu-id="4bd28-139">You can make changes to the email that is automatically sent to users including the email address and the display name that is included in the *From* contact information.</span></span> <span data-ttu-id="4bd28-140">默认情况下，电子邮件发件人将从 Office 365，但您可以更改电子邮件地址，并显示名称使用 Windows PowerShell 和[设置 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4bd28-140">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span> <span data-ttu-id="4bd28-141">若要更改向用户发送电子邮件的电子邮件地址，您必须：</span><span class="sxs-lookup"><span data-stu-id="4bd28-141">To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="4bd28-142">在  _SendEmailFromAddress_ 参数中输入电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="4bd28-142">Enter the email address in the  _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="4bd28-143">在  _SendEmailFromDisplayName_ 参数中输入电子邮件的显示名称。</span><span class="sxs-lookup"><span data-stu-id="4bd28-143">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="4bd28-144">_SendEmailOverride_参数设置为_True_。</span><span class="sxs-lookup"><span data-stu-id="4bd28-144">Set the  _SendEmailOverride_ parameter to  _True_.</span></span>
    
<span data-ttu-id="4bd28-145">对电子邮件发送给用户，例如从发送电子邮件的电子邮件地址和电子邮件、 的显示名称的运行，您可以进行更改：</span><span class="sxs-lookup"><span data-stu-id="4bd28-145">You can make changes to the email sent to users, such as the email address that the email is sent from and the display name for the email, by running:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  <span data-ttu-id="4bd28-146">如果您想要更改的电子邮件地址信息，您需要确保您的环境的入站电子邮件策略允许来自指定发件人地址的自定义的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="4bd28-146">If you want to change the email address information, you need to make sure that the inbound email policies of your environment allow emails that come from the custom specified from address.</span></span> <span data-ttu-id="4bd28-147">如果您决定覆盖*从*联系信息，您应验证正确向用户发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="4bd28-147">If you decide to override the *From* contact information, you should verify that the emails are correctly sent to users.</span></span> <span data-ttu-id="4bd28-148">您可以通过测试这与您的组织中的一个用户执行此操作。</span><span class="sxs-lookup"><span data-stu-id="4bd28-148">You can do this by testing this with one user in your organization.</span></span>
  
<span data-ttu-id="4bd28-149">[设置 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet 可用于管理您的组织，包括电子邮件的其他设置。</span><span class="sxs-lookup"><span data-stu-id="4bd28-149">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="4bd28-150">如果不想向用户发送电子邮件，又该怎样做？</span><span class="sxs-lookup"><span data-stu-id="4bd28-150">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="4bd28-151">当禁用电子邮件发送给用户时，即使用户拥有分配的许可证，也不会向其发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="4bd28-151">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="4bd28-152">在此情况下，会议 ID，默认会议电话号码，以及更重要的是，将不会向用户发送其音频会议 PIN。</span><span class="sxs-lookup"><span data-stu-id="4bd28-152">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="4bd28-153">发生这种情况时，你必须通过向用户发送单独的电子邮件或呼叫他们进行通知。</span><span class="sxs-lookup"><span data-stu-id="4bd28-153">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>
  
<span data-ttu-id="4bd28-154">默认情况下将电子邮件发送给用户，但如果您想要阻止发送电子邮件的音频会议，您可以使用 Skype 业务管理中心或 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4bd28-154">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use the Skype for Business admin center or Windows PowerShell.</span></span> 
 
<span data-ttu-id="4bd28-155">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png)  **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="4bd28-155">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png)  **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="4bd28-156">在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议** > **Microsoft 网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="4bd28-156">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="4bd28-157">在**Microsoft 网桥的设置**页上，选中或清除**自动发送电子邮件发送给用户，如果其音频会议设置更改**。</span><span class="sxs-lookup"><span data-stu-id="4bd28-157">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their audio conferencing settings change**.</span></span> 
    
3. <span data-ttu-id="4bd28-158">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="4bd28-158">Click **Save**.</span></span> 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
<span data-ttu-id="4bd28-159">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="4bd28-159">**Using Windows PowerShell**</span></span>
  
1. <span data-ttu-id="4bd28-160">运行以下操作以禁用向你的用户发送所有电子邮件：</span><span class="sxs-lookup"><span data-stu-id="4bd28-160">Run the following to disable sending all of your users email:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

<span data-ttu-id="4bd28-161">[设置 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet 可用于管理您的组织，包括电子邮件的其他设置。</span><span class="sxs-lookup"><span data-stu-id="4bd28-161">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="4bd28-162">此电子邮件的其他须知事项。</span><span class="sxs-lookup"><span data-stu-id="4bd28-162">What else should you know about this email?</span></span>

- <span data-ttu-id="4bd28-163">有关如何启用和禁用自动向用户发送电子邮件的更多信息，请参阅[启用或禁用发送电子邮件时更改音频会议设置](enable-or-disable-sending-emails-when-their-settings-change.md)。</span><span class="sxs-lookup"><span data-stu-id="4bd28-163">For more on enabling and disabling automatically sending email to your users, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
    
- <span data-ttu-id="4bd28-164">有时用户会丢失其音频的信息，您需要能够它们他们的所有音频信息向他们发送。</span><span class="sxs-lookup"><span data-stu-id="4bd28-164">Sometimes users lose their audio information and you need to be able to send them all of their audio information to them.</span></span> <span data-ttu-id="4bd28-165">您可以通过业务管理中心的使用 Skype 并单击用户的音频会议属性下的**发送会议信息通过电子邮件**来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="4bd28-165">You can do this by using the Skype for Business admin center and clicking **Send conference info via email** under the audio conferencing properties for a user.</span></span> <span data-ttu-id="4bd28-166">请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。</span><span class="sxs-lookup"><span data-stu-id="4bd28-166">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span> <span data-ttu-id="4bd28-167">但是，此信息不包括音频会议 PIN。</span><span class="sxs-lookup"><span data-stu-id="4bd28-167">However, this information doesn't include the audio conferencing PIN.</span></span>
    
    <span data-ttu-id="4bd28-168">下面是将发送给用户的电子邮件的一个示例：</span><span class="sxs-lookup"><span data-stu-id="4bd28-168">Here is an example of this email that will be sent to them:</span></span>
    
     ![电话拨入式会议电子邮件](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="4bd28-170">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="4bd28-170">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="4bd28-171">默认情况下，电子邮件发件人将从 Office 365，但您可以更改电子邮件地址，并显示名称使用 Windows PowerShell 和[设置 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4bd28-171">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span>
    
- <span data-ttu-id="4bd28-p113">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="4bd28-p113">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4bd28-175">为什么您需要使用 Office 365 PowerShell 中</span><span class="sxs-lookup"><span data-stu-id="4bd28-175">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="4bd28-176">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="4bd28-176">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="4bd28-177">Windows PowerShell 具有很多好处中快速、 简便起见和生产力通过只使用 Office 365 管理中心中的，如时要进行设置更改多个用户一次。</span><span class="sxs-lookup"><span data-stu-id="4bd28-177">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="4bd28-178">请在以下主题中了解这些优点：</span><span class="sxs-lookup"><span data-stu-id="4bd28-178">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="4bd28-179">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="4bd28-179">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="4bd28-180">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4bd28-180">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="4bd28-181">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="4bd28-181">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="4bd28-p115">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="4bd28-p115">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4bd28-184">相关主题</span><span class="sxs-lookup"><span data-stu-id="4bd28-184">Related topics</span></span>

[<span data-ttu-id="4bd28-185">启用或禁用发送电子邮件时更改音频会议设置</span><span class="sxs-lookup"><span data-stu-id="4bd28-185">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[<span data-ttu-id="4bd28-186">对其音频会议信息的用户发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="4bd28-186">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)
