---
title: 在 Microsoft Teams 中重置音频会议 PIN
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解你应该了解的 PIN 相关信息以及如何在 Microsoft Teams 中重置 PIN。 '
ms.openlocfilehash: 778e9841d3a355597b4b048d79bb62a144eed349
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37568352"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a><span data-ttu-id="fe938-103">在 Microsoft Teams 中重置音频会议 PIN</span><span class="sxs-lookup"><span data-stu-id="fe938-103">Reset the Audio Conferencing PIN in Microsoft Teams</span></span>

<span data-ttu-id="fe938-104">PIN 是指为启用了音频会议的每个 Microsoft Teams 用户创建的由数字组成的代码。</span><span class="sxs-lookup"><span data-stu-id="fe938-104">A PIN is a code made up of numbers that is created for each Microsoft Teams user who is enabled for audio conferencing.</span></span> <span data-ttu-id="fe938-105">音频会议 PIN 由会议组织者用于标识自己是会议组织者，并且会议组织者可以使用 PIN 通过电话启动会议。</span><span class="sxs-lookup"><span data-stu-id="fe938-105">Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="fe938-106">如果他们使用 Microsoft Teams 应用启动会议，则不需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="fe938-106">If they use the Microsoft Teams app to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="fe938-107">如果用户忘记了其 PIN，并且在启用音频会议时收到的电子邮件中找不到 PIN，管理员可以重置其 PIN，或者用户可以重置自己的 PIN。</span><span class="sxs-lookup"><span data-stu-id="fe938-107">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="fe938-108">当经过身份验证的用户使用 Microsoft Teams 应用加入时或者当组织者通过电话使用其 PIN 加入时，可以启动会议。</span><span class="sxs-lookup"><span data-stu-id="fe938-108">Meetings can be started when an authenticated user joins using the Microsoft Teams app or when the organizer joins with his or her PIN over the phone.</span></span> <span data-ttu-id="fe938-109">如果会议要求提供 PIN 才能启动，则通过电话加入会议的所有用户都将进入会议厅并将收听保持音乐，直至会议启动。</span><span class="sxs-lookup"><span data-stu-id="fe938-109">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts.</span></span> <span data-ttu-id="fe938-110">如果会议组织者不需要 PIN 来通过电话启动会议，则当呼叫者加入会议时，系统不会要求他们提供 PIN。</span><span class="sxs-lookup"><span data-stu-id="fe938-110">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>

## <a name="reset-a-users-pin"></a><span data-ttu-id="fe938-111">重置用户的 PIN</span><span class="sxs-lookup"><span data-stu-id="fe938-111">Reset a user's PIN</span></span>

