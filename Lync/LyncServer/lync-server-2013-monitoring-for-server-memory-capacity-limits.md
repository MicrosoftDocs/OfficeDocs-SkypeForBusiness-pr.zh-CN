---
title: Lync Server 2013：监视服务器内存容量限制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring for server memory capacity limits
ms:assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689982(v=OCS.15)
ms:contentKeyID: 48183506
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45600ed9c822851c89b13cb776bbc58464decde0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048095"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a><span data-ttu-id="abf65-102">在 Lync Server 2013 中监视服务器内存容量限制</span><span class="sxs-lookup"><span data-stu-id="abf65-102">Monitoring for server memory capacity limits in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abf65-103">_**上次修改的主题：** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="abf65-103">_**Topic Last Modified:** 2016-12-08_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> <span data-ttu-id="abf65-104">本主题中涉及容量规划的信息仅适用于 Lync 2010 移动客户端和移动服务（Mcx）。</span><span class="sxs-lookup"><span data-stu-id="abf65-104">The information in this topic that refers to Capacity Planning pertains only to Lync 2010 Mobile clients and the Mobility Service (Mcx).</span></span> <span data-ttu-id="abf65-105">Lync 2013 移动客户端使用的统一通信 Web API （UCWA）的容量规划由 Lync Server 2013、规划工具提供。</span><span class="sxs-lookup"><span data-stu-id="abf65-105">Capacity Planning for the Unified Communications Web API (UCWA), used by the Lync 2013 Mobile clients, is provided by the Lync Server 2013, Planning Tool.</span></span>



</div>

<span data-ttu-id="abf65-106">两个移动性能计数器可帮助您确定当前的使用情况，并帮助您规划 Lync Server 2013 移动服务（Mcx）的容量，并监视 UCWA 的内存使用率。</span><span class="sxs-lookup"><span data-stu-id="abf65-106">Two mobility performance counters can help you to determine your current usage and help you plan capacity for the Lync Server 2013 Mobility Service (Mcx), as well as to monitor memory usage for UCWA.</span></span> <span data-ttu-id="abf65-107">对于 UCWA，计数器类别为**LS： WEB – UCWA**。</span><span class="sxs-lookup"><span data-stu-id="abf65-107">For UCWA, the counter category is **LS:WEB – UCWA**.</span></span> <span data-ttu-id="abf65-108">对于移动服务（Mcx），计数器位于类别**LS： WEB-移动通信服务**的下面。</span><span class="sxs-lookup"><span data-stu-id="abf65-108">For the Mobility Service (Mcx), the counters are under the category **LS:WEB - Mobile Communication Service**.</span></span> <span data-ttu-id="abf65-109">要监视的计数器包括：</span><span class="sxs-lookup"><span data-stu-id="abf65-109">The counters to monitor are:</span></span>

  - <span data-ttu-id="abf65-110">**当前处于活动状态订阅的活动会话计数**，这是通过 UCWA 注册的当前终结点或具有活动状态订阅的移动服务（Mcx）的当前活动会话数（始终连接的移动用户数）</span><span class="sxs-lookup"><span data-stu-id="abf65-110">**Currently Active Session Count with Active Presence Subscriptions**, which is the current number of endpoints registered through UCWA or the Mobility Service (Mcx) that have active presence subscriptions (number of always-connected mobile users)</span></span>

  - <span data-ttu-id="abf65-111">**当前处于活动状态的会话计数**，是通过 UCWA 或移动服务注册的当前终结点的数目</span><span class="sxs-lookup"><span data-stu-id="abf65-111">**Currently Active Session Count**, which is the current number of endpoints registered through UCWA or the Mobility Service</span></span>

<span data-ttu-id="abf65-112">如果**当前活动会话计数与活动状态订阅**和**当前活动会话计数**相差较小，则意味着大多数移动设备用户都有一个始终连接的设备，例如 Android 或 Nokia 移动设备（仅适用于 Mcx）。</span><span class="sxs-lookup"><span data-stu-id="abf65-112">If the difference between **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** is small over time, this means that most mobile device users have an always-connected device, such as an Android or Nokia mobile device (for Mcx only).</span></span> <span data-ttu-id="abf65-113">UCWA 始终连接的设备包括运行 Lync 2013 移动客户端的 Apple 和 Android 设备。</span><span class="sxs-lookup"><span data-stu-id="abf65-113">UCWA always-connected devices include Apple and Android devices running Lync 2013 Mobile clients).</span></span> <span data-ttu-id="abf65-114">如果**当前处于活动状态的会话计数**比**活动状态订阅当前活动会话计数**高得多，则表示在 Mcx 下的用户使用的是更多的后台终结点设备（如 Apple IOS 设备或 Windows Phone）。</span><span class="sxs-lookup"><span data-stu-id="abf65-114">If **Currently Active Session Count** is much higher than **Currently Active Session Count with Active Presence Subscriptions**, this indicates that more users are using a background endpoint device, such as an Apple iOS device or Windows Phone under Mcx.</span></span> <span data-ttu-id="abf65-115">（Windows Phone 是唯一将注册为此的 Lync 2013 移动客户端）。</span><span class="sxs-lookup"><span data-stu-id="abf65-115">(Windows Phone is the only Lync 2013 Mobile client that will register as this).</span></span>

