---
title: Lync Server 2013：监视 Lync Server 性能
description: Lync Server 2013：监视 Lync Server 性能。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring Lync Server 2013 performance
ms:assetid: 2acfd720-6120-4816-a2d4-30476bd5cd0e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720910(v=OCS.15)
ms:contentKeyID: 63969592
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efe63a881c9db105fc36a1ccd0b0fdc15086a36f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548098"
---
# <a name="monitoring-lync-server-2013-performance"></a><span data-ttu-id="771fb-103">监视 Lync Server 2013 性能</span><span class="sxs-lookup"><span data-stu-id="771fb-103">Monitoring Lync Server 2013 performance</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="771fb-104">_**上次修改的主题：** 2014-05-15_</span><span class="sxs-lookup"><span data-stu-id="771fb-104">_**Topic Last Modified:** 2014-05-15_</span></span>

<span data-ttu-id="771fb-105">Lync Server 2013 的性能受各种因素（如用户配置文件、系统体系结构、软件、硬件组件、第三方集成点，如网关和电话设备、网络连接和性能、Windows Active Directory 服务配置和性能以及 Windows 操作系统功能）的影响。</span><span class="sxs-lookup"><span data-stu-id="771fb-105">Lync Server 2013 performance is affected by various factors such as user profiles, system architecture, software, hardware components, third-party integration points such as gateways and telephony equipment, network connectivity and performance, Windows Active Directory service configuration and performance in addition to the Windows operating system functionality.</span></span>

<span data-ttu-id="771fb-106">在 Lync Server 2013 部署的核心上，性能是实施它的服务器软件和硬件。</span><span class="sxs-lookup"><span data-stu-id="771fb-106">At the core of a Lync Server 2013 deployments’ performance is the server software and hardware it is implemented on.</span></span> <span data-ttu-id="771fb-107">例如，前端服务器必须具有足够的硬件资源，以处理预期的 (短期) 用户负载。</span><span class="sxs-lookup"><span data-stu-id="771fb-107">As an example, a front-end server must have sufficient hardware resources to cope with the expected (short-term) user load.</span></span> <span data-ttu-id="771fb-108">如果需要使用相应的前端服务器来向10000用户提供服务，则经过充分配置的服务器必须满足预期的负载要求，才能最终帮助确保最佳的最终用户体验。</span><span class="sxs-lookup"><span data-stu-id="771fb-108">If a respective front-end server is required to provide services to 10 thousand users, then an adequately configured server must meet the expected load requirements to ultimately help ensure the best possible end-user experience.</span></span>

<span data-ttu-id="771fb-109">因此，监视服务器性能对于评估所实施的服务器基础结构是否有适合日常负载要求的硬件资源极其重要。</span><span class="sxs-lookup"><span data-stu-id="771fb-109">Monitoring server performance is therefore extremely important to gauge whether the implemented server infrastructure have suitable hardware resources for the day-to-day peak-load requirements.</span></span> <span data-ttu-id="771fb-110">监视服务器性能有助于识别系统瓶颈，从而使管理员能够在最终用户体验受到影响之前应用纠正措施。</span><span class="sxs-lookup"><span data-stu-id="771fb-110">Monitoring server performance helps identify system bottlenecks allowing administrators to apply corrective action before the end-user experience is affected.</span></span> <span data-ttu-id="771fb-111">应使用性能数据进行长期容量规划。</span><span class="sxs-lookup"><span data-stu-id="771fb-111">The performance data should be used for long-term capacity planning.</span></span>

