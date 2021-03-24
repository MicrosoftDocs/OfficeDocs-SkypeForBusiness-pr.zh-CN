---
title: 管理 Microsoft Teams 会议室的 Windows 更新
ms.author: v-cichur
author: cichur
ms.reviewer: sohailta
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: 管理 Microsoft Teams 会议室的 Windows 更新
ms.openlocfilehash: cb3007acd31f84cedb8996f440b9634f0551f638
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103198"
---
# <a name="manage-windows-updates"></a><span data-ttu-id="6c69e-103">管理 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="6c69e-103">Manage Windows Updates</span></span>

<span data-ttu-id="6c69e-104">Microsoft Teams 会议室在 Windows 10 企业版 IoT 或 Windows 10 企业版 (VL) 并接收与标准桌面相同的 Windows 更新和操作系统版本。</span><span class="sxs-lookup"><span data-stu-id="6c69e-104">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span>

<span data-ttu-id="6c69e-105">可通过几种不同的方式管理 Windows 更新：</span><span class="sxs-lookup"><span data-stu-id="6c69e-105">Windows Updates can be managed in a few different ways:</span></span>

## <a name="hands-off-approach"></a><span data-ttu-id="6c69e-106">动手方法</span><span class="sxs-lookup"><span data-stu-id="6c69e-106">Hands-off approach</span></span> 
- <span data-ttu-id="6c69e-107">更新可以直接从 Windows 更新自动下载，在非工作时间安装。</span><span class="sxs-lookup"><span data-stu-id="6c69e-107">Updates can be downloaded directly from Windows Updates automatically and installed during off-hours.</span></span> <span data-ttu-id="6c69e-108">如果未对配置做出任何更改，则这是默认状态。</span><span class="sxs-lookup"><span data-stu-id="6c69e-108">If no change is made to configuration this is the default state.</span></span>
- <span data-ttu-id="6c69e-109">不可延迟的更新将自动安装第一天发布。</span><span class="sxs-lookup"><span data-stu-id="6c69e-109">Non-deferrable Updates will install day-one of release automatically.</span></span> 
- <span data-ttu-id="6c69e-110">质量更新和驱动程序将自动下载并安装第一天。</span><span class="sxs-lookup"><span data-stu-id="6c69e-110">Quality Updates and drivers will download and install day-one automatically.</span></span> 
- <span data-ttu-id="6c69e-111">功能更新。</span><span class="sxs-lookup"><span data-stu-id="6c69e-111">Feature Updates.</span></span> <span data-ttu-id="6c69e-112">请参阅下面的其他说明。</span><span class="sxs-lookup"><span data-stu-id="6c69e-112">See additional notes below.</span></span> 

## <a name="windows-updates-for-business-gpo-or-intune"></a><span data-ttu-id="6c69e-113">[适用于 Business 的 Windows](/windows/deployment/update/waas-manage-updates-wufb) (GPO 或 Intune) </span><span class="sxs-lookup"><span data-stu-id="6c69e-113">[Windows Updates for Business](/windows/deployment/update/waas-manage-updates-wufb) (GPO or Intune)</span></span>   
- <span data-ttu-id="6c69e-114">更新从 WU 或 WSUS 下载，但配置的延迟已过 KB 的原始发布日期。</span><span class="sxs-lookup"><span data-stu-id="6c69e-114">Updates are downloaded from WU or your WSUS but with configured delays past the KB’s original release date.</span></span> 
- <span data-ttu-id="6c69e-115">结合多个 OU 或筛选的策略，这允许创建部署"圈"，其中管理员可以指定哪些设备首先安装质量更新，哪些设备将在以后安装。</span><span class="sxs-lookup"><span data-stu-id="6c69e-115">Combined with multiple OU’s or filtered policies, this allows for the creation of deployment “rings”, where administrators can specify which devices install Quality Updates first and which ones will install later.</span></span> <span data-ttu-id="6c69e-116">这允许在整个部署中推出更新之前，对部分系统进行可靠性和性能测试，而无需在 Microsoft Endpoint Configuration Manager 中管理 Windows 更新等开销。</span><span class="sxs-lookup"><span data-stu-id="6c69e-116">This allows for reliability and performance testing on a subset of systems before rolling out updates across the entire deployment without the overhead of managing Windows Updates in Microsoft Endpoint Configuration Manager for example.</span></span>
- <span data-ttu-id="6c69e-117">如果你同时需要带宽管理和适用于 Business 的[](/windows/deployment/update/waas-integrate-wufb)Windows 更新提供的控制，可以同时配置适用于 Business 的 WSUS 和 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="6c69e-117">WSUS and Windows Updates for Business can be [configured at the same time](/windows/deployment/update/waas-integrate-wufb) if you desire both bandwidth management and the control Windows Updates for Business provides.</span></span>
- <span data-ttu-id="6c69e-118">功能更新。</span><span class="sxs-lookup"><span data-stu-id="6c69e-118">Feature updates.</span></span> <span data-ttu-id="6c69e-119">请参阅下面的其他说明。</span><span class="sxs-lookup"><span data-stu-id="6c69e-119">See additional notes below.</span></span>

