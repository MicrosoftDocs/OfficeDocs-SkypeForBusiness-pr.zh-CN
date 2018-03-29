---
title: 在 Skype for Business Server 2015 中针对服务器内存容量限制进行监视
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: 摘要： 了解如何监视的服务器内存容量限制在 Skype 业务服务器 2015年。
ms.openlocfilehash: df05cdf43a7f09f49760f9671c900d6a9ea992b1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server-2015"></a><span data-ttu-id="25b7c-103">在 Skype for Business Server 2015 中针对服务器内存容量限制进行监视</span><span class="sxs-lookup"><span data-stu-id="25b7c-103">Monitor for server memory capacity limits in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="25b7c-104">**摘要：**了解如何监视的服务器内存容量限制在 Skype 业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="25b7c-104">**Summary:** Learn how to monitor for server memory capacity limits in Skype for Business Server 2015.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="25b7c-105">容量规划是指此主题中的信息仅适用于 Lync 2010 移动客户端和移动服务 (Mcx)。</span><span class="sxs-lookup"><span data-stu-id="25b7c-105">The information in this topic that refers to Capacity Planning pertains only to Lync 2010 Mobile clients and the Mobility Service (Mcx).</span></span> <span data-ttu-id="25b7c-106">容量规划的统一通信 Web API (UCWA)，使用 Lync 2013 移动客户端，可通过 Lync Server 2013，规划工具。</span><span class="sxs-lookup"><span data-stu-id="25b7c-106">Capacity Planning for the Unified Communications Web API (UCWA), used by the Lync 2013 Mobile clients, is provided by the Lync Server 2013, Planning Tool.</span></span> 
  
<span data-ttu-id="25b7c-107">两个移动性能计数器可帮助您确定当前的使用情况，并帮助您规划产能为 Skype 业务服务器 2015年移动服务 (Mcx) 也为 UCWA，监视内存使用情况。</span><span class="sxs-lookup"><span data-stu-id="25b7c-107">Two mobility performance counters can help you to determine your current usage and help you plan capacity for the Skype for Business Server 2015 Mobility Service (Mcx), as well as to monitor memory usage for UCWA.</span></span> <span data-ttu-id="25b7c-108">对于 UCWA，该计数器类别为**LS:WEB-UCWA**。</span><span class="sxs-lookup"><span data-stu-id="25b7c-108">For UCWA, the counter category is **LS:WEB - UCWA**.</span></span> <span data-ttu-id="25b7c-109">对于 Mobility Service (Mcx)，计数器类别为“**LS:WEB - 移动通信服务**”。</span><span class="sxs-lookup"><span data-stu-id="25b7c-109">For the Mobility Service (Mcx), the counters are under the category **LS:WEB - Mobile Communication Service**.</span></span> <span data-ttu-id="25b7c-110">要监控的计数器包括：</span><span class="sxs-lookup"><span data-stu-id="25b7c-110">The counters to monitor are:</span></span>
  
- <span data-ttu-id="25b7c-111">**Currently Active Session Count with Active Presence Subscriptions**，它是当前通过 UCWA 或 Mobility Service (Mcx) 注册的终结点的数目，这些终结点具有活动状态订阅（始终连接的移动用户的数目）</span><span class="sxs-lookup"><span data-stu-id="25b7c-111">**Currently Active Session Count with Active Presence Subscriptions**, which is the current number of endpoints registered through UCWA or the Mobility Service (Mcx) that have active presence subscriptions (number of always-connected mobile users)</span></span>
    
- <span data-ttu-id="25b7c-112">**Currently Active Session Count**，它是当前通过 UCWA 或 Mobility Service 注册的终结点的数目</span><span class="sxs-lookup"><span data-stu-id="25b7c-112">**Currently Active Session Count**, which is the current number of endpoints registered through UCWA or the Mobility Service</span></span>
    
<span data-ttu-id="25b7c-113">如果随着时间的推移，**当前活动状态订阅使用的活动会话数**和**当前活动会话数**之间的差异很小，这意味着大多数移动设备用户可以始终连接的设备，如 Android 或诺基亚移动设备 （仅 Mcx)。</span><span class="sxs-lookup"><span data-stu-id="25b7c-113">If the difference between **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** is small over time, this means that most mobile device users have an always-connected device, such as an Android or Nokia mobile device (for Mcx only).</span></span> <span data-ttu-id="25b7c-114">UCWA 总是连接设备包括苹果和 Android 设备运行 Lync 2013 移动客户端）。</span><span class="sxs-lookup"><span data-stu-id="25b7c-114">UCWA always-connected devices include Apple and Android devices running Lync 2013 Mobile clients).</span></span> <span data-ttu-id="25b7c-115">如果**当前活动会话数**要远远高于**当前活动状态订阅使用的活动会话计数**，这表示更多的用户正在使用背景终结点设备，如苹果 iOS 设备或在 Windows PhoneMcx。</span><span class="sxs-lookup"><span data-stu-id="25b7c-115">If **Currently Active Session Count** is much higher than **Currently Active Session Count with Active Presence Subscriptions**, this indicates that more users are using a background endpoint device, such as an Apple iOS device or Windows Phone under Mcx.</span></span> <span data-ttu-id="25b7c-116">（Windows Phone 是将注册为这只 Lync 2013 移动客户端）。</span><span class="sxs-lookup"><span data-stu-id="25b7c-116">(Windows Phone is the only Lync 2013 Mobile client that will register as this).</span></span>
  
