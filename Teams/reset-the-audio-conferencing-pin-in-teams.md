---
title: 在 Microsoft Teams 中重置音频会议 PIN
mms.author: tonysmit
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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解你应该了解的 PIN 相关信息以及如何在 Microsoft Teams 中重置 PIN。 '
ms.openlocfilehash: 9c63df504150dce7ba1d46329fc86a27c75ced8d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "23892951"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a><span data-ttu-id="dc687-103">在 Microsoft Teams 中重置音频会议 PIN</span><span class="sxs-lookup"><span data-stu-id="dc687-103">Reset the Audio Conferencing PIN in Microsoft Teams</span></span>

<span data-ttu-id="dc687-104">PIN 是指为启用了音频会议的每个 Microsoft Teams 用户创建的由数字组成的代码。</span><span class="sxs-lookup"><span data-stu-id="dc687-104">A PIN is a code made up of numbers that is created for each user who is enabled for dial-in conferencing.</span></span> <span data-ttu-id="dc687-105">音频会议 PIN 由会议组织者用于标识自己是会议组织者，并且会议组织者可以使用 PIN 通过电话启动会议。</span><span class="sxs-lookup"><span data-stu-id="dc687-105">Dial-in conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="dc687-106">如果他们使用 Microsoft Teams 应用启动会议，则不需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="dc687-106">If they use the Skype for Business client to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="dc687-107">如果用户忘记了其 PIN，并且在启用音频会议时收到的电子邮件中找不到 PIN，管理员可以重置其 PIN，或者用户可以重置自己的 PIN。</span><span class="sxs-lookup"><span data-stu-id="dc687-107">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for dial-in conferencing, an administrator will need to reset their PIN.</span></span>
  
<span data-ttu-id="dc687-108">当经过身份验证的用户使用 Microsoft Teams 应用加入时或者当组织者通过电话使用其 PIN 加入时，可以启动会议。</span><span class="sxs-lookup"><span data-stu-id="dc687-108">Meetings can be started when an authenticated user joins using a Skype for Business client or when the organizer joins with his or her PIN over the phone.</span></span> <span data-ttu-id="dc687-109">如果会议要求提供 PIN 才能启动，则通过电话加入会议的所有用户都将进入会议厅并将收听保持音乐，直至会议启动。</span><span class="sxs-lookup"><span data-stu-id="dc687-109">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts.</span></span> <span data-ttu-id="dc687-110">如果会议组织者不需要 PIN 来通过电话启动会议，则当呼叫者加入会议时，系统不会要求他们提供 PIN。</span><span class="sxs-lookup"><span data-stu-id="dc687-110">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>

## <a name="reset-a-users-pin"></a><span data-ttu-id="dc687-111">重置用户的 PIN</span><span class="sxs-lookup"><span data-stu-id="dc687-111">Reset a user's PIN</span></span>

1. <span data-ttu-id="dc687-112">在左侧导航中，单击“**用户**”，然后从可用用户列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="dc687-112">In the **Skype for Business admin center**, in the left navigation go to Dial-in conferencingDial-in users, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="dc687-113">在页面顶部，单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="dc687-113">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="dc687-114">在“**音频会议**”下，单击“**重置 PIN**”。</span><span class="sxs-lookup"><span data-stu-id="dc687-114">Under **Audio Conferencing**, click **Reset PIN**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a><span data-ttu-id="dc687-115">让用户重置自己的 PIN</span><span class="sxs-lookup"><span data-stu-id="dc687-115">Have a user reset his or her own PIN</span></span>

1. <span data-ttu-id="dc687-116">让用户访问 [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing)。</span><span class="sxs-lookup"><span data-stu-id="dc687-116">Have the user go to [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).</span></span>
2. <span data-ttu-id="dc687-117">单击“**重置 PIN**”。</span><span class="sxs-lookup"><span data-stu-id="dc687-117">Click **Reset PIN**.</span></span> 


## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="dc687-118">你还应该了解有关 PIN 的哪些信息？</span><span class="sxs-lookup"><span data-stu-id="dc687-118">What else should you know about PINs?</span></span>

