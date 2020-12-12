---
title: 将 Lync Room System 设备迁移到 Microsoft Teams 会议室
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: 阅读本主题，了解如何迁移 Lync Room System 设备以使用 Microsoft Teams 会议室软件。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d8da14f2d5f3ec75c6a9fb9c03a33d7e83cd1aed
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662617"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a><span data-ttu-id="677c7-103">将 Lync Room System (LRS) 迁移到 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="677c7-103">Migrate Lync Room System (LRS) devices to Microsoft Teams Rooms</span></span>

<span data-ttu-id="677c7-104">具有 Skype Room System 版本 1 (SRS v1) 软件的 Lync Room System (LRS) 设备于 [2018 年 10](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018)月 9 日终止支持。</span><span class="sxs-lookup"><span data-stu-id="677c7-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software has reached [end of support on October 9, 2018](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018).</span></span> <span data-ttu-id="677c7-105">这意味着 Skype Room Systems v1 软件将不再获得任何产品更新或修补程序。</span><span class="sxs-lookup"><span data-stu-id="677c7-105">This means Skype Room Systems v1 software will no longer get any product updates or fixes anymore.</span></span> <span data-ttu-id="677c7-106">建议安装有 Skype Room System v1 软件的 Lync Room System 设备的用户将其设备升级到 Microsoft Teams 会议室。</span><span class="sxs-lookup"><span data-stu-id="677c7-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Microsoft Teams Rooms.</span></span>

<span data-ttu-id="677c7-107">除了 Skype for Business Server 和 Online 服务外，Microsoft Teams 会议室软件还适用于 Microsoft Teams，用于会议和呼叫所有 Microsoft Teams 会议室支持的设备。</span><span class="sxs-lookup"><span data-stu-id="677c7-107">Microsoft Teams Rooms software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all Microsoft Teams Rooms supported devices.</span></span>

<span data-ttu-id="677c7-108">在 Skype会议室系统 v1 软件支持结束后，你的现有设备可能会继续工作。</span><span class="sxs-lookup"><span data-stu-id="677c7-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software support.</span></span> <span data-ttu-id="677c7-109">但是，如果此软件命中需要 Microsoft 发布修补程序的软件 bug，则它将不受支持。</span><span class="sxs-lookup"><span data-stu-id="677c7-109">However, if this software hits a software bug that needs Microsoft to release a fix, it will not be supported.</span></span> <span data-ttu-id="677c7-110">SRS v1 使用 TLS 1.0/ 1.1，将来 Microsoft 将弃用它。</span><span class="sxs-lookup"><span data-stu-id="677c7-110">SRS v1 uses TLS 1.0/ 1.1 which will be deprecated by Microsoft in the future.</span></span> <span data-ttu-id="677c7-111">可以详细了解如何准备弃用[TLS 1.0/1.1。](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608)</span><span class="sxs-lookup"><span data-stu-id="677c7-111">You can learn more about [preparing for TLS 1.0/1.1 deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span> 

## <a name="which-devices-are-affected"></a><span data-ttu-id="677c7-112">哪些设备受影响？</span><span class="sxs-lookup"><span data-stu-id="677c7-112">Which devices are affected?</span></span>

<span data-ttu-id="677c7-113">下面是受此更改影响的设备列表：</span><span class="sxs-lookup"><span data-stu-id="677c7-113">Here is the list of the devices that are affected by this change:</span></span>

