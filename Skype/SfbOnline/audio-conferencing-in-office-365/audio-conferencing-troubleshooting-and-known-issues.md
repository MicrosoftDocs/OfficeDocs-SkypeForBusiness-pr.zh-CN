---
title: 音频会议故障排除和已知问题
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 72979911-5319-4de2-a275-4dd9a0f44fe6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '使用 Microsoft 作为其电话拨入式会议提供程序、 状态和一些解决方法时，请获取已知问题的列表。 '
ms.openlocfilehash: 997cc5007df35b307cb714b891bc60764bd4a645
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229181"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a><span data-ttu-id="140d6-103">音频会议故障排除和已知问题</span><span class="sxs-lookup"><span data-stu-id="140d6-103">Audio Conferencing troubleshooting and known issues</span></span>

 <span data-ttu-id="140d6-104">**本文是 Skype 业务用户使用 Microsoft 作为其音频会议提供商。不适用于于使用第三方音频会议提供商 (ACP) 的客户。**</span><span class="sxs-lookup"><span data-stu-id="140d6-104">**This article is for Skype for Business users using Microsoft as their audio conferencing provider. It does not apply to customers who are using a third-party audio conferencing provider (ACP).**</span></span>
  
## <a name="troubleshooting-and-known-issues"></a><span data-ttu-id="140d6-105">疑难解答和已知问题</span><span class="sxs-lookup"><span data-stu-id="140d6-105">Troubleshooting and known issues</span></span>

<span data-ttu-id="140d6-106">使用 Microsoft 的音频会议提供程序具有当前是正在跟踪，主动调查，会在未来更新功能时可能会解决的问题的音频会议的 Office 365 版本。</span><span class="sxs-lookup"><span data-stu-id="140d6-106">Audio Conferencing that uses Microsoft as the audio conferencing provider has current issues that are being tracked and actively investigated and will be potentially resolved when the feature is updated in future releases of Office 365.</span></span>
  
<span data-ttu-id="140d6-107">现在时, 使用此参考解决潜在问题获取音频会议设置和使用 Skype for Business 组织中的人员的工作。</span><span class="sxs-lookup"><span data-stu-id="140d6-107">For now, use this as a reference when you are troubleshooting potential issues with getting Audio Conferencing set up and working for the people using Skype for Business in your organization.</span></span>

