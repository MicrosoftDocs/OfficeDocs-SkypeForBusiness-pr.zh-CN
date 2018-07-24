---
title: 监视 Mobility Service 和 UCWA 使用量 Skype 的业务服务器
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 摘要： 管理业务服务器 Mobility Service (Mcx) 和 Skype 中的统一的通信 Web API (UCWA)。
ms.openlocfilehash: 780d8fca068a78ec08312551d03dbdb5327df90e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20975947"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a><span data-ttu-id="c123a-103">监视 Mobility Service 和 UCWA 使用量 Skype 的业务服务器</span><span class="sxs-lookup"><span data-stu-id="c123a-103">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>
 
<span data-ttu-id="c123a-104">**摘要：** 管理业务服务器 Mobility Service (Mcx) 和 Skype 中的统一的通信 Web API (UCWA)。</span><span class="sxs-lookup"><span data-stu-id="c123a-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="c123a-105">MCX 旧的移动客户端支持不再可用的业务服务器 2019 Skype 中。</span><span class="sxs-lookup"><span data-stu-id="c123a-105">MCX support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="c123a-106">您的用户需要升级到当前客户端。</span><span class="sxs-lookup"><span data-stu-id="c123a-106">Your users will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="c123a-107">持续，您应监视的 CPU 和内存 Skype 用于业务服务器 Mobility Service (Mcx) 和统一通信 Web API (UCWA)。</span><span class="sxs-lookup"><span data-stu-id="c123a-107">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="c123a-108">若要监视使用率，您可以使用以下任一方法：</span><span class="sxs-lookup"><span data-stu-id="c123a-108">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="c123a-109">**对于统一通信 Web API (UCWA)：**</span><span class="sxs-lookup"><span data-stu-id="c123a-109">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="c123a-110">在 Internet 信息服务 (IIS) 管理器**LyncUcwa**工作进程。</span><span class="sxs-lookup"><span data-stu-id="c123a-110">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="c123a-111">在“**工作进程**”窗格中，查看“**CPU 百分比**”和“**专用字节 (KB)**”（内存）列。</span><span class="sxs-lookup"><span data-stu-id="c123a-111">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="c123a-112">**CPU** 和**处理器**性能计数器。</span><span class="sxs-lookup"><span data-stu-id="c123a-112">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="c123a-113">对于大多数部署，UCWA CPU 平均使用率应低于 15%。</span><span class="sxs-lookup"><span data-stu-id="c123a-113">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="c123a-114">内存使用情况应范围内[的 Skype 业务服务器中的服务器内存容量限制监视器](server-memory-capacity-limits.md)中所述的限制。</span><span class="sxs-lookup"><span data-stu-id="c123a-114">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="c123a-115">除 CPU 和内存使用率计数器之外，您可以使用以下性能计数器来帮助确定服务器上的请求何时过载：</span><span class="sxs-lookup"><span data-stu-id="c123a-115">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="c123a-116">**LS:WEB-限制和 Authentication\WEB-正在处理的请求总数**，表示挂起的服务器上的 web 请求的次数。</span><span class="sxs-lookup"><span data-stu-id="c123a-116">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="c123a-117">当此计数器达到 10,000 时，后续请求将失败，错误消息为“503 - 服务不可用”。</span><span class="sxs-lookup"><span data-stu-id="c123a-117">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="c123a-118">**Asp.net\requests Queued**（应始终为零）。</span><span class="sxs-lookup"><span data-stu-id="c123a-118">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="c123a-119">如果满足或超出这些值，则应重新审视并重新计算你的容量规划，以确定承载 Web 服务的计算机的正确 CPU 大小、内核数和内存。</span><span class="sxs-lookup"><span data-stu-id="c123a-119">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="c123a-120">**对于 Mobility Service (Mcx)：**</span><span class="sxs-lookup"><span data-stu-id="c123a-120">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="c123a-121">**CSIntMcxAppPool**和**CSExtMcxAppPool**中的工作进程 Internet 信息服务 (IIS) 管理器。</span><span class="sxs-lookup"><span data-stu-id="c123a-121">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="c123a-122">在“**工作进程**”窗格中，查看“**CPU 百分比**”和“**专用字节 (KB)**”（内存）列。</span><span class="sxs-lookup"><span data-stu-id="c123a-122">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="c123a-123">**CPU** 和**处理器**性能计数器。</span><span class="sxs-lookup"><span data-stu-id="c123a-123">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="c123a-124">对于大多数部署，Mobility Service CPU 平均使用率应低于 15%。</span><span class="sxs-lookup"><span data-stu-id="c123a-124">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="c123a-125">内存使用情况应范围内[的 Skype 业务服务器中的服务器内存容量限制监视器](server-memory-capacity-limits.md)中所述的限制。</span><span class="sxs-lookup"><span data-stu-id="c123a-125">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="c123a-126">除 CPU 和内存使用率计数器之外，您可以使用以下 ASP.NET 性能计数器来帮助确定服务器上的请求何时过载：</span><span class="sxs-lookup"><span data-stu-id="c123a-126">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="c123a-127">**ASP.NET v2.0.50727\Requests 当前**，后者指示挂起的服务器上的 web 请求的次数。</span><span class="sxs-lookup"><span data-stu-id="c123a-127">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="c123a-128">当此计数器达到 5,000 时，后续请求将失败，错误消息为“503 - 服务不可用”。</span><span class="sxs-lookup"><span data-stu-id="c123a-128">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="c123a-129">**Asp.net\requests Queued**（应始终为零）。</span><span class="sxs-lookup"><span data-stu-id="c123a-129">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="c123a-130">如果满足或超出这些值，则应重新审视并重新计算你的容量规划，以确定承载 Web 服务的计算机的正确 CPU 大小、内核数和内存。</span><span class="sxs-lookup"><span data-stu-id="c123a-130">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 

> [!NOTE]
> <span data-ttu-id="c123a-131">MCX 旧的移动客户端支持不再可用的业务服务器 2019 Skype 中。</span><span class="sxs-lookup"><span data-stu-id="c123a-131">MCX support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="c123a-132">您的用户需要升级到当前客户端。</span><span class="sxs-lookup"><span data-stu-id="c123a-132">Your users will need to upgrade to a current client.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c123a-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c123a-133">See also</span></span>

[<span data-ttu-id="c123a-134">监控服务器内存容量限制 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="c123a-134">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)