---
title: Lync Server 2013：监视 Lync Server 性能
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
ms.openlocfilehash: bd46beb944f676b9916472cc39394d84ae205786
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-lync-server-2013-performance"></a><span data-ttu-id="e02f9-102">监视 Lync Server 2013 性能</span><span class="sxs-lookup"><span data-stu-id="e02f9-102">Monitoring Lync Server 2013 performance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e02f9-103">_**上次修改的主题：** 2014-05-15_</span><span class="sxs-lookup"><span data-stu-id="e02f9-103">_**Topic Last Modified:** 2014-05-15_</span></span>

<span data-ttu-id="e02f9-104">Lync Server 2013 的性能受到各种因素的影响，如用户配置文件、系统体系结构、软件、硬件组件、第三方集成点（例如网关和电话设备）、网络连接和性能、Windows除 Windows 操作系统功能之外的 Active Directory 服务配置和性能。</span><span class="sxs-lookup"><span data-stu-id="e02f9-104">Lync Server 2013 performance is affected by various factors such as user profiles, system architecture, software, hardware components, third-party integration points such as gateways and telephony equipment, network connectivity and performance, Windows Active Directory service configuration and performance in addition to the Windows operating system functionality.</span></span>

<span data-ttu-id="e02f9-105">在 Lync Server 2013 部署的核心上，性能是实施它的服务器软件和硬件。</span><span class="sxs-lookup"><span data-stu-id="e02f9-105">At the core of a Lync Server 2013 deployments’ performance is the server software and hardware it is implemented on.</span></span> <span data-ttu-id="e02f9-106">例如，前端服务器必须有足够的硬件资源来处理预期的（短期）用户负载。</span><span class="sxs-lookup"><span data-stu-id="e02f9-106">As an example, a front-end server must have sufficient hardware resources to cope with the expected (short-term) user load.</span></span> <span data-ttu-id="e02f9-107">如果需要使用相应的前端服务器来向10000用户提供服务，则经过充分配置的服务器必须满足预期的负载要求，才能最终帮助确保最佳的最终用户体验。</span><span class="sxs-lookup"><span data-stu-id="e02f9-107">If a respective front-end server is required to provide services to 10 thousand users, then an adequately configured server must meet the expected load requirements to ultimately help ensure the best possible end-user experience.</span></span>

<span data-ttu-id="e02f9-108">因此，监视服务器性能对于评估所实施的服务器基础结构是否有适合日常负载要求的硬件资源极其重要。</span><span class="sxs-lookup"><span data-stu-id="e02f9-108">Monitoring server performance is therefore extremely important to gauge whether the implemented server infrastructure have suitable hardware resources for the day-to-day peak-load requirements.</span></span> <span data-ttu-id="e02f9-109">监视服务器性能有助于识别系统瓶颈，从而使管理员能够在最终用户体验受到影响之前应用纠正措施。</span><span class="sxs-lookup"><span data-stu-id="e02f9-109">Monitoring server performance helps identify system bottlenecks allowing administrators to apply corrective action before the end-user experience is affected.</span></span> <span data-ttu-id="e02f9-110">应使用性能数据进行长期容量规划。</span><span class="sxs-lookup"><span data-stu-id="e02f9-110">The performance data should be used for long-term capacity planning.</span></span>

