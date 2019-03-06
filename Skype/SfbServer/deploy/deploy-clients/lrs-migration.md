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
ms.openlocfilehash: c01b579e73775e5f6b237f74975681fef7ea45ea
ms.sourcegitcommit: d90beb625c2d12616fb9aee39b6dd1c2d4c12947
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "30408210"
---
# <a name="migrate-lync-room-system-lrs-devices-to-skype-room-system-v2"></a><span data-ttu-id="28d22-103">将 Lync 会议室系统 (LRS) 设备迁移到 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="28d22-103">Migrate Lync Room System (LRS) devices to Skype Room System v2</span></span>

<span data-ttu-id="28d22-104">Skype 会议室系统版本 1 (SR v1) 软件 Lync 会议室系统 (LRS) 设备已达到[2018 年 10 月 9，支持的结束](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018)。</span><span class="sxs-lookup"><span data-stu-id="28d22-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software has reached [end of support on October 9, 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018).</span></span> <span data-ttu-id="28d22-105">这意味着 Skype 会议室系统 v1 软件将不再能够获取所有产品更新或修补程序不再。</span><span class="sxs-lookup"><span data-stu-id="28d22-105">This means Skype Room Systems v1 software will no longer get any product updates or fixes anymore.</span></span> <span data-ttu-id="28d22-106">建议使用 Skype 会议室系统 v1 软件的 Lync 会议室系统设备的客户升级其设备到 Skype 会议室系统版本 2 (SR v2)。</span><span class="sxs-lookup"><span data-stu-id="28d22-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Skype Room System version 2 (SRS v2).</span></span>

<span data-ttu-id="28d22-107">Skype 会议室系统版本 2 (SR v2) 软件与除了 Skype 的 Microsoft 团队适用于会议和呼叫所有 SR v2 支持设备上的业务服务器和联机服务。</span><span class="sxs-lookup"><span data-stu-id="28d22-107">Skype Room System Version 2 (SRS v2) software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all SRS v2 supported devices.</span></span>

<span data-ttu-id="28d22-108">您现有设备**可能会**继续工作后的末尾 Skype 会议室系统 v1 软件支持。</span><span class="sxs-lookup"><span data-stu-id="28d22-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software support.</span></span> <span data-ttu-id="28d22-109">但是，如果此软件命中需要释放修复的 Microsoft 软件 bug，它将不支持。</span><span class="sxs-lookup"><span data-stu-id="28d22-109">However, if this software hits a software bug that needs Microsoft to release a fix, it will not be supported.</span></span> <span data-ttu-id="28d22-110">SR v1 使用 TLS 1.0 / 1.1 其 Microsoft 将来将弃用。</span><span class="sxs-lookup"><span data-stu-id="28d22-110">SRS v1 uses TLS 1.0/ 1.1 which will be deprecated by Microsoft in the future.</span></span> <span data-ttu-id="28d22-111">您可以了解有关[TLS 1.0/1.1 否决准备](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="28d22-111">You can learn more about [Preparing for TLS 1.0/1.1 Deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span> <span data-ttu-id="28d22-112">Skype 会议室系统 V2 正在添加支持 TLS 1.2 和将继续过 2018 年 10 月 31，工作。</span><span class="sxs-lookup"><span data-stu-id="28d22-112">Skype Room System V2 is adding support for TLS 1.2 and will continue to work past October 31, 2018.</span></span> <span data-ttu-id="28d22-113">Skype for Business 的本地客户不应禁用 TLS 1.0/1.1，直到 Skype 会议室系统 V2 宣布支持 TLS 1.2 无论 TLS 1.0/1.1 否决的一般准则。</span><span class="sxs-lookup"><span data-stu-id="28d22-113">Skype for Business on-premises customers should not disable TLS 1.0/1.1 until Skype Room System V2 announces support for TLS 1.2 regardless of general guidelines on TLS 1.0/1.1 deprecation.</span></span>

## <a name="which-devices-are-affected"></a><span data-ttu-id="28d22-114">哪些设备会受到影响？</span><span class="sxs-lookup"><span data-stu-id="28d22-114">Which devices are affected?</span></span>

<span data-ttu-id="28d22-115">下面是此更改影响的设备的列表：</span><span class="sxs-lookup"><span data-stu-id="28d22-115">Here is the list of the devices that are affected by this change:</span></span>