<span data-ttu-id="771fb-112">[！注意] 有关要观测到的所有性能对象和计数器的详细信息均链接到 [使用 System Center Operations Manager 监视 Lync Server 2013](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)，应遵循的一些性能计数器可以为管理员提供系统性能的快速视图：</span><span class="sxs-lookup"><span data-stu-id="771fb-112">While detailed information on all performance objects and counters to be observed is linked to in [Monitoring Lync Server 2013 with System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md), some performance counters that you should follow can provide administrators a quick view of the system performance:</span></span>

  - <span data-ttu-id="771fb-113">为了跟踪前端服务器的整体系统运行状况，良好的起始点是检查处理器 \\ 的处理器时间。</span><span class="sxs-lookup"><span data-stu-id="771fb-113">To track overall system health of the front-end server, a good starting point is to check Processor\\% Processor Time.</span></span> <span data-ttu-id="771fb-114">该值应始终低于80%。</span><span class="sxs-lookup"><span data-stu-id="771fb-114">The value should always be below 80 percent.</span></span>

  - <span data-ttu-id="771fb-115">若要跟踪前端池使用的后端 SQL Server 数据库软件实例的性能，请监视以下性能计数器：</span><span class="sxs-lookup"><span data-stu-id="771fb-115">To track the performance of the back end SQL Server database software instance used by the Front End pool, monitor the following performance counters:</span></span>
    
    <span data-ttu-id="771fb-116">LC： USrv –00– DBStore \\ USrv –002– (毫秒的队列延迟) </span><span class="sxs-lookup"><span data-stu-id="771fb-116">LC:USrv – 00 – DBStore\\Usrv – 002 – Queue Latency (msec)</span></span>
    
    <span data-ttu-id="771fb-117">LC： USrv –00– DBStore \\ USrv – 0 04 –过程延迟 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="771fb-117">LC:USrv – 00 – DBStore\\Usrv – 0 04– Sproc Latency (msec)</span></span>
    
    <span data-ttu-id="771fb-118">处于稳定状态的正常服务器应显示 \< 100 毫秒延迟值。</span><span class="sxs-lookup"><span data-stu-id="771fb-118">The healthy server at steady state should show \<100 ms latency values.</span></span> <span data-ttu-id="771fb-119">当延迟达到12秒时，将会进行限制机制，这意味着前端服务器开始将请求限制到后端。</span><span class="sxs-lookup"><span data-stu-id="771fb-119">The throttling mechanism will engage when latency reaches 12 seconds, which means the front-end server starts throttling requests to the back end.</span></span> <span data-ttu-id="771fb-120">这会导致客户端收到 "503 服务器太忙" 错误消息。</span><span class="sxs-lookup"><span data-stu-id="771fb-120">This causes clients to start to receive a 503 Server too busy error message.</span></span>

  - <span data-ttu-id="771fb-121">若要跟踪前端服务器的处理时间，请监视以下计数器：</span><span class="sxs-lookup"><span data-stu-id="771fb-121">To track the processing time at the front-end server, monitor the following counter:</span></span>
    
    <span data-ttu-id="771fb-122">LC： SIP-07-Load Management \\ SIP-000-传入邮件的平均保留时间</span><span class="sxs-lookup"><span data-stu-id="771fb-122">LC:SIP - 07 - Load Management\\SIP - 000 - Average Holding Time For Incoming Messages</span></span>
    
    <span data-ttu-id="771fb-123">这是前端服务器上的另一种限制机制，这一次是在前端处理时间较高时开始。</span><span class="sxs-lookup"><span data-stu-id="771fb-123">This is another throttling mechanism on the front-end servers, this time starting when the processing time on the front end is high.</span></span> <span data-ttu-id="771fb-124">如果平均处理时间超过6秒，则服务器将进入限制模式，并且每个客户端连接只允许一个未完成的事务。</span><span class="sxs-lookup"><span data-stu-id="771fb-124">If average processing time is more than six seconds, the server goes into throttling mode and only allows one outstanding transaction per client connection.</span></span>

  - <span data-ttu-id="771fb-125">若要跟踪 SQL 后端服务器上的内存问题，请监视以下计数器：</span><span class="sxs-lookup"><span data-stu-id="771fb-125">To track memory issues at SQL Back End Server, monitor the following counter:</span></span>
    
    <span data-ttu-id="771fb-126">SQL Server 缓冲区管理器 \\ 页生命预期</span><span class="sxs-lookup"><span data-stu-id="771fb-126">SQL Server Buffer Manager\\Page life expectancy</span></span>
    
    <span data-ttu-id="771fb-127">低值低于3600秒 (与高延迟写入数/秒和检查点页/秒) 表示内存压力。</span><span class="sxs-lookup"><span data-stu-id="771fb-127">A low value, below 3600 seconds (together with high latency writes/sec and checkpoint pages/sec) indicates memory pressure.</span></span>

<div>

## <a name="additional-counters-to-view"></a><span data-ttu-id="771fb-128">要查看的其他计数器</span><span class="sxs-lookup"><span data-stu-id="771fb-128">Additional Counters to View</span></span>

