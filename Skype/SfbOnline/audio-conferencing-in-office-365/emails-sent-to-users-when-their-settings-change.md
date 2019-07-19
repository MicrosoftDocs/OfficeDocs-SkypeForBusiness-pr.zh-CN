---
title: 在 Skype for Business Online 中其设置发生更改时发送给用户的电子邮件
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
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
description: '了解当 Skype for business Online 中的电话拨入式会议设置更改时, 通过电子邮件自动向用户发送哪些信息。 '
ms.openlocfilehash: 4f1916778985012754cc436f37e76f0097dd49e9
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792432"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-skype-for-business-online"></a><span data-ttu-id="1b492-103">在 Skype for Business Online 中其设置发生更改时发送给用户的电子邮件</span><span class="sxs-lookup"><span data-stu-id="1b492-103">Emails sent to users when their settings change in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="1b492-104">如果要查找 Microsoft 团队中的自动电子邮件信息, 请参阅在[Microsoft 团队中的设置更改时发送给用户的电子邮件](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="1b492-104">If you're looking for automatic email information in Microsoft Teams, see [Emails sent to users when their settings change in Microsoft Teams](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="1b492-105">电子邮件将自动发送给已使用 Microsoft 作为音频会议提供商[的音频会议的](set-up-audio-conferencing.md)用户。</span><span class="sxs-lookup"><span data-stu-id="1b492-105">Emails will be automatically sent to users who are [enabled for Audio Conferencing](set-up-audio-conferencing.md) using Microsoft as the audio conferencing provider.</span></span>
  
<span data-ttu-id="1b492-106">默认情况下, 将向已启用音频会议的用户发送四种类型的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1b492-106">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="1b492-107">但是，如果要限制向用户发送的电子邮件数，你可以将其关闭。</span><span class="sxs-lookup"><span data-stu-id="1b492-107">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="1b492-108">在以下情况中, Office 365 中的音频会议会将电子邮件发送给用户的电子邮件:</span><span class="sxs-lookup"><span data-stu-id="1b492-108">Audio Conferencing in Office 365 will send email to your users' email when:</span></span>
  
- <span data-ttu-id="1b492-109">**向 Microsoft 分配音频会议许可证或将音频会议提供商更改为 Microsoft 时。**</span><span class="sxs-lookup"><span data-stu-id="1b492-109">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>
    
     <span data-ttu-id="1b492-110">此电子邮件包括会议 ID、会议的默认会议电话号码、用户的音频会议 PIN 以及使用 Skype for Business Online 会议更新工具 (用于更新现有会议) 的说明和链接user.</span><span class="sxs-lookup"><span data-stu-id="1b492-110">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="1b492-111">请参阅[分配 Skype for business 许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)或[指定 Microsoft 作为音频会议提供商](assign-microsoft-as-the-audio-conferencing-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="1b492-111">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1b492-112">[!注释] 如果你的组织已启用动态会议 ID，用户安排的所有会议将具有唯一的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="1b492-112">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="1b492-113">您可以[在您的组织中设置音频会议动态 id](using-audio-conferencing-dynamic-ids-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="1b492-113">You can set up [Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
    <span data-ttu-id="1b492-114">下面是此电子邮件的一个示例：</span><span class="sxs-lookup"><span data-stu-id="1b492-114">Here is an example of this email:</span></span>
    
     ![Skype for Business 验证许可证](../images/audio-conferencing-user-enabled.png)
  
    <span data-ttu-id="1b492-116">你可以通过参阅 [Skype for Business 附加许可](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)了解有关 Skype for Business 许可的更多信息。</span><span class="sxs-lookup"><span data-stu-id="1b492-116">You can find out more about Skype for Business licensing by seeing [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
- <span data-ttu-id="1b492-117">**会议 ID 或用户默认会议电话号码更改。**</span><span class="sxs-lookup"><span data-stu-id="1b492-117">**The conference ID or default conference phone number of a user changes.**</span></span>
    
    <span data-ttu-id="1b492-118">此电子邮件包括会议 ID、默认会议电话号码以及使用 Skype for Business Online 会议更新工具为用户更新现有会议的说明和链接。</span><span class="sxs-lookup"><span data-stu-id="1b492-118">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="1b492-119">但此电子邮件不包含用户的音频会议 PIN。</span><span class="sxs-lookup"><span data-stu-id="1b492-119">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="1b492-120">请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="1b492-120">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1b492-121">[!注释] 如果你的组织已启用动态会议 ID，用户安排的所有会议将具有唯一的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="1b492-121">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="1b492-122">您可以[在您的组织中设置音频会议动态 id](using-audio-conferencing-dynamic-ids-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="1b492-122">You can set up [Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
    <span data-ttu-id="1b492-123">下面是此电子邮件的一个示例：</span><span class="sxs-lookup"><span data-stu-id="1b492-123">Here is an example of this email:</span></span>
    
     ![电话拨入式会议信息已更改。](../images/audio-conferencing-info-change.png)
  
- <span data-ttu-id="1b492-125">**用户的音频会议 PIN 将重置。**</span><span class="sxs-lookup"><span data-stu-id="1b492-125">**The audio conferencing PIN of a user is reset.**</span></span>
    
    <span data-ttu-id="1b492-126">此电子邮件包含组织者的音频会议 PIN、现有会议 ID 和用户的默认会议电话号码。</span><span class="sxs-lookup"><span data-stu-id="1b492-126">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="1b492-127">请参阅[重置音频会议 PIN 码](reset-the-audio-conferencing-pin.md)。</span><span class="sxs-lookup"><span data-stu-id="1b492-127">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1b492-128">[!注释] 如果你的组织已启用动态会议 ID，用户安排的所有会议将具有唯一的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="1b492-128">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="1b492-129">您可以[在您的组织中设置音频会议动态 id](using-audio-conferencing-dynamic-ids-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="1b492-129">You can set up [Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
    <span data-ttu-id="1b492-130">下面是此电子邮件的一个示例：</span><span class="sxs-lookup"><span data-stu-id="1b492-130">Here is an example of this email:</span></span>
    
     ![电话拨入式会议 PIN 已更改。](../images/audio-conferencing-pin-has-changed.png)
  
- <span data-ttu-id="1b492-132">**当音频会议提供商从 Microsoft 更改为其他提供商或 "无" 时, 将删除用户许可证。**</span><span class="sxs-lookup"><span data-stu-id="1b492-132">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>
    
    <span data-ttu-id="1b492-133">如果从用户删除**音频会议**许可证或将用户的音频会议提供商从 Microsoft 更改为第三方音频会议提供商或将提供商设置为 "**无**", 则会出现此情况。</span><span class="sxs-lookup"><span data-stu-id="1b492-133">This happens when the **Audio Conferencing** license is removed from a user or when changing the audio conferencing provider of a user from Microsoft to a third-party audio conferencing provider or when setting the provider to **None**.</span></span> <span data-ttu-id="1b492-134">此电子邮件包含用户使用 Skype for Business Online 会议更新工具删除音频会议特定信息 (如默认会议电话号码或会议 ID) 的说明和信息。</span><span class="sxs-lookup"><span data-stu-id="1b492-134">This email contains the instructions and information for the user to use the Skype for Business Online Meeting Update Tool to remove audio conferencing specific information, such as the default conference phone number or conference ID.</span></span>
    
    <span data-ttu-id="1b492-135">请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="1b492-135">See [Assign or remove licenses for Office 365 for business](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
    
    <span data-ttu-id="1b492-136">下面是此电子邮件的一个示例：</span><span class="sxs-lookup"><span data-stu-id="1b492-136">Here is an example of this email:</span></span>
    
     ![电话拨入式会议已关闭。](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="1b492-138">更改发送给用户的电子邮件</span><span class="sxs-lookup"><span data-stu-id="1b492-138">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="1b492-139">您可以对自动发送给用户的电子邮件进行更改, 包括 "*发件*人联系人" 信息中包含的电子邮件地址和显示名称。</span><span class="sxs-lookup"><span data-stu-id="1b492-139">You can make changes to the email that is automatically sent to users including the email address and the display name that is included in the *From* contact information.</span></span> <span data-ttu-id="1b492-140">默认情况下, 电子邮件的发件人将来自 Office 365, 但你可以使用 Windows PowerShell 和[set-csonlinedialinconferencingtenantsettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet 更改电子邮件地址和显示名称。</span><span class="sxs-lookup"><span data-stu-id="1b492-140">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span> <span data-ttu-id="1b492-141">若要对向用户发送电子邮件的电子邮件地址进行更改, 必须执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="1b492-141">To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="1b492-142">在  _SendEmailFromAddress_ 参数中输入电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="1b492-142">Enter the email address in the  _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="1b492-143">在  _SendEmailFromDisplayName_ 参数中输入电子邮件的显示名称。</span><span class="sxs-lookup"><span data-stu-id="1b492-143">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="1b492-144">将_SendEmailOverride_参数设置为_True_。</span><span class="sxs-lookup"><span data-stu-id="1b492-144">Set the  _SendEmailOverride_ parameter to  _True_.</span></span>
    
<span data-ttu-id="1b492-145">您可以通过运行以下内容来更改发送给用户的电子邮件, 例如电子邮件的发件人电子邮件地址和电子邮件的显示名称:</span><span class="sxs-lookup"><span data-stu-id="1b492-145">You can make changes to the email sent to users, such as the email address that the email is sent from and the display name for the email, by running:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  <span data-ttu-id="1b492-146">如果要更改电子邮件地址信息, 你需要确保你的环境的入站电子邮件策略允许来自自定义指定发件人地址的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1b492-146">If you want to change the email address information, you need to make sure that the inbound email policies of your environment allow emails that come from the custom specified from address.</span></span> <span data-ttu-id="1b492-147">如果您决定覆盖 "*发件*联系人" 信息, 应验证电子邮件是否已正确发送给用户。</span><span class="sxs-lookup"><span data-stu-id="1b492-147">If you decide to override the *From* contact information, you should verify that the emails are correctly sent to users.</span></span> <span data-ttu-id="1b492-148">你可以通过在你的组织中的一个用户进行测试来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="1b492-148">You can do this by testing this with one user in your organization.</span></span>
  
<span data-ttu-id="1b492-149">你可以使用[set-csonlinedialinconferencingtenantsettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet 管理你的组织的其他设置, 包括电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1b492-149">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="1b492-150">如果不想向用户发送电子邮件，又该怎样做？</span><span class="sxs-lookup"><span data-stu-id="1b492-150">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="1b492-151">当禁用电子邮件发送给用户时，即使用户拥有分配的许可证，也不会向其发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1b492-151">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="1b492-152">在此情况下, 会议 ID、默认会议电话号码和更重要的是, 其音频会议 PIN 不会发送给用户。</span><span class="sxs-lookup"><span data-stu-id="1b492-152">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="1b492-153">发生这种情况时，你必须通过向用户发送单独的电子邮件或呼叫他们进行通知。</span><span class="sxs-lookup"><span data-stu-id="1b492-153">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>
  
<span data-ttu-id="1b492-154">默认情况下, 将向你的用户发送电子邮件, 但如果你希望阻止他们接收用于音频会议的电子邮件, 则可以使用 Skype for Business 管理中心或 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="1b492-154">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use the Skype for Business admin center or Windows PowerShell.</span></span> 
 
<span data-ttu-id="1b492-155">![](../images/sfb-logo-30x30.png)**使用 skype for business 管理中心**显示 skype for business 徽标的图标  </span><span class="sxs-lookup"><span data-stu-id="1b492-155">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png)  **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="1b492-156">在**Skype for business 管理中心**的左侧导航中, 转到 "**音频会议** > **Microsoft 网桥设置**"。</span><span class="sxs-lookup"><span data-stu-id="1b492-156">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="1b492-157">在 " **Microsoft 网桥设置**" 页面上, 选择或清除 "**如果其音频会议设置发生更改, 则自动向用户发送电子邮件**"。</span><span class="sxs-lookup"><span data-stu-id="1b492-157">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their audio conferencing settings change**.</span></span> 
    
3. <span data-ttu-id="1b492-158">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="1b492-158">Click **Save**.</span></span> 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
<span data-ttu-id="1b492-159">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="1b492-159">**Using Windows PowerShell**</span></span>
  
1. <span data-ttu-id="1b492-160">运行以下操作以禁用向你的用户发送所有电子邮件：</span><span class="sxs-lookup"><span data-stu-id="1b492-160">Run the following to disable sending all of your users email:</span></span>
    
   ```
   Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $false
   ```

<span data-ttu-id="1b492-161">你可以使用[set-csonlinedialinconferencingtenantsettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet 管理你的组织的其他设置, 包括电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1b492-161">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="1b492-162">此电子邮件的其他须知事项。</span><span class="sxs-lookup"><span data-stu-id="1b492-162">What else should you know about this email?</span></span>

- <span data-ttu-id="1b492-163">有关如何启用和禁用自动向用户发送电子邮件的更多信息，请参阅[启用或禁用发送电子邮件时更改音频会议设置](enable-or-disable-sending-emails-when-their-settings-change.md)。</span><span class="sxs-lookup"><span data-stu-id="1b492-163">For more on enabling and disabling automatically sending email to your users, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
    
- <span data-ttu-id="1b492-164">有时, 用户会丢失其音频信息, 您需要能够将他们的所有音频信息发送给他们。</span><span class="sxs-lookup"><span data-stu-id="1b492-164">Sometimes users lose their audio information and you need to be able to send them all of their audio information to them.</span></span> <span data-ttu-id="1b492-165">你可以通过使用 Skype for Business 管理中心, 然后单击用户的音频会议属性下的 "**通过电子邮件发送会议信息**" 来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="1b492-165">You can do this by using the Skype for Business admin center and clicking **Send conference info via email** under the audio conferencing properties for a user.</span></span> <span data-ttu-id="1b492-166">请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。</span><span class="sxs-lookup"><span data-stu-id="1b492-166">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span> <span data-ttu-id="1b492-167">但是, 此信息不包括音频会议 PIN 码。</span><span class="sxs-lookup"><span data-stu-id="1b492-167">However, this information doesn't include the audio conferencing PIN.</span></span>
    
    <span data-ttu-id="1b492-168">下面是将发送给用户的电子邮件的一个示例：</span><span class="sxs-lookup"><span data-stu-id="1b492-168">Here is an example of this email that will be sent to them:</span></span>
    
     ![电话拨入式会议电子邮件](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="1b492-170">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="1b492-170">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="1b492-171">默认情况下, 电子邮件的发件人将来自 Office 365, 但你可以使用 Windows PowerShell 和[set-csonlinedialinconferencingtenantsettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet 更改电子邮件地址和显示名称。</span><span class="sxs-lookup"><span data-stu-id="1b492-171">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span>
    
- <span data-ttu-id="1b492-p113">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="1b492-p113">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="1b492-175">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b492-175">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="1b492-176">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="1b492-176">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="1b492-177">Windows PowerShell 在速度、简洁性和效率方面具有许多优势, 仅限于使用 Microsoft 365 管理中心, 例如当你为多个用户同时进行设置更改时。</span><span class="sxs-lookup"><span data-stu-id="1b492-177">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="1b492-178">请在以下主题中了解这些优点：</span><span class="sxs-lookup"><span data-stu-id="1b492-178">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="1b492-179">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="1b492-179">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="1b492-180">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1b492-180">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="1b492-181">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="1b492-181">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="1b492-p115">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="1b492-p115">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="1b492-184">相关主题</span><span class="sxs-lookup"><span data-stu-id="1b492-184">Related topics</span></span>

[<span data-ttu-id="1b492-185">启用或禁用发送电子邮件时更改音频会议设置</span><span class="sxs-lookup"><span data-stu-id="1b492-185">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[<span data-ttu-id="1b492-186">对其音频会议信息的用户发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="1b492-186">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)
