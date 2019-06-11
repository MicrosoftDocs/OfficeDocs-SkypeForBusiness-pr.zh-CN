---
title: 'Lync Server 2013: 海报: 关键运行状况指示器'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Poster: Key Health Indicators'
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9454197642ac87f5d8bc0d768795854d792f9a31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-health-indicators-in-lync-server-2013"></a><span data-ttu-id="8eaf5-102">Lync Server 2013 中的关键运行状况指示器</span><span class="sxs-lookup"><span data-stu-id="8eaf5-102">Key Health Indicators in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8eaf5-103">_**主题上次修改时间:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="8eaf5-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="8eaf5-104">本文介绍了[关键运行状况指示器: 维护正常的 Lync 服务器海报的基础](http://go.microsoft.com/fwlink/?linkid=391838), 您可以从下载中心下载。</span><span class="sxs-lookup"><span data-stu-id="8eaf5-104">This article is a companion to the [Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers](http://go.microsoft.com/fwlink/?linkid=391838) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="8eaf5-105">![描述使用 KHI 数据进行疑难解答的海报](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "描述使用 KHI 数据进行疑难解答的海报")</span><span class="sxs-lookup"><span data-stu-id="8eaf5-105">![Poster describing troubleshooting using KHI data](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster describing troubleshooting using KHI data")</span></span>

<span data-ttu-id="8eaf5-106">你可以使用此海报了解有关关键运行状况指示器 (KHIs) 的性能计数器, 其阈值旨在展示用户体验问题。</span><span class="sxs-lookup"><span data-stu-id="8eaf5-106">You can use this poster to learn about Key Health Indicators (KHIs), performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="8eaf5-107">收集 KHI 数据通常是实现呼叫质量方法 (CQM) 的第一步, 它侧重于确保 Lync 用户的音质音频体验。</span><span class="sxs-lookup"><span data-stu-id="8eaf5-107">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="8eaf5-108">如果对如何使用 CQM 有疑问, 可以将问题提交到 cqmfeedback@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="8eaf5-108">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="8eaf5-109">海报介绍以下方面:</span><span class="sxs-lookup"><span data-stu-id="8eaf5-109">The poster explains the following areas:</span></span>

  - <span data-ttu-id="8eaf5-110">什么是关键运行状况指示器？</span><span class="sxs-lookup"><span data-stu-id="8eaf5-110">What are Key Health Indicators?</span></span>

  - <span data-ttu-id="8eaf5-111">收集 KHI 数据</span><span class="sxs-lookup"><span data-stu-id="8eaf5-111">To Collect KHI Data</span></span>

  - <span data-ttu-id="8eaf5-112">所有服务器角色的更新流</span><span class="sxs-lookup"><span data-stu-id="8eaf5-112">Remediation Flow for all Server Roles</span></span>

  - <span data-ttu-id="8eaf5-113">词条</span><span class="sxs-lookup"><span data-stu-id="8eaf5-113">Glossary</span></span>

  - <span data-ttu-id="8eaf5-114">前端服务器</span><span class="sxs-lookup"><span data-stu-id="8eaf5-114">Front-end Servers</span></span>

  - <span data-ttu-id="8eaf5-115">后端 SQL 服务器</span><span class="sxs-lookup"><span data-stu-id="8eaf5-115">Backend SQL Servers</span></span>

  - <span data-ttu-id="8eaf5-116">中介服务器</span><span class="sxs-lookup"><span data-stu-id="8eaf5-116">Mediation Servers</span></span>

  - <span data-ttu-id="8eaf5-117">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="8eaf5-117">Edge Servers</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a><span data-ttu-id="8eaf5-118">什么是关键运行状况指示器？</span><span class="sxs-lookup"><span data-stu-id="8eaf5-118">What are Key Health Indicators?</span></span>