<span data-ttu-id="e02f9-111">[！注意] 有关要观测到的所有性能对象和计数器的详细信息均链接到[使用 System Center Operations Manager 监视 Lync Server 2013](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)，应遵循的一些性能计数器可以为管理员提供系统性能的快速视图：</span><span class="sxs-lookup"><span data-stu-id="e02f9-111">While detailed information on all performance objects and counters to be observed is linked to in [Monitoring Lync Server 2013 with System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md), some performance counters that you should follow can provide administrators a quick view of the system performance:</span></span>

  - <span data-ttu-id="e02f9-112">为了跟踪前端服务器的整体系统运行状况，良好的起始点是检查处理器\\的处理器时间。</span><span class="sxs-lookup"><span data-stu-id="e02f9-112">To track overall system health of the front-end server, a good starting point is to check Processor\\% Processor Time.</span></span> <span data-ttu-id="e02f9-113">该值应始终低于80%。</span><span class="sxs-lookup"><span data-stu-id="e02f9-113">The value should always be below 80 percent.</span></span>

  - <span data-ttu-id="e02f9-114">若要跟踪前端池使用的后端 SQL Server 数据库软件实例的性能，请监视以下性能计数器：</span><span class="sxs-lookup"><span data-stu-id="e02f9-114">To track the performance of the back end SQL Server database software instance used by the Front End pool, monitor the following performance counters:</span></span>
    
    <span data-ttu-id="e02f9-115">LC： USrv –00– DBStore\\USrv –002–队列延迟（毫秒）</span><span class="sxs-lookup"><span data-stu-id="e02f9-115">LC:USrv – 00 – DBStore\\Usrv – 002 – Queue Latency (msec)</span></span>
    
    <span data-ttu-id="e02f9-116">LC： USrv –00– DBStore\\USrv – 0 04 –过程延迟（毫秒）</span><span class="sxs-lookup"><span data-stu-id="e02f9-116">LC:USrv – 00 – DBStore\\Usrv – 0 04– Sproc Latency (msec)</span></span>
    
    <span data-ttu-id="e02f9-117">处于稳定状态的正常服务器应显示\<100 毫秒延迟值。</span><span class="sxs-lookup"><span data-stu-id="e02f9-117">The healthy server at steady state should show \<100 ms latency values.</span></span> <span data-ttu-id="e02f9-118">当延迟达到12秒时，将会进行限制机制，这意味着前端服务器开始将请求限制到后端。</span><span class="sxs-lookup"><span data-stu-id="e02f9-118">The throttling mechanism will engage when latency reaches 12 seconds, which means the front-end server starts throttling requests to the back end.</span></span> <span data-ttu-id="e02f9-119">这会导致客户端收到 "503 服务器太忙" 错误消息。</span><span class="sxs-lookup"><span data-stu-id="e02f9-119">This causes clients to start to receive a 503 Server too busy error message.</span></span>

  - <span data-ttu-id="e02f9-120">若要跟踪前端服务器的处理时间，请监视以下计数器：</span><span class="sxs-lookup"><span data-stu-id="e02f9-120">To track the processing time at the front-end server, monitor the following counter:</span></span>
    
    <span data-ttu-id="e02f9-121">LC： SIP-07-Load Management\\SIP-000-传入邮件的平均保留时间</span><span class="sxs-lookup"><span data-stu-id="e02f9-121">LC:SIP - 07 - Load Management\\SIP - 000 - Average Holding Time For Incoming Messages</span></span>
    
    <span data-ttu-id="e02f9-122">这是前端服务器上的另一种限制机制，这一次是在前端处理时间较高时开始。</span><span class="sxs-lookup"><span data-stu-id="e02f9-122">This is another throttling mechanism on the front-end servers, this time starting when the processing time on the front end is high.</span></span> <span data-ttu-id="e02f9-123">如果平均处理时间超过6秒，则服务器将进入限制模式，并且每个客户端连接只允许一个未完成的事务。</span><span class="sxs-lookup"><span data-stu-id="e02f9-123">If average processing time is more than six seconds, the server goes into throttling mode and only allows one outstanding transaction per client connection.</span></span>

  - <span data-ttu-id="e02f9-124">若要跟踪 SQL 后端服务器上的内存问题，请监视以下计数器：</span><span class="sxs-lookup"><span data-stu-id="e02f9-124">To track memory issues at SQL Back End Server, monitor the following counter:</span></span>
    
    <span data-ttu-id="e02f9-125">SQL Server 缓冲区管理\\器页生命预期</span><span class="sxs-lookup"><span data-stu-id="e02f9-125">SQL Server Buffer Manager\\Page life expectancy</span></span>
    
    <span data-ttu-id="e02f9-126">低值低于3600秒（加上高延迟写入次数/秒和检查点页数/秒）表示内存压力。</span><span class="sxs-lookup"><span data-stu-id="e02f9-126">A low value, below 3600 seconds (together with high latency writes/sec and checkpoint pages/sec) indicates memory pressure.</span></span>

<div>

## <a name="additional-counters-to-view"></a><span data-ttu-id="e02f9-127">要查看的其他计数器</span><span class="sxs-lookup"><span data-stu-id="e02f9-127">Additional Counters to View</span></span>

