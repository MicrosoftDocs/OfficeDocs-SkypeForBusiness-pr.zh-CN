---
title: 将 Lync 会议室系统设备迁移到 Skype 会议室系统版本 2
ms.author: jambirk
author: jambirk
ms.reviewer: sohailta
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ''
description: 阅读本主题可了解如何迁移 Lync 会议室系统设备使用 Skype 会议室系统 v2 软件。
ms.openlocfilehash: 9436c5a843f21b9913c0dbcbed6e62df8ef62ce2
ms.sourcegitcommit: e53749714dcde9f7b184d5ef554bffbc77f54267
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2019
ms.locfileid: "28729405"
---
# <a name="migrate-lync-room-system-lrs-devices-to-skype-room-system-v2"></a><span data-ttu-id="3eac9-103">将 Lync 会议室系统 (LRS) 设备迁移到 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="3eac9-103">Migrate Lync Room System (LRS) devices to Skype Room System v2</span></span> 
<span data-ttu-id="3eac9-104">Skype 会议室系统版本 1 (SR v1) 软件 Lync 会议室系统 (LRS) 设备已达到[2018 年 10 月 9，支持的结束](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018)。</span><span class="sxs-lookup"><span data-stu-id="3eac9-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software has reached [end of support on October 9, 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018).</span></span> <span data-ttu-id="3eac9-105">这意味着 Skype 会议室系统 v1 软件将不再能够获取所有产品更新或修补程序不再。</span><span class="sxs-lookup"><span data-stu-id="3eac9-105">This means Skype Room Systems v1 software will no longer get any product updates or fixes anymore.</span></span> <span data-ttu-id="3eac9-106">建议使用 Skype 会议室系统 v1 软件的 Lync 会议室系统设备的客户升级其设备到 Skype 会议室系统版本 2 (SR v2)。</span><span class="sxs-lookup"><span data-stu-id="3eac9-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Skype Room System version 2 (SRS v2).</span></span>

<span data-ttu-id="3eac9-107">Skype 会议室系统版本 2 (SR v2) 软件与除了 Skype 的 Microsoft 团队适用于会议和呼叫所有 SR v2 支持设备上的业务服务器和联机服务。</span><span class="sxs-lookup"><span data-stu-id="3eac9-107">Skype Room System Version 2 (SRS v2) software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all SRS v2 supported devices.</span></span>