## <a name="wsusconfiguration-manager"></a>[<span data-ttu-id="6c69e-120">WSUS/Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="6c69e-120">WSUS/Configuration Manager</span></span>](/windows/deployment/update/waas-manage-updates-configuration-manager)
- <span data-ttu-id="6c69e-121">与适用于 Business 的 Windows 更新很类似，但具有用于在每个"圈"或整个部署中定位特定 KB 的其他选项。</span><span class="sxs-lookup"><span data-stu-id="6c69e-121">Much like Windows Update for Business, but with the additional option of targeting specific KB's within each "ring" or the entire deployment.</span></span> <span data-ttu-id="6c69e-122">可以立即单独部署和测试每个更新，而不是仅依赖延迟。</span><span class="sxs-lookup"><span data-stu-id="6c69e-122">Each Update can be individually deployed and tested at will, rather than relying on only a delay.</span></span> 
- <span data-ttu-id="6c69e-123">功能更新。</span><span class="sxs-lookup"><span data-stu-id="6c69e-123">Feature updates.</span></span> <span data-ttu-id="6c69e-124">请参阅下面的其他说明。</span><span class="sxs-lookup"><span data-stu-id="6c69e-124">See additional notes below.</span></span>


### <a name="feature-updates"></a><span data-ttu-id="6c69e-125">功能更新</span><span class="sxs-lookup"><span data-stu-id="6c69e-125">Feature updates</span></span>

<span data-ttu-id="6c69e-126">与质量和不可延迟更新不同，Windows 10"功能更新" (主要操作系统版本) 仅在 Microsoft 测试和验证 Microsoft Teams 会议室的给定更新功能后安装。</span><span class="sxs-lookup"><span data-stu-id="6c69e-126">Unlike Quality and Non-Deferable updates, Windows 10 "Feature Updates" (major OS releases) will only be installed after Microsoft tests and validates a given updates functionality with Microsoft Teams Rooms.</span></span> <span data-ttu-id="6c69e-127">即使你将系统设置为该通道以测试) 甚至由你自己的尝试或配置手动推送Semi-Annual Channel (或 Targeted，它也不允许安装，直到我们端上的块被删除。</span><span class="sxs-lookup"><span data-stu-id="6c69e-127">Even if it is released to the Semi-Annual Channel (or Targeted if you have systems set to that channel for testing) or even manually pushed by your own attempts or configurations, it will not allow the installation until the block on our end is removed.</span></span>

<span data-ttu-id="6c69e-128">Microsoft Teams 会议室"开箱即用"使用"方法，将不会由于 Windows 更新而自动安装 Windows 更新或重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="6c69e-128">Microsoft Teams Room "out-of-box", using the hands off approach, will not install a Windows Update or reboot a device automatically because of a Windows Update.</span></span> <span data-ttu-id="6c69e-129">但是，系统可能会下载更新并等待下一次重启进行安装。</span><span class="sxs-lookup"><span data-stu-id="6c69e-129">Systems may, however, download an update and wait for the next reboot to install it.</span></span> <span data-ttu-id="6c69e-130">除非有人手动重新启动，否则安装应在自动夜间重启时执行。</span><span class="sxs-lookup"><span data-stu-id="6c69e-130">Unless someone reboots it manually, installation should happen at the automatic nightly reboot.</span></span> <span data-ttu-id="6c69e-131">Windows 更新在聊天室中应该是透明的，并且 WINDOWS 更新永远不应中断 UI。</span><span class="sxs-lookup"><span data-stu-id="6c69e-131">Windows Updates should be transparent in the room, the UI should never be interrupted by Windows Updates.</span></span>

<span data-ttu-id="6c69e-132">如果选择加入域，请使用 Microsoft Endpoint Configuration Manager 或 WSUS，请特别注意可能会导致设备在营业时间安装更新或强制重启的策略或操作。</span><span class="sxs-lookup"><span data-stu-id="6c69e-132">If you choose to domain join, use Microsoft Endpoint Configuration Manager or WSUS, and please pay special attention to policies or actions that may result in the device installing an update or forcing a reboot during business hours.</span></span> <span data-ttu-id="6c69e-133">如果你在使用期间在部署中重新启动系统，或者通过 UI 警告 Windows 更新，你将希望查看你的配置。</span><span class="sxs-lookup"><span data-stu-id="6c69e-133">If you have systems in your deployment rebooting during use or alerting about Windows Updates over the UI, you will want to look into your configuration.</span></span>