<span data-ttu-id="e02f9-128">有几个关键计数器是前端服务器的总体运行状况的良好指示器。</span><span class="sxs-lookup"><span data-stu-id="e02f9-128">There are several key counters that are good indicators of overall health from the front end server.</span></span> <span data-ttu-id="e02f9-129">这并不是一个完整的列表，并不是为了确定根本原因。</span><span class="sxs-lookup"><span data-stu-id="e02f9-129">This is not a comprehensive list and is not meant to identify root cause.</span></span> <span data-ttu-id="e02f9-130">这些计数器将允许你对服务器运行状况执行快速检查。</span><span class="sxs-lookup"><span data-stu-id="e02f9-130">These counters will let you perform a quick check on your server health.</span></span> <span data-ttu-id="e02f9-131">建议在池中的每台服务器上验证这些计数器。</span><span class="sxs-lookup"><span data-stu-id="e02f9-131">We recommend verifying these counters on each of the servers in the pool.</span></span> <span data-ttu-id="e02f9-132">在服务器运行正常时，了解这些计数器的值是非常重要的。</span><span class="sxs-lookup"><span data-stu-id="e02f9-132">It is important to understand what these counter values are when your server is healthy.</span></span> <span data-ttu-id="e02f9-133">需要使用基准来了解在用户体验降级时所做的更改。</span><span class="sxs-lookup"><span data-stu-id="e02f9-133">A baseline is required to understand what changed when the user experience is degraded.</span></span>

<span data-ttu-id="e02f9-134">前端服务器可以指示可能由系统中其他地方的瓶颈导致的问题。</span><span class="sxs-lookup"><span data-stu-id="e02f9-134">The front-end server can indicate issues that may be caused by bottlenecks elsewhere in the system.</span></span> <span data-ttu-id="e02f9-135">这意味着，它是查看整体系统运行状况时的最佳开始位置。</span><span class="sxs-lookup"><span data-stu-id="e02f9-135">This means that it is the best place to start when looking at overall system health.</span></span>

<span data-ttu-id="e02f9-136">要首先查看的两个额外的计数器如下所示：</span><span class="sxs-lookup"><span data-stu-id="e02f9-136">Two additional counters to review first are as follows:</span></span>

<span data-ttu-id="e02f9-137">LC： USrv-00-DBStore\\USrv-002-队列延迟（毫秒）</span><span class="sxs-lookup"><span data-stu-id="e02f9-137">LC:USrv-00-DBStore\\Usrv-002-Queue Latency (msec)</span></span>

<span data-ttu-id="e02f9-138">LC： USrv-00-DBStore\\USrv-004-过程延迟（毫秒）</span><span class="sxs-lookup"><span data-stu-id="e02f9-138">LC:USrv-00-DBStore\\Usrv-004-Sproc Latency (msec)</span></span>

<span data-ttu-id="e02f9-139">Queue counter 计数器表示队列中的请求在后端所用的时间，而处理程序延迟表示后端处理请求所用的时间。</span><span class="sxs-lookup"><span data-stu-id="e02f9-139">The queue latency counter represents the time that a request spent in the queue to the back end and the Sproc latency represents the time that it took for the back end to process the request.</span></span> <span data-ttu-id="e02f9-140">如果出于任何原因导致后端的磁盘、内存、网络和处理器出现问题，则队列延迟计数器将较高。</span><span class="sxs-lookup"><span data-stu-id="e02f9-140">If, for any reason, disk, memory, network, and processor on the back end are in trouble, the queue latency counter will be high.</span></span>

<span data-ttu-id="e02f9-141">如果前端和后端之间存在较高的网络延迟，则它也可能很高。</span><span class="sxs-lookup"><span data-stu-id="e02f9-141">It can also be high if there is high network latency between the front end and the back end.</span></span> <span data-ttu-id="e02f9-142">那么，可接受的队列延迟是什么？</span><span class="sxs-lookup"><span data-stu-id="e02f9-142">So what is acceptable queue latency?</span></span>

<span data-ttu-id="e02f9-143">在12秒时，前端服务器开始对后端服务器的限制请求。</span><span class="sxs-lookup"><span data-stu-id="e02f9-143">At 12 seconds, the Front End Servers start throttling requests to the Back End Servers.</span></span> <span data-ttu-id="e02f9-144">这意味着服务器开始向客户端返回的服务器太忙–503错误。</span><span class="sxs-lookup"><span data-stu-id="e02f9-144">This means the servers start returning Server too busy – 503 errors to the clients.</span></span> <span data-ttu-id="e02f9-145">正常运行的服务器应具有低于100毫秒的 DBStore 队列延迟，但在服务器刚刚联机且同时用户同时登录时，该计数器可能会非常高，甚至你可能会看到它在数秒内遇到了多次。</span><span class="sxs-lookup"><span data-stu-id="e02f9-145">A healthy server should have less than 100 msec DBStore queue latencies at steady state, but during times where the server has just come online and users are all logging in at the same time, that counter can be very high and you may even see it hit multiple seconds.</span></span>