<span data-ttu-id="3eac9-108">您现有设备**可能会**继续工作后的末尾 Skype 会议室系统 v1 软件支持。</span><span class="sxs-lookup"><span data-stu-id="3eac9-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software support.</span></span> <span data-ttu-id="3eac9-109">但是，如果此软件命中需要释放修复的 Microsoft 软件 bug，它将不支持。</span><span class="sxs-lookup"><span data-stu-id="3eac9-109">However, if this software hits a software bug that needs Microsoft to release a fix, it will not be supported.</span></span> <span data-ttu-id="3eac9-110">SR v1 使用 TLS 1.0 / 1.1 其 Microsoft 在将来将弃用。</span><span class="sxs-lookup"><span data-stu-id="3eac9-110">SRS v1 uses TLS 1.0/ 1.1 which will be deprecated by Microsoft in future.</span></span> <span data-ttu-id="3eac9-111">您可以了解有关[TLS 1.0/1.1 否决准备](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3eac9-111">You can learn more about [Preparing for TLS 1.0/1.1 Deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span> <span data-ttu-id="3eac9-112">Skype 会议室系统 V2 正在添加支持 TLS 1.2 和将继续过 2018 年 10 月 31，工作。</span><span class="sxs-lookup"><span data-stu-id="3eac9-112">Skype Room System V2 is adding support for TLS 1.2 and will continue to work past October 31, 2018.</span></span> <span data-ttu-id="3eac9-113">在内部部署客户业务的 Skype 不应禁用 TLS 1.0/1.1 Skype 会议室系统 V2 annouces 支持 TLS 1.2 无论 TLS 1.0/1.1 否决的一般准则。</span><span class="sxs-lookup"><span data-stu-id="3eac9-113">Skype for Business on premise customers should not disable TLS 1.0/1.1 until Skype Room System V2 annouces support for TLS 1.2 regardless of general guidelines on TLS 1.0/1.1 deprecation.</span></span>

## <a name="which-devices-are-affected"></a><span data-ttu-id="3eac9-114">哪些设备会受到影响？</span><span class="sxs-lookup"><span data-stu-id="3eac9-114">Which devices are affected?</span></span>
<span data-ttu-id="3eac9-115">下面是此更改影响的设备的列表：</span><span class="sxs-lookup"><span data-stu-id="3eac9-115">Here is the list of the devices that are affected by this change:</span></span>
- [<span data-ttu-id="3eac9-116">智能会议室系统</span><span class="sxs-lookup"><span data-stu-id="3eac9-116">SMART Room systems</span></span>](https://support.smarttech.com/en/hardware/room-systems-skype)
- [<span data-ttu-id="3eac9-117">Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="3eac9-117">Crestron RL2</span></span>](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="3eac9-118">Polycom CX8000</span><span class="sxs-lookup"><span data-stu-id="3eac9-118">Polycom CX8000</span></span>](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)
- <span data-ttu-id="3eac9-119">Crestron RL</span><span class="sxs-lookup"><span data-stu-id="3eac9-119">Crestron RL</span></span>

## <a name="upgrade-options"></a><span data-ttu-id="3eac9-120">升级选项</span><span class="sxs-lookup"><span data-stu-id="3eac9-120">Upgrade options</span></span>
<span data-ttu-id="3eac9-121">有多个选项下一代 Skype 会议室系统 (SR v2) 的升级 Lync 会议室系统。</span><span class="sxs-lookup"><span data-stu-id="3eac9-121">There are multiple options for upgrading Lync Room Systems to the next generation of Skype Room Systems (SRS v2).</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="3eac9-122">Crestron 硬件折旧计划</span><span class="sxs-lookup"><span data-stu-id="3eac9-122">Crestron hardware Trade-in program</span></span>
<span data-ttu-id="3eac9-123">Crestron 将为所有非 Crestron Lync 会议室系统客户[Crestron SR 系统](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr)或等效提供升级。</span><span class="sxs-lookup"><span data-stu-id="3eac9-123">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers.</span></span> <span data-ttu-id="3eac9-124">此程序的详细信息，请参阅[此处](https://support.crestron.com/app/answers/answer_view/a_id/1000220)或<!-- For details, -->[电子邮件](mailto:lrsupgrade@crestron.com)Crestron LRS 支持。</span><span class="sxs-lookup"><span data-stu-id="3eac9-124">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or <!-- For details, -->[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  


### <a name="crestron-rl2-upgrade-to-srs-v2"></a><span data-ttu-id="3eac9-125">Crestron RL2 升级到 SR V2</span><span class="sxs-lookup"><span data-stu-id="3eac9-125">Crestron RL2 upgrade to SRS V2</span></span>
<span data-ttu-id="3eac9-126">现有 Crestron RL2 （也称为 Crestron RL200） 客户可以获取升级到 RL3 使用当前 RL2 的升级工具包的每个设备的最小成本。</span><span class="sxs-lookup"><span data-stu-id="3eac9-126">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade kit to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="3eac9-127">此程序的详细信息，请参阅[此处](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)。</span><span class="sxs-lookup"><span data-stu-id="3eac9-127">See details of this program [here](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).</span></span> 


### <a name="smart-room-systems-upgrade"></a><span data-ttu-id="3eac9-128">智能会议室系统升级</span><span class="sxs-lookup"><span data-stu-id="3eac9-128">SMART Room Systems upgrade</span></span> 
<span data-ttu-id="3eac9-129">对于智能 LRS 客户，除了 Crestron 硬件折旧计划，Microsoft 和智能还提供解决方案升级到 Skype 会议室系统 v2 工作。</span><span class="sxs-lookup"><span data-stu-id="3eac9-129">For SMART LRS customers, apart from Crestron hardware trade-in program, Microsoft and SMART are also working on providing a solution to upgrade to Skype Room System v2.</span></span> <span data-ttu-id="3eac9-130">将通过智能技术 Inc.提供此升级请参阅有关此[此处](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3eac9-130">This upgrade will be provided by SMART Technologies Inc. Please see more about this [here](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).</span></span>

  
<span data-ttu-id="3eac9-131">若要使用此选项，但是所示，客户必须另外购买[Logitech 屏幕共享](https://www.logitech.com/en-us/product/screen-share)适配器。</span><span class="sxs-lookup"><span data-stu-id="3eac9-131">To use this option however, customers must additionaly buy a [Logitech Screen Share](https://www.logitech.com/en-us/product/screen-share) adapter.</span></span> <span data-ttu-id="3eac9-132">Microsoft 将提供有关如何与 Skype 会议室系统 v2 软件一起使用此适配器的说明。</span><span class="sxs-lookup"><span data-stu-id="3eac9-132">Microsoft will provide instructions on how to use this adapter with Skype Room System v2 software.</span></span> 


<span data-ttu-id="3eac9-133">查找有关此页上的升级说明回来。</span><span class="sxs-lookup"><span data-stu-id="3eac9-133">Look for upgrade instructions on this page shortly.</span></span> 
  
### <a name="summary-of-upgrade-options"></a><span data-ttu-id="3eac9-134">升级选项摘要</span><span class="sxs-lookup"><span data-stu-id="3eac9-134">Summary of upgrade options</span></span>
<span data-ttu-id="3eac9-135">下表列出的所有可用选项的现有 LRS 设备的摘要：</span><span class="sxs-lookup"><span data-stu-id="3eac9-135">This table lists summary of all available options for existing LRS devices:</span></span>

## <a name="what-should-you-do"></a><span data-ttu-id="3eac9-136">怎么办？</span><span class="sxs-lookup"><span data-stu-id="3eac9-136">What should you do?</span></span>
<span data-ttu-id="3eac9-137">我们建议您打算到之前使用上面提到的升级选项的 TLS 1.0/1.1 否决的 Skype 会议室系统 v2 更新 Lync 会议室系统的设备。</span><span class="sxs-lookup"><span data-stu-id="3eac9-137">We recommend you plan to update Lync Room System devices to Skype Room Systems v2 before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="3eac9-138">此外，也可以考虑将新设备认证 SR v2 替换为现有的设备。</span><span class="sxs-lookup"><span data-stu-id="3eac9-138">Additionally, you may also consider replacing existing devices with new devices certified for SRS v2.</span></span> <span data-ttu-id="3eac9-139">有关详细信息，请参阅[聊天室设备](https://aka.ms/roomdevices)和也看看[Skype 会议室系统 v2 要求](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)。</span><span class="sxs-lookup"><span data-stu-id="3eac9-139">See [Room devices](https://aka.ms/roomdevices) for details and also take a look at [Skype Room Systems v2 requirements](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  

> [!NOTE]
> <span data-ttu-id="3eac9-140">Skype 会议室系统 v2 中尚不支持触摸和白板功能。</span><span class="sxs-lookup"><span data-stu-id="3eac9-140">Touch and whiteboard functionality is not yet supported in Skype Room System v2.</span></span> <span data-ttu-id="3eac9-141">触摸和白板支持的 Skype 会议室系统 v2 积压工作中，将被添加到 H1 CY2019。</span><span class="sxs-lookup"><span data-stu-id="3eac9-141">Touch and whiteboard support is in the backlog for Skype Room System v2 and will be added in H1 CY2019.</span></span>

> [!NOTE]
> <span data-ttu-id="3eac9-142">Skype 会议室系统 V2 软件应用程序版本 4.0.64.0 以来 2018 年 12 月 14，支持 TLS 1.2 协议。</span><span class="sxs-lookup"><span data-stu-id="3eac9-142">Skype Room System V2 software supports TLS 1.2 protocol since December 14, 2018 with app version 4.0.64.0.</span></span> <span data-ttu-id="3eac9-143">对于在内部部署客户通讯 over TLS 1.2 启用 Skype 会议室系统 V2 需要 Skype 业务 2015 Cummulative 更新 9 (CU9) 或 Skype Buisness 2019 Cummulative 更新 1 (CU1)。</span><span class="sxs-lookup"><span data-stu-id="3eac9-143">For on premise customers, enabling communciation over TLS 1.2 for Skype Room System V2 requires Skype for Business Server 2015 Cummulative Update 9 (CU9) or Skype for Buisness Server 2019 Cummulative Update 1 (CU1).</span></span> <span data-ttu-id="3eac9-144">更改应不可知到 Skype 业务联机客户的客户端的更改一样向前和向后兼容。</span><span class="sxs-lookup"><span data-stu-id="3eac9-144">The change should be agnostic to Skype for Business Online customers as client changes are forward and backward compliant.</span></span> 
