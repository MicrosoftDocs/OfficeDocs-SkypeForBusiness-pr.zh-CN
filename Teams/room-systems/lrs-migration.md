---
title: 将 Lync 会议室系统设备迁移到 Microsoft 团队聊天室
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: 阅读本主题，了解如何将 Lync 会议室系统设备迁移到使用 Microsoft 团队聊天室软件。
ms.openlocfilehash: 377e901446d69e0956ff981b1b45686c949cf61c
ms.sourcegitcommit: 70bf1669442bbb50cb293c86d6a0c80fb3b2b55a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2019
ms.locfileid: "38675356"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a><span data-ttu-id="30fb2-103">将 Lync 会议室系统（LRS）设备迁移到 Microsoft 团队聊天室</span><span class="sxs-lookup"><span data-stu-id="30fb2-103">Migrate Lync Room System (LRS) devices to Microsoft Teams Rooms</span></span>

<span data-ttu-id="30fb2-104">[在2018年10月9日，](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018)具有 Skype 会议室系统版本1（SRS v1）软件的 Lync 会议室系统（LRS）设备已达到支持的结束。</span><span class="sxs-lookup"><span data-stu-id="30fb2-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software has reached [end of support on October 9, 2018](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018).</span></span> <span data-ttu-id="30fb2-105">这意味着 Skype Room Systems v1 软件将不再获得任何产品更新或修补程序。</span><span class="sxs-lookup"><span data-stu-id="30fb2-105">This means Skype Room Systems v1 software will no longer get any product updates or fixes anymore.</span></span> <span data-ttu-id="30fb2-106">建议安装有 Skype Room System v1 软件的 Lync Room System 设备的用户将其设备升级到 Microsoft Teams 会议室。</span><span class="sxs-lookup"><span data-stu-id="30fb2-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Microsoft Teams Rooms.</span></span>

<span data-ttu-id="30fb2-107">Microsoft 团队会议室软件除了适用于 office 的 Skype for business 服务器和在线服务，还可与 Microsoft 团队一起使用，并可在所有 Microsoft 团队会议室支持的设备上通话。</span><span class="sxs-lookup"><span data-stu-id="30fb2-107">Microsoft Teams Rooms software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all Microsoft Teams Rooms supported devices.</span></span>

<span data-ttu-id="30fb2-108">在 Skype 会议室系统 v1 软件支持结束后，您的现有设备**可能会**继续正常工作。</span><span class="sxs-lookup"><span data-stu-id="30fb2-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software support.</span></span> <span data-ttu-id="30fb2-109">但是，如果此软件点击了需要 Microsoft 发布修补程序的软件 bug，则不受支持。</span><span class="sxs-lookup"><span data-stu-id="30fb2-109">However, if this software hits a software bug that needs Microsoft to release a fix, it will not be supported.</span></span> <span data-ttu-id="30fb2-110">SRS v1 使用 TLS 1.0/1.1，将来将被 Microsoft 弃用。</span><span class="sxs-lookup"><span data-stu-id="30fb2-110">SRS v1 uses TLS 1.0/ 1.1 which will be deprecated by Microsoft in the future.</span></span> <span data-ttu-id="30fb2-111">你可以了解有关[为 TLS 1.0/1.1 弃用做准备的](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608)详细信息。</span><span class="sxs-lookup"><span data-stu-id="30fb2-111">You can learn more about [Preparing for TLS 1.0/1.1 Deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span> <span data-ttu-id="30fb2-112">Microsoft 团队聊天室正在添加对 TLS 1.2 的支持，将继续在10月31日（2018）之前工作。</span><span class="sxs-lookup"><span data-stu-id="30fb2-112">Microsoft Teams Rooms is adding support for TLS 1.2 and will continue to work past October 31, 2018.</span></span> <span data-ttu-id="30fb2-113">Skype for Business 本地客户不应禁用 TLS 1.0/1.1，直到 Microsoft 团队聊天室宣布对 TLS 1.2 的支持（无论 TLS 1.0/1.1 过时的常规指南）。</span><span class="sxs-lookup"><span data-stu-id="30fb2-113">Skype for Business on-premises customers should not disable TLS 1.0/1.1 until Microsoft Teams Rooms announces support for TLS 1.2 regardless of general guidelines on TLS 1.0/1.1 deprecation.</span></span>

