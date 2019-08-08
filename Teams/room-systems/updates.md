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
ms.openlocfilehash: 434e6d28796662c1cc8904b7ad94f059d7d447b0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243274"
---
# <a name="manage-windows-updates"></a><span data-ttu-id="a796e-103">管理 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="a796e-103">Manage Windows Updates</span></span>

<span data-ttu-id="a796e-104">Microsoft 团队聊天室在 Windows 10 企业版 IoT 或 Windows 10 企业版 (VL) 上运行, 并作为标准桌面接收相同的 Windows 更新和 OS 版本。</span><span class="sxs-lookup"><span data-stu-id="a796e-104">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span>

<span data-ttu-id="a796e-105">可通过几种不同的方式管理 Windows 更新:</span><span class="sxs-lookup"><span data-stu-id="a796e-105">Windows Updates can be managed in a few different ways:</span></span>

## <a name="hands-off-approach"></a><span data-ttu-id="a796e-106">免提做法</span><span class="sxs-lookup"><span data-stu-id="a796e-106">Hands-off approach</span></span> 

- <span data-ttu-id="a796e-107">更新可以直接从 Windows 更新下载并在下班期间安装。</span><span class="sxs-lookup"><span data-stu-id="a796e-107">Updates can be downloaded directly from Windows Updates automatically and installed during off-hours.</span></span> <span data-ttu-id="a796e-108">这是默认配置。</span><span class="sxs-lookup"><span data-stu-id="a796e-108">This is the default configuration.</span></span>
- <span data-ttu-id="a796e-109">非延迟更新安装第1天-自动发布其中一个版本。</span><span class="sxs-lookup"><span data-stu-id="a796e-109">Non-deferrable Updates install day-one of release automatically.</span></span>
- <span data-ttu-id="a796e-110">质量更新和驱动程序自动下载和安装第一天。</span><span class="sxs-lookup"><span data-stu-id="a796e-110">Quality Updates and drivers download and install day-one automatically.</span></span>
- <span data-ttu-id="a796e-111">功能更新。</span><span class="sxs-lookup"><span data-stu-id="a796e-111">Feature Updates.</span></span> <span data-ttu-id="a796e-112">请参阅下面的备注。</span><span class="sxs-lookup"><span data-stu-id="a796e-112">See the notes that follow.</span></span>

## <a name="windows-updates-for-business-gpo-or-intune"></a><span data-ttu-id="a796e-113">适用于企业的 Windows 更新 (GPO 或 Intune)</span><span class="sxs-lookup"><span data-stu-id="a796e-113">Windows Updates for Business (GPO or Intune)</span></span>  

- <span data-ttu-id="a796e-114">[Windows 更新企业](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)版下载</span><span class="sxs-lookup"><span data-stu-id="a796e-114">[Windows Updates for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) download</span></span>
- <span data-ttu-id="a796e-115">从 WU 或你的 WSUS 下载更新, 但已配置的延迟超过 KB 的原始发布日期。</span><span class="sxs-lookup"><span data-stu-id="a796e-115">Updates are downloaded from WU or your WSUS but with configured delays past the KB’s original release date.</span></span>
- <span data-ttu-id="a796e-116">与多个 OU 或筛选的策略一起使用, 您可以创建部署 "震铃", 管理员可在其中指定首先安装质量更新的设备, 以及哪些设备将在以后安装。</span><span class="sxs-lookup"><span data-stu-id="a796e-116">Used with multiple OU’s or filtered policies, you can create deployment “rings” where administrators can specify which devices install Quality Updates first and which ones install later.</span></span> <span data-ttu-id="a796e-117">这样, 在通过整个部署 (例如在 SCCM 中管理 Windows 更新的开销) 在整个部署中滚动更新之前, 可以对系统的子集进行可靠性和性能测试。</span><span class="sxs-lookup"><span data-stu-id="a796e-117">This allows for reliability and performance testing on a subset of systems before rolling out updates across the entire deployment without the overhead of managing Windows Updates in SCCM for example.</span></span>
- <span data-ttu-id="a796e-118">如果你希望带宽管理和适用于企业的 Windows 更新的控件提供, 则可以[同时配置](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb)WSUS 和 Windows 更新 for business。</span><span class="sxs-lookup"><span data-stu-id="a796e-118">WSUS and Windows Updates for Business can be [configured at the same time](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) if you desire both the bandwidth management and the control Windows Updates for Business provides.</span></span>
- <span data-ttu-id="a796e-119">功能更新。</span><span class="sxs-lookup"><span data-stu-id="a796e-119">Feature updates.</span></span> <span data-ttu-id="a796e-120">请参阅下面的备注。</span><span class="sxs-lookup"><span data-stu-id="a796e-120">See the notes that follow.</span></span>

