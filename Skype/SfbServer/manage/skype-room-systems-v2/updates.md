---
title: 为 Microsoft 团队房间管理 Windows 更新
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 10/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: 为 Microsoft 团队房间管理 Windows 更新
ms.openlocfilehash: d9374fc00dcb5a19d2c15c91da18ce6c7d353033
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910303"
---
# <a name="manage-windows-updates"></a><span data-ttu-id="b6f67-103">管理 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="b6f67-103">Manage Windows Updates</span></span>

<span data-ttu-id="b6f67-104">Microsoft 团队聊天室 Windows 10 企业 IoT 或 Windows 10 企业 (VL) 上运行并接收作为标准桌面相同的 Windows 更新和操作系统版本。</span><span class="sxs-lookup"><span data-stu-id="b6f67-104">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span>

<span data-ttu-id="b6f67-105">Windows 更新可以管理几个不同的方式：</span><span class="sxs-lookup"><span data-stu-id="b6f67-105">Windows Updates can be managed in a few different ways:</span></span>

## <a name="hands-off-approach"></a><span data-ttu-id="b6f67-106">干预方法</span><span class="sxs-lookup"><span data-stu-id="b6f67-106">Hands-off approach</span></span> 
- <span data-ttu-id="b6f67-107">可以自动下载直接从 Windows 更新和非工作时间安装更新。</span><span class="sxs-lookup"><span data-stu-id="b6f67-107">Updates can be downloaded directly from Windows Updates automatically and installed during off-hours.</span></span> <span data-ttu-id="b6f67-108">如果不做任何更改到配置这是默认状态。</span><span class="sxs-lookup"><span data-stu-id="b6f67-108">If no change is made to configuration this is the default state.</span></span>
- <span data-ttu-id="b6f67-109">非可延迟更新将自动安装版本的-一天。</span><span class="sxs-lookup"><span data-stu-id="b6f67-109">Non-deferrable Updates will install day-one of release automatically.</span></span> 
- <span data-ttu-id="b6f67-110">质量更新和驱动程序将自动下载和安装第一天。</span><span class="sxs-lookup"><span data-stu-id="b6f67-110">Quality Updates and drivers will download and install day-one automatically.</span></span> 
- <span data-ttu-id="b6f67-111">功能更新。</span><span class="sxs-lookup"><span data-stu-id="b6f67-111">Feature Updates.</span></span> <span data-ttu-id="b6f67-112">请参阅以下其他注意事项。</span><span class="sxs-lookup"><span data-stu-id="b6f67-112">See additional notes below.</span></span> 

## <a name="windows-updates-for-businesshttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-wufb-gpo-or-intune"></a><span data-ttu-id="b6f67-113">[Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)（GPO 或 Intune）</span><span class="sxs-lookup"><span data-stu-id="b6f67-113">[Windows Updates for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) (GPO or Intune)</span></span>   
- <span data-ttu-id="b6f67-114">从 WU 或您 WSUS 但以前 KB 的原始发行版的日期配置延迟下载更新。</span><span class="sxs-lookup"><span data-stu-id="b6f67-114">Updates are downloaded from WU or your WSUS but with configured delays past the KB’s original release date.</span></span> 
- <span data-ttu-id="b6f67-115">结合多个 OU 或筛选策略，这将允许创建的部署"拨打"，其中管理员可以指定哪些设备先安装高质量的更新和其与将安装更高版本。</span><span class="sxs-lookup"><span data-stu-id="b6f67-115">Combined with multiple OU’s or filtered policies, this allows for the creation of deployment “rings”, where administrators can specify which devices install Quality Updates first and which ones will install later.</span></span> <span data-ttu-id="b6f67-116">这样，以实现可靠性和性能测试跨整个部署无需开销的管理 SCCM 中的 Windows 更新，例如推出更新之前系统的子集。</span><span class="sxs-lookup"><span data-stu-id="b6f67-116">This allows for reliability and performance testing on a subset of systems before rolling out updates across the entire deployment without the overhead of managing Windows Updates in SCCM for example.</span></span>
- <span data-ttu-id="b6f67-117">WSUS 和 for Business Windows 更新，可以[同时配置](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb)根据需要带宽管理和控制业务的 Windows Update 提供。</span><span class="sxs-lookup"><span data-stu-id="b6f67-117">WSUS and Windows Updates for Business can be [configured at the same time](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) if you desire both bandwidth management and the control Windows Updates for Business provides.</span></span>
- <span data-ttu-id="b6f67-118">功能更新。</span><span class="sxs-lookup"><span data-stu-id="b6f67-118">Feature updates.</span></span> <span data-ttu-id="b6f67-119">请参阅以下其他注意事项。</span><span class="sxs-lookup"><span data-stu-id="b6f67-119">See additional notes below.</span></span>

