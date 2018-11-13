---
title: 规划业务 Server 为统计信息管理器中的 Skype
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 5/23/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 摘要： 阅读本主题可为 Skype 业务服务器了解有关统计信息管理器。
ms.openlocfilehash: b843cf44edf0c566a1c0a8a99a5ba9380d41c306
ms.sourcegitcommit: 8536a34cb13d40b30f84d95e6df10542ef85c36d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2018
ms.locfileid: "26292974"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="040bb-103">规划业务 Server 为统计信息管理器中的 Skype</span><span class="sxs-lookup"><span data-stu-id="040bb-103">Plan for Statistics Manager for Skype for Business Server</span></span>

<span data-ttu-id="040bb-104">**摘要：** 阅读此主题以业务服务器的 Skype 了解有关统计信息管理器。</span><span class="sxs-lookup"><span data-stu-id="040bb-104">**Summary:** Read this topic to learn about Statistics Manager for Skype for Business Server.</span></span>

 <span data-ttu-id="040bb-105">适用于业务服务器 Skype 的统计信息管理器是一个强大的工具，允许您查看 Skype 的实时业务服务器运行状况和性能数据。</span><span class="sxs-lookup"><span data-stu-id="040bb-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="040bb-106">可以跨服务器数百每隔几秒钟轮询性能数据，并立即统计信息管理器网站上查看结果。</span><span class="sxs-lookup"><span data-stu-id="040bb-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>

<span data-ttu-id="040bb-107">统计信息管理器可用于确定持续的性能问题，与您的环境中查看计划更改的结果，跟踪的中断，分辨率和更多。</span><span class="sxs-lookup"><span data-stu-id="040bb-107">You can use Statistics Manager to identify ongoing performance issues, view the results of a planned change to your environment, track resolution of outages, and much more.</span></span> <span data-ttu-id="040bb-108">现成，统计信息管理器中使用键运行状况指示器 (KHI) 阈值配置，可以对其进行自定义，以满足您的部署唯一需求。</span><span class="sxs-lookup"><span data-stu-id="040bb-108">Out of the box, Statistics Manager is configured with Key Health Indicator (KHI) thresholds, and can be customized to suit your deployment's unique needs.</span></span>

