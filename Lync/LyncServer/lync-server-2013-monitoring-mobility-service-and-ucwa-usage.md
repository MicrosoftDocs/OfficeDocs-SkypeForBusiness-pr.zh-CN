---
title: Lync Server 2013：监视移动服务和 UCWA 使用情况
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring Mobility Service and UCWA usage
ms:assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690025(v=OCS.15)
ms:contentKeyID: 48184683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4968c1a3b3dc30bdab2a3c19fd8e930da6122cb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756806"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a><span data-ttu-id="6101e-102">在 Lync Server 2013 中监视移动服务和 UCWA 使用情况</span><span class="sxs-lookup"><span data-stu-id="6101e-102">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6101e-103">_**主题上次修改时间：** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="6101e-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="6101e-104">在持续的基础上，你应该监视 Lync Server 移动服务（Mcx）和统一通信 Web API （UCWA）使用的 CPU 和内存。</span><span class="sxs-lookup"><span data-stu-id="6101e-104">On an ongoing basis, you should monitor the CPU and memory that is used by the Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="6101e-105">若要监视使用率，您可以使用以下任一方法：</span><span class="sxs-lookup"><span data-stu-id="6101e-105">To monitor usage, you can use the following:</span></span>

<span data-ttu-id="6101e-106">**对于统一通信 Web API (UCWA)：**</span><span class="sxs-lookup"><span data-stu-id="6101e-106">**For Unified Communications Web API (UCWA):**</span></span>

  - <span data-ttu-id="6101e-107">Internet Information Services （IIS）管理器中的**LyncUcwa**工作进程。</span><span class="sxs-lookup"><span data-stu-id="6101e-107">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="6101e-108">在“**工作进程**”窗格中，查看“**CPU 百分比**”和“**专用字节 (KB)**”（内存）列。</span><span class="sxs-lookup"><span data-stu-id="6101e-108">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="6101e-109">**CPU** 和**处理器**性能计数器。</span><span class="sxs-lookup"><span data-stu-id="6101e-109">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="6101e-110">对于大多数部署，UCWA CPU 平均使用率应低于 15%。</span><span class="sxs-lookup"><span data-stu-id="6101e-110">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="6101e-111">内存使用率应在 "在[Lync server 2013 中监视服务器内存容量限制](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)" 中介绍的限制范围内。</span><span class="sxs-lookup"><span data-stu-id="6101e-111">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="6101e-112">除 CPU 和内存使用率计数器之外，您可以使用以下性能计数器来帮助确定服务器上的请求何时过载：</span><span class="sxs-lookup"><span data-stu-id="6101e-112">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="6101e-113">**LS： web-限制和身份\\验证 web –处理中的总请求**数，指示服务器上的挂起 WEB 请求数。</span><span class="sxs-lookup"><span data-stu-id="6101e-113">**LS:WEB – Throttling and Authentication\\WEB – Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="6101e-114">当此计数器达到 10,000 时，后续请求将失败，错误消息为“503 - 服务不可用”。</span><span class="sxs-lookup"><span data-stu-id="6101e-114">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="6101e-115">**ASP.NET\\请求已排队**（应始终为零）。</span><span class="sxs-lookup"><span data-stu-id="6101e-115">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6101e-116">如果您达到或超过这些值，则应该重新访问和重新计算您的容量规划，以便对托管 Web 服务的计算机进行正确的 CPU、内核数和内存的调整。</span><span class="sxs-lookup"><span data-stu-id="6101e-116">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the Web services.</span></span>



</div>

<span data-ttu-id="6101e-117">**对于 Mobility Service (Mcx)：**</span><span class="sxs-lookup"><span data-stu-id="6101e-117">**For the Mobility Service (Mcx):**</span></span>

  - <span data-ttu-id="6101e-118">Internet Information Services （IIS）管理器中的**CSIntMcxAppPool**和**CSExtMcxAppPool**工作进程。</span><span class="sxs-lookup"><span data-stu-id="6101e-118">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="6101e-119">在“**工作进程**”窗格中，查看“**CPU 百分比**”和“**专用字节 (KB)**”（内存）列。</span><span class="sxs-lookup"><span data-stu-id="6101e-119">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="6101e-120">**CPU** 和**处理器**性能计数器。</span><span class="sxs-lookup"><span data-stu-id="6101e-120">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="6101e-121">对于大多数部署，Mobility Service CPU 平均使用率应低于 15%。</span><span class="sxs-lookup"><span data-stu-id="6101e-121">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="6101e-122">内存使用率应在 "在[Lync server 2013 中监视服务器内存容量限制](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)" 中介绍的限制范围内。</span><span class="sxs-lookup"><span data-stu-id="6101e-122">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="6101e-123">除 CPU 和内存使用率计数器之外，您可以使用以下 ASP.NET 性能计数器来帮助确定服务器上的请求何时过载：</span><span class="sxs-lookup"><span data-stu-id="6101e-123">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="6101e-124">**ASP.NET v 2.0.50727\\请求 "当前**"，这表示服务器上已挂起的 web 请求数。</span><span class="sxs-lookup"><span data-stu-id="6101e-124">**ASP.NET v2.0.50727\\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="6101e-125">当此计数器达到 5,000 时，后续请求将失败，错误消息为“503 - 服务不可用”。</span><span class="sxs-lookup"><span data-stu-id="6101e-125">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="6101e-126">**ASP.NET\\请求已排队**（应始终为零）。</span><span class="sxs-lookup"><span data-stu-id="6101e-126">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6101e-127">如果您达到或超过这些值，则应该重新访问和重新计算您的容量规划，以便正确调整托管 Web 服务的计算机的 CPU、内核数和内存的大小。</span><span class="sxs-lookup"><span data-stu-id="6101e-127">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the Web services.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6101e-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6101e-128">See Also</span></span>


[<span data-ttu-id="6101e-129">在 Lync Server 2013 中监视服务器内存容量限制</span><span class="sxs-lookup"><span data-stu-id="6101e-129">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