<span data-ttu-id="8eaf5-119">关键运行状况指示器是性能计数器, 其阈值旨在展示用户体验问题。</span><span class="sxs-lookup"><span data-stu-id="8eaf5-119">Key Health Indicators are performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="8eaf5-120">收集 KHI 数据通常是实现呼叫质量方法 (CQM) 的第一步, 它侧重于确保 Lync 用户的音质音频体验。</span><span class="sxs-lookup"><span data-stu-id="8eaf5-120">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="8eaf5-121">除了标准 Lync 监视解决方案 (如 System Center Operations Manager、合成事务、监视服务器) 之外, 还可使用 KHIs, 而不是使用这些解决方案。</span><span class="sxs-lookup"><span data-stu-id="8eaf5-121">KHIs are used in addition to standard Lync Monitoring Solutions (e.g. System Center Operations Manager, Synthetic Transactions, Monitoring Server) and not instead of those solutions.</span></span>

<span data-ttu-id="8eaf5-122">收集 KHI 性能计数器并填充网络指南随附的 KHI 电子表格, 以生成可帮助你确定 Lync 部署的服务器运行状况的记分卡。</span><span class="sxs-lookup"><span data-stu-id="8eaf5-122">Collect the KHI performance counters and populate the KHI spreadsheet accompanying the Networking Guide to produce a scorecard that will help you determine the server health of a Lync deployment.</span></span> <span data-ttu-id="8eaf5-123">填充后, 它将引导你修复环境并向其他利益干系人提供进一步的洞察力。</span><span class="sxs-lookup"><span data-stu-id="8eaf5-123">Once populated, it guides you in repairing the environment and gives additional insight to other stakeholders.</span></span> <span data-ttu-id="8eaf5-124">按月评估 KHIs, 并将它们合并到任何部署的日常操作流程中。</span><span class="sxs-lookup"><span data-stu-id="8eaf5-124">Evaluate KHIs on a monthly basis and incorporate them into any deployment’s ongoing operational processes.</span></span>

