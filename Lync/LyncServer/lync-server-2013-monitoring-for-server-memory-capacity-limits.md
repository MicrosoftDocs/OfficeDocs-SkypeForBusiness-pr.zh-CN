---
title: 'Lync Server 2013: 监视服务器内存容量限制'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring for server memory capacity limits
ms:assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689982(v=OCS.15)
ms:contentKeyID: 48183506
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68728c85b14231644b445569857896f34abe535f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a><span data-ttu-id="ba404-102">在 Lync Server 2013 中监视服务器内存容量限制</span><span class="sxs-lookup"><span data-stu-id="ba404-102">Monitoring for server memory capacity limits in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba404-103">_**主题上次修改时间:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="ba404-103">_**Topic Last Modified:** 2016-12-08_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> <span data-ttu-id="ba404-104">本主题中涉及容量规划的信息仅适用于 Lync 2010 移动客户端和移动服务 (Mcx)。</span><span class="sxs-lookup"><span data-stu-id="ba404-104">The information in this topic that refers to Capacity Planning pertains only to Lync 2010 Mobile clients and the Mobility Service (Mcx).</span></span> <span data-ttu-id="ba404-105">Lync 2013 移动客户端使用的统一通信 Web API (UCWA) 的容量规划由 Lync Server 2013、计划工具提供。</span><span class="sxs-lookup"><span data-stu-id="ba404-105">Capacity Planning for the Unified Communications Web API (UCWA), used by the Lync 2013 Mobile clients, is provided by the Lync Server 2013, Planning Tool.</span></span>



</div>

<span data-ttu-id="ba404-106">两个移动性能计数器可帮助你确定当前使用情况并帮助你规划 Lync Server 2013 移动服务 (Mcx) 的容量, 以及监视 UCWA 的内存使用情况。</span><span class="sxs-lookup"><span data-stu-id="ba404-106">Two mobility performance counters can help you to determine your current usage and help you plan capacity for the Lync Server 2013 Mobility Service (Mcx), as well as to monitor memory usage for UCWA.</span></span> <span data-ttu-id="ba404-107">对于 UCWA，计数器类别为“**LS:WEB – UCWA**”。</span><span class="sxs-lookup"><span data-stu-id="ba404-107">For UCWA, the counter category is **LS:WEB – UCWA**.</span></span> <span data-ttu-id="ba404-108">对于 Mobility Service (Mcx)，计数器类别为“**LS:WEB - 移动通信服务**”。</span><span class="sxs-lookup"><span data-stu-id="ba404-108">For the Mobility Service (Mcx), the counters are under the category **LS:WEB - Mobile Communication Service**.</span></span> <span data-ttu-id="ba404-109">要监控的计数器包括：</span><span class="sxs-lookup"><span data-stu-id="ba404-109">The counters to monitor are:</span></span>

  - <span data-ttu-id="ba404-110">**Currently Active Session Count with Active Presence Subscriptions**，它是当前通过 UCWA 或 Mobility Service (Mcx) 注册的终结点的数目，这些终结点具有活动状态订阅（始终连接的移动用户的数目）</span><span class="sxs-lookup"><span data-stu-id="ba404-110">**Currently Active Session Count with Active Presence Subscriptions**, which is the current number of endpoints registered through UCWA or the Mobility Service (Mcx) that have active presence subscriptions (number of always-connected mobile users)</span></span>

  - <span data-ttu-id="ba404-111">**Currently Active Session Count**，它是当前通过 UCWA 或 Mobility Service 注册的终结点的数目</span><span class="sxs-lookup"><span data-stu-id="ba404-111">**Currently Active Session Count**, which is the current number of endpoints registered through UCWA or the Mobility Service</span></span>

<span data-ttu-id="ba404-112">如果**当前活动的会话计数与活动状态订阅**和**当前活动会话计数**之间的差异在一段时间内较小, 这意味着大多数移动设备用户拥有一个始终连接的设备, 例如 Android 或Nokia 移动设备 (仅限 Mcx)。</span><span class="sxs-lookup"><span data-stu-id="ba404-112">If the difference between **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** is small over time, this means that most mobile device users have an always-connected device, such as an Android or Nokia mobile device (for Mcx only).</span></span> <span data-ttu-id="ba404-113">UCWA 始终连接的设备包括运行 Lync 2013 移动客户端的 Apple 和 Android 设备。</span><span class="sxs-lookup"><span data-stu-id="ba404-113">UCWA always-connected devices include Apple and Android devices running Lync 2013 Mobile clients).</span></span> <span data-ttu-id="ba404-114">如果**当前处于活动状态的会话计数**比**当前处于活动状态订阅的当前活动会话计数**高得多, 这表示使用后台终结点设备 (如 Apple IOS 设备或 Windows Phone) 的用户Mcx.</span><span class="sxs-lookup"><span data-stu-id="ba404-114">If **Currently Active Session Count** is much higher than **Currently Active Session Count with Active Presence Subscriptions**, this indicates that more users are using a background endpoint device, such as an Apple iOS device or Windows Phone under Mcx.</span></span> <span data-ttu-id="ba404-115">(Windows Phone 是唯一将注册为此的 Lync 2013 移动客户端)。</span><span class="sxs-lookup"><span data-stu-id="ba404-115">(Windows Phone is the only Lync 2013 Mobile client that will register as this).</span></span>

