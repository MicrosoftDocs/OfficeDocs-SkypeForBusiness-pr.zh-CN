---
title: 在 Skype for Business Online 中重置用户的会议 ID
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
description: '了解在 Skype for Business Online 中重置用户的会议 ID 的步骤，并获取会议更新和迁移工具的链接。 '
ms.openlocfilehash: 424b0dfb24d6034af20c18a0172221a09bef5ecd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114208"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a><span data-ttu-id="8af64-103">在 Skype for Business Online 中重置用户的会议 ID</span><span class="sxs-lookup"><span data-stu-id="8af64-103">Reset a conference ID for a user in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="8af64-104">有关重置 Microsoft Teams 中的会议 ID 的信息，请参阅[在 Microsoft  Teams 中重置用户的会议 ID](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="8af64-104">For information about resetting conference ID in Microsoft Teams, see [Reset a conference ID for a user in Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span></span>

<span data-ttu-id="8af64-105">会议邀请底部包含动态会议 ID，以及呼叫者可用于拨入会议的拨入电话号码。</span><span class="sxs-lookup"><span data-stu-id="8af64-105">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="8af64-106">当用户拨打电话号码时，会议的自动助理将要求呼叫者输入此会议 ID，以便他们可以参加会议。</span><span class="sxs-lookup"><span data-stu-id="8af64-106">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8af64-107">如果会议提供商是 Microsoft，则用户的会议 ID 设置为"仅动态"。</span><span class="sxs-lookup"><span data-stu-id="8af64-107">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only.</span></span> <span data-ttu-id="8af64-108">这无法更改。</span><span class="sxs-lookup"><span data-stu-id="8af64-108">This cannot be changed.</span></span> <span data-ttu-id="8af64-109">仅为启用音频会议的 Skype for Business 用户自动设置会议 ID。</span><span class="sxs-lookup"><span data-stu-id="8af64-109">Conference IDs are automatically set only for Skype for Business users enabled for Audio Conferencing.</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="8af64-110">重置用户的会议 ID</span><span class="sxs-lookup"><span data-stu-id="8af64-110">Resetting the conference ID for a user</span></span>
   
1. <span data-ttu-id="8af64-111">在 **Skype for Business 管理中心中**，单击"**音频会议用户**"，选择一个用户，然后在"会议 ID"下的"操作"窗格中单击  >  "重置 **"。** </span><span class="sxs-lookup"><span data-stu-id="8af64-111">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
2. <span data-ttu-id="8af64-112">在"**重置会议 ID？"** 窗口中，单击"**是"。**</span><span class="sxs-lookup"><span data-stu-id="8af64-112">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="8af64-113">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="8af64-113">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="8af64-114">默认情况下，电子邮件将发送给用户，但可以将其关闭。</span><span class="sxs-lookup"><span data-stu-id="8af64-114">By default, emails are sent to users, but this can be turned off.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8af64-115">[!注释] 重置会议 ID 后，会向用户发送包含新会议 ID 的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="8af64-115">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="8af64-116">此电子邮件将发送到主要电子邮件地址（在许多情况下为 Microsoft 365 或 Office 365 邮箱）。</span><span class="sxs-lookup"><span data-stu-id="8af64-116">This email will be sent to the primary email address, in many cases, their Microsoft 365 or Office 365 mailbox.</span></span> <span data-ttu-id="8af64-117">电子邮件中包含新的会议 ID、默认拨入电话号码以及使用 Skype for Business 会议更新工具更新现有会议的说明。</span><span class="sxs-lookup"><span data-stu-id="8af64-117">The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="8af64-118">我还需了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="8af64-118">What else should I know?</span></span>

- <span data-ttu-id="8af64-119">您可以通过在"操作"窗格中单击"通过电子邮件发送会议信息"，在包含会议 ID 和拨入电话号码的电子邮件中向用户发送所有会议信息。</span><span class="sxs-lookup"><span data-stu-id="8af64-119">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane.</span></span> <span data-ttu-id="8af64-120">它不会发送 PIN。</span><span class="sxs-lookup"><span data-stu-id="8af64-120">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="8af64-121">会议 ID 将包含 7 个数字，并且你无法更改 Skype for Business 管理中心中或通过使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="8af64-121">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="8af64-122">重置之后，你可以看到新会议 ID 列在" **会议 ID**"下方。</span><span class="sxs-lookup"><span data-stu-id="8af64-122">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="8af64-123">当你在"用户"页面上选择用户时，可以在"音频会议"下的"操作"窗格底部查看音频会议 **用户的会议** ID。</span><span class="sxs-lookup"><span data-stu-id="8af64-123">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="8af64-124">[!重要信息]  创建新会议 ID 后，呼叫者不能再使用旧会议 ID。</span><span class="sxs-lookup"><span data-stu-id="8af64-124">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="8af64-125">应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。</span><span class="sxs-lookup"><span data-stu-id="8af64-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="8af64-126">用户可以使用 Skype for Business 会议工具更新其现有会议。</span><span class="sxs-lookup"><span data-stu-id="8af64-126">The users can use Skype for Business Meeting Tool to update their existing meetings.</span></span> <span data-ttu-id="8af64-127">若要了解如何下载、安装和运行 Skype for Business 会议更新工具，请参阅：</span><span class="sxs-lookup"><span data-stu-id="8af64-127">To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="8af64-128">Skype for Business 和 Lync 的会议更新工具</span><span class="sxs-lookup"><span data-stu-id="8af64-128">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="8af64-129">Skype for Business Online、会议迁移工具（64 位）</span><span class="sxs-lookup"><span data-stu-id="8af64-129">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="8af64-130">Skype for Business Online、会议迁移工具（32 位）</span><span class="sxs-lookup"><span data-stu-id="8af64-130">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="8af64-131">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="8af64-131">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="8af64-132">对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。</span><span class="sxs-lookup"><span data-stu-id="8af64-132">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="8af64-133">使用 Windows PowerShell，当你有多个任务需要执行时，可以使用可以简化日常工作的单一管理点来管理 Microsoft 365 或 Office 365 和 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="8af64-133">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="8af64-134">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="8af64-134">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="8af64-135">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="8af64-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="8af64-136">为何需要使用 Microsoft 365 或 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="8af64-136">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
 
- <span data-ttu-id="8af64-137">Windows PowerShell比使用 Microsoft 365 管理中心（例如，一次对许多用户进行设置更改时）具有许多速度、简单性和工作效率优势。</span><span class="sxs-lookup"><span data-stu-id="8af64-137">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="8af64-138">通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="8af64-138">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="8af64-139">[使用 Office 365 管理 Microsoft 365 或 Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="8af64-139">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="8af64-140">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8af64-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="8af64-141">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="8af64-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="8af64-142">相关主题</span><span class="sxs-lookup"><span data-stu-id="8af64-142">Related topics</span></span>

[<span data-ttu-id="8af64-143">重置音频会议 PIN</span><span class="sxs-lookup"><span data-stu-id="8af64-143">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin.md)