## <a name="wsussccmhttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-configuration-manager"></a>[<span data-ttu-id="b6f67-120">WSUS/SCCM</span><span class="sxs-lookup"><span data-stu-id="b6f67-120">WSUS/SCCM</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- <span data-ttu-id="b6f67-121">就像 Windows Update for Business，但是有面向特定 KB 的每个"拨打"或整个部署中的其他选项。</span><span class="sxs-lookup"><span data-stu-id="b6f67-121">Much like Windows Update for Business, but with the additional option of targeting specific KB's within each "ring" or the entire deployment.</span></span> <span data-ttu-id="b6f67-122">每个更新可以分别部署和测试在将，而不是信赖上仅延迟。</span><span class="sxs-lookup"><span data-stu-id="b6f67-122">Each Update can be individually deployed and tested at will, rather than relying on only a delay.</span></span> 
- <span data-ttu-id="b6f67-123">功能更新。</span><span class="sxs-lookup"><span data-stu-id="b6f67-123">Feature updates.</span></span> <span data-ttu-id="b6f67-124">请参阅以下其他注意事项。</span><span class="sxs-lookup"><span data-stu-id="b6f67-124">See additional notes below.</span></span>


### <a name="feature-updates"></a><span data-ttu-id="b6f67-125">功能更新</span><span class="sxs-lookup"><span data-stu-id="b6f67-125">Feature updates</span></span>

<span data-ttu-id="b6f67-126">质量和非 Deferable 与更新不同，Windows 10 Microsoft 测试并验证给定的更新功能与 Microsoft 团队聊天室后，将仅安装"功能更新"（主要操作系统版本）。</span><span class="sxs-lookup"><span data-stu-id="b6f67-126">Unlike Quality and Non-Deferable updates, Windows 10 "Feature Updates" (major OS releases) will only be installed after Microsoft tests and validates a given updates functionality with Microsoft Teams Rooms.</span></span> <span data-ttu-id="b6f67-127">即使它是释放到半年通道 （或目标如果必须设置为测试该频道的系统），或者甚至手动推送尝试或配置，它将不允许安装，直到删除的阻止，我们结束。</span><span class="sxs-lookup"><span data-stu-id="b6f67-127">Even if it is released to the Semi-Annual Channel (or Targeted if you have systems set to that channel for testing) or even manually pushed by your own attempts or configurations, it will not allow the installation until the block on our end is removed.</span></span>

<span data-ttu-id="b6f67-128">使用手中的关闭方法中，Microsoft 团队会议室"out box"不将安装 Windows Update 或由于 Windows Update 的自动重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="b6f67-128">Microsoft Teams Room "out-of-box", using the hands off approach, will not install a Windows Update or reboot a device automatically because of a Windows Update.</span></span> <span data-ttu-id="b6f67-129">但是，系统可能下载更新，等待下一步的重新启动以安装它。</span><span class="sxs-lookup"><span data-stu-id="b6f67-129">Systems may, however, download an update and wait for the next reboot to install it.</span></span> <span data-ttu-id="b6f67-130">除非某人重新启动它手动安装何时发生在夜间自动重新启动。</span><span class="sxs-lookup"><span data-stu-id="b6f67-130">Unless someone reboots it manually, installation should happen at the automatic nightly reboot.</span></span> <span data-ttu-id="b6f67-131">Windows 更新在聊天室中应为透明，UI 应永远不会在 Windows 更新被打断。</span><span class="sxs-lookup"><span data-stu-id="b6f67-131">Windows Updates should be transparent in the room, the UI should never be interrupted by Windows Updates.</span></span>

<span data-ttu-id="b6f67-132">如果您选择加入域，使用 SCCM 或 WSUS，并请特别注意策略或可能会导致设备安装更新或强制重新启动工作时间内的操作。</span><span class="sxs-lookup"><span data-stu-id="b6f67-132">If you choose to domain join, use SCCM or WSUS, and please pay special attention to policies or actions that may result in the device installing an update or forcing a reboot during business hours.</span></span> <span data-ttu-id="b6f67-133">如果您有系统使用过程中重新启动或通过 UI 警报 Windows 更新有关在部署中，要查看您的配置。</span><span class="sxs-lookup"><span data-stu-id="b6f67-133">If you have systems in your deployment rebooting during use or alerting about Windows Updates over the UI, you will want to look into your configuration.</span></span>
