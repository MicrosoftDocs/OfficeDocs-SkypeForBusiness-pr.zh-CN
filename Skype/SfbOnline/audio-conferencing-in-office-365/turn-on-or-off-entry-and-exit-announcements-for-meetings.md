---
title: 打开或关闭会议的进入和退出通知
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to turn entry and exit announcements on or off in a Skype for Business Online meeting using the Skype for Business admin center. '
ms.openlocfilehash: 18b22e5491b67b6f4ec3f089803bcfb5e486eb14
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703451"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings"></a><span data-ttu-id="132f9-103">打开或关闭会议的进入和退出通知</span><span class="sxs-lookup"><span data-stu-id="132f9-103">Turn on or off entry and exit announcements for meetings</span></span>

<span data-ttu-id="132f9-104">当您要设置 Office 365 中的音频会议时，您将看到音频会议桥。</span><span class="sxs-lookup"><span data-stu-id="132f9-104">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="132f9-105">会议桥可以包含一个或多个人员将用于连接到企业或 Microsoft 团队会议 Skype 的电话号码。</span><span class="sxs-lookup"><span data-stu-id="132f9-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business or Microsoft Teams meeting.</span></span> 
  
<span data-ttu-id="132f9-106">会议网桥负责应答使用电话拨入会议的用户的呼叫。</span><span class="sxs-lookup"><span data-stu-id="132f9-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="132f9-107">会议桥应答来自会议自动助理的呼叫者使用语音提示并随后，具体取决于您的设置，可以播放通知，向呼叫者提出记录其姓名，并设置 PIN 安全。</span><span class="sxs-lookup"><span data-stu-id="132f9-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="132f9-108">PIN 赋予业务或 Microsoft 团队会议组织者，Skype 并允许其开始会议，如果它们无法启动会议使用 Skype 业务或 Microsoft 团队的应用程序。</span><span class="sxs-lookup"><span data-stu-id="132f9-108">A PIN is given to a Skype for Business or Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using a Skype for Business or Microsoft Teams app.</span></span> <span data-ttu-id="132f9-109">但是，可以将它以便启动会议不需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="132f9-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="132f9-110">设置会议加入选项</span><span class="sxs-lookup"><span data-stu-id="132f9-110">Setting meeting join options</span></span>

<span data-ttu-id="132f9-111">![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**</span><span class="sxs-lookup"><span data-stu-id="132f9-111">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="132f9-112">在左侧导航窗格中，转到**会议** > **会议桥**。</span><span class="sxs-lookup"><span data-stu-id="132f9-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="132f9-113">在**会议桥**页的顶部，单击**网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="132f9-113">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="132f9-114">在**桥设置**窗格中，启用或禁用**启用会议进入和退出通知，以打开**。</span><span class="sxs-lookup"><span data-stu-id="132f9-114">In the **Bridge settings** pane, enable or disable **Enable meeting entry and exit notifications to be turned on**.</span></span> <span data-ttu-id="132f9-115">默认情况下，此选项处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="132f9-115">This is selected by default.</span></span> <span data-ttu-id="132f9-116">如果清除它，某人进入或离开会议时，已加入会议的用户不会将收到通知。</span><span class="sxs-lookup"><span data-stu-id="132f9-116">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
4. <span data-ttu-id="132f9-117">在**条目/退出通知类型**，选择**姓名或电话号码**或**提示音**。</span><span class="sxs-lookup"><span data-stu-id="132f9-117">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
5. <span data-ttu-id="132f9-118">启用或禁用**Ask 呼叫者在记录其姓名之前加入会议**。</span><span class="sxs-lookup"><span data-stu-id="132f9-118">Enable or disable **Ask callers to record their name before joining the meeting**.</span></span>
    
6. <span data-ttu-id="132f9-119">进行更改后，单击**应用**。</span><span class="sxs-lookup"><span data-stu-id="132f9-119">After you make your changes, click **Apply**.</span></span>

<span data-ttu-id="132f9-120">![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**</span><span class="sxs-lookup"><span data-stu-id="132f9-120">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="132f9-121">在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议** > **Microsoft 网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="132f9-121">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="132f9-122">在**会议的与会体验**中,，选中或清除**启用会议进入和退出通知，以打开**。</span><span class="sxs-lookup"><span data-stu-id="132f9-122">Under **Meeting join experience**, select or clear **Enable meeting entry and exit notifications to be turned on**.</span></span> <span data-ttu-id="132f9-123">默认情况下，此选项处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="132f9-123">This is selected by default.</span></span> <span data-ttu-id="132f9-124">如果清除它，某人进入或离开会议时，已加入会议的用户不会将收到通知。</span><span class="sxs-lookup"><span data-stu-id="132f9-124">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
3. <span data-ttu-id="132f9-125">在**条目/退出通知类型**，选择**姓名或电话号码**或**提示音**。</span><span class="sxs-lookup"><span data-stu-id="132f9-125">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
4. <span data-ttu-id="132f9-126">选中或取消选中**Ask 呼叫者在记录其姓名之前加入会议**。</span><span class="sxs-lookup"><span data-stu-id="132f9-126">Check or uncheck **Ask callers to record their name before joining the meeting**.</span></span>
    
5. <span data-ttu-id="132f9-127">完成更改后，单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="132f9-127">After you make your changes, click **Save**.</span></span>
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="132f9-128">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="132f9-128">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="132f9-129">为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="132f9-129">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet.</span></span>
    
-  <span data-ttu-id="132f9-p105">对于 Windows PowerShell，Skype for Business Online 的功能是管理用户以及允许或不允许用户执行的操作。 使用 Windows PowerShell，可以通过单点管理来管理 Office 365，这样做可在有多个任务需要执行时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="132f9-p105">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="132f9-133">为什么您需要使用 Office 365 PowerShell 中</span><span class="sxs-lookup"><span data-stu-id="132f9-133">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="132f9-134">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="132f9-134">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="132f9-135">Windows PowerShell 已通过仅使用如时要进行设置更改多个用户一次在 Office 365 管理中心中快速、 简便起见和生产力很多好处。</span><span class="sxs-lookup"><span data-stu-id="132f9-135">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="132f9-136">请在以下主题中了解这些优点：</span><span class="sxs-lookup"><span data-stu-id="132f9-136">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="132f9-137">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="132f9-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="132f9-138">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="132f9-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="132f9-139">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="132f9-139">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="132f9-p107">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="132f9-p107">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="132f9-142">相关主题</span><span class="sxs-lookup"><span data-stu-id="132f9-142">Related topics</span></span>

[<span data-ttu-id="132f9-143">音频会议常见问题</span><span class="sxs-lookup"><span data-stu-id="132f9-143">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
