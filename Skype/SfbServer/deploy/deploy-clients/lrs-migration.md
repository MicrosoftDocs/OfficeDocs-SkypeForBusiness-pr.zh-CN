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
ms.openlocfilehash: b2d748a37e7e060e19d0708b6979f9254af13682
ms.sourcegitcommit: 454ded73af5854d7b81a3b996702a6464b3fc313
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "27772901"
---
# <a name="migrate-lync-room-system-lrs-devices-to-skype-room-system-v2"></a><span data-ttu-id="6cc7f-103">将 Lync 会议室系统 (LRS) 设备迁移到 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="6cc7f-103">Migrate Lync Room System (LRS) devices to Skype Room System v2</span></span> 
<span data-ttu-id="6cc7f-104">Skype 会议室系统版本 1 (SR v1) 软件 Lync 会议室系统 (LRS) 设备已达到[2018 年 10 月 9，支持的结束](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018)。</span><span class="sxs-lookup"><span data-stu-id="6cc7f-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software has reached [end of support on October 9, 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018).</span></span> <span data-ttu-id="6cc7f-105">这意味着 Skype 会议室系统 v1 软件将不再能够获取所有产品更新或修补程序不再。</span><span class="sxs-lookup"><span data-stu-id="6cc7f-105">This means Skype Room Systems v1 software will no longer get any product updates or fixes anymore.</span></span> <span data-ttu-id="6cc7f-106">建议使用 Skype 会议室系统 v1 软件的 Lync 会议室系统设备的客户升级其设备到 Skype 会议室系统版本 2 (SR v2)。</span><span class="sxs-lookup"><span data-stu-id="6cc7f-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Skype Room System version 2 (SRS v2).</span></span>

<span data-ttu-id="6cc7f-107">Skype 会议室系统版本 2 (SR v2) 软件与除了 Skype 的 Microsoft 团队适用于会议和呼叫所有 SR v2 支持设备上的业务服务器和联机服务。</span><span class="sxs-lookup"><span data-stu-id="6cc7f-107">Skype Room System Version 2 (SRS v2) software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all SRS v2 supported devices.</span></span>

