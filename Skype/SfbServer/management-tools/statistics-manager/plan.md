---
title: 规划 Skype for Business Server 的统计信息管理器
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
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 摘要：阅读本主题以了解 Skype for Business Server 的统计信息管理器。
ms.openlocfilehash: cdc536abcbd1bd98c4a3c7ce974247a716865582
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821822"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="f37a4-103">规划 Skype for Business Server 的统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="f37a4-103">Plan for Statistics Manager for Skype for Business Server</span></span>

<span data-ttu-id="f37a4-104">**摘要：** 阅读本主题以了解 Skype for Business Server 统计信息管理器。</span><span class="sxs-lookup"><span data-stu-id="f37a4-104">**Summary:** Read this topic to learn about Statistics Manager for Skype for Business Server.</span></span>

 <span data-ttu-id="f37a4-105">Skype for Business Server 统计信息管理器是一个强大的工具，允许你实时查看 Skype for Business Server 运行状况和性能数据。</span><span class="sxs-lookup"><span data-stu-id="f37a4-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="f37a4-106">您可以每隔几秒钟轮询数百台服务器的性能数据，并立即在统计信息管理器网站上查看结果。</span><span class="sxs-lookup"><span data-stu-id="f37a4-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>

<span data-ttu-id="f37a4-107">您可以使用统计信息管理器来识别持续的性能问题、查看环境计划更改的结果、跟踪中断的解决情况等。</span><span class="sxs-lookup"><span data-stu-id="f37a4-107">You can use Statistics Manager to identify ongoing performance issues, view the results of a planned change to your environment, track resolution of outages, and much more.</span></span> <span data-ttu-id="f37a4-108">统计信息管理器开箱即用关键运行状况指示器 (KHI) 阈值进行配置，并可以自定义以满足部署的独特需求。</span><span class="sxs-lookup"><span data-stu-id="f37a4-108">Out of the box, Statistics Manager is configured with Key Health Indicator (KHI) thresholds, and can be customized to suit your deployment's unique needs.</span></span>

