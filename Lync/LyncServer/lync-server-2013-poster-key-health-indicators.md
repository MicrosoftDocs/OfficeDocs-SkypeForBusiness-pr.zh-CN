---
title: Lync Server 2013：海报：关键运行状况指示器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Poster: Key Health Indicators'
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6db6a701c98a44b042d9ee36d0a749bf6363bd2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513379"
---
# <a name="key-health-indicators-in-lync-server-2013"></a><span data-ttu-id="b5607-102">Lync Server 2013 中的关键运行状况指示器</span><span class="sxs-lookup"><span data-stu-id="b5607-102">Key Health Indicators in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5607-103">_**上次修改的主题：** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="b5607-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="b5607-104">本文是与 [关键运行状况指示器的伴随：维护正常的 Lync server 海报的基础](https://go.microsoft.com/fwlink/?linkid=391838) ，可以从下载中心下载。</span><span class="sxs-lookup"><span data-stu-id="b5607-104">This article is a companion to the [Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers](https://go.microsoft.com/fwlink/?linkid=391838) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="b5607-105">![描述使用 KHI 数据进行故障排除的海报](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "描述使用 KHI 数据进行故障排除的海报")</span><span class="sxs-lookup"><span data-stu-id="b5607-105">![Poster describing troubleshooting using KHI data](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster describing troubleshooting using KHI data")</span></span>

<span data-ttu-id="b5607-106">您可以使用此海报了解 (KHIs) 的关键运行状况指示器、性能计数器以及旨在暴露用户体验问题的阈值。</span><span class="sxs-lookup"><span data-stu-id="b5607-106">You can use this poster to learn about Key Health Indicators (KHIs), performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="b5607-107">收集 KHI 数据通常是实施呼叫质量方法 (CQM) 的第一步，该方法主要用于确保 Lync 用户的音质音频体验。</span><span class="sxs-lookup"><span data-stu-id="b5607-107">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="b5607-108">如果您对如何使用 CQM 有疑问，可以将问题提交到 cqmfeedback@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="b5607-108">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="b5607-109">海报对以下方面进行了说明：</span><span class="sxs-lookup"><span data-stu-id="b5607-109">The poster explains the following areas:</span></span>

  - <span data-ttu-id="b5607-110">关键运行状况指示器是什么？</span><span class="sxs-lookup"><span data-stu-id="b5607-110">What are Key Health Indicators?</span></span>

  - <span data-ttu-id="b5607-111">收集 KHI 数据</span><span class="sxs-lookup"><span data-stu-id="b5607-111">To Collect KHI Data</span></span>

  - <span data-ttu-id="b5607-112">所有服务器角色的修正流</span><span class="sxs-lookup"><span data-stu-id="b5607-112">Remediation Flow for all Server Roles</span></span>

  - <span data-ttu-id="b5607-113">术语表</span><span class="sxs-lookup"><span data-stu-id="b5607-113">Glossary</span></span>

  - <span data-ttu-id="b5607-114">前端服务器</span><span class="sxs-lookup"><span data-stu-id="b5607-114">Front-end Servers</span></span>

  - <span data-ttu-id="b5607-115">后端 SQL 服务器</span><span class="sxs-lookup"><span data-stu-id="b5607-115">Backend SQL Servers</span></span>

  - <span data-ttu-id="b5607-116">中介服务器</span><span class="sxs-lookup"><span data-stu-id="b5607-116">Mediation Servers</span></span>

  - <span data-ttu-id="b5607-117">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="b5607-117">Edge Servers</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a><span data-ttu-id="b5607-118">关键运行状况指示器是什么？</span><span class="sxs-lookup"><span data-stu-id="b5607-118">What are Key Health Indicators?</span></span>

<span data-ttu-id="b5607-119">关键运行状况指示器是性能计数器，其阈值旨在暴露用户体验问题。</span><span class="sxs-lookup"><span data-stu-id="b5607-119">Key Health Indicators are performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="b5607-120">收集 KHI 数据通常是实施呼叫质量方法 (CQM) 的第一步，该方法主要用于确保 Lync 用户的音质音频体验。</span><span class="sxs-lookup"><span data-stu-id="b5607-120">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="b5607-121">除了 KHIs 标准 Lync 监视 (解决方案之外，还使用，例如 System Center Operations Manager、综合事务、监视服务器) 而不是这些解决方案。</span><span class="sxs-lookup"><span data-stu-id="b5607-121">KHIs are used in addition to standard Lync Monitoring Solutions (e.g. System Center Operations Manager, Synthetic Transactions, Monitoring Server) and not instead of those solutions.</span></span>

