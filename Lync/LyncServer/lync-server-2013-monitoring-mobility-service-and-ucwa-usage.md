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
ms.openlocfilehash: 2248bbd2eea4bb9204a98b5c5805ef196cbf2015
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531789"
---
# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a><span data-ttu-id="b78fe-102">在 Lync Server 2013 中监视移动服务和 UCWA 使用情况</span><span class="sxs-lookup"><span data-stu-id="b78fe-102">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b78fe-103">_**上次修改的主题：** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="b78fe-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="b78fe-104">在持续的基础上，应监视 Lync Server 移动服务 (Mcx) 和统一通信 Web API (UCWA) 所使用的 CPU 和内存。</span><span class="sxs-lookup"><span data-stu-id="b78fe-104">On an ongoing basis, you should monitor the CPU and memory that is used by the Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="b78fe-105">若要监视使用情况，可以使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="b78fe-105">To monitor usage, you can use the following:</span></span>

<span data-ttu-id="b78fe-106">**对于统一通信 Web API (UCWA) ：**</span><span class="sxs-lookup"><span data-stu-id="b78fe-106">**For Unified Communications Web API (UCWA):**</span></span>

  - <span data-ttu-id="b78fe-107">Internet 信息服务 (IIS) 管理器中的 **LyncUcwa** 工作进程。</span><span class="sxs-lookup"><span data-stu-id="b78fe-107">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="b78fe-108">在“工作进程”\*\*\*\* 窗格中，查看“CPU 百分比”\*\*\*\* 和“专用字节(KB)”\*\*\*\*（内存）列。</span><span class="sxs-lookup"><span data-stu-id="b78fe-108">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="b78fe-109">**CPU** 和 **Processor** 性能计数器。</span><span class="sxs-lookup"><span data-stu-id="b78fe-109">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="b78fe-110">对于大多数部署，UCWA CPU 使用率平均应低于15%。</span><span class="sxs-lookup"><span data-stu-id="b78fe-110">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="b78fe-111">内存使用率应处于在 [Lync server 2013 中监视服务器内存容量限制](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)中所描述的限制范围内。</span><span class="sxs-lookup"><span data-stu-id="b78fe-111">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="b78fe-112">除了 CPU 和内存使用率计数器之外，您还可以使用以下性能计数器来帮助确定服务器何时因请求而过载：</span><span class="sxs-lookup"><span data-stu-id="b78fe-112">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="b78fe-113">**LS： WEB –限制和身份验证 \\WEB –处理中的总请求**数，指示服务器上的挂起的 web 请求数。</span><span class="sxs-lookup"><span data-stu-id="b78fe-113">**LS:WEB – Throttling and Authentication\\WEB – Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="b78fe-114">当此计数器达到10000时，后续请求将失败，错误消息为 "503-服务不可用"。</span><span class="sxs-lookup"><span data-stu-id="b78fe-114">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="b78fe-115">**ASP.NET \\排队** (的请求应始终为零) 。</span><span class="sxs-lookup"><span data-stu-id="b78fe-115">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b78fe-116">如果达到或超过这些值，则应重新访问并重新计算容量规划，以确保承载 Web 服务的计算机的 CPU、内核数和内存的正确大小。</span><span class="sxs-lookup"><span data-stu-id="b78fe-116">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the Web services.</span></span>



</div>

<span data-ttu-id="b78fe-117">**对于移动服务 (Mcx) ：**</span><span class="sxs-lookup"><span data-stu-id="b78fe-117">**For the Mobility Service (Mcx):**</span></span>

  - <span data-ttu-id="b78fe-118">Internet 信息服务中的 **CSIntMcxAppPool** 和 **CSExtMcxAppPool** 工作进程 (IIS) 管理器。</span><span class="sxs-lookup"><span data-stu-id="b78fe-118">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="b78fe-119">在“工作进程”\*\*\*\* 窗格中，查看“CPU 百分比”\*\*\*\* 和“专用字节(KB)”\*\*\*\*（内存）列。</span><span class="sxs-lookup"><span data-stu-id="b78fe-119">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="b78fe-120">**CPU** 和 **Processor** 性能计数器。</span><span class="sxs-lookup"><span data-stu-id="b78fe-120">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="b78fe-121">对于大多数部署，移动服务 CPU 使用率平均应低于15%。</span><span class="sxs-lookup"><span data-stu-id="b78fe-121">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="b78fe-122">内存使用率应处于在 [Lync server 2013 中监视服务器内存容量限制](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)中所描述的限制范围内。</span><span class="sxs-lookup"><span data-stu-id="b78fe-122">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="b78fe-123">除 CPU 和内存使用率计数器之外，您可以使用以下 ASP.NET 性能计数器来帮助确定服务器上的请求何时过载：</span><span class="sxs-lookup"><span data-stu-id="b78fe-123">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="b78fe-124">**ASP.NET v 2.0.50727 \\请求 "Current**"，指示服务器上的挂起的 web 请求数。</span><span class="sxs-lookup"><span data-stu-id="b78fe-124">**ASP.NET v2.0.50727\\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="b78fe-125">当此计数器达到5000时，后续请求将失败，并出现错误消息 "503-服务不可用"。</span><span class="sxs-lookup"><span data-stu-id="b78fe-125">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="b78fe-126">**ASP.NET \\排队** (的请求应始终为零) 。</span><span class="sxs-lookup"><span data-stu-id="b78fe-126">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b78fe-127">如果达到或超过这些值，则应重新访问并重新计算容量规划，以确保承载 Web 服务的计算机的 CPU、核心数量和内存的正确大小。</span><span class="sxs-lookup"><span data-stu-id="b78fe-127">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the Web services.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b78fe-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b78fe-128">See Also</span></span>


[<span data-ttu-id="b78fe-129">在 Lync Server 2013 中监视服务器内存容量限制</span><span class="sxs-lookup"><span data-stu-id="b78fe-129">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

