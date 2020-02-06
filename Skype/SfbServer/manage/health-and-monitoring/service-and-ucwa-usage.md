---
title: 在 Skype for Business 服务器中监视移动服务和 UCWA 使用情况
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 摘要：在 Skype for Business 服务器中管理移动服务（Mcx）和统一通信 Web API （UCWA）。
ms.openlocfilehash: 7c41e92b144e1bd4d198c5e9d9f90913ce41400e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817681"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a><span data-ttu-id="a969d-103">在 Skype for Business 服务器中监视移动服务和 UCWA 使用情况</span><span class="sxs-lookup"><span data-stu-id="a969d-103">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>
 
<span data-ttu-id="a969d-104">**摘要：** 在 Skype for Business 服务器中管理移动服务（Mcx）和统一通信 Web API （UCWA）。</span><span class="sxs-lookup"><span data-stu-id="a969d-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="a969d-105">在 Skype for Business Server 2019 中，MCX （移动服务）对旧式移动客户端的支持不再可用。</span><span class="sxs-lookup"><span data-stu-id="a969d-105">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="a969d-106">所有当前 Skype for business 移动客户端都已使用统一通信 Web API （UCWA）来支持即时消息（IM）、状态和联系人。</span><span class="sxs-lookup"><span data-stu-id="a969d-106">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="a969d-107">具有使用 MCX 的旧客户端的用户将需要升级到当前客户端。</span><span class="sxs-lookup"><span data-stu-id="a969d-107">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="a969d-108">在持续的基础上，你应该监视 Skype for Business Server 移动服务（Mcx）和统一通信 Web API （UCWA）使用的 CPU 和内存。</span><span class="sxs-lookup"><span data-stu-id="a969d-108">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="a969d-109">若要监视使用率，您可以使用以下任一方法：</span><span class="sxs-lookup"><span data-stu-id="a969d-109">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="a969d-110">**对于统一通信 Web API (UCWA)：**</span><span class="sxs-lookup"><span data-stu-id="a969d-110">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="a969d-111">Internet Information Services （IIS）管理器中的**LyncUcwa**工作进程。</span><span class="sxs-lookup"><span data-stu-id="a969d-111">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="a969d-112">在“**工作进程**”窗格中，查看“**CPU 百分比**”和“**专用字节 (KB)**”（内存）列。</span><span class="sxs-lookup"><span data-stu-id="a969d-112">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="a969d-113">**CPU** 和**处理器**性能计数器。</span><span class="sxs-lookup"><span data-stu-id="a969d-113">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="a969d-114">对于大多数部署，UCWA CPU 平均使用率应低于 15%。</span><span class="sxs-lookup"><span data-stu-id="a969d-114">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="a969d-115">内存使用率应在[监视器的 "Skype for business" 服务器的 "服务器内存容量限制](server-memory-capacity-limits.md)" 中介绍的限制范围内。</span><span class="sxs-lookup"><span data-stu-id="a969d-115">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="a969d-116">除 CPU 和内存使用率计数器之外，您可以使用以下性能计数器来帮助确定服务器上的请求何时过载：</span><span class="sxs-lookup"><span data-stu-id="a969d-116">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="a969d-117">**LS： WEB 阻止和 Authentication\WEB-正在处理的请求总数**，指示服务器上的挂起 WEB 请求的数量。</span><span class="sxs-lookup"><span data-stu-id="a969d-117">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="a969d-118">当此计数器达到 10,000 时，后续请求将失败，错误消息为“503 - 服务不可用”。</span><span class="sxs-lookup"><span data-stu-id="a969d-118">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="a969d-119">**ASP.NET\Requests Queued**（应始终为零）。</span><span class="sxs-lookup"><span data-stu-id="a969d-119">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="a969d-120">如果满足或超出这些值，则应重新审视并重新计算你的容量规划，以确定承载 Web 服务的计算机的正确 CPU 大小、内核数和内存。</span><span class="sxs-lookup"><span data-stu-id="a969d-120">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="a969d-121">**对于 Mobility Service (Mcx)：**</span><span class="sxs-lookup"><span data-stu-id="a969d-121">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="a969d-122">Internet Information Services （IIS）管理器中的**CSIntMcxAppPool**和**CSExtMcxAppPool**工作进程。</span><span class="sxs-lookup"><span data-stu-id="a969d-122">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="a969d-123">在“**工作进程**”窗格中，查看“**CPU 百分比**”和“**专用字节 (KB)**”（内存）列。</span><span class="sxs-lookup"><span data-stu-id="a969d-123">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="a969d-124">**CPU** 和**处理器**性能计数器。</span><span class="sxs-lookup"><span data-stu-id="a969d-124">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="a969d-125">对于大多数部署，Mobility Service CPU 平均使用率应低于 15%。</span><span class="sxs-lookup"><span data-stu-id="a969d-125">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="a969d-126">内存使用率应在[监视器的 "Skype for business" 服务器的 "服务器内存容量限制](server-memory-capacity-limits.md)" 中介绍的限制范围内。</span><span class="sxs-lookup"><span data-stu-id="a969d-126">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="a969d-127">除 CPU 和内存使用率计数器之外，您可以使用以下 ASP.NET 性能计数器来帮助确定服务器上的请求何时过载：</span><span class="sxs-lookup"><span data-stu-id="a969d-127">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="a969d-128">**ASP.NET v2.0.50727\Requests Current**，指示服务器上挂起的 Web 请求的数目。</span><span class="sxs-lookup"><span data-stu-id="a969d-128">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="a969d-129">当此计数器达到 5,000 时，后续请求将失败，错误消息为“503 - 服务不可用”。</span><span class="sxs-lookup"><span data-stu-id="a969d-129">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="a969d-130">**ASP.NET\Requests Queued**（应始终为零）。</span><span class="sxs-lookup"><span data-stu-id="a969d-130">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="a969d-131">如果满足或超出这些值，则应重新审视并重新计算你的容量规划，以确定承载 Web 服务的计算机的正确 CPU 大小、内核数和内存。</span><span class="sxs-lookup"><span data-stu-id="a969d-131">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 

> [!NOTE]
> <span data-ttu-id="a969d-132">在 Skype for Business Server 2019 中，MCX （移动服务）对旧式移动客户端的支持不再可用。</span><span class="sxs-lookup"><span data-stu-id="a969d-132">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="a969d-133">所有当前 Skype for business 移动客户端都已使用统一通信 Web API （UCWA）来支持即时消息（IM）、状态和联系人。</span><span class="sxs-lookup"><span data-stu-id="a969d-133">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="a969d-134">具有使用 MCX 的旧客户端的用户将需要升级到当前客户端。</span><span class="sxs-lookup"><span data-stu-id="a969d-134">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a969d-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a969d-135">See also</span></span>

[<span data-ttu-id="a969d-136">监视 Skype for Business 服务器中的服务器内存容量限制</span><span class="sxs-lookup"><span data-stu-id="a969d-136">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
