---
title: 打开或关闭条目和退出通知中的 Microsoft 团队会议
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
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解如何启用条目并退出 Microsoft 团队会议中的打开或关闭通知。 '
ms.openlocfilehash: 44b3c88b9e4284c7606d57661022dbe21d236147
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23851004"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a><span data-ttu-id="be179-103">打开或关闭条目和退出通知中的 Microsoft 团队会议</span><span class="sxs-lookup"><span data-stu-id="be179-103">Turn on or off entry and exit announcements for meetings in Microsoft Teams</span></span>

<span data-ttu-id="be179-104">当设置 Office 365 中的音频会议时，您将看到音频会议桥。</span><span class="sxs-lookup"><span data-stu-id="be179-104">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="be179-105">会议桥可以包含一个或多个人员将用于向 Microsoft 团队会议呼叫中的电话号码。</span><span class="sxs-lookup"><span data-stu-id="be179-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Microsoft Teams meeting.</span></span> 
  
<span data-ttu-id="be179-106">会议网桥负责应答使用电话拨入会议的用户的呼叫。</span><span class="sxs-lookup"><span data-stu-id="be179-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="be179-107">会议桥应答来自会议自动助理的呼叫者使用语音提示并随后，具体取决于您的设置，可以播放通知，向呼叫者提出记录其姓名，并设置 PIN 安全。</span><span class="sxs-lookup"><span data-stu-id="be179-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="be179-108">PIN 赋予的 Microsoft 团队会议组织者，并允许其开始会议，如果它们无法启动会议使用 Microsoft 团队应用程序。</span><span class="sxs-lookup"><span data-stu-id="be179-108">A PIN is given to a Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Microsoft Teams app.</span></span> <span data-ttu-id="be179-109">但是，可以将它以便启动会议不需要 PIN。</span><span class="sxs-lookup"><span data-stu-id="be179-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="be179-110">设置会议加入选项</span><span class="sxs-lookup"><span data-stu-id="be179-110">Setting meeting join options</span></span>

1. <span data-ttu-id="be179-111">在左侧导航窗格中，转到**会议** > **会议桥**。</span><span class="sxs-lookup"><span data-stu-id="be179-111">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="be179-112">在**会议桥**页的顶部，单击**网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="be179-112">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="be179-113">在**桥设置**窗格中，启用或禁用**会议项和退出通知**。</span><span class="sxs-lookup"><span data-stu-id="be179-113">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span> <span data-ttu-id="be179-114">默认情况下，此选项处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="be179-114">This is selected by default.</span></span> <span data-ttu-id="be179-115">如果清除它，某人进入或离开会议时，已加入会议的用户不会将收到通知。</span><span class="sxs-lookup"><span data-stu-id="be179-115">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
4. <span data-ttu-id="be179-116">在**进入/退出公告类型**下，选择**姓名或电话号码** 或 **提示音**。</span><span class="sxs-lookup"><span data-stu-id="be179-116">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
5. <span data-ttu-id="be179-117">如果您选择**姓名或电话号码**，启用或禁用**Ask 呼叫者在记录其姓名之前加入会议**。</span><span class="sxs-lookup"><span data-stu-id="be179-117">If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.</span></span>
    
6. <span data-ttu-id="be179-118">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="be179-118">Click **Save**.</span></span>

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="be179-119">要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="be179-119">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="be179-p104">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="be179-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="be179-123">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="be179-123">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="be179-124">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="be179-124">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="be179-125">有关 Windows PowerShell 的详细信息，请参阅[Microsoft 团队 PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)（英文） 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="be179-125">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="be179-126">相关主题</span><span class="sxs-lookup"><span data-stu-id="be179-126">Related topics</span></span>

[<span data-ttu-id="be179-127">音频会议常见问题</span><span class="sxs-lookup"><span data-stu-id="be179-127">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