<span data-ttu-id="771fb-129">有几个关键计数器是前端服务器的总体运行状况的良好指示器。</span><span class="sxs-lookup"><span data-stu-id="771fb-129">There are several key counters that are good indicators of overall health from the front end server.</span></span> <span data-ttu-id="771fb-130">这并不是一个完整的列表，并不是为了确定根本原因。</span><span class="sxs-lookup"><span data-stu-id="771fb-130">This is not a comprehensive list and is not meant to identify root cause.</span></span> <span data-ttu-id="771fb-131">这些计数器将允许你对服务器运行状况执行快速检查。</span><span class="sxs-lookup"><span data-stu-id="771fb-131">These counters will let you perform a quick check on your server health.</span></span> <span data-ttu-id="771fb-132">建议在池中的每台服务器上验证这些计数器。</span><span class="sxs-lookup"><span data-stu-id="771fb-132">We recommend verifying these counters on each of the servers in the pool.</span></span> <span data-ttu-id="771fb-133">在服务器运行正常时，了解这些计数器的值是非常重要的。</span><span class="sxs-lookup"><span data-stu-id="771fb-133">It is important to understand what these counter values are when your server is healthy.</span></span> <span data-ttu-id="771fb-134">需要使用基准来了解在用户体验降级时所做的更改。</span><span class="sxs-lookup"><span data-stu-id="771fb-134">A baseline is required to understand what changed when the user experience is degraded.</span></span>

<span data-ttu-id="771fb-135">前端服务器可以指示可能由系统中其他地方的瓶颈导致的问题。</span><span class="sxs-lookup"><span data-stu-id="771fb-135">The front-end server can indicate issues that may be caused by bottlenecks elsewhere in the system.</span></span> <span data-ttu-id="771fb-136">这意味着，它是查看整体系统运行状况时的最佳开始位置。</span><span class="sxs-lookup"><span data-stu-id="771fb-136">This means that it is the best place to start when looking at overall system health.</span></span>

<span data-ttu-id="771fb-137">要首先查看的两个额外的计数器如下所示：</span><span class="sxs-lookup"><span data-stu-id="771fb-137">Two additional counters to review first are as follows:</span></span>

<span data-ttu-id="771fb-138">LC： USrv-00-DBStore \\ USrv-002-队列延迟 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="771fb-138">LC:USrv-00-DBStore\\Usrv-002-Queue Latency (msec)</span></span>

<span data-ttu-id="771fb-139">LC： USrv-00-DBStore \\ USrv-004---过程延迟 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="771fb-139">LC:USrv-00-DBStore\\Usrv-004-Sproc Latency (msec)</span></span>

<span data-ttu-id="771fb-140">Queue counter 计数器表示队列中的请求在后端所用的时间，而处理程序延迟表示后端处理请求所用的时间。</span><span class="sxs-lookup"><span data-stu-id="771fb-140">The queue latency counter represents the time that a request spent in the queue to the back end and the Sproc latency represents the time that it took for the back end to process the request.</span></span> <span data-ttu-id="771fb-141">如果出于任何原因导致后端的磁盘、内存、网络和处理器出现问题，则队列延迟计数器将较高。</span><span class="sxs-lookup"><span data-stu-id="771fb-141">If, for any reason, disk, memory, network, and processor on the back end are in trouble, the queue latency counter will be high.</span></span>

<span data-ttu-id="771fb-142">如果前端和后端之间存在较高的网络延迟，则它也可能很高。</span><span class="sxs-lookup"><span data-stu-id="771fb-142">It can also be high if there is high network latency between the front end and the back end.</span></span> <span data-ttu-id="771fb-143">那么，可接受的队列延迟是什么？</span><span class="sxs-lookup"><span data-stu-id="771fb-143">So what is acceptable queue latency?</span></span>

<span data-ttu-id="771fb-144">在12秒时，前端服务器开始对后端服务器的限制请求。</span><span class="sxs-lookup"><span data-stu-id="771fb-144">At 12 seconds, the Front End Servers start throttling requests to the Back End Servers.</span></span> <span data-ttu-id="771fb-145">这意味着服务器开始向客户端返回的服务器太忙–503错误。</span><span class="sxs-lookup"><span data-stu-id="771fb-145">This means the servers start returning Server too busy – 503 errors to the clients.</span></span> <span data-ttu-id="771fb-146">正常运行的服务器应具有低于100毫秒的 DBStore 队列延迟，但在服务器刚刚联机且同时用户同时登录时，该计数器可能会非常高，甚至你可能会看到它在数秒内遇到了多次。</span><span class="sxs-lookup"><span data-stu-id="771fb-146">A healthy server should have less than 100 msec DBStore queue latencies at steady state, but during times where the server has just come online and users are all logging in at the same time, that counter can be very high and you may even see it hit multiple seconds.</span></span>

