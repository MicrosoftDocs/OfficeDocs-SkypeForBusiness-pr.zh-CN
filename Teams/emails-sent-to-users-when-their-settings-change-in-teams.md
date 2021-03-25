---
title: 用户设置更改时向其发送的电子邮件
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
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: '了解当用户的电话拨入式会议设置在 Microsoft Teams 中更改时，哪些信息会自动通过电子邮件发送给用户。 '
ms.openlocfilehash: a9ca30e7e701afca2e42eccfaef4f3d45660cd3a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120753"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a><span data-ttu-id="3e58f-103">在 Microsoft Teams 中当用户设置更改时向其发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="3e58f-103">Emails sent to users when their settings change in Microsoft Teams</span></span>

<span data-ttu-id="3e58f-104">电子邮件将自动发送给使用 Microsoft 作为音频会议[](set-up-audio-conferencing-in-teams.md)提供商启用音频会议的用户。</span><span class="sxs-lookup"><span data-stu-id="3e58f-104">Emails will be automatically sent to users who are [enabled for Audio Conferencing](set-up-audio-conferencing-in-teams.md) using Microsoft as the audio conferencing provider.</span></span>

<span data-ttu-id="3e58f-105">默认情况下，有四种类型的电子邮件将发送给启用了音频会议的用户。</span><span class="sxs-lookup"><span data-stu-id="3e58f-105">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="3e58f-106">但是，如果要限制向用户发送的电子邮件数，你可以将其关闭。</span><span class="sxs-lookup"><span data-stu-id="3e58f-106">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="3e58f-107">Microsoft 365 或 Office 365 中的音频会议将在以下时间向用户的电子邮件发送电子邮件：</span><span class="sxs-lookup"><span data-stu-id="3e58f-107">Audio Conferencing in Microsoft 365 or Office 365 will send email to your users' email when:</span></span>

