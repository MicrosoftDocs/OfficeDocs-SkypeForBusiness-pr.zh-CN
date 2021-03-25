---
title: 允许用户在 Skype for Business Online 中加入会议时录制其姓名
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 了解如何在 Skype for Business Online 中加入会议时启用或禁用用户是否可以录制其姓名。
ms.openlocfilehash: 7fd8afb71ee524b20f24f9583ec847adbec2ff43
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114238"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a><span data-ttu-id="6c731-103">允许用户在 Skype for Business Online 中加入会议时录制其姓名</span><span class="sxs-lookup"><span data-stu-id="6c731-103">Enable users to record their name when they join a meeting in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="6c731-104">如果您希望允许用户在 Teams 中记录他们的姓名，请参阅[  允许用户在加入 Microsoft Teams 中的会议时记录他们的姓名](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams) 。</span><span class="sxs-lookup"><span data-stu-id="6c731-104">If you want to allow users to record their names in Teams, see [Enable users to record their name when they join a meeting in Microsoft Teams](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams).</span></span>

<span data-ttu-id="6c731-105">在 Microsoft 365 或 Office 365 中设置音频会议时，将收到电话号码和音频会议网桥。</span><span class="sxs-lookup"><span data-stu-id="6c731-105">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will receive phone numbers and what is called an audio conferencing bridge.</span></span> <span data-ttu-id="6c731-106">会议网桥可以包含一个或多个电话号码，这些号码可以是专用或共享电话号码。</span><span class="sxs-lookup"><span data-stu-id="6c731-106">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="6c731-107">会议网桥负责应答使用电话拨入会议的用户的呼叫。</span><span class="sxs-lookup"><span data-stu-id="6c731-107">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="6c731-108">会议网桥通过来自自动助理的语音提示来应答呼叫者，然后，根据他们的设置，可以播放通知、让呼叫者录制其姓名，以及为会议组织者设置 PIN 安全性。</span><span class="sxs-lookup"><span data-stu-id="6c731-108">The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers.</span></span> <span data-ttu-id="6c731-109">PIN 被赋予会议组织者，以便他们启动会议。</span><span class="sxs-lookup"><span data-stu-id="6c731-109">PINs are given to meeting organizers to allow them to start a meeting.</span></span> <span data-ttu-id="6c731-110">然而，你也可以将其设置为无需 PIN 即可启动会议。</span><span class="sxs-lookup"><span data-stu-id="6c731-110">However, you can set it up so a PIN isn't required to start a meeting.</span></span>

## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="6c731-111">设置呼叫者是否应录制其姓名</span><span class="sxs-lookup"><span data-stu-id="6c731-111">Set whether callers should record their name</span></span>
    
1. <span data-ttu-id="6c731-112">在 **Skype for Business 管理中心的** 左侧导航中，转到"**音频会议**  >  **""Microsoft 网桥设置"。**</span><span class="sxs-lookup"><span data-stu-id="6c731-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="6c731-113">在 **会议的与会体验** 中，请参阅标记为 **打开启用会议加入和退出通知** 的复选框。</span><span class="sxs-lookup"><span data-stu-id="6c731-113">Under **Meeting join experience**, see the check box labeled **Enable meeting entry and exit notifications to be turned on**.</span></span>
    
   - <span data-ttu-id="6c731-114">**已选择** 呼叫者进入会议之前，将要求他们录制其姓名。</span><span class="sxs-lookup"><span data-stu-id="6c731-114">**Selected** Callers will be asked to record their name before they enter the meeting.</span></span> <span data-ttu-id="6c731-115">默认情况下，此选项处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="6c731-115">This is selected by default.</span></span>
    
   - <span data-ttu-id="6c731-116">**已清除** 呼叫者在进入会议之前不会要求他们录制其姓名。</span><span class="sxs-lookup"><span data-stu-id="6c731-116">**Cleared** Callers won't be asked to record their name before they enter the meeting.</span></span>
    
3. <span data-ttu-id="6c731-117">完成更改后，单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="6c731-117">After you make your changes, click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="6c731-118">想知道如何使用 Windows PowerShell 进行管理吗？</span><span class="sxs-lookup"><span data-stu-id="6c731-118">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="6c731-119">为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6c731-119">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) cmdlet.</span></span>
    
- <span data-ttu-id="6c731-120">Windows PowerShell管理用户以及允许用户执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="6c731-120">Windows PowerShell is all about managing users and what users are allowed to do.</span></span> <span data-ttu-id="6c731-121">使用Windows PowerShell，您可以使用单点管理来管理 Microsoft 365 或 Office 365，当您有多个任务需要执行时，可以简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="6c731-121">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="6c731-122">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="6c731-122">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="6c731-123">为何需要使用 Microsoft 365 或 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="6c731-123">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="6c731-124">[使用 Office 365 管理 Microsoft 365 或 Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="6c731-124">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="6c731-125">Windows PowerShell比仅使用 Microsoft 365 管理中心具有许多速度、简单性和工作效率优势，例如，一次对多个用户进行设置更改时。</span><span class="sxs-lookup"><span data-stu-id="6c731-125">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="6c731-126">请在以下主题中了解这些优点：</span><span class="sxs-lookup"><span data-stu-id="6c731-126">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="6c731-127">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="6c731-127">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="6c731-128">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6c731-128">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="6c731-129">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="6c731-129">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="6c731-p106">[!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。</span><span class="sxs-lookup"><span data-stu-id="6c731-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="6c731-132">相关主题</span><span class="sxs-lookup"><span data-stu-id="6c731-132">Related topics</span></span>

[<span data-ttu-id="6c731-133">在 Microsoft 365 或 Office 365 中试用或购买音频会议</span><span class="sxs-lookup"><span data-stu-id="6c731-133">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)