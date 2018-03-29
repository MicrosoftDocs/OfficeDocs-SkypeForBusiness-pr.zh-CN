---
title: 为业务服务器 2015年计划为 Skype 统计信息经理
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
description: 摘要： 请阅读本主题，以学习为 Skype 业务服务器 2015年有关统计数据管理器。
ms.openlocfilehash: 63f064f9a6632250f3cfadddbcbb5fca2120f07b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server-2015"></a><span data-ttu-id="0fbc3-103">为业务服务器 2015年计划为 Skype 统计信息经理</span><span class="sxs-lookup"><span data-stu-id="0fbc3-103">Plan for Statistics Manager for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0fbc3-104">**摘要：**阅读本主题，以学习为 Skype 业务服务器 2015年有关统计数据管理器。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-104">**Summary:** Read this topic to learn about Statistics Manager for Skype for Business Server 2015.</span></span>
  
 <span data-ttu-id="0fbc3-105">Skype 业务服务器的统计信息管理器是一个强大的工具，允许您查看 Skype 实时业务服务器运行状况和性能数据。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="0fbc3-106">可以跨数百个服务器每隔几秒钟轮询性能数据和统计数据管理器网站上可立即查看结果。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>
  
<span data-ttu-id="0fbc3-107">统计管理器用于标识正在进行性能问题，对您的环境中查看计划修改的结果，跟踪解决停机的情况，以及更多。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-107">You can use Statistics Manager to identify ongoing performance issues, view the results of a planned change to your environment, track resolution of outages, and much more.</span></span> <span data-ttu-id="0fbc3-108">开箱即用，统计管理器项健康指标 (KHI) 阈值与配置，并可以进行自定义以满足您的部署的唯一需要。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-108">Out of the box, Statistics Manager is configured with Key Health Indicator (KHI) thresholds, and can be customized to suit your deployment's unique needs.</span></span> 
  