## <a name="wsussccm"></a><span data-ttu-id="a796e-121">WSUS/SCCM</span><span class="sxs-lookup"><span data-stu-id="a796e-121">WSUS/SCCM</span></span>

- <span data-ttu-id="a796e-122">[WSUS/SCCM](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)下载</span><span class="sxs-lookup"><span data-stu-id="a796e-122">[WSUS/SCCM](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager) download</span></span>
- <span data-ttu-id="a796e-123">与面向企业的 Windows 更新非常相似, 但具有针对每个 "铃声" 或整个部署中特定的 KB 的附加选项。</span><span class="sxs-lookup"><span data-stu-id="a796e-123">Much like Windows Update for Business, but with the additional option of targeting specific KB's within each "ring" or the entire deployment.</span></span> <span data-ttu-id="a796e-124">每个更新都可以单独部署和测试, 而不只是依赖于延迟。</span><span class="sxs-lookup"><span data-stu-id="a796e-124">Each Update can be individually deployed and tested at will, rather than relying on only a delay.</span></span>
- <span data-ttu-id="a796e-125">功能更新。</span><span class="sxs-lookup"><span data-stu-id="a796e-125">Feature updates.</span></span> <span data-ttu-id="a796e-126">请参阅下面的备注。</span><span class="sxs-lookup"><span data-stu-id="a796e-126">See the notes that follow.</span></span>

### <a name="feature-updates"></a><span data-ttu-id="a796e-127">功能更新</span><span class="sxs-lookup"><span data-stu-id="a796e-127">Feature updates</span></span>

<span data-ttu-id="a796e-128">与质量和非可推迟更新不同, Windows 10 "功能更新" (主要操作系统版本) 将仅在 Microsoft 团队聊天室测试和验证给定更新功能之后安装。</span><span class="sxs-lookup"><span data-stu-id="a796e-128">Unlike Quality and Non-Deferrable updates, Windows 10 "Feature Updates" (major OS releases) will only be installed after Microsoft tests and validates a given updates functionality with Microsoft Teams Rooms.</span></span> <span data-ttu-id="a796e-129">即使将更新发布到半年频道 (或者如果系统设置为用于测试的系统) 或手动推送的更新, Microsoft 会议室系统设备也不允许安装未经测试的更新。</span><span class="sxs-lookup"><span data-stu-id="a796e-129">Even if the update is released to the Semi-Annual Channel (or Targeted if you have systems set to that channel for testing) or manually pushed, a Microsoft Room Systems device won't allow the untested update to install.</span></span>

<span data-ttu-id="a796e-130">Microsoft 团队会议室 "开箱", 使用 "退出" 方法, 不会为 Windows 更新自动安装 Windows 更新或重启设备。</span><span class="sxs-lookup"><span data-stu-id="a796e-130">Microsoft Teams Rooms "out-of-box", using the hands off approach, will not install a Windows Update or reboot a device automatically for a Windows Update.</span></span> <span data-ttu-id="a796e-131">系统可能会下载更新并等待下一次重新启动进行安装。</span><span class="sxs-lookup"><span data-stu-id="a796e-131">Systems may download an update and wait for the next reboot to install it.</span></span> <span data-ttu-id="a796e-132">除非有人手动重新启动, 否则在每次自动重新启动时, 安装应会发生。</span><span class="sxs-lookup"><span data-stu-id="a796e-132">Unless someone reboots it manually, installation should happen at the automatic nightly reboot.</span></span> <span data-ttu-id="a796e-133">在聊天室中, windows 更新应该是透明的, UI 永远不会被 Windows 更新中断。</span><span class="sxs-lookup"><span data-stu-id="a796e-133">Windows Updates should be transparent in the room, the UI should never be interrupted by Windows Updates.</span></span>

<span data-ttu-id="a796e-134">如果你选择加入域的设备, 请使用 SCCM 或 WSUS。</span><span class="sxs-lookup"><span data-stu-id="a796e-134">If you choose to domain joined devices, use SCCM or WSUS.</span></span> <span data-ttu-id="a796e-135">特别注意可能会导致设备在工作时间安装更新或强制重启的策略或操作。</span><span class="sxs-lookup"><span data-stu-id="a796e-135">Pay special attention to policies or actions that may result in the device installing an update or forcing a reboot during business hours.</span></span> <span data-ttu-id="a796e-136">在使用期间, 你的部署中的系统不应重启或在使用期间发出有关 Windows 更新的警报。如果发生此行为, 请查看你的配置。</span><span class="sxs-lookup"><span data-stu-id="a796e-136">Systems in your deployment should not reboot during use or alert about Windows Updates over the UI during usage hours, review your configuration if that behavior happens.</span></span>