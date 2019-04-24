---
title: 在 Microsoft Teams 中重置音频会议 PIN
mms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解你应该了解的 PIN 相关信息以及如何在 Microsoft Teams 中重置 PIN。 '
ms.openlocfilehash: 7fe1ae3487caf9433b8f41753f6af9584a7d7f4d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32206591"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a><span data-ttu-id="7f41c-103">在 Microsoft Teams 中重置音频会议 PIN</span><span class="sxs-lookup"><span data-stu-id="7f41c-103">Reset the Audio Conferencing PIN in Microsoft Teams</span></span>

<span data-ttu-id="7f41c-104">PIN 是指为启用了音频会议的每个 Microsoft Teams 用户创建的由数字组成的代码。</span><span class="sxs-lookup"><span data-stu-id="7f41c-104">A PIN is a code made up of numbers that is created for each Microsoft Teams user who is enabled for audio conferencing.</span></span> <span data-ttu-id="7f41c-105">音频会议 PIN 由会议组织者用于标识自己是会议组织者，并且会议组织者可以使用 PIN 通过电话启动会议。</span><span class="sxs-lookup"><span data-stu-id="7f41c-105">Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="7f41c-106">如果他们使用 Microsoft Teams 应用启动会议，则不需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="7f41c-106">If they use the Microsoft Teams app to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="7f41c-107">如果用户忘记了其 PIN，并且在启用音频会议时收到的电子邮件中找不到 PIN，管理员可以重置其 PIN，或者用户可以重置自己的 PIN。</span><span class="sxs-lookup"><span data-stu-id="7f41c-107">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="7f41c-108">当经过身份验证的用户使用 Microsoft Teams 应用加入时或者当组织者通过电话使用其 PIN 加入时，可以启动会议。</span><span class="sxs-lookup"><span data-stu-id="7f41c-108">Meetings can be started when an authenticated user joins using the Microsoft Teams app or when the organizer joins with his or her PIN over the phone.</span></span> <span data-ttu-id="7f41c-109">如果会议要求提供 PIN 才能启动，则通过电话加入会议的所有用户都将进入会议厅并将收听保持音乐，直至会议启动。</span><span class="sxs-lookup"><span data-stu-id="7f41c-109">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts.</span></span> <span data-ttu-id="7f41c-110">如果会议组织者不需要 PIN 来通过电话启动会议，则当呼叫者加入会议时，系统不会要求他们提供 PIN。</span><span class="sxs-lookup"><span data-stu-id="7f41c-110">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>

## <a name="reset-a-users-pin"></a><span data-ttu-id="7f41c-111">重置用户的 PIN</span><span class="sxs-lookup"><span data-stu-id="7f41c-111">Reset a user's PIN</span></span>

