---
title: 在 Skype for Business Online 中重置音频会议 PIN
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '了解有关引脚以及如何在 Skype for Business Online 中重置它们的信息。 '
ms.openlocfilehash: a2f91e1ccae53f08507a63ea56b499a3ad968c73
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777697"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a><span data-ttu-id="61601-103">在 Skype for Business Online 中重置音频会议 PIN</span><span class="sxs-lookup"><span data-stu-id="61601-103">Reset the Audio Conferencing PIN in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="61601-104">有关在 Microsoft 团队中重置音频会议 pin 的信息，请参阅[重置 Microsoft 团队中的音频会议 pin](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="61601-104">For information about resetting Audio Conferencing PINs in Microsoft Teams, see [Reset the Audio Conferencing PIN in Microsoft Teams](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).</span></span>

<span data-ttu-id="61601-105">PIN 是由为每个启用了音频会议的 Skype for business 用户创建的数字组成的代码。</span><span class="sxs-lookup"><span data-stu-id="61601-105">A PIN is a code made up of numbers that is created for each Skype for Business user who is enabled for audio conferencing.</span></span> <span data-ttu-id="61601-106">会议组织者使用音频会议 Pin 标识他们是会议组织者，并允许他们通过电话启动会议。</span><span class="sxs-lookup"><span data-stu-id="61601-106">Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="61601-107">如果他们使用 Skype for Business 应用启动会议，则不需要 PIN 码。</span><span class="sxs-lookup"><span data-stu-id="61601-107">If they use the Skype for Business app to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="61601-108">如果用户忘记了 PIN，并且他们在启用音频会议时收到的电子邮件中找不到该用户的 PIN，则管理员可以重置其 PIN，也可以重置其自己的 PIN。</span><span class="sxs-lookup"><span data-stu-id="61601-108">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="61601-109">当通过身份验证的用户使用 Skype for Business 应用加入或当组织者通过电话与他或她的 PIN 进行联接时，可以启动会议。</span><span class="sxs-lookup"><span data-stu-id="61601-109">Meetings can be started when an authenticated user joins using the Skype for Business app or when the organizer joins with his or her PIN over the phone.</span></span> <span data-ttu-id="61601-110">如果会议要求提供 PIN 才能启动，则通过电话加入会议的所有用户都将进入会议厅并将收听保持音乐，直至会议启动。</span><span class="sxs-lookup"><span data-stu-id="61601-110">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts.</span></span> <span data-ttu-id="61601-111">如果会议组织者不需要 PIN 来通过电话启动会议，则当呼叫者加入会议时，系统不会要求他们提供 PIN。</span><span class="sxs-lookup"><span data-stu-id="61601-111">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>
  
## <a name="reset-a-users-pin"></a><span data-ttu-id="61601-112">重置用户的 PIN</span><span class="sxs-lookup"><span data-stu-id="61601-112">Reset a user's PIN</span></span>

1. <span data-ttu-id="61601-113">使用你的工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="61601-113">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="61601-114">转到管理中心 > **Skype for**business，然后在左侧导航中单击 "**音频会议**"。</span><span class="sxs-lookup"><span data-stu-id="61601-114">Go to the admin center > **Skype for Business**, and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="61601-115">单击 "**用户**"，选择要为其重置 PIN 的用户。</span><span class="sxs-lookup"><span data-stu-id="61601-115">Click on **Users**, select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="61601-116">在操作窗格中的 "**固定**" 下，单击 "**重置**"。</span><span class="sxs-lookup"><span data-stu-id="61601-116">In the Action pane, under **PIN**, click **Reset**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a><span data-ttu-id="61601-117">让用户重置其自己的 PIN</span><span class="sxs-lookup"><span data-stu-id="61601-117">Have a user reset his or her own PIN</span></span>

<span data-ttu-id="61601-118">用户可以通过使用 "**电话拨入式会议**" 页面上的 "**重置 pin** " 选项重置 pin。</span><span class="sxs-lookup"><span data-stu-id="61601-118">A user can reset a PIN by using the **Reset PIN** option on the **Dial-in Conferencing** page.</span></span> <span data-ttu-id="61601-119">可通过以下三种方式之一访问此页面：</span><span class="sxs-lookup"><span data-stu-id="61601-119">This page can be accessed in one of three ways:</span></span>

* <span data-ttu-id="61601-120">在浏览器中，转[https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling)到。</span><span class="sxs-lookup"><span data-stu-id="61601-120">In a browser, go to [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).</span></span>
* <span data-ttu-id="61601-121">在 Skype for business 中，单击 "**选项**" 旁边的 "**显示菜单**" 箭头，然后单击 "**工具** > **电话拨入式会议设置**"。</span><span class="sxs-lookup"><span data-stu-id="61601-121">In Skype for Business, click the **Show Menu** arrow next to **Options**, and then click **Tools** > **Dial-in Conference Settings**.</span></span>
* <span data-ttu-id="61601-122">在 Skype for Business 中，单击 "**选项**"，在左侧菜单中单击 "**呼叫转接**"，然后在 "**更多通话设置**" 部分中，单击 "**编辑联机设置**"。</span><span class="sxs-lookup"><span data-stu-id="61601-122">In Skype for Business, click **Options**, click **Call Forwarding** in the left menu, and then in the **More Call Settings** section, click **Edit settings online**.</span></span> 

## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="61601-123">你还应该知道有关 PIN 的哪些信息？</span><span class="sxs-lookup"><span data-stu-id="61601-123">What else should you know about PINs?</span></span>

