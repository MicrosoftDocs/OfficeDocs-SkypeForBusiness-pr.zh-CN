---
title: "使用户能够在加入会议时录制其姓名"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to enable or disable whether your users can record their names when they join a meeting '
ms.openlocfilehash: f07bb24530e7b59ab6f54dfe2cd4eadf91def20c
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2017
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting"></a><span data-ttu-id="5bd57-103">使用户能够在加入会议时录制其姓名</span><span class="sxs-lookup"><span data-stu-id="5bd57-103">Enable users to record their name when they join a meeting</span></span>

<span data-ttu-id="5bd57-104">当您设置 Office 365 中的音频会议时，您将收到的电话号码和所谓的音频会议桥。</span><span class="sxs-lookup"><span data-stu-id="5bd57-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers and what is called an audio conferencing bridge.</span></span> <span data-ttu-id="5bd57-105">会议桥可以包含一个或多个可以是专用或共享电话号码的电话号码。</span><span class="sxs-lookup"><span data-stu-id="5bd57-105">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="5bd57-106">会议桥的会议使用电话拨入用户应答呼叫。</span><span class="sxs-lookup"><span data-stu-id="5bd57-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="5bd57-107">会议桥从自动助理，回答带语音提示的调用方，然后，根据其设置中，可以播放通知，要求调用方记录其姓名，并对会议组织者针安全设置。</span><span class="sxs-lookup"><span data-stu-id="5bd57-107">The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers.</span></span> <span data-ttu-id="5bd57-108">向会议组织者提供的针脚，让他们可以开始会议。</span><span class="sxs-lookup"><span data-stu-id="5bd57-108">PINs are given to meeting organizers to allow them to start a meeting.</span></span> <span data-ttu-id="5bd57-109">但是，您可以设置它以便 PIN 不需要召开会议。</span><span class="sxs-lookup"><span data-stu-id="5bd57-109">However, you can set it up so a PIN isn't required to start a meeting.</span></span>
  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="5bd57-110">设置呼叫者是否应录制其姓名</span><span class="sxs-lookup"><span data-stu-id="5bd57-110">Set whether callers should record their name</span></span>

1. <span data-ttu-id="5bd57-111">使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="5bd57-111">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="5bd57-112">请转到**Office 365 管理中心** > **业务的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="5bd57-112">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="5bd57-113">在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议** > **Microsoft 网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="5bd57-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="5bd57-114">在**会议连接体验**，请参阅**启用会议进入和退出通知以打开**标记的复选框。</span><span class="sxs-lookup"><span data-stu-id="5bd57-114">Under **Meeting join experience**, see the check box labeled **Enable meeting entry and exit notifications to be turned on**.</span></span>
    
  - <span data-ttu-id="5bd57-115">**选择**将要求调用方才能进入会议记录他们的姓名。</span><span class="sxs-lookup"><span data-stu-id="5bd57-115">**Selected** Callers will be asked to record their name before they enter the meeting.</span></span> <span data-ttu-id="5bd57-116">默认情况下选择此选项。</span><span class="sxs-lookup"><span data-stu-id="5bd57-116">This is selected by default.</span></span>
    
  - <span data-ttu-id="5bd57-117">**清除**调用方不需要记下其名称才能进入会议。</span><span class="sxs-lookup"><span data-stu-id="5bd57-117">**Cleared** Callers won't be asked to record their name before they enter the meeting.</span></span>
    
5. <span data-ttu-id="5bd57-118">完成更改后，单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="5bd57-118">After you make your changes, click **Save**.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="5bd57-119">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="5bd57-119">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="5bd57-120">为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5bd57-120">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
-  <span data-ttu-id="5bd57-121">所有有关管理用户和哪些用户有权执行此是 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="5bd57-121">Windows PowerShell is all about managing users and what users are allowed to do.</span></span> <span data-ttu-id="5bd57-122">使用 Windows PowerShell 可以管理 Office 365 使用单点管理，可以简化您的日常工作时必须要执行多个任务。</span><span class="sxs-lookup"><span data-stu-id="5bd57-122">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="5bd57-123">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="5bd57-123">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5bd57-124">为什么需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="5bd57-124">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="5bd57-125">使用 Windows PowerShell 管理 Office 365 的最佳方法</span><span class="sxs-lookup"><span data-stu-id="5bd57-125">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="5bd57-p105">Windows PowerShell 许多相比具有的优势在速度、 简易性和生产率仅使用 Office 365 管理中心，例如，当将设置更改为许多用户一次。了解这些优势中的以下主题：</span><span class="sxs-lookup"><span data-stu-id="5bd57-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="5bd57-128">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="5bd57-128">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="5bd57-129">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="5bd57-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="5bd57-130">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="5bd57-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="5bd57-p106">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="5bd57-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="5bd57-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="5bd57-133">Related topics</span></span>

[<span data-ttu-id="5bd57-134">设置 Skype for Business 和 Microsoft Teams 音频会议</span><span class="sxs-lookup"><span data-stu-id="5bd57-134">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)

