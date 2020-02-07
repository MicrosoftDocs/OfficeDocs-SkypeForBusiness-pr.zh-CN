---
title: 管理 Microsoft 团队聊天室的 Windows 更新
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: 管理 Microsoft 团队聊天室的 Windows 更新
ms.openlocfilehash: 2fc96118b70ff7c15e7bde02fdcd048c07581ad3
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827910"
---
# <a name="manage-windows-updates"></a><span data-ttu-id="5af14-103">管理 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="5af14-103">Manage Windows Updates</span></span>

<span data-ttu-id="5af14-104">Microsoft 团队聊天室在 Windows 10 企业版 IoT 或 Windows 10 企业版（VL）上运行，并接收与标准桌面计算机相同的 Windows 更新和操作系统版本。</span><span class="sxs-lookup"><span data-stu-id="5af14-104">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop computer.</span></span>

<span data-ttu-id="5af14-105">可按以下部分中的讨论对 Windows 更新进行管理：</span><span class="sxs-lookup"><span data-stu-id="5af14-105">Windows Updates can be managed as discussed in the following sections:</span></span>

## <a name="hands-off-approach"></a><span data-ttu-id="5af14-106">免提做法</span><span class="sxs-lookup"><span data-stu-id="5af14-106">Hands-off approach</span></span> 

- <span data-ttu-id="5af14-107">默认情况下，自动从 Windows 更新下载并在小时内安装更新。</span><span class="sxs-lookup"><span data-stu-id="5af14-107">By default, updates are downloaded directly from Windows Updates automatically and installed during off-hours.</span></span>
- <span data-ttu-id="5af14-108">非延迟更新安装第1天-自动发布其中一个版本。</span><span class="sxs-lookup"><span data-stu-id="5af14-108">Non-deferrable Updates install day-one of release automatically.</span></span>
- <span data-ttu-id="5af14-109">质量更新和驱动程序自动下载和安装第一天。</span><span class="sxs-lookup"><span data-stu-id="5af14-109">Quality Updates and drivers download and install day-one automatically.</span></span>
- <span data-ttu-id="5af14-110">功能更新。</span><span class="sxs-lookup"><span data-stu-id="5af14-110">Feature Updates.</span></span> <span data-ttu-id="5af14-111">请参阅下面的备注。</span><span class="sxs-lookup"><span data-stu-id="5af14-111">See the notes that follow.</span></span>

## <a name="windows-updates-for-business-gpo-or-intune"></a><span data-ttu-id="5af14-112">适用于企业的 Windows 更新（GPO 或 Intune）</span><span class="sxs-lookup"><span data-stu-id="5af14-112">Windows Updates for Business (GPO or Intune)</span></span>  

- <span data-ttu-id="5af14-113">[Windows 更新企业](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)版下载</span><span class="sxs-lookup"><span data-stu-id="5af14-113">[Windows Updates for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) download</span></span>
- <span data-ttu-id="5af14-114">从 Windows 更新或 WSUS 下载更新，但已配置的延迟已超过原始发布日期。</span><span class="sxs-lookup"><span data-stu-id="5af14-114">Updates are downloaded from Windows Update or your WSUS but with configured delays past the original release date.</span></span>
- <span data-ttu-id="5af14-115">你可以使用多个 Ou 或筛选的策略创建部署 "铃声"，管理员可以在其中指定首先安装质量更新的设备，以及哪些设备将在以后安装。</span><span class="sxs-lookup"><span data-stu-id="5af14-115">You can use multiple OUs or filtered policies to create deployment “rings” where administrators can specify which devices install Quality Updates first and which ones install later.</span></span> <span data-ttu-id="5af14-116">可以在系统子集上测试可靠性和性能，而无需在配置管理器中管理 Windows 更新的开销。</span><span class="sxs-lookup"><span data-stu-id="5af14-116">Reliability and performance can be tested on a subset of systems before rolling out updates across the entire deployment without the overhead of managing Windows Updates in Configuration Manager.</span></span>
- <span data-ttu-id="5af14-117">如果你希望带宽管理和适用于企业的 Windows 更新的控件提供，则可以[同时配置](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb)WSUS 和 Windows 更新 for business。</span><span class="sxs-lookup"><span data-stu-id="5af14-117">WSUS and Windows Updates for Business can be [configured at the same time](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) if you desire both the bandwidth management and the control Windows Updates for Business provides.</span></span>
- <span data-ttu-id="5af14-118">功能更新。</span><span class="sxs-lookup"><span data-stu-id="5af14-118">Feature updates.</span></span> <span data-ttu-id="5af14-119">请参阅下面的备注。</span><span class="sxs-lookup"><span data-stu-id="5af14-119">See the notes that follow.</span></span>