<span data-ttu-id="7f41c-112">![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**</span><span class="sxs-lookup"><span data-stu-id="7f41c-112">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="7f41c-113">在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。</span><span class="sxs-lookup"><span data-stu-id="7f41c-113">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="7f41c-114">单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="7f41c-114">Click **Edit**.</span></span>

3. <span data-ttu-id="7f41c-115">在**音频会议**，下单击**重置 PIN**。</span><span class="sxs-lookup"><span data-stu-id="7f41c-115">Under **Audio Conferencing**, click **Reset PIN**.</span></span>

4. <span data-ttu-id="7f41c-116">单击**重置**。</span><span class="sxs-lookup"><span data-stu-id="7f41c-116">Click **Reset**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a><span data-ttu-id="7f41c-117">具有重置其自己的 PIN 的用户</span><span class="sxs-lookup"><span data-stu-id="7f41c-117">Have a user reset his or her own PIN</span></span>

1. <span data-ttu-id="7f41c-118">让用户转到[https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing)。</span><span class="sxs-lookup"><span data-stu-id="7f41c-118">Have the user go to [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).</span></span>
2. <span data-ttu-id="7f41c-119">单击**重置 PIN**。</span><span class="sxs-lookup"><span data-stu-id="7f41c-119">Click **Reset PIN**.</span></span> 


## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="7f41c-120">你还应该知道有关 PIN 的哪些信息？</span><span class="sxs-lookup"><span data-stu-id="7f41c-120">What else should you know about PINs?</span></span>

- <span data-ttu-id="7f41c-121">出于安全考虑，PIN 仅在重置时向管理员显示一次。</span><span class="sxs-lookup"><span data-stu-id="7f41c-121">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset.</span></span> <span data-ttu-id="7f41c-122">由管理员重置 PIN 后，将作为列出 PIN \*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7f41c-122">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\*.</span></span>
    
- <span data-ttu-id="7f41c-123">默认情况下启用，自动向用户发送电子邮件，并且他们正在启用音频会议或时重置 PIN 时，用户将收到电子邮件与他们的 PIN。</span><span class="sxs-lookup"><span data-stu-id="7f41c-123">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="7f41c-124">但如果您已禁用自动发送电子邮件、 PIN 重置电子邮件将不会发送给用户，并且必须手动发送给用户的 PIN 信息。</span><span class="sxs-lookup"><span data-stu-id="7f41c-124">But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="7f41c-p105">当会议启动时，会议厅中的所有用户都将自动加入该会议。 例如，如果两个参与者在会议启动之前尝试加入会议，他们将进入会议厅并将收听保持音乐，当会议组织者通过电话使用 PIN 加入时，该会议将启动，会议厅中的参与者将加入会议。</span><span class="sxs-lookup"><span data-stu-id="7f41c-p105">When a meeting starts, all of the users in the lobby will automatically join it. For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using his PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="7f41c-127">默认设置是不允许由匿名呼叫者启动会议。</span><span class="sxs-lookup"><span data-stu-id="7f41c-127">The default setting is to not allow a meeting to be started by anonymous callers.</span></span>
    
- <span data-ttu-id="7f41c-128">当您启用音频会议的用户时，默认情况下它们发送电子邮件，包括会议信息和其 PIN。</span><span class="sxs-lookup"><span data-stu-id="7f41c-128">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN.</span></span> <span data-ttu-id="7f41c-129">用户必须具有 Office 365 邮箱，因为一个新的 PIN 重置 PIN 时, 将发送到电子邮件到为用户设置其主 SMTP 地址 （别名） 中的用户。</span><span class="sxs-lookup"><span data-stu-id="7f41c-129">The user must have an Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="7f41c-130">当您设置了音频会议时，您设置所需的 Pin 在组织中的数字。</span><span class="sxs-lookup"><span data-stu-id="7f41c-130">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="7f41c-131">PIN 可以包含 4 至 12 个数字，默认情况下为 5 个。</span><span class="sxs-lookup"><span data-stu-id="7f41c-131">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="7f41c-132">如果您更改 PIN 长度设置，请设置仅应用于新生成的旋转中心点，并且不应用于启用了音频会议的现有用户的 PIN 设置。</span><span class="sxs-lookup"><span data-stu-id="7f41c-132">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="7f41c-133">请参阅[设置音频会议的 PIN 长度](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="7f41c-133">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).</span></span>
    
- <span data-ttu-id="7f41c-134">默认情况下电子邮件将设置为用户的 Office 365 主 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="7f41c-134">The email by default will be set to the Office 365 primary SMTP address of the user.</span></span> <span data-ttu-id="7f41c-135">您可以向 Office 365 的地址，例如 Hotmail 或 MSN 电子邮件地址发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7f41c-135">You can send an email to a non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="7f41c-136">通过使用 Windows PowerShell，可以覆盖默认电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="7f41c-136">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="7f41c-137">如果用户在 Office 365 中没有 Exchange 邮箱，则此功能非常有用。</span><span class="sxs-lookup"><span data-stu-id="7f41c-137">This is useful if the users don't have an Exchange mailbox in Office 365.</span></span>

    

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="7f41c-138">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="7f41c-138">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="7f41c-p109">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="7f41c-p109">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="7f41c-142">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="7f41c-142">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="7f41c-143">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="7f41c-143">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="7f41c-144">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="7f41c-144">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="7f41c-145">相关主题</span><span class="sxs-lookup"><span data-stu-id="7f41c-145">Related topics</span></span>

[<span data-ttu-id="7f41c-146">重置用户的会议 ID</span><span class="sxs-lookup"><span data-stu-id="7f41c-146">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user-in-teams.md)
