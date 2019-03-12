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
- Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解在 Microsoft Teams 中重置用户的会议 ID 以及获取会议更新和迁移工具链接的步骤。 '
ms.openlocfilehash: f5926d838d61d38eb5b8e9f840cd9d7a4694253f
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2019
ms.locfileid: "30542844"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="4c8b2-103">在 Microsoft Teams 中重置用户的会议 ID</span><span class="sxs-lookup"><span data-stu-id="4c8b2-103">Reset a conference ID for a user in Microsoft Teams</span></span>

<span data-ttu-id="4c8b2-104">一个动态会议 ID 与呼叫者可用于拨入会议的拨入电话号码一起包含在会议邀请底部。</span><span class="sxs-lookup"><span data-stu-id="4c8b2-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="4c8b2-105">在用户拨打电话号码时，会议的自动助理会要求呼叫者输入此会议 ID 才能参加会议。</span><span class="sxs-lookup"><span data-stu-id="4c8b2-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4c8b2-106">如果你的会议提供商是 Microsoft，则默认情况下，你的用户的会议 ID 设置为“仅动态”。</span><span class="sxs-lookup"><span data-stu-id="4c8b2-106">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="4c8b2-107">很遗憾，无法将其更改为静态，因为现在不支持。</span><span class="sxs-lookup"><span data-stu-id="4c8b2-107">Unfortunately, there's no ability to change it to become static, as this is now unsupported.</span></span> <span data-ttu-id="4c8b2-108">仅会为启用了音频会议的 Microsoft Teams 用户自动设置会议 ID。</span><span class="sxs-lookup"><span data-stu-id="4c8b2-108">Conference IDs are only automatically set for Microsoft Teams users enabled for Audio Conferencing.</span></span> 


## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="4c8b2-109">重置用户的会议 ID</span><span class="sxs-lookup"><span data-stu-id="4c8b2-109">Resetting the conference ID for a user</span></span>

<span data-ttu-id="4c8b2-110">![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**</span><span class="sxs-lookup"><span data-stu-id="4c8b2-110">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="4c8b2-111">在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。</span><span class="sxs-lookup"><span data-stu-id="4c8b2-111">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="4c8b2-112">单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="4c8b2-112">Click **Edit**.</span></span>

3. <span data-ttu-id="4c8b2-113">在**音频会议**下单击**重置的会议 ID**。</span><span class="sxs-lookup"><span data-stu-id="4c8b2-113">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="4c8b2-114">在**重置的会议 ID**窗口中，单击**重置**。</span><span class="sxs-lookup"><span data-stu-id="4c8b2-114">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="4c8b2-115">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="4c8b2-115">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="4c8b2-116">默认情况下电子邮件发送给用户，但这可以关闭。</span><span class="sxs-lookup"><span data-stu-id="4c8b2-116">By default, emails are sent to users, but this can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="4c8b2-117">[!注释] 重置会议 ID 后，会向用户发送包含新会议 ID 的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="4c8b2-117">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="4c8b2-118">此电子邮件将发送到主电子邮件地址，大多数情况下是其 Office 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="4c8b2-118">This email will be sent to the primary email address, in many cases, their Office 365 mailbox.</span></span> <span data-ttu-id="4c8b2-119">电子邮件包含新的会议 ID、 默认电话拨入电话号码和更新现有会议的说明。</span><span class="sxs-lookup"><span data-stu-id="4c8b2-119">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="4c8b2-120">我还需了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="4c8b2-120">What else should I know?</span></span>

- <span data-ttu-id="4c8b2-121">您可以向中包括会议 ID 和电话拨入电话号码，通过单击**音频会议**部分中为用户的**发送电子邮件中的会议信息**的电子邮件的用户发送的所有会议信息。</span><span class="sxs-lookup"><span data-stu-id="4c8b2-121">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info in email** for the user in the **Audio Conferencing** section.</span></span> <span data-ttu-id="4c8b2-122">它不会发送 PIN。</span><span class="sxs-lookup"><span data-stu-id="4c8b2-122">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="4c8b2-123">会议 ID 将包含 7 位数字，并且您无法更改它的长度。</span><span class="sxs-lookup"><span data-stu-id="4c8b2-123">A conference ID will contain 7 digits, and you can't change its length.</span></span>
    
- <span data-ttu-id="4c8b2-124">重置之后，你可以看到新会议 ID 列在" **会议 ID**"下方。</span><span class="sxs-lookup"><span data-stu-id="4c8b2-124">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="4c8b2-125">[!重要信息]  创建新会议 ID 后，呼叫者不能再使用旧会议 ID。</span><span class="sxs-lookup"><span data-stu-id="4c8b2-125">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="4c8b2-126">应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。</span><span class="sxs-lookup"><span data-stu-id="4c8b2-126">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="4c8b2-127">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="4c8b2-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="4c8b2-p107">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="4c8b2-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4c8b2-131">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c8b2-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="4c8b2-132">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="4c8b2-132">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="4c8b2-133">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="4c8b2-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="4c8b2-134">相关主题</span><span class="sxs-lookup"><span data-stu-id="4c8b2-134">Related topics</span></span>

[<span data-ttu-id="4c8b2-135">重置音频会议 PIN</span><span class="sxs-lookup"><span data-stu-id="4c8b2-135">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin-in-teams.md)
