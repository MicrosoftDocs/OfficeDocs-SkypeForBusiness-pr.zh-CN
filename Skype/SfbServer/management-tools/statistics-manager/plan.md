---
title: Skype for Business Server 的统计信息管理器规划
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
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 摘要：阅读本主题，了解 Skype for business 服务器的统计信息管理器。
ms.openlocfilehash: 0bf7a5366047a0f4435a98cd8bca75eeb3ebc8d7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816231"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="b126d-103">Skype for Business Server 的统计信息管理器规划</span><span class="sxs-lookup"><span data-stu-id="b126d-103">Plan for Statistics Manager for Skype for Business Server</span></span>

<span data-ttu-id="b126d-104">**摘要：** 阅读本主题，了解 Skype for business 服务器的统计信息管理器。</span><span class="sxs-lookup"><span data-stu-id="b126d-104">**Summary:** Read this topic to learn about Statistics Manager for Skype for Business Server.</span></span>

 <span data-ttu-id="b126d-105">Skype for Business Server 统计信息管理器是一个功能强大的工具，可让你实时查看 Skype for Business Server 运行状况和性能数据。</span><span class="sxs-lookup"><span data-stu-id="b126d-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="b126d-106">你可以每隔几秒钟轮询数百台服务器的性能数据，并且在统计信息管理器网站上立即查看结果。</span><span class="sxs-lookup"><span data-stu-id="b126d-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>

<span data-ttu-id="b126d-107">你可以使用统计管理器确定持续的性能问题、查看你的环境的计划更改的结果、跟踪中断的解决情况以及更多功能。</span><span class="sxs-lookup"><span data-stu-id="b126d-107">You can use Statistics Manager to identify ongoing performance issues, view the results of a planned change to your environment, track resolution of outages, and much more.</span></span> <span data-ttu-id="b126d-108">在该框外，统计管理器配置有关键运行状况指示器（KHI）阈值，并且可以进行自定义以满足你的部署的独特需求。</span><span class="sxs-lookup"><span data-stu-id="b126d-108">Out of the box, Statistics Manager is configured with Key Health Indicator (KHI) thresholds, and can be customized to suit your deployment's unique needs.</span></span>