<span data-ttu-id="e02f9-146">您可以使用负载平衡配置，其中包含多台前端服务器部署的池和配置为 "最少连接数" 的负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="e02f9-146">You may have a load-balanced configuration, where you have a pool deployed with multiple front-end servers and a load balancer that is configured for "least number of connections."</span></span> <span data-ttu-id="e02f9-147">在这种情况下，如果一台前端服务器重新启动，则尝试重新连接的所有用户都将指向重新启动的服务器，因为与其他池成员相比，该服务器的连接数较少。</span><span class="sxs-lookup"><span data-stu-id="e02f9-147">In this case, if one front-end server is restarted, then all users who attempt to reconnect will be pointed to the restarted server, because that server will have fewer connections compared to the other pool members.</span></span> <span data-ttu-id="e02f9-148">在这段时间内，可能会重载相应的前端服务器，而其他池成员则不会。</span><span class="sxs-lookup"><span data-stu-id="e02f9-148">During this time, the respective front-end server may be overloaded while the other pool members are not.</span></span>

<span data-ttu-id="e02f9-149">我们建议您在非工作时间执行维护以降低性能影响，因为用户不会同时与服务器同时连接到服务器。</span><span class="sxs-lookup"><span data-stu-id="e02f9-149">We recommend that you perform maintenance during off-hours to reduce the performance affect as users will not all be competing to connect to the server at the same time.</span></span>

<span data-ttu-id="e02f9-150">如果前两个性能计数器较高，则最可能的瓶颈是 SQL 后端服务器。</span><span class="sxs-lookup"><span data-stu-id="e02f9-150">If the previous two performance counters are high, the most likely bottleneck is the SQL Back End Server.</span></span> <span data-ttu-id="e02f9-151">下一个要确认的组件如下所示：</span><span class="sxs-lookup"><span data-stu-id="e02f9-151">The next components to confirm are as follows:</span></span>

  - <span data-ttu-id="e02f9-152">SQL Server CPU 是否过高？</span><span class="sxs-lookup"><span data-stu-id="e02f9-152">Is the SQL Server CPU too high?</span></span> <span data-ttu-id="e02f9-153">例如，它是否大于80%？</span><span class="sxs-lookup"><span data-stu-id="e02f9-153">For example, is it greater than 80 percent?</span></span>

  - <span data-ttu-id="e02f9-154">磁盘延迟是否为高？</span><span class="sxs-lookup"><span data-stu-id="e02f9-154">Is the disk latency high?</span></span>

<span data-ttu-id="e02f9-155">在理想的世界中，有足够的 RAM 将 RTC 和 RTCDYN 数据库同时存储在内存中。</span><span class="sxs-lookup"><span data-stu-id="e02f9-155">In an ideal world, you have enough RAM to have both the RTC and RTCDYN databases in memory.</span></span> <span data-ttu-id="e02f9-156">然后，服务器将访问磁盘的唯一原因是写入日志文件并刷新数据库。</span><span class="sxs-lookup"><span data-stu-id="e02f9-156">Then, the only reason the server would be accessing the disk, is to write to the log files and flush to the databases.</span></span> <span data-ttu-id="e02f9-157">测试显示，12 GB RAM 足以满足100000用户部署的需要。</span><span class="sxs-lookup"><span data-stu-id="e02f9-157">Tests have shown that 12 GB of RAM is sufficient for 100 thousand user deployments.</span></span> <span data-ttu-id="e02f9-158">这假定 RTC 和 RTCDYN 数据库的大小总和小于 12 GB。</span><span class="sxs-lookup"><span data-stu-id="e02f9-158">This assumes that the RTC and RTCDYN databases size totals less than 12 GB.</span></span> <span data-ttu-id="e02f9-159">如果您的数据库大于该数据库，则可能需要额外的内存。</span><span class="sxs-lookup"><span data-stu-id="e02f9-159">If your databases are larger than that, then you may need additional memory.</span></span>

