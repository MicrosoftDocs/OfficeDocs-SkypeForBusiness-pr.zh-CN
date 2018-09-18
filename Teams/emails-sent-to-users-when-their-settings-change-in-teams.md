---
title: 在 Microsoft Teams 中当用户设置更改时向其发送的电子邮件
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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解在 Microsoft Teams 中当用户的电话拨入式会议设置更改时自动通过电子邮件向其发送的信息。 '
ms.openlocfilehash: f351f7a1107c3f52ddc2c9f60b7cd79feb31388c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23890059"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a><span data-ttu-id="c8ab3-103">在 Microsoft Teams 中当用户设置更改时向其发送的电子邮件</span><span class="sxs-lookup"><span data-stu-id="c8ab3-103">Emails sent to users when their settings change</span></span>

<span data-ttu-id="c8ab3-104">当使用 Microsoft 作为音频会议提供商时，会自动向[启用了音频会议](/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)的用户发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="c8ab3-104">Emails will be automatically sent to users who are [Set up Audio Conferencing for Skype for Business and Microsoft Teams](/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing) using Microsoft as the dial-in conferencing provider.</span></span>
  
<span data-ttu-id="c8ab3-105">默认情况下，对于启用了音频会议的用户，向其发送的电子邮件共有四种类型。</span><span class="sxs-lookup"><span data-stu-id="c8ab3-105">By default, there are four types of email that will be sent to your users who are enabled for dial-in conferencing.</span></span> <span data-ttu-id="c8ab3-106">但是，如果你要限制向用户发送的电子邮件数，你可以将其关闭。</span><span class="sxs-lookup"><span data-stu-id="c8ab3-106">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="c8ab3-107">在下列情况下，Office 365 中的音频会议将向用户发送电子邮件：</span><span class="sxs-lookup"><span data-stu-id="c8ab3-107">Audio Conferencing in Office 365 will send email to your users' email when:</span></span>
  