- <span data-ttu-id="61601-124">出于安全考虑，PIN 仅在重置时向管理员显示一次。</span><span class="sxs-lookup"><span data-stu-id="61601-124">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset.</span></span> <span data-ttu-id="61601-125">在管理员重置 PIN 后，在 Skype for Business 管理中心以及在 Windows PowerShell 中使用 CsCsOnlineDialInConfencingUser 时，PIN 将在**Skype For business 管理中心**和结果中列为 \* \* \* \* \* \* \*。</span><span class="sxs-lookup"><span data-stu-id="61601-125">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\* in the **Skype for Business admin center** and in the results when they use Get-CsCsOnlineDialInConfencingUser in Windows PowerShell.</span></span>
    
- <span data-ttu-id="61601-126">默认情况下启用 "自动向用户发送电子邮件"，用户在启用音频会议或 PIN 重置时，将收到一封电子邮件及其 PIN。</span><span class="sxs-lookup"><span data-stu-id="61601-126">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="61601-127">但是，如果您已禁用自动发送电子邮件，则 PIN 重置电子邮件不会发送给用户，您将必须手动向用户发送 PIN 信息。</span><span class="sxs-lookup"><span data-stu-id="61601-127">But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="61601-p106">当会议启动时，会议厅中的所有用户都将自动加入该会议。 例如，如果两个参与者在会议启动之前尝试加入会议，他们将进入会议厅并将收听保持音乐，当会议组织者通过电话使用 PIN 加入时，该会议将启动，会议厅中的参与者将加入会议。</span><span class="sxs-lookup"><span data-stu-id="61601-p106">When a meeting starts, all of the users in the lobby will automatically join it. For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using his PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="61601-130">默认设置是不允许匿名呼叫者启动会议。</span><span class="sxs-lookup"><span data-stu-id="61601-130">The default setting is to not allow a meeting to be started by anonymous callers.</span></span>
    
- <span data-ttu-id="61601-131">当为用户启用音频会议时，默认情况下，会向他们发送包含会议信息的电子邮件及其 PIN 码。</span><span class="sxs-lookup"><span data-stu-id="61601-131">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN.</span></span> <span data-ttu-id="61601-132">用户必须拥有 Office 365 邮箱，因为当重置 PIN 时，将向用户发送电子邮件中的新 PIN，以发送到为用户设置的主 SMTP 地址（别名）。</span><span class="sxs-lookup"><span data-stu-id="61601-132">The user must have an Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="61601-133">设置音频会议时，设置您的组织中的 Pin 所需的数字。</span><span class="sxs-lookup"><span data-stu-id="61601-133">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="61601-134">PIN 可以包含 4 至 12 个数字，默认情况下为 5 个。</span><span class="sxs-lookup"><span data-stu-id="61601-134">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="61601-135">如果您更改了 "引脚长度" 设置，则该设置仅应用于新生成的引脚，并且不会应用到已启用音频会议的现有用户的引脚设置。</span><span class="sxs-lookup"><span data-stu-id="61601-135">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="61601-136">请参阅[设置音频会议会议的 PIN 长度](Set-the-PIN-length-for-Audio-Conferencing-meetings.md)。</span><span class="sxs-lookup"><span data-stu-id="61601-136">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).</span></span>
    
- <span data-ttu-id="61601-137">默认情况下，电子邮件将设置为用户的 Office 365 主 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="61601-137">The email by default will be set to the Office 365 primary SMTP address of the user.</span></span> <span data-ttu-id="61601-138">您可以向非 Office 365 地址（如 Hotmail 或 MSN 电子邮件地址）发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="61601-138">You can send an email to a non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="61601-139">你可以使用 Windows PowerShell 替代默认电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="61601-139">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="61601-140">如果用户在 Office 365 中没有 Exchange 邮箱，则此功能非常有用。</span><span class="sxs-lookup"><span data-stu-id="61601-140">This is useful if the users don't have an Exchange mailbox in Office 365.</span></span>
    
- <span data-ttu-id="61601-141">若要覆盖发送电子邮件的默认用户地址，租户管理员可以使用以下 cmdlet： Get-csonlinedialinconferencinguser-amos-ResetLeaderPIN-SendEmail-SendEmailToAddress "u@hotmail.com"。</span><span class="sxs-lookup"><span data-stu-id="61601-141">To override the default user address where the email is sent, the tenant admin can use the following cmdlet: Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com".</span></span> <span data-ttu-id="61601-142">需要使用 SendEmail 参数来替代用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="61601-142">The SendEmail parameter is required to override the email address of the user.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="61601-143">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="61601-143">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="61601-144">为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="61601-144">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
- <span data-ttu-id="61601-145">你可以通过运行以下命令来设置 Amos Marble 的 PIN：</span><span class="sxs-lookup"><span data-stu-id="61601-145">You can set the PIN for Amos Marble by running:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- <span data-ttu-id="61601-p111">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="61601-p111">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="61601-149">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="61601-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="61601-150">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="61601-150">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="61601-151">Windows PowerShell 在速度、简洁性和效率方面具有许多优势，仅限于使用 Microsoft 365 管理中心，例如当你在一次为多个用户进行设置更改时。</span><span class="sxs-lookup"><span data-stu-id="61601-151">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="61601-152">请在以下主题中了解这些优点：</span><span class="sxs-lookup"><span data-stu-id="61601-152">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="61601-153">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="61601-153">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="61601-154">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="61601-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="61601-155">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="61601-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="61601-p113">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="61601-p113">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="61601-158">相关主题</span><span class="sxs-lookup"><span data-stu-id="61601-158">Related topics</span></span>

[<span data-ttu-id="61601-159">重置用户的会议 ID</span><span class="sxs-lookup"><span data-stu-id="61601-159">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user.md)
