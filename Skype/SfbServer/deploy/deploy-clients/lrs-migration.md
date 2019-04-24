---
title: 将 Lync 会议室系统设备迁移到 Microsoft 团队聊天室
ms.author: jambirk
author: jambirk
ms.reviewer: sohailta
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: 阅读本主题可了解如何迁移 Lync 会议室系统设备要使用的 Microsoft 团队聊天室软件。
ms.openlocfilehash: 2d9187643d8ffa72a843cbd72a47f4fd4a564f6e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219393"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a><span data-ttu-id="c9715-103">将 Lync 会议室系统 (LRS) 设备迁移到 Microsoft 团队聊天室</span><span class="sxs-lookup"><span data-stu-id="c9715-103">Migrate Lync Room System (LRS) devices to Microsoft Teams Rooms</span></span>

<span data-ttu-id="c9715-104">Skype 会议室系统版本 1 (SR v1) 软件 Lync 会议室系统 (LRS) 设备已达到[2018 年 10 月 9，支持的结束](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018)。</span><span class="sxs-lookup"><span data-stu-id="c9715-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software has reached [end of support on October 9, 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018).</span></span> <span data-ttu-id="c9715-105">这意味着 Skype 会议室系统 v1 软件将不再能够获取所有产品更新或修补程序不再。</span><span class="sxs-lookup"><span data-stu-id="c9715-105">This means Skype Room Systems v1 software will no longer get any product updates or fixes anymore.</span></span> <span data-ttu-id="c9715-106">建议使用 Skype 会议室系统 v1 软件的 Lync 会议室系统设备的客户以将其设备升级到 Microsoft 团队聊天室。</span><span class="sxs-lookup"><span data-stu-id="c9715-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Microsoft Teams Rooms.</span></span>

<span data-ttu-id="c9715-107">Microsoft 团队聊天室软件适用于 Microsoft 团队除了 Skype 业务服务器和联机会议和电话上所有的 Microsoft 团队会议室的服务支持的设备。</span><span class="sxs-lookup"><span data-stu-id="c9715-107">Microsoft Teams Rooms software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all Microsoft Teams Rooms supported devices.</span></span>