<span data-ttu-id="8eaf5-125">下载[Lync Server 网络指南](http://go.microsoft.com/fwlink/p/?linkid=390677)以查看完整的 KHIs 列表和获取相关的电子表格。</span><span class="sxs-lookup"><span data-stu-id="8eaf5-125">Download the [Lync Server Networking Guide](http://go.microsoft.com/fwlink/p/?linkid=390677) to see the full list of KHIs and to get the related spreadsheets.</span></span>

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a><span data-ttu-id="8eaf5-126">收集 KHI 数据</span><span class="sxs-lookup"><span data-stu-id="8eaf5-126">To Collect KHI Data</span></span>

1.  <span data-ttu-id="8eaf5-127">在每个 Lync 服务器上运行 Lync Server 网络指南附带的 KHI 脚本。</span><span class="sxs-lookup"><span data-stu-id="8eaf5-127">Run the KHI script included with the Lync Server Networking Guide on each Lync Server.</span></span> <span data-ttu-id="8eaf5-128">这将在性能监视器内创建一个数据收集器, 并将其命名为 KHI。</span><span class="sxs-lookup"><span data-stu-id="8eaf5-128">This will create a Data Collector inside of Performance Monitor and name it KHI.</span></span> <span data-ttu-id="8eaf5-129">默认情况下, 将每隔15秒对数据进行轮询。</span><span class="sxs-lookup"><span data-stu-id="8eaf5-129">By default, data will be polled every 15 seconds.</span></span>

2.  <span data-ttu-id="8eaf5-130">在公司的工作日内开始之前, 请转到每个 Lync 服务器并启动 KHI 数据收集器。</span><span class="sxs-lookup"><span data-stu-id="8eaf5-130">Before the start of your company's business day, go to each Lync Server and start the KHI Data Collector.</span></span>

3.  <span data-ttu-id="8eaf5-131">在该日期结束时, 停止 KHI 数据收集器并将数据复制到一个中心位置。</span><span class="sxs-lookup"><span data-stu-id="8eaf5-131">At the end of that day, stop the KHI Data Collector and copy the data to a central location.</span></span>

4.  <span data-ttu-id="8eaf5-132">使用性能监视器填充 Lync Server 网络指南附带的 KHI 电子表格后, 将结果与推荐的目标进行比较。</span><span class="sxs-lookup"><span data-stu-id="8eaf5-132">After using Performance Monitor to fill in the KHI spreadsheet included with the Lync Server Networking Guide download, compare the results to the recommended targets.</span></span>

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a><span data-ttu-id="8eaf5-133">所有服务器角色的更新流</span><span class="sxs-lookup"><span data-stu-id="8eaf5-133">Remediation Flow for all Server Roles</span></span>

<span data-ttu-id="8eaf5-134">对于 Lync 实现中的每个服务器, 首先验证服务器的组件运行状况和系统性能是否在所需级别或更高级别。</span><span class="sxs-lookup"><span data-stu-id="8eaf5-134">For each server in your Lync implementation, begin by verifying that the server’s component health and system performance is at or above the desired level.</span></span> <span data-ttu-id="8eaf5-135">只有在该情况之后, 才应查看整个 Lync 实现中与服务器角色相关的指示器。</span><span class="sxs-lookup"><span data-stu-id="8eaf5-135">Only after that should you look at the indicators relating to the server’s role in the overall Lync implementation.</span></span>

<span data-ttu-id="8eaf5-136">首先收集所有服务器的 KHI 性能数据。</span><span class="sxs-lookup"><span data-stu-id="8eaf5-136">Begin by collecting KHI Performance Data for all servers.</span></span> <span data-ttu-id="8eaf5-137">对于每个系统角色 (本文档后面部分讨论的详细信息) 确定基本系统组件是否满足推荐的目标。</span><span class="sxs-lookup"><span data-stu-id="8eaf5-137">For each of the system roles (details discussed later in this document) determine whether the basic system components meet the recommended targets.</span></span> <span data-ttu-id="8eaf5-138">如果不是这样, 请先补救系统性能, 然后重新收集 KHI 数据并确保系统运行状况, 然后再查看特定于 Lync 实现中的服务器角色的指标。</span><span class="sxs-lookup"><span data-stu-id="8eaf5-138">If they do not, remediate the system performance then re-collect KHI data and ensure system health before looking at the metrics specific to the server’s role in the Lync implementation.</span></span> <span data-ttu-id="8eaf5-139">所有角色的组件运行状况定义如下:</span><span class="sxs-lookup"><span data-stu-id="8eaf5-139">Component health for all roles is defined as:</span></span>

  - <span data-ttu-id="8eaf5-140">CPU 利用率\< 80%</span><span class="sxs-lookup"><span data-stu-id="8eaf5-140">CPU Utilization \< 80%</span></span>

  - <span data-ttu-id="8eaf5-141">平均磁盘写入\< 10 毫秒</span><span class="sxs-lookup"><span data-stu-id="8eaf5-141">Avg. Disk Write \< 10 ms</span></span>

  - <span data-ttu-id="8eaf5-142">平均磁盘读取\< 10 毫秒</span><span class="sxs-lookup"><span data-stu-id="8eaf5-142">Avg. Disk Read \< 10 ms</span></span>

  - <span data-ttu-id="8eaf5-143">可用内存\>20% 系统总 MB</span><span class="sxs-lookup"><span data-stu-id="8eaf5-143">Available memory \>20% System Total MB</span></span>

  - <span data-ttu-id="8eaf5-144">网络队列长度\< 2</span><span class="sxs-lookup"><span data-stu-id="8eaf5-144">Network Queue Length \< 2</span></span>

  - <span data-ttu-id="8eaf5-145">已丢弃的数据包 (in/out) = 0</span><span class="sxs-lookup"><span data-stu-id="8eaf5-145">Discarded Packets (in / out) = 0</span></span>

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a><span data-ttu-id="8eaf5-146">词条</span><span class="sxs-lookup"><span data-stu-id="8eaf5-146">Glossary</span></span>

<span data-ttu-id="8eaf5-147">本海报中使用下列术语和首字母缩写:</span><span class="sxs-lookup"><span data-stu-id="8eaf5-147">The following terms and acronyms are used in this poster:</span></span>

<span data-ttu-id="8eaf5-148">作为 MCU = 应用程序共享多点控制单元</span><span class="sxs-lookup"><span data-stu-id="8eaf5-148">AS MCU = Application Sharing Multi-point Control Unit</span></span>

<span data-ttu-id="8eaf5-149">AV MCU = 音频/视频 MCU</span><span class="sxs-lookup"><span data-stu-id="8eaf5-149">AV MCU = Audio/Video MCU</span></span>

<span data-ttu-id="8eaf5-150">IM MCU = 即时消息 MCU</span><span class="sxs-lookup"><span data-stu-id="8eaf5-150">IM MCU = Instant Messaging MCU</span></span>

<span data-ttu-id="8eaf5-151">UCWA = 统一通信 Web API</span><span class="sxs-lookup"><span data-stu-id="8eaf5-151">UCWA = Unified Communications Web API</span></span>

<span data-ttu-id="8eaf5-152">AV 边缘 = 通过边缘遍历音频/视频</span><span class="sxs-lookup"><span data-stu-id="8eaf5-152">AV Edge = Traversal of audio/video via edge</span></span>

<span data-ttu-id="8eaf5-153">AV 身份验证 = 音频/视频身份验证</span><span class="sxs-lookup"><span data-stu-id="8eaf5-153">AV Auth = Audio/Video Authentication</span></span>

<span data-ttu-id="8eaf5-154">SIP 堆栈 = 包含 Lync 的核心 SIP 实现</span><span class="sxs-lookup"><span data-stu-id="8eaf5-154">SIP Stack = Contains Lync’s core SIP implementation</span></span>

<span data-ttu-id="8eaf5-155">数据代理 = 用于边缘会议</span><span class="sxs-lookup"><span data-stu-id="8eaf5-155">Data Proxy = Used for edge conferencing</span></span>

<span data-ttu-id="8eaf5-156">LySS = Lync 存储服务</span><span class="sxs-lookup"><span data-stu-id="8eaf5-156">LySS = Lync Storage Service</span></span>

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a><span data-ttu-id="8eaf5-157">前端服务器</span><span class="sxs-lookup"><span data-stu-id="8eaf5-157">Front-end Servers</span></span>

<span data-ttu-id="8eaf5-158">除了基本组件运行状况之外, 以下建议的 KHI 目标还特定于前端服务器:</span><span class="sxs-lookup"><span data-stu-id="8eaf5-158">The following recommended KHI targets are specific to front-end servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8eaf5-159">功能区域</span><span class="sxs-lookup"><span data-stu-id="8eaf5-159">Functional area</span></span></th>
<th><span data-ttu-id="8eaf5-160">目标指标</span><span class="sxs-lookup"><span data-stu-id="8eaf5-160">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8eaf5-161">AS/AV/IM MCU</span><span class="sxs-lookup"><span data-stu-id="8eaf5-161">AS/AV/IM MCU</span></span></p></td>
<td><p><span data-ttu-id="8eaf5-162">MCU 运行状态&lt;2</span><span class="sxs-lookup"><span data-stu-id="8eaf5-162">MCU Health State &lt;2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8eaf5-163">Web 组件</span><span class="sxs-lookup"><span data-stu-id="8eaf5-163">Web Components</span></span></p></td>
<td><p><span data-ttu-id="8eaf5-164">通讯组列表展开广告&lt;超时0</span><span class="sxs-lookup"><span data-stu-id="8eaf5-164">Distribution List expansion AD timeouts &lt;0</span></span></p>
<p><span data-ttu-id="8eaf5-165">ABWQ 失败 = 0</span><span class="sxs-lookup"><span data-stu-id="8eaf5-165">ABWQ failures = 0</span></span></p>
<p><span data-ttu-id="8eaf5-166">.LIS 故障 = 0</span><span class="sxs-lookup"><span data-stu-id="8eaf5-166">LIS failures = 0</span></span></p>
<p><span data-ttu-id="8eaf5-167">身份验证&lt;错误 1/sec</span><span class="sxs-lookup"><span data-stu-id="8eaf5-167">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="8eaf5-168">ASP.NET v4 请求被拒绝 = 0</span><span class="sxs-lookup"><span data-stu-id="8eaf5-168">ASP.NET v4 Requests Rejected = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8eaf5-169">SIP 堆栈</span><span class="sxs-lookup"><span data-stu-id="8eaf5-169">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="8eaf5-170">平均传入消息处理&lt; 1 秒</span><span class="sxs-lookup"><span data-stu-id="8eaf5-170">Avg. Incoming Message Processing &lt; 1 sec</span></span></p>
<p><span data-ttu-id="8eaf5-171">传入响应丢弃&lt; 1/秒传入的请求&lt;已丢弃 1/秒</span><span class="sxs-lookup"><span data-stu-id="8eaf5-171">Incoming Responses Dropped &lt; 1/sec Incoming Requests Dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="8eaf5-172">队列延迟&lt; 100 ms</span><span class="sxs-lookup"><span data-stu-id="8eaf5-172">Queue Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="8eaf5-173">过程延迟&lt; 100 ms</span><span class="sxs-lookup"><span data-stu-id="8eaf5-173">Sproc Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="8eaf5-174">限制的请求数 = 0</span><span class="sxs-lookup"><span data-stu-id="8eaf5-174">Throttled Requests = 0</span></span></p>
<p><span data-ttu-id="8eaf5-175">身份验证&lt;错误 1/sec</span><span class="sxs-lookup"><span data-stu-id="8eaf5-175">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="8eaf5-176">传入消息超时&lt; 2</span><span class="sxs-lookup"><span data-stu-id="8eaf5-176">Incoming Messages Timed Out &lt; 2</span></span></p>
<p><span data-ttu-id="8eaf5-177">平均传入消息保留&lt; 1 秒</span><span class="sxs-lookup"><span data-stu-id="8eaf5-177">Avg. Incoming Message Hold &lt; 1 sec</span></span></p>
<p><span data-ttu-id="8eaf5-178">流控制的&lt;连接2</span><span class="sxs-lookup"><span data-stu-id="8eaf5-178">Flow Controlled Connections &lt; 2</span></span></p>
<p><span data-ttu-id="8eaf5-179">平均超时排队延迟&lt; 2 秒</span><span class="sxs-lookup"><span data-stu-id="8eaf5-179">Avg. Out Queue Delay &lt; 2 sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8eaf5-180">LySS</span><span class="sxs-lookup"><span data-stu-id="8eaf5-180">LySS</span></span></p></td>
<td><p><span data-ttu-id="8eaf5-181">存储服务数据库&lt; 80 占用的空间百分比</span><span class="sxs-lookup"><span data-stu-id="8eaf5-181">% of space used by Storage Service DB &lt; 80</span></span></p>
<p><span data-ttu-id="8eaf5-182">#复制副本复制失败次数 = 0</span><span class="sxs-lookup"><span data-stu-id="8eaf5-182"># of replica replication failures = 0</span></span></p>
<p><span data-ttu-id="8eaf5-183">#数据丢失事件数 = 0</span><span class="sxs-lookup"><span data-stu-id="8eaf5-183"># of data loss events = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8eaf5-184">SQL</span><span class="sxs-lookup"><span data-stu-id="8eaf5-184">SQL</span></span></p></td>
<td><p><span data-ttu-id="8eaf5-185">页生命预期&gt; 300 秒。</span><span class="sxs-lookup"><span data-stu-id="8eaf5-185">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="8eaf5-186">批处理请求/秒&lt; 2500</span><span class="sxs-lookup"><span data-stu-id="8eaf5-186">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a><span data-ttu-id="8eaf5-187">后端 SQL 服务器</span><span class="sxs-lookup"><span data-stu-id="8eaf5-187">Backend SQL Servers</span></span>

<span data-ttu-id="8eaf5-188">除了基本组件运行状况之外, 以下建议的 KHI 目标还特定于 SQL server:</span><span class="sxs-lookup"><span data-stu-id="8eaf5-188">The following recommended KHI targets are specific to SQL servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8eaf5-189">功能区域</span><span class="sxs-lookup"><span data-stu-id="8eaf5-189">Functional area</span></span></th>
<th><span data-ttu-id="8eaf5-190">目标指标</span><span class="sxs-lookup"><span data-stu-id="8eaf5-190">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8eaf5-191">SQL</span><span class="sxs-lookup"><span data-stu-id="8eaf5-191">SQL</span></span></p></td>
<td><p><span data-ttu-id="8eaf5-192">页生命预期&gt; 300 秒。</span><span class="sxs-lookup"><span data-stu-id="8eaf5-192">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="8eaf5-193">批处理请求/秒&lt; 2500</span><span class="sxs-lookup"><span data-stu-id="8eaf5-193">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a><span data-ttu-id="8eaf5-194">中介服务器</span><span class="sxs-lookup"><span data-stu-id="8eaf5-194">Mediation Servers</span></span>

<span data-ttu-id="8eaf5-195">除了基本组件运行状况之外, 以下建议的 KHI 目标还特定于中介服务器:</span><span class="sxs-lookup"><span data-stu-id="8eaf5-195">The following recommended KHI targets are specific to mediation servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8eaf5-196">功能区域</span><span class="sxs-lookup"><span data-stu-id="8eaf5-196">Functional area</span></span></th>
<th><span data-ttu-id="8eaf5-197">目标指标</span><span class="sxs-lookup"><span data-stu-id="8eaf5-197">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8eaf5-198">中介服务器服务</span><span class="sxs-lookup"><span data-stu-id="8eaf5-198">Mediation Server Service</span></span></p></td>
<td><p><span data-ttu-id="8eaf5-199">加载呼叫失败索引 = 0</span><span class="sxs-lookup"><span data-stu-id="8eaf5-199">Load Call Failure Index = 0</span></span></p>
<p><span data-ttu-id="8eaf5-200">由于代理&lt;10 导致的呼叫失败</span><span class="sxs-lookup"><span data-stu-id="8eaf5-200">Failed Calls due to Proxy &lt;10</span></span></p>
<p><span data-ttu-id="8eaf5-201">由于网关&lt;10 导致的呼叫失败</span><span class="sxs-lookup"><span data-stu-id="8eaf5-201">Failed Calls due to Gateway &lt;10</span></span></p>
<p><span data-ttu-id="8eaf5-202">通话 (拨入或拨出) 被拒绝 = 0</span><span class="sxs-lookup"><span data-stu-id="8eaf5-202">Calls (in or out) rejected = 0</span></span></p>
<p><span data-ttu-id="8eaf5-203">缺少媒体候选人 = 0</span><span class="sxs-lookup"><span data-stu-id="8eaf5-203">Media Candidates missing = 0</span></span></p>
<p><span data-ttu-id="8eaf5-204">媒体连接检查失败 = 0</span><span class="sxs-lookup"><span data-stu-id="8eaf5-204">Media Connectivity Check Failures = 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a><span data-ttu-id="8eaf5-205">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="8eaf5-205">Edge Servers</span></span>

<span data-ttu-id="8eaf5-206">除了基本组件运行状况之外, 以下建议的 KHI 目标还特定于边缘服务器:</span><span class="sxs-lookup"><span data-stu-id="8eaf5-206">The following recommended KHI targets are specific to edge servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8eaf5-207">功能区域</span><span class="sxs-lookup"><span data-stu-id="8eaf5-207">Functional area</span></span></th>
<th><span data-ttu-id="8eaf5-208">目标指标</span><span class="sxs-lookup"><span data-stu-id="8eaf5-208">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8eaf5-209">AV 身份验证</span><span class="sxs-lookup"><span data-stu-id="8eaf5-209">AV Auth</span></span></p></td>
<td><p><span data-ttu-id="8eaf5-210">错误请求&lt; 20/秒</span><span class="sxs-lookup"><span data-stu-id="8eaf5-210">Bad Requests &lt; 20/sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8eaf5-211">AV 边缘</span><span class="sxs-lookup"><span data-stu-id="8eaf5-211">AV Edge</span></span></p></td>
<td><p><span data-ttu-id="8eaf5-212">验证失败&lt;20/秒</span><span class="sxs-lookup"><span data-stu-id="8eaf5-212">Auth. Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="8eaf5-213">分配失败&lt;20/秒</span><span class="sxs-lookup"><span data-stu-id="8eaf5-213">Allocation Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="8eaf5-214">每秒&lt;丢弃的数据包</span><span class="sxs-lookup"><span data-stu-id="8eaf5-214">Packets Dropped &lt;300/sec</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8eaf5-215">数据代理</span><span class="sxs-lookup"><span data-stu-id="8eaf5-215">Data Proxy</span></span></p></td>
<td><p><span data-ttu-id="8eaf5-216">已限制的&lt;服务器连接3</span><span class="sxs-lookup"><span data-stu-id="8eaf5-216">Throttled Server connections &lt; 3</span></span></p>
<p><span data-ttu-id="8eaf5-217">系统为带宽&lt;限制1</span><span class="sxs-lookup"><span data-stu-id="8eaf5-217">System is Throttling &lt;1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8eaf5-218">SIP 堆栈</span><span class="sxs-lookup"><span data-stu-id="8eaf5-218">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="8eaf5-219">超过极限的连接&lt;降1</span><span class="sxs-lookup"><span data-stu-id="8eaf5-219">Connections over limit dropped &lt; 1</span></span></p>
<p><span data-ttu-id="8eaf5-220">发送超时&lt;10</span><span class="sxs-lookup"><span data-stu-id="8eaf5-220">Sends timed out &lt;10</span></span></p>
<p><span data-ttu-id="8eaf5-221">流控制的&lt;连接100</span><span class="sxs-lookup"><span data-stu-id="8eaf5-221">Flow Controlled Connections &lt;100</span></span></p>
<p><span data-ttu-id="8eaf5-222">传入的请求&lt;已丢弃 1/秒</span><span class="sxs-lookup"><span data-stu-id="8eaf5-222">Incoming requests dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="8eaf5-223">平均邮件处理&lt; 3 秒</span><span class="sxs-lookup"><span data-stu-id="8eaf5-223">Avg. Message Processing &lt; 3 sec</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8eaf5-224">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8eaf5-224">See Also</span></span>


[<span data-ttu-id="8eaf5-225">Lync Server 网络指南</span><span class="sxs-lookup"><span data-stu-id="8eaf5-225">Lync Server Networking Guide</span></span>](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="8eaf5-226">关键运行状况指示器: 用于维护正常 Lync 服务器的基础</span><span class="sxs-lookup"><span data-stu-id="8eaf5-226">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](http://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="8eaf5-227">Lync 通话质量方法</span><span class="sxs-lookup"><span data-stu-id="8eaf5-227">Lync Call Quality Methodology</span></span>](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

