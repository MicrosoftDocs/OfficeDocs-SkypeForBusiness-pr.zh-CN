---
title: 在 Microsoft Teams 中当用户设置更改时向其发送的电子邮件
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解在 Microsoft Teams 中当用户的电话拨入式会议设置更改时自动通过电子邮件向其发送的信息。 '
ms.openlocfilehash: b1bd7764f7780267d9f2a98a3203f49d2c0e938e
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016162"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a><span data-ttu-id="87f58-103">在 Microsoft Teams 中当用户设置更改时向其发送的电子邮件</span><span class="sxs-lookup"><span data-stu-id="87f58-103">Emails sent to users when their settings change in Microsoft Teams</span></span>

<span data-ttu-id="87f58-104">当使用 Microsoft 作为音频会议提供商时，会自动向[启用了音频会议](/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)的用户发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="87f58-104">Emails will be automatically sent to users who are [enabled for Audio Conferencing](/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing) using Microsoft as the audio conferencing provider.</span></span>
  
<span data-ttu-id="87f58-105">默认情况下，有四种类型的电子邮件将发送到您的用户启用了音频会议。</span><span class="sxs-lookup"><span data-stu-id="87f58-105">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="87f58-106">但是，如果要限制向用户发送的电子邮件数，你可以将其关闭。</span><span class="sxs-lookup"><span data-stu-id="87f58-106">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="87f58-107">Office 365 中的音频会议将向用户发送电子邮件时的电子邮件：</span><span class="sxs-lookup"><span data-stu-id="87f58-107">Audio Conferencing in Office 365 will send email to your users' email when:</span></span>
  