<span data-ttu-id="b126d-109">你可以在单个服务器托管所有服务器端统计信息管理器组件的本地部署中部署统计信息管理器。</span><span class="sxs-lookup"><span data-stu-id="b126d-109">You can deploy Statistics Manager in an on-premises deployment in which a single server hosts all of the server-side Statistics Manager components.</span></span> <span data-ttu-id="b126d-110">有关部署统计信息管理器的详细信息，请参阅[部署 Skype for Business 服务器的统计管理器](deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="b126d-110">For more information about deploying Statistics Manager, see [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span> <span data-ttu-id="b126d-111">如果已有一个现有的统计信息管理器部署，但尚未升级到版本2.0，请参阅[版本2.0 中的新增功能](plan.md#BKMK_WhatsNew)和[Skype for Business 服务器的升级统计管理器](upgrade.md)。</span><span class="sxs-lookup"><span data-stu-id="b126d-111">If you already have an existing deployment of Statistics Manager, but you have not yet upgraded to Release 2.0, see [What's new in Release 2.0](plan.md#BKMK_WhatsNew) and [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

<span data-ttu-id="b126d-112">本主题包括以下部分：</span><span class="sxs-lookup"><span data-stu-id="b126d-112">This topic contains the following sections:</span></span>

- [<span data-ttu-id="b126d-113">功能和功能</span><span class="sxs-lookup"><span data-stu-id="b126d-113">Features and capabilities</span></span>](plan.md#BKMK_Features)

- [<span data-ttu-id="b126d-114">版本2.0 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="b126d-114">What's new in Release 2.0</span></span>](plan.md#BKMK_WhatsNew)

- [<span data-ttu-id="b126d-115">组件</span><span class="sxs-lookup"><span data-stu-id="b126d-115">Components</span></span>](plan.md#BKMK_Components)

- [<span data-ttu-id="b126d-116">本地部署</span><span class="sxs-lookup"><span data-stu-id="b126d-116">On-premises deployment</span></span>](plan.md#BKMK_DeploymentOptions)

- [<span data-ttu-id="b126d-117">要求</span><span class="sxs-lookup"><span data-stu-id="b126d-117">Requirements</span></span>](plan.md#BKMK_Requirements)

- [<span data-ttu-id="b126d-118">安全注意事项</span><span class="sxs-lookup"><span data-stu-id="b126d-118">Security considerations</span></span>](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a><span data-ttu-id="b126d-119">功能和功能</span><span class="sxs-lookup"><span data-stu-id="b126d-119">Features and capabilities</span></span>
<span data-ttu-id="b126d-120"><a name="BKMK_Features"> </a></span><span class="sxs-lookup"><span data-stu-id="b126d-120"><a name="BKMK_Features"> </a></span></span>

<span data-ttu-id="b126d-121">统计信息管理器允许您：</span><span class="sxs-lookup"><span data-stu-id="b126d-121">Statistics Manager allows you to:</span></span>

- <span data-ttu-id="b126d-122">实时查看所有服务器的原始数据。</span><span class="sxs-lookup"><span data-stu-id="b126d-122">View raw data for all servers in real time.</span></span> <span data-ttu-id="b126d-123">（数据以极其高的费率进行采样，并在不到一秒钟的时间内发送到网站。）</span><span class="sxs-lookup"><span data-stu-id="b126d-123">(Data is sampled at a very high rate and sent to the website in less than one second.)</span></span>

- <span data-ttu-id="b126d-124">查看针对特定角色聚合的数据;例如，前端服务器、中介服务器、边缘服务器等。</span><span class="sxs-lookup"><span data-stu-id="b126d-124">View data that is aggregated for a specific role; for example, Front End Server, Mediation Server, Edge Server, and so on.</span></span>

- <span data-ttu-id="b126d-125">向下钻取以查看特定网站、网站内特定池的数据，以及池中的特定服务器的数据。</span><span class="sxs-lookup"><span data-stu-id="b126d-125">Drill down to view data for specific sites, specific pools within the site, and then specific servers within the pool.</span></span>

- <span data-ttu-id="b126d-126">创建自定义图表，以便默认显示所选计数器。</span><span class="sxs-lookup"><span data-stu-id="b126d-126">Create custom charts so that chosen counters are shown by default.</span></span>

- <span data-ttu-id="b126d-127">仅在 x 轴和 y 轴上或在 x 轴上缩放和平移。</span><span class="sxs-lookup"><span data-stu-id="b126d-127">Zoom and pan on both the x- and y- axes or on the x-axis only.</span></span>

- <span data-ttu-id="b126d-128">使用日期范围或时间点来筛选数据。</span><span class="sxs-lookup"><span data-stu-id="b126d-128">Use date ranges or points in time to filter data.</span></span>

- <span data-ttu-id="b126d-129">基于已建立的密钥运行状况指示器（KHIs）查看服务器性能。</span><span class="sxs-lookup"><span data-stu-id="b126d-129">View server performance based on established key health indicators (KHIs).</span></span> <span data-ttu-id="b126d-130">KHIs 表示具有定义的正常范围的性能计数器的集合。</span><span class="sxs-lookup"><span data-stu-id="b126d-130">KHIs represent a collection of performance counters with a defined healthy range.</span></span>

- <span data-ttu-id="b126d-131">查看每个计数器的详细指标。</span><span class="sxs-lookup"><span data-stu-id="b126d-131">View detailed metrics for each counter.</span></span>

- <span data-ttu-id="b126d-132">比较多个人口或服务器上的数据。</span><span class="sxs-lookup"><span data-stu-id="b126d-132">Compare data across multiple populations or servers.</span></span>

- <span data-ttu-id="b126d-133">查看潜在计数器报表，以标识不向仪表板服务报告当前数据的代理。</span><span class="sxs-lookup"><span data-stu-id="b126d-133">View latent counter reports to identify agents that are not reporting current data to the dashboard service.</span></span>

- <span data-ttu-id="b126d-134">将图表数据的特定实例保存到文件。</span><span class="sxs-lookup"><span data-stu-id="b126d-134">Save a particular instance of chart data to a file.</span></span>

- <span data-ttu-id="b126d-135">实时查看 KHIs，包括更新。</span><span class="sxs-lookup"><span data-stu-id="b126d-135">View KHIs in real time, including updates.</span></span> <span data-ttu-id="b126d-136">如果启用了 "历史记录" 视图，则仅显示新的失败。</span><span class="sxs-lookup"><span data-stu-id="b126d-136">If the history view is enabled, only new failures are shown.</span></span>

  - <span data-ttu-id="b126d-137">一次查看所有 KHIs</span><span class="sxs-lookup"><span data-stu-id="b126d-137">View all KHIs at one time</span></span>

  - <span data-ttu-id="b126d-138">按服务器查看 KHIs （横向视图）</span><span class="sxs-lookup"><span data-stu-id="b126d-138">View KHIs by server (Landscape view)</span></span>

  - <span data-ttu-id="b126d-139">查看 KHI 定义</span><span class="sxs-lookup"><span data-stu-id="b126d-139">View KHI definitions</span></span>

## <a name="whats-new-in-release-20"></a><span data-ttu-id="b126d-140">版本2.0 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="b126d-140">What's new in Release 2.0</span></span>
<span data-ttu-id="b126d-141"><a name="BKMK_WhatsNew"> </a></span><span class="sxs-lookup"><span data-stu-id="b126d-141"><a name="BKMK_WhatsNew"> </a></span></span>

<span data-ttu-id="b126d-142">下面介绍了版本2.0 中的新增功能。</span><span class="sxs-lookup"><span data-stu-id="b126d-142">The following describes what's new in Release 2.0.</span></span> <span data-ttu-id="b126d-143">如果你有现有的统计信息管理器部署，但尚未升级，请参阅[升级 Skype for Business 服务器的统计信息管理器](upgrade.md)。</span><span class="sxs-lookup"><span data-stu-id="b126d-143">If you have an existing deployment of Statistics Manager and you've not yet upgraded, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

- <span data-ttu-id="b126d-144">已为 Edge 媒体、结构运行状况、池故障转移和注册方案添加了方案视图。</span><span class="sxs-lookup"><span data-stu-id="b126d-144">Scenario views have been added for Edge Media, Fabric Health, Pool Failover and Registration scenarios.</span></span>

- <span data-ttu-id="b126d-145">为 SQL server 添加了许多新的计数器、更多 Skype for Business 使用率计数器等。</span><span class="sxs-lookup"><span data-stu-id="b126d-145">Many new counters have been added for SQL servers, more Skype for Business usage counters, and so on.</span></span>

- <span data-ttu-id="b126d-146">统计信息管理器代理的观察程序节点集成-如果在观察程序节点上安装了代理，它会将合成事务统计信息作为计数器报告回统计信息管理器。</span><span class="sxs-lookup"><span data-stu-id="b126d-146">Watcher node integration for the Statistics Manager Agent - if the Agent is installed on a watcher node, it will report synthetic transaction statistics as counters back to Statistics Manager.</span></span>

- <span data-ttu-id="b126d-147">许多可靠性和性能改进。</span><span class="sxs-lookup"><span data-stu-id="b126d-147">Numerous reliability and performance improvements.</span></span>

<span data-ttu-id="b126d-148">若要验证你正在运行的统计信息管理器网站的版本，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b126d-148">To verify the version of the Statistics Manager Website you are running:</span></span>

- <span data-ttu-id="b126d-149">在文件资源管理器中，打开（默认目录） C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span><span class="sxs-lookup"><span data-stu-id="b126d-149">In File Explorer, open (default directory) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span></span>

- <span data-ttu-id="b126d-150">右键单击 StatsManHubWebSite 并查看其属性</span><span class="sxs-lookup"><span data-stu-id="b126d-150">Right click on StatsManHubWebSite.dll and view its properties</span></span>

- <span data-ttu-id="b126d-151">产品版本将在“说明”详细信息中显示。</span><span class="sxs-lookup"><span data-stu-id="b126d-151">The product version will be shown in the Description details.</span></span>

## <a name="components"></a><span data-ttu-id="b126d-152">组件</span><span class="sxs-lookup"><span data-stu-id="b126d-152">Components</span></span>
<span data-ttu-id="b126d-153"><a name="BKMK_Components"> </a></span><span class="sxs-lookup"><span data-stu-id="b126d-153"><a name="BKMK_Components"> </a></span></span>

<span data-ttu-id="b126d-154">统计信息管理器包含以下组件：</span><span class="sxs-lookup"><span data-stu-id="b126d-154">Statistics Manager consists of the following components:</span></span>

- <span data-ttu-id="b126d-155">**工程师.**</span><span class="sxs-lookup"><span data-stu-id="b126d-155">**Agent.**</span></span> <span data-ttu-id="b126d-156">在每个受监视的服务器上运行的轻量代理。</span><span class="sxs-lookup"><span data-stu-id="b126d-156">A lightweight agent that runs on each monitored server.</span></span> <span data-ttu-id="b126d-157">代理允许对具有本地聚合的性能计数器进行可配置的高速率轮询。</span><span class="sxs-lookup"><span data-stu-id="b126d-157">The Agent allows configurable high rate polling of performance counters with local aggregation.</span></span>

- <span data-ttu-id="b126d-158">**监听器.**</span><span class="sxs-lookup"><span data-stu-id="b126d-158">**Listener.**</span></span> <span data-ttu-id="b126d-159">从所有代理接收数据并跨人口聚合数据的服务器端 API。</span><span class="sxs-lookup"><span data-stu-id="b126d-159">The server side API that receives data from all Agents, and aggregates data across populations.</span></span>

- <span data-ttu-id="b126d-160">**中心.**</span><span class="sxs-lookup"><span data-stu-id="b126d-160">**Hub.**</span></span> <span data-ttu-id="b126d-161">充当系统的客户端 API，在 web 服务器上运行，并向通过网站连接的客户端提供实时数据更新。</span><span class="sxs-lookup"><span data-stu-id="b126d-161">Serves as the client API for the system, runs on the web server(s), and provides real-time data updates to clients connected via the website.</span></span> <span data-ttu-id="b126d-162">（中心将自动作为网站 msi 的一部分进行安装。）</span><span class="sxs-lookup"><span data-stu-id="b126d-162">(The Hub is automatically installed as part of the Website msi.)</span></span>

- <span data-ttu-id="b126d-163">**网站.**</span><span class="sxs-lookup"><span data-stu-id="b126d-163">**Website.**</span></span> <span data-ttu-id="b126d-164">将系统中可用的所有功能集中在一起的用户界面。</span><span class="sxs-lookup"><span data-stu-id="b126d-164">A user interface that pulls together all the features available in the system.</span></span>

<span data-ttu-id="b126d-165">此外，统计信息管理器需要**Redis**，这是一个开放来源的数据结构服务器，用于内存中的缓存。</span><span class="sxs-lookup"><span data-stu-id="b126d-165">In addition, Statistics Manager requires **Redis**, an open-sourced data structure server for in-memory caching.</span></span> <span data-ttu-id="b126d-166">有关下载 Redis 的详细信息，请参阅[部署统计信息管理器](deploy.md#BKMK_Deploy)。</span><span class="sxs-lookup"><span data-stu-id="b126d-166">For more information about downloading Redis, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy) .</span></span>

## <a name="on-premises-deployment"></a><span data-ttu-id="b126d-167">本地部署</span><span class="sxs-lookup"><span data-stu-id="b126d-167">On-premises deployment</span></span>
<span data-ttu-id="b126d-168"><a name="BKMK_DeploymentOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="b126d-168"><a name="BKMK_DeploymentOptions"> </a></span></span>

<span data-ttu-id="b126d-169">在本地部署中，单个服务器托管所有服务器端统计信息管理器组件。</span><span class="sxs-lookup"><span data-stu-id="b126d-169">In an on-premises deployment, a single server hosts all of the server-side Statistics Manager components.</span></span>

<span data-ttu-id="b126d-170">下图显示了一个本地部署，其中统计信息管理器网站、中心、侦听器和 Redis 缓存系统托管在一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="b126d-170">The following diagram shows an on-premises deployment, in which the Statistics Manager Website, Hub, Listener, and Redis caching system are hosted on a single machine.</span></span> <span data-ttu-id="b126d-171">统计信息管理器监视三个 Skype for Business 服务器，每个服务器都有一个代理将数据传输到侦听器。</span><span class="sxs-lookup"><span data-stu-id="b126d-171">Statistics Manager is monitoring three Skype for Business servers, each of which have a single Agent transmitting data to the Listener.</span></span> <span data-ttu-id="b126d-172">用户连接到单个网站以查看统计信息管理器聚合的所有数据：</span><span class="sxs-lookup"><span data-stu-id="b126d-172">Users connect to a single Website to view all data aggregated by Statistics Manager:</span></span>

![统计管理器本地部署](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a><span data-ttu-id="b126d-174">要求</span><span class="sxs-lookup"><span data-stu-id="b126d-174">Requirements</span></span>
<span data-ttu-id="b126d-175"><a name="BKMK_Requirements"> </a></span><span class="sxs-lookup"><span data-stu-id="b126d-175"><a name="BKMK_Requirements"> </a></span></span>

<span data-ttu-id="b126d-176">部署统计信息管理器之前，需要考虑以下软件、网络和硬件要求。</span><span class="sxs-lookup"><span data-stu-id="b126d-176">You will need to consider the following software, networking, and hardware requirements before you deploy Statistics Manager.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="b126d-177">软件要求</span><span class="sxs-lookup"><span data-stu-id="b126d-177">Software requirements</span></span>

- <span data-ttu-id="b126d-178">Windows Server 2016 和2019</span><span class="sxs-lookup"><span data-stu-id="b126d-178">Windows Server 2016 and 2019</span></span>

- <span data-ttu-id="b126d-179">IIS （自动安装）</span><span class="sxs-lookup"><span data-stu-id="b126d-179">IIS (automatically installed)</span></span>

- <span data-ttu-id="b126d-180">Redis</span><span class="sxs-lookup"><span data-stu-id="b126d-180">Redis</span></span>

- <span data-ttu-id="b126d-181">统计管理器服务（自动安装）</span><span class="sxs-lookup"><span data-stu-id="b126d-181">Statistics Manager services (automatically installed)</span></span>

- <span data-ttu-id="b126d-182">PSExec-执行远程代理部署所需</span><span class="sxs-lookup"><span data-stu-id="b126d-182">PSExec - Required to do remote agent deployment</span></span>

- <span data-ttu-id="b126d-183">.NET 4.5 （包含于 2012 R2）-工程师和服务器端组件所需</span><span class="sxs-lookup"><span data-stu-id="b126d-183">.NET 4.5 (included with 2012 R2) - Required for agents and server-side components</span></span>
- <span data-ttu-id="b126d-184">下载[Skype For Business 服务器，实时统计信息管理器（64位）](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span><span class="sxs-lookup"><span data-stu-id="b126d-184">Download the [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="b126d-185">网络要求</span><span class="sxs-lookup"><span data-stu-id="b126d-185">Networking requirements</span></span>


|<span data-ttu-id="b126d-186">**托管服务器**</span><span class="sxs-lookup"><span data-stu-id="b126d-186">**Hosting server**</span></span>|<span data-ttu-id="b126d-187">**代理**</span><span class="sxs-lookup"><span data-stu-id="b126d-187">**Agents**</span></span>|<span data-ttu-id="b126d-188">**监听器**</span><span class="sxs-lookup"><span data-stu-id="b126d-188">**Listener**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b126d-189">最低千兆位全双工网络。</span><span class="sxs-lookup"><span data-stu-id="b126d-189">Minimum gigabit full duplex networking.</span></span>  <br/> |<span data-ttu-id="b126d-190">出站 TCP 端口8443（可自定义端口号）与侦听器通信。</span><span class="sxs-lookup"><span data-stu-id="b126d-190">Outbound TCP port 8443 (customizable port number) to communicate with the Listener.</span></span>  <br/> |<span data-ttu-id="b126d-191">侦听器端口在所有服务器上必须是相同的。</span><span class="sxs-lookup"><span data-stu-id="b126d-191">The Listener port must be the same on all servers.</span></span>  <br/> |
|<span data-ttu-id="b126d-192">已打开入站 TCP 端口80或443以托管网站。</span><span class="sxs-lookup"><span data-stu-id="b126d-192">Inbound TCP port 80 or 443 open to host the website.</span></span>  <br/> |||
|<span data-ttu-id="b126d-193">代理与之通信的入站 TCP 端口8443（可自定义端口号）。</span><span class="sxs-lookup"><span data-stu-id="b126d-193">Inbound TCP port 8443 (customizable port number) for the agents to communicate with it.</span></span>  <br/> |||

<span data-ttu-id="b126d-194">在安装过程中，将自动创建侦听器和网站的防火墙端口。</span><span class="sxs-lookup"><span data-stu-id="b126d-194">During installation, firewall ports for the Listener and the Website are automatically created.</span></span> <span data-ttu-id="b126d-195">对于代理，安装假定默认情况下允许出站 TCP 连接。</span><span class="sxs-lookup"><span data-stu-id="b126d-195">For the Agents, the installation assumes that outbound TCP connections are allowed by default.</span></span>

### <a name="hardware-requirements"></a><span data-ttu-id="b126d-196">硬件要求</span><span class="sxs-lookup"><span data-stu-id="b126d-196">Hardware requirements</span></span>

<span data-ttu-id="b126d-197">在本地部署中，如果单个服务器托管所有服务器端统计信息管理器组件，则具有 16 GB RAM 和 4 CPU 的服务器应该能够支持平均每秒150样本。</span><span class="sxs-lookup"><span data-stu-id="b126d-197">In an on-premises deployment, in which a single server hosts all of the server-side Statistics Manager components, a server with 16 GB of RAM and 4 CPU's should be able to support about 150 samples per second on average.</span></span> <span data-ttu-id="b126d-198">若要确定可以支持多少个计数器/代理，请使用以下计算：</span><span class="sxs-lookup"><span data-stu-id="b126d-198">To determine how many counters/agents you can support, use the following calculation:</span></span>

<span data-ttu-id="b126d-199">100 server \*80 每\*秒从每个代理/60 秒开始每分钟1采样 = 大约每秒133采样。</span><span class="sxs-lookup"><span data-stu-id="b126d-199">100 servers \*80 counters \* 1 sample per minute from each agent / 60 seconds = ~ 133 samples per second.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="b126d-200">安全注意事项</span><span class="sxs-lookup"><span data-stu-id="b126d-200">Security considerations</span></span>
<span data-ttu-id="b126d-201"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="b126d-201"><a name="BKMK_Security"> </a></span></span>

<span data-ttu-id="b126d-202">服务器之间的所有流量均已加密。</span><span class="sxs-lookup"><span data-stu-id="b126d-202">All traffic between servers is encrypted.</span></span>

- <span data-ttu-id="b126d-203">加密 HTTPS 流量将通过端口8443（默认情况）从代理发送到侦听器服务器。</span><span class="sxs-lookup"><span data-stu-id="b126d-203">Encrypted HTTPS traffic will be sent over port 8443 (by default) from the Agent to the Listener server.</span></span>

- <span data-ttu-id="b126d-204">代理将在服务器上验证 SSL 指纹，以确保监听器服务器是预期的收件人。</span><span class="sxs-lookup"><span data-stu-id="b126d-204">The Agent will verify the SSL thumbprint on the server to ensure the Listener server is the expected recipient.</span></span> <span data-ttu-id="b126d-205">请注意，代理使用证书指纹验证（而不是链验证）。</span><span class="sxs-lookup"><span data-stu-id="b126d-205">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="b126d-206">由于可能使用自签名证书，因此它不会执行完整证书验证。</span><span class="sxs-lookup"><span data-stu-id="b126d-206">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>

- <span data-ttu-id="b126d-207">当该代理达到可信后，该监听器将由监听器验证，然后由监听器验证。</span><span class="sxs-lookup"><span data-stu-id="b126d-207">After the Agent is satisfied the Listener is authentic, a password will be presented by the Agent which is then verified by the Listener.</span></span>

- <span data-ttu-id="b126d-208">代理将通过与侦听器的连接开始传输性能数据。</span><span class="sxs-lookup"><span data-stu-id="b126d-208">The Agent begins transmitting performance data over the connection to the Listener.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="b126d-209">有关详细信息</span><span class="sxs-lookup"><span data-stu-id="b126d-209">For more information</span></span>
<span data-ttu-id="b126d-210"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="b126d-210"><a name="BKMK_Security"> </a></span></span>

<span data-ttu-id="b126d-211">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="b126d-211">For more information, see the following:</span></span>

- [<span data-ttu-id="b126d-212">部署 Skype for Business Server 的统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="b126d-212">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)

- [<span data-ttu-id="b126d-213">更新 Skype for Business Server 的统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="b126d-213">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)

- [<span data-ttu-id="b126d-214">对 Skype for Business Server 的统计信息管理器进行故障排除</span><span class="sxs-lookup"><span data-stu-id="b126d-214">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
