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
ms.openlocfilehash: 145965f3ff2737b21c8fcb13c144e07e969fbeef
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372201"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a><span data-ttu-id="2de67-103">在 Microsoft Teams 中打开或关闭会议的进入和退出公告</span><span class="sxs-lookup"><span data-stu-id="2de67-103">Turn on or off entry and exit announcements for meetings in Microsoft Teams</span></span>

<span data-ttu-id="2de67-104">在 Microsoft 365 或 Office 365 中设置音频会议时，你将收到音频会议桥。</span><span class="sxs-lookup"><span data-stu-id="2de67-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="2de67-105">会议网桥可以包含一个或多个供大家用于拨入 Microsoft Teams 会议的电话号码。</span><span class="sxs-lookup"><span data-stu-id="2de67-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Microsoft Teams meeting.</span></span>
  
<span data-ttu-id="2de67-106">会议网桥负责应答使用电话拨入会议的用户的呼叫。</span><span class="sxs-lookup"><span data-stu-id="2de67-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="2de67-107">会议网桥通过来自会议自动助理的语音提示应答呼叫者，然后根据你的设置，可以播放通知、让呼叫者录制其姓名以及设置 PIN 安全。</span><span class="sxs-lookup"><span data-stu-id="2de67-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="2de67-108">将向 Microsoft Teams 会议组织者提供一个 PIN，如果组织者无法使用 Microsoft Teams 应用启动会议，可以使用该 PIN 启动会议。</span><span class="sxs-lookup"><span data-stu-id="2de67-108">A PIN is given to a Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Microsoft Teams app.</span></span> <span data-ttu-id="2de67-109">但你可以设置不需要使用 PIN 即可启动会议。</span><span class="sxs-lookup"><span data-stu-id="2de67-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="2de67-110">设置会议加入选项</span><span class="sxs-lookup"><span data-stu-id="2de67-110">Setting meeting join options</span></span>

<span data-ttu-id="2de67-111">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="2de67-111">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="2de67-112">您必须是团队服务管理员才能进行这些更改。</span><span class="sxs-lookup"><span data-stu-id="2de67-112">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="2de67-113">请参阅[使用团队管理员角色管理团队](https://docs.microsoft.com/microsoftteams/using-admin-roles)，了解如何获取管理员角色和权限。</span><span class="sxs-lookup"><span data-stu-id="2de67-113">See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="2de67-114">登录管理中心。</span><span class="sxs-lookup"><span data-stu-id="2de67-114">Log in to the admin center.</span></span>

2. <span data-ttu-id="2de67-115">在左侧导航中，转到“**会议**” > “**会议网桥**”。</span><span class="sxs-lookup"><span data-stu-id="2de67-115">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span>

3. <span data-ttu-id="2de67-116">在“**会议网桥**”页面顶部，单击“**网桥设置**”。</span><span class="sxs-lookup"><span data-stu-id="2de67-116">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span>

4. <span data-ttu-id="2de67-117">在“**网桥设置**”窗格中，启用或禁用“**会议进入和退出通知**”。</span><span class="sxs-lookup"><span data-stu-id="2de67-117">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span> <span data-ttu-id="2de67-118">默认情况下，此选项处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="2de67-118">This is selected by default.</span></span> <span data-ttu-id="2de67-119">如果你将其取消选中，则当有人进入或离开会议时，已加入会议的用户不会收到通知。</span><span class="sxs-lookup"><span data-stu-id="2de67-119">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>

5. <span data-ttu-id="2de67-120">在**进入/退出公告类型**下，选择**姓名或电话号码** 或 **提示音**。</span><span class="sxs-lookup"><span data-stu-id="2de67-120">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2de67-121">默认情况下，外部参与者看不到拨入的参与者的电话号码。</span><span class="sxs-lookup"><span data-stu-id="2de67-121">By default, external participants can't see the phone numbers of dialed-in participants.</span></span> <span data-ttu-id="2de67-122">如果想要保持这些电话号码的隐私，请选择“**进入/退出公告类型**”的“**提示音**”（这会阻止 Teams 读出电话号码）。</span><span class="sxs-lookup"><span data-stu-id="2de67-122">If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams).</span></span>

6. <span data-ttu-id="2de67-123">如果你选择“**姓名或电话号码**”，请启用或禁用“**要求呼叫者在加入会议之前录制其姓名**”。</span><span class="sxs-lookup"><span data-stu-id="2de67-123">If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.</span></span>

7. <span data-ttu-id="2de67-124">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="2de67-124">Click **Save**.</span></span>

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="2de67-125">希望了解有关 Windows PowerShell 的详细信息</span><span class="sxs-lookup"><span data-stu-id="2de67-125">Want to know more about Windows PowerShell</span></span>

<span data-ttu-id="2de67-126">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="2de67-126">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="2de67-127">使用 Windows PowerShell，你可以使用单一的管理点管理 Microsoft 365 或 Office 365，这可以在你有多个任务时简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="2de67-127">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="2de67-128">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="2de67-128">To get started with Windows PowerShell, see these topics:</span></span>

- [<span data-ttu-id="2de67-129">为什么需要使用 Microsoft 365 或 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="2de67-129">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- [<span data-ttu-id="2de67-130">通过 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法</span><span class="sxs-lookup"><span data-stu-id="2de67-130">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

<span data-ttu-id="2de67-131">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="2de67-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="2de67-132">相关主题</span><span class="sxs-lookup"><span data-stu-id="2de67-132">Related topics</span></span>

[<span data-ttu-id="2de67-133">音频会议常见问题</span><span class="sxs-lookup"><span data-stu-id="2de67-133">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