<span data-ttu-id="040bb-109">您可以在本地部署中的单个服务器承载的所有服务器端统计信息管理器组件部署统计信息管理器。</span><span class="sxs-lookup"><span data-stu-id="040bb-109">You can deploy Statistics Manager in an on-premises deployment in which a single server hosts all of the server-side Statistics Manager components.</span></span> <span data-ttu-id="040bb-110">有关部署统计信息管理器的详细信息，请参阅[适用于业务服务器 Skype 部署统计信息管理器](deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="040bb-110">For more information about deploying Statistics Manager, see [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span> <span data-ttu-id="040bb-111">如果您已有现有部署的统计信息管理器中，但尚未升级到版本 2.0，请参阅[What's new in 版本 2.0](plan.md#BKMK_WhatsNew)和[Skype 业务服务器的升级统计信息管理器](upgrade.md)。</span><span class="sxs-lookup"><span data-stu-id="040bb-111">If you already have an existing deployment of Statistics Manager, but you have not yet upgraded to Release 2.0, see [What's new in Release 2.0](plan.md#BKMK_WhatsNew) and [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

<span data-ttu-id="040bb-112">本主题包括以下部分：</span><span class="sxs-lookup"><span data-stu-id="040bb-112">This topic contains the following sections:</span></span>

- [<span data-ttu-id="040bb-113">特性和功能</span><span class="sxs-lookup"><span data-stu-id="040bb-113">Features and capabilities</span></span>](plan.md#BKMK_Features)

- [<span data-ttu-id="040bb-114">What's new in 版本 2.0</span><span class="sxs-lookup"><span data-stu-id="040bb-114">What's new in Release 2.0</span></span>](plan.md#BKMK_WhatsNew)

- [<span data-ttu-id="040bb-115">组件</span><span class="sxs-lookup"><span data-stu-id="040bb-115">Components</span></span>](plan.md#BKMK_Components)

- [<span data-ttu-id="040bb-116">在本地部署</span><span class="sxs-lookup"><span data-stu-id="040bb-116">On-premises deployment</span></span>](plan.md#BKMK_DeploymentOptions)

- [<span data-ttu-id="040bb-117">要求</span><span class="sxs-lookup"><span data-stu-id="040bb-117">Requirements</span></span>](plan.md#BKMK_Requirements)

- [<span data-ttu-id="040bb-118">安全注意事项</span><span class="sxs-lookup"><span data-stu-id="040bb-118">Security considerations</span></span>](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a><span data-ttu-id="040bb-119">特性和功能</span><span class="sxs-lookup"><span data-stu-id="040bb-119">Features and capabilities</span></span>
<span data-ttu-id="040bb-120"><a name="BKMK_Features"> </a></span><span class="sxs-lookup"><span data-stu-id="040bb-120"></span></span>

<span data-ttu-id="040bb-121">统计信息管理器，您可以：</span><span class="sxs-lookup"><span data-stu-id="040bb-121">Statistics Manager allows you to:</span></span>

- <span data-ttu-id="040bb-122">实时查看所有服务器的原始的数据。</span><span class="sxs-lookup"><span data-stu-id="040bb-122">View raw data for all servers in real time.</span></span> <span data-ttu-id="040bb-123">（数据取样速率非常高和小于一秒内发送到网站。）</span><span class="sxs-lookup"><span data-stu-id="040bb-123">(Data is sampled at a very high rate and sent to the website in less than one second.)</span></span>

- <span data-ttu-id="040bb-124">为特定的角色; 聚合的视图数据例如，前端服务器、 中介服务器、 边缘服务器，等。</span><span class="sxs-lookup"><span data-stu-id="040bb-124">View data that is aggregated for a specific role; for example, Front End Server, Mediation Server, Edge Server, and so on.</span></span>

- <span data-ttu-id="040bb-125">查看特定网站、 网站内的特定池和池中然后特定服务器的数据向下钻取。</span><span class="sxs-lookup"><span data-stu-id="040bb-125">Drill down to view data for specific sites, specific pools within the site, and then specific servers within the pool.</span></span>

- <span data-ttu-id="040bb-126">创建自定义图表，以便选择计数器显示默认情况下。</span><span class="sxs-lookup"><span data-stu-id="040bb-126">Create custom charts so that chosen counters are shown by default.</span></span>

- <span data-ttu-id="040bb-127">缩放和平移上两个 x 轴和 y 轴或仅在 x 轴上。</span><span class="sxs-lookup"><span data-stu-id="040bb-127">Zoom and pan on both the x- and y- axes or on the x-axis only.</span></span>

- <span data-ttu-id="040bb-128">筛选数据的时间使用日期范围或点。</span><span class="sxs-lookup"><span data-stu-id="040bb-128">Use date ranges or points in time to filter data.</span></span>

- <span data-ttu-id="040bb-129">查看服务器性能基于建立关键运行状况指示器 (KHIs)。</span><span class="sxs-lookup"><span data-stu-id="040bb-129">View server performance based on established key health indicators (KHIs).</span></span> <span data-ttu-id="040bb-130">KHIs 表示取值范围定义为正常的性能计数器的集合。</span><span class="sxs-lookup"><span data-stu-id="040bb-130">KHIs represent a collection of performance counters with a defined healthy range.</span></span>

- <span data-ttu-id="040bb-131">查看每个计数器的详细的指标。</span><span class="sxs-lookup"><span data-stu-id="040bb-131">View detailed metrics for each counter.</span></span>

- <span data-ttu-id="040bb-132">比较跨多个选中或服务器的数据。</span><span class="sxs-lookup"><span data-stu-id="040bb-132">Compare data across multiple populations or servers.</span></span>

- <span data-ttu-id="040bb-133">查看延迟计数器报告来标识不当前数据报告到仪表板服务的代理。</span><span class="sxs-lookup"><span data-stu-id="040bb-133">View latent counter reports to identify agents that are not reporting current data to the dashboard service.</span></span>

- <span data-ttu-id="040bb-134">保存到文件的图表数据的特定实例。</span><span class="sxs-lookup"><span data-stu-id="040bb-134">Save a particular instance of chart data to a file.</span></span>

- <span data-ttu-id="040bb-135">实时，包括更新视图 KHIs。</span><span class="sxs-lookup"><span data-stu-id="040bb-135">View KHIs in real time, including updates.</span></span> <span data-ttu-id="040bb-136">如果已启用的历史记录视图，显示仅新失败。</span><span class="sxs-lookup"><span data-stu-id="040bb-136">If the history view is enabled, only new failures are shown.</span></span>

  - <span data-ttu-id="040bb-137">一次查看所有 KHIs</span><span class="sxs-lookup"><span data-stu-id="040bb-137">View all KHIs at one time</span></span>

  - <span data-ttu-id="040bb-138">查看 KHIs 服务器 （横向视图）</span><span class="sxs-lookup"><span data-stu-id="040bb-138">View KHIs by server (Landscape view)</span></span>

  - <span data-ttu-id="040bb-139">视图 KHI 定义</span><span class="sxs-lookup"><span data-stu-id="040bb-139">View KHI definitions</span></span>

## <a name="whats-new-in-release-20"></a><span data-ttu-id="040bb-140">What's new in 版本 2.0</span><span class="sxs-lookup"><span data-stu-id="040bb-140">What's new in Release 2.0</span></span>
<span data-ttu-id="040bb-141"><a name="BKMK_WhatsNew"> </a></span><span class="sxs-lookup"><span data-stu-id="040bb-141"></span></span>

<span data-ttu-id="040bb-142">以下介绍 what's new in 版本 2.0。</span><span class="sxs-lookup"><span data-stu-id="040bb-142">The following describes what's new in Release 2.0.</span></span> <span data-ttu-id="040bb-143">如果您拥有现有部署的统计信息管理器中，并且尚未升级，请参阅[适用于业务服务器 Skype 升级统计信息管理器](upgrade.md)。</span><span class="sxs-lookup"><span data-stu-id="040bb-143">If you have an existing deployment of Statistics Manager and you've not yet upgraded, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

- <span data-ttu-id="040bb-144">已为边缘媒体、 结构运行状况、 池故障转移和注册方案添加了方案视图。</span><span class="sxs-lookup"><span data-stu-id="040bb-144">Scenario views have been added for Edge Media, Fabric Health, Pool Failover and Registration scenarios.</span></span>

- <span data-ttu-id="040bb-145">许多新计数器已添加为 SQL 服务器和多个 Skype 的业务使用率计数器，等等。</span><span class="sxs-lookup"><span data-stu-id="040bb-145">Many new counters have been added for SQL servers, more Skype for Business usage counters, and so on.</span></span>

- <span data-ttu-id="040bb-146">观察程序节点集成的统计信息管理器代理-如果观察程序节点上安装代理将报告综合事务统计信息计数器为返回到统计信息管理器。</span><span class="sxs-lookup"><span data-stu-id="040bb-146">Watcher node integration for the Statistics Manager Agent - if the Agent is installed on a watcher node, it will report synthetic transaction statistics as counters back to Statistics Manager.</span></span>

- <span data-ttu-id="040bb-147">大量的可靠性和性能改进。</span><span class="sxs-lookup"><span data-stu-id="040bb-147">Numerous reliability and performance improvements.</span></span>

<span data-ttu-id="040bb-148">若要验证您运行的统计信息管理器网站的版本：</span><span class="sxs-lookup"><span data-stu-id="040bb-148">To verify the version of the Statistics Manager Website you are running:</span></span>

- <span data-ttu-id="040bb-149">在文件资源管理器，打开 （默认目录） 的业务服务器 StatsMan WebSite\bin C:\Program Files\Skype</span><span class="sxs-lookup"><span data-stu-id="040bb-149">In File Explorer, open (default directory) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span></span>

- <span data-ttu-id="040bb-150">右键单击 StatsManHubWebSite.dll 并查看其属性</span><span class="sxs-lookup"><span data-stu-id="040bb-150">Right click on StatsManHubWebSite.dll and view its properties</span></span>

- <span data-ttu-id="040bb-151">产品版本将在“说明”详细信息中显示。</span><span class="sxs-lookup"><span data-stu-id="040bb-151">The product version will be shown in the Description details.</span></span>

## <a name="components"></a><span data-ttu-id="040bb-152">组件</span><span class="sxs-lookup"><span data-stu-id="040bb-152">Components</span></span>
<span data-ttu-id="040bb-153"><a name="BKMK_Components"> </a></span><span class="sxs-lookup"><span data-stu-id="040bb-153"></span></span>

<span data-ttu-id="040bb-154">统计信息管理器包括以下组件：</span><span class="sxs-lookup"><span data-stu-id="040bb-154">Statistics Manager consists of the following components:</span></span>

- <span data-ttu-id="040bb-155">**代理。**</span><span class="sxs-lookup"><span data-stu-id="040bb-155">**Agent.**</span></span> <span data-ttu-id="040bb-156">每个监控服务器运行轻型代理。</span><span class="sxs-lookup"><span data-stu-id="040bb-156">A lightweight agent that runs on each monitored server.</span></span> <span data-ttu-id="040bb-157">代理允许具有本地聚合的性能计数器的可配置率太高轮询。</span><span class="sxs-lookup"><span data-stu-id="040bb-157">The Agent allows configurable high rate polling of performance counters with local aggregation.</span></span>

- <span data-ttu-id="040bb-158">**侦听器。**</span><span class="sxs-lookup"><span data-stu-id="040bb-158">**Listener.**</span></span> <span data-ttu-id="040bb-159">服务器端 API 的从所有代理接收数据，并选中跨汇总数据。</span><span class="sxs-lookup"><span data-stu-id="040bb-159">The server side API that receives data from all Agents, and aggregates data across populations.</span></span>

- <span data-ttu-id="040bb-160">**集线器。**</span><span class="sxs-lookup"><span data-stu-id="040bb-160">**Hub.**</span></span> <span data-ttu-id="040bb-161">客户端 API 系统上的 web 服务器，请运行并向客户端连接通过网站提供实时数据更新充当。</span><span class="sxs-lookup"><span data-stu-id="040bb-161">Serves as the client API for the system, runs on the web server(s), and provides real-time data updates to clients connected via the website.</span></span> <span data-ttu-id="040bb-162">（集线器会自动安装网站 msi 的一部分。）</span><span class="sxs-lookup"><span data-stu-id="040bb-162">(The Hub is automatically installed as part of the Website msi.)</span></span>

- <span data-ttu-id="040bb-163">**网站。**</span><span class="sxs-lookup"><span data-stu-id="040bb-163">**Website.**</span></span> <span data-ttu-id="040bb-164">用户界面的组合系统中可用的所有功能。</span><span class="sxs-lookup"><span data-stu-id="040bb-164">A user interface that pulls together all the features available in the system.</span></span>

<span data-ttu-id="040bb-165">此外，统计信息管理器要求**Redis**，用于在内存缓存的开放源代码数据结构服务器。</span><span class="sxs-lookup"><span data-stu-id="040bb-165">In addition, Statistics Manager requires **Redis**, an open-sourced data structure server for in-memory caching.</span></span> <span data-ttu-id="040bb-166">有关下载 Redis 的详细信息，请参阅[部署统计信息管理器](deploy.md#BKMK_Deploy)。</span><span class="sxs-lookup"><span data-stu-id="040bb-166">For more information about downloading Redis, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy) .</span></span>

## <a name="on-premises-deployment"></a><span data-ttu-id="040bb-167">在本地部署</span><span class="sxs-lookup"><span data-stu-id="040bb-167">On-premises deployment</span></span>
<span data-ttu-id="040bb-168"><a name="BKMK_DeploymentOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="040bb-168"></span></span>

<span data-ttu-id="040bb-169">在本地部署中，一台服务器承载的所有服务器端统计信息管理器组件。</span><span class="sxs-lookup"><span data-stu-id="040bb-169">In an on-premises deployment, a single server hosts all of the server-side Statistics Manager components.</span></span>

<span data-ttu-id="040bb-170">下图显示在本地部署中，在其中统计信息管理器网站、 集线器、 侦听器和 Redis 缓存系统承载一台计算机。</span><span class="sxs-lookup"><span data-stu-id="040bb-170">The following diagram shows an on-premises deployment, in which the Statistics Manager Website, Hub, Listener, and Redis caching system are hosted on a single machine.</span></span> <span data-ttu-id="040bb-171">统计信息管理器所监控业务服务器，其中每个具有一个代理将数据传输到侦听器的三个的 Skype。</span><span class="sxs-lookup"><span data-stu-id="040bb-171">Statistics Manager is monitoring three Skype for Business servers, each of which have a single Agent transmitting data to the Listener.</span></span> <span data-ttu-id="040bb-172">用户连接到单个网站以查看聚合由统计信息管理器中的所有数据：</span><span class="sxs-lookup"><span data-stu-id="040bb-172">Users connect to a single Website to view all data aggregated by Statistics Manager:</span></span>

![统计管理器本地部署](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a><span data-ttu-id="040bb-174">要求</span><span class="sxs-lookup"><span data-stu-id="040bb-174">Requirements</span></span>
<span data-ttu-id="040bb-175"><a name="BKMK_Requirements"> </a></span><span class="sxs-lookup"><span data-stu-id="040bb-175"></span></span>

<span data-ttu-id="040bb-176">您将需要部署统计信息管理器之前，请考虑以下软件、 网络和硬件要求。</span><span class="sxs-lookup"><span data-stu-id="040bb-176">You will need to consider the following software, networking, and hardware requirements before you deploy Statistics Manager.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="040bb-177">软件要求</span><span class="sxs-lookup"><span data-stu-id="040bb-177">Software requirements</span></span>

- <span data-ttu-id="040bb-178">Windows Server 2016 和 2019</span><span class="sxs-lookup"><span data-stu-id="040bb-178">Windows Server 2016 and 2019</span></span>

- <span data-ttu-id="040bb-179">IIS （自动安装）</span><span class="sxs-lookup"><span data-stu-id="040bb-179">IIS (automatically installed)</span></span>

- <span data-ttu-id="040bb-180">Redis</span><span class="sxs-lookup"><span data-stu-id="040bb-180">Redis</span></span>

- <span data-ttu-id="040bb-181">（自动安装） 的统计信息管理器服务</span><span class="sxs-lookup"><span data-stu-id="040bb-181">Statistics Manager services (automatically installed)</span></span>

- <span data-ttu-id="040bb-182">PSExec-需要执行远程代理部署</span><span class="sxs-lookup"><span data-stu-id="040bb-182">PSExec - Required to do remote agent deployment</span></span>

- <span data-ttu-id="040bb-183">代理和服务器端组件所需的.NET 4.5 （附带 2012 R2）-</span><span class="sxs-lookup"><span data-stu-id="040bb-183">.NET 4.5 (included with 2012 R2) - Required for agents and server-side components</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="040bb-184">网络要求</span><span class="sxs-lookup"><span data-stu-id="040bb-184">Networking requirements</span></span>


|<span data-ttu-id="040bb-185">**承载服务器**</span><span class="sxs-lookup"><span data-stu-id="040bb-185">**Hosting server**</span></span>|<span data-ttu-id="040bb-186">**代理**</span><span class="sxs-lookup"><span data-stu-id="040bb-186">**Agents**</span></span>|<span data-ttu-id="040bb-187">**侦听器**</span><span class="sxs-lookup"><span data-stu-id="040bb-187">**Listener**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="040bb-188">全双工最低千兆位网络。</span><span class="sxs-lookup"><span data-stu-id="040bb-188">Minimum gigabit full duplex networking.</span></span>  <br/> |<span data-ttu-id="040bb-189">出站 TCP 端口 8443 （可自定义端口号） 与侦听器进行通信。</span><span class="sxs-lookup"><span data-stu-id="040bb-189">Outbound TCP port 8443 (customizable port number) to communicate with the Listener.</span></span>  <br/> |<span data-ttu-id="040bb-190">侦听器端口必须在所有服务器上相同。</span><span class="sxs-lookup"><span data-stu-id="040bb-190">The Listener port must be the same on all servers.</span></span>  <br/> |
|<span data-ttu-id="040bb-191">入站 TCP 端口 80 或 443 打开来承载网站。</span><span class="sxs-lookup"><span data-stu-id="040bb-191">Inbound TCP port 80 or 443 open to host the website.</span></span>  <br/> |||
|<span data-ttu-id="040bb-192">入站代理与其通信的 TCP 端口 8443 （可自定义端口号）。</span><span class="sxs-lookup"><span data-stu-id="040bb-192">Inbound TCP port 8443 (customizable port number) for the agents to communicate with it.</span></span>  <br/> |||

<span data-ttu-id="040bb-193">安装过程中，将自动创建的侦听器和网站的防火墙端口。</span><span class="sxs-lookup"><span data-stu-id="040bb-193">During installation, firewall ports for the Listener and the Website are automatically created.</span></span> <span data-ttu-id="040bb-194">针对代理，安装假定，默认情况下允许出站 TCP 连接。</span><span class="sxs-lookup"><span data-stu-id="040bb-194">For the Agents, the installation assumes that outbound TCP connections are allowed by default.</span></span>

### <a name="hardware-requirements"></a><span data-ttu-id="040bb-195">硬件要求</span><span class="sxs-lookup"><span data-stu-id="040bb-195">Hardware requirements</span></span>

<span data-ttu-id="040bb-196">在本地部署中，在其中一台服务器承载的所有服务器端统计信息管理器组件的服务器具有 16 GB 的 RAM 和 4 应能够支持大约 150 示例每秒平均 CPU 的。</span><span class="sxs-lookup"><span data-stu-id="040bb-196">In an on-premises deployment, in which a single server hosts all of the server-side Statistics Manager components, a server with 16 GB of RAM and 4 CPU's should be able to support about 150 samples per second on average.</span></span> <span data-ttu-id="040bb-197">若要确定可以支持多少个计数器/代理，请使用以下计算：</span><span class="sxs-lookup"><span data-stu-id="040bb-197">To determine how many counters/agents you can support, use the following calculation:</span></span>

<span data-ttu-id="040bb-198">100 服务器\*80 计数器\*每分钟每个代理 / 60 秒 1 示例 = ~ 每秒 133 示例。</span><span class="sxs-lookup"><span data-stu-id="040bb-198">100 servers \*80 counters \* 1 sample per minute from each agent / 60 seconds = ~ 133 samples per second.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="040bb-199">安全注意事项</span><span class="sxs-lookup"><span data-stu-id="040bb-199">Security considerations</span></span>
<span data-ttu-id="040bb-200"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="040bb-200"></span></span>

<span data-ttu-id="040bb-201">服务器之间的所有通信进行都加密。</span><span class="sxs-lookup"><span data-stu-id="040bb-201">All traffic between servers is encrypted.</span></span>

- <span data-ttu-id="040bb-202">加密的 HTTPS 通信将会通过端口 8443 （默认） 从代理发送到侦听器服务器。</span><span class="sxs-lookup"><span data-stu-id="040bb-202">Encrypted HTTPS traffic will be sent over port 8443 (by default) from the Agent to the Listener server.</span></span>

- <span data-ttu-id="040bb-203">代理将验证以确保侦听器服务器是预期的收件人的服务器上的 SSL 指纹。</span><span class="sxs-lookup"><span data-stu-id="040bb-203">The Agent will verify the SSL thumbprint on the server to ensure the Listener server is the expected recipient.</span></span> <span data-ttu-id="040bb-204">请注意，代理使用证书指纹验证（而不是链验证）。</span><span class="sxs-lookup"><span data-stu-id="040bb-204">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="040bb-205">由于可能使用自签名证书，因此它不会执行完整证书验证。</span><span class="sxs-lookup"><span data-stu-id="040bb-205">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>

- <span data-ttu-id="040bb-206">代理是满足后侦听器是可信，将其然后由侦听器验证的代理必须提供密码。</span><span class="sxs-lookup"><span data-stu-id="040bb-206">After the Agent is satisfied the Listener is authentic, a password will be presented by the Agent which is then verified by the Listener.</span></span>

- <span data-ttu-id="040bb-207">代理开始通过连接到侦听器传输性能数据。</span><span class="sxs-lookup"><span data-stu-id="040bb-207">The Agent begins transmitting performance data over the connection to the Listener.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="040bb-208">有关详细信息</span><span class="sxs-lookup"><span data-stu-id="040bb-208">For more information</span></span>
<span data-ttu-id="040bb-209"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="040bb-209"></span></span>

<span data-ttu-id="040bb-210">有关详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="040bb-210">For more information, see the following:</span></span>

- [<span data-ttu-id="040bb-211">为业务 Server 部署的 Skype 的统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="040bb-211">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)

- [<span data-ttu-id="040bb-212">为业务服务器升级的 Skype 的统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="040bb-212">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)

- [<span data-ttu-id="040bb-213">解决的 Skype 的统计信息管理器的企业服务器</span><span class="sxs-lookup"><span data-stu-id="040bb-213">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)

- [<span data-ttu-id="040bb-214">Skype for Business Server 统计信息管理器博客</span><span class="sxs-lookup"><span data-stu-id="040bb-214">Skype for Business Server Statistics Manager blog</span></span>](https://blogs.technet.microsoft.com/dodeitte/2015/10/24/skype-for-business-server-real-time-statistics-manager)