<span data-ttu-id="771fb-147">您可以使用负载平衡配置，其中包含多台前端服务器部署的池和配置为 "最少连接数" 的负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="771fb-147">You may have a load-balanced configuration, where you have a pool deployed with multiple front-end servers and a load balancer that is configured for "least number of connections."</span></span> <span data-ttu-id="771fb-148">在这种情况下，如果一台前端服务器重新启动，则尝试重新连接的所有用户都将指向重新启动的服务器，因为与其他池成员相比，该服务器的连接数较少。</span><span class="sxs-lookup"><span data-stu-id="771fb-148">In this case, if one front-end server is restarted, then all users who attempt to reconnect will be pointed to the restarted server, because that server will have fewer connections compared to the other pool members.</span></span> <span data-ttu-id="771fb-149">在这段时间内，可能会重载相应的前端服务器，而其他池成员则不会。</span><span class="sxs-lookup"><span data-stu-id="771fb-149">During this time, the respective front-end server may be overloaded while the other pool members are not.</span></span>

<span data-ttu-id="771fb-150">我们建议您在非工作时间执行维护以降低性能影响，因为用户不会同时与服务器同时连接到服务器。</span><span class="sxs-lookup"><span data-stu-id="771fb-150">We recommend that you perform maintenance during off-hours to reduce the performance affect as users will not all be competing to connect to the server at the same time.</span></span>

<span data-ttu-id="771fb-151">如果前两个性能计数器较高，则最可能的瓶颈是 SQL 后端服务器。</span><span class="sxs-lookup"><span data-stu-id="771fb-151">If the previous two performance counters are high, the most likely bottleneck is the SQL Back End Server.</span></span> <span data-ttu-id="771fb-152">下一个要确认的组件如下所示：</span><span class="sxs-lookup"><span data-stu-id="771fb-152">The next components to confirm are as follows:</span></span>

  - <span data-ttu-id="771fb-153">SQL Server CPU 是否过高？</span><span class="sxs-lookup"><span data-stu-id="771fb-153">Is the SQL Server CPU too high?</span></span> <span data-ttu-id="771fb-154">例如，它是否大于80%？</span><span class="sxs-lookup"><span data-stu-id="771fb-154">For example, is it greater than 80 percent?</span></span>

  - <span data-ttu-id="771fb-155">磁盘延迟是否为高？</span><span class="sxs-lookup"><span data-stu-id="771fb-155">Is the disk latency high?</span></span>

<span data-ttu-id="771fb-156">在理想的世界中，有足够的 RAM 将 RTC 和 RTCDYN 数据库同时存储在内存中。</span><span class="sxs-lookup"><span data-stu-id="771fb-156">In an ideal world, you have enough RAM to have both the RTC and RTCDYN databases in memory.</span></span> <span data-ttu-id="771fb-157">然后，服务器将访问磁盘的唯一原因是写入日志文件并刷新数据库。</span><span class="sxs-lookup"><span data-stu-id="771fb-157">Then, the only reason the server would be accessing the disk, is to write to the log files and flush to the databases.</span></span> <span data-ttu-id="771fb-158">测试显示，12 GB RAM 足以满足100000用户部署的需要。</span><span class="sxs-lookup"><span data-stu-id="771fb-158">Tests have shown that 12 GB of RAM is sufficient for 100 thousand user deployments.</span></span> <span data-ttu-id="771fb-159">这假定 RTC 和 RTCDYN 数据库的大小总和小于 12 GB。</span><span class="sxs-lookup"><span data-stu-id="771fb-159">This assumes that the RTC and RTCDYN databases size totals less than 12 GB.</span></span> <span data-ttu-id="771fb-160">如果您的数据库大于该数据库，则可能需要额外的内存。</span><span class="sxs-lookup"><span data-stu-id="771fb-160">If your databases are larger than that, then you may need additional memory.</span></span>

