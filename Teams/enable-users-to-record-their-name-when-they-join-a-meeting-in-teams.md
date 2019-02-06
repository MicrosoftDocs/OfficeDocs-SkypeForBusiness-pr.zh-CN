---
title: 在 Microsoft Teams 中让用户能够在加入会议时录制其姓名
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 了解如何在 Microsoft Teams 中启用或禁用用户是否可以在加入会议时录制其姓名。
ms.openlocfilehash: 36e55b4cbffe4f1f57771578104f426f705a5ecd
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754240"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-microsoft-teams"></a><span data-ttu-id="9a631-103">在 Microsoft Teams 中让用户能够在加入会议时录制其姓名</span><span class="sxs-lookup"><span data-stu-id="9a631-103">Enable users to record their name when they join a meeting in Microsoft Teams</span></span>

<span data-ttu-id="9a631-104">当你在 Office 365 中设置音频会议时，你将收到电话号码以及所谓的音频会议网桥。</span><span class="sxs-lookup"><span data-stu-id="9a631-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers and what is called an audio conferencing bridge.</span></span> <span data-ttu-id="9a631-105">会议网桥可以包含一个或多个电话号码，这些电话号码可以是专用或共享电话号码。</span><span class="sxs-lookup"><span data-stu-id="9a631-105">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="9a631-106">会议网桥负责应答使用电话拨入会议的用户的呼叫。</span><span class="sxs-lookup"><span data-stu-id="9a631-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="9a631-107">会议网桥通过来自自动助理的语音提示应答呼叫者，然后根据其设置，可以播放通知、让呼叫者录制其姓名以及为会议组织者设置 PIN 安全。</span><span class="sxs-lookup"><span data-stu-id="9a631-107">The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers.</span></span> <span data-ttu-id="9a631-108">将向会议组织者提供 PIN 以允许他们启动会议。</span><span class="sxs-lookup"><span data-stu-id="9a631-108">PINs are given to meeting organizers to allow them to start a meeting.</span></span> <span data-ttu-id="9a631-109">但你可以设置不需要使用 PIN 即可启动会议。</span><span class="sxs-lookup"><span data-stu-id="9a631-109">However, you can set it up so a PIN isn't required to start a meeting.</span></span>

  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="9a631-110">设置呼叫者是否应录制其姓名</span><span class="sxs-lookup"><span data-stu-id="9a631-110">Set whether callers should record their name</span></span>

<span data-ttu-id="9a631-111">![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**</span><span class="sxs-lookup"><span data-stu-id="9a631-111">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="9a631-112">在左侧导航中，转到“**会议**” > “**会议网桥**”。</span><span class="sxs-lookup"><span data-stu-id="9a631-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="9a631-113">在**会议桥**页的顶部，单击**网桥的设置**。</span><span class="sxs-lookup"><span data-stu-id="9a631-113">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="9a631-114">启用或禁用**会议项和退出通知**。</span><span class="sxs-lookup"><span data-stu-id="9a631-114">Enable or disable **Meeting entry and exit notifications**.</span></span>

4. <span data-ttu-id="9a631-115">如果启用通知，请选择**姓名或电话号码**下**条目/退出通知类型**，然后再打开**向呼叫者加入会议之前记录其姓名提出。**</span><span class="sxs-lookup"><span data-stu-id="9a631-115">If enabling notifications, choose **Names or phone numbers** under **Entry/exit announcement type**, and then turn on **Ask callers to record their name before joining a meeting.**</span></span>

6. <span data-ttu-id="9a631-116">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="9a631-116">Click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="9a631-117">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="9a631-117">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="9a631-p103">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="9a631-p103">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="9a631-121">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="9a631-121">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="9a631-122">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="9a631-122">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="9a631-123">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="9a631-123">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="9a631-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="9a631-124">Related topics</span></span>

[<span data-ttu-id="9a631-125">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="9a631-125">Try or purchase Audio Conferencing in Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