- <span data-ttu-id="dc687-119">出于安全考虑，PIN 仅在重置时向管理员显示一次。</span><span class="sxs-lookup"><span data-stu-id="dc687-119">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset.</span></span> <span data-ttu-id="dc687-120">管理员重置 PIN 后，PIN 将以 \*\*\*\*\*\*\*\*\*\*\* 列出。</span><span class="sxs-lookup"><span data-stu-id="dc687-120">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\* in the Skype for Business admin center and in the results when they use Get-CsCsOnlineDialInConfencingUser in the Windows PowerShell.</span></span>
    
- <span data-ttu-id="dc687-121">默认情况下启用自动向用户发送电子邮件，当为用户启用了音频会议时或重置 PIN 时，用户将收到包含其 PIN 的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="dc687-121">Automatically sending emails to users is enabled by default and users will receive an email with their PIN when they're enabled for dial-in conferencing or when the PIN is reset.</span></span> <span data-ttu-id="dc687-122">但如果你已禁用自动发送电子邮件，则不会向用户发送 PIN 重置电子邮件，并且你必须手动向用户发送 PIN 信息。</span><span class="sxs-lookup"><span data-stu-id="dc687-122">But if you have disabled automatically sending emails, then a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="dc687-p105">当会议启动时，会议厅中的所有用户都将自动加入该会议。 例如，如果两个参与者在会议启动之前尝试加入会议，他们将进入会议厅并将收听保持音乐，当会议组织者通过电话使用 PIN 加入时，该会议将启动，会议厅中的参与者将加入会议。</span><span class="sxs-lookup"><span data-stu-id="dc687-p105">When a meeting starts, all of the users in the lobby will automatically join it. For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using his PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="dc687-125">默认设置不允许匿名呼叫者启动会议。</span><span class="sxs-lookup"><span data-stu-id="dc687-125">The default setting isn't to allow a meeting to be started by an anonymous callers.</span></span>
    
- <span data-ttu-id="dc687-126">当你为用户启用音频会议时，默认情况下，将会向他们发送包括会议信息及其 PIN 的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="dc687-126">When you enable a user for dial-in conferencing, by default they are sent emails that includes conferencing information and their PIN.</span></span> <span data-ttu-id="dc687-127">用户必须有 Office 365 邮箱是因为当重置 PIN 时，将通过电子邮件向为用户设置的主 SMTP 地址（别名）发送新 PIN。</span><span class="sxs-lookup"><span data-stu-id="dc687-127">The user must have an Office 365 mailbox because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="dc687-128">当你设置音频会议时，将设置贵组织所需的 PIN 位数。</span><span class="sxs-lookup"><span data-stu-id="dc687-128">When you set up dial-in conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="dc687-129">PIN 可以为 4 至 12 位数 - 默认为 5 位。</span><span class="sxs-lookup"><span data-stu-id="dc687-129">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="dc687-130">如果你更改 PIN 长度设置，则仅对新生成的 PIN 应用设置，不会对启用了音频会议的现有用户的 PIN 设置应用更改。</span><span class="sxs-lookup"><span data-stu-id="dc687-130">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for dial-in conferencing.</span></span> <span data-ttu-id="dc687-131">请参阅[设置音频会议的 PIN 的长度](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="dc687-131">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)</span></span>
    
- <span data-ttu-id="dc687-132">默认情况下，电子邮件将设置为用户的 Office 365 主 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="dc687-132">The email by default will be set to the Office 365 primary SMTP address of the user you can send an email to a non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="dc687-133">你可以向 Hotmail 或 MSN 电子邮件地址等非 Office 365 地址发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="dc687-133">The email by default will be set to the Office 365 primary SMTP address of the user you can send an email to a non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="dc687-134">你可以使用 Windows PowerShell 覆盖默认电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="dc687-134">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="dc687-135">如果用户在 Office 365 中没有 Exchange 邮箱，则此功能很有用。</span><span class="sxs-lookup"><span data-stu-id="dc687-135">This is useful if the users don't have an Exchange mailbox in Office 365.</span></span>

    

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="dc687-136">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="dc687-136">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="dc687-p109">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="dc687-p109">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="dc687-140">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="dc687-140">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="dc687-141">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="dc687-141">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="dc687-142">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="dc687-142">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="dc687-143">相关主题</span><span class="sxs-lookup"><span data-stu-id="dc687-143">Related topics</span></span>

[<span data-ttu-id="dc687-144">重置用户的会议 ID</span><span class="sxs-lookup"><span data-stu-id="dc687-144">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user-in-teams.md)