<span data-ttu-id="771fb-161">您可以通过查看 SQL Server 缓冲区管理器页生命预期性能计数器来确定您的 SQL Server 是否需要额外的 RAM。</span><span class="sxs-lookup"><span data-stu-id="771fb-161">You can determine whether your SQL Server requires additional RAM by reviewing the SQL Server Buffer Manager page life expectancy performance counter.</span></span> <span data-ttu-id="771fb-162">小于3600的值表示内存压力。</span><span class="sxs-lookup"><span data-stu-id="771fb-162">A value less than 3,600 indicates memory pressure.</span></span> <span data-ttu-id="771fb-163">如果有足够的内存，您还应该在数据库驱动器上看不到读取的内容，因为 SQL Server 只应写入数据库。</span><span class="sxs-lookup"><span data-stu-id="771fb-163">You should also see little to no reads on your database drive if you have sufficient memory because SQL Server should only be writing to the database.</span></span>

<span data-ttu-id="771fb-164">如果服务器处理时间较高，则会在启动 Lync Server 2013 前端服务器时启动其他限制机制。</span><span class="sxs-lookup"><span data-stu-id="771fb-164">There is an additional throttling mechanism in a Lync Server 2013 Front End Server that starts if the server processing time is high.</span></span> <span data-ttu-id="771fb-165">仅当对 SQL Server 的延迟较高时，才会启用 DBStore 延迟限制。</span><span class="sxs-lookup"><span data-stu-id="771fb-165">The DBStore latency throttling is only enabled if the latency to the SQL Server is high.</span></span> <span data-ttu-id="771fb-166">启用此限制的一个示例是，如果前端服务器是 CPU 界限的。</span><span class="sxs-lookup"><span data-stu-id="771fb-166">One example in which such throttling is enabled is if the front-end server is CPU-bound.</span></span>

<span data-ttu-id="771fb-167">如果在服务器上的平均处理时间 \*\* (LC：在服务器上 \\) 的传入邮件的平均保留时间 \*\* 超过6秒，则服务器将进入限制模式，并只为用户每个客户端连接提供一个未完成的事务。</span><span class="sxs-lookup"><span data-stu-id="771fb-167">If the average processing time **(LC:SIP-07-Load Management\\SIP-000-Average Holding Time For Incoming Messages)** on the server exceeds six seconds, then the server goes into throttling mode and only gives users one outstanding transaction per client connection.</span></span> <span data-ttu-id="771fb-168">在处理时间降到3秒后，服务器将断开限制模式，并为用户提供每个客户端连接20个未完成的事务。</span><span class="sxs-lookup"><span data-stu-id="771fb-168">Once the processing time drops to three seconds, then the server drops out of throttling mode and gives users up to 20 outstanding transactions per client connection.</span></span> <span data-ttu-id="771fb-169">只要特定连接上的事务数超过上述阈值，该连接将被标记为 "以流方式控制"。</span><span class="sxs-lookup"><span data-stu-id="771fb-169">Whenever the number of transactions on a specific connection exceeds the threshold above, the connection is marked as flow controlled.</span></span> <span data-ttu-id="771fb-170">结果是服务器不会在其上发布任何接收，而 **LC： SIP-01 对等 \\ 流控制的连接** 计数器将递增。</span><span class="sxs-lookup"><span data-stu-id="771fb-170">The result is the server does not post any receives on it, and the **LC:SIP-01-Peers\\Flow Controlled Connections** counter is incremented.</span></span> <span data-ttu-id="771fb-171">如果连接在受流控制的状态中保持一分钟以上，则服务器将关闭该连接。</span><span class="sxs-lookup"><span data-stu-id="771fb-171">If a connection stays in a flow-controlled state for more than one minute, then the server closes it.</span></span> <span data-ttu-id="771fb-172">它会以延迟的方法执行此操作。</span><span class="sxs-lookup"><span data-stu-id="771fb-172">It does so lazily.</span></span> <span data-ttu-id="771fb-173">如果有机会检查连接，它将确定它是否被限制为太长，如果超过一分钟，则关闭该连接。</span><span class="sxs-lookup"><span data-stu-id="771fb-173">When it has an opportunity to check the connection, it determines whether it was throttled for too long and closes it if it has more than one minute.</span></span>