|<span data-ttu-id="140d6-108">**问题**</span><span class="sxs-lookup"><span data-stu-id="140d6-108">**Issue**</span></span>|<span data-ttu-id="140d6-109">**行为/症状**</span><span class="sxs-lookup"><span data-stu-id="140d6-109">**Behavior/Symptoms**</span></span>|<span data-ttu-id="140d6-110">**已知解决方法**</span><span class="sxs-lookup"><span data-stu-id="140d6-110">**Known workaround**</span></span>|<span data-ttu-id="140d6-111">**发现日期**</span><span class="sxs-lookup"><span data-stu-id="140d6-111">**Discovery date**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="140d6-112">进入和退出通知时启动会议，但他们正在关闭不久后打开在会议开始。</span><span class="sxs-lookup"><span data-stu-id="140d6-112">Entry and exit notifications are turned on when a meeting starts, but they're turned off shortly after the meeting starts.</span></span>  <br/> |<span data-ttu-id="140d6-113">默认情况下，其中两个 Skype 业务应用程序中的参与者加入和时拨入时进入和退出通知的会议中禁用。</span><span class="sxs-lookup"><span data-stu-id="140d6-113">By default, entry and exit notifications are disabled for meetings where participants join from both Skype for Business apps and when they dial in.</span></span> <span data-ttu-id="140d6-114">您可以在**Skype 会议选项**中的企业应用程序 Skype 通知。</span><span class="sxs-lookup"><span data-stu-id="140d6-114">You can enable the announcements in the **Skype Meeting Options** in the Skype for Business app.</span></span> <span data-ttu-id="140d6-115">对于所有参与者拨入加入的会议，默认情况下会启用进入和退出通知，因为任何参与者都无法获得参与者名单。</span><span class="sxs-lookup"><span data-stu-id="140d6-115">For a meeting where all participants dial in and join a meeting, entry and exit notifications are enabled by default as the participant roster isn't available to any participant.</span></span> <span data-ttu-id="140d6-116">当会议已开始仅调用条目中的参与者和退出通知将打开，但时为业务应用程序使用 Skype 参与者加入，通知将关闭。</span><span class="sxs-lookup"><span data-stu-id="140d6-116">When a meeting has started with only participants calling in, the entry and exit notifications will be turned on, but when a participant joins using a Skype for Business app, the notifications will be turned off.</span></span> <span data-ttu-id="140d6-117">关闭时，可以在 Skype 后使用**Skype 会议选项**，业务应用程序启用通知。</span><span class="sxs-lookup"><span data-stu-id="140d6-117">When turned off, the notifications can be enabled back using **Skype Meeting Options** in the Skype for Business app.</span></span> <br/> |<span data-ttu-id="140d6-118">无解决方法。</span><span class="sxs-lookup"><span data-stu-id="140d6-118">No workaround.</span></span>  <br/> |<span data-ttu-id="140d6-119">8/30/2017</span><span class="sxs-lookup"><span data-stu-id="140d6-119">8/30/2017</span></span>  <br/> |
|<span data-ttu-id="140d6-120">如果用户已由其分配一个 E5 许可证设置第一次、，有可能为音频会议欢迎电子邮件未传送到用户如果没有启用邮箱。</span><span class="sxs-lookup"><span data-stu-id="140d6-120">If a user is provisioned the first time by being assigned an E5 license, it might be possible for the Audio Conferencing welcome email to not be delivered to the user if the mailbox isn't enabled.</span></span>  <br/> |<span data-ttu-id="140d6-121">如果发生这种情况，始终可以重新发送业务管理中心的 Skype 中使用**音频会议**或使用 PowerShell 的用户的音频会议信息。</span><span class="sxs-lookup"><span data-stu-id="140d6-121">If this happens, you can always resend the audio conferencing information of the user using **Audio conferencing** in the Skype for Business admin center or using PowerShell.</span></span> <span data-ttu-id="140d6-122">请参阅[启用或禁用发送电子邮件时要进行音频会议设置更改](enable-or-disable-sending-emails-when-their-settings-change.md)。</span><span class="sxs-lookup"><span data-stu-id="140d6-122">See [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>  <br/> <span data-ttu-id="140d6-123">**注意：** 若要重新发送给用户的音频会议 PIN，PIN 具有要重置。</span><span class="sxs-lookup"><span data-stu-id="140d6-123">**Note:** In order to resend the audio conferencing PIN to the user, the PIN has to be reset.</span></span> <span data-ttu-id="140d6-124">这也可以通过在业务管理中心的 Skype 中使用**音频会议**或通过使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="140d6-124">This can also be done by using **Audio conferencing** in the Skype for Business admin center or by using PowerShell.</span></span>          |<span data-ttu-id="140d6-125">无解决方法。</span><span class="sxs-lookup"><span data-stu-id="140d6-125">No workaround.</span></span>  <br/> |<span data-ttu-id="140d6-126">8/30/2017</span><span class="sxs-lookup"><span data-stu-id="140d6-126">8/30/2017</span></span>  <br/> |
|<span data-ttu-id="140d6-127">音频会议呼叫可能需要 24 小时的使用率报告中显示。</span><span class="sxs-lookup"><span data-stu-id="140d6-127">Audio conferencing calls could take up to 24 hours to show in the usage reports.</span></span>  <br/> |<span data-ttu-id="140d6-128">我们期待于在将来的服务更新，以使在这方面的改进。</span><span class="sxs-lookup"><span data-stu-id="140d6-128">We're looking forward to making improvements on this area in future service updates.</span></span>  <br/> |<span data-ttu-id="140d6-129">无解决方法。</span><span class="sxs-lookup"><span data-stu-id="140d6-129">No workaround.</span></span>  <br/> |<span data-ttu-id="140d6-130">8/30/2017</span><span class="sxs-lookup"><span data-stu-id="140d6-130">8/30/2017</span></span>  <br/> |
|<span data-ttu-id="140d6-131">当呼叫者拨入的会议桥业务用户 Skype 已锁定会议后时，没有的通知中的业务应用程序指出 Skype 等待用户对会议厅中。</span><span class="sxs-lookup"><span data-stu-id="140d6-131">When a caller dials in to a conference bridge after the meeting has been locked by a Skype for Business user, there isn't a notification in the Skype for Business app stating that the user is waiting in the lobby.</span></span>  <br/> |<span data-ttu-id="140d6-132">当前此设置是特意为之，但我们会考虑此反馈以便在未来的服务更新中支持此功能。</span><span class="sxs-lookup"><span data-stu-id="140d6-132">This is currently by design, but we've taken the feedback in regard to supporting this capability in future service updates.</span></span>  <br/> |<span data-ttu-id="140d6-133">无解决方法。</span><span class="sxs-lookup"><span data-stu-id="140d6-133">No workaround.</span></span>  <br/> |<span data-ttu-id="140d6-134">8/30/2017</span><span class="sxs-lookup"><span data-stu-id="140d6-134">8/30/2017</span></span>  <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="140d6-135">相关主题</span><span class="sxs-lookup"><span data-stu-id="140d6-135">Related topics</span></span>

[<span data-ttu-id="140d6-136">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="140d6-136">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
