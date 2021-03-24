---
title: 允许用户录制其会议名称
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
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 了解如何启用或禁用用户在 Microsoft Teams 中加入会议时是否可以录制其姓名。
ms.openlocfilehash: 8b92e0d4a73cc18ceaf374f1a05102e51752c083
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092690"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-microsoft-teams"></a><span data-ttu-id="3ea3c-103">在 Microsoft Teams 中让用户能够在加入会议时录制其姓名</span><span class="sxs-lookup"><span data-stu-id="3ea3c-103">Enable users to record their name when they join a meeting in Microsoft Teams</span></span>

<span data-ttu-id="3ea3c-104">在 Microsoft 365 或 Office 365 中设置音频会议时，将收到电话号码和音频会议网桥。</span><span class="sxs-lookup"><span data-stu-id="3ea3c-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will receive phone numbers and what is called an audio conferencing bridge.</span></span> <span data-ttu-id="3ea3c-105">会议网桥可以包含一个或多个电话号码，这些号码可以是专用或共享电话号码。</span><span class="sxs-lookup"><span data-stu-id="3ea3c-105">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="3ea3c-106">会议网桥负责应答使用电话拨入会议的用户的呼叫。</span><span class="sxs-lookup"><span data-stu-id="3ea3c-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="3ea3c-107">会议网桥通过来自自动助理的语音提示来应答呼叫者，然后，根据他们的设置，可以播放通知、让呼叫者录制其姓名，以及为会议组织者设置 PIN 安全性。</span><span class="sxs-lookup"><span data-stu-id="3ea3c-107">The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers.</span></span> <span data-ttu-id="3ea3c-108">PIN 被赋予会议组织者，以便他们启动会议。</span><span class="sxs-lookup"><span data-stu-id="3ea3c-108">PINs are given to meeting organizers to allow them to start a meeting.</span></span> <span data-ttu-id="3ea3c-109">然而，你也可以将其设置为无需 PIN 即可启动会议。</span><span class="sxs-lookup"><span data-stu-id="3ea3c-109">However, you can set it up so a PIN isn't required to start a meeting.</span></span>

  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="3ea3c-110">设置呼叫者是否应录制其姓名</span><span class="sxs-lookup"><span data-stu-id="3ea3c-110">Set whether callers should record their name</span></span>

<span data-ttu-id="3ea3c-111">![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="3ea3c-111">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="3ea3c-112">在左侧导航中，转到“**会议**” > “**会议网桥**”。</span><span class="sxs-lookup"><span data-stu-id="3ea3c-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="3ea3c-113">在"会议网桥"**页面顶部**，单击"**网桥设置"。**</span><span class="sxs-lookup"><span data-stu-id="3ea3c-113">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="3ea3c-114">启用或禁用 **会议进入和退出通知**。</span><span class="sxs-lookup"><span data-stu-id="3ea3c-114">Enable or disable **Meeting entry and exit notifications**.</span></span>

4. <span data-ttu-id="3ea3c-115">如果启用通知 **，请选择"** 进入 **/** 退出通知类型"下的"姓名"或"电话号码"，然后打开"让呼叫者在加入会议之前 **录制其姓名"。**</span><span class="sxs-lookup"><span data-stu-id="3ea3c-115">If enabling notifications, choose **Names or phone numbers** under **Entry/exit announcement type**, and then turn on **Ask callers to record their name before joining a meeting.**</span></span>

6. <span data-ttu-id="3ea3c-116">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="3ea3c-116">Click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="3ea3c-117">想要了解有关 Windows PowerShell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="3ea3c-117">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="3ea3c-118">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="3ea3c-118">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="3ea3c-119">使用Windows PowerShell，您可以使用单点管理来管理 Microsoft 365 或 Office 365，当您有多个任务需要执行时，可以简化日常工作。</span><span class="sxs-lookup"><span data-stu-id="3ea3c-119">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="3ea3c-120">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="3ea3c-120">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="3ea3c-121">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ea3c-121">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="3ea3c-122">[使用 Windows PowerShell 管理 Office 365 的最佳方式](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="3ea3c-122">[Best ways to manage Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="3ea3c-123">有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](/powershell/module/teams/?view=teams-ps)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="3ea3c-123">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="3ea3c-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="3ea3c-124">Related topics</span></span>

[<span data-ttu-id="3ea3c-125">尝试或购买音频会议</span><span class="sxs-lookup"><span data-stu-id="3ea3c-125">Try or purchase Audio Conferencing</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)