<span data-ttu-id="f37a4-109">您可以在本地部署中部署统计信息管理器，其中单个服务器承载所有服务器端统计信息管理器组件。</span><span class="sxs-lookup"><span data-stu-id="f37a4-109">You can deploy Statistics Manager in an on-premises deployment in which a single server hosts all of the server-side Statistics Manager components.</span></span> <span data-ttu-id="f37a4-110">有关部署统计信息管理器的信息，请参阅 [部署 Skype for Business Server 的统计信息管理器](deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="f37a4-110">For more information about deploying Statistics Manager, see [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span> <span data-ttu-id="f37a4-111">如果你已拥有统计信息管理器的现有部署，但尚未升级到 2.0 版，请参阅 [2.0](plan.md#BKMK_WhatsNew) 版中的新增功能以及升级 Skype for [Business Server](upgrade.md)的统计信息管理器。</span><span class="sxs-lookup"><span data-stu-id="f37a4-111">If you already have an existing deployment of Statistics Manager, but you have not yet upgraded to Release 2.0, see [What's new in Release 2.0](plan.md#BKMK_WhatsNew) and [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

<span data-ttu-id="f37a4-112">本主题包含以下各部分：</span><span class="sxs-lookup"><span data-stu-id="f37a4-112">This topic contains the following sections:</span></span>

- [<span data-ttu-id="f37a4-113">特性和功能</span><span class="sxs-lookup"><span data-stu-id="f37a4-113">Features and capabilities</span></span>](plan.md#BKMK_Features)

- [<span data-ttu-id="f37a4-114">2.0 版中的新增功能</span><span class="sxs-lookup"><span data-stu-id="f37a4-114">What's new in Release 2.0</span></span>](plan.md#BKMK_WhatsNew)

- [<span data-ttu-id="f37a4-115">组件</span><span class="sxs-lookup"><span data-stu-id="f37a4-115">Components</span></span>](plan.md#BKMK_Components)

- [<span data-ttu-id="f37a4-116">本地部署</span><span class="sxs-lookup"><span data-stu-id="f37a4-116">On-premises deployment</span></span>](plan.md#BKMK_DeploymentOptions)

- [<span data-ttu-id="f37a4-117">要求</span><span class="sxs-lookup"><span data-stu-id="f37a4-117">Requirements</span></span>](plan.md#BKMK_Requirements)

- [<span data-ttu-id="f37a4-118">安全注意事项</span><span class="sxs-lookup"><span data-stu-id="f37a4-118">Security considerations</span></span>](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a><span data-ttu-id="f37a4-119">特性和功能</span><span class="sxs-lookup"><span data-stu-id="f37a4-119">Features and capabilities</span></span>
<span data-ttu-id="f37a4-120"><a name="BKMK_Features"> </a></span><span class="sxs-lookup"><span data-stu-id="f37a4-120"><a name="BKMK_Features"> </a></span></span>

<span data-ttu-id="f37a4-121">统计信息管理器允许你：</span><span class="sxs-lookup"><span data-stu-id="f37a4-121">Statistics Manager allows you to:</span></span>

- <span data-ttu-id="f37a4-122">实时查看所有服务器的原始数据。</span><span class="sxs-lookup"><span data-stu-id="f37a4-122">View raw data for all servers in real time.</span></span> <span data-ttu-id="f37a4-123"> (数据以非常高的速率进行采样，并不到一秒就发送到网站。) </span><span class="sxs-lookup"><span data-stu-id="f37a4-123">(Data is sampled at a very high rate and sent to the website in less than one second.)</span></span>

- <span data-ttu-id="f37a4-124">查看为特定角色聚合的数据;例如，前端服务器、中介服务器、边缘服务器等。</span><span class="sxs-lookup"><span data-stu-id="f37a4-124">View data that is aggregated for a specific role; for example, Front End Server, Mediation Server, Edge Server, and so on.</span></span>

- <span data-ttu-id="f37a4-125">向下钻取以查看特定站点、站点中的特定池以及池中的特定服务器的数据。</span><span class="sxs-lookup"><span data-stu-id="f37a4-125">Drill down to view data for specific sites, specific pools within the site, and then specific servers within the pool.</span></span>

- <span data-ttu-id="f37a4-126">创建自定义图表，以便默认显示所选的计数器。</span><span class="sxs-lookup"><span data-stu-id="f37a4-126">Create custom charts so that chosen counters are shown by default.</span></span>

- <span data-ttu-id="f37a4-127">仅在 x 轴和 y 轴或 x 轴上缩放和平移。</span><span class="sxs-lookup"><span data-stu-id="f37a4-127">Zoom and pan on both the x- and y- axes or on the x-axis only.</span></span>

- <span data-ttu-id="f37a4-128">使用日期范围或时间点筛选数据。</span><span class="sxs-lookup"><span data-stu-id="f37a4-128">Use date ranges or points in time to filter data.</span></span>

- <span data-ttu-id="f37a4-129">根据已建立的关键运行状况指示器和 KHIS (查看) 。</span><span class="sxs-lookup"><span data-stu-id="f37a4-129">View server performance based on established key health indicators (KHIs).</span></span> <span data-ttu-id="f37a4-130">KHIs 表示具有定义的正常范围的性能计数器的集合。</span><span class="sxs-lookup"><span data-stu-id="f37a4-130">KHIs represent a collection of performance counters with a defined healthy range.</span></span>

- <span data-ttu-id="f37a4-131">查看每个计数器的详细指标。</span><span class="sxs-lookup"><span data-stu-id="f37a4-131">View detailed metrics for each counter.</span></span>

- <span data-ttu-id="f37a4-132">跨多个总体或服务器比较数据。</span><span class="sxs-lookup"><span data-stu-id="f37a4-132">Compare data across multiple populations or servers.</span></span>

- <span data-ttu-id="f37a4-133">查看潜在计数器报告，以标识未向仪表板服务报告当前数据的代理。</span><span class="sxs-lookup"><span data-stu-id="f37a4-133">View latent counter reports to identify agents that are not reporting current data to the dashboard service.</span></span>

- <span data-ttu-id="f37a4-134">将图表数据的特定实例保存到文件中。</span><span class="sxs-lookup"><span data-stu-id="f37a4-134">Save a particular instance of chart data to a file.</span></span>

- <span data-ttu-id="f37a4-135">实时查看 KHIS，包括更新。</span><span class="sxs-lookup"><span data-stu-id="f37a4-135">View KHIs in real time, including updates.</span></span> <span data-ttu-id="f37a4-136">如果启用历史记录视图，则只显示新故障。</span><span class="sxs-lookup"><span data-stu-id="f37a4-136">If the history view is enabled, only new failures are shown.</span></span>

  - <span data-ttu-id="f37a4-137">一次查看所有 KHIS</span><span class="sxs-lookup"><span data-stu-id="f37a4-137">View all KHIs at one time</span></span>

  - <span data-ttu-id="f37a4-138">按服务器视图视图 KHIS (横向视图) </span><span class="sxs-lookup"><span data-stu-id="f37a4-138">View KHIs by server (Landscape view)</span></span>

  - <span data-ttu-id="f37a4-139">查看 KHI 定义</span><span class="sxs-lookup"><span data-stu-id="f37a4-139">View KHI definitions</span></span>

## <a name="whats-new-in-release-20"></a><span data-ttu-id="f37a4-140">2.0 版中的新增功能</span><span class="sxs-lookup"><span data-stu-id="f37a4-140">What's new in Release 2.0</span></span>
<span data-ttu-id="f37a4-141"><a name="BKMK_WhatsNew"> </a></span><span class="sxs-lookup"><span data-stu-id="f37a4-141"><a name="BKMK_WhatsNew"> </a></span></span>

<span data-ttu-id="f37a4-142">下面介绍了 2.0 版中的新增功能。</span><span class="sxs-lookup"><span data-stu-id="f37a4-142">The following describes what's new in Release 2.0.</span></span> <span data-ttu-id="f37a4-143">如果你有统计信息管理器的现有部署，并且尚未升级，请参阅 Upgrade Statistics Manager [for Skype for Business Server。](upgrade.md)</span><span class="sxs-lookup"><span data-stu-id="f37a4-143">If you have an existing deployment of Statistics Manager and you've not yet upgraded, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

- <span data-ttu-id="f37a4-144">已针对边缘媒体、Fabric Health、池故障转移和注册方案添加了方案视图。</span><span class="sxs-lookup"><span data-stu-id="f37a4-144">Scenario views have been added for Edge Media, Fabric Health, Pool Failover and Registration scenarios.</span></span>

- <span data-ttu-id="f37a4-145">添加了许多新的计数器，SQL服务器、更多 Skype for Business 使用计数器等。</span><span class="sxs-lookup"><span data-stu-id="f37a4-145">Many new counters have been added for SQL servers, more Skype for Business usage counters, and so on.</span></span>

- <span data-ttu-id="f37a4-146">统计信息管理器代理的观察程序节点集成 - 如果代理安装在观察程序节点上，它将综合事务统计信息作为计数器报告回统计信息管理器。</span><span class="sxs-lookup"><span data-stu-id="f37a4-146">Watcher node integration for the Statistics Manager Agent - if the Agent is installed on a watcher node, it will report synthetic transaction statistics as counters back to Statistics Manager.</span></span>

- <span data-ttu-id="f37a4-147">大量可靠性和性能改进。</span><span class="sxs-lookup"><span data-stu-id="f37a4-147">Numerous reliability and performance improvements.</span></span>

<span data-ttu-id="f37a4-148">要验证统计信息管理器网站的版本，请运行：</span><span class="sxs-lookup"><span data-stu-id="f37a4-148">To verify the version of the Statistics Manager Website you are running:</span></span>

- <span data-ttu-id="f37a4-149">在文件资源管理器中， (C：\Program Files\Skype for Business Server StatsMan WebSite\bin) 默认目录</span><span class="sxs-lookup"><span data-stu-id="f37a4-149">In File Explorer, open (default directory) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span></span>

- <span data-ttu-id="f37a4-150">右键单击StatsManHubWebSite.dll并查看其属性</span><span class="sxs-lookup"><span data-stu-id="f37a4-150">Right click on StatsManHubWebSite.dll and view its properties</span></span>

- <span data-ttu-id="f37a4-151">产品版本将显示在"说明"详细信息中。</span><span class="sxs-lookup"><span data-stu-id="f37a4-151">The product version will be shown in the Description details.</span></span>

## <a name="components"></a><span data-ttu-id="f37a4-152">组件</span><span class="sxs-lookup"><span data-stu-id="f37a4-152">Components</span></span>
<span data-ttu-id="f37a4-153"><a name="BKMK_Components"> </a></span><span class="sxs-lookup"><span data-stu-id="f37a4-153"><a name="BKMK_Components"> </a></span></span>

<span data-ttu-id="f37a4-154">统计信息管理器包含以下组件：</span><span class="sxs-lookup"><span data-stu-id="f37a4-154">Statistics Manager consists of the following components:</span></span>

- <span data-ttu-id="f37a4-155">**代理。**</span><span class="sxs-lookup"><span data-stu-id="f37a4-155">**Agent.**</span></span> <span data-ttu-id="f37a4-156">在每个受监视服务器上运行的轻型代理。</span><span class="sxs-lookup"><span data-stu-id="f37a4-156">A lightweight agent that runs on each monitored server.</span></span> <span data-ttu-id="f37a4-157">代理允许使用本地聚合对性能计数器进行可配置的高速率轮询。</span><span class="sxs-lookup"><span data-stu-id="f37a4-157">The Agent allows configurable high rate polling of performance counters with local aggregation.</span></span>

- <span data-ttu-id="f37a4-158">**侦听器。**</span><span class="sxs-lookup"><span data-stu-id="f37a4-158">**Listener.**</span></span> <span data-ttu-id="f37a4-159">从所有代理接收数据并聚合各总体数据的服务器端 API。</span><span class="sxs-lookup"><span data-stu-id="f37a4-159">The server side API that receives data from all Agents, and aggregates data across populations.</span></span>

- <span data-ttu-id="f37a4-160">**中心。**</span><span class="sxs-lookup"><span data-stu-id="f37a4-160">**Hub.**</span></span> <span data-ttu-id="f37a4-161">充当系统的客户端 API，在 Web 服务器上 () ，并针对通过网站连接的客户端提供实时数据更新。</span><span class="sxs-lookup"><span data-stu-id="f37a4-161">Serves as the client API for the system, runs on the web server(s), and provides real-time data updates to clients connected via the website.</span></span> <span data-ttu-id="f37a4-162"> (作为网站 msi.) 的一部分自动安装中心</span><span class="sxs-lookup"><span data-stu-id="f37a4-162">(The Hub is automatically installed as part of the Website msi.)</span></span>

- <span data-ttu-id="f37a4-163">**网站。**</span><span class="sxs-lookup"><span data-stu-id="f37a4-163">**Website.**</span></span> <span data-ttu-id="f37a4-164">将系统中所有可用功能汇集在一起的用户界面。</span><span class="sxs-lookup"><span data-stu-id="f37a4-164">A user interface that pulls together all the features available in the system.</span></span>

<span data-ttu-id="f37a4-165">此外，统计信息管理器需要 **Redis，** 这是一个用于内存中缓存的开源数据结构服务器。</span><span class="sxs-lookup"><span data-stu-id="f37a4-165">In addition, Statistics Manager requires **Redis**, an open-sourced data structure server for in-memory caching.</span></span> <span data-ttu-id="f37a4-166">有关下载 Redis 的信息，请参阅 [部署统计信息管理器](deploy.md#BKMK_Deploy) 。</span><span class="sxs-lookup"><span data-stu-id="f37a4-166">For more information about downloading Redis, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy) .</span></span>

## <a name="on-premises-deployment"></a><span data-ttu-id="f37a4-167">本地部署</span><span class="sxs-lookup"><span data-stu-id="f37a4-167">On-premises deployment</span></span>
<span data-ttu-id="f37a4-168"><a name="BKMK_DeploymentOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="f37a4-168"><a name="BKMK_DeploymentOptions"> </a></span></span>

<span data-ttu-id="f37a4-169">在本地部署中，单个服务器托管所有服务器端统计信息管理器组件。</span><span class="sxs-lookup"><span data-stu-id="f37a4-169">In an on-premises deployment, a single server hosts all of the server-side Statistics Manager components.</span></span>

<span data-ttu-id="f37a4-170">下图显示了本地部署，其中统计信息管理器网站、中心、侦听器和 Redis 缓存系统托管在一台计算机中。</span><span class="sxs-lookup"><span data-stu-id="f37a4-170">The following diagram shows an on-premises deployment, in which the Statistics Manager Website, Hub, Listener, and Redis caching system are hosted on a single machine.</span></span> <span data-ttu-id="f37a4-171">统计信息管理器监视三台 Skype for Business 服务器，每个服务器都有一个代理将数据传输到侦听器。</span><span class="sxs-lookup"><span data-stu-id="f37a4-171">Statistics Manager is monitoring three Skype for Business servers, each of which have a single Agent transmitting data to the Listener.</span></span> <span data-ttu-id="f37a4-172">用户连接到单个网站以查看统计信息管理器聚合的所有数据：</span><span class="sxs-lookup"><span data-stu-id="f37a4-172">Users connect to a single Website to view all data aggregated by Statistics Manager:</span></span>

![统计数据管理器本地部署](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a><span data-ttu-id="f37a4-174">要求</span><span class="sxs-lookup"><span data-stu-id="f37a4-174">Requirements</span></span>
<span data-ttu-id="f37a4-175"><a name="BKMK_Requirements"> </a></span><span class="sxs-lookup"><span data-stu-id="f37a4-175"><a name="BKMK_Requirements"> </a></span></span>

<span data-ttu-id="f37a4-176">部署统计信息管理器之前，需要考虑以下软件、网络和硬件要求。</span><span class="sxs-lookup"><span data-stu-id="f37a4-176">You will need to consider the following software, networking, and hardware requirements before you deploy Statistics Manager.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="f37a4-177">软件要求</span><span class="sxs-lookup"><span data-stu-id="f37a4-177">Software requirements</span></span>

- <span data-ttu-id="f37a4-178">Windows Server 2016 和 Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="f37a4-178">Windows Server 2016 and 2019</span></span>

- <span data-ttu-id="f37a4-179">IIS (自动安装) </span><span class="sxs-lookup"><span data-stu-id="f37a4-179">IIS (automatically installed)</span></span>

- <span data-ttu-id="f37a4-180">Redis</span><span class="sxs-lookup"><span data-stu-id="f37a4-180">Redis</span></span>

- <span data-ttu-id="f37a4-181">自动安装统计信息 (服务) </span><span class="sxs-lookup"><span data-stu-id="f37a4-181">Statistics Manager services (automatically installed)</span></span>

- <span data-ttu-id="f37a4-182">PSExec - 需要执行远程代理部署</span><span class="sxs-lookup"><span data-stu-id="f37a4-182">PSExec - Required to do remote agent deployment</span></span>

- <span data-ttu-id="f37a4-183">2012 R2 (中包含的 .NET 4.5) - 代理和服务器端组件必需</span><span class="sxs-lookup"><span data-stu-id="f37a4-183">.NET 4.5 (included with 2012 R2) - Required for agents and server-side components</span></span>
- <span data-ttu-id="f37a4-184">下载 [64 位Real-Time Skype for Business Server (统计信息管理器) ](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span><span class="sxs-lookup"><span data-stu-id="f37a4-184">Download the [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="f37a4-185">网络要求</span><span class="sxs-lookup"><span data-stu-id="f37a4-185">Networking requirements</span></span>


|<span data-ttu-id="f37a4-186">**托管服务器**</span><span class="sxs-lookup"><span data-stu-id="f37a4-186">**Hosting server**</span></span>|<span data-ttu-id="f37a4-187">**Agents**</span><span class="sxs-lookup"><span data-stu-id="f37a4-187">**Agents**</span></span>|<span data-ttu-id="f37a4-188">**侦听器**</span><span class="sxs-lookup"><span data-stu-id="f37a4-188">**Listener**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f37a4-189">最小千兆位全双工网络。</span><span class="sxs-lookup"><span data-stu-id="f37a4-189">Minimum gigabit full duplex networking.</span></span>  <br/> |<span data-ttu-id="f37a4-190">出站 TCP 端口 8443 (端口号) 与侦听器通信。</span><span class="sxs-lookup"><span data-stu-id="f37a4-190">Outbound TCP port 8443 (customizable port number) to communicate with the Listener.</span></span>  <br/> |<span data-ttu-id="f37a4-191">侦听器端口必须在所有服务器上都相同。</span><span class="sxs-lookup"><span data-stu-id="f37a4-191">The Listener port must be the same on all servers.</span></span>  <br/> |
|<span data-ttu-id="f37a4-192">入站 TCP 端口 80 或 443 打开以承载网站。</span><span class="sxs-lookup"><span data-stu-id="f37a4-192">Inbound TCP port 80 or 443 open to host the website.</span></span>  <br/> |||
|<span data-ttu-id="f37a4-193">入站 TCP 端口 8443 (代理) 可自定义的端口号。</span><span class="sxs-lookup"><span data-stu-id="f37a4-193">Inbound TCP port 8443 (customizable port number) for the agents to communicate with it.</span></span>  <br/> |||

<span data-ttu-id="f37a4-194">在安装过程中，将自动创建侦听器和网站的防火墙端口。</span><span class="sxs-lookup"><span data-stu-id="f37a4-194">During installation, firewall ports for the Listener and the Website are automatically created.</span></span> <span data-ttu-id="f37a4-195">对于代理，安装假定默认情况下允许出站 TCP 连接。</span><span class="sxs-lookup"><span data-stu-id="f37a4-195">For the Agents, the installation assumes that outbound TCP connections are allowed by default.</span></span>

### <a name="hardware-requirements"></a><span data-ttu-id="f37a4-196">硬件要求</span><span class="sxs-lookup"><span data-stu-id="f37a4-196">Hardware requirements</span></span>

<span data-ttu-id="f37a4-197">在单台服务器托管所有服务器端统计信息管理器组件的本地部署中，具有 16 GB RAM 和 4 个 CPU 的服务器平均每秒应支持大约 150 个样本。</span><span class="sxs-lookup"><span data-stu-id="f37a4-197">In an on-premises deployment, in which a single server hosts all of the server-side Statistics Manager components, a server with 16 GB of RAM and 4 CPU's should be able to support about 150 samples per second on average.</span></span> <span data-ttu-id="f37a4-198">若要确定可以支持的计数器/代理数，请使用以下计算：</span><span class="sxs-lookup"><span data-stu-id="f37a4-198">To determine how many counters/agents you can support, use the following calculation:</span></span>

<span data-ttu-id="f37a4-199">100 台服务器 80 个计数器，每个代理每分钟 1 个样本 \* \* /60 秒 = ~ 133 个样本/秒。</span><span class="sxs-lookup"><span data-stu-id="f37a4-199">100 servers \*80 counters \* 1 sample per minute from each agent / 60 seconds = ~ 133 samples per second.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="f37a4-200">安全考虑事项</span><span class="sxs-lookup"><span data-stu-id="f37a4-200">Security considerations</span></span>
<span data-ttu-id="f37a4-201"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="f37a4-201"><a name="BKMK_Security"> </a></span></span>

<span data-ttu-id="f37a4-202">服务器之间的所有流量都经过加密。</span><span class="sxs-lookup"><span data-stu-id="f37a4-202">All traffic between servers is encrypted.</span></span>

- <span data-ttu-id="f37a4-203">默认情况下，加密的 HTTPS 流量通过端口 8443 (从) 代理发送到侦听器服务器。</span><span class="sxs-lookup"><span data-stu-id="f37a4-203">Encrypted HTTPS traffic will be sent over port 8443 (by default) from the Agent to the Listener server.</span></span>

- <span data-ttu-id="f37a4-204">代理将验证服务器上 SSL 指纹，以确保侦听器服务器是预期的收件人。</span><span class="sxs-lookup"><span data-stu-id="f37a4-204">The Agent will verify the SSL thumbprint on the server to ensure the Listener server is the expected recipient.</span></span> <span data-ttu-id="f37a4-205">请注意，代理使用证书指纹验证 (而不是链验证) 。</span><span class="sxs-lookup"><span data-stu-id="f37a4-205">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="f37a4-206">它将不会执行完整证书验证，因为可以使用自签名证书。</span><span class="sxs-lookup"><span data-stu-id="f37a4-206">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>

- <span data-ttu-id="f37a4-207">在代理得到确认后，侦听器会提供密码，然后由侦听器进行验证。</span><span class="sxs-lookup"><span data-stu-id="f37a4-207">After the Agent is satisfied the Listener is authentic, a password will be presented by the Agent which is then verified by the Listener.</span></span>

- <span data-ttu-id="f37a4-208">代理开始通过与侦听器的连接传输性能数据。</span><span class="sxs-lookup"><span data-stu-id="f37a4-208">The Agent begins transmitting performance data over the connection to the Listener.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="f37a4-209">更多详细信息</span><span class="sxs-lookup"><span data-stu-id="f37a4-209">For more information</span></span>
<span data-ttu-id="f37a4-210"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="f37a4-210"><a name="BKMK_Security"> </a></span></span>

<span data-ttu-id="f37a4-211">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="f37a4-211">For more information, see the following:</span></span>

- [<span data-ttu-id="f37a4-212">部署 Skype for Business Server 的统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="f37a4-212">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)

- [<span data-ttu-id="f37a4-213">更新 Skype for Business Server 的统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="f37a4-213">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)

- [<span data-ttu-id="f37a4-214">对 Skype for Business Server 的统计信息管理器进行故障排除</span><span class="sxs-lookup"><span data-stu-id="f37a4-214">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
