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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解如何使用 Skype for Business 管理中心打开或关闭 Skype for Business Online 会议的加入和退出公告。 '
ms.openlocfilehash: 8d91db2014439eb2c9e38f65215cf85d6f047157
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23863260"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a><span data-ttu-id="a6b46-103">打开或关闭 Skype for Business Online 中的会议加入和退出公告</span><span class="sxs-lookup"><span data-stu-id="a6b46-103">Turn on or off entry and exit announcements for meetings in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="a6b46-104">打开或关闭 Skype for Business Online 中的会议加入和退出公告[](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams)</span><span class="sxs-lookup"><span data-stu-id="a6b46-104">For information about entry and exit announcements in Microsoft Teams, see [Turn on or off entry and exit announcements for meetings in Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span></span>

<span data-ttu-id="a6b46-105">当设置 Office 365 中的音频会议时，您将看到音频会议桥。</span><span class="sxs-lookup"><span data-stu-id="a6b46-105">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="a6b46-106">会议桥可以包含一个或多个人员用于致电 Skype for Business 会议的电话号码。</span><span class="sxs-lookup"><span data-stu-id="a6b46-106">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business meeting.</span></span> 
  
<span data-ttu-id="a6b46-107">会议网桥负责应答使用电话拨入会议的用户的呼叫。</span><span class="sxs-lookup"><span data-stu-id="a6b46-107">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="a6b46-108">会议网桥通过来自自动助理的语音提示应答呼叫者，然后根据你的设置，会议网桥可以播放通知、让呼叫者录制其姓名以及设置 PIN 安全。</span><span class="sxs-lookup"><span data-stu-id="a6b46-108">The conferencing bridge answers the caller with voice prompts from an auto attendant and then depending on your settings can play notifications, ask callers to record their name and sets up the PIN security.</span></span> <span data-ttu-id="a6b46-109">为 Skype for Business 会议组织者提供了 PIN，这让他们能够在无法使用 Skype for Business 应用开始会议的情况下开始会议。</span><span class="sxs-lookup"><span data-stu-id="a6b46-109">A PIN is given to a Skype for Business meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Skype for Business app.</span></span> <span data-ttu-id="a6b46-110">然而，您可以设置不需要使用 PIN 启动会议。</span><span class="sxs-lookup"><span data-stu-id="a6b46-110">You can however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="a6b46-111">设置会议加入选项</span><span class="sxs-lookup"><span data-stu-id="a6b46-111">Setting meeting join options</span></span>
    
1. <span data-ttu-id="a6b46-112">在 **Skype for Business 管理中心** 中，在左侧导航中，转到**音频会议** > **Microsoft 桥接设置**。</span><span class="sxs-lookup"><span data-stu-id="a6b46-112">In the **Skype for Business admin center**, in the left navigation go to **Dial-in conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="a6b46-113">在 **会议的与会体验**中，选中或清除**打开启用会议加入和退出通知**。</span><span class="sxs-lookup"><span data-stu-id="a6b46-113">Under \*\* Meeting join experience\*\* > check or uncheck Enable meeting entry and exit notifications to be turned on This is selected by default.</span></span> <span data-ttu-id="a6b46-114">默认情况下，此选项处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="a6b46-114">This is selected by default.</span></span> <span data-ttu-id="a6b46-115">如果清除，已加入会议的用户将不会在某人进入或离开会议时收到通知。</span><span class="sxs-lookup"><span data-stu-id="a6b46-115">However if you uncheck it, users that have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>
    
3. <span data-ttu-id="a6b46-116">在**进入/退出公告类型**下，选择**姓名或电话号码** 或 **提示音**。</span><span class="sxs-lookup"><span data-stu-id="a6b46-116">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
4. <span data-ttu-id="a6b46-117">选中或取消选中**要求呼叫者在加入会议之前记录姓名**。</span><span class="sxs-lookup"><span data-stu-id="a6b46-117">Ask callers to record their name before joining the meeting</span></span>
    
5. <span data-ttu-id="a6b46-118">完成更改后，单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="a6b46-118">After you make your changes, click **Save**.</span></span>
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="a6b46-119">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="a6b46-119">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="a6b46-120">为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a6b46-120">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span>
    
-  <span data-ttu-id="a6b46-p104">对于 Windows PowerShell，Skype for Business Online 的功能是管理用户以及允许或不允许用户执行的操作。使用 Windows PowerShell，可以通过单点管理来管理 Office 365，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="a6b46-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="a6b46-124">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6b46-124">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="a6b46-125">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="a6b46-125">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="a6b46-126">Windows PowerShell 在速度、简单性和生产率方面有许多优点，仅限于使用 Office 365 管理中心，例如当您同时为许多用户进行设置更改时。</span><span class="sxs-lookup"><span data-stu-id="a6b46-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="a6b46-127">请在以下主题中了解这些优点：</span><span class="sxs-lookup"><span data-stu-id="a6b46-127">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="a6b46-128">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="a6b46-128">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="a6b46-129">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a6b46-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="a6b46-130">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="a6b46-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="a6b46-p106">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="a6b46-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="a6b46-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="a6b46-133">Related topics</span></span>

[<span data-ttu-id="a6b46-134">音频会议常见问题</span><span class="sxs-lookup"><span data-stu-id="a6b46-134">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
