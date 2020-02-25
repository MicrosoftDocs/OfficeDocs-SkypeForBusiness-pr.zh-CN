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
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: '了解在 Microsoft Teams 中当用户的电话拨入式会议设置更改时自动通过电子邮件向其发送的信息。 '
ms.openlocfilehash: 28dcf8e166eff4a8852dd1ad77828213dc88fd05
ms.sourcegitcommit: 73518a589db1a9883fc97827f0ddb9132995fbfa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42236862"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a><span data-ttu-id="a8f00-103">在 Microsoft Teams 中当用户设置更改时向其发送的电子邮件</span><span class="sxs-lookup"><span data-stu-id="a8f00-103">Emails sent to users when their settings change in Microsoft Teams</span></span>

<span data-ttu-id="a8f00-104">当使用 Microsoft 作为音频会议提供商时，会自动向[启用了音频会议](set-up-audio-conferencing-in-teams.md)的用户发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a8f00-104">Emails will be automatically sent to users who are [enabled for Audio Conferencing](set-up-audio-conferencing-in-teams.md) using Microsoft as the audio conferencing provider.</span></span>

<span data-ttu-id="a8f00-105">默认情况下，对于启用了音频会议的用户，向其发送的电子邮件共有四种类型。</span><span class="sxs-lookup"><span data-stu-id="a8f00-105">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="a8f00-106">但是，如果你要限制向用户发送的电子邮件数，你可以将其关闭。</span><span class="sxs-lookup"><span data-stu-id="a8f00-106">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="a8f00-107">在下列情况下，Office 365 中的音频会议将向用户发送电子邮件：</span><span class="sxs-lookup"><span data-stu-id="a8f00-107">Audio Conferencing in Office 365 will send email to your users' email when:</span></span>

