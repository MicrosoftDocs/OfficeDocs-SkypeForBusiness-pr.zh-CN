---
title: 在 Microsoft Teams 中重置用户的会议 ID
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
description: 了解在 Microsoft Teams 中重置用户的会议 ID 的步骤，并获取会议更新和迁移工具的链接。
ms.openlocfilehash: edccab5da883c1707ade75519e96615ed3524bf3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117640"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="11db9-103">在 Microsoft Teams 中重置用户的会议 ID</span><span class="sxs-lookup"><span data-stu-id="11db9-103">Reset a conference ID for a user in Microsoft Teams</span></span>

<span data-ttu-id="11db9-104">会议邀请底部包含动态会议 ID，以及呼叫者可用于拨入会议的拨入电话号码。</span><span class="sxs-lookup"><span data-stu-id="11db9-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="11db9-105">当用户拨打电话号码时，会议的自动助理将要求呼叫者输入此会议 ID，以便他们可以参加会议。</span><span class="sxs-lookup"><span data-stu-id="11db9-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="11db9-106">会议 ID 将自动生成，介于 7-9 位数之间，并且会在为用户启用音频会议时设置。</span><span class="sxs-lookup"><span data-stu-id="11db9-106">Conference IDs are generated automatically, will be between 7-9 digits, and are set when you enable Audio Conferencing for a user.</span></span> <span data-ttu-id="11db9-107">**不支持静态会议 ID。**</span><span class="sxs-lookup"><span data-stu-id="11db9-107">**Static conference IDs aren't supported.**</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="11db9-108">重置用户的会议 ID</span><span class="sxs-lookup"><span data-stu-id="11db9-108">Resetting the conference ID for a user</span></span>

<span data-ttu-id="11db9-109">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="11db9-109">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="11db9-110">在左侧导航栏中， **单击"用户**"，然后从可用用户列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="11db9-110">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="11db9-111">单击"**编辑"。**</span><span class="sxs-lookup"><span data-stu-id="11db9-111">Click **Edit**.</span></span>

3. <span data-ttu-id="11db9-112">在"**音频会议"下，单击\*\*\*\*"重置会议 ID"。**</span><span class="sxs-lookup"><span data-stu-id="11db9-112">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="11db9-113">在"**重置会议 ID"窗口中**，单击"重置 **"。**</span><span class="sxs-lookup"><span data-stu-id="11db9-113">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="11db9-114">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="11db9-114">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="11db9-115">默认情况下，电子邮件将发送给用户，但可以将其关闭。</span><span class="sxs-lookup"><span data-stu-id="11db9-115">By default, emails are sent to users, but this can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="11db9-116">[!注释] 重置会议 ID 后，会向用户发送包含新会议 ID 的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="11db9-116">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="11db9-117">此电子邮件将发送到主要电子邮件地址（在许多情况下为 Microsoft 365 或 Office 365 邮箱）。</span><span class="sxs-lookup"><span data-stu-id="11db9-117">This email will be sent to the primary email address, in many cases, their Microsoft 365 or Office 365 mailbox.</span></span> <span data-ttu-id="11db9-118">电子邮件包含新的会议 ID、默认拨入电话号码 (以及) 现有会议的说明。</span><span class="sxs-lookup"><span data-stu-id="11db9-118">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="11db9-119">我还需了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="11db9-119">What else should I know?</span></span>

- <span data-ttu-id="11db9-120">您可以通过在"音频会议"部分中单击"在电子邮件中为用户发送会议信息"，在包含会议 ID 和拨入电话号码的电子邮件中向用户发送 **所有会议** 信息。</span><span class="sxs-lookup"><span data-stu-id="11db9-120">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info in email** for the user in the **Audio Conferencing** section.</span></span> <span data-ttu-id="11db9-121">它不会发送 PIN。</span><span class="sxs-lookup"><span data-stu-id="11db9-121">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="11db9-122">Teams 服务创建一个 7-9 位数的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="11db9-122">A 7- 9 digit conference ID is created by the Teams service.</span></span> <span data-ttu-id="11db9-123">不能更改其长度。</span><span class="sxs-lookup"><span data-stu-id="11db9-123">You can't change its length.</span></span>
    
- <span data-ttu-id="11db9-124">重置之后，你可以看到新会议 ID 列在" **会议 ID**"下方。</span><span class="sxs-lookup"><span data-stu-id="11db9-124">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="11db9-125">[!重要信息]  创建新会议 ID 后，呼叫者不能再使用旧会议 ID。</span><span class="sxs-lookup"><span data-stu-id="11db9-125">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="11db9-126">应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。</span><span class="sxs-lookup"><span data-stu-id="11db9-126">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="11db9-127">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="11db9-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="11db9-128">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="11db9-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="11db9-129">使用Windows PowerShell，您可以使用单点管理来管理 Microsoft 365 或 Office 365，当您有多个任务需要执行时，可以简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="11db9-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="11db9-130">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="11db9-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="11db9-131">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="11db9-131">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="11db9-132">[使用 Office 365 管理 Microsoft 365 或 Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="11db9-132">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="11db9-133">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="11db9-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="11db9-134">相关主题</span><span class="sxs-lookup"><span data-stu-id="11db9-134">Related topics</span></span>

[<span data-ttu-id="11db9-135">重置音频会议 PIN</span><span class="sxs-lookup"><span data-stu-id="11db9-135">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin-in-teams.md)