- <span data-ttu-id="87f58-108">**为用户分配了音频会议许可证时，或者你将音频会议提供商更改为 Microsoft 时。**</span><span class="sxs-lookup"><span data-stu-id="87f58-108">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>
    
     <span data-ttu-id="87f58-109">此电子邮件包括会议 ID，会议，音频会议的用户和链接说明要用于业务在线会议更新工具，用来更新现有会议的 Skype 的 PIN 的默认会议电话号码用户。</span><span class="sxs-lookup"><span data-stu-id="87f58-109">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="87f58-110">请参阅[业务和 Microsoft 团队许可证分配 Skype](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)或[分配 Microsoft 作为音频会议提供商](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。</span><span class="sxs-lookup"><span data-stu-id="87f58-110">See [Assign Skype for Business and Microsoft Teams licenses](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft as the audio conferencing provider](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="87f58-111">[!注释] 如果你的组织已启用动态会议 ID，用户安排的所有会议将具有唯一的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="87f58-111">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="87f58-112">您可以设置[您的组织中的音频会议动态 Id](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user)。</span><span class="sxs-lookup"><span data-stu-id="87f58-112">You can set up [Audio Conferencing dynamic IDs in your organization](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user).</span></span> 
  
    <span data-ttu-id="87f58-113">下面是此电子邮件示例：</span><span class="sxs-lookup"><span data-stu-id="87f58-113">Here is an example of this email:</span></span>
    
     ![Skype for Business 验证许可证](media/audio-conferencing-user-enabled.png)
  
    <span data-ttu-id="87f58-115">有关许可的详细信息，请参阅 [Skype for Business 和 Microsoft Teams 加载项许可](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)。</span><span class="sxs-lookup"><span data-stu-id="87f58-115">You can find out more about licensing by seeing [Skype for Business and Microsoft Teams add-on licensing](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span></span>
    
- <span data-ttu-id="87f58-116">**更改了用户的会议 ID 或默认会议电话号码。**</span><span class="sxs-lookup"><span data-stu-id="87f58-116">**The conference ID or default conference phone number of a user changes.**</span></span>
    
    <span data-ttu-id="87f58-117">此电子邮件包括会议 ID、默认会议电话号码以及使用 Skype for Business Online 会议更新工具为用户更新现有会议的说明和链接。</span><span class="sxs-lookup"><span data-stu-id="87f58-117">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="87f58-118">但此电子邮件不包括用户的音频会议 PIN。</span><span class="sxs-lookup"><span data-stu-id="87f58-118">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="87f58-119">请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="87f58-119">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>
  
    <span data-ttu-id="87f58-120">下面是此电子邮件示例：</span><span class="sxs-lookup"><span data-stu-id="87f58-120">Here is an example of this email:</span></span>
    
     ![电话拨入式会议信息已更改。](media/audio-conferencing-info-change.png)
  
- <span data-ttu-id="87f58-122">**重置了用户的音频会议 PIN。**</span><span class="sxs-lookup"><span data-stu-id="87f58-122">**The audio conferencing PIN of a user is reset.**</span></span>
    
    <span data-ttu-id="87f58-123">此电子邮件包含组织者的音频会议 PIN、 现有会议 ID 和用户的默认会议电话号码。</span><span class="sxs-lookup"><span data-stu-id="87f58-123">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="87f58-124">请参阅[重置 PIN 的音频会议](reset-the-audio-conferencing-pin-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="87f58-124">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
  
    <span data-ttu-id="87f58-125">下面是此电子邮件示例：</span><span class="sxs-lookup"><span data-stu-id="87f58-125">Here is an example of this email:</span></span>
    
     ![电话拨入式会议 PIN 已更改。](media/audio-conferencing-pin-has-changed.png)
  
- <span data-ttu-id="87f58-127">**用户的许可证被删除，或者音频会议提供商从 Microsoft 更改为其他提供商或“无”。**</span><span class="sxs-lookup"><span data-stu-id="87f58-127">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>
    
    <span data-ttu-id="87f58-128">**音频会议**许可证时将删除来自用户或从 Microsoft 更改用户的音频会议提供商，为第三方音频会议提供商时或设置为**无**的提供程序时，将发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="87f58-128">This happens when the **Audio Conferencing** license is removed from a user or when changing the audio conferencing provider of a user from Microsoft to a third-party audio conferencing provider or when setting the provider to **None**.</span></span> <span data-ttu-id="87f58-129">此电子邮件包含说明和信息的用户使用的业务联机会议更新工具 Skype 删除音频会议的特定信息，例如默认会议电话号码或会议 id。</span><span class="sxs-lookup"><span data-stu-id="87f58-129">This email contains the instructions and information for the user to use the Skype for Business Online Meeting Update Tool to remove audio conferencing specific information, such as the default conference phone number or conference ID.</span></span>
    
    <span data-ttu-id="87f58-130">请参阅[分配或删除 Office 365 商业版许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="87f58-130">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
    
    <span data-ttu-id="87f58-131">下面是此电子邮件示例：</span><span class="sxs-lookup"><span data-stu-id="87f58-131">Here is an example of this email:</span></span>
    
     ![电话拨入式会议已关闭。](media/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="87f58-133">更改向用户发送的电子邮件</span><span class="sxs-lookup"><span data-stu-id="87f58-133">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="87f58-134">您可以对会自动向用户的电子邮件地址和*从*联系人信息中包括的显示名称包括发送的电子邮件进行更改。</span><span class="sxs-lookup"><span data-stu-id="87f58-134">You can make changes to the email that is automatically sent to users including the email address and the display name that is included in the *From* contact information.</span></span> <span data-ttu-id="87f58-135">默认情况下，发件人的电子邮件将从 Office 365 中，但您可以更改的电子邮件地址，并且可以显示使用 Windows PowerShell 的名称。</span><span class="sxs-lookup"><span data-stu-id="87f58-135">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell.</span></span> <span data-ttu-id="87f58-136">请参阅[Microsoft 团队 PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)（英文） 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="87f58-136">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="87f58-137">如果不希望向用户发送电子邮件该怎么办？</span><span class="sxs-lookup"><span data-stu-id="87f58-137">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="87f58-138">当禁用电子邮件发送给用户时，即使用户拥有分配的许可证，也不会向其发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="87f58-138">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="87f58-139">在此情况下，会议 ID，默认会议电话号码，以及更重要的是，将不会向用户发送其音频会议 PIN。</span><span class="sxs-lookup"><span data-stu-id="87f58-139">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="87f58-140">发生这种情况时，你必须通过向用户发送单独的电子邮件或呼叫他们进行通知。</span><span class="sxs-lookup"><span data-stu-id="87f58-140">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>
  
<span data-ttu-id="87f58-141">默认情况下，将向你的用户发送电子邮件，但如果你不希望他们收到音频会议的电子邮件，可使用 Microsoft Teams 或 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="87f58-141">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use Microsoft Teams or Windows PowerShell.</span></span> 

<span data-ttu-id="87f58-142">![teams-logo-30x30.png](media/teams-logo-30x30.png) **使用 Microsoft Teams 和 Skype for Business 管理中心：**</span><span class="sxs-lookup"><span data-stu-id="87f58-142">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="87f58-143">在左侧导航中，转到“**会议**” > “**会议网桥**”。</span><span class="sxs-lookup"><span data-stu-id="87f58-143">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="87f58-144">在“**会议网桥**”页面顶部，单击“**网桥设置**”。</span><span class="sxs-lookup"><span data-stu-id="87f58-144">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="87f58-145">在“**网桥设置**”窗格中，启用或禁用“**当用户的拨入设置更改时自动向用户发送电子邮件**”。</span><span class="sxs-lookup"><span data-stu-id="87f58-145">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="87f58-146">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="87f58-146">Click **Save**.</span></span>
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
<span data-ttu-id="87f58-147">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="87f58-147">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="87f58-148">有关详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。</span><span class="sxs-lookup"><span data-stu-id="87f58-148">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="87f58-149">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="87f58-149">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="87f58-150">默认情况下，这些电子邮件的发件人将显示为来自 Office 365，但你可以使用 Windows PowerShell 更改电子邮件地址和显示名称。</span><span class="sxs-lookup"><span data-stu-id="87f58-150">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell.</span></span> 

<span data-ttu-id="87f58-p109">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="87f58-p109">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="87f58-154">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="87f58-154">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="87f58-155">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="87f58-155">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="87f58-156">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="87f58-156">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
  
## <a name="related-topics"></a><span data-ttu-id="87f58-157">相关主题</span><span class="sxs-lookup"><span data-stu-id="87f58-157">Related topics</span></span>

[<span data-ttu-id="87f58-158">启用或禁用在音频会议设置更改时发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="87f58-158">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)
  
[<span data-ttu-id="87f58-159">对其音频会议信息的用户发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="87f58-159">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
