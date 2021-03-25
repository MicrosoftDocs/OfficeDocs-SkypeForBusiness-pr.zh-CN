---
title: 管理 Microsoft Teams 会议室的 Windows 更新
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
description: 管理员可以了解如何管理 Microsoft Teams 会议室的 Windows 更新和 Windows 功能更新。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7bb233ceedadeaf9c7f14ddf831bd9d324d9211
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117360"
---
# <a name="manage-windows-updates"></a><span data-ttu-id="86009-103">管理 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="86009-103">Manage Windows Updates</span></span>

<span data-ttu-id="86009-104">Microsoft Teams 会议室在 Windows 10 企业版 IoT 或 Windows 10 企业版 (VL) 上运行，接收与标准台式计算机相同的 Windows 更新和 OS 版本。</span><span class="sxs-lookup"><span data-stu-id="86009-104">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop computer.</span></span>

<span data-ttu-id="86009-105">可以按照以下部分所述管理 Windows 更新：</span><span class="sxs-lookup"><span data-stu-id="86009-105">Windows Updates can be managed as discussed in the following sections:</span></span>

## <a name="hands-off-approach"></a><span data-ttu-id="86009-106">动手方法</span><span class="sxs-lookup"><span data-stu-id="86009-106">Hands-off approach</span></span> 

- <span data-ttu-id="86009-107">默认情况下，更新直接从 Windows 更新下载，在非工作时间安装。</span><span class="sxs-lookup"><span data-stu-id="86009-107">By default, updates are downloaded directly from Windows Updates automatically and installed during off-hours.</span></span>
- <span data-ttu-id="86009-108">不可延迟的更新在发布的第一天自动安装。</span><span class="sxs-lookup"><span data-stu-id="86009-108">Non-deferrable Updates install day-one of release automatically.</span></span>
- <span data-ttu-id="86009-109">质量更新和驱动程序会自动下载并安装第一天。</span><span class="sxs-lookup"><span data-stu-id="86009-109">Quality Updates and drivers download and install day-one automatically.</span></span>
- <span data-ttu-id="86009-110">功能更新。</span><span class="sxs-lookup"><span data-stu-id="86009-110">Feature Updates.</span></span> <span data-ttu-id="86009-111">请参阅以下备注。</span><span class="sxs-lookup"><span data-stu-id="86009-111">See the notes that follow.</span></span>

## <a name="windows-updates-for-business-gpo-or-intune"></a><span data-ttu-id="86009-112">适用于 Business 的 Windows (GPO 或 Intune) </span><span class="sxs-lookup"><span data-stu-id="86009-112">Windows Updates for Business (GPO or Intune)</span></span>  

- <span data-ttu-id="86009-113">[适用于 Business 的 Windows 更新](/windows/deployment/update/waas-manage-updates-wufb) 下载</span><span class="sxs-lookup"><span data-stu-id="86009-113">[Windows Updates for Business](/windows/deployment/update/waas-manage-updates-wufb) download</span></span>
- <span data-ttu-id="86009-114">更新从 Windows 更新或 WSUS 下载，但配置的延迟会过原始发布日期。</span><span class="sxs-lookup"><span data-stu-id="86009-114">Updates are downloaded from Windows Update or your WSUS but with configured delays past the original release date.</span></span>
- <span data-ttu-id="86009-115">可以使用多个 US 或筛选的策略创建部署"环"，管理员可以在部署"环"中指定哪些设备先安装质量更新，哪些设备稍后安装。</span><span class="sxs-lookup"><span data-stu-id="86009-115">You can use multiple OUs or filtered policies to create deployment "rings" where administrators can specify which devices install Quality Updates first and which ones install later.</span></span> <span data-ttu-id="86009-116">在整个部署中推出更新之前，可以在一部分系统上测试可靠性和性能，而无需在配置管理器中管理 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="86009-116">Reliability and performance can be tested on a subset of systems before rolling out updates across the entire deployment without the overhead of managing Windows Updates in Configuration Manager.</span></span>
- <span data-ttu-id="86009-117">如果你同时需要带宽管理和 Windows 商业更新[](/windows/deployment/update/waas-integrate-wufb)提供的控件，可以同时配置 WSUS 和 Windows 更新 for Business。</span><span class="sxs-lookup"><span data-stu-id="86009-117">WSUS and Windows Updates for Business can be [configured at the same time](/windows/deployment/update/waas-integrate-wufb) if you desire both the bandwidth management and the control Windows Updates for Business provides.</span></span>
- <span data-ttu-id="86009-118">功能更新。</span><span class="sxs-lookup"><span data-stu-id="86009-118">Feature updates.</span></span> <span data-ttu-id="86009-119">请参阅以下备注。</span><span class="sxs-lookup"><span data-stu-id="86009-119">See the notes that follow.</span></span>