<span data-ttu-id="ba404-116">你应该针对**当前处于活动状态的订阅**和**当前活动会话计数**性能计数器 (基于你预期的使用情况、容量计划结果和持续监视) 设置当前活动会话计数的限制移动服务和其他前端服务器计数器。</span><span class="sxs-lookup"><span data-stu-id="ba404-116">You should set a limit on the **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** performance counters based on your expected usage, capacity planning results, and ongoing monitoring of Mobility Service and other Front End Server counters.</span></span> <span data-ttu-id="ba404-117">您设置的限制应允许您计算服务器容量并在超出容量时发出警报。</span><span class="sxs-lookup"><span data-stu-id="ba404-117">The limits you set should enable you to evaluate server capacity and raise alerts when capacity is exceeded.</span></span>

<span data-ttu-id="ba404-118">若要确定相应的限制, 需要首先确定移动服务前端服务器上的可用内存量。</span><span class="sxs-lookup"><span data-stu-id="ba404-118">To determine the appropriate limits, you need to first determine how much memory is available on the Front End Server for the Mobility Service.</span></span> <span data-ttu-id="ba404-119">请监控计数器以根据以下公式确定您需要何时规划额外的容量：</span><span class="sxs-lookup"><span data-stu-id="ba404-119">Monitor the counters to determine when you need to plan for extra capacity, according to the following formula:</span></span>

<span data-ttu-id="ba404-120">Mcx 移动服务 (MB) 使用的总内存 = 164 + (400 + 134)/1024 \* **当前处于活动状态订阅的活动会话计数**+ 400/1024 \* (**当前处于活动**状态的会话计数-当前处于活动状态的会话计数**有活动的状态订阅**)</span><span class="sxs-lookup"><span data-stu-id="ba404-120">Total memory used by the Mcx Mobility Service (MB) = 164 + (400 + 134) / 1024 \* **Currently Active Session Count with Active Presence Subscriptions** + 400 / 1024 \* (**Currently Active Session Count** – **Currently Active Session Count with Active Presence Subscriptions**)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ba404-121">Microsoft Lync Server 2010 容量计算器是预填充了所有公式的电子表格, 它使 planner 能够确定服务器 (包括 CPU、内存和硬盘) 的要求。</span><span class="sxs-lookup"><span data-stu-id="ba404-121">The Microsoft Lync Server 2010 Capacity Calculator is a spreadsheet that is prepopulated with all of the formulas that enable a planner to determine what the requirements will be for the servers, including CPU, memory, and hard drive.</span></span> <span data-ttu-id="ba404-122">您可以在以下位置下载电子表格和相关文档:<A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A></span><span class="sxs-lookup"><span data-stu-id="ba404-122">You can download the spreadsheet and an associated document at: <A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A></span></span>



</div>

<span data-ttu-id="ba404-123">前端服务器需要足够的可用内存才能在故障转移情况下支持移动服务。</span><span class="sxs-lookup"><span data-stu-id="ba404-123">The Front End Server needs enough available memory to support the Mobility Service in failover situations.</span></span> <span data-ttu-id="ba404-124">你可以使用**内存\\可用**的 "mb" 计数器来监视前端服务器上的当前可用内存, 或使用前面提到的公式来规划你希望移动服务使用的内存量。</span><span class="sxs-lookup"><span data-stu-id="ba404-124">You can monitor the current available memory on the Front End Server by using the **Memory\\Available Mbytes** counter, or by using the equation mentioned earlier, to plan for the amount of memory that you expect the Mobility Service to use.</span></span>

<span data-ttu-id="ba404-125">如果在针对预期的移动用户数进行规划时前端服务器上可用的内存量小于 1500 MB, 则需要添加更多硬件来支持移动服务。</span><span class="sxs-lookup"><span data-stu-id="ba404-125">If the amount of memory available on the Front End Server is lower than 1,500 MB when you plan for the expected number of mobility users, you need to add more hardware to support the Mobility Service.</span></span> <span data-ttu-id="ba404-126">有关更多详细信息, 请参阅在操作文档中[监视 Lync Server 2013 中的性能移动性](lync-server-2013-monitoring-mobility-for-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="ba404-126">For more details, see [Monitoring mobility for performance in Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) in the Operations documentation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="ba404-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba404-127">See Also</span></span>


[<span data-ttu-id="ba404-128">在 Lync Server 2013 中监视移动性能</span><span class="sxs-lookup"><span data-stu-id="ba404-128">Monitoring mobility for performance in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

