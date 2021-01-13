---
title: 监视 Skype for Business Server 中的服务器内存容量限制
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: 摘要：了解如何监视 Skype for Business Server 中的服务器内存容量限制。
ms.openlocfilehash: f1423d840fdf690332081a8083617c3a072b373c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814292"
---
# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server"></a><span data-ttu-id="85596-103">监视 Skype for Business Server 中的服务器内存容量限制</span><span class="sxs-lookup"><span data-stu-id="85596-103">Monitor for server memory capacity limits in Skype for Business Server</span></span>
 
<span data-ttu-id="85596-104">**摘要：** 了解如何监视 Skype for Business Server 中的服务器内存容量限制。</span><span class="sxs-lookup"><span data-stu-id="85596-104">**Summary:** Learn how to monitor for server memory capacity limits in Skype for Business Server.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="85596-105">本主题中有关容量规划的信息仅适用于 Lync 2010 移动客户端和 Mobility Service (Mcx) 。</span><span class="sxs-lookup"><span data-stu-id="85596-105">The information in this topic that refers to Capacity Planning pertains only to Lync 2010 Mobile clients and the Mobility Service (Mcx).</span></span> <span data-ttu-id="85596-106">Lync 2013 移动客户端使用的统一通信 Web API (UCWA) 的容量规划由 Lync Server 2013 规划工具提供。</span><span class="sxs-lookup"><span data-stu-id="85596-106">Capacity Planning for the Unified Communications Web API (UCWA), used by the Lync 2013 Mobile clients, is provided by the Lync Server 2013, Planning Tool.</span></span> 

> [!NOTE]
> <span data-ttu-id="85596-107">SKYPE (Server 2019 中不再提供对) 移动客户端的 MCX 移动服务支持。</span><span class="sxs-lookup"><span data-stu-id="85596-107">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="85596-108">所有当前的 Skype for Business 移动客户端已使用统一通信 Web API (UCWA) 来支持即时消息 (IM) 、状态和联系人。</span><span class="sxs-lookup"><span data-stu-id="85596-108">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="85596-109">使用 MCX 的旧客户端的用户将需要升级到当前客户端。</span><span class="sxs-lookup"><span data-stu-id="85596-109">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="85596-110">两个移动性能计数器可以帮助您确定当前使用情况，并帮助您规划 Skype for Business Server Mobility Service (Mcx) 的容量，以及监视 UCWA 的内存使用情况。</span><span class="sxs-lookup"><span data-stu-id="85596-110">Two mobility performance counters can help you to determine your current usage and help you plan capacity for the Skype for Business Server Mobility Service (Mcx), as well as to monitor memory usage for UCWA.</span></span> <span data-ttu-id="85596-111">对于 UCWA，计数器类别为 **LS：WEB - UCWA。**</span><span class="sxs-lookup"><span data-stu-id="85596-111">For UCWA, the counter category is **LS:WEB - UCWA**.</span></span> <span data-ttu-id="85596-112">对于 Mobility Service (Mcx) ，计数器在 **类别 LS：WEB - Mobile Communication Service 下**。</span><span class="sxs-lookup"><span data-stu-id="85596-112">For the Mobility Service (Mcx), the counters are under the category **LS:WEB - Mobile Communication Service**.</span></span> <span data-ttu-id="85596-113">要监视的计数器包括：</span><span class="sxs-lookup"><span data-stu-id="85596-113">The counters to monitor are:</span></span>
  
- <span data-ttu-id="85596-114">**Currently Active Session Count with Active Presence Subscriptions，** which is the current number of endpoints registered through UCWA or the Mobility Service (Mcx) that have active presence subscriptions (number of always-connected mobile users) </span><span class="sxs-lookup"><span data-stu-id="85596-114">**Currently Active Session Count with Active Presence Subscriptions**, which is the current number of endpoints registered through UCWA or the Mobility Service (Mcx) that have active presence subscriptions (number of always-connected mobile users)</span></span>
    
- <span data-ttu-id="85596-115">**Currently Active Session Count**， which is the current number of endpoints registered through UCWA or the Mobility Service</span><span class="sxs-lookup"><span data-stu-id="85596-115">**Currently Active Session Count**, which is the current number of endpoints registered through UCWA or the Mobility Service</span></span>
    
<span data-ttu-id="85596-116">如果当前 Active **Session Count with Active Presence Subscriptions** 和 Currently Active Session **Count** 的差值随着时间的推移较小，这意味着大多数移动设备用户都有始终连接的设备，例如 Android 或 Nokia 移动设备 (for Mcx) 。</span><span class="sxs-lookup"><span data-stu-id="85596-116">If the difference between **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** is small over time, this means that most mobile device users have an always-connected device, such as an Android or Nokia mobile device (for Mcx only).</span></span> <span data-ttu-id="85596-117">UCWA 始终连接的设备包括运行 Lync 2013 移动客户端的 Apple 和 Android) 。</span><span class="sxs-lookup"><span data-stu-id="85596-117">UCWA always-connected devices include Apple and Android devices running Lync 2013 Mobile clients).</span></span> <span data-ttu-id="85596-118">如果当前 **活动会话计数** 比具有 **活动** 状态订阅的"当前活动会话计数"要高很多，则表明使用后台终结点设备（如 Apple iOS 设备或 Mcx 下的 Windows Phone）的用户更多。</span><span class="sxs-lookup"><span data-stu-id="85596-118">If **Currently Active Session Count** is much higher than **Currently Active Session Count with Active Presence Subscriptions**, this indicates that more users are using a background endpoint device, such as an Apple iOS device or Windows Phone under Mcx.</span></span> <span data-ttu-id="85596-119"> (Windows Phone 是唯一一个将注册为此客户端的 Lync 2013 移动) 。</span><span class="sxs-lookup"><span data-stu-id="85596-119">(Windows Phone is the only Lync 2013 Mobile client that will register as this).</span></span>
  