<span data-ttu-id="b5607-122">收集 KHI 性能计数器，并填充 "网络指南" 附带的 KHI 电子表格，以生成可帮助您确定 Lync 部署的服务器运行状况的记分卡。</span><span class="sxs-lookup"><span data-stu-id="b5607-122">Collect the KHI performance counters and populate the KHI spreadsheet accompanying the Networking Guide to produce a scorecard that will help you determine the server health of a Lync deployment.</span></span> <span data-ttu-id="b5607-123">填充后，它将指导您修复环境，并向其他利益干系人提供进一步的洞察力。</span><span class="sxs-lookup"><span data-stu-id="b5607-123">Once populated, it guides you in repairing the environment and gives additional insight to other stakeholders.</span></span> <span data-ttu-id="b5607-124">按月评估 KHIs，并将其合并到任何部署的日常操作过程中。</span><span class="sxs-lookup"><span data-stu-id="b5607-124">Evaluate KHIs on a monthly basis and incorporate them into any deployment’s ongoing operational processes.</span></span>

<span data-ttu-id="b5607-125">下载 [Lync Server 网络指南](https://go.microsoft.com/fwlink/p/?linkid=390677) 以查看完整的 KHIs 列表，并获取相关的电子表格。</span><span class="sxs-lookup"><span data-stu-id="b5607-125">Download the [Lync Server Networking Guide](https://go.microsoft.com/fwlink/p/?linkid=390677) to see the full list of KHIs and to get the related spreadsheets.</span></span>

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a><span data-ttu-id="b5607-126">收集 KHI 数据</span><span class="sxs-lookup"><span data-stu-id="b5607-126">To Collect KHI Data</span></span>

1.  <span data-ttu-id="b5607-127">在每个 Lync Server 上运行 Lync Server 网络指南附带的 KHI 脚本。</span><span class="sxs-lookup"><span data-stu-id="b5607-127">Run the KHI script included with the Lync Server Networking Guide on each Lync Server.</span></span> <span data-ttu-id="b5607-128">这将在性能监视器中创建一个数据收集器，并将其命名为 KHI。</span><span class="sxs-lookup"><span data-stu-id="b5607-128">This will create a Data Collector inside of Performance Monitor and name it KHI.</span></span> <span data-ttu-id="b5607-129">默认情况下，将每15秒轮询一次数据。</span><span class="sxs-lookup"><span data-stu-id="b5607-129">By default, data will be polled every 15 seconds.</span></span>

2.  <span data-ttu-id="b5607-130">在公司的工作日开始之前，请转到每个 Lync Server 并启动 KHI 数据收集器。</span><span class="sxs-lookup"><span data-stu-id="b5607-130">Before the start of your company's business day, go to each Lync Server and start the KHI Data Collector.</span></span>

3.  <span data-ttu-id="b5607-131">在那天结束时，停止 KHI 数据收集器并将数据复制到一个中心位置。</span><span class="sxs-lookup"><span data-stu-id="b5607-131">At the end of that day, stop the KHI Data Collector and copy the data to a central location.</span></span>

4.  <span data-ttu-id="b5607-132">使用性能监视器填充 Lync Server 网络指南中附带的 KHI 电子表格后，将结果与建议的目标进行比较。</span><span class="sxs-lookup"><span data-stu-id="b5607-132">After using Performance Monitor to fill in the KHI spreadsheet included with the Lync Server Networking Guide download, compare the results to the recommended targets.</span></span>

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a><span data-ttu-id="b5607-133">所有服务器角色的修正流</span><span class="sxs-lookup"><span data-stu-id="b5607-133">Remediation Flow for all Server Roles</span></span>

<span data-ttu-id="b5607-134">对于 Lync 实施中的每台服务器，首先验证服务器的组件运行状况和系统性能是否在所需级别或更高级别。</span><span class="sxs-lookup"><span data-stu-id="b5607-134">For each server in your Lync implementation, begin by verifying that the server’s component health and system performance is at or above the desired level.</span></span> <span data-ttu-id="b5607-135">只有在此之后，才应查看整个 Lync 实现中与服务器角色相关的指示器。</span><span class="sxs-lookup"><span data-stu-id="b5607-135">Only after that should you look at the indicators relating to the server’s role in the overall Lync implementation.</span></span>

<span data-ttu-id="b5607-136">首先，收集所有服务器的 KHI 性能数据。</span><span class="sxs-lookup"><span data-stu-id="b5607-136">Begin by collecting KHI Performance Data for all servers.</span></span> <span data-ttu-id="b5607-137">对于每个系统角色 (稍后将在本文档中讨论的详细信息) 确定基本系统组件是否符合建议的目标。</span><span class="sxs-lookup"><span data-stu-id="b5607-137">For each of the system roles (details discussed later in this document) determine whether the basic system components meet the recommended targets.</span></span> <span data-ttu-id="b5607-138">如果没有，则先修正系统性能，然后重新收集 KHI 数据，并确保系统运行状况，然后再在 Lync 实现中查看特定于服务器角色的指标。</span><span class="sxs-lookup"><span data-stu-id="b5607-138">If they do not, remediate the system performance then re-collect KHI data and ensure system health before looking at the metrics specific to the server’s role in the Lync implementation.</span></span> <span data-ttu-id="b5607-139">所有角色的组件运行状况均定义为：</span><span class="sxs-lookup"><span data-stu-id="b5607-139">Component health for all roles is defined as:</span></span>

  - <span data-ttu-id="b5607-140">CPU 使用率 \< 80%</span><span class="sxs-lookup"><span data-stu-id="b5607-140">CPU Utilization \< 80%</span></span>

  - <span data-ttu-id="b5607-141">平均磁盘写入 \< 10 毫秒</span><span class="sxs-lookup"><span data-stu-id="b5607-141">Avg. Disk Write \< 10 ms</span></span>

  - <span data-ttu-id="b5607-142">平均磁盘读取 \< 10 毫秒</span><span class="sxs-lookup"><span data-stu-id="b5607-142">Avg. Disk Read \< 10 ms</span></span>

  - <span data-ttu-id="b5607-143">可用内存 \> 20% 系统总 MB</span><span class="sxs-lookup"><span data-stu-id="b5607-143">Available memory \>20% System Total MB</span></span>

  - <span data-ttu-id="b5607-144">网络队列长度 \< 2</span><span class="sxs-lookup"><span data-stu-id="b5607-144">Network Queue Length \< 2</span></span>

  - <span data-ttu-id="b5607-145"> (in/out 的丢弃数据包) = 0</span><span class="sxs-lookup"><span data-stu-id="b5607-145">Discarded Packets (in / out) = 0</span></span>

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a><span data-ttu-id="b5607-146">术语表</span><span class="sxs-lookup"><span data-stu-id="b5607-146">Glossary</span></span>

<span data-ttu-id="b5607-147">此海报中使用以下术语和首字母缩写词：</span><span class="sxs-lookup"><span data-stu-id="b5607-147">The following terms and acronyms are used in this poster:</span></span>

<span data-ttu-id="b5607-148">AS MCU = 应用程序共享多点控制单元</span><span class="sxs-lookup"><span data-stu-id="b5607-148">AS MCU = Application Sharing Multi-point Control Unit</span></span>

<span data-ttu-id="b5607-149">AV MCU = 音频/视频 MCU</span><span class="sxs-lookup"><span data-stu-id="b5607-149">AV MCU = Audio/Video MCU</span></span>

<span data-ttu-id="b5607-150">IM MCU = 即时消息 MCU</span><span class="sxs-lookup"><span data-stu-id="b5607-150">IM MCU = Instant Messaging MCU</span></span>

<span data-ttu-id="b5607-151">UCWA = 统一通信 Web API</span><span class="sxs-lookup"><span data-stu-id="b5607-151">UCWA = Unified Communications Web API</span></span>

<span data-ttu-id="b5607-152">AV 边缘 = 通过边缘遍历音频/视频</span><span class="sxs-lookup"><span data-stu-id="b5607-152">AV Edge = Traversal of audio/video via edge</span></span>

<span data-ttu-id="b5607-153">AV Auth = 音频/视频身份验证</span><span class="sxs-lookup"><span data-stu-id="b5607-153">AV Auth = Audio/Video Authentication</span></span>

<span data-ttu-id="b5607-154">SIP 堆栈 = 包含 Lync 的核心 SIP 实现</span><span class="sxs-lookup"><span data-stu-id="b5607-154">SIP Stack = Contains Lync’s core SIP implementation</span></span>

<span data-ttu-id="b5607-155">数据代理 = 用于边缘会议</span><span class="sxs-lookup"><span data-stu-id="b5607-155">Data Proxy = Used for edge conferencing</span></span>

<span data-ttu-id="b5607-156">LySS = Lync Storage Service</span><span class="sxs-lookup"><span data-stu-id="b5607-156">LySS = Lync Storage Service</span></span>

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a><span data-ttu-id="b5607-157">前端服务器</span><span class="sxs-lookup"><span data-stu-id="b5607-157">Front-end Servers</span></span>

<span data-ttu-id="b5607-158">除了基本组件运行状况之外，以下建议的 KHI 目标还特定于前端服务器：</span><span class="sxs-lookup"><span data-stu-id="b5607-158">The following recommended KHI targets are specific to front-end servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5607-159">功能区域</span><span class="sxs-lookup"><span data-stu-id="b5607-159">Functional area</span></span></th>
<th><span data-ttu-id="b5607-160">目标指标</span><span class="sxs-lookup"><span data-stu-id="b5607-160">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5607-161">AS/AV/IM MCU</span><span class="sxs-lookup"><span data-stu-id="b5607-161">AS/AV/IM MCU</span></span></p></td>
<td><p><span data-ttu-id="b5607-162">MCU 运行状况状态 &lt; 2</span><span class="sxs-lookup"><span data-stu-id="b5607-162">MCU Health State &lt;2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5607-163">Web 组件</span><span class="sxs-lookup"><span data-stu-id="b5607-163">Web Components</span></span></p></td>
<td><p><span data-ttu-id="b5607-164">通讯组列表展开 AD 超时 &lt; 0</span><span class="sxs-lookup"><span data-stu-id="b5607-164">Distribution List expansion AD timeouts &lt;0</span></span></p>
<p><span data-ttu-id="b5607-165">ABWQ 失败 = 0</span><span class="sxs-lookup"><span data-stu-id="b5607-165">ABWQ failures = 0</span></span></p>
<p><span data-ttu-id="b5607-166">IIS 故障 = 0</span><span class="sxs-lookup"><span data-stu-id="b5607-166">LIS failures = 0</span></span></p>
<p><span data-ttu-id="b5607-167">身份验证错误 &lt; 1/秒</span><span class="sxs-lookup"><span data-stu-id="b5607-167">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="b5607-168">已拒绝的 ASP.NET v4 请求 = 0</span><span class="sxs-lookup"><span data-stu-id="b5607-168">ASP.NET v4 Requests Rejected = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5607-169">SIP 堆栈</span><span class="sxs-lookup"><span data-stu-id="b5607-169">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="b5607-170">平均传入邮件处理 &lt; 1 秒</span><span class="sxs-lookup"><span data-stu-id="b5607-170">Avg. Incoming Message Processing &lt; 1 sec</span></span></p>
<p><span data-ttu-id="b5607-171">传入响应丢弃 &lt; 1/秒传入的请求丢弃 &lt; 1/秒</span><span class="sxs-lookup"><span data-stu-id="b5607-171">Incoming Responses Dropped &lt; 1/sec Incoming Requests Dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="b5607-172">队列延迟 &lt; 100 毫秒</span><span class="sxs-lookup"><span data-stu-id="b5607-172">Queue Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="b5607-173">过程延迟 &lt; 100 毫秒</span><span class="sxs-lookup"><span data-stu-id="b5607-173">Sproc Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="b5607-174">限制的请求数 = 0</span><span class="sxs-lookup"><span data-stu-id="b5607-174">Throttled Requests = 0</span></span></p>
<p><span data-ttu-id="b5607-175">身份验证错误 &lt; 1/秒</span><span class="sxs-lookup"><span data-stu-id="b5607-175">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="b5607-176">传入邮件超时 &lt; 2</span><span class="sxs-lookup"><span data-stu-id="b5607-176">Incoming Messages Timed Out &lt; 2</span></span></p>
<p><span data-ttu-id="b5607-177">平均传入邮件保留 &lt; 1 秒</span><span class="sxs-lookup"><span data-stu-id="b5607-177">Avg. Incoming Message Hold &lt; 1 sec</span></span></p>
<p><span data-ttu-id="b5607-178">流控制的连接 &lt; 2</span><span class="sxs-lookup"><span data-stu-id="b5607-178">Flow Controlled Connections &lt; 2</span></span></p>
<p><span data-ttu-id="b5607-179">平均超时队列延迟 &lt; 2 秒</span><span class="sxs-lookup"><span data-stu-id="b5607-179">Avg. Out Queue Delay &lt; 2 sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5607-180">LySS</span><span class="sxs-lookup"><span data-stu-id="b5607-180">LySS</span></span></p></td>
<td><p><span data-ttu-id="b5607-181">存储服务 DB 80 使用的空间百分比 &lt;</span><span class="sxs-lookup"><span data-stu-id="b5607-181">% of space used by Storage Service DB &lt; 80</span></span></p>
<p><span data-ttu-id="b5607-182"># 副本复制失败的次数 = 0</span><span class="sxs-lookup"><span data-stu-id="b5607-182"># of replica replication failures = 0</span></span></p>
<p><span data-ttu-id="b5607-183"># 数据丢失事件数 = 0</span><span class="sxs-lookup"><span data-stu-id="b5607-183"># of data loss events = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5607-184">SQL</span><span class="sxs-lookup"><span data-stu-id="b5607-184">SQL</span></span></p></td>
<td><p><span data-ttu-id="b5607-185">页生命预期 &gt; 300 秒。</span><span class="sxs-lookup"><span data-stu-id="b5607-185">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="b5607-186">批处理请求数/秒 &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="b5607-186">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a><span data-ttu-id="b5607-187">后端 SQL 服务器</span><span class="sxs-lookup"><span data-stu-id="b5607-187">Backend SQL Servers</span></span>

<span data-ttu-id="b5607-188">除了基本组件运行状况之外，以下建议的 KHI 目标也是特定于 SQL server 的：</span><span class="sxs-lookup"><span data-stu-id="b5607-188">The following recommended KHI targets are specific to SQL servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5607-189">功能区域</span><span class="sxs-lookup"><span data-stu-id="b5607-189">Functional area</span></span></th>
<th><span data-ttu-id="b5607-190">目标指标</span><span class="sxs-lookup"><span data-stu-id="b5607-190">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5607-191">SQL</span><span class="sxs-lookup"><span data-stu-id="b5607-191">SQL</span></span></p></td>
<td><p><span data-ttu-id="b5607-192">页生命预期 &gt; 300 秒。</span><span class="sxs-lookup"><span data-stu-id="b5607-192">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="b5607-193">批处理请求数/秒 &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="b5607-193">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a><span data-ttu-id="b5607-194">中介服务器</span><span class="sxs-lookup"><span data-stu-id="b5607-194">Mediation Servers</span></span>

<span data-ttu-id="b5607-195">除了基本组件运行状况之外，以下建议的 KHI 目标特定于中介服务器：</span><span class="sxs-lookup"><span data-stu-id="b5607-195">The following recommended KHI targets are specific to mediation servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5607-196">功能区域</span><span class="sxs-lookup"><span data-stu-id="b5607-196">Functional area</span></span></th>
<th><span data-ttu-id="b5607-197">目标指标</span><span class="sxs-lookup"><span data-stu-id="b5607-197">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5607-198">中介服务器服务</span><span class="sxs-lookup"><span data-stu-id="b5607-198">Mediation Server Service</span></span></p></td>
<td><p><span data-ttu-id="b5607-199">加载呼叫失败索引 = 0</span><span class="sxs-lookup"><span data-stu-id="b5607-199">Load Call Failure Index = 0</span></span></p>
<p><span data-ttu-id="b5607-200">因代理10导致的失败呼叫 &lt;</span><span class="sxs-lookup"><span data-stu-id="b5607-200">Failed Calls due to Proxy &lt;10</span></span></p>
<p><span data-ttu-id="b5607-201">由于网关10导致的失败呼叫 &lt;</span><span class="sxs-lookup"><span data-stu-id="b5607-201">Failed Calls due to Gateway &lt;10</span></span></p>
<p><span data-ttu-id="b5607-202">调用) 拒绝的 (或传出的 = 0</span><span class="sxs-lookup"><span data-stu-id="b5607-202">Calls (in or out) rejected = 0</span></span></p>
<p><span data-ttu-id="b5607-203">缺少媒体候选人 = 0</span><span class="sxs-lookup"><span data-stu-id="b5607-203">Media Candidates missing = 0</span></span></p>
<p><span data-ttu-id="b5607-204">媒体连接检查故障 = 0</span><span class="sxs-lookup"><span data-stu-id="b5607-204">Media Connectivity Check Failures = 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a><span data-ttu-id="b5607-205">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="b5607-205">Edge Servers</span></span>

<span data-ttu-id="b5607-206">除了基本组件运行状况之外，以下建议的 KHI 目标还特定于边缘服务器：</span><span class="sxs-lookup"><span data-stu-id="b5607-206">The following recommended KHI targets are specific to edge servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5607-207">功能区域</span><span class="sxs-lookup"><span data-stu-id="b5607-207">Functional area</span></span></th>
<th><span data-ttu-id="b5607-208">目标指标</span><span class="sxs-lookup"><span data-stu-id="b5607-208">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5607-209">AV 身份验证</span><span class="sxs-lookup"><span data-stu-id="b5607-209">AV Auth</span></span></p></td>
<td><p><span data-ttu-id="b5607-210">错误请求 &lt; 20/秒</span><span class="sxs-lookup"><span data-stu-id="b5607-210">Bad Requests &lt; 20/sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5607-211">AV 边缘</span><span class="sxs-lookup"><span data-stu-id="b5607-211">AV Edge</span></span></p></td>
<td><p><span data-ttu-id="b5607-212">Auth 失败 &lt; 20/秒</span><span class="sxs-lookup"><span data-stu-id="b5607-212">Auth. Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="b5607-213">分配失败 &lt; 20/秒</span><span class="sxs-lookup"><span data-stu-id="b5607-213">Allocation Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="b5607-214">丢弃 &lt; 300/秒的数据包</span><span class="sxs-lookup"><span data-stu-id="b5607-214">Packets Dropped &lt;300/sec</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5607-215">数据代理</span><span class="sxs-lookup"><span data-stu-id="b5607-215">Data Proxy</span></span></p></td>
<td><p><span data-ttu-id="b5607-216">限制的服务器连接 &lt; 3</span><span class="sxs-lookup"><span data-stu-id="b5607-216">Throttled Server connections &lt; 3</span></span></p>
<p><span data-ttu-id="b5607-217">系统为限制 &lt; 1</span><span class="sxs-lookup"><span data-stu-id="b5607-217">System is Throttling &lt;1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5607-218">SIP 堆栈</span><span class="sxs-lookup"><span data-stu-id="b5607-218">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="b5607-219">超过极限的连接丢弃 &lt; 1</span><span class="sxs-lookup"><span data-stu-id="b5607-219">Connections over limit dropped &lt; 1</span></span></p>
<p><span data-ttu-id="b5607-220">发送超时 &lt; 10</span><span class="sxs-lookup"><span data-stu-id="b5607-220">Sends timed out &lt;10</span></span></p>
<p><span data-ttu-id="b5607-221">流控制的连接 &lt; 100</span><span class="sxs-lookup"><span data-stu-id="b5607-221">Flow Controlled Connections &lt;100</span></span></p>
<p><span data-ttu-id="b5607-222">传入请求丢弃 &lt; 1/秒</span><span class="sxs-lookup"><span data-stu-id="b5607-222">Incoming requests dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="b5607-223">平均邮件处理 &lt; 3 秒</span><span class="sxs-lookup"><span data-stu-id="b5607-223">Avg. Message Processing &lt; 3 sec</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b5607-224">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b5607-224">See Also</span></span>


[<span data-ttu-id="b5607-225">Lync Server 网络指南</span><span class="sxs-lookup"><span data-stu-id="b5607-225">Lync Server Networking Guide</span></span>](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="b5607-226">关键运行状况指示器：用于维护正常运行的 Lync 服务器的基础</span><span class="sxs-lookup"><span data-stu-id="b5607-226">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](https://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="b5607-227">Lync 呼叫质量方法</span><span class="sxs-lookup"><span data-stu-id="b5607-227">Lync Call Quality Methodology</span></span>](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