<span data-ttu-id="e02f9-160">您可以通过查看 SQL Server 缓冲区管理器页生命预期性能计数器来确定您的 SQL Server 是否需要额外的 RAM。</span><span class="sxs-lookup"><span data-stu-id="e02f9-160">You can determine whether your SQL Server requires additional RAM by reviewing the SQL Server Buffer Manager page life expectancy performance counter.</span></span> <span data-ttu-id="e02f9-161">小于3600的值表示内存压力。</span><span class="sxs-lookup"><span data-stu-id="e02f9-161">A value less than 3,600 indicates memory pressure.</span></span> <span data-ttu-id="e02f9-162">如果有足够的内存，您还应该在数据库驱动器上看不到读取的内容，因为 SQL Server 只应写入数据库。</span><span class="sxs-lookup"><span data-stu-id="e02f9-162">You should also see little to no reads on your database drive if you have sufficient memory because SQL Server should only be writing to the database.</span></span>

<span data-ttu-id="e02f9-163">如果服务器处理时间较高，则会在启动 Lync Server 2013 前端服务器时启动其他限制机制。</span><span class="sxs-lookup"><span data-stu-id="e02f9-163">There is an additional throttling mechanism in a Lync Server 2013 Front End Server that starts if the server processing time is high.</span></span> <span data-ttu-id="e02f9-164">仅当对 SQL Server 的延迟较高时，才会启用 DBStore 延迟限制。</span><span class="sxs-lookup"><span data-stu-id="e02f9-164">The DBStore latency throttling is only enabled if the latency to the SQL Server is high.</span></span> <span data-ttu-id="e02f9-165">启用此限制的一个示例是，如果前端服务器是 CPU 界限的。</span><span class="sxs-lookup"><span data-stu-id="e02f9-165">One example in which such throttling is enabled is if the front-end server is CPU-bound.</span></span>

<span data-ttu-id="e02f9-166">如果服务器上的平均处理时间 **（LC：针对传入邮件的\\"LC： Sip-Load Management sip-000 –平均保留时间"）** 超过6秒，则服务器将进入限制模式，并只为用户提供每个客户端连接一个未完成的事务。</span><span class="sxs-lookup"><span data-stu-id="e02f9-166">If the average processing time **(LC:SIP-07-Load Management\\SIP-000-Average Holding Time For Incoming Messages)** on the server exceeds six seconds, then the server goes into throttling mode and only gives users one outstanding transaction per client connection.</span></span> <span data-ttu-id="e02f9-167">在处理时间降到3秒后，服务器将断开限制模式，并为用户提供每个客户端连接20个未完成的事务。</span><span class="sxs-lookup"><span data-stu-id="e02f9-167">Once the processing time drops to three seconds, then the server drops out of throttling mode and gives users up to 20 outstanding transactions per client connection.</span></span> <span data-ttu-id="e02f9-168">只要特定连接上的事务数超过上述阈值，该连接将被标记为 "以流方式控制"。</span><span class="sxs-lookup"><span data-stu-id="e02f9-168">Whenever the number of transactions on a specific connection exceeds the threshold above, the connection is marked as flow controlled.</span></span> <span data-ttu-id="e02f9-169">结果是服务器不会在其上发布任何接收，而**LC： SIP-01 对等\\流控制的连接**计数器将递增。</span><span class="sxs-lookup"><span data-stu-id="e02f9-169">The result is the server does not post any receives on it, and the **LC:SIP-01-Peers\\Flow Controlled Connections** counter is incremented.</span></span> <span data-ttu-id="e02f9-170">如果连接在受流控制的状态中保持一分钟以上，则服务器将关闭该连接。</span><span class="sxs-lookup"><span data-stu-id="e02f9-170">If a connection stays in a flow-controlled state for more than one minute, then the server closes it.</span></span> <span data-ttu-id="e02f9-171">它会以延迟的方法执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e02f9-171">It does so lazily.</span></span> <span data-ttu-id="e02f9-172">如果有机会检查连接，它将确定它是否被限制为太长，如果超过一分钟，则关闭该连接。</span><span class="sxs-lookup"><span data-stu-id="e02f9-172">When it has an opportunity to check the connection, it determines whether it was throttled for too long and closes it if it has more than one minute.</span></span>

