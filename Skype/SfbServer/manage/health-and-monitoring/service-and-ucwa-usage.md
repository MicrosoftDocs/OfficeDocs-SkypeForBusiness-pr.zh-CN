---
title: 监视 Skype for Business Server 中的 Mobility Service 和 UCWA 使用情况
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
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 摘要：在 Skype for Business Server 中管理 Mobility Service (Mcx) 和统一通信 Web API (UCWA) 。
ms.openlocfilehash: 76bcf8727d3abbb417595f033ce9a59ec00a39ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814242"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a><span data-ttu-id="cc337-103">监视 Skype for Business Server 中的 Mobility Service 和 UCWA 使用情况</span><span class="sxs-lookup"><span data-stu-id="cc337-103">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>
 
<span data-ttu-id="cc337-104">**摘要：** 在 Skype for Business Server 中管理 Mobility Service (Mcx) 和统一通信 Web API (UCWA) 。</span><span class="sxs-lookup"><span data-stu-id="cc337-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="cc337-105">SKYPE (Server 2019 中不再提供对) 移动客户端的 MCX 移动服务支持。</span><span class="sxs-lookup"><span data-stu-id="cc337-105">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="cc337-106">所有当前的 Skype for Business 移动客户端已使用统一通信 Web API (UCWA) 来支持即时消息 (IM) 、状态和联系人。</span><span class="sxs-lookup"><span data-stu-id="cc337-106">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="cc337-107">使用 MCX 的旧客户端的用户将需要升级到当前客户端。</span><span class="sxs-lookup"><span data-stu-id="cc337-107">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="cc337-108">您应持续监视 Skype for Business Server Mobility Service (Mcx) 和 UCWA (统一通信 Web API) 使用的 CPU 和内存。</span><span class="sxs-lookup"><span data-stu-id="cc337-108">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="cc337-109">若要监视使用情况，可以使用以下内容：</span><span class="sxs-lookup"><span data-stu-id="cc337-109">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="cc337-110">**对于统一通信 Web API (UCWA) ：**</span><span class="sxs-lookup"><span data-stu-id="cc337-110">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="cc337-111">IIS Internet Information Services (管理器中的 **LyncUcwa**) 进程。</span><span class="sxs-lookup"><span data-stu-id="cc337-111">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="cc337-112">在“工作进程”窗格中，查看“CPU 百分比”和“专用字节(KB)”（内存）列。</span><span class="sxs-lookup"><span data-stu-id="cc337-112">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="cc337-113">**CPU** 和 **Processor** 性能计数器。</span><span class="sxs-lookup"><span data-stu-id="cc337-113">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="cc337-114">对于大多数部署，UCWA CPU 平均使用率应低于 15%。</span><span class="sxs-lookup"><span data-stu-id="cc337-114">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="cc337-115">内存使用量应位于 Skype for [Business Server 中的服务器内存容量限制的监视器中所述的限制内](server-memory-capacity-limits.md)。</span><span class="sxs-lookup"><span data-stu-id="cc337-115">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="cc337-116">除了 CPU 和内存使用率计数器之外，您还可以使用以下性能计数器来帮助确定服务器何时因请求而过载：</span><span class="sxs-lookup"><span data-stu-id="cc337-116">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="cc337-117">**LS：WEB - 限制和身份验证\WEB -** 处理中的请求总数，指示服务器上挂起的 Web 请求数。</span><span class="sxs-lookup"><span data-stu-id="cc337-117">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="cc337-118">当此计数器达到 10，000 时，后续请求将失败，并出现错误消息"503 - 服务不可用"。</span><span class="sxs-lookup"><span data-stu-id="cc337-118">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="cc337-119">**ASP.NET\Requests Queued**（应始终为零）。</span><span class="sxs-lookup"><span data-stu-id="cc337-119">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="cc337-120">如果满足或超过这些值，应重新访问和重新计算容量规划，以正确调整承载 Web 服务的计算机的 CPU、内核数和内存大小。</span><span class="sxs-lookup"><span data-stu-id="cc337-120">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="cc337-121">**对于 Mobility Service (Mcx) ：**</span><span class="sxs-lookup"><span data-stu-id="cc337-121">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="cc337-122">**IIS 管理器中的 CSIntMcxAppPool** 和 **CSExtMcxAppPool** Internet Information Services () 进程。</span><span class="sxs-lookup"><span data-stu-id="cc337-122">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="cc337-123">在“工作进程”窗格中，查看“CPU 百分比”和“专用字节(KB)”（内存）列。</span><span class="sxs-lookup"><span data-stu-id="cc337-123">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="cc337-124">**CPU** 和 **Processor** 性能计数器。</span><span class="sxs-lookup"><span data-stu-id="cc337-124">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="cc337-125">对于大多数部署，Mobility Service CPU 使用率应平均低于 15%。</span><span class="sxs-lookup"><span data-stu-id="cc337-125">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="cc337-126">内存使用量应位于 Skype for [Business Server 中的服务器内存容量限制的监视器中所述的限制内](server-memory-capacity-limits.md)。</span><span class="sxs-lookup"><span data-stu-id="cc337-126">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="cc337-127">除 CPU 和内存使用率计数器之外，您可以使用以下 ASP.NET 性能计数器来帮助确定服务器上的请求何时过载：</span><span class="sxs-lookup"><span data-stu-id="cc337-127">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="cc337-128">**ASP.NET v2.0.50727\Requests Current**，指示服务器上挂起的 Web 请求的数目。</span><span class="sxs-lookup"><span data-stu-id="cc337-128">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="cc337-129">当此计数器达到 5，000 时，后续请求将失败，并返回错误消息"503 - 服务不可用"。</span><span class="sxs-lookup"><span data-stu-id="cc337-129">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="cc337-130">**ASP.NET\Requests Queued**（应始终为零）。</span><span class="sxs-lookup"><span data-stu-id="cc337-130">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="cc337-131">如果满足或超过这些值，应重新检查和重新计算容量规划，以正确调整承载 Web 服务的计算机的 CPU、内核数和内存大小。</span><span class="sxs-lookup"><span data-stu-id="cc337-131">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 

> [!NOTE]
> <span data-ttu-id="cc337-132">SKYPE (Server 2019 中不再提供对) 移动客户端的 MCX 移动服务支持。</span><span class="sxs-lookup"><span data-stu-id="cc337-132">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="cc337-133">所有当前的 Skype for Business 移动客户端已使用统一通信 Web API (UCWA) 来支持即时消息 (IM) 、状态和联系人。</span><span class="sxs-lookup"><span data-stu-id="cc337-133">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="cc337-134">使用 MCX 的旧客户端的用户将需要升级到当前客户端。</span><span class="sxs-lookup"><span data-stu-id="cc337-134">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cc337-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cc337-135">See also</span></span>

[<span data-ttu-id="cc337-136">监视 Skype for Business Server 中的服务器内存容量限制</span><span class="sxs-lookup"><span data-stu-id="cc337-136">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
