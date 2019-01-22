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
ms.openlocfilehash: 22693913c613f87c3f11ad5b421d771b661d9b91
ms.sourcegitcommit: 502f85e7920b1a9a14f879d6211e10ad8daba69f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2019
ms.locfileid: "29382469"
---
# <a name="migrate-lync-room-system-lrs-devices-to-skype-room-system-v2"></a><span data-ttu-id="1c968-103">将 Lync 会议室系统 (LRS) 设备迁移到 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="1c968-103">Migrate Lync Room System (LRS) devices to Skype Room System v2</span></span>

<span data-ttu-id="1c968-104">Skype 会议室系统版本 1 (SR v1) 软件 Lync 会议室系统 (LRS) 设备已达到[2018 年 10 月 9，支持的结束](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018)。</span><span class="sxs-lookup"><span data-stu-id="1c968-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software has reached [end of support on October 9, 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018).</span></span> <span data-ttu-id="1c968-105">这意味着 Skype 会议室系统 v1 软件将不再能够获取所有产品更新或修补程序不再。</span><span class="sxs-lookup"><span data-stu-id="1c968-105">This means Skype Room Systems v1 software will no longer get any product updates or fixes anymore.</span></span> <span data-ttu-id="1c968-106">建议使用 Skype 会议室系统 v1 软件的 Lync 会议室系统设备的客户升级其设备到 Skype 会议室系统版本 2 (SR v2)。</span><span class="sxs-lookup"><span data-stu-id="1c968-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Skype Room System version 2 (SRS v2).</span></span>

<span data-ttu-id="1c968-107">Skype 会议室系统版本 2 (SR v2) 软件与除了 Skype 的 Microsoft 团队适用于会议和呼叫所有 SR v2 支持设备上的业务服务器和联机服务。</span><span class="sxs-lookup"><span data-stu-id="1c968-107">Skype Room System Version 2 (SRS v2) software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all SRS v2 supported devices.</span></span>