- <span data-ttu-id="a8f00-108">**为用户分配了音频会议许可证时，或者你将音频会议提供商更改为 Microsoft 时。**</span><span class="sxs-lookup"><span data-stu-id="a8f00-108">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>

     <span data-ttu-id="a8f00-109">此电子邮件包括会议 ID、默认的会议电话号码、用户的音频会议 PIN 以及使用 Skype for Business Online 会议更新工具为用户更新现有会议的说明和链接。</span><span class="sxs-lookup"><span data-stu-id="a8f00-109">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="a8f00-110">请参阅[分配 Microsoft 团队许可证](assign-teams-licenses.md)或[指定 microsoft 作为音频会议提供商](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。</span><span class="sxs-lookup"><span data-stu-id="a8f00-110">See [Assign Microsoft Teams licenses](assign-teams-licenses.md) or [Assign Microsoft as the audio conferencing provider](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

    > [!NOTE]
    > <span data-ttu-id="a8f00-111">如果贵组织已启用动态会议 ID，则用户安排的所有会议都将具有唯一的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="a8f00-111">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="a8f00-112">你可以[在贵组织中设置音频会议动态 ID](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user)。</span><span class="sxs-lookup"><span data-stu-id="a8f00-112">You can set up [Audio Conferencing dynamic IDs in your organization](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user).</span></span> 

    <span data-ttu-id="a8f00-113">下面是此电子邮件示例：</span><span class="sxs-lookup"><span data-stu-id="a8f00-113">Here is an example of this email:</span></span>

     ![Skype for Business 验证许可证](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    <span data-ttu-id="a8f00-115">若要了解有关许可的详细信息，请参阅[Microsoft 团队加载项许可](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="a8f00-115">To find out more about licensing, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

- <span data-ttu-id="a8f00-116">**更改了用户的会议 ID 或默认会议电话号码。**</span><span class="sxs-lookup"><span data-stu-id="a8f00-116">**The conference ID or default conference phone number of a user changes.**</span></span>

    <span data-ttu-id="a8f00-117">此电子邮件包括会议 ID、默认会议电话号码以及使用 Skype for Business Online 会议更新工具为用户更新现有会议的说明和链接。</span><span class="sxs-lookup"><span data-stu-id="a8f00-117">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="a8f00-118">但此电子邮件不包括用户的音频会议 PIN。</span><span class="sxs-lookup"><span data-stu-id="a8f00-118">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="a8f00-119">请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="a8f00-119">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>

    <span data-ttu-id="a8f00-120">下面是此电子邮件示例：</span><span class="sxs-lookup"><span data-stu-id="a8f00-120">Here is an example of this email:</span></span>

     ![电话拨入式会议信息已更改。](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- <span data-ttu-id="a8f00-122">**重置了用户的音频会议 PIN。**</span><span class="sxs-lookup"><span data-stu-id="a8f00-122">**The audio conferencing PIN of a user is reset.**</span></span>

    <span data-ttu-id="a8f00-123">此电子邮件包含组织者的音频会议 PIN、用户的现有会议 ID 和默认会议电话号码。</span><span class="sxs-lookup"><span data-stu-id="a8f00-123">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="a8f00-124">请参阅[重置音频会议 PIN](reset-the-audio-conferencing-pin-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="a8f00-124">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
     <span data-ttu-id="a8f00-125">下面是此电子邮件示例：</span><span class="sxs-lookup"><span data-stu-id="a8f00-125">Here is an example of this email:</span></span>
    
     ![电话拨入式会议 PIN 已更改。](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- <span data-ttu-id="a8f00-127">**用户的许可证被删除，或者音频会议提供商从 Microsoft 更改为其他提供商或“无”。**</span><span class="sxs-lookup"><span data-stu-id="a8f00-127">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>

    <span data-ttu-id="a8f00-128">当从用户删除**音频会议**许可证或将音频会议提供商设置为 "**无**" 时，会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="a8f00-128">This happens when the **Audio Conferencing** license is removed from a user or when setting the audio conferencing provider to **None**.</span></span>

    <span data-ttu-id="a8f00-129">请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="a8f00-129">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

    <span data-ttu-id="a8f00-130">下面是此电子邮件的一个示例：</span><span class="sxs-lookup"><span data-stu-id="a8f00-130">Here is an example of this email:</span></span>

     ![电话拨入式会议已关闭。](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="a8f00-132">更改发送给用户的电子邮件</span><span class="sxs-lookup"><span data-stu-id="a8f00-132">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="a8f00-133">您可以对自动发送给用户的电子邮件进行更改。</span><span class="sxs-lookup"><span data-stu-id="a8f00-133">You can make changes to the email that is automatically sent to users.</span></span> <span data-ttu-id="a8f00-134">默认情况下，电子邮件的发件人将来自 Office 365，但你可以使用 Windows PowerShell 更改显示名称。</span><span class="sxs-lookup"><span data-stu-id="a8f00-134">By default, the sender of the emails will be from Office 365, but you can change the display name using Windows PowerShell.</span></span> <span data-ttu-id="a8f00-135">有关详细信息，请参阅[Microsoft 团队 PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。</span><span class="sxs-lookup"><span data-stu-id="a8f00-135">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="a8f00-136">如果不想向用户发送电子邮件，又该怎样做？</span><span class="sxs-lookup"><span data-stu-id="a8f00-136">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="a8f00-137">当禁用电子邮件发送给用户时，即使用户拥有分配的许可证，也不会向其发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a8f00-137">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="a8f00-138">在此情况下，会议 ID、默认会议电话号码和更重要的是，其音频会议 PIN 不会发送给用户。</span><span class="sxs-lookup"><span data-stu-id="a8f00-138">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="a8f00-139">发生这种情况时，你必须通过向用户发送单独的电子邮件或呼叫他们进行通知。</span><span class="sxs-lookup"><span data-stu-id="a8f00-139">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>

<span data-ttu-id="a8f00-140">默认情况下，将向你的用户发送电子邮件，但如果你希望阻止他们接收用于音频会议的电子邮件，则可以使用 Microsoft 团队或 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a8f00-140">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use Microsoft Teams or Windows PowerShell.</span></span> 

<span data-ttu-id="a8f00-141">![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标</span><span class="sxs-lookup"><span data-stu-id="a8f00-141">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="a8f00-142">在左侧导航中，转到“**会议**” > “**会议网桥**”。</span><span class="sxs-lookup"><span data-stu-id="a8f00-142">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="a8f00-143">在 "**会议桥**" 页面顶部，单击 "**桥接设置**"。</span><span class="sxs-lookup"><span data-stu-id="a8f00-143">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="a8f00-144">在**桥设置**窗格中，启用或禁用**如果其拨入设置发生更改，则自动向用户发送电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="a8f00-144">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="a8f00-145">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a8f00-145">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="a8f00-146">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a8f00-146">**Using Windows PowerShell**</span></span>

<span data-ttu-id="a8f00-147">有关详细信息，请参阅[Microsoft 团队 PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。</span><span class="sxs-lookup"><span data-stu-id="a8f00-147">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="a8f00-148">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="a8f00-148">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="a8f00-149">默认情况下，电子邮件的发件人将来自 Office 365，但你可以使用 Windows PowerShell 更改电子邮件地址和显示名称。</span><span class="sxs-lookup"><span data-stu-id="a8f00-149">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell.</span></span> 

<span data-ttu-id="a8f00-p108">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="a8f00-p108">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="a8f00-153">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="a8f00-153">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [<span data-ttu-id="a8f00-154">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="a8f00-154">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

<span data-ttu-id="a8f00-155">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="a8f00-155">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="related-topics"></a><span data-ttu-id="a8f00-156">相关主题</span><span class="sxs-lookup"><span data-stu-id="a8f00-156">Related topics</span></span>

[<span data-ttu-id="a8f00-157">启用或禁用发送电子邮件时更改音频会议设置</span><span class="sxs-lookup"><span data-stu-id="a8f00-157">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[<span data-ttu-id="a8f00-158">对其音频会议信息的用户发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="a8f00-158">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