## <a name="which-devices-are-affected"></a><span data-ttu-id="30fb2-114">哪些设备受到影响？</span><span class="sxs-lookup"><span data-stu-id="30fb2-114">Which devices are affected?</span></span>

<span data-ttu-id="30fb2-115">下面是受此更改影响的设备的列表：</span><span class="sxs-lookup"><span data-stu-id="30fb2-115">Here is the list of the devices that are affected by this change:</span></span>

- <span data-ttu-id="30fb2-116">Crestron RL</span><span class="sxs-lookup"><span data-stu-id="30fb2-116">Crestron RL</span></span>
- [<span data-ttu-id="30fb2-117">Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="30fb2-117">Crestron RL2</span></span>](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="30fb2-118">智能房间系统</span><span class="sxs-lookup"><span data-stu-id="30fb2-118">SMART Room systems</span></span>](https://support.smarttech.com/en/hardware/room-systems-skype)
- [<span data-ttu-id="30fb2-119">Polycom CX8000</span><span class="sxs-lookup"><span data-stu-id="30fb2-119">Polycom CX8000</span></span>](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a><span data-ttu-id="30fb2-120">升级选项</span><span class="sxs-lookup"><span data-stu-id="30fb2-120">Upgrade options</span></span>

<span data-ttu-id="30fb2-121">有多个选项可用于将 Lync 聊天室系统升级到下一代 Microsoft 团队聊天室。</span><span class="sxs-lookup"><span data-stu-id="30fb2-121">There are multiple options for upgrading Lync Room Systems to the next generation of Microsoft Teams Rooms.</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="30fb2-122">Crestron 硬件贸易计划</span><span class="sxs-lookup"><span data-stu-id="30fb2-122">Crestron hardware Trade-in program</span></span>

<span data-ttu-id="30fb2-123">Crestron 将为所有非 Crestron Lync 会议室系统客户（如 Smart 或 Polycom LRS）提供对[CRESTRON SR 系统](https://www.crestron.com/products/featured-solutions/crestron-sr)或等效项的升级。</span><span class="sxs-lookup"><span data-stu-id="30fb2-123">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers (e.g Smart or Polycom LRS).</span></span> <span data-ttu-id="30fb2-124">[在此处](https://support.crestron.com/app/answers/answer_view/a_id/1000220)查看此程序的详细信息或</span><span class="sxs-lookup"><span data-stu-id="30fb2-124">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or</span></span> <!-- For details, --><span data-ttu-id="30fb2-125">[电子邮件](mailto:lrsupgrade@crestron.com)Crestron LRS 支持。</span><span class="sxs-lookup"><span data-stu-id="30fb2-125">[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a><span data-ttu-id="30fb2-126">Crestron RL2 升级到 Microsoft 团队聊天室</span><span class="sxs-lookup"><span data-stu-id="30fb2-126">Crestron RL2 upgrade to Microsoft Teams Rooms</span></span>

<span data-ttu-id="30fb2-127">现有的 Crestron RL2 （也称为 Crestron RL200）客户可以获取升级工具包，以便使用每个设备的最低成本将当前 RL2 升级到 RL3。</span><span class="sxs-lookup"><span data-stu-id="30fb2-127">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade kit to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="30fb2-128">请[在此处](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)查看该程序的详细信息。</span><span class="sxs-lookup"><span data-stu-id="30fb2-128">See details of this program [here](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).</span></span>

### <a name="smart-room-systems-upgrade"></a><span data-ttu-id="30fb2-129">智能房间系统升级</span><span class="sxs-lookup"><span data-stu-id="30fb2-129">SMART Room Systems upgrade</span></span>

<span data-ttu-id="30fb2-130">对于 SMART LRS 客户，除了 Crestron 硬件的使用计划外，还提供了一种解决方案来升级到 Microsoft 团队的会议室。</span><span class="sxs-lookup"><span data-stu-id="30fb2-130">For SMART LRS customers, apart from Crestron hardware trade-in program, SMART is also working on providing a solution to upgrade to Microsoft Teams Rooms.</span></span> <span data-ttu-id="30fb2-131">此升级将由智能技术公司提供给产品支持部门的客户。</span><span class="sxs-lookup"><span data-stu-id="30fb2-131">This upgrade will be provided by SMART Technologies Inc. to customer under product support.</span></span> <span data-ttu-id="30fb2-132">请参阅[此处](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="30fb2-132">Please see more about this [here](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).</span></span>


## <a name="what-should-you-do"></a><span data-ttu-id="30fb2-133">应该怎么办？</span><span class="sxs-lookup"><span data-stu-id="30fb2-133">What should you do?</span></span>

<span data-ttu-id="30fb2-134">我们建议你计划在 TLS 1.0/1.1 弃用之前使用上述升级选项将 Lync 会议室系统设备更新到 Microsoft 团队聊天室。</span><span class="sxs-lookup"><span data-stu-id="30fb2-134">We recommend you plan to update Lync Room System devices to Microsoft Teams Rooms before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="30fb2-135">此外，你还可以考虑将现有设备替换为针对 Microsoft 团队聊天室认证的新设备。</span><span class="sxs-lookup"><span data-stu-id="30fb2-135">Additionally, you may also consider replacing existing devices with new devices certified for Microsoft Teams Rooms.</span></span> <span data-ttu-id="30fb2-136">有关详细信息，请参阅[房间设备](https://aka.ms/roomdevices)，还可查看[Microsoft 团队会议室的要求](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)。</span><span class="sxs-lookup"><span data-stu-id="30fb2-136">See [Room devices](https://aka.ms/roomdevices) for details and also take a look at [Microsoft Teams Rooms requirements](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  

> [!NOTE]
> <span data-ttu-id="30fb2-137">Microsoft 团队聊天室尚不支持触摸和白板功能。</span><span class="sxs-lookup"><span data-stu-id="30fb2-137">Touch and whiteboard functionality is not yet supported in Microsoft Teams Rooms.</span></span> <span data-ttu-id="30fb2-138">触摸和白板支持目前计划用于 Microsoft 团队聊天室，将添加到2019。</span><span class="sxs-lookup"><span data-stu-id="30fb2-138">Touch and whiteboard support is currently planned for Microsoft Teams Rooms and will be added in 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="30fb2-139">Microsoft 团队会议室软件支持的 TLS 1.2 协议，4.0.64.0 应用版本为2018。</span><span class="sxs-lookup"><span data-stu-id="30fb2-139">Microsoft Teams Rooms software supports the TLS 1.2 protocol as of December 14, 2018 with app version 4.0.64.0.</span></span> <span data-ttu-id="30fb2-140">对于本地客户，为 Microsoft 团队聊天室启用通过 TLS 1.2 进行通信需要 Skype for business Server 2015 累积更新9（CU9）或 Skype for business 服务器2019累积更新1（CU1）。</span><span class="sxs-lookup"><span data-stu-id="30fb2-140">For on-premises customers, enabling communication over TLS 1.2 for Microsoft Teams Rooms requires Skype for Business Server 2015 Cumulative Update 9 (CU9) or Skype for Business Server 2019 Cumulative Update 1 (CU1).</span></span> <span data-ttu-id="30fb2-141">更改不应影响 Skype for Business Online 客户，因为客户端更改是向前和向后兼容的。</span><span class="sxs-lookup"><span data-stu-id="30fb2-141">The change should not affect Skype for Business Online customers as client changes are forward and backward compliant.</span></span>