- <span data-ttu-id="28d22-116">Crestron RL</span><span class="sxs-lookup"><span data-stu-id="28d22-116">Crestron RL</span></span>
- [<span data-ttu-id="28d22-117">Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="28d22-117">Crestron RL2</span></span>](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="28d22-118">智能会议室系统</span><span class="sxs-lookup"><span data-stu-id="28d22-118">SMART Room systems</span></span>](https://support.smarttech.com/en/hardware/room-systems-skype)
- [<span data-ttu-id="28d22-119">Polycom CX8000</span><span class="sxs-lookup"><span data-stu-id="28d22-119">Polycom CX8000</span></span>](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)


## <a name="upgrade-options"></a><span data-ttu-id="28d22-120">升级选项</span><span class="sxs-lookup"><span data-stu-id="28d22-120">Upgrade options</span></span>

<span data-ttu-id="28d22-121">有多个选项下一代 Skype 会议室系统 (SR v2) 的升级 Lync 会议室系统。</span><span class="sxs-lookup"><span data-stu-id="28d22-121">There are multiple options for upgrading Lync Room Systems to the next generation of Skype Room Systems (SRS v2).</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="28d22-122">Crestron 硬件折旧计划</span><span class="sxs-lookup"><span data-stu-id="28d22-122">Crestron hardware Trade-in program</span></span>

<span data-ttu-id="28d22-123">Crestron 将提供升级到[Crestron SR 系统](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr)或等效的所有非 Crestron Lync 会议室系统客户 （例如智能或 Polycom LRS）。</span><span class="sxs-lookup"><span data-stu-id="28d22-123">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers (e.g Smart or Polycom LRS).</span></span> <span data-ttu-id="28d22-124">此程序的详细信息，请参阅[此处](https://support.crestron.com/app/answers/answer_view/a_id/1000220)或<!-- For details, -->[电子邮件](mailto:lrsupgrade@crestron.com)Crestron LRS 支持。</span><span class="sxs-lookup"><span data-stu-id="28d22-124">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or <!-- For details, -->[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  

### <a name="crestron-rl2-upgrade-to-srs-v2"></a><span data-ttu-id="28d22-125">Crestron RL2 升级到 SR v2</span><span class="sxs-lookup"><span data-stu-id="28d22-125">Crestron RL2 upgrade to SRS v2</span></span>

<span data-ttu-id="28d22-126">现有 Crestron RL2 （也称为 Crestron RL200） 客户可以获取升级到 RL3 使用当前 RL2 的升级工具包的每个设备的最小成本。</span><span class="sxs-lookup"><span data-stu-id="28d22-126">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade kit to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="28d22-127">此程序的详细信息，请参阅[此处](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)。</span><span class="sxs-lookup"><span data-stu-id="28d22-127">See details of this program [here](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).</span></span>

### <a name="smart-room-systems-upgrade"></a><span data-ttu-id="28d22-128">智能会议室系统升级</span><span class="sxs-lookup"><span data-stu-id="28d22-128">SMART Room Systems upgrade</span></span>

<span data-ttu-id="28d22-129">对于智能 LRS 客户，除了 Crestron 硬件折旧计划，智能也正在提供解决方案升级到 Skype 会议室系统 v2。</span><span class="sxs-lookup"><span data-stu-id="28d22-129">For SMART LRS customers, apart from Crestron hardware trade-in program, SMART is also working on providing a solution to upgrade to Skype Room System v2.</span></span> <span data-ttu-id="28d22-130">向下产品支持的客户，将通过智能技术 Inc.提供此升级。</span><span class="sxs-lookup"><span data-stu-id="28d22-130">This upgrade will be provided by SMART Technologies Inc. to customer under product support.</span></span> <span data-ttu-id="28d22-131">请参阅有关此[此处](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="28d22-131">Please see more about this [here](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).</span></span>


## <a name="what-should-you-do"></a><span data-ttu-id="28d22-132">怎么办？</span><span class="sxs-lookup"><span data-stu-id="28d22-132">What should you do?</span></span>

<span data-ttu-id="28d22-133">我们建议您打算到之前使用上面提到的升级选项的 TLS 1.0/1.1 否决的 Skype 会议室系统 v2 更新 Lync 会议室系统的设备。</span><span class="sxs-lookup"><span data-stu-id="28d22-133">We recommend you plan to update Lync Room System devices to Skype Room Systems v2 before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="28d22-134">此外，也可以考虑将新设备认证 SR v2 替换为现有的设备。</span><span class="sxs-lookup"><span data-stu-id="28d22-134">Additionally, you may also consider replacing existing devices with new devices certified for SRS v2.</span></span> <span data-ttu-id="28d22-135">有关详细信息，请参阅[聊天室设备](https://aka.ms/roomdevices)和也看看[Skype 会议室系统 v2 要求](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)。</span><span class="sxs-lookup"><span data-stu-id="28d22-135">See [Room devices](https://aka.ms/roomdevices) for details and also take a look at [Skype Room Systems v2 requirements](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  

> [!NOTE]
> <span data-ttu-id="28d22-136">Skype 会议室系统 v2 中尚不支持触摸和白板功能。</span><span class="sxs-lookup"><span data-stu-id="28d22-136">Touch and whiteboard functionality is not yet supported in Skype Room System v2.</span></span> <span data-ttu-id="28d22-137">触摸和白板支持当前计划的 Skype 会议室系统 v2，并将添加到 2019年。</span><span class="sxs-lookup"><span data-stu-id="28d22-137">Touch and whiteboard support is currently planned for Skype Room System v2 and will be added in 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="28d22-138">Skype 会议室系统 V2 软件支持与应用程序版本 4.0.64.0 截止 2018 年 12 月 14，TLS 1.2 协议。</span><span class="sxs-lookup"><span data-stu-id="28d22-138">Skype Room System V2 software supports the TLS 1.2 protocol as of December 14, 2018 with app version 4.0.64.0.</span></span> <span data-ttu-id="28d22-139">对于本地客户通过 TLS 1.2 通信启用 Skype 会议室系统 V2 需要 Skype 业务 Server 2015 累积更新 9 (CU9) 或 Skype 业务 Server 2019 累积更新 1 (CU1)。</span><span class="sxs-lookup"><span data-stu-id="28d22-139">For on-premises customers, enabling communication over TLS 1.2 for Skype Room System V2 requires Skype for Business Server 2015 Cumulative Update 9 (CU9) or Skype for Business Server 2019 Cumulative Update 1 (CU1).</span></span> <span data-ttu-id="28d22-140">更改应不会影响 Skype 的业务联机客户客户端的更改一样向前和向后兼容。</span><span class="sxs-lookup"><span data-stu-id="28d22-140">The change should not affect Skype for Business Online customers as client changes are forward and backward compliant.</span></span>