- <span data-ttu-id="c8ab3-108">**为用户分配了音频会议许可证时，或者你将音频会议提供商更改为 Microsoft 时。**</span><span class="sxs-lookup"><span data-stu-id="c8ab3-108">**A Skype for Business PSTN Conferencing license is assigned to them or when you are changing the dial-in conferencing provider to Microsoft.**</span></span>
    
     <span data-ttu-id="c8ab3-109">此电子邮件包括会议 ID、默认的会议电话号码、用户的音频会议 PIN 以及使用 Skype for Business Online 会议更新工具为用户更新现有会议的说明和链接。</span><span class="sxs-lookup"><span data-stu-id="c8ab3-109">This email includes the conference ID, the default conference phone number for the meetings, the dial-in conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="c8ab3-110">请参阅[分配 Skype for Business 和 Microsoft Teams 许可证](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)或[将 Microsoft 指定为音频会议提供商](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。</span><span class="sxs-lookup"><span data-stu-id="c8ab3-110">See [Assign Skype for Business and Microsoft Teams licenses](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft as the audio conferencing provider](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c8ab3-111">如果贵组织已启用动态会议 ID，则用户安排的所有会议都将具有唯一的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="c8ab3-111">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="c8ab3-112">你可以[在贵组织中设置音频会议动态 ID](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user)。</span><span class="sxs-lookup"><span data-stu-id="c8ab3-112">You can set up [Using dial-in conferencing dynamic IDs in your organization](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user).</span></span> 
  
    <span data-ttu-id="c8ab3-113">下面是此电子邮件示例：</span><span class="sxs-lookup"><span data-stu-id="c8ab3-113">Here is an example of this email:</span></span>
    
     ![Skype for Business 验证许可证](media/audio-conferencing-user-enabled.png)
  
    <span data-ttu-id="c8ab3-115">有关许可的详细信息，请参阅 [Skype for Business 和 Microsoft Teams 加载项许可](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)。</span><span class="sxs-lookup"><span data-stu-id="c8ab3-115">You can find out more about Skype for Business licensing by seeing [Skype for Business add-on licensing](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span></span>
    
- <span data-ttu-id="c8ab3-116">**更改了用户的会议 ID 或默认会议电话号码。**</span><span class="sxs-lookup"><span data-stu-id="c8ab3-116">**The conference ID or default conference phone number of a user changes.**</span></span>
    
    <span data-ttu-id="c8ab3-117">此电子邮件包括会议 ID、默认会议电话号码以及使用 Skype for Business Online 会议更新工具为用户更新现有会议的说明和链接。</span><span class="sxs-lookup"><span data-stu-id="c8ab3-117">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="c8ab3-118">但此电子邮件不包括用户的音频会议 PIN。</span><span class="sxs-lookup"><span data-stu-id="c8ab3-118">But this email doesn't include the user's dial-in conferencing PIN.</span></span> <span data-ttu-id="c8ab3-119">请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="c8ab3-119">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>
  
    <span data-ttu-id="c8ab3-120">下面是此电子邮件示例：</span><span class="sxs-lookup"><span data-stu-id="c8ab3-120">Here is an example of this email:</span></span>
    
     ![电话拨入式会议信息已更改。](media/audio-conferencing-info-change.png)
  
- <span data-ttu-id="c8ab3-122">**重置了用户的音频会议 PIN。**</span><span class="sxs-lookup"><span data-stu-id="c8ab3-122">**The dial-in conferencing PIN of a user is reset.**</span></span>
    
    <span data-ttu-id="c8ab3-123">此电子邮件包含组织者的音频会议 PIN、用户的现有会议 ID 和默认会议电话号码。</span><span class="sxs-lookup"><span data-stu-id="c8ab3-123">This email contains the organizer's dial-in conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="c8ab3-124">请参阅[重置音频会议 PIN](reset-the-audio-conferencing-pin-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="c8ab3-124">See [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
  
    <span data-ttu-id="c8ab3-125">下面是此电子邮件示例：</span><span class="sxs-lookup"><span data-stu-id="c8ab3-125">Here is an example of this email:</span></span>
    
     ![电话拨入式会议 PIN 已更改。](media/audio-conferencing-pin-has-changed.png)
  
- <span data-ttu-id="c8ab3-127">**用户的许可证被删除，或者音频会议提供商从 Microsoft 更改为其他提供商或“无”。**</span><span class="sxs-lookup"><span data-stu-id="c8ab3-127">**A user's license is removed or when their dial-in conferencing provider changes from Microsoft to other provider or None**</span></span>
    
    <span data-ttu-id="c8ab3-128">在删除了用户的**音频会议**许可证，或者将用户的音频会议提供商从 Microsoft 更改为第三方音频会议提供商，或将提供商设置为“**无**”时，会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="c8ab3-128">This happens when the **Skype for Business PSTN Conferencing** license is removed from a user or when changing the dial-in conferencing provider of a user from Microsoft to a third-party audio conferencing provider or when setting the provider to **None**.</span></span> <span data-ttu-id="c8ab3-129">此电子邮件包含用户使用 Skype for Business Online 会议更新工具删除音频会议特定信息（例如默认会议电话号码或会议 ID）的说明和信息。</span><span class="sxs-lookup"><span data-stu-id="c8ab3-129">This email contains the instructions and information for the user to use the Skype for Business Online Meeting Update Tool to remove dial-in conferencing specific information, such as the default conference phone number or conference ID.</span></span>
    
    <span data-ttu-id="c8ab3-130">请参阅[分配或删除 Office 365 商业版许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="c8ab3-130">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
    
    <span data-ttu-id="c8ab3-131">下面是此电子邮件示例：</span><span class="sxs-lookup"><span data-stu-id="c8ab3-131">Here is an example of this email:</span></span>
    
     ![电话拨入式会议已关闭。](media/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="c8ab3-133">更改向用户发送的电子邮件</span><span class="sxs-lookup"><span data-stu-id="c8ab3-133">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="c8ab3-134">你可以更改自动向用户发送的电子邮件，包括电子邮件地址和包含在“*发件人*”联系信息中的显示名称。</span><span class="sxs-lookup"><span data-stu-id="c8ab3-134">You can make changes to the email that is automatically sent to your users including the email address and the display name that is included in the  *From*  contact information.</span></span> <span data-ttu-id="c8ab3-135">默认情况下，这些电子邮件的发件人将显示为来自 Office 365，但你可以使用 Windows PowerShell 更改电子邮件地址和显示名称。</span><span class="sxs-lookup"><span data-stu-id="c8ab3-135">By default, the sender of the emails will be from Office 365 but you can change the email address and display name using Windows PowerShell and theSet-CsOnlineDialInConferencingTenantSettings cmdlet.</span></span> <span data-ttu-id="c8ab3-136">有关详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。</span><span class="sxs-lookup"><span data-stu-id="c8ab3-136">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="c8ab3-137">如果不希望向用户发送电子邮件该怎么办？</span><span class="sxs-lookup"><span data-stu-id="c8ab3-137">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="c8ab3-138">禁用向用户发送电子邮件时，即使为用户分配了许可证，也不会发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="c8ab3-138">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="c8ab3-139">在此情况下，不会向用户发送会议 ID、默认会议电话号码，以及更重要的是，他们的音频会议 PIN。</span><span class="sxs-lookup"><span data-stu-id="c8ab3-139">If this is the case, the conference ID, default conferencing phone number and more importantly, their dial-in conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="c8ab3-140">发生这种情况时，你必须通过向用户发送单独的电子邮件或给他们打电话进行通知。</span><span class="sxs-lookup"><span data-stu-id="c8ab3-140">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>
  
<span data-ttu-id="c8ab3-141">默认情况下，将向你的用户发送电子邮件，但如果你不希望他们收到音频会议的电子邮件，可使用 Microsoft Teams 或 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c8ab3-141">By default, emails will be sent to your users, but if you want to prevent them from receiving email for dial-in conferencing use can use the Skype for Business admin center or Windows PowerShell.</span></span> 

<span data-ttu-id="c8ab3-142">![teams-logo-30x30.png](media/teams-logo-30x30.png) **使用 Microsoft Teams 和 Skype for Business 管理中心：**</span><span class="sxs-lookup"><span data-stu-id="c8ab3-142">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center:**</span></span>

1. <span data-ttu-id="c8ab3-143">在左侧导航中，转到“**会议**” > “**会议网桥**”。</span><span class="sxs-lookup"><span data-stu-id="c8ab3-143">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="c8ab3-144">在“**会议网桥**”页面顶部，单击“**网桥设置**”。</span><span class="sxs-lookup"><span data-stu-id="c8ab3-144">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="c8ab3-145">在“**网桥设置**”窗格中，启用或禁用“**当用户的拨入设置更改时自动向用户发送电子邮件**”。</span><span class="sxs-lookup"><span data-stu-id="c8ab3-145">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="c8ab3-146">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="c8ab3-146">Click **Save**.</span></span>
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
<span data-ttu-id="c8ab3-147">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c8ab3-147">\*\*\*\* Using Windows PowerShell</span></span>
  
<span data-ttu-id="c8ab3-148">有关详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。</span><span class="sxs-lookup"><span data-stu-id="c8ab3-148">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="c8ab3-149">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="c8ab3-149">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="c8ab3-150">默认情况下，这些电子邮件的发件人将显示为来自 Office 365，但你可以使用 Windows PowerShell 更改电子邮件地址和显示名称。</span><span class="sxs-lookup"><span data-stu-id="c8ab3-150">By default, the sender of the emails will be from Office 365 but you can change the email address and display name using Windows PowerShell and theSet-CsOnlineDialInConferencingTenantSettings cmdlet.</span></span> 

<span data-ttu-id="c8ab3-p109">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="c8ab3-p109">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c8ab3-154">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="c8ab3-154">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="c8ab3-155">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="c8ab3-155">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="c8ab3-156">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="c8ab3-156">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
  
## <a name="related-topics"></a><span data-ttu-id="c8ab3-157">相关主题</span><span class="sxs-lookup"><span data-stu-id="c8ab3-157">Related topics</span></span>

[<span data-ttu-id="c8ab3-158">启用或禁用在音频会议设置更改时发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="c8ab3-158">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)
  
[<span data-ttu-id="c8ab3-159">对其音频会议信息的用户发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="c8ab3-159">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