- <span data-ttu-id="3e58f-108">**音频会议许可证分配给他们，或者当你将音频会议提供商更改到 Microsoft 时。**</span><span class="sxs-lookup"><span data-stu-id="3e58f-108">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>

     <span data-ttu-id="3e58f-109">此电子邮件包括会议 ID、会议的默认会议电话号码、用户的音频会议 PIN，以及使用 Skype for Business Online 会议更新工具（用于更新用户的现有会议）的说明和链接。</span><span class="sxs-lookup"><span data-stu-id="3e58f-109">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="3e58f-110">请参阅[分配 Microsoft Teams 附加许可证或](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)[将 Microsoft 分配为音频会议提供商](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。</span><span class="sxs-lookup"><span data-stu-id="3e58f-110">See [Assign Microsoft Teams add-on licenses](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) or [Assign Microsoft as the audio conferencing provider](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

    > [!NOTE]
    > <span data-ttu-id="3e58f-111">[!注释] 如果你的组织已启用动态会议 ID，用户安排的所有会议将具有唯一的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="3e58f-111">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="3e58f-112">可以在组织中[设置音频会议动态 ID。](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user)</span><span class="sxs-lookup"><span data-stu-id="3e58f-112">You can set up [Audio Conferencing dynamic IDs in your organization](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user).</span></span> 

    <span data-ttu-id="3e58f-113">下面是此电子邮件的一个示例：</span><span class="sxs-lookup"><span data-stu-id="3e58f-113">Here is an example of this email:</span></span>

     ![Skype for Business 验证许可证](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    <span data-ttu-id="3e58f-115">若要详细了解许可，请参阅 [Microsoft Teams 附加许可](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="3e58f-115">To find out more about licensing, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

- <span data-ttu-id="3e58f-116">**会议 ID 或用户默认会议电话号码更改。**</span><span class="sxs-lookup"><span data-stu-id="3e58f-116">**The conference ID or default conference phone number of a user changes.**</span></span>

    <span data-ttu-id="3e58f-117">此电子邮件包括会议 ID、默认会议电话号码以及使用 Skype for Business Online 会议更新工具为用户更新现有会议的说明和链接。</span><span class="sxs-lookup"><span data-stu-id="3e58f-117">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="3e58f-118">但是，此电子邮件不包括用户的音频会议 PIN。</span><span class="sxs-lookup"><span data-stu-id="3e58f-118">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="3e58f-119">请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="3e58f-119">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>

    <span data-ttu-id="3e58f-120">下面是此电子邮件的一个示例：</span><span class="sxs-lookup"><span data-stu-id="3e58f-120">Here is an example of this email:</span></span>

     ![电话拨入式会议信息已更改。](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- <span data-ttu-id="3e58f-122">**重置用户的音频会议 PIN。**</span><span class="sxs-lookup"><span data-stu-id="3e58f-122">**The audio conferencing PIN of a user is reset.**</span></span>

    <span data-ttu-id="3e58f-123">此电子邮件包含组织者的音频会议 PIN、现有会议 ID 和用户的默认会议电话号码。</span><span class="sxs-lookup"><span data-stu-id="3e58f-123">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="3e58f-124">请参阅[重置音频会议 PIN。](reset-the-audio-conferencing-pin-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="3e58f-124">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
     <span data-ttu-id="3e58f-125">下面是此电子邮件的一个示例：</span><span class="sxs-lookup"><span data-stu-id="3e58f-125">Here is an example of this email:</span></span>
    
     ![电话拨入式会议 PIN 已更改。](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- <span data-ttu-id="3e58f-127">**将删除用户的许可证，或者当音频会议提供商从 Microsoft 更改到其他提供商或"无"时。**</span><span class="sxs-lookup"><span data-stu-id="3e58f-127">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>

    <span data-ttu-id="3e58f-128">从用户中删除 **音频会议许可证** 或将音频会议提供商设置为"无"时，将 **发生这种情况**。</span><span class="sxs-lookup"><span data-stu-id="3e58f-128">This happens when the **Audio Conferencing** license is removed from a user or when setting the audio conferencing provider to **None**.</span></span>

    <span data-ttu-id="3e58f-129">请参阅 [分配或删除 Microsoft 365 商业版许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="3e58f-129">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

    <span data-ttu-id="3e58f-130">下面是此电子邮件的一个示例：</span><span class="sxs-lookup"><span data-stu-id="3e58f-130">Here is an example of this email:</span></span>

     ![电话拨入式会议已关闭。](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="3e58f-132">更改发送给用户的电子邮件</span><span class="sxs-lookup"><span data-stu-id="3e58f-132">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="3e58f-133">您可以更改自动发送给用户的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="3e58f-133">You can make changes to the email that is automatically sent to users.</span></span> <span data-ttu-id="3e58f-134">默认情况下，电子邮件的发件人来自 Microsoft 365 或 Office 365，但您可以使用 显示名称 更改Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3e58f-134">By default, the sender of the emails will be from Microsoft 365 or Office 365, but you can change the display name using Windows PowerShell.</span></span> <span data-ttu-id="3e58f-135">有关详细信息， [请参阅 Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) 参考。</span><span class="sxs-lookup"><span data-stu-id="3e58f-135">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="3e58f-136">如果不想向用户发送电子邮件，又该怎样做？</span><span class="sxs-lookup"><span data-stu-id="3e58f-136">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="3e58f-137">当禁用电子邮件发送给用户时，即使用户拥有分配的许可证，也不会向其发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="3e58f-137">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="3e58f-138">在这种情况下，会议 ID、默认会议电话号码以及更重要的是，其音频会议 PIN 不会发送给用户。</span><span class="sxs-lookup"><span data-stu-id="3e58f-138">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="3e58f-139">发生这种情况时，你必须通过向用户发送单独的电子邮件或呼叫他们进行通知。</span><span class="sxs-lookup"><span data-stu-id="3e58f-139">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>

<span data-ttu-id="3e58f-140">默认情况下，电子邮件将发送给你的用户，但如果你想要阻止他们接收音频会议的电子邮件，可以使用 Microsoft Teams 或 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3e58f-140">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use Microsoft Teams or Windows PowerShell.</span></span> 

<span data-ttu-id="3e58f-141">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="3e58f-141">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="3e58f-142">在左侧导航中，转到“**会议**” > “**会议网桥**”。</span><span class="sxs-lookup"><span data-stu-id="3e58f-142">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="3e58f-143">在"会议网桥"**页面顶部**，单击"**网桥设置"。**</span><span class="sxs-lookup"><span data-stu-id="3e58f-143">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="3e58f-144">在"**网桥设置"** 窗格中，启用或禁用"如果用户的拨入 **设置更改时自动发送电子邮件"。**</span><span class="sxs-lookup"><span data-stu-id="3e58f-144">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="3e58f-145">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="3e58f-145">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="3e58f-146">**使用Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="3e58f-146">**Using Windows PowerShell**</span></span>

<span data-ttu-id="3e58f-147">有关详细信息， [请参阅 Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) 参考。</span><span class="sxs-lookup"><span data-stu-id="3e58f-147">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="3e58f-148">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="3e58f-148">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="3e58f-149">默认情况下，电子邮件的发件人来自 Microsoft 365 或 Office 365，但您可以使用 显示名称 更改Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3e58f-149">By default, the sender of the emails will be from Microsoft 365 or Office 365, but you can change the email address and display name using Windows PowerShell.</span></span> 

<span data-ttu-id="3e58f-150">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="3e58f-150">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="3e58f-151">使用Windows PowerShell，您可以使用单点管理来管理 Microsoft 365 或 Office 365，当您有多个任务需要执行时，可以简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="3e58f-151">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="3e58f-152">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="3e58f-152">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="3e58f-153">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="3e58f-153">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - <span data-ttu-id="3e58f-154">[使用 Windows PowerShell 管理 Office 365 的最佳方式](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="3e58f-154">[Best ways to manage Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

<span data-ttu-id="3e58f-155">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="3e58f-155">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="related-topics"></a><span data-ttu-id="3e58f-156">相关主题</span><span class="sxs-lookup"><span data-stu-id="3e58f-156">Related topics</span></span>

[<span data-ttu-id="3e58f-157">启用或禁用发送电子邮件时更改音频会议设置</span><span class="sxs-lookup"><span data-stu-id="3e58f-157">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[<span data-ttu-id="3e58f-158">对其音频会议信息的用户发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="3e58f-158">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)