<span data-ttu-id="6cc7f-108">您现有设备**可能会**继续工作后的末尾 Skype 会议室系统 v1 软件支持。</span><span class="sxs-lookup"><span data-stu-id="6cc7f-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software support.</span></span> <span data-ttu-id="6cc7f-109">但是，如果此软件命中需要释放修复的 Microsoft 软件 bug，它将不支持。</span><span class="sxs-lookup"><span data-stu-id="6cc7f-109">However, if this software hits a software bug that needs Microsoft to release a fix, it will not be supported.</span></span> <span data-ttu-id="6cc7f-110">SR v1 使用 TLS 1.0 / 1.1 其 Microsoft 在将来将弃用。</span><span class="sxs-lookup"><span data-stu-id="6cc7f-110">SRS v1 uses TLS 1.0/ 1.1 which will be deprecated by Microsoft in future.</span></span> <span data-ttu-id="6cc7f-111">您可以了解有关[TLS 1.0/1.1 否决准备](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6cc7f-111">You can learn more about [Preparing for TLS 1.0/1.1 Deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span> <span data-ttu-id="6cc7f-112">Skype 会议室系统 V2 正在添加支持 TLS 1.2 和将继续过 2018 年 10 月 31，工作。</span><span class="sxs-lookup"><span data-stu-id="6cc7f-112">Skype Room System V2 is adding support for TLS 1.2 and will continue to work past October 31, 2018.</span></span> <span data-ttu-id="6cc7f-113">在内部部署客户业务的 Skype 不应禁用 TLS 1.0/1.1 Skype 会议室系统 V2 annouces 支持 TLS 1.2 无论 TLS 1.0/1.1 否决的一般准则。</span><span class="sxs-lookup"><span data-stu-id="6cc7f-113">Skype for Business on premise customers should not disable TLS 1.0/1.1 until Skype Room System V2 annouces support for TLS 1.2 regardless of general guidelines on TLS 1.0/1.1 deprecation.</span></span>

## <a name="which-devices-are-affected"></a><span data-ttu-id="6cc7f-114">哪些设备会受到影响？</span><span class="sxs-lookup"><span data-stu-id="6cc7f-114">Which devices are affected?</span></span>
<span data-ttu-id="6cc7f-115">下面是此更改影响的设备的列表：</span><span class="sxs-lookup"><span data-stu-id="6cc7f-115">Here is the list of the devices that are affected by this change:</span></span>
- [<span data-ttu-id="6cc7f-116">智能会议室系统</span><span class="sxs-lookup"><span data-stu-id="6cc7f-116">SMART Room systems</span></span>](https://support.smarttech.com/en/hardware/room-systems-skype)
- [<span data-ttu-id="6cc7f-117">Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="6cc7f-117">Crestron RL2</span></span>](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="6cc7f-118">Polycom CX8000</span><span class="sxs-lookup"><span data-stu-id="6cc7f-118">Polycom CX8000</span></span>](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)
- <span data-ttu-id="6cc7f-119">Crestron RL</span><span class="sxs-lookup"><span data-stu-id="6cc7f-119">Crestron RL</span></span>

## <a name="upgrade-options"></a><span data-ttu-id="6cc7f-120">升级选项</span><span class="sxs-lookup"><span data-stu-id="6cc7f-120">Upgrade options</span></span>
<span data-ttu-id="6cc7f-121">有多个选项下一代 Skype 会议室系统 (SR v2) 的升级 Lync 会议室系统。</span><span class="sxs-lookup"><span data-stu-id="6cc7f-121">There are multiple options for upgrading Lync Room Systems to the next generation of Skype Room Systems (SRS v2).</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="6cc7f-122">Crestron 硬件折旧计划</span><span class="sxs-lookup"><span data-stu-id="6cc7f-122">Crestron hardware Trade-in program</span></span>
<span data-ttu-id="6cc7f-123">Crestron 将为所有非 Crestron Lync 会议室系统客户[Crestron SR 系统](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr)或等效提供升级。</span><span class="sxs-lookup"><span data-stu-id="6cc7f-123">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers.</span></span> <span data-ttu-id="6cc7f-124">此程序的详细信息，请参阅[此处](https://support.crestron.com/app/answers/answer_view/a_id/1000220)或<!-- For details, -->[电子邮件](mailto:lrsupgrade@crestron.com)Crestron LRS 支持。</span><span class="sxs-lookup"><span data-stu-id="6cc7f-124">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or <!-- For details, -->[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  


### <a name="crestron-rl2-upgrade-to-srs-v2"></a><span data-ttu-id="6cc7f-125">Crestron RL2 升级到 SR V2</span><span class="sxs-lookup"><span data-stu-id="6cc7f-125">Crestron RL2 upgrade to SRS V2</span></span>
<span data-ttu-id="6cc7f-126">现有 Crestron RL2 （也称为 Crestron RL200） 客户可以获取升级到 RL3 使用当前 RL2 的升级工具包的每个设备的最小成本。</span><span class="sxs-lookup"><span data-stu-id="6cc7f-126">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade kit to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="6cc7f-127">此程序的详细信息，请参阅[此处](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)。</span><span class="sxs-lookup"><span data-stu-id="6cc7f-127">See details of this program [here](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).</span></span> 


### <a name="smart-room-systems-upgrade"></a><span data-ttu-id="6cc7f-128">智能会议室系统升级</span><span class="sxs-lookup"><span data-stu-id="6cc7f-128">SMART Room Systems upgrade</span></span> 
<span data-ttu-id="6cc7f-129">对于智能 LRS 客户，除了 Crestron 硬件折旧计划，Microsoft 和智能还提供解决方案升级到 Skype 会议室系统 v2 工作。</span><span class="sxs-lookup"><span data-stu-id="6cc7f-129">For SMART LRS customers, apart from Crestron hardware trade-in program, Microsoft and SMART are also working on providing a solution to upgrade to Skype Room System v2.</span></span> <span data-ttu-id="6cc7f-130">将通过智能技术 Inc.提供此升级请参阅有关此[此处](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6cc7f-130">This upgrade will be provided by SMART Technologies Inc. Please see more about this [here](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).</span></span>

<!--  
For later 
### Do-It-Yourself
A Do-It-Yourself option is also available for customers with upgrade to Windows 10 and Skype Room Systems v2 software. Windows 10 Enterprise Licenses are available through [approved resellers](https://www.microsoft.com/en-us/Licensing/how-to-buy/how-to-buy.aspx) and Skype Room System V2 software will be available through this guide. 
 
  
To use this option however, customers must additionaly buy a [Logitech Screen Share](https://www.logitech.com/en-us/product/screen-share) adapter. Microsoft will provide instructions on how to use this adapter with Skype Room System v2 software. 


Look for upgrade instructions on this page shortly. 
  
### Summary of upgrade options
This table lists summary of all available options for existing LRS devices:
<!--  For later 
| Upgrade Option | SMART Room Systems | Crestron RL2 | Polycom CX8000 | Crestron RL |
|:--- |:--- |:--- |:--- |:--- |
|**Crestron hardware </br>Trade-in program**|Available|Available|Available|Available|
|**Crestron RL3**|Not Available|Available|Not Available|Not Available|
|**Do-It-Yourself**|Available|Not Available|Not Available|Not Available|
| | | | | |
-->

## <a name="what-should-you-do"></a><span data-ttu-id="6cc7f-131">怎么办？</span><span class="sxs-lookup"><span data-stu-id="6cc7f-131">What should you do?</span></span>
<span data-ttu-id="6cc7f-132">我们建议您打算到之前使用上面提到的升级选项的 TLS 1.0/1.1 否决的 Skype 会议室系统 v2 更新 Lync 会议室系统的设备。</span><span class="sxs-lookup"><span data-stu-id="6cc7f-132">We recommend you plan to update Lync Room System devices to Skype Room Systems v2 before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="6cc7f-133">此外，也可以考虑将新设备认证 SR v2 替换为现有的设备。</span><span class="sxs-lookup"><span data-stu-id="6cc7f-133">Additionally, you may also consider replacing existing devices with new devices certified for SRS v2.</span></span> <span data-ttu-id="6cc7f-134">有关详细信息，请参阅[聊天室设备](https://aka.ms/roomdevices)和也看看[Skype 会议室系统 v2 要求](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)。</span><span class="sxs-lookup"><span data-stu-id="6cc7f-134">See [Room devices](https://aka.ms/roomdevices) for details and also take a look at [Skype Room Systems v2 requirements](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  

> [!NOTE]
> <span data-ttu-id="6cc7f-135">Skype 会议室系统 v2 中尚不支持触摸和白板功能。</span><span class="sxs-lookup"><span data-stu-id="6cc7f-135">Touch and whiteboard functionality is not yet supported in Skype Room System v2.</span></span> <span data-ttu-id="6cc7f-136">触摸和白板支持的 Skype 会议室系统 v2 积压工作中，将被添加到 H1 CY2019。</span><span class="sxs-lookup"><span data-stu-id="6cc7f-136">Touch and whiteboard support is in the backlog for Skype Room System v2 and will be added in H1 CY2019.</span></span>

> [!NOTE]
> <span data-ttu-id="6cc7f-137">Skype 会议室系统 V2 软件当前不支持 TLS 1.2 协议。</span><span class="sxs-lookup"><span data-stu-id="6cc7f-137">Skype Room System V2 software currently does not support TLS 1.2 protocol.</span></span> <span data-ttu-id="6cc7f-138">TLS 1.2 支持正在处理，并且将在 TLS 1.0/1.1 否决之前完成。</span><span class="sxs-lookup"><span data-stu-id="6cc7f-138">TLS 1.2 support is being worked on and will be completed before TLS 1.0/1.1 deprecation.</span></span> <span data-ttu-id="6cc7f-139">客户升级到 SR v2 运行 SR v2 应用程序的最新版本的会议室设备上将不会看到 TLS 1.0/1.1 否决任何的影响。</span><span class="sxs-lookup"><span data-stu-id="6cc7f-139">Customers upgradging to SRS v2 will not see any impact of TLS 1.0/1.1 deprecation on Room devices running latest version of SRS v2 app.</span></span> <span data-ttu-id="6cc7f-140">在内部部署客户业务的 Skype 不应禁用 TLS 1.0/1.1 Skype 会议室系统 V2 annouces 支持 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="6cc7f-140">Skype for Business on premise customers should not disable TLS 1.0/1.1 until Skype Room System V2 annouces support for TLS 1.2.</span></span> 