<span data-ttu-id="85596-120">应基于预期使用情况、容量规划结果以及持续监控 Mobility Service 和其他前端服务器计数器，对具有 **活动** 状态订阅的"当前活动会话计数"和"当前 **活动** 会话计数"性能计数器设置限制。</span><span class="sxs-lookup"><span data-stu-id="85596-120">You should set a limit on the **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** performance counters based on your expected usage, capacity planning results, and ongoing monitoring of Mobility Service and other Front End Server counters.</span></span> <span data-ttu-id="85596-121">您设置的限制应使您能够评估服务器容量，并当超出容量时发出警报。</span><span class="sxs-lookup"><span data-stu-id="85596-121">The limits you set should enable you to evaluate server capacity and raise alerts when capacity is exceeded.</span></span>
  
<span data-ttu-id="85596-122">若要确定适当的限制，您需要首先确定 Mobility Service 的前端服务器上可用的内存量。</span><span class="sxs-lookup"><span data-stu-id="85596-122">To determine the appropriate limits, you need to first determine how much memory is available on the Front End Server for the Mobility Service.</span></span> <span data-ttu-id="85596-123">根据以下公式，监视计数器以确定何时需要规划额外容量：</span><span class="sxs-lookup"><span data-stu-id="85596-123">Monitor the counters to determine when you need to plan for extra capacity, according to the following formula:</span></span>
  
<span data-ttu-id="85596-124">Mcx Mobility Service (MB) = 164 + (400 + 134) / 1024 \* **Currently Active Session Count with Active Presence Subscriptions** + 400 / 1024 \* ( Currently Active Session **Count** Currently Active Session Count with Active  -  **Presence Subscriptions**) </span><span class="sxs-lookup"><span data-stu-id="85596-124">Total memory used by the Mcx Mobility Service (MB) = 164 + (400 + 134) / 1024 \* **Currently Active Session Count with Active Presence Subscriptions** + 400 / 1024 \* ( **Currently Active Session Count** - **Currently Active Session Count with Active Presence Subscriptions**)</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="85596-125">Microsoft Lync Server 2010 容量计算器是一个电子表格，它预填充了所有公式，使规划器可以确定 Skype for Business 服务器（包括 CPU、内存和硬盘驱动器）的要求。</span><span class="sxs-lookup"><span data-stu-id="85596-125">The Microsoft Lync Server 2010 Capacity Calculator is a spreadsheet that is prepopulated with all of the formulas that enable a planner to determine what the requirements will be for the Skype for Business servers, including CPU, memory, and hard drive.</span></span> <span data-ttu-id="85596-126">您可以 [下载电子表格和关联的文档](https://go.microsoft.com/fwlink/p/?LinkID=212657)。</span><span class="sxs-lookup"><span data-stu-id="85596-126">You can [download the spreadsheet and an associated document](https://go.microsoft.com/fwlink/p/?LinkID=212657).</span></span> 
  
<span data-ttu-id="85596-127">前端服务器需要足够的可用内存来支持故障转移情况下的移动服务。</span><span class="sxs-lookup"><span data-stu-id="85596-127">The Front End Server needs enough available memory to support the Mobility Service in failover situations.</span></span> <span data-ttu-id="85596-128">您可以使用 **Memory\Available Mbytes** 计数器或使用前面提到的公式来规划预计 Mobility Service 使用的内存量，以监视前端服务器上当前的可用内存。</span><span class="sxs-lookup"><span data-stu-id="85596-128">You can monitor the current available memory on the Front End Server by using the **Memory\Available Mbytes** counter, or by using the equation mentioned earlier, to plan for the amount of memory that you expect the Mobility Service to use.</span></span>
  
<span data-ttu-id="85596-129">如果规划预计的移动用户数时，前端服务器上可用的内存量小于 1，500 MB，则需要添加更多硬件以支持 Mobility Service。</span><span class="sxs-lookup"><span data-stu-id="85596-129">If the amount of memory available on the Front End Server is lower than 1,500 MB when you plan for the expected number of mobility users, you need to add more hardware to support the Mobility Service.</span></span> <span data-ttu-id="85596-130">有关详细信息，请参阅操作文档中的 ["监视 Skype for Business Server](monitor-mobility-performance.md) 中的移动性能"。</span><span class="sxs-lookup"><span data-stu-id="85596-130">For more details, see [Monitor mobility for performance in Skype for Business Server](monitor-mobility-performance.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="85596-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="85596-131">See also</span></span>

[<span data-ttu-id="85596-132">监视 Skype for Business Server 中的移动性能</span><span class="sxs-lookup"><span data-stu-id="85596-132">Monitor mobility for performance in Skype for Business Server</span></span>](monitor-mobility-performance.md)