<span data-ttu-id="25b7c-117">您应该根据您预期的用途、 容量规划的结果，并持续监视**当前活动状态订阅使用的活动会话数**和**当前活动会话计数**性能计数器上设置限制移动服务，前端服务器的其他计数器。</span><span class="sxs-lookup"><span data-stu-id="25b7c-117">You should set a limit on the **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** performance counters based on your expected usage, capacity planning results, and ongoing monitoring of Mobility Service and other Front End Server counters.</span></span> <span data-ttu-id="25b7c-118">您设置的限制应允许您计算服务器容量并在超出容量时发出警报。</span><span class="sxs-lookup"><span data-stu-id="25b7c-118">The limits you set should enable you to evaluate server capacity and raise alerts when capacity is exceeded.</span></span>
  
<span data-ttu-id="25b7c-119">若要确定适当的限制，您需要首先确定是移动服务的前端服务器上的可用内存量。</span><span class="sxs-lookup"><span data-stu-id="25b7c-119">To determine the appropriate limits, you need to first determine how much memory is available on the Front End Server for the Mobility Service.</span></span> <span data-ttu-id="25b7c-120">请监控计数器以根据以下公式确定您需要何时规划额外的容量：</span><span class="sxs-lookup"><span data-stu-id="25b7c-120">Monitor the counters to determine when you need to plan for extra capacity, according to the following formula:</span></span>
  
<span data-ttu-id="25b7c-121">使用通过 Mcx 移动服务 (MB) 的内存总量 = 164 + (400 + 134) / 1024年 ***当前活动状态订阅使用的活动会话数**+ 400 / 1024年 * (**当前活动会话数** - **当前处于活动状态的会话数的活动状态订阅**)</span><span class="sxs-lookup"><span data-stu-id="25b7c-121">Total memory used by the Mcx Mobility Service (MB) = 164 + (400 + 134) / 1024 * **Currently Active Session Count with Active Presence Subscriptions** + 400 / 1024 * ( **Currently Active Session Count** - **Currently Active Session Count with Active Presence Subscriptions**)</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="25b7c-122">Microsoft Lync 服务器 2010年容量计算器是填入所有的公式，使规划者确定要求将有关业务服务器，包括 CPU、 内存和硬盘的 Skype 是一个电子表格。</span><span class="sxs-lookup"><span data-stu-id="25b7c-122">The Microsoft Lync Server 2010 Capacity Calculator is a spreadsheet that is prepopulated with all of the formulas that enable a planner to determine what the requirements will be for the Skype for Business servers, including CPU, memory, and hard drive.</span></span> <span data-ttu-id="25b7c-123">您可以[下载该电子表格和相关联的文档](https://go.microsoft.com/fwlink/p/?LinkID=212657)。</span><span class="sxs-lookup"><span data-stu-id="25b7c-123">You can [download the spreadsheet and an associated document](https://go.microsoft.com/fwlink/p/?LinkID=212657).</span></span> 
  
<span data-ttu-id="25b7c-124">前端服务器需要内存不足，无法在故障转移情况下支持移动服务。</span><span class="sxs-lookup"><span data-stu-id="25b7c-124">The Front End Server needs enough available memory to support the Mobility Service in failover situations.</span></span> <span data-ttu-id="25b7c-125">通过使用该**Memory\Available 兆字节数**计数器，或通过使用前面提到的计划希望移动服务使用的内存量的计算公式，您可以监视在前端服务器上当前可用的内存。</span><span class="sxs-lookup"><span data-stu-id="25b7c-125">You can monitor the current available memory on the Front End Server by using the **Memory\Available Mbytes** counter, or by using the equation mentioned earlier, to plan for the amount of memory that you expect the Mobility Service to use.</span></span>
  
<span data-ttu-id="25b7c-126">如果在前端服务器上可用的内存量低于 1500 MB 在规划预期的移动用户数量时，您需要添加更多硬件以支持移动服务。</span><span class="sxs-lookup"><span data-stu-id="25b7c-126">If the amount of memory available on the Front End Server is lower than 1,500 MB when you plan for the expected number of mobility users, you need to add more hardware to support the Mobility Service.</span></span> <span data-ttu-id="25b7c-127">有关详细信息，请参阅[有关业务服务器 2015年的 Skype 的性能监视器移动](monitor-mobility-performance.md)运营文档资料。</span><span class="sxs-lookup"><span data-stu-id="25b7c-127">For more details, see [Monitor mobility for performance in Skype for Business Server 2015](monitor-mobility-performance.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="25b7c-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="25b7c-128">See also</span></span>

#### 

[<span data-ttu-id="25b7c-129">监视业务服务器 2015年的性能在 Skype 的移动性</span><span class="sxs-lookup"><span data-stu-id="25b7c-129">Monitor mobility for performance in Skype for Business Server 2015</span></span>](monitor-mobility-performance.md)