<span data-ttu-id="abf65-116">您应根据预期的使用情况、容量规划结果和对移动服务和其他前端服务器计数器的持续监控，对**当前处于活动状态的会话计数**和**当前活动会话计数**性能计数器设置限制。</span><span class="sxs-lookup"><span data-stu-id="abf65-116">You should set a limit on the **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** performance counters based on your expected usage, capacity planning results, and ongoing monitoring of Mobility Service and other Front End Server counters.</span></span> <span data-ttu-id="abf65-117">你设置的限制应允许你评估服务器容量并在超出容量时发出警报。</span><span class="sxs-lookup"><span data-stu-id="abf65-117">The limits you set should enable you to evaluate server capacity and raise alerts when capacity is exceeded.</span></span>

<span data-ttu-id="abf65-118">若要确定适当的限制，需要先确定可在移动服务的前端服务器上使用的内存量。</span><span class="sxs-lookup"><span data-stu-id="abf65-118">To determine the appropriate limits, you need to first determine how much memory is available on the Front End Server for the Mobility Service.</span></span> <span data-ttu-id="abf65-119">根据以下公式监视计数器，以确定何时需要规划额外的容量：</span><span class="sxs-lookup"><span data-stu-id="abf65-119">Monitor the counters to determine when you need to plan for extra capacity, according to the following formula:</span></span>

<span data-ttu-id="abf65-120">Mcx 移动服务（MB）使用的内存总量 = 164 + （400 + 134）/1024 \* **当前处于活动状态订阅的活动会话计数**+ 400/1024 \* （**当前**活动会话计数–**当前活动会话计数与活动状态订阅**）</span><span class="sxs-lookup"><span data-stu-id="abf65-120">Total memory used by the Mcx Mobility Service (MB) = 164 + (400 + 134) / 1024 \* **Currently Active Session Count with Active Presence Subscriptions** + 400 / 1024 \* (**Currently Active Session Count** – **Currently Active Session Count with Active Presence Subscriptions**)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="abf65-121">Microsoft Lync Server 2010 容量计算器是预填充了所有公式的电子表格，以使规划器能够确定服务器（包括 CPU、内存和硬盘驱动器）的要求。</span><span class="sxs-lookup"><span data-stu-id="abf65-121">The Microsoft Lync Server 2010 Capacity Calculator is a spreadsheet that is prepopulated with all of the formulas that enable a planner to determine what the requirements will be for the servers, including CPU, memory, and hard drive.</span></span> <span data-ttu-id="abf65-122">您可以从以下位置下载电子表格和关联文档：<A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A></span><span class="sxs-lookup"><span data-stu-id="abf65-122">You can download the spreadsheet and an associated document at: <A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A></span></span>



</div>

<span data-ttu-id="abf65-123">前端服务器需要足够的可用内存来支持故障转移情况下的移动服务。</span><span class="sxs-lookup"><span data-stu-id="abf65-123">The Front End Server needs enough available memory to support the Mobility Service in failover situations.</span></span> <span data-ttu-id="abf65-124">您可以通过使用**\\内存可用的 mb**计数器，或使用前面提到的公式来规划预期移动服务要使用的内存量来监视前端服务器上当前可用的内存。</span><span class="sxs-lookup"><span data-stu-id="abf65-124">You can monitor the current available memory on the Front End Server by using the **Memory\\Available Mbytes** counter, or by using the equation mentioned earlier, to plan for the amount of memory that you expect the Mobility Service to use.</span></span>

<span data-ttu-id="abf65-125">如果在规划预期的移动用户数时前端服务器上可用的内存量低于 1500 MB，则需要添加更多硬件以支持移动服务。</span><span class="sxs-lookup"><span data-stu-id="abf65-125">If the amount of memory available on the Front End Server is lower than 1,500 MB when you plan for the expected number of mobility users, you need to add more hardware to support the Mobility Service.</span></span> <span data-ttu-id="abf65-126">有关更多详细信息，请参阅操作文档中的[监视 Lync Server 2013 中的性能移动性](lync-server-2013-monitoring-mobility-for-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="abf65-126">For more details, see [Monitoring mobility for performance in Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) in the Operations documentation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="abf65-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="abf65-127">See Also</span></span>


[<span data-ttu-id="abf65-128">在 Lync Server 2013 中监视移动性以提高性能</span><span class="sxs-lookup"><span data-stu-id="abf65-128">Monitoring mobility for performance in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

