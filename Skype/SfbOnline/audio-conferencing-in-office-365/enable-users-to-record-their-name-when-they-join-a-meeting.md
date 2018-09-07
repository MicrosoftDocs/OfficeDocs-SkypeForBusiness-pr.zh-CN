---
title: 允许用户在 Skype for Business Online 中加入会议时记录其姓名
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
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
description: 了解如何启用或禁用用户在 Skype for Business Online 中加入会议时是否可以记录其姓名。
ms.openlocfilehash: 6022d7ebf0e653bc43373cb00faabc207f91562a
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850038"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a><span data-ttu-id="e5f46-103">允许用户在 Skype for Business Online 中加入会议时记录其姓名</span><span class="sxs-lookup"><span data-stu-id="e5f46-103">Enable users to record their name when they join a meeting</span></span>

> [!Note]
> <span data-ttu-id="e5f46-104">如果您希望允许用户在 Teams 中记录他们的姓名，请参阅[  允许用户在加入 Microsoft Teams 中的会议时记录他们的姓名](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams) 。</span><span class="sxs-lookup"><span data-stu-id="e5f46-104">If you want to allow users to record their names in Teams, see [Enable users to record their name when they join a meeting in Microsoft Teams](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams).</span></span>

<span data-ttu-id="e5f46-105">在 Office 365 中设置音频会议时，您将收到电话号码和音频会议网桥。</span><span class="sxs-lookup"><span data-stu-id="e5f46-105">When you are setting up dial-in conferencing in Skype for Business Online, you will receive phone numbers and what is called a dial-in or audio conferencing bridge.</span></span> <span data-ttu-id="e5f46-106">会议网桥可以包含一个或多个电话号码，这些号码可以是专用或共享电话号码。</span><span class="sxs-lookup"><span data-stu-id="e5f46-106">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="e5f46-107">会议网桥负责应答使用电话拨入会议的用户的呼叫。</span><span class="sxs-lookup"><span data-stu-id="e5f46-107">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="e5f46-108">会议网桥通过来自自动助理的语音提示应答呼叫者，根据它们的具体设置，会议网桥可以播放通知、让呼叫者在录音中留下姓名以及为会议组织者设置 PIN 安全码。</span><span class="sxs-lookup"><span data-stu-id="e5f46-108">The conferencing bridge answers the caller with voice prompts from an auto attendant and then, depending on their settings, can play notifications, ask callers to record their name, and sets up the PIN security for meeting organizers.</span></span> <span data-ttu-id="e5f46-109">会员组织者可以获得 PIN 码，以便他们启动会议。</span><span class="sxs-lookup"><span data-stu-id="e5f46-109">PINs are given to a meeting organizer that allows them to start a meeting.</span></span> <span data-ttu-id="e5f46-110">然而，您也可以将其设置为无需 PIN 即可启动会议。</span><span class="sxs-lookup"><span data-stu-id="e5f46-110">However, you can set it up so a PIN isn't required to start a meeting.</span></span>

## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="e5f46-111">设置呼叫者是否应录制其姓名</span><span class="sxs-lookup"><span data-stu-id="e5f46-111">Set whether callers should record their name</span></span>
    
1. <span data-ttu-id="e5f46-112">在 **Skype for Business 管理中心**中的左侧导航中，转到 **音频会议** > **Microsoft 桥接设置**。</span><span class="sxs-lookup"><span data-stu-id="e5f46-112">In the **Skype for Business admin center**, in the left navigation go to **Dial-in conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="e5f46-113">在 **会议的与会体验**中，请参阅标记为**打开启用会议加入和退出通知**的复选框。</span><span class="sxs-lookup"><span data-stu-id="e5f46-113">Under **Meeting join experience**, see the check box labeled **Enable meeting entry and exit notifications to be turned on**.</span></span>
    
  - <span data-ttu-id="e5f46-114">**选中** 要求呼叫者在进入会议之前记录其姓名。</span><span class="sxs-lookup"><span data-stu-id="e5f46-114">**Checked** Callers will be asked to record their name before they enter the meeting.</span></span> <span data-ttu-id="e5f46-115">默认情况下，此选项处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="e5f46-115">This is selected by default.</span></span>
    
  - <span data-ttu-id="e5f46-116">**未选中** 不要求呼叫者在进入会议之前记录其姓名。</span><span class="sxs-lookup"><span data-stu-id="e5f46-116">**Unchecked** Callers won't be asked to record their name before they enter the meeting.</span></span>
    
3. <span data-ttu-id="e5f46-117">完成更改后，单击 **保存**。</span><span class="sxs-lookup"><span data-stu-id="e5f46-117">After you make your changes, click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="e5f46-118">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="e5f46-118">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="e5f46-119">为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e5f46-119">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
-  <span data-ttu-id="e5f46-120">Windows PowerShell 的功能是管理用户以及允许用户执行的操作。</span><span class="sxs-lookup"><span data-stu-id="e5f46-120">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="e5f46-121">使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="e5f46-121">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="e5f46-122">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="e5f46-122">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e5f46-123">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5f46-123">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="e5f46-124">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="e5f46-124">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="e5f46-125">与仅使用 Office 365 管理中心相比，Windows PowerShell 在速度、简化和工作效率方面具有许多优点，例如，当一次更改许多用户的设置时。</span><span class="sxs-lookup"><span data-stu-id="e5f46-125">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="e5f46-126">请在以下主题中了解这些优点：</span><span class="sxs-lookup"><span data-stu-id="e5f46-126">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="e5f46-127">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="e5f46-127">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="e5f46-128">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e5f46-128">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="e5f46-129">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="e5f46-129">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="e5f46-p106">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="e5f46-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e5f46-132">相关主题</span><span class="sxs-lookup"><span data-stu-id="e5f46-132">Related topics</span></span>

[<span data-ttu-id="e5f46-133">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="e5f46-133">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