## <a name="wsusconfiguration-manager"></a><span data-ttu-id="86009-120">WSUS/Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="86009-120">WSUS/Configuration Manager</span></span>

- <span data-ttu-id="86009-121">[WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager) 下载</span><span class="sxs-lookup"><span data-stu-id="86009-121">[WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager) download</span></span>
- <span data-ttu-id="86009-122">与 Windows Update for Business 非常类似，但具有在每个"环"或整个部署中以特定 KB 为目标的额外选项。</span><span class="sxs-lookup"><span data-stu-id="86009-122">Much like Windows Update for Business, but with the additional option of targeting specific KB's within each "ring" or the entire deployment.</span></span> <span data-ttu-id="86009-123">可以单独部署并测试每个更新，而不是仅依赖于延迟。</span><span class="sxs-lookup"><span data-stu-id="86009-123">Each Update can be individually deployed and tested at will, rather than relying on only a delay.</span></span>
- <span data-ttu-id="86009-124">功能更新。</span><span class="sxs-lookup"><span data-stu-id="86009-124">Feature updates.</span></span> <span data-ttu-id="86009-125">请参阅以下备注。</span><span class="sxs-lookup"><span data-stu-id="86009-125">See the notes that follow.</span></span>

### <a name="feature-updates"></a><span data-ttu-id="86009-126">功能更新</span><span class="sxs-lookup"><span data-stu-id="86009-126">Feature updates</span></span>

<span data-ttu-id="86009-127">与质量和不可延迟更新不同，Windows 10"功能更新" (主要操作系统版本) 仅在 Microsoft 通过 Microsoft Teams 会议室测试和验证给定更新功能后安装。</span><span class="sxs-lookup"><span data-stu-id="86009-127">Unlike Quality and Non-Deferrable updates, Windows 10 "Feature Updates" (major OS releases) will only be installed after Microsoft tests and validates a given updates functionality with Microsoft Teams Rooms.</span></span> <span data-ttu-id="86009-128">即使更新已发布到 Semi-Annual Channel (或 Targeted（如果系统已设置为用于测试) 或手动推送的通道，Microsoft Room Systems 设备也不允许安装未经测试的更新。</span><span class="sxs-lookup"><span data-stu-id="86009-128">Even if the update is released to the Semi-Annual Channel (or Targeted if you have systems set to that channel for testing) or manually pushed, a Microsoft Room Systems device won't allow the untested update to install.</span></span>

<span data-ttu-id="86009-129">Microsoft Teams 会议室功能"开箱即用"，不会为 Windows 更新自动安装 Windows 更新或重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="86009-129">Microsoft Teams Rooms functions "out-of-box" with a hands-off approach, and will not install a Windows Update or reboot a device automatically for a Windows Update.</span></span> <span data-ttu-id="86009-130">系统下载更新并等待下次重新启动以安装它。</span><span class="sxs-lookup"><span data-stu-id="86009-130">Systems download an update and wait for the next reboot to install it.</span></span> <span data-ttu-id="86009-131">除非有人手动重新启动它，否则安装仅在夜间自动重新启动时进行。</span><span class="sxs-lookup"><span data-stu-id="86009-131">Unless someone reboots it manually, installation only happens at the automatic nightly reboot.</span></span> <span data-ttu-id="86009-132">Windows 更新在聊天室中应该是透明的，正常操作不应被 Windows 更新中断。</span><span class="sxs-lookup"><span data-stu-id="86009-132">Windows Updates should be transparent in the room, and normal operation should never be interrupted by Windows Updates.</span></span>

<span data-ttu-id="86009-133">如果选择将设备加入域，请使用 Microsoft 终结点配置管理器或 WSUS。</span><span class="sxs-lookup"><span data-stu-id="86009-133">If you choose to domain join devices, use Microsoft Endpoint Configuration Manager or WSUS.</span></span> <span data-ttu-id="86009-134">请特别注意在营业时间导致设备更新或强制重新启动的策略或操作。</span><span class="sxs-lookup"><span data-stu-id="86009-134">Pay special attention to policies or actions that result in a device update or forced reboot during business hours.</span></span> <span data-ttu-id="86009-135">部署中的系统不应在使用期间重新启动，也不应在使用时间通过 UI 提醒 Windows 更新，如果发生此行为，请查看配置。</span><span class="sxs-lookup"><span data-stu-id="86009-135">Systems in your deployment should not reboot during use or alert about Windows Updates over the UI during usage hours, review your configuration if that behavior happens.</span></span>