<span data-ttu-id="fe938-112">![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标</span><span class="sxs-lookup"><span data-stu-id="fe938-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="fe938-113">在左侧导航中，单击 "**用户**"，然后从可用用户列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="fe938-113">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="fe938-114">单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="fe938-114">Click **Edit**.</span></span>

3. <span data-ttu-id="fe938-115">在 "**音频会议**" 下，单击 "**重置 PIN**"。</span><span class="sxs-lookup"><span data-stu-id="fe938-115">Under **Audio Conferencing**, click **Reset PIN**.</span></span>

4. <span data-ttu-id="fe938-116">单击 "**重置**"。</span><span class="sxs-lookup"><span data-stu-id="fe938-116">Click **Reset**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a><span data-ttu-id="fe938-117">让用户重置其自己的 PIN</span><span class="sxs-lookup"><span data-stu-id="fe938-117">Have a user reset his or her own PIN</span></span>

1. <span data-ttu-id="fe938-118">让用户转到[https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing)。</span><span class="sxs-lookup"><span data-stu-id="fe938-118">Have the user go to [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).</span></span>
2. <span data-ttu-id="fe938-119">单击 "**重置 PIN**"。</span><span class="sxs-lookup"><span data-stu-id="fe938-119">Click **Reset PIN**.</span></span> 


## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="fe938-120">你还应该知道有关 PIN 的哪些信息？</span><span class="sxs-lookup"><span data-stu-id="fe938-120">What else should you know about PINs?</span></span>

- <span data-ttu-id="fe938-121">出于安全考虑，PIN 仅在重置时向管理员显示一次。</span><span class="sxs-lookup"><span data-stu-id="fe938-121">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset.</span></span> <span data-ttu-id="fe938-122">管理员重置 PIN 后，PIN 将被列为 \* \* \* \* \* \* \* \* \*。</span><span class="sxs-lookup"><span data-stu-id="fe938-122">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\*.</span></span>
    
- <span data-ttu-id="fe938-123">默认情况下启用 "自动向用户发送电子邮件"，用户在启用音频会议或 PIN 重置时，将收到一封电子邮件及其 PIN。</span><span class="sxs-lookup"><span data-stu-id="fe938-123">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="fe938-124">但是，如果您已禁用自动发送电子邮件，则 PIN 重置电子邮件不会发送给用户，您将必须手动向用户发送 PIN 信息。</span><span class="sxs-lookup"><span data-stu-id="fe938-124">But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="fe938-p105">当会议启动时，会议厅中的所有用户都将自动加入该会议。 例如，如果两个参与者在会议启动之前尝试加入会议，他们将进入会议厅并将收听保持音乐，当会议组织者通过电话使用 PIN 加入时，该会议将启动，会议厅中的参与者将加入会议。</span><span class="sxs-lookup"><span data-stu-id="fe938-p105">When a meeting starts, all of the users in the lobby will automatically join it. For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using his PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="fe938-127">默认设置是不允许匿名呼叫者启动会议。</span><span class="sxs-lookup"><span data-stu-id="fe938-127">The default setting is to not allow a meeting to be started by anonymous callers.</span></span>
    
- <span data-ttu-id="fe938-128">当为用户启用音频会议时，默认情况下，会向他们发送包含会议信息的电子邮件及其 PIN 码。</span><span class="sxs-lookup"><span data-stu-id="fe938-128">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN.</span></span> <span data-ttu-id="fe938-129">用户必须拥有 Office 365 邮箱，因为当重置 PIN 时，将向用户发送电子邮件中的新 PIN，以发送到为用户设置的主 SMTP 地址（别名）。</span><span class="sxs-lookup"><span data-stu-id="fe938-129">The user must have an Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="fe938-130">设置音频会议时，设置您的组织中的 Pin 所需的数字。</span><span class="sxs-lookup"><span data-stu-id="fe938-130">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="fe938-131">PIN 可以包含 4 至 12 个数字，默认情况下为 5 个。</span><span class="sxs-lookup"><span data-stu-id="fe938-131">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="fe938-132">如果您更改了 "引脚长度" 设置，则该设置仅应用于新生成的引脚，并且不会应用到已启用音频会议的现有用户的引脚设置。</span><span class="sxs-lookup"><span data-stu-id="fe938-132">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="fe938-133">请参阅[设置音频会议会议的 PIN 长度](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="fe938-133">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).</span></span>
    
- <span data-ttu-id="fe938-134">默认情况下，电子邮件将设置为用户的 Office 365 主 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="fe938-134">The email by default will be set to the Office 365 primary SMTP address of the user.</span></span> <span data-ttu-id="fe938-135">您可以向非 Office 365 地址（如 Hotmail 或 MSN 电子邮件地址）发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="fe938-135">You can send an email to a non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="fe938-136">你可以使用 Windows PowerShell 替代默认电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="fe938-136">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="fe938-137">如果用户在 Office 365 中没有 Exchange 邮箱，则此功能非常有用。</span><span class="sxs-lookup"><span data-stu-id="fe938-137">This is useful if the users don't have an Exchange mailbox in Office 365.</span></span>

    

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="fe938-138">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="fe938-138">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="fe938-p109">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="fe938-p109">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="fe938-142">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe938-142">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="fe938-143">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="fe938-143">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="fe938-144">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="fe938-144">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="fe938-145">相关主题</span><span class="sxs-lookup"><span data-stu-id="fe938-145">Related topics</span></span>

[<span data-ttu-id="fe938-146">重置用户的会议 ID</span><span class="sxs-lookup"><span data-stu-id="fe938-146">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user-in-teams.md)
