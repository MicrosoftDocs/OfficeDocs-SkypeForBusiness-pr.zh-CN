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
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: 了解如何重置用户的音频会议 PIN Microsoft Teams了解有关 PIN 的重要事实。
ms.openlocfilehash: 7ea380fbeb722337eaec598823b12dbe18f49918
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117630"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a><span data-ttu-id="c1257-103">在 Microsoft Teams 中重置音频会议 PIN</span><span class="sxs-lookup"><span data-stu-id="c1257-103">Reset the Audio Conferencing PIN in Microsoft Teams</span></span>

<span data-ttu-id="c1257-104">PIN 是由为启用了音频会议的每个Microsoft Teams创建的数字的代码。</span><span class="sxs-lookup"><span data-stu-id="c1257-104">A PIN is a code made up of numbers that is created for each Microsoft Teams user who is enabled for audio conferencing.</span></span> <span data-ttu-id="c1257-105">音频会议 PIN 由会议组织者用来标识他们是会议组织者并允许他们通过电话启动会议。</span><span class="sxs-lookup"><span data-stu-id="c1257-105">Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="c1257-106">如果他们使用Microsoft Teams启动会议，则不需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="c1257-106">If they use the Microsoft Teams app to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="c1257-107">如果用户忘记了 PIN，在启用音频会议时发送给他们的电子邮件中找不到 PIN，则管理员可以重置其 PIN，也可以重置自己的 PIN。</span><span class="sxs-lookup"><span data-stu-id="c1257-107">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="c1257-108">当经过身份验证的用户使用 Microsoft Teams 应用加入时，或者当组织者通过电话使用 PIN 加入时，可以启动会议。</span><span class="sxs-lookup"><span data-stu-id="c1257-108">Meetings can be started when an authenticated user joins using the Microsoft Teams app or when the organizer joins with their PIN over the phone.</span></span> <span data-ttu-id="c1257-109">如果会议要求提供 PIN 才能启动，则通过电话加入会议的所有用户都将进入会议厅并将收听保持音乐，直至会议启动。</span><span class="sxs-lookup"><span data-stu-id="c1257-109">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts.</span></span> <span data-ttu-id="c1257-110">如果会议组织者不需要 PIN 来通过电话启动会议，则当呼叫者加入会议时，系统不会要求他们提供 PIN。</span><span class="sxs-lookup"><span data-stu-id="c1257-110">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>

## <a name="reset-a-users-pin"></a><span data-ttu-id="c1257-111">重置用户的 PIN</span><span class="sxs-lookup"><span data-stu-id="c1257-111">Reset a user's PIN</span></span>

<span data-ttu-id="c1257-112">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="c1257-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="c1257-113">在左侧导航栏中， **单击"用户**"，然后从可用用户列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="c1257-113">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="c1257-114">单击"**编辑"。**</span><span class="sxs-lookup"><span data-stu-id="c1257-114">Click **Edit**.</span></span>

3. <span data-ttu-id="c1257-115">在 **"音频会议"下**，单击"**重置 PIN"。**</span><span class="sxs-lookup"><span data-stu-id="c1257-115">Under **Audio Conferencing**, click **Reset PIN**.</span></span>

4. <span data-ttu-id="c1257-116">单击"**重置"。**</span><span class="sxs-lookup"><span data-stu-id="c1257-116">Click **Reset**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-their-own-pin"></a><span data-ttu-id="c1257-117">让用户重置其自己的 PIN</span><span class="sxs-lookup"><span data-stu-id="c1257-117">Have a user reset their own PIN</span></span>

1. <span data-ttu-id="c1257-118">让用户转到 [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing) 。</span><span class="sxs-lookup"><span data-stu-id="c1257-118">Have the user go to [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).</span></span>
2. <span data-ttu-id="c1257-119">单击"**重置 PIN"。**</span><span class="sxs-lookup"><span data-stu-id="c1257-119">Click **Reset PIN**.</span></span> 

> [!NOTE]
> <span data-ttu-id="c1257-120">对于 GCCH，请转到 https://webdir2g.online.gov.skypeforbusiness.us/lscp/usp/pstnconferencing ：。</span><span class="sxs-lookup"><span data-stu-id="c1257-120">For GCCH go to: https://webdir2g.online.gov.skypeforbusiness.us/lscp/usp/pstnconferencing.</span></span>

## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="c1257-121">你还应该知道有关 PIN 的哪些信息？</span><span class="sxs-lookup"><span data-stu-id="c1257-121">What else should you know about PINs?</span></span>

