---
title: 管理 Microsoft 团队聊天室的 Windows 更新
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: 管理 Microsoft 团队聊天室的 Windows 更新
ms.openlocfilehash: 4ac80404acf507cafa038fe6a0cf667621f5b798
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288433"
---
# <a name="manage-windows-updates"></a><span data-ttu-id="332fd-103">管理 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="332fd-103">Manage Windows Updates</span></span>

<span data-ttu-id="332fd-104">Microsoft 团队聊天室在 Windows 10 企业版 IoT 或 Windows 10 企业版 (VL) 上运行, 并作为标准桌面接收相同的 Windows 更新和 OS 版本。</span><span class="sxs-lookup"><span data-stu-id="332fd-104">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span>

<span data-ttu-id="332fd-105">可通过几种不同的方式管理 Windows 更新:</span><span class="sxs-lookup"><span data-stu-id="332fd-105">Windows Updates can be managed in a few different ways:</span></span>

## <a name="hands-off-approach"></a><span data-ttu-id="332fd-106">免提做法</span><span class="sxs-lookup"><span data-stu-id="332fd-106">Hands-off approach</span></span> 
- <span data-ttu-id="332fd-107">更新可以直接从 Windows 更新下载并在下班期间安装。</span><span class="sxs-lookup"><span data-stu-id="332fd-107">Updates can be downloaded directly from Windows Updates automatically and installed during off-hours.</span></span> <span data-ttu-id="332fd-108">如果未对配置进行任何更改, 则这是默认状态。</span><span class="sxs-lookup"><span data-stu-id="332fd-108">If no change is made to configuration this is the default state.</span></span>
- <span data-ttu-id="332fd-109">不可推迟的更新将会自动安装1天内的版本。</span><span class="sxs-lookup"><span data-stu-id="332fd-109">Non-deferrable Updates will install day-one of release automatically.</span></span> 
- <span data-ttu-id="332fd-110">质量更新和驱动程序将自动下载并安装第一天。</span><span class="sxs-lookup"><span data-stu-id="332fd-110">Quality Updates and drivers will download and install day-one automatically.</span></span> 
- <span data-ttu-id="332fd-111">功能更新。</span><span class="sxs-lookup"><span data-stu-id="332fd-111">Feature Updates.</span></span> <span data-ttu-id="332fd-112">请参阅下面的其他说明。</span><span class="sxs-lookup"><span data-stu-id="332fd-112">See additional notes below.</span></span> 

## <a name="windows-updates-for-businesshttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-wufb-gpo-or-intune"></a><span data-ttu-id="332fd-113">[适用于企业的 Windows 更新](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)(GPO 或 Intune)</span><span class="sxs-lookup"><span data-stu-id="332fd-113">[Windows Updates for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) (GPO or Intune)</span></span>   
- <span data-ttu-id="332fd-114">从 WU 或你的 WSUS 下载更新, 但已配置的延迟超过 KB 的原始发布日期。</span><span class="sxs-lookup"><span data-stu-id="332fd-114">Updates are downloaded from WU or your WSUS but with configured delays past the KB’s original release date.</span></span> 
- <span data-ttu-id="332fd-115">与多个 OU 或筛选的策略相结合, 这允许创建部署 "震铃", 管理员可在其中指定首先安装质量更新的设备, 以及哪些设备将在以后安装。</span><span class="sxs-lookup"><span data-stu-id="332fd-115">Combined with multiple OU’s or filtered policies, this allows for the creation of deployment “rings”, where administrators can specify which devices install Quality Updates first and which ones will install later.</span></span> <span data-ttu-id="332fd-116">这样, 在通过整个部署 (例如在 SCCM 中管理 Windows 更新的开销) 在整个部署中滚动更新之前, 可以对系统的子集进行可靠性和性能测试。</span><span class="sxs-lookup"><span data-stu-id="332fd-116">This allows for reliability and performance testing on a subset of systems before rolling out updates across the entire deployment without the overhead of managing Windows Updates in SCCM for example.</span></span>
- <span data-ttu-id="332fd-117">如果你希望带宽管理和适用于企业的 Windows 更新的控件提供, 则可以[同时配置](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb)WSUS 和 windows 更新 for business。</span><span class="sxs-lookup"><span data-stu-id="332fd-117">WSUS and Windows Updates for Business can be [configured at the same time](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) if you desire both bandwidth management and the control Windows Updates for Business provides.</span></span>
- <span data-ttu-id="332fd-118">功能更新。</span><span class="sxs-lookup"><span data-stu-id="332fd-118">Feature updates.</span></span> <span data-ttu-id="332fd-119">请参阅下面的其他说明。</span><span class="sxs-lookup"><span data-stu-id="332fd-119">See additional notes below.</span></span>

