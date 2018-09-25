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
ms.openlocfilehash: 8583ca92de2544946eb898d128e423b6df62cb24
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25012934"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-microsoft-teams"></a><span data-ttu-id="8d42d-103">在 Microsoft Teams 中让用户能够在加入会议时录制其姓名</span><span class="sxs-lookup"><span data-stu-id="8d42d-103">Enable users to record their name when they join a meeting in Microsoft Teams</span></span>

<span data-ttu-id="8d42d-104">当您要设置 Office 365 中的音频会议时，您将收到电话号码和所谓音频会议桥。</span><span class="sxs-lookup"><span data-stu-id="8d42d-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers and what is called an audio conferencing bridge.</span></span> <span data-ttu-id="8d42d-105">会议网桥可以包含一个或多个电话号码，这些号码可以是专用或共享电话号码。</span><span class="sxs-lookup"><span data-stu-id="8d42d-105">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="8d42d-106">会议网桥负责应答使用电话拨入会议的用户的呼叫。</span><span class="sxs-lookup"><span data-stu-id="8d42d-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="8d42d-107">会议桥的自动助理，从接听呼叫者使用语音提示，然后，具体取决于其设置，可以播放通知，向呼叫者提出记录其姓名，并对会议组织者 PIN 安全设置。</span><span class="sxs-lookup"><span data-stu-id="8d42d-107">The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers.</span></span> <span data-ttu-id="8d42d-108">旋转中心点分发给会议组织者，以允许其开始会议。</span><span class="sxs-lookup"><span data-stu-id="8d42d-108">PINs are given to meeting organizers to allow them to start a meeting.</span></span> <span data-ttu-id="8d42d-109">然而，你也可以将其设置为无需 PIN 即可启动会议。</span><span class="sxs-lookup"><span data-stu-id="8d42d-109">However, you can set it up so a PIN isn't required to start a meeting.</span></span>

  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="8d42d-110">设置呼叫者是否应录制其姓名</span><span class="sxs-lookup"><span data-stu-id="8d42d-110">Set whether callers should record their name</span></span>

1. <span data-ttu-id="8d42d-111">在 Microsoft 团队和 Skype 的业务管理中心，在左侧导航窗格中，转到**会议** > **会议桥**。</span><span class="sxs-lookup"><span data-stu-id="8d42d-111">In the Microsoft Teams & Skype for Business Admin Center, in the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="8d42d-112">在“**会议网桥**”页面顶部，单击“**网桥设置**”。</span><span class="sxs-lookup"><span data-stu-id="8d42d-112">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="8d42d-113">启用或禁用“**会议进入和退出通知**”。</span><span class="sxs-lookup"><span data-stu-id="8d42d-113">Enable or disable **Meeting entry and exit notifications**.</span></span>

4. <span data-ttu-id="8d42d-114">如果启用通知，请选择“**进入/退出公告类型**”下的“**姓名或电话号码**”，然后开启“**要求呼叫者在加入会议之前录制其姓名**”。</span><span class="sxs-lookup"><span data-stu-id="8d42d-114">If enabling notifications, choose **Names or phone numbers** under **Entry/exit announcement type**, and then turn on **Ask callers to record their name before joining a meeting.**</span></span>

6. <span data-ttu-id="8d42d-115">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="8d42d-115">Click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="8d42d-116">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="8d42d-116">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="8d42d-p103">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="8d42d-p103">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="8d42d-120">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d42d-120">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="8d42d-121">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="8d42d-121">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="8d42d-122">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="8d42d-122">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="8d42d-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="8d42d-123">Related topics</span></span>

[<span data-ttu-id="8d42d-124">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="8d42d-124">Try or purchase Audio Conferencing in Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