## <a name="wsusconfiguration-manager"></a><span data-ttu-id="5af14-120">WSUS/配置管理器</span><span class="sxs-lookup"><span data-stu-id="5af14-120">WSUS/Configuration Manager</span></span>

- <span data-ttu-id="5af14-121">[WSUS/配置管理器](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)下载</span><span class="sxs-lookup"><span data-stu-id="5af14-121">[WSUS/Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager) download</span></span>
- <span data-ttu-id="5af14-122">与面向企业的 Windows 更新非常相似，但具有针对每个 "铃声" 或整个部署中特定的 KB 的附加选项。</span><span class="sxs-lookup"><span data-stu-id="5af14-122">Much like Windows Update for Business, but with the additional option of targeting specific KB's within each "ring" or the entire deployment.</span></span> <span data-ttu-id="5af14-123">每个更新都可以单独部署和测试，而不只是依赖于延迟。</span><span class="sxs-lookup"><span data-stu-id="5af14-123">Each Update can be individually deployed and tested at will, rather than relying on only a delay.</span></span>
- <span data-ttu-id="5af14-124">功能更新。</span><span class="sxs-lookup"><span data-stu-id="5af14-124">Feature updates.</span></span> <span data-ttu-id="5af14-125">请参阅下面的备注。</span><span class="sxs-lookup"><span data-stu-id="5af14-125">See the notes that follow.</span></span>

### <a name="feature-updates"></a><span data-ttu-id="5af14-126">功能更新</span><span class="sxs-lookup"><span data-stu-id="5af14-126">Feature updates</span></span>

<span data-ttu-id="5af14-127">与质量和非可推迟更新不同，Windows 10 "功能更新" （主要操作系统版本）将仅在 Microsoft 团队聊天室测试和验证给定更新功能之后安装。</span><span class="sxs-lookup"><span data-stu-id="5af14-127">Unlike Quality and Non-Deferrable updates, Windows 10 "Feature Updates" (major OS releases) will only be installed after Microsoft tests and validates a given updates functionality with Microsoft Teams Rooms.</span></span> <span data-ttu-id="5af14-128">即使将更新发布到半年频道（或者如果系统设置为用于测试的系统）或手动推送的更新，Microsoft 会议室系统设备也不允许安装未经测试的更新。</span><span class="sxs-lookup"><span data-stu-id="5af14-128">Even if the update is released to the Semi-Annual Channel (or Targeted if you have systems set to that channel for testing) or manually pushed, a Microsoft Room Systems device won't allow the untested update to install.</span></span>

<span data-ttu-id="5af14-129">Microsoft 团队聊天室使用有干预方法的 "开箱" 功能，不会为 Windows 更新自动安装 Windows 更新或重启设备。</span><span class="sxs-lookup"><span data-stu-id="5af14-129">Microsoft Teams Rooms functions "out-of-box" with a hands-off approach, and will not install a Windows Update or reboot a device automatically for a Windows Update.</span></span> <span data-ttu-id="5af14-130">系统下载更新，并等待下一次重新启动进行安装。</span><span class="sxs-lookup"><span data-stu-id="5af14-130">Systems download an update and wait for the next reboot to install it.</span></span> <span data-ttu-id="5af14-131">除非有人手动重启，否则，仅在夜间自动重启时才会进行安装。</span><span class="sxs-lookup"><span data-stu-id="5af14-131">Unless someone reboots it manually, installation only happens at the automatic nightly reboot.</span></span> <span data-ttu-id="5af14-132">Windows 更新在聊天室中应该是透明的，正常操作不应被 Windows 更新中断。</span><span class="sxs-lookup"><span data-stu-id="5af14-132">Windows Updates should be transparent in the room, and normal operation should never be interrupted by Windows Updates.</span></span>

<span data-ttu-id="5af14-133">如果你选择 "加入域" 设备，请使用 Microsoft 终结点配置管理器或 WSUS。</span><span class="sxs-lookup"><span data-stu-id="5af14-133">If you choose to domain join devices, use Microsoft Endpoint Configuration Manager or WSUS.</span></span> <span data-ttu-id="5af14-134">特别注意在营业时间内导致设备更新或强制重启的策略或操作。</span><span class="sxs-lookup"><span data-stu-id="5af14-134">Pay special attention to policies or actions that result in a device update or forced reboot during business hours.</span></span> <span data-ttu-id="5af14-135">在使用期间，你的部署中的系统不应重启或在使用期间发出有关 Windows 更新的警报。如果发生此行为，请查看你的配置。</span><span class="sxs-lookup"><span data-stu-id="5af14-135">Systems in your deployment should not reboot during use or alert about Windows Updates over the UI during usage hours, review your configuration if that behavior happens.</span></span>