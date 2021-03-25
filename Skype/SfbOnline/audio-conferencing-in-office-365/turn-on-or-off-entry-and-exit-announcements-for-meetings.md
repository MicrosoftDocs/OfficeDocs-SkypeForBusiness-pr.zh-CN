---
title: 打开或关闭 Skype for Business Online 中的会议加入和退出公告
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
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
description: '了解如何使用 Skype for Business 管理中心打开或关闭 Skype for Business Online 会议的加入和退出公告。 '
ms.openlocfilehash: 5165facfdc4de040b24b199cd99a1bb42565a76b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111928"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a><span data-ttu-id="b5508-103">打开或关闭 Skype for Business Online 中的会议加入和退出公告</span><span class="sxs-lookup"><span data-stu-id="b5508-103">Turn on or off entry and exit announcements for meetings in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="b5508-104">打开或关闭 Skype for Business Online 中的会议加入和退出公告[](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams)</span><span class="sxs-lookup"><span data-stu-id="b5508-104">For information about entry and exit announcements in Microsoft Teams, see [Turn on or off entry and exit announcements for meetings in Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span></span>

<span data-ttu-id="b5508-105">在 Microsoft 365 或 Office 365 中设置音频会议时，你将获得音频会议网桥。</span><span class="sxs-lookup"><span data-stu-id="b5508-105">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="b5508-106">会议桥可以包含一个或多个人员用于致电 Skype for Business 会议的电话号码。</span><span class="sxs-lookup"><span data-stu-id="b5508-106">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business meeting.</span></span> 
  
<span data-ttu-id="b5508-107">会议网桥负责应答使用电话拨入会议的用户的呼叫。</span><span class="sxs-lookup"><span data-stu-id="b5508-107">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="b5508-108">会议网桥通过来自会议自动助理的语音提示应答呼叫者，然后根据你的设置，可以播放通知、让呼叫者录制其姓名以及设置 PIN 安全。</span><span class="sxs-lookup"><span data-stu-id="b5508-108">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="b5508-109">为 Skype for Business 会议组织者提供了 PIN，这让他们能够在无法使用 Skype for Business 应用开始会议的情况下开始会议。</span><span class="sxs-lookup"><span data-stu-id="b5508-109">A PIN is given to a Skype for Business meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Skype for Business app.</span></span> <span data-ttu-id="b5508-110">但你可以设置不需要使用 PIN 即可启动会议。</span><span class="sxs-lookup"><span data-stu-id="b5508-110">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="b5508-111">设置会议加入选项</span><span class="sxs-lookup"><span data-stu-id="b5508-111">Setting meeting join options</span></span>
    
1. <span data-ttu-id="b5508-112">在 **Skype for Business 管理中心的** 左侧导航中，转到"**音频会议**  >  **""Microsoft 网桥设置"。**</span><span class="sxs-lookup"><span data-stu-id="b5508-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="b5508-113">在 **"会议加入体验"** 下，选择或清除"启用会议进入和 **退出通知"以打开**。</span><span class="sxs-lookup"><span data-stu-id="b5508-113">Under **Meeting join experience**, select or clear **Enable meeting entry and exit notifications to be turned on**.</span></span> <span data-ttu-id="b5508-114">默认情况下，此选项处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="b5508-114">This is selected by default.</span></span> <span data-ttu-id="b5508-115">如果你将其取消选中，则当有人进入或离开会议时，已加入会议的用户不会收到通知。</span><span class="sxs-lookup"><span data-stu-id="b5508-115">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
3. <span data-ttu-id="b5508-116">在 **进入/退出公告类型** 下，选择 **姓名或电话号码** 或 **提示音**。</span><span class="sxs-lookup"><span data-stu-id="b5508-116">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
4. <span data-ttu-id="b5508-117">选中或取消选中 **"让呼叫者在加入会议之前录制其姓名"。**</span><span class="sxs-lookup"><span data-stu-id="b5508-117">Check or uncheck **Ask callers to record their name before joining the meeting**.</span></span>
    
5. <span data-ttu-id="b5508-118">完成更改后，单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="b5508-118">After you make your changes, click **Save**.</span></span>
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="b5508-119">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="b5508-119">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="b5508-120">为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b5508-120">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span>
    
- <span data-ttu-id="b5508-121">对于 Windows PowerShell，Skype for Business Online 的功能是管理用户以及允许或不允许用户执行的操作。</span><span class="sxs-lookup"><span data-stu-id="b5508-121">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="b5508-122">使用Windows PowerShell，您可以使用单点管理来管理 Microsoft 365 或 Office 365，当您有多个任务需要执行时，可以简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="b5508-122">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="b5508-123">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="b5508-123">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="b5508-124">为何需要使用 Microsoft 365 或 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="b5508-124">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="b5508-125">[使用 Office 365 管理 Microsoft 365 或 Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="b5508-125">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="b5508-126">Windows PowerShell使用 Microsoft 365 管理中心（例如，一次更改许多用户的设置时）在速度、简单性和工作效率方面有许多优势。</span><span class="sxs-lookup"><span data-stu-id="b5508-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="b5508-127">请在以下主题中了解这些优点：</span><span class="sxs-lookup"><span data-stu-id="b5508-127">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="b5508-128">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="b5508-128">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="b5508-129">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b5508-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="b5508-130">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="b5508-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="b5508-p106">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="b5508-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b5508-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="b5508-133">Related topics</span></span>

[<span data-ttu-id="b5508-134">音频会议常见问题</span><span class="sxs-lookup"><span data-stu-id="b5508-134">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)