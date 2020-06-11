---
title: 在团队中打开或关闭会议的进入和退出通知
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
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
- seo-marvel-apr2020
description: 管理员可以了解如何在 Microsoft 团队会议中打开或关闭 "进入" 和 "退出" 通知。
ms.openlocfilehash: 824949ea1c212f514830dfad3926444944ac099c
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2020
ms.locfileid: "44690978"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a><span data-ttu-id="609bb-103">在 Microsoft Teams 中打开或关闭会议的进入和退出公告</span><span class="sxs-lookup"><span data-stu-id="609bb-103">Turn on or off entry and exit announcements for meetings in Microsoft Teams</span></span>

<span data-ttu-id="609bb-104">在 Microsoft 365 或 Office 365 中设置音频会议时，你将收到音频会议桥。</span><span class="sxs-lookup"><span data-stu-id="609bb-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="609bb-105">会议网桥可以包含一个或多个供大家用于拨入 Microsoft Teams 会议的电话号码。</span><span class="sxs-lookup"><span data-stu-id="609bb-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Microsoft Teams meeting.</span></span> 
  
<span data-ttu-id="609bb-106">会议网桥负责应答使用电话拨入会议的用户的呼叫。</span><span class="sxs-lookup"><span data-stu-id="609bb-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="609bb-107">会议网桥通过来自会议自动助理的语音提示应答呼叫者，然后根据你的设置，可以播放通知、让呼叫者录制其姓名以及设置 PIN 安全。</span><span class="sxs-lookup"><span data-stu-id="609bb-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="609bb-108">将向 Microsoft Teams 会议组织者提供一个 PIN，如果组织者无法使用 Microsoft Teams 应用启动会议，可以使用该 PIN 启动会议。</span><span class="sxs-lookup"><span data-stu-id="609bb-108">A PIN is given to a Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Microsoft Teams app.</span></span> <span data-ttu-id="609bb-109">但你可以设置不需要使用 PIN 即可启动会议。</span><span class="sxs-lookup"><span data-stu-id="609bb-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="609bb-110">设置会议加入选项</span><span class="sxs-lookup"><span data-stu-id="609bb-110">Setting meeting join options</span></span>

<span data-ttu-id="609bb-111">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="609bb-111">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="609bb-112">只有管理员才能进行这些更改。</span><span class="sxs-lookup"><span data-stu-id="609bb-112">You must be an admin to make these changes.</span></span>

1. <span data-ttu-id="609bb-113">登录到管理中心  <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。</span><span class="sxs-lookup"><span data-stu-id="609bb-113">Log in to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="609bb-114">在左侧导航中，转到“**会议**” > “**会议网桥**”。</span><span class="sxs-lookup"><span data-stu-id="609bb-114">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

3. <span data-ttu-id="609bb-115">在“**会议网桥**”页面顶部，单击“**网桥设置**”。</span><span class="sxs-lookup"><span data-stu-id="609bb-115">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

4. <span data-ttu-id="609bb-116">在“**网桥设置**”窗格中，启用或禁用“**会议进入和退出通知**”。</span><span class="sxs-lookup"><span data-stu-id="609bb-116">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span> <span data-ttu-id="609bb-117">默认情况下，此选项处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="609bb-117">This is selected by default.</span></span> <span data-ttu-id="609bb-118">如果你将其取消选中，则当有人进入或离开会议时，已加入会议的用户不会收到通知。</span><span class="sxs-lookup"><span data-stu-id="609bb-118">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
5. <span data-ttu-id="609bb-119">在**进入/退出公告类型**下，选择**姓名或电话号码** 或 **提示音**。</span><span class="sxs-lookup"><span data-stu-id="609bb-119">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="609bb-120">默认情况下，外部参与者看不到拨入的参与者的电话号码。</span><span class="sxs-lookup"><span data-stu-id="609bb-120">By default, external participants can't see the phone numbers of dialed-in participants.</span></span> <span data-ttu-id="609bb-121">如果您想要维护这些电话号码的隐私，请选择 "**输入/退出通知类型**" 的 "**声音**" （这可防止 "团队" 朗读数字）。</span><span class="sxs-lookup"><span data-stu-id="609bb-121">If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams).</span></span>
    
6. <span data-ttu-id="609bb-122">如果你选择“**姓名或电话号码**”，请启用或禁用“**要求呼叫者在加入会议之前录制其姓名**”。</span><span class="sxs-lookup"><span data-stu-id="609bb-122">If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.</span></span>
    
7. <span data-ttu-id="609bb-123">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="609bb-123">Click **Save**.</span></span>

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="609bb-124">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="609bb-124">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="609bb-125">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="609bb-125">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="609bb-126">使用 Windows PowerShell，你可以使用单一的管理点管理 Microsoft 365 或 Office 365，这可以在你有多个任务时简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="609bb-126">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="609bb-127">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="609bb-127">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="609bb-128">为什么需要使用 Microsoft 365 或 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="609bb-128">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="609bb-129">通过 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法</span><span class="sxs-lookup"><span data-stu-id="609bb-129">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="609bb-130">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="609bb-130">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="609bb-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="609bb-131">Related topics</span></span>

[<span data-ttu-id="609bb-132">音频会议常见问题</span><span class="sxs-lookup"><span data-stu-id="609bb-132">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