- <span data-ttu-id="c1257-122">出于安全目的，PIN 仅在重置 PIN 时向管理员显示一次。</span><span class="sxs-lookup"><span data-stu-id="c1257-122">For security purposes, the PIN is only shown to an administrator one time, when the PIN is reset.</span></span> <span data-ttu-id="c1257-123">管理员重置 PIN 后，PIN 将列为 \*\*\*\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c1257-123">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\*.</span></span>
    
- <span data-ttu-id="c1257-124">默认情况下，会自动向用户发送电子邮件，并且当用户启用音频会议或重置 PIN 时，将收到一封包含其 PIN 的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="c1257-124">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="c1257-125">但是，如果已禁用自动发送电子邮件，则 PIN 重置电子邮件不会发送给用户，您必须手动将 PIN 信息发送给用户。</span><span class="sxs-lookup"><span data-stu-id="c1257-125">But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="c1257-126">当会议启动时，会议厅中的所有用户都将自动加入该会议。</span><span class="sxs-lookup"><span data-stu-id="c1257-126">When a meeting starts, all of the users in the lobby will automatically join it.</span></span> <span data-ttu-id="c1257-127">例如，如果两个参与者在会议开始之前尝试加入会议，他们将进入会议厅并收听保持音乐，当会议组织者通过电话使用其 PIN 加入时，会议将开始，会议厅中的参与者将加入会议。</span><span class="sxs-lookup"><span data-stu-id="c1257-127">For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using their PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="c1257-128">默认设置是不允许匿名呼叫者启动会议。</span><span class="sxs-lookup"><span data-stu-id="c1257-128">The default setting is to not allow a meeting to be started by anonymous callers.</span></span>
    
- <span data-ttu-id="c1257-129">当你为用户启用音频会议时，默认情况下会向用户发送包含会议信息和 PIN 的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="c1257-129">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN.</span></span> <span data-ttu-id="c1257-130">用户必须具有 Microsoft 365 或 Office 365 邮箱，因为重置 PIN 时，将在电子邮件中向用户发送新的 PIN，并发送到用户设置的主要 SMTP 地址 (别名) 。</span><span class="sxs-lookup"><span data-stu-id="c1257-130">The user must have a Microsoft 365 or Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="c1257-131">设置音频会议时，设置组织中 PIN 所需的数字。</span><span class="sxs-lookup"><span data-stu-id="c1257-131">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="c1257-132">PIN 可以包含 4 至 12 个数字，默认情况下为 5 个。</span><span class="sxs-lookup"><span data-stu-id="c1257-132">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="c1257-133">如果更改 PIN 长度设置，该设置将仅应用于新生成的 PIN，不会应用于为音频会议启用的现有用户的 PIN 设置。</span><span class="sxs-lookup"><span data-stu-id="c1257-133">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="c1257-134">请参阅 [设置音频会议 PIN 的长度](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="c1257-134">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).</span></span>
    
- <span data-ttu-id="c1257-135">默认情况下，电子邮件将设置为Microsoft 365或Office 365 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="c1257-135">The email by default will be set to the Microsoft 365 or Office 365 primary SMTP address of the user.</span></span> <span data-ttu-id="c1257-136">您可以将电子邮件发送到非 Microsoft 365 或非 Office 365 地址，例如 Hotmail 或 MSN 电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="c1257-136">You can send an email to a non-Microsoft 365 or non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="c1257-137">可以使用默认电子邮件地址替代Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c1257-137">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="c1257-138">如果用户在邮箱或邮箱中Exchange邮箱，Microsoft 365 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c1257-138">This is useful if the users don't have an Exchange mailbox in Microsoft 365 or Office 365.</span></span>

    

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="c1257-139">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="c1257-139">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="c1257-140">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="c1257-140">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="c1257-141">使用Windows PowerShell，Microsoft 365管理Office 365管理点，可在有多个任务需要执行时简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="c1257-141">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="c1257-142">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="c1257-142">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c1257-143">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1257-143">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="c1257-144">[使用 Microsoft 365 Office 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="c1257-144">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="c1257-145">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="c1257-145">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c1257-146">相关主题</span><span class="sxs-lookup"><span data-stu-id="c1257-146">Related topics</span></span>

[<span data-ttu-id="c1257-147">重置用户的会议 ID</span><span class="sxs-lookup"><span data-stu-id="c1257-147">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user-in-teams.md)