<span data-ttu-id="c9715-108">您现有设备**可能会**继续工作后的末尾 Skype 会议室系统 v1 软件支持。</span><span class="sxs-lookup"><span data-stu-id="c9715-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software support.</span></span> <span data-ttu-id="c9715-109">但是，如果此软件命中需要释放修复的 Microsoft 软件 bug，它将不支持。</span><span class="sxs-lookup"><span data-stu-id="c9715-109">However, if this software hits a software bug that needs Microsoft to release a fix, it will not be supported.</span></span> <span data-ttu-id="c9715-110">SR v1 使用 TLS 1.0 / 1.1 其 Microsoft 将来将弃用。</span><span class="sxs-lookup"><span data-stu-id="c9715-110">SRS v1 uses TLS 1.0/ 1.1 which will be deprecated by Microsoft in the future.</span></span> <span data-ttu-id="c9715-111">您可以了解有关[TLS 1.0/1.1 否决准备](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c9715-111">You can learn more about [Preparing for TLS 1.0/1.1 Deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span> <span data-ttu-id="c9715-112">Microsoft 团队会议室正在添加支持 TLS 1.2，并将继续过 2018 年 10 月 31，工作。</span><span class="sxs-lookup"><span data-stu-id="c9715-112">Microsoft Teams Rooms is adding support for TLS 1.2 and will continue to work past October 31, 2018.</span></span> <span data-ttu-id="c9715-113">Skype for Business 的本地客户不应禁用 TLS 1.0/1.1，直到 Microsoft 团队聊天室宣布支持 TLS 1.2 无论 TLS 1.0/1.1 否决的一般准则。</span><span class="sxs-lookup"><span data-stu-id="c9715-113">Skype for Business on-premises customers should not disable TLS 1.0/1.1 until Microsoft Teams Rooms announces support for TLS 1.2 regardless of general guidelines on TLS 1.0/1.1 deprecation.</span></span>

## <a name="which-devices-are-affected"></a><span data-ttu-id="c9715-114">哪些设备会受到影响？</span><span class="sxs-lookup"><span data-stu-id="c9715-114">Which devices are affected?</span></span>

<span data-ttu-id="c9715-115">下面是此更改影响的设备的列表：</span><span class="sxs-lookup"><span data-stu-id="c9715-115">Here is the list of the devices that are affected by this change:</span></span>

- <span data-ttu-id="c9715-116">Crestron RL</span><span class="sxs-lookup"><span data-stu-id="c9715-116">Crestron RL</span></span>
- [<span data-ttu-id="c9715-117">Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="c9715-117">Crestron RL2</span></span>](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="c9715-118">智能会议室系统</span><span class="sxs-lookup"><span data-stu-id="c9715-118">SMART Room systems</span></span>](https://support.smarttech.com/en/hardware/room-systems-skype)
- [<span data-ttu-id="c9715-119">Polycom CX8000</span><span class="sxs-lookup"><span data-stu-id="c9715-119">Polycom CX8000</span></span>](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a><span data-ttu-id="c9715-120">升级选项</span><span class="sxs-lookup"><span data-stu-id="c9715-120">Upgrade options</span></span>

<span data-ttu-id="c9715-121">有多种升级到下一代 Microsoft 团队聊天室 Lync 会议室系统。</span><span class="sxs-lookup"><span data-stu-id="c9715-121">There are multiple options for upgrading Lync Room Systems to the next generation of Microsoft Teams Rooms.</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="c9715-122">Crestron 硬件折旧计划</span><span class="sxs-lookup"><span data-stu-id="c9715-122">Crestron hardware Trade-in program</span></span>

<span data-ttu-id="c9715-123">Crestron 将提供升级到[Crestron SR 系统](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr)或等效的所有非 Crestron Lync 会议室系统客户 （例如智能或 Polycom LRS）。</span><span class="sxs-lookup"><span data-stu-id="c9715-123">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers (e.g Smart or Polycom LRS).</span></span> <span data-ttu-id="c9715-124">此程序的详细信息，请参阅[此处](https://support.crestron.com/app/answers/answer_view/a_id/1000220)或</span><span class="sxs-lookup"><span data-stu-id="c9715-124">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or</span></span> <!-- For details, --><span data-ttu-id="c9715-125">[电子邮件](mailto:lrsupgrade@crestron.com)Crestron LRS 支持。</span><span class="sxs-lookup"><span data-stu-id="c9715-125">[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a><span data-ttu-id="c9715-126">Crestron RL2 升级到 Microsoft 团队聊天室</span><span class="sxs-lookup"><span data-stu-id="c9715-126">Crestron RL2 upgrade to Microsoft Teams Rooms</span></span>

<span data-ttu-id="c9715-127">现有 Crestron RL2 （也称为 Crestron RL200） 客户可以获取升级到 RL3 使用当前 RL2 的升级工具包的每个设备的最小成本。</span><span class="sxs-lookup"><span data-stu-id="c9715-127">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade kit to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="c9715-128">此程序的详细信息，请参阅[此处](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)。</span><span class="sxs-lookup"><span data-stu-id="c9715-128">See details of this program [here](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).</span></span>

### <a name="smart-room-systems-upgrade"></a><span data-ttu-id="c9715-129">智能会议室系统升级</span><span class="sxs-lookup"><span data-stu-id="c9715-129">SMART Room Systems upgrade</span></span>

<span data-ttu-id="c9715-130">对于智能 LRS 客户，除了 Crestron 硬件折旧计划，智能也正在提供的解决方案升级到 Microsoft 团队聊天室。</span><span class="sxs-lookup"><span data-stu-id="c9715-130">For SMART LRS customers, apart from Crestron hardware trade-in program, SMART is also working on providing a solution to upgrade to Microsoft Teams Rooms.</span></span> <span data-ttu-id="c9715-131">向下产品支持的客户，将通过智能技术 Inc.提供此升级。</span><span class="sxs-lookup"><span data-stu-id="c9715-131">This upgrade will be provided by SMART Technologies Inc. to customer under product support.</span></span> <span data-ttu-id="c9715-132">请参阅有关此[此处](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c9715-132">Please see more about this [here](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).</span></span>


## <a name="what-should-you-do"></a><span data-ttu-id="c9715-133">怎么办？</span><span class="sxs-lookup"><span data-stu-id="c9715-133">What should you do?</span></span>

<span data-ttu-id="c9715-134">我们建议您打算使用上面提到的升级选项的 TLS 1.0/1.1 否决之前 Microsoft 团队 room 更新 Lync 会议室系统设备。</span><span class="sxs-lookup"><span data-stu-id="c9715-134">We recommend you plan to update Lync Room System devices to Microsoft Teams Rooms before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="c9715-135">此外，也可以考虑为 Microsoft 团队房间认证的新设备替换现有的设备。</span><span class="sxs-lookup"><span data-stu-id="c9715-135">Additionally, you may also consider replacing existing devices with new devices certified for Microsoft Teams Rooms.</span></span> <span data-ttu-id="c9715-136">有关详细信息，请参阅[聊天室设备](https://aka.ms/roomdevices)和也看看[Microsoft 团队聊天室要求](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)。</span><span class="sxs-lookup"><span data-stu-id="c9715-136">See [Room devices](https://aka.ms/roomdevices) for details and also take a look at [Microsoft Teams Rooms requirements](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  

> [!NOTE]
> <span data-ttu-id="c9715-137">在 Microsoft 团队聊天室中尚不支持触摸和白板功能。</span><span class="sxs-lookup"><span data-stu-id="c9715-137">Touch and whiteboard functionality is not yet supported in Microsoft Teams Rooms.</span></span> <span data-ttu-id="c9715-138">触摸和白板支持当前计划的 Microsoft 团队聊天室，并将添加到 2019年。</span><span class="sxs-lookup"><span data-stu-id="c9715-138">Touch and whiteboard support is currently planned for Microsoft Teams Rooms and will be added in 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="c9715-139">Microsoft 团队聊天室软件支持与应用程序版本 4.0.64.0 截止 2018 年 12 月 14，TLS 1.2 协议。</span><span class="sxs-lookup"><span data-stu-id="c9715-139">Microsoft Teams Rooms software supports the TLS 1.2 protocol as of December 14, 2018 with app version 4.0.64.0.</span></span> <span data-ttu-id="c9715-140">对于本地客户为 Microsoft 团队房间 over TLS 1.2 启用通信需要 Skype 业务 Server 2015 累积更新 9 (CU9) 或 Skype 业务 Server 2019 累积更新 1 (CU1)。</span><span class="sxs-lookup"><span data-stu-id="c9715-140">For on-premises customers, enabling communication over TLS 1.2 for Microsoft Teams Rooms requires Skype for Business Server 2015 Cumulative Update 9 (CU9) or Skype for Business Server 2019 Cumulative Update 1 (CU1).</span></span> <span data-ttu-id="c9715-141">更改应不会影响 Skype 的业务联机客户客户端的更改一样向前和向后兼容。</span><span class="sxs-lookup"><span data-stu-id="c9715-141">The change should not affect Skype for Business Online customers as client changes are forward and backward compliant.</span></span>