## <a name="wsussccmhttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-configuration-manager"></a>[<span data-ttu-id="332fd-120">WSUS/SCCM</span><span class="sxs-lookup"><span data-stu-id="332fd-120">WSUS/SCCM</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- <span data-ttu-id="332fd-121">与面向企业的 Windows 更新非常相似, 但具有针对每个 "铃声" 或整个部署中特定的 KB 的附加选项。</span><span class="sxs-lookup"><span data-stu-id="332fd-121">Much like Windows Update for Business, but with the additional option of targeting specific KB's within each "ring" or the entire deployment.</span></span> <span data-ttu-id="332fd-122">每个更新都可以单独部署和测试, 而不只是依赖于延迟。</span><span class="sxs-lookup"><span data-stu-id="332fd-122">Each Update can be individually deployed and tested at will, rather than relying on only a delay.</span></span> 
- <span data-ttu-id="332fd-123">功能更新。</span><span class="sxs-lookup"><span data-stu-id="332fd-123">Feature updates.</span></span> <span data-ttu-id="332fd-124">请参阅下面的其他说明。</span><span class="sxs-lookup"><span data-stu-id="332fd-124">See additional notes below.</span></span>


### <a name="feature-updates"></a><span data-ttu-id="332fd-125">功能更新</span><span class="sxs-lookup"><span data-stu-id="332fd-125">Feature updates</span></span>

<span data-ttu-id="332fd-126">与 Quality 和非 Deferable 更新不同, Windows 10 "功能更新" (主要 OS 版本) 将仅在 Microsoft 团队聊天室测试和验证给定更新功能之后安装。</span><span class="sxs-lookup"><span data-stu-id="332fd-126">Unlike Quality and Non-Deferable updates, Windows 10 "Feature Updates" (major OS releases) will only be installed after Microsoft tests and validates a given updates functionality with Microsoft Teams Rooms.</span></span> <span data-ttu-id="332fd-127">即使已将其发布到半年频道 (或目标系统将系统设置为用于测试的系统), 或者甚至手动按您自己的尝试或配置手动推送, 它也不会允许安装, 直到删除端点上的块。</span><span class="sxs-lookup"><span data-stu-id="332fd-127">Even if it is released to the Semi-Annual Channel (or Targeted if you have systems set to that channel for testing) or even manually pushed by your own attempts or configurations, it will not allow the installation until the block on our end is removed.</span></span>

<span data-ttu-id="332fd-128">Microsoft 团队聊天室 "开箱", 使用 "退出" 方法, 将不会因 Windows 更新而自动安装 Windows 更新或重启设备。</span><span class="sxs-lookup"><span data-stu-id="332fd-128">Microsoft Teams Room "out-of-box", using the hands off approach, will not install a Windows Update or reboot a device automatically because of a Windows Update.</span></span> <span data-ttu-id="332fd-129">但是, 系统可能会下载更新并等待下一次重新启动进行安装。</span><span class="sxs-lookup"><span data-stu-id="332fd-129">Systems may, however, download an update and wait for the next reboot to install it.</span></span> <span data-ttu-id="332fd-130">除非有人手动重新启动, 否则在每次自动重新启动时, 安装应会发生。</span><span class="sxs-lookup"><span data-stu-id="332fd-130">Unless someone reboots it manually, installation should happen at the automatic nightly reboot.</span></span> <span data-ttu-id="332fd-131">在聊天室中, windows 更新应该是透明的, UI 永远不会被 Windows 更新中断。</span><span class="sxs-lookup"><span data-stu-id="332fd-131">Windows Updates should be transparent in the room, the UI should never be interrupted by Windows Updates.</span></span>

<span data-ttu-id="332fd-132">如果你选择加入域, 请使用 SCCM 或 WSUS, 并特别注意可能会导致设备安装更新或在工作时间强制重启的策略或操作。</span><span class="sxs-lookup"><span data-stu-id="332fd-132">If you choose to domain join, use SCCM or WSUS, and please pay special attention to policies or actions that may result in the device installing an update or forcing a reboot during business hours.</span></span> <span data-ttu-id="332fd-133">如果你的部署在使用期间重启系统或通过 UI 发出有关 Windows 更新的警报, 你将希望查看你的配置。</span><span class="sxs-lookup"><span data-stu-id="332fd-133">If you have systems in your deployment rebooting during use or alerting about Windows Updates over the UI, you will want to look into your configuration.</span></span>