<span data-ttu-id="771fb-174">这些是两种限制机制，并且有一个性能计数器，用于汇总服务器执行的操作（如果有）（如果有）限制。</span><span class="sxs-lookup"><span data-stu-id="771fb-174">These are the two throttling mechanisms and there is one performance counter that summarizes what, if any, throttling the server is performing.</span></span>

<span data-ttu-id="771fb-175">**LC： SIP-04-响应 \\ SIP-053-本地503响应数/秒**</span><span class="sxs-lookup"><span data-stu-id="771fb-175">**LC:SIP-04-Responses\\SIP-053-Local 503 Responses/sec**</span></span>

  - <span data-ttu-id="771fb-176">上一个计数器中的 "Local" 一词指的是本地生成的响应。</span><span class="sxs-lookup"><span data-stu-id="771fb-176">The term "Local" in the previous counter refers to locally generated responses.</span></span>

  - <span data-ttu-id="771fb-177">503代码对应于服务器不可用，您不应在正常服务器上看到任何503代码。</span><span class="sxs-lookup"><span data-stu-id="771fb-177">The 503 code corresponds to server unavailable—where you should not see any 503 codes on a healthy server.</span></span> <span data-ttu-id="771fb-178">在服务器刚联机后的一段时间内，您可能会看到一些503代码。</span><span class="sxs-lookup"><span data-stu-id="771fb-178">During the period after a server is just brought online, you may see some 503 codes.</span></span> <span data-ttu-id="771fb-179">当所有用户重新登录并返回到稳定状态时，不应再添加503个代码。</span><span class="sxs-lookup"><span data-stu-id="771fb-179">When all of the users sign back in and the server returns to a stable state, there should no additional 503 codes.</span></span>

<span data-ttu-id="771fb-180">**LC： SIP-04-响应 \\ SIP-074-本地504响应数/秒**</span><span class="sxs-lookup"><span data-stu-id="771fb-180">**LC:SIP-04-Responses\\SIP-074-Local 504 Responses/sec**</span></span>

<span data-ttu-id="771fb-181">此性能计数器指示其他服务器的连接问题，它可能指示连接失败或连接延迟。</span><span class="sxs-lookup"><span data-stu-id="771fb-181">This performance counter indicates connectivity issues with other servers and it can indicate failures to connect or delays in connecting.</span></span> <span data-ttu-id="771fb-182">如果您看到504错误，则应检查以下性能计数器。</span><span class="sxs-lookup"><span data-stu-id="771fb-182">If you are seeing 504 errors then the following performance counter should be checked.</span></span>

<span data-ttu-id="771fb-183">**LC： SIP-01-对等 \\ sip-017-发送未完成**</span><span class="sxs-lookup"><span data-stu-id="771fb-183">**LC:SIP-01-Peers\\SIP-017-Sends Outstanding**</span></span>

<span data-ttu-id="771fb-184">此计数器指示传出排队的请求和响应的数量。</span><span class="sxs-lookup"><span data-stu-id="771fb-184">This counter indicates the number of outgoing queued requests and responses.</span></span> <span data-ttu-id="771fb-185">如果此计数器较高，则问题很可能不在本地服务器上。</span><span class="sxs-lookup"><span data-stu-id="771fb-185">If this counter is high then the issue is most likely not on the local server.</span></span> <span data-ttu-id="771fb-186">请注意，如果存在网络延迟问题，此计数器可能很高。</span><span class="sxs-lookup"><span data-stu-id="771fb-186">Note that this counter can be high if there are network latency issues.</span></span> <span data-ttu-id="771fb-187">它还可能指示本地网络适配器存在问题，但更可能是由远程服务器上的问题导致的。</span><span class="sxs-lookup"><span data-stu-id="771fb-187">It could also indicate issues with the local network adapter, but is more likely caused by an issue on a remote server.</span></span> <span data-ttu-id="771fb-188">当要与之进行通信的池超载时，此计数器很可能在控制器服务器上是很高的。</span><span class="sxs-lookup"><span data-stu-id="771fb-188">This counter would most likely be high on a Director server when the pool it is trying to communicate with is overloaded.</span></span> <span data-ttu-id="771fb-189">此计数器的关键是查看实例，而不仅仅是总数。</span><span class="sxs-lookup"><span data-stu-id="771fb-189">The key with this counter is to look at the instances, not just the total.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