<span data-ttu-id="e02f9-173">这些是两种限制机制，并且有一个性能计数器，用于汇总服务器执行的操作（如果有）（如果有）限制。</span><span class="sxs-lookup"><span data-stu-id="e02f9-173">These are the two throttling mechanisms and there is one performance counter that summarizes what, if any, throttling the server is performing.</span></span>

<span data-ttu-id="e02f9-174">**LC： SIP-04-响应\\SIP-053-本地503响应数/秒**</span><span class="sxs-lookup"><span data-stu-id="e02f9-174">**LC:SIP-04-Responses\\SIP-053-Local 503 Responses/sec**</span></span>

  - <span data-ttu-id="e02f9-175">上一个计数器中的 "Local" 一词指的是本地生成的响应。</span><span class="sxs-lookup"><span data-stu-id="e02f9-175">The term "Local" in the previous counter refers to locally generated responses.</span></span>

  - <span data-ttu-id="e02f9-176">503代码对应于服务器不可用，您不应在正常服务器上看到任何503代码。</span><span class="sxs-lookup"><span data-stu-id="e02f9-176">The 503 code corresponds to server unavailable—where you should not see any 503 codes on a healthy server.</span></span> <span data-ttu-id="e02f9-177">在服务器刚联机后的一段时间内，您可能会看到一些503代码。</span><span class="sxs-lookup"><span data-stu-id="e02f9-177">During the period after a server is just brought online, you may see some 503 codes.</span></span> <span data-ttu-id="e02f9-178">当所有用户重新登录并返回到稳定状态时，不应再添加503个代码。</span><span class="sxs-lookup"><span data-stu-id="e02f9-178">When all of the users sign back in and the server returns to a stable state, there should no additional 503 codes.</span></span>

<span data-ttu-id="e02f9-179">**LC： SIP-04-响应\\SIP-074-本地504响应数/秒**</span><span class="sxs-lookup"><span data-stu-id="e02f9-179">**LC:SIP-04-Responses\\SIP-074-Local 504 Responses/sec**</span></span>

<span data-ttu-id="e02f9-180">此性能计数器指示其他服务器的连接问题，它可能指示连接失败或连接延迟。</span><span class="sxs-lookup"><span data-stu-id="e02f9-180">This performance counter indicates connectivity issues with other servers and it can indicate failures to connect or delays in connecting.</span></span> <span data-ttu-id="e02f9-181">如果您看到504错误，则应检查以下性能计数器。</span><span class="sxs-lookup"><span data-stu-id="e02f9-181">If you are seeing 504 errors then the following performance counter should be checked.</span></span>

<span data-ttu-id="e02f9-182">**LC： SIP-01-对\\等 sip-017-发送未完成**</span><span class="sxs-lookup"><span data-stu-id="e02f9-182">**LC:SIP-01-Peers\\SIP-017-Sends Outstanding**</span></span>

<span data-ttu-id="e02f9-183">此计数器指示传出排队的请求和响应的数量。</span><span class="sxs-lookup"><span data-stu-id="e02f9-183">This counter indicates the number of outgoing queued requests and responses.</span></span> <span data-ttu-id="e02f9-184">如果此计数器较高，则问题很可能不在本地服务器上。</span><span class="sxs-lookup"><span data-stu-id="e02f9-184">If this counter is high then the issue is most likely not on the local server.</span></span> <span data-ttu-id="e02f9-185">请注意，如果存在网络延迟问题，此计数器可能很高。</span><span class="sxs-lookup"><span data-stu-id="e02f9-185">Note that this counter can be high if there are network latency issues.</span></span> <span data-ttu-id="e02f9-186">它还可能指示本地网络适配器存在问题，但更可能是由远程服务器上的问题导致的。</span><span class="sxs-lookup"><span data-stu-id="e02f9-186">It could also indicate issues with the local network adapter, but is more likely caused by an issue on a remote server.</span></span> <span data-ttu-id="e02f9-187">当要与之进行通信的池超载时，此计数器很可能在控制器服务器上是很高的。</span><span class="sxs-lookup"><span data-stu-id="e02f9-187">This counter would most likely be high on a Director server when the pool it is trying to communicate with is overloaded.</span></span> <span data-ttu-id="e02f9-188">此计数器的关键是查看实例，而不仅仅是总数。</span><span class="sxs-lookup"><span data-stu-id="e02f9-188">The key with this counter is to look at the instances, not just the total.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

