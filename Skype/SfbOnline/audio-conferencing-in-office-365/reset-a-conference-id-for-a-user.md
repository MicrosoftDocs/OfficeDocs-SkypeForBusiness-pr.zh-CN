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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解在 Skype for Business Online 中重置用户会议 ID 的步骤，并获取会议更新和迁移工具的链接。 '
ms.openlocfilehash: 34e165d92f4dc63eea8fc31c05612b6e20b64025
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850058"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a><span data-ttu-id="4b8c6-103">在 Skype for Business Online 中重置用户的会议 ID</span><span class="sxs-lookup"><span data-stu-id="4b8c6-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="4b8c6-104">有关重置 Microsoft Teams 中的会议 ID 的信息，请参阅[在 Microsoft  Teams 中重置用户的会议 ID](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="4b8c6-104">For information about resetting conference ID in Microsoft Teams, see [Reset a conference ID for a user in Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span></span>

<span data-ttu-id="4b8c6-105">会议邀请底部包含有动态会议 ID，以及呼叫者可用于拨入会议的电话号码。</span><span class="sxs-lookup"><span data-stu-id="4b8c6-105">This conference ID is included at the bottom of Skype for Business Online meeting invitations along with the dial-in phone numbers that can be used by callers to call into a meeting.</span></span> <span data-ttu-id="4b8c6-106">用户拨打该电话号码时，会议的自动助理会要求呼叫者输入此会议 ID 方可参加会议。</span><span class="sxs-lookup"><span data-stu-id="4b8c6-106">When the user dials the phone number, the auto attendant for the meeting will ask the caller to input this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4b8c6-107">如果你的会议提供商是 Microsoft，默认情况下用户的会议 ID 设置为“仅动态”。</span><span class="sxs-lookup"><span data-stu-id="4b8c6-107">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="4b8c6-108">但是，不能在 Skype for Business 管理中心或使用 Windows Powershell 将其更改为静态，目前该操作不受支持。</span><span class="sxs-lookup"><span data-stu-id="4b8c6-108">Unfortunately, there's no ability to change it in the Skype for Business Admin Center or using Windows Powershell to become static, as this is now unsupported.</span></span> <span data-ttu-id="4b8c6-109">仅为启用音频会议的 Skype for Business 用户自动设置会议 ID。</span><span class="sxs-lookup"><span data-stu-id="4b8c6-109">Conference IDs are automatically set only for Skype for Business users enabled for Audio Conferencing.</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="4b8c6-110">重置用户的会议 ID</span><span class="sxs-lookup"><span data-stu-id="4b8c6-110">Resetting the meeting conference ID for a user</span></span>
   
1. <span data-ttu-id="4b8c6-111">在 **Skype for Business 管理中心**，单击**音频会议** > **用户**，选择用户，然后在**会议 ID** 下的操作窗格中单击**重置**。</span><span class="sxs-lookup"><span data-stu-id="4b8c6-111">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
2. <span data-ttu-id="4b8c6-112">在**重置会议 ID？** 窗口，单击**是**。</span><span class="sxs-lookup"><span data-stu-id="4b8c6-112">In the \*\* Reset conference ID?\*\* window, click **Yes**.</span></span> <span data-ttu-id="4b8c6-113">会议 ID 将自动创建，将有一封含有新会议 ID 的电子邮件发送给用户。</span><span class="sxs-lookup"><span data-stu-id="4b8c6-113">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="4b8c6-114">默认情况下，电子邮件会发送给用户，但这一功能可以关闭。</span><span class="sxs-lookup"><span data-stu-id="4b8c6-114">By default, emails are sent to users, but it can be turned off.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4b8c6-p104">[!注释] 重置会议 ID 后，会向用户发送包含新会议 ID 的电子邮件。此电子邮件将发送到主电子邮件地址，大多数情况下是其 Office 365 邮箱。电子邮件中包含新的会议 ID、默认拨入电话号码以及使用 Skype for Business 会议更新工具更新现有会议的说明。</span><span class="sxs-lookup"><span data-stu-id="4b8c6-p104">After you reset the conference ID, an email with the new conference ID will be sent to the user. This email will be sent to the primary email address, in many cases, their Office 365 mailbox. The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="4b8c6-118">我还需了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="4b8c6-118">What else should I know?</span></span>

- <span data-ttu-id="4b8c6-119">你可以单击 **通过电子邮件发送会议信息**，在一封电子邮件中向“操作”窗 格中的用户发送全部会议信息，包括会议 ID 和拨入电话号码。</span><span class="sxs-lookup"><span data-stu-id="4b8c6-119">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking the **Send conference info via email**.</span></span> <span data-ttu-id="4b8c6-120">它不会发送 PIN。</span><span class="sxs-lookup"><span data-stu-id="4b8c6-120">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="4b8c6-121">会议 ID 必须包含 7 位数，不能在 Skype for Business 管理中心中或使用 Windows PowerShell 更改其长度。</span><span class="sxs-lookup"><span data-stu-id="4b8c6-121">A conference ID will contain 7 digits and you can't change it's length in either the Skype for Business admin center or using Windows PowerShell.</span></span>
    
- <span data-ttu-id="4b8c6-122">重置之后，你可以看到新会议 ID 列在**会议 ID** 下方。</span><span class="sxs-lookup"><span data-stu-id="4b8c6-122">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="4b8c6-123">当你在**用户**页面上选择用户时，可以在“操作”窗格底部的**音频会议**下查看用户的音频会议 ID。</span><span class="sxs-lookup"><span data-stu-id="4b8c6-123">The conference ID for a user for dial-in conferencing can be viewed at the bottom of the Action pane under **Dial-in conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="4b8c6-124">创建新会议 ID 后，呼叫者不能再使用旧会议 ID。</span><span class="sxs-lookup"><span data-stu-id="4b8c6-124">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="4b8c6-125">应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。</span><span class="sxs-lookup"><span data-stu-id="4b8c6-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="4b8c6-126">用户可以使用 Skype for Business 会议工具来更新其现有会议。</span><span class="sxs-lookup"><span data-stu-id="4b8c6-126">The users can use Skype for Business Meeting Meeting Tool to update their existing meetings.</span></span> <span data-ttu-id="4b8c6-127">要了解如何下载、安装和运行 Skype for Business 会议更新工具，请参阅：</span><span class="sxs-lookup"><span data-stu-id="4b8c6-127">To see how to download, install and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="4b8c6-128">Skype for Business 和 Lync 的会议更新工具</span><span class="sxs-lookup"><span data-stu-id="4b8c6-128">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="4b8c6-129">Skype for Business Online、会议迁移工具（64 位）</span><span class="sxs-lookup"><span data-stu-id="4b8c6-129">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="4b8c6-130">Skype for Business Online、会议迁移工具（32 位）</span><span class="sxs-lookup"><span data-stu-id="4b8c6-130">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="4b8c6-131">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="4b8c6-131">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="4b8c6-p107">对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="4b8c6-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4b8c6-135">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="4b8c6-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="4b8c6-136">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="4b8c6-136">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="4b8c6-p108">例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="4b8c6-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="4b8c6-139">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="4b8c6-139">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="4b8c6-140">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4b8c6-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="4b8c6-141">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="4b8c6-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="4b8c6-142">相关主题</span><span class="sxs-lookup"><span data-stu-id="4b8c6-142">Related topics</span></span>

<span data-ttu-id="4b8c6-143">[重置音频会议 PIN](reset-the-audio-conferencing-pin.md)</span><span class="sxs-lookup"><span data-stu-id="4b8c6-143">[](reset-the-audio-conferencing-pin.md)Reset the Audio Conferencing PIN for a user</span></span>