<span data-ttu-id="1c968-108">您现有设备**可能会**继续工作后的末尾 Skype 会议室系统 v1 软件支持。</span><span class="sxs-lookup"><span data-stu-id="1c968-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software support.</span></span> <span data-ttu-id="1c968-109">但是，如果此软件命中需要释放修复的 Microsoft 软件 bug，它将不支持。</span><span class="sxs-lookup"><span data-stu-id="1c968-109">However, if this software hits a software bug that needs Microsoft to release a fix, it will not be supported.</span></span> <span data-ttu-id="1c968-110">SR v1 使用 TLS 1.0 / 1.1 其 Microsoft 将来将弃用。</span><span class="sxs-lookup"><span data-stu-id="1c968-110">SRS v1 uses TLS 1.0/ 1.1 which will be deprecated by Microsoft in the future.</span></span> <span data-ttu-id="1c968-111">您可以了解有关[TLS 1.0/1.1 否决准备](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1c968-111">You can learn more about [Preparing for TLS 1.0/1.1 Deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span> <span data-ttu-id="1c968-112">Skype 会议室系统 V2 正在添加支持 TLS 1.2 和将继续过 2018 年 10 月 31，工作。</span><span class="sxs-lookup"><span data-stu-id="1c968-112">Skype Room System V2 is adding support for TLS 1.2 and will continue to work past October 31, 2018.</span></span> <span data-ttu-id="1c968-113">Skype for Business 的本地客户不应禁用 TLS 1.0/1.1，直到 Skype 会议室系统 V2 宣布支持 TLS 1.2 无论 TLS 1.0/1.1 否决的一般准则。</span><span class="sxs-lookup"><span data-stu-id="1c968-113">Skype for Business on-premises customers should not disable TLS 1.0/1.1 until Skype Room System V2 announces support for TLS 1.2 regardless of general guidelines on TLS 1.0/1.1 deprecation.</span></span>

## <a name="which-devices-are-affected"></a><span data-ttu-id="1c968-114">哪些设备会受到影响？</span><span class="sxs-lookup"><span data-stu-id="1c968-114">Which devices are affected?</span></span>

<span data-ttu-id="1c968-115">下面是此更改影响的设备的列表：</span><span class="sxs-lookup"><span data-stu-id="1c968-115">Here is the list of the devices that are affected by this change:</span></span>

- <span data-ttu-id="1c968-116">Crestron RL</span><span class="sxs-lookup"><span data-stu-id="1c968-116">Crestron RL</span></span>
- [<span data-ttu-id="1c968-117">Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="1c968-117">Crestron RL2</span></span>](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="1c968-118">智能会议室系统</span><span class="sxs-lookup"><span data-stu-id="1c968-118">SMART Room systems</span></span>](https://support.smarttech.com/en/hardware/room-systems-skype)
- [<span data-ttu-id="1c968-119">Polycom CX8000</span><span class="sxs-lookup"><span data-stu-id="1c968-119">Polycom CX8000</span></span>](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)


## <a name="upgrade-options"></a><span data-ttu-id="1c968-120">升级选项</span><span class="sxs-lookup"><span data-stu-id="1c968-120">Upgrade options</span></span>

<span data-ttu-id="1c968-121">有多个选项下一代 Skype 会议室系统 (SR v2) 的升级 Lync 会议室系统。</span><span class="sxs-lookup"><span data-stu-id="1c968-121">There are multiple options for upgrading Lync Room Systems to the next generation of Skype Room Systems (SRS v2).</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="1c968-122">Crestron 硬件折旧计划</span><span class="sxs-lookup"><span data-stu-id="1c968-122">Crestron hardware Trade-in program</span></span>

<span data-ttu-id="1c968-123">Crestron 将为所有非 Crestron Lync 会议室系统客户[Crestron SR 系统](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr)或等效提供升级。</span><span class="sxs-lookup"><span data-stu-id="1c968-123">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers.</span></span> <span data-ttu-id="1c968-124">此程序的详细信息，请参阅[此处](https://support.crestron.com/app/answers/answer_view/a_id/1000220)或<!-- For details, -->[电子邮件](mailto:lrsupgrade@crestron.com)Crestron LRS 支持。</span><span class="sxs-lookup"><span data-stu-id="1c968-124">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or <!-- For details, -->[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  

### <a name="crestron-rl2-upgrade-to-srs-v2"></a><span data-ttu-id="1c968-125">Crestron RL2 升级到 SR v2</span><span class="sxs-lookup"><span data-stu-id="1c968-125">Crestron RL2 upgrade to SRS v2</span></span>

<span data-ttu-id="1c968-126">现有 Crestron RL2 （也称为 Crestron RL200） 客户可以获取升级到 RL3 使用当前 RL2 的升级工具包的每个设备的最小成本。</span><span class="sxs-lookup"><span data-stu-id="1c968-126">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade kit to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="1c968-127">此程序的详细信息，请参阅[此处](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)。</span><span class="sxs-lookup"><span data-stu-id="1c968-127">See details of this program [here](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).</span></span>

### <a name="smart-room-systems-upgrade"></a><span data-ttu-id="1c968-128">智能会议室系统升级</span><span class="sxs-lookup"><span data-stu-id="1c968-128">SMART Room Systems upgrade</span></span>

<span data-ttu-id="1c968-129">对于智能 LRS 客户，除了 Crestron 硬件折旧计划，Microsoft 和智能还提供解决方案升级到 Skype 会议室系统 v2 工作。</span><span class="sxs-lookup"><span data-stu-id="1c968-129">For SMART LRS customers, apart from Crestron hardware trade-in program, Microsoft and SMART are also working on providing a solution to upgrade to Skype Room System v2.</span></span> <span data-ttu-id="1c968-130">将通过智能技术 Inc.提供此升级请参阅有关此[此处](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1c968-130">This upgrade will be provided by SMART Technologies Inc. Please see more about this [here](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).</span></span>

<span data-ttu-id="1c968-131">若要使用此选项，客户必须此外购买[Logitech 屏幕共享](https://www.logitech.com/en-us/product/screen-share)适配器。</span><span class="sxs-lookup"><span data-stu-id="1c968-131">To use this option, customers must additionally buy a [Logitech Screen Share](https://www.logitech.com/en-us/product/screen-share) adapter.</span></span> <span data-ttu-id="1c968-132">Microsoft 将提供有关如何与 Skype 会议室系统 v2 软件一起使用此适配器的说明。</span><span class="sxs-lookup"><span data-stu-id="1c968-132">Microsoft will provide instructions on how to use this adapter with Skype Room System v2 software.</span></span>

<span data-ttu-id="1c968-133">查找有关此页上的升级说明回来。</span><span class="sxs-lookup"><span data-stu-id="1c968-133">Look for upgrade instructions on this page shortly.</span></span>
  
<!-- 
### Summary of upgrade options

This table lists summary of all available options for existing LRS devices:
-->

## <a name="what-should-you-do"></a><span data-ttu-id="1c968-134">怎么办？</span><span class="sxs-lookup"><span data-stu-id="1c968-134">What should you do?</span></span>

<span data-ttu-id="1c968-135">我们建议您打算到之前使用上面提到的升级选项的 TLS 1.0/1.1 否决的 Skype 会议室系统 v2 更新 Lync 会议室系统的设备。</span><span class="sxs-lookup"><span data-stu-id="1c968-135">We recommend you plan to update Lync Room System devices to Skype Room Systems v2 before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="1c968-136">此外，也可以考虑将新设备认证 SR v2 替换为现有的设备。</span><span class="sxs-lookup"><span data-stu-id="1c968-136">Additionally, you may also consider replacing existing devices with new devices certified for SRS v2.</span></span> <span data-ttu-id="1c968-137">有关详细信息，请参阅[聊天室设备](https://aka.ms/roomdevices)和也看看[Skype 会议室系统 v2 要求](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)。</span><span class="sxs-lookup"><span data-stu-id="1c968-137">See [Room devices](https://aka.ms/roomdevices) for details and also take a look at [Skype Room Systems v2 requirements](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  

> [!NOTE]
> <span data-ttu-id="1c968-138">Skype 会议室系统 v2 中尚不支持触摸和白板功能。</span><span class="sxs-lookup"><span data-stu-id="1c968-138">Touch and whiteboard functionality is not yet supported in Skype Room System v2.</span></span> <span data-ttu-id="1c968-139">触摸和白板支持当前计划的 Skype 会议室系统 v2，并将添加到 2019年。</span><span class="sxs-lookup"><span data-stu-id="1c968-139">Touch and whiteboard support is currently planned for Skype Room System v2 and will be added in 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="1c968-140">Skype 会议室系统 V2 软件支持与应用程序版本 4.0.64.0 截止 2018 年 12 月 14，TLS 1.2 协议。</span><span class="sxs-lookup"><span data-stu-id="1c968-140">Skype Room System V2 software supports the TLS 1.2 protocol as of December 14, 2018 with app version 4.0.64.0.</span></span> <span data-ttu-id="1c968-141">对于本地客户通过 TLS 1.2 通信启用 Skype 会议室系统 V2 需要 Skype 业务 Server 2015 累积更新 9 (CU9) 或 Skype 业务 Server 2019 累积更新 1 (CU1)。</span><span class="sxs-lookup"><span data-stu-id="1c968-141">For on-premises customers, enabling communication over TLS 1.2 for Skype Room System V2 requires Skype for Business Server 2015 Cumulative Update 9 (CU9) or Skype for Business Server 2019 Cumulative Update 1 (CU1).</span></span> <span data-ttu-id="1c968-142">更改应不会影响 Skype 的业务联机客户客户端的更改一样向前和向后兼容。</span><span class="sxs-lookup"><span data-stu-id="1c968-142">The change should not affect Skype for Business Online customers as client changes are forward and backward compliant.</span></span>
