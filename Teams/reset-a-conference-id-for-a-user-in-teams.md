---
title: 在 Microsoft Teams 中重置用户的会议 ID
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
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解在 Microsoft Teams 中重置用户的会议 ID 以及获取会议更新和迁移工具链接的步骤。 '
ms.openlocfilehash: 4e338e5ad00792a48e0a6c9e0791c0c5e4b759ac
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887849"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="b3970-103">在 Microsoft Teams 中重置用户的会议 ID</span><span class="sxs-lookup"><span data-stu-id="b3970-103">For information about resetting conference ID in Microsoft Teams, see Reset a conference ID for a user in Microsoft Teams.</span></span>

<span data-ttu-id="b3970-104">一个动态会议 ID 与呼叫者可用于拨入会议的拨入电话号码一起包含在会议邀请底部。</span><span class="sxs-lookup"><span data-stu-id="b3970-104">This conference ID is included at the bottom of Skype for Business Online meeting invitations along with the dial-in phone numbers that can be used by callers to call into a meeting.</span></span> <span data-ttu-id="b3970-105">在用户拨打电话号码时，会议的自动助理会要求呼叫者输入此会议 ID 才能参加会议。</span><span class="sxs-lookup"><span data-stu-id="b3970-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to input this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b3970-106">如果你的会议提供商是 Microsoft，则默认情况下，你的用户的会议 ID 设置为“仅动态”。</span><span class="sxs-lookup"><span data-stu-id="b3970-106">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="b3970-107">很遗憾，无法将其更改为静态，因为现在不支持。</span><span class="sxs-lookup"><span data-stu-id="b3970-107">Unfortunately, there's no ability to change it in the Skype for Business Admin Center or using Windows Powershell to become static, as this is now unsupported.</span></span> <span data-ttu-id="b3970-108">仅会为启用了音频会议的 Microsoft Teams 用户自动设置会议 ID。</span><span class="sxs-lookup"><span data-stu-id="b3970-108">Conference IDs are automatically set only for Skype for Business users enabled for Audio Conferencing.</span></span> 


## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="b3970-109">重置用户的会议 ID</span><span class="sxs-lookup"><span data-stu-id="b3970-109">Resetting the meeting conference ID for a user</span></span>

1. <span data-ttu-id="b3970-110">在左侧导航中，单击“**用户**”，然后从可用用户列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="b3970-110">In the **Skype for Business admin center**, in the left navigation go to Dial-in conferencingDial-in users, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="b3970-111">在页面顶部，单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="b3970-111">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="b3970-112">在“**音频会议**”下，单击“**重置会议 ID**”。</span><span class="sxs-lookup"><span data-stu-id="b3970-112">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="b3970-113">在“**重置会议 ID**”窗口中，单击“**重置**”。</span><span class="sxs-lookup"><span data-stu-id="b3970-113">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="b3970-114">将自动创建一个会议 ID，并向用户发送包含新会议 ID 的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b3970-114">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="b3970-115">默认情况下，将向用户发送电子邮件，但可以关闭此功能。</span><span class="sxs-lookup"><span data-stu-id="b3970-115">By default, emails are sent to users, but it can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="b3970-116">重置会议 ID 后，将向用户发送包含新会议 ID 的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b3970-116">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="b3970-117">此电子邮件将发送到主电子邮件地址，大多数情况下是其 Office 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="b3970-117">This email will be sent to the primary email address, in many cases, their Office 365 mailbox.</span></span> <span data-ttu-id="b3970-118">该电子邮件包含新会议 ID、默认拨入电话号码以及更新现有会议的说明。</span><span class="sxs-lookup"><span data-stu-id="b3970-118">The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="b3970-119">我还应该了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="b3970-119">What else should I know?</span></span>

- <span data-ttu-id="b3970-120">你可以在“**音频会议**”部分针对用户单击“**通过电子邮件发送会议信息**”，通过电子邮件向用户发送所有会议信息（包括会议 ID 和拨入电话号码）。</span><span class="sxs-lookup"><span data-stu-id="b3970-120">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking the **Send conference info via email**.</span></span> <span data-ttu-id="b3970-121">它不会发送 PIN。</span><span class="sxs-lookup"><span data-stu-id="b3970-121">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="b3970-122">会议 ID 将包含 7 位数，你不能更改其长度。</span><span class="sxs-lookup"><span data-stu-id="b3970-122">A conference ID will contain 7 digits and you can't change it's length in either the Skype for Business admin center or using Windows PowerShell.</span></span>
    
- <span data-ttu-id="b3970-123">重置后，你可以看到新会议 ID 列在“**会议 ID**”下。</span><span class="sxs-lookup"><span data-stu-id="b3970-123">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="b3970-124">创建新会议 ID 后，呼叫者不能使用旧会议 ID。</span><span class="sxs-lookup"><span data-stu-id="b3970-124">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="b3970-125">应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。</span><span class="sxs-lookup"><span data-stu-id="b3970-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="b3970-126">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="b3970-126">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="b3970-p107">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="b3970-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="b3970-130">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="b3970-130">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="b3970-131">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="b3970-131">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="b3970-132">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="b3970-132">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="b3970-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="b3970-133">Related topics</span></span>

<span data-ttu-id="b3970-134">[重置音频会议 PIN](reset-the-audio-conferencing-pin-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="b3970-134">[](reset-the-audio-conferencing-pin-in-teams.md)Reset the Audio Conferencing PIN for a user</span></span>