<span data-ttu-id="0fbc3-109">您可以在一台服务器承载的所有服务器端统计管理器组件在内部部署中部署统计数据管理器。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-109">You can deploy Statistics Manager in an on-premises deployment in which a single server hosts all of the server-side Statistics Manager components.</span></span> <span data-ttu-id="0fbc3-110">有关部署管理器统计信息的详细信息，请参阅[部署业务服务器 2015年的 Skype 统计管理](deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-110">For more information about deploying Statistics Manager, see [Deploy Statistics Manager for Skype for Business Server 2015](deploy.md).</span></span> <span data-ttu-id="0fbc3-111">如果您已经有现有部署的统计管理器中，但尚未升级到版本 1.1，请参阅[什么是版本 1.1 版中的新增功能](plan.md#BKMK_WhatsNew)和[业务服务器 2015年的 Skype 的升级统计数据管理器](upgrade.md)。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-111">If you already have an existing deployment of Statistics Manager, but you have not yet upgraded to Release 1.1, see [What's new in Release 1.1](plan.md#BKMK_WhatsNew) and [Upgrade Statistics Manager for Skype for Business Server 2015](upgrade.md).</span></span>
  
<span data-ttu-id="0fbc3-112">本主题包括以下部分：</span><span class="sxs-lookup"><span data-stu-id="0fbc3-112">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="0fbc3-113">特性和功能</span><span class="sxs-lookup"><span data-stu-id="0fbc3-113">Features and capabilities</span></span>](http://technet.microsoft.com/library/1c5110a0-b92a-4656-b42b-3650bdb62b4f.aspx#BKMK_Features)
    
- [<span data-ttu-id="0fbc3-114">什么是版本 1.1 中的新功能</span><span class="sxs-lookup"><span data-stu-id="0fbc3-114">What's new in Release 1.1</span></span>](plan.md#BKMK_WhatsNew)
    
- [<span data-ttu-id="0fbc3-115">组件</span><span class="sxs-lookup"><span data-stu-id="0fbc3-115">Components</span></span>](http://technet.microsoft.com/library/1c5110a0-b92a-4656-b42b-3650bdb62b4f.aspx#BKMK_Components)
    
- [<span data-ttu-id="0fbc3-116">内部部署</span><span class="sxs-lookup"><span data-stu-id="0fbc3-116">On-premises deployment</span></span>](plan.md#BKMK_DeploymentOptions)
    
- [<span data-ttu-id="0fbc3-117">要求</span><span class="sxs-lookup"><span data-stu-id="0fbc3-117">Requirements</span></span>](http://technet.microsoft.com/library/1c5110a0-b92a-4656-b42b-3650bdb62b4f.aspx#BKMK_Requirements)
    
- [<span data-ttu-id="0fbc3-118">安全注意事项</span><span class="sxs-lookup"><span data-stu-id="0fbc3-118">Security considerations</span></span>](plan.md#BKMK_Security)
    
## <a name="features-and-capabilities"></a><span data-ttu-id="0fbc3-119">特性和功能</span><span class="sxs-lookup"><span data-stu-id="0fbc3-119">Features and capabilities</span></span>
<span data-ttu-id="0fbc3-120"><a name="BKMK_Features"> </a></span><span class="sxs-lookup"><span data-stu-id="0fbc3-120"></span></span>

<span data-ttu-id="0fbc3-121">统计信息管理器，您可以：</span><span class="sxs-lookup"><span data-stu-id="0fbc3-121">Statistics Manager allows you to:</span></span>
  
- <span data-ttu-id="0fbc3-122">实时查看原始数据进行的所有服务器。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-122">View raw data for all servers in real time.</span></span> <span data-ttu-id="0fbc3-123">（数据采样率非常高的速率，小于一秒内发送到该网站。）</span><span class="sxs-lookup"><span data-stu-id="0fbc3-123">(Data is sampled at a very high rate and sent to the website in less than one second.)</span></span>
    
- <span data-ttu-id="0fbc3-124">查看数据聚合为一个特定的角色;例如，前端服务器、 中介服务器、 边缘服务器等。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-124">View data that is aggregated for a specific role; for example, Front End Server, Mediation Server, Edge Server, and so on.</span></span>
    
- <span data-ttu-id="0fbc3-125">查看特定的站点，在站点中的特定池，池内的然后特定服务器的数据向下钻取。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-125">Drill down to view data for specific sites, specific pools within the site, and then specific servers within the pool.</span></span>
    
- <span data-ttu-id="0fbc3-126">创建自定义的图表，以便选择默认情况下显示的计数器。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-126">Create custom charts so that chosen counters are shown by default.</span></span>
    
- <span data-ttu-id="0fbc3-127">缩放和平移在这两个 x 轴和 y 轴或 x 轴只上。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-127">Zoom and pan on both the x- and y- axes or on the x-axis only.</span></span>
    
- <span data-ttu-id="0fbc3-128">在筛选数据时使用的日期范围或点。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-128">Use date ranges or points in time to filter data.</span></span> 
    
- <span data-ttu-id="0fbc3-129">查看基于已建立的关键运行状况指标 (KHIs) 的服务器性能。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-129">View server performance based on established key health indicators (KHIs).</span></span> <span data-ttu-id="0fbc3-130">KHIs 表示集合的性能计数器与定义的正常范围。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-130">KHIs represent a collection of performance counters with a defined healthy range.</span></span> 
    
- <span data-ttu-id="0fbc3-131">查看每个计数器的详细的指标。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-131">View detailed metrics for each counter.</span></span>
    
- <span data-ttu-id="0fbc3-132">跨多个群体或服务器数据进行比较。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-132">Compare data across multiple populations or servers.</span></span>
    
- <span data-ttu-id="0fbc3-133">查看潜在的计数器报告弄不到仪表板服务报告当前数据的代理。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-133">View latent counter reports to identify agents that are not reporting current data to the dashboard service.</span></span>
    
- <span data-ttu-id="0fbc3-134">保存到文件的特定实例的图表数据。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-134">Save a particular instance of chart data to a file.</span></span>
    
- <span data-ttu-id="0fbc3-135">实时更新包括查看 KHIs。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-135">View KHIs in real time, including updates.</span></span> <span data-ttu-id="0fbc3-136">如果启用历史记录视图，则将显示只新故障。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-136">If the history view is enabled, only new failures are shown.</span></span>
    
  - <span data-ttu-id="0fbc3-137">一次查看所有 KHIs</span><span class="sxs-lookup"><span data-stu-id="0fbc3-137">View all KHIs at one time</span></span>
    
  - <span data-ttu-id="0fbc3-138">查看 KHIs 服务器 （横向视图）</span><span class="sxs-lookup"><span data-stu-id="0fbc3-138">View KHIs by server (Landscape view)</span></span>
    
  - <span data-ttu-id="0fbc3-139">KHI 视图定义</span><span class="sxs-lookup"><span data-stu-id="0fbc3-139">View KHI definitions</span></span>
    
## <a name="whats-new-in-release-11"></a><span data-ttu-id="0fbc3-140">什么是版本 1.1 中的新功能</span><span class="sxs-lookup"><span data-stu-id="0fbc3-140">What's new in Release 1.1</span></span>
<span data-ttu-id="0fbc3-141"><a name="BKMK_WhatsNew"> </a></span><span class="sxs-lookup"><span data-stu-id="0fbc3-141"></span></span>

<span data-ttu-id="0fbc3-142">下面介绍在版本 1.1 中的新增功能。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-142">The following describes what's new in Release 1.1.</span></span> <span data-ttu-id="0fbc3-143">如果已经部署的统计信息管理器，您还没有升级，请参阅[升级业务服务器 2015年的 Skype 统计管理](upgrade.md)。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-143">If you have an existing deployment of Statistics Manager and you've not yet upgraded, see [Upgrade Statistics Manager for Skype for Business Server 2015](upgrade.md).</span></span>
  
- <span data-ttu-id="0fbc3-144">方案中的视图添加了边缘介质、 结构状况、 池故障转移和登记方案。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-144">Scenario views have been added for Edge Media, Fabric Health, Pool Failover and Registration scenarios.</span></span>
    
- <span data-ttu-id="0fbc3-145">命令行 PerfAgentStorageManager.exe （安装到侦听程序） 现在可以作为 CSV 导出计数器数据。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-145">Command line PerfAgentStorageManager.exe (installed with the Listener) can now export counter data as a CSV.</span></span>
    
- <span data-ttu-id="0fbc3-146">很多新的计数器添加了 SQL 服务器，多个 Windows 结构计数器，更多的业务使用情况计数器，Skype 等等。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-146">Many new counters have been added for SQL servers, more Windows Fabric counters, more Skype for Business usage counters, and so on.</span></span>
    
- <span data-ttu-id="0fbc3-147">观察程序节点集成统计管理器代理-如果观察程序节点上安装了代理将报告综合事务统计信息计数器作为回到统计信息管理器。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-147">Watcher node integration for the Statistics Manager Agent - if the Agent is installed on a watcher node, it will report synthetic transaction statistics as counters back to Statistics Manager.</span></span>
    
- <span data-ttu-id="0fbc3-148">许多的可靠性和性能改进。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-148">Numerous reliability and performance improvements.</span></span>
    
<span data-ttu-id="0fbc3-149">若要验证您运行的统计数据管理器网站版本：</span><span class="sxs-lookup"><span data-stu-id="0fbc3-149">To verify the version of the Statistics Manager Website you are running:</span></span>
  
- <span data-ttu-id="0fbc3-150">文件资源管理器中打开 （默认目录） 的业务服务器 StatsMan WebSite\bin C:\Program Files\Skype</span><span class="sxs-lookup"><span data-stu-id="0fbc3-150">In File Explorer, open (default directory) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span></span>
    
- <span data-ttu-id="0fbc3-151">在 StatsManHubWebSite.dll 上右键单击，然后查看其属性</span><span class="sxs-lookup"><span data-stu-id="0fbc3-151">Right click on StatsManHubWebSite.dll and view its properties</span></span>
    
- <span data-ttu-id="0fbc3-152">产品版本将在“说明”详细信息中显示。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-152">The product version will be shown in the Description details.</span></span>
    
## <a name="components"></a><span data-ttu-id="0fbc3-153">组件</span><span class="sxs-lookup"><span data-stu-id="0fbc3-153">Components</span></span>
<span data-ttu-id="0fbc3-154"><a name="BKMK_Components"> </a></span><span class="sxs-lookup"><span data-stu-id="0fbc3-154"></span></span>

<span data-ttu-id="0fbc3-155">统计管理器包含以下组件：</span><span class="sxs-lookup"><span data-stu-id="0fbc3-155">Statistics Manager consists of the following components:</span></span>
  
- <span data-ttu-id="0fbc3-156">**代理。**</span><span class="sxs-lookup"><span data-stu-id="0fbc3-156">**Agent.**</span></span> <span data-ttu-id="0fbc3-157">在每个被监视的服务器运行一个轻量级代理。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-157">A lightweight agent that runs on each monitored server.</span></span> <span data-ttu-id="0fbc3-158">该代理允许具有本地的聚合性能计数器可配置高的速率轮询。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-158">The Agent allows configurable high rate polling of performance counters with local aggregation.</span></span>
    
- <span data-ttu-id="0fbc3-159">**监听器。**</span><span class="sxs-lookup"><span data-stu-id="0fbc3-159">**Listener.**</span></span> <span data-ttu-id="0fbc3-160">服务器端 API 的所有代理，从接收数据和聚合数据跨群体。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-160">The server side API that receives data from all Agents, and aggregates data across populations.</span></span>
    
- <span data-ttu-id="0fbc3-161">**集线器。**</span><span class="sxs-lookup"><span data-stu-id="0fbc3-161">**Hub.**</span></span> <span data-ttu-id="0fbc3-162">提供服务系统中，客户端 API 用户运行的 web 服务器，以及通过网站连接的客户端提供实时数据更新。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-162">Serves as the client API for the system, runs on the web server(s), and provides real-time data updates to clients connected via the website.</span></span> <span data-ttu-id="0fbc3-163">（集线器是自动安装的网站 msi 的一部分。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-163">(The Hub is automatically installed as part of the Website msi.)</span></span>
    
- <span data-ttu-id="0fbc3-164">**网站。**</span><span class="sxs-lookup"><span data-stu-id="0fbc3-164">**Website.**</span></span> <span data-ttu-id="0fbc3-165">一个用户界面，齐心协力系统中提供的所有功能。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-165">A user interface that pulls together all the features available in the system.</span></span>
    
<span data-ttu-id="0fbc3-166">此外，统计数据管理器要求**Redis**，开放源代码的数据结构服务器的内存中缓存。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-166">In addition, Statistics Manager requires **Redis**, an open-sourced data structure server for in-memory caching.</span></span> <span data-ttu-id="0fbc3-167">有关下载 Redis 的详细信息，请参阅[部署管理器统计信息](deploy.md#BKMK_Deploy)。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-167">For more information about downloading Redis, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy) .</span></span>
  
## <a name="on-premises-deployment"></a><span data-ttu-id="0fbc3-168">内部部署</span><span class="sxs-lookup"><span data-stu-id="0fbc3-168">On-premises deployment</span></span>
<span data-ttu-id="0fbc3-169"><a name="BKMK_DeploymentOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="0fbc3-169"></span></span>

<span data-ttu-id="0fbc3-170">在内部部署中，一台服务器承载的所有服务器端统计管理器组件。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-170">In an on-premises deployment, a single server hosts all of the server-side Statistics Manager components.</span></span> 
  
<span data-ttu-id="0fbc3-171">下图显示在内部部署，其中统计管理器网站、 中心、 侦听器和缓存系统的 Redis 寄宿在一台计算机。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-171">The following diagram shows an on-premises deployment, in which the Statistics Manager Website, Hub, Listener, and Redis caching system are hosted on a single machine.</span></span> <span data-ttu-id="0fbc3-172">统计管理器监视三个 Skype 业务服务器，其中每个有一个代理将数据传输到侦听器。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-172">Statistics Manager is monitoring three Skype for Business servers, each of which have a single Agent transmitting data to the Listener.</span></span> <span data-ttu-id="0fbc3-173">用户连接到一个网站以查看所有数据聚合由统计数据管理器：</span><span class="sxs-lookup"><span data-stu-id="0fbc3-173">Users connect to a single Website to view all data aggregated by Statistics Manager:</span></span>
  
![统计管理器本地部署](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)
  
## <a name="requirements"></a><span data-ttu-id="0fbc3-175">要求</span><span class="sxs-lookup"><span data-stu-id="0fbc3-175">Requirements</span></span>
<span data-ttu-id="0fbc3-176"><a name="BKMK_Requirements"> </a></span><span class="sxs-lookup"><span data-stu-id="0fbc3-176"></span></span>

<span data-ttu-id="0fbc3-177">您需要在部署管理器统计信息之前，请考虑以下软件、 网络和硬件要求。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-177">You will need to consider the following software, networking, and hardware requirements before you deploy Statistics Manager.</span></span> 
  
### <a name="software-requirements"></a><span data-ttu-id="0fbc3-178">软件要求</span><span class="sxs-lookup"><span data-stu-id="0fbc3-178">Software requirements</span></span>

- <span data-ttu-id="0fbc3-179">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="0fbc3-179">Windows Server 2012 R2</span></span>
    
- <span data-ttu-id="0fbc3-180">IIS （自动安装）</span><span class="sxs-lookup"><span data-stu-id="0fbc3-180">IIS (automatically installed)</span></span>
    
- <span data-ttu-id="0fbc3-181">Redis</span><span class="sxs-lookup"><span data-stu-id="0fbc3-181">Redis</span></span>
    
- <span data-ttu-id="0fbc3-182">（自动安装） 的统计信息管理器服务</span><span class="sxs-lookup"><span data-stu-id="0fbc3-182">Statistics Manager services (automatically installed)</span></span>
    
- <span data-ttu-id="0fbc3-183">PSExec 的要求做远程代理部署</span><span class="sxs-lookup"><span data-stu-id="0fbc3-183">PSExec - Required to do remote agent deployment</span></span>
    
- <span data-ttu-id="0fbc3-184">（附带 2012 R2）.NET 4.5-所需的服务器端组件</span><span class="sxs-lookup"><span data-stu-id="0fbc3-184">.NET 4.5 (included with 2012 R2) - Required for server-side components</span></span>
    
- <span data-ttu-id="0fbc3-185">.NET 4.0-所需的代理</span><span class="sxs-lookup"><span data-stu-id="0fbc3-185">.NET 4.0 - Required for agents</span></span>
    
### <a name="networking-requirements"></a><span data-ttu-id="0fbc3-186">网络要求</span><span class="sxs-lookup"><span data-stu-id="0fbc3-186">Networking requirements</span></span>


|<span data-ttu-id="0fbc3-187">**托管服务器**</span><span class="sxs-lookup"><span data-stu-id="0fbc3-187">**Hosting server**</span></span>|<span data-ttu-id="0fbc3-188">**代理**</span><span class="sxs-lookup"><span data-stu-id="0fbc3-188">**Agents**</span></span>|<span data-ttu-id="0fbc3-189">**侦听器**</span><span class="sxs-lookup"><span data-stu-id="0fbc3-189">**Listener**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0fbc3-190">最小的千兆全双工的网络。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-190">Minimum gigabit full duplex networking.</span></span>  <br/> |<span data-ttu-id="0fbc3-191">出站 TCP 端口 8443 （可自定义的端口号） 与侦听程序进行通信。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-191">Outbound TCP port 8443 (customizable port number) to communicate with the Listener.</span></span>  <br/> |<span data-ttu-id="0fbc3-192">侦听器端口必须为所有服务器上相同。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-192">The Listener port must be the same on all servers.</span></span>  <br/> |
|<span data-ttu-id="0fbc3-193">入站 TCP 端口 80 或 443 打开该网站的宿主。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-193">Inbound TCP port 80 or 443 open to host the website.</span></span>  <br/> |||
|<span data-ttu-id="0fbc3-194">要与之通信的代理程序的入站 TCP 端口 8443 （可自定义的端口号）。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-194">Inbound TCP port 8443 (customizable port number) for the agents to communicate with it.</span></span>  <br/> |||
   
<span data-ttu-id="0fbc3-195">在安装期间，系统会自动创建监听器和该网站的防火墙端口。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-195">During installation, firewall ports for the Listener and the Website are automatically created.</span></span> <span data-ttu-id="0fbc3-196">对于代理，安装假定默认情况下允许出站 TCP 连接。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-196">For the Agents, the installation assumes that outbound TCP connections are allowed by default.</span></span>
  
### <a name="hardware-requirements"></a><span data-ttu-id="0fbc3-197">硬件要求</span><span class="sxs-lookup"><span data-stu-id="0fbc3-197">Hardware requirements</span></span>

<span data-ttu-id="0fbc3-198">在内部部署中，一台服务器承载的所有服务器端统计管理器组件，16 gb 的 RAM 和 4 服务器 CPU 的应该是能够平均支持每秒大约 150 个样本。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-198">In an on-premises deployment, in which a single server hosts all of the server-side Statistics Manager components, a server with 16 GB of RAM and 4 CPU's should be able to support about 150 samples per second on average.</span></span> <span data-ttu-id="0fbc3-199">若要确定可支持多少个计数器/代理，请使用以下方法计算：</span><span class="sxs-lookup"><span data-stu-id="0fbc3-199">To determine how many counters/agents you can support, use the following calculation:</span></span> 
  
<span data-ttu-id="0fbc3-200">100 个服务器\*80 计数器\*1 示例每分钟每个代理 / 60 秒 = ~ 每秒 133 样本。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-200">100 servers \*80 counters \* 1 sample per minute from each agent / 60 seconds = ~ 133 samples per second.</span></span>
  
## <a name="security-considerations"></a><span data-ttu-id="0fbc3-201">安全注意事项</span><span class="sxs-lookup"><span data-stu-id="0fbc3-201">Security considerations</span></span>
<span data-ttu-id="0fbc3-202"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="0fbc3-202"></span></span>

<span data-ttu-id="0fbc3-203">服务器之间的所有通信进行都加密。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-203">All traffic between servers is encrypted.</span></span> 
  
- <span data-ttu-id="0fbc3-204">加密的 HTTPS 通信将是通过端口 8443 （默认值） 从代理发送到侦听器服务器。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-204">Encrypted HTTPS traffic will be sent over port 8443 (by default) from the Agent to the Listener server.</span></span>
    
- <span data-ttu-id="0fbc3-205">该代理将验证以确保监听器服务器是预期的收件人的服务器上的 SSL 指纹。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-205">The Agent will verify the SSL thumbprint on the server to ensure the Listener server is the expected recipient.</span></span> <span data-ttu-id="0fbc3-206">请注意，代理使用证书指纹验证（而不是链验证）。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-206">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="0fbc3-207">由于可能使用自签名证书，因此它不会执行完整证书验证。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-207">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>
    
- <span data-ttu-id="0fbc3-208">代理满意后侦听器可信，必须由代理然后验证侦听器中提供密码。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-208">After the Agent is satisfied the Listener is authentic, a password will be presented by the Agent which is then verified by the Listener.</span></span> 
    
- <span data-ttu-id="0fbc3-209">该代理开始通过向监听器连接传输性能数据。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-209">The Agent begins transmitting performance data over the connection to the Listener.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="0fbc3-210">详细信息</span><span class="sxs-lookup"><span data-stu-id="0fbc3-210">For more information</span></span>
<span data-ttu-id="0fbc3-211"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="0fbc3-211"></span></span>

<span data-ttu-id="0fbc3-212">有关详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="0fbc3-212">For more information, see the following:</span></span>
  
- [<span data-ttu-id="0fbc3-213">为业务服务器 2015年部署 Skype 的统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="0fbc3-213">Deploy Statistics Manager for Skype for Business Server 2015</span></span>](deploy.md)
    
- [<span data-ttu-id="0fbc3-214">为业务服务器 2015年升级为 Skype 的统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="0fbc3-214">Upgrade Statistics Manager for Skype for Business Server 2015</span></span>](upgrade.md)
    
- [<span data-ttu-id="0fbc3-215">解决业务服务器 2015年的 Skype 的统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="0fbc3-215">Troubleshoot Statistics Manager for Skype for Business Server 2015</span></span>](troubleshoot.md)
    
- [<span data-ttu-id="0fbc3-216">Skype 业务服务器统计信息管理器日志</span><span class="sxs-lookup"><span data-stu-id="0fbc3-216">Skype for Business Server Statistics Manager blog</span></span>](https://blogs.technet.microsoft.com/skypestatsman/)
    

