---
title: 在 Skype for Business Server 2015 中监视 Mobility Service 和 UCWA 的使用情况
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 摘要： 管理 (Mcx) 的移动服务和统一的通信 Web API (UCWA) 在 Skype 业务服务器 2015年。
ms.openlocfilehash: e71d18fe90eb9a7f2fd7b6563e6d6930f2473e74
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server-2015"></a><span data-ttu-id="fe354-103">在 Skype for Business Server 2015 中监视 Mobility Service 和 UCWA 的使用情况</span><span class="sxs-lookup"><span data-stu-id="fe354-103">Monitor Mobility Service and UCWA usage in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="fe354-104">**摘要：**管理 (Mcx) 的移动服务和统一的通信 Web API (UCWA) 在 Skype 业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="fe354-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="fe354-105">不断地，应该监视 CPU 和内存，可通过 Skype 业务服务器移动服务 (Mcx) 和统一通信 Web API (UCWA)。</span><span class="sxs-lookup"><span data-stu-id="fe354-105">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="fe354-106">若要监视使用率，您可以使用以下任一方法：</span><span class="sxs-lookup"><span data-stu-id="fe354-106">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="fe354-107">**对于统一通信 Web API (UCWA)：**</span><span class="sxs-lookup"><span data-stu-id="fe354-107">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="fe354-108">**LyncUcwa**工作在 Internet Information Services (IIS) 管理器进程。</span><span class="sxs-lookup"><span data-stu-id="fe354-108">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="fe354-109">在“**工作进程**”窗格中，查看“**CPU 百分比**”和“**专用字节 (KB)**”（内存）列。</span><span class="sxs-lookup"><span data-stu-id="fe354-109">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="fe354-110">**CPU** 和**处理器**性能计数器。</span><span class="sxs-lookup"><span data-stu-id="fe354-110">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="fe354-111">对于大多数部署，UCWA CPU 平均使用率应低于 15%。</span><span class="sxs-lookup"><span data-stu-id="fe354-111">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="fe354-112">内存使用情况应属于所述[显示器中业务服务器 2015年的 Skype 的服务器内存容量限制](server-memory-capacity-limits.md)的范围之内。</span><span class="sxs-lookup"><span data-stu-id="fe354-112">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server 2015](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="fe354-113">除 CPU 和内存使用率计数器之外，您可以使用以下性能计数器来帮助确定服务器上的请求何时过载：</span><span class="sxs-lookup"><span data-stu-id="fe354-113">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="fe354-114">**LS:WEB-调节和 Authentication\WEB-正在处理的请求总数**，它指示挂起的 web 服务器上的请求的次数。</span><span class="sxs-lookup"><span data-stu-id="fe354-114">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="fe354-115">当此计数器达到 10,000 时，后续请求将失败，错误消息为“503 - 服务不可用”。</span><span class="sxs-lookup"><span data-stu-id="fe354-115">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="fe354-116">**ASP.NET\Requests 排队**（应始终为零）。</span><span class="sxs-lookup"><span data-stu-id="fe354-116">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="fe354-117">如果满足或超出这些值，则应重新审视并重新计算你的容量规划，以确定承载 Web 服务的计算机的正确 CPU 大小、内核数和内存。</span><span class="sxs-lookup"><span data-stu-id="fe354-117">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="fe354-118">**对于 Mobility Service (Mcx)：**</span><span class="sxs-lookup"><span data-stu-id="fe354-118">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="fe354-119">**CSIntMcxAppPool**和**CSExtMcxAppPool**中的工作进程 Internet Information Services (IIS) 管理器。</span><span class="sxs-lookup"><span data-stu-id="fe354-119">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="fe354-120">在“**工作进程**”窗格中，查看“**CPU 百分比**”和“**专用字节 (KB)**”（内存）列。</span><span class="sxs-lookup"><span data-stu-id="fe354-120">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="fe354-121">**CPU** 和**处理器**性能计数器。</span><span class="sxs-lookup"><span data-stu-id="fe354-121">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="fe354-122">对于大多数部署，Mobility Service CPU 平均使用率应低于 15%。</span><span class="sxs-lookup"><span data-stu-id="fe354-122">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="fe354-123">内存使用情况应属于所述[显示器中业务服务器 2015年的 Skype 的服务器内存容量限制](server-memory-capacity-limits.md)的范围之内。</span><span class="sxs-lookup"><span data-stu-id="fe354-123">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server 2015](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="fe354-124">除 CPU 和内存使用率计数器之外，您可以使用以下 ASP.NET 性能计数器来帮助确定服务器上的请求何时过载：</span><span class="sxs-lookup"><span data-stu-id="fe354-124">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="fe354-125">**当前的 ASP.NET v2.0.50727\Requests**，它指示挂起的 web 服务器上的请求的次数。</span><span class="sxs-lookup"><span data-stu-id="fe354-125">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="fe354-126">当此计数器达到 5,000 时，后续请求将失败，错误消息为“503 - 服务不可用”。</span><span class="sxs-lookup"><span data-stu-id="fe354-126">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="fe354-127">**ASP.NET\Requests 排队**（应始终为零）。</span><span class="sxs-lookup"><span data-stu-id="fe354-127">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="fe354-128">如果满足或超出这些值，则应重新审视并重新计算你的容量规划，以确定承载 Web 服务的计算机的正确 CPU 大小、内核数和内存。</span><span class="sxs-lookup"><span data-stu-id="fe354-128">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="fe354-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe354-129">See also</span></span>

#### 

[<span data-ttu-id="fe354-130">服务器内存容量限制在商业服务器 2015年的 Skype 的监视器</span><span class="sxs-lookup"><span data-stu-id="fe354-130">Monitor for server memory capacity limits in Skype for Business Server 2015</span></span>](server-memory-capacity-limits.md)