- <span data-ttu-id="677c7-114">Crestron RL</span><span class="sxs-lookup"><span data-stu-id="677c7-114">Crestron RL</span></span>
- [<span data-ttu-id="677c7-115">Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="677c7-115">Crestron RL2</span></span>](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="677c7-116">SMART Room 系统</span><span class="sxs-lookup"><span data-stu-id="677c7-116">SMART Room systems</span></span>](https://support.smarttech.com/en/hardware/room-systems-skype)
- [<span data-ttu-id="677c7-117">Polycom CX8000</span><span class="sxs-lookup"><span data-stu-id="677c7-117">Polycom CX8000</span></span>](https://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a><span data-ttu-id="677c7-118">升级选项</span><span class="sxs-lookup"><span data-stu-id="677c7-118">Upgrade options</span></span>

<span data-ttu-id="677c7-119">有多种选项用于将 Lync Room Systems 升级到下一代 Microsoft Teams 会议室。</span><span class="sxs-lookup"><span data-stu-id="677c7-119">There are multiple options for upgrading Lync Room Systems to the next generation of Microsoft Teams Rooms.</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="677c7-120">Crestron 硬件折中程序</span><span class="sxs-lookup"><span data-stu-id="677c7-120">Crestron hardware Trade-in program</span></span>

<span data-ttu-id="677c7-121">对于 Smart 或 Polycom LRS 等所有非 (Lync Room System 客户 [，Crestron 将提供到 Crestron SR](https://www.crestron.com/products/featured-solutions/crestron-sr) 系统的升级或等效) 。</span><span class="sxs-lookup"><span data-stu-id="677c7-121">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers (e.g Smart or Polycom LRS).</span></span> <span data-ttu-id="677c7-122">在此处查看此计划 [的详细信息，](https://support.crestron.com/app/answers/answer_view/a_id/1000220) 或</span><span class="sxs-lookup"><span data-stu-id="677c7-122">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or</span></span> <!-- For details, --><span data-ttu-id="677c7-123">[电子邮件](mailto:lrsupgrade@crestron.com) Crestron LRS 支持。</span><span class="sxs-lookup"><span data-stu-id="677c7-123">[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a><span data-ttu-id="677c7-124">将 Crestron RL2 升级到 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="677c7-124">Crestron RL2 upgrade to Microsoft Teams Rooms</span></span>

<span data-ttu-id="677c7-125">现有 Crestron RL2 (也称为 Crestron RL200) 客户可以获取升级工具包，以使用每个设备的最低成本将当前 RL2 升级到 RL3。</span><span class="sxs-lookup"><span data-stu-id="677c7-125">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade kit to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="677c7-126">请在此处查看此计划 [的详细信息](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)。</span><span class="sxs-lookup"><span data-stu-id="677c7-126">See details of this program [here](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).</span></span>

### <a name="smart-room-systems-upgrade"></a><span data-ttu-id="677c7-127">SMART Room Systems 升级</span><span class="sxs-lookup"><span data-stu-id="677c7-127">SMART Room Systems upgrade</span></span>

<span data-ttu-id="677c7-128">对于 SMART LRS 客户，除了使用 Crestron 硬件折中计划外，SMART 还致力于提供升级到 Microsoft Teams 会议室的解决方案。</span><span class="sxs-lookup"><span data-stu-id="677c7-128">For SMART LRS customers, apart from Crestron hardware trade-in program, SMART is also working on providing a solution to upgrade to Microsoft Teams Rooms.</span></span> <span data-ttu-id="677c7-129">此升级由 SMART Technologies Inc. 在产品支持下提供给客户。</span><span class="sxs-lookup"><span data-stu-id="677c7-129">This upgrade will be provided by SMART Technologies Inc. to customer under product support.</span></span> <span data-ttu-id="677c7-130">请在此处查看有关 [此方面更多信息](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)。</span><span class="sxs-lookup"><span data-stu-id="677c7-130">Please see more about this [here](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).</span></span>


## <a name="what-should-you-do"></a><span data-ttu-id="677c7-131">应该怎么办？</span><span class="sxs-lookup"><span data-stu-id="677c7-131">What should you do?</span></span>

<span data-ttu-id="677c7-132">我们建议您计划使用上述升级选项在 TLS 1.0/1.1 弃用之前将 Lync Room System 设备更新到 Microsoft Teams 会议室。</span><span class="sxs-lookup"><span data-stu-id="677c7-132">We recommend you plan to update Lync Room System devices to Microsoft Teams Rooms before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="677c7-133">此外，还可以考虑将现有设备替换为通过 Microsoft Teams 会议室认证的新设备。</span><span class="sxs-lookup"><span data-stu-id="677c7-133">Additionally, you may also consider replacing existing devices with new devices certified for Microsoft Teams Rooms.</span></span> <span data-ttu-id="677c7-134">有关详细信息 [，请参阅](https://aka.ms/roomdevices) 会议室设备，并查看 [Microsoft Teams 会议室要求](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)。</span><span class="sxs-lookup"><span data-stu-id="677c7-134">See [Room devices](https://aka.ms/roomdevices) for details and also take a look at [Microsoft Teams Rooms requirements](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  


> [!NOTE]
> <span data-ttu-id="677c7-135">自 2018 年 12 月 14 日起，Microsoft Teams 会议室软件支持应用版本 4.0.64.0 的 TLS 1.2 协议。</span><span class="sxs-lookup"><span data-stu-id="677c7-135">Microsoft Teams Rooms software supports the TLS 1.2 protocol as of December 14, 2018 with app version 4.0.64.0.</span></span> <span data-ttu-id="677c7-136">对于本地客户，通过 TLS 1.2 为 Microsoft Teams 会议室启用通信需要 Skype for Business Server 2015 累积更新 9 (CU9) 或 Skype for Business Server 2019 累积更新 1 (CU1) 。</span><span class="sxs-lookup"><span data-stu-id="677c7-136">For on-premises customers, enabling communication over TLS 1.2 for Microsoft Teams Rooms requires Skype for Business Server 2015 Cumulative Update 9 (CU9) or Skype for Business Server 2019 Cumulative Update 1 (CU1).</span></span> <span data-ttu-id="677c7-137">更改不会影响 Skype for Business Online 客户，因为客户端更改是向前和向后兼容的。</span><span class="sxs-lookup"><span data-stu-id="677c7-137">The change should not affect Skype for Business Online customers as client changes are forward and backward compliant.</span></span>
