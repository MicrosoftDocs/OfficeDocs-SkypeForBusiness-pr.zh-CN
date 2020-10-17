---
title: Lync Server 2013：服务器性能报告
description: Lync Server 2013：服务器性能报告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server Performance Report
ms:assetid: 942bb39a-1790-498e-9d99-8f6ce2d155c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615018(v=OCS.15)
ms:contentKeyID: 48184879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aed9b3b9eeec4487dce4d401df0d70ffba89677b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543338"
---
# <a name="server-performance-report-in-lync-server-2013"></a><span data-ttu-id="b42e5-103">Lync Server 2013 中的服务器性能报告</span><span class="sxs-lookup"><span data-stu-id="b42e5-103">Server Performance Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b42e5-104">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="b42e5-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="b42e5-105">Server Performance Report 提供了 Microsoft Lync Server 2013 服务器的列表，这些服务器已经历最高百分比的较差呼叫。</span><span class="sxs-lookup"><span data-stu-id="b42e5-105">The Server Performance Report provides a list of Microsoft Lync Server 2013 servers that have experienced the highest-percentage of poor calls.</span></span> <span data-ttu-id="b42e5-106">该报告按服务器类型划分服务器，报告针对以下类型的单独统计信息：</span><span class="sxs-lookup"><span data-stu-id="b42e5-106">The report breaks down servers by server type, reporting separate statistics for the following types:</span></span>

  - <span data-ttu-id="b42e5-107">中介服务器</span><span class="sxs-lookup"><span data-stu-id="b42e5-107">Mediation Server</span></span>

  - <span data-ttu-id="b42e5-108">A/V 会议服务器</span><span class="sxs-lookup"><span data-stu-id="b42e5-108">A/V Conferencing Server</span></span>

  - <span data-ttu-id="b42e5-109">A/V 边缘服务器</span><span class="sxs-lookup"><span data-stu-id="b42e5-109">A/V Edge Server</span></span>

  - <span data-ttu-id="b42e5-110">网关（中介服务器）</span><span class="sxs-lookup"><span data-stu-id="b42e5-110">Gateway (Mediation Server)</span></span>

  - <span data-ttu-id="b42e5-111"> (中介服务器旁路) 的网关</span><span class="sxs-lookup"><span data-stu-id="b42e5-111">Gateway (Mediation Server bypass)</span></span>

  - <span data-ttu-id="b42e5-112">视频 (，包括 A/V 会议服务器和 A/V 边缘服务器的视频指标) </span><span class="sxs-lookup"><span data-stu-id="b42e5-112">Video (including video metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

  - <span data-ttu-id="b42e5-113">应用程序共享 (包括 A/V 会议服务器和 A/V 边缘服务器的应用程序共享指标) </span><span class="sxs-lookup"><span data-stu-id="b42e5-113">Application Sharing (including application sharing metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

<span data-ttu-id="b42e5-114">请注意，此报告中显示的排名是相对排名，这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="b42e5-114">It’s important to note that the ranking shown in this report as relative rankings.</span></span> <span data-ttu-id="b42e5-115">例如，假设性能最差的服务器在其1000发出的呼叫中有一个较差的呼叫。</span><span class="sxs-lookup"><span data-stu-id="b42e5-115">For example, suppose your worst-performing server had one poor call among its 1,000 placed calls.</span></span> <span data-ttu-id="b42e5-116">这是一个超过1% 的可接受百分比。</span><span class="sxs-lookup"><span data-stu-id="b42e5-116">That's a more-than-acceptable percentage of .1%.</span></span> <span data-ttu-id="b42e5-117">但是，如果这是您 (的性能最差的服务器，即，如果所有其他服务器的呼叫百分比不低于 .1% ) ，则该服务器将仍显示在服务器性能报告中。</span><span class="sxs-lookup"><span data-stu-id="b42e5-117">However, if that's the worst-performing server you have (that is, if all your other servers have a poor call percentage even lower than .1%), then that server will still appear on the Server Performance Report.</span></span>

<div>

## <a name="accessing-the-server-performance-report"></a><span data-ttu-id="b42e5-118">访问服务器性能报告</span><span class="sxs-lookup"><span data-stu-id="b42e5-118">Accessing the Server Performance Report</span></span>

<span data-ttu-id="b42e5-119">可以从 "监控报告" 主页访问服务器性能报告。</span><span class="sxs-lookup"><span data-stu-id="b42e5-119">The Server Performance Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="b42e5-120">您可以通过单击以下任一指标深入到 [Lync Server 2013 中的呼叫列表报告](lync-server-2013-call-list-report.md) ：</span><span class="sxs-lookup"><span data-stu-id="b42e5-120">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="b42e5-121">呼叫量</span><span class="sxs-lookup"><span data-stu-id="b42e5-121">Call volume</span></span>

  - <span data-ttu-id="b42e5-122">质量欠佳的呼叫百分比</span><span class="sxs-lookup"><span data-stu-id="b42e5-122">Poor call percentage</span></span>

<span data-ttu-id="b42e5-123">此外，您还可以通过单击以下指标深入到 "服务器媒体质量趋势" 报告：</span><span class="sxs-lookup"><span data-stu-id="b42e5-123">In addition, you can drill down to the Server Media Quality Trend Report by clicking the following metric:</span></span>

  - <span data-ttu-id="b42e5-124">趋势</span><span class="sxs-lookup"><span data-stu-id="b42e5-124">Trend</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-server-performance-report"></a><span data-ttu-id="b42e5-125">充分利用服务器性能报告</span><span class="sxs-lookup"><span data-stu-id="b42e5-125">Making the Best Use of the Server Performance Report</span></span>

<span data-ttu-id="b42e5-126">服务器性能报告提供了多种筛选数据的方法;例如，您可以筛选网络类型 (通过有线连接进行的呼叫与从无线连接进行的呼叫) 和访问类型 (从防火墙内部发出的呼叫和从防火墙外) 发出的呼叫。</span><span class="sxs-lookup"><span data-stu-id="b42e5-126">The Server Performance Report provides a number of ways to filter data; for example, you can filter on network type (calls made from a wired connection vs. calls made from a wireless connection) and access type (calls made from inside the firewall vs. calls made from outside the firewall).</span></span> <span data-ttu-id="b42e5-127">查看服务器性能报告以使用这些筛选器是一个不错的主意。</span><span class="sxs-lookup"><span data-stu-id="b42e5-127">It's a good idea when viewing the server performance report to make use of these filters.</span></span> <span data-ttu-id="b42e5-128">例如，假设您的中介服务器的呼叫百分比差为3.24%。</span><span class="sxs-lookup"><span data-stu-id="b42e5-128">For example, suppose you have a Mediation Server that has a poor call percentage of 3.24%.</span></span> <span data-ttu-id="b42e5-129">如果只查看无线呼叫，则同一台服务器可能会有接近20% 的呼叫百分比较差。</span><span class="sxs-lookup"><span data-stu-id="b42e5-129">If you look solely at wireless calls, that same server might have a poor call percentage approaching 20%.</span></span> <span data-ttu-id="b42e5-130">这意味着服务器在无线呼叫中遇到困难，这是由于服务器没有有线呼叫的问题而部分遮住的问题。</span><span class="sxs-lookup"><span data-stu-id="b42e5-130">That means that the server was having difficulty with wireless calls, a problem that is partially obscured because the server was not having problems with wired calls.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="b42e5-131">筛选器</span><span class="sxs-lookup"><span data-stu-id="b42e5-131">Filters</span></span>

<span data-ttu-id="b42e5-132">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。</span><span class="sxs-lookup"><span data-stu-id="b42e5-132">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="b42e5-133">例如，使用 Server Performance Report 可以执行以下操作：按服务器类型或网络类型筛选返回的数据，即有线或无线)  (。</span><span class="sxs-lookup"><span data-stu-id="b42e5-133">For example, the Server Performance Report enables you to do such things as filter the returned data by server type or by network type (that is, wired or wireless).</span></span> <span data-ttu-id="b42e5-134">您还可以选择数据的分组方式。</span><span class="sxs-lookup"><span data-stu-id="b42e5-134">You can also choose how data should be grouped.</span></span> <span data-ttu-id="b42e5-135">在这种情况下，将按小时、日、周或月对数据进行分组。</span><span class="sxs-lookup"><span data-stu-id="b42e5-135">In this case, data is grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="b42e5-136">下表列出了可用于服务器性能报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="b42e5-136">The following table lists the filters that you can use with the Server Performance Report.</span></span>

### <a name="server-performance-report-filters"></a><span data-ttu-id="b42e5-137">服务器性能报告筛选器</span><span class="sxs-lookup"><span data-stu-id="b42e5-137">Server Performance Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b42e5-138">名称</span><span class="sxs-lookup"><span data-stu-id="b42e5-138">Name</span></span></th>
<th><span data-ttu-id="b42e5-139">说明</span><span class="sxs-lookup"><span data-stu-id="b42e5-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b42e5-140"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-140"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-p106">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b42e5-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="b42e5-143">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="b42e5-143">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b42e5-p107">如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="b42e5-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b42e5-146">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b42e5-146">7/7/2012</span></span></p>
<p><span data-ttu-id="b42e5-147">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="b42e5-147">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b42e5-148">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b42e5-148">7/3/2012</span></span></p>
<p><span data-ttu-id="b42e5-149">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="b42e5-149">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b42e5-150"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-150"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-p108">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b42e5-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="b42e5-153">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="b42e5-153">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b42e5-p109">如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="b42e5-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b42e5-156">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b42e5-156">7/7/2012</span></span></p>
<p><span data-ttu-id="b42e5-157">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="b42e5-157">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b42e5-158">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b42e5-158">7/3/2012</span></span></p>
<p><span data-ttu-id="b42e5-159">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="b42e5-159">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b42e5-160"><strong>服务器类型</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-160"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-161">指示应报告其性能的服务器的类型。</span><span class="sxs-lookup"><span data-stu-id="b42e5-161">Indicates the type of server whose performance should be reported.</span></span> <span data-ttu-id="b42e5-162">选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="b42e5-162">Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="b42e5-163">各种</span><span class="sxs-lookup"><span data-stu-id="b42e5-163">[All]</span></span></p></li>
<li><p><span data-ttu-id="b42e5-164">中介服务器</span><span class="sxs-lookup"><span data-stu-id="b42e5-164">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="b42e5-165">A/V 会议服务器</span><span class="sxs-lookup"><span data-stu-id="b42e5-165">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="b42e5-166">A/V 边缘服务器</span><span class="sxs-lookup"><span data-stu-id="b42e5-166">A/V Edge Server</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b42e5-167"><strong>前 N 个</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-167"><strong>Top N</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-168">根据要在每个类别中显示的不好的呼叫百分比) 指示 (的服务器数量。</span><span class="sxs-lookup"><span data-stu-id="b42e5-168">Indicates the number of servers (based on their poor call percentage) to be displayed in each category.</span></span> <span data-ttu-id="b42e5-169">例如，如果选择 " <strong>5</strong> "，则会显示五个 poorest 服务器。</span><span class="sxs-lookup"><span data-stu-id="b42e5-169">For example, if you select <strong>5</strong> then the five poorest-performing servers are displayed.</span></span> <span data-ttu-id="b42e5-170">选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="b42e5-170">Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="b42e5-171">各种</span><span class="sxs-lookup"><span data-stu-id="b42e5-171">[All]</span></span></p></li>
<li><p><span data-ttu-id="b42e5-172">5 </span><span class="sxs-lookup"><span data-stu-id="b42e5-172">5</span></span></p></li>
<li><p><span data-ttu-id="b42e5-173">10  </span><span class="sxs-lookup"><span data-stu-id="b42e5-173">10</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b42e5-174"><strong>访问类型</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-174"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-p112">指示客户端在发起呼叫时已登录到内部网络还是外部网络。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="b42e5-p112">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="b42e5-177">各种</span><span class="sxs-lookup"><span data-stu-id="b42e5-177">[All]</span></span></p></li>
<li><p><span data-ttu-id="b42e5-178">内部</span><span class="sxs-lookup"><span data-stu-id="b42e5-178">Internal</span></span></p></li>
<li><p><span data-ttu-id="b42e5-179">外部</span><span class="sxs-lookup"><span data-stu-id="b42e5-179">External</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b42e5-180"><strong>网络类型</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-180"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-p113">指示客户端在发起呼叫时已连接到的网络的类型。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="b42e5-p113">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="b42e5-183">各种</span><span class="sxs-lookup"><span data-stu-id="b42e5-183">[All]</span></span></p></li>
<li><p><span data-ttu-id="b42e5-184">有线</span><span class="sxs-lookup"><span data-stu-id="b42e5-184">Wired</span></span></p></li>
<li><p><span data-ttu-id="b42e5-185">无线</span><span class="sxs-lookup"><span data-stu-id="b42e5-185">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b42e5-186"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-186"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-p114">指示外部客户端在发起呼叫时是否使用了虚拟专用网 (VPN) 连接。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="b42e5-p114">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="b42e5-189">各种</span><span class="sxs-lookup"><span data-stu-id="b42e5-189">[All]</span></span></p></li>
<li><p><span data-ttu-id="b42e5-190">VPN</span><span class="sxs-lookup"><span data-stu-id="b42e5-190">VPN</span></span></p></li>
<li><p><span data-ttu-id="b42e5-191">非 VPN</span><span class="sxs-lookup"><span data-stu-id="b42e5-191">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="b42e5-192">指标</span><span class="sxs-lookup"><span data-stu-id="b42e5-192">Metrics</span></span>

<span data-ttu-id="b42e5-193">下表列出了服务器性能报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="b42e5-193">The following table lists the information provided in the Server Performance Report.</span></span>

### <a name="server-performance-report-metrics-audio-call-summary"></a><span data-ttu-id="b42e5-194">服务器性能报告指标：音频呼叫摘要</span><span class="sxs-lookup"><span data-stu-id="b42e5-194">Server Performance Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b42e5-195">名称</span><span class="sxs-lookup"><span data-stu-id="b42e5-195">Name</span></span></th>
<th><span data-ttu-id="b42e5-196">可以按</span><span class="sxs-lookup"><span data-stu-id="b42e5-196">Can Sort On</span></span></th>
<th><span data-ttu-id="b42e5-197">说明</span><span class="sxs-lookup"><span data-stu-id="b42e5-197">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b42e5-198"><strong>Server</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-198"><strong>Server</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-199">否</span><span class="sxs-lookup"><span data-stu-id="b42e5-199">No</span></span></p></td>
<td><p><span data-ttu-id="b42e5-200">服务器的名称/IP 地址。</span><span class="sxs-lookup"><span data-stu-id="b42e5-200">Name/IP address of the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b42e5-201"><strong>呼叫量</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-201"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-202">否</span><span class="sxs-lookup"><span data-stu-id="b42e5-202">No</span></span></p></td>
<td><p><span data-ttu-id="b42e5-203">发出的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="b42e5-203">Total number of calls made.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b42e5-204"><strong>质量欠佳的呼叫百分比</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-204"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-205">否</span><span class="sxs-lookup"><span data-stu-id="b42e5-205">No</span></span></p></td>
<td><p><span data-ttu-id="b42e5-p115">归类为质量欠佳的呼叫的总数。质量欠佳的呼叫是指至少一项测量指标超过允许的值的任何呼叫（例如，信号极不稳定的呼叫）。</span><span class="sxs-lookup"><span data-stu-id="b42e5-p115">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b42e5-208"><strong>来回行程(毫秒)</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-208"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-209">是</span><span class="sxs-lookup"><span data-stu-id="b42e5-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="b42e5-p116">实时传输协议 (RTP) 数据包来往于另一个终结点所需的平均时间量（以毫秒为单位）。来回行程的时间小于或等于 100 毫秒被视为质量可接受。</span><span class="sxs-lookup"><span data-stu-id="b42e5-p116">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="b42e5-p117">高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。</span><span class="sxs-lookup"><span data-stu-id="b42e5-p117">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b42e5-214"><strong>性能降低(MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-214"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-215">是</span><span class="sxs-lookup"><span data-stu-id="b42e5-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="b42e5-216">呼叫过程中遇到的性能降低的平均意见得分 (MOS) 的平均值。</span><span class="sxs-lookup"><span data-stu-id="b42e5-216">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="b42e5-217">性能降低值的范围介于 0.0 和 5.0 之间。</span><span class="sxs-lookup"><span data-stu-id="b42e5-217">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="b42e5-218">该值小于或等于 0.5 表示可接受的性能降低。</span><span class="sxs-lookup"><span data-stu-id="b42e5-218">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="b42e5-219">过去，平均意见得分是通过让用户对呼叫质量进行评级（范围为 1 到 5）来计算得出的。</span><span class="sxs-lookup"><span data-stu-id="b42e5-219">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="b42e5-220">在 Lync Server 中，监视服务器使用一组算法来预测用户对呼叫进行评级的方式。</span><span class="sxs-lookup"><span data-stu-id="b42e5-220">In Lync Server, the Monitoring Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="b42e5-p119">高性能降低值可能是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器或终结点超载造成的，从而导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="b42e5-p119">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b42e5-223"><strong>数据包丢失</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-223"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-224">是</span><span class="sxs-lookup"><span data-stu-id="b42e5-224">Yes</span></span></p></td>
<td><p><span data-ttu-id="b42e5-225">实时传输协议 (RTP) 数据包丢失的平均速率。</span><span class="sxs-lookup"><span data-stu-id="b42e5-225">Average rate of real-time transport protocol (RTP) packet loss.</span></span> <span data-ttu-id="b42e5-226">当 RTP 数据包（用于通过 Internet 传输音频和视频的协议）无法到达其目标时，会发生 (数据包丢失。 ) 高丢失率通常是由拥塞、缺少带宽、无线拥塞或干扰或过载的媒体服务器造成的。</span><span class="sxs-lookup"><span data-stu-id="b42e5-226">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server.</span></span> <span data-ttu-id="b42e5-227">数据包丢失通常导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="b42e5-227">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b42e5-228"><strong>抖动(毫秒)</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-228"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-229">是</span><span class="sxs-lookup"><span data-stu-id="b42e5-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="b42e5-230">在 RTP 数据包到达之间检查到的平均抖动率。</span><span class="sxs-lookup"><span data-stu-id="b42e5-230">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="b42e5-231"> (抖动是 shakiness 的衡量指标 &quot; &quot; 。 ) 高抖动值通常由拥塞或过载的媒体服务器引起，并导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="b42e5-231">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b42e5-232"><strong>修复程序隐藏比率</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-232"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-233">是</span><span class="sxs-lookup"><span data-stu-id="b42e5-233">Yes</span></span></p></td>
<td><p><span data-ttu-id="b42e5-p122">隐藏的音频样本与样本总数的平均比率。（隐藏的音频样本是一项技术，用于消除通常由丢弃的网络数据包造成的意外转换。）高值指示数据包丢失或抖动造成的显著的丢失隐藏级别，从而导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="b42e5-p122">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b42e5-236"><strong>修复程序拉伸比率</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-236"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-237">是</span><span class="sxs-lookup"><span data-stu-id="b42e5-237">Yes</span></span></p></td>
<td><p><span data-ttu-id="b42e5-p123">拉伸的音频样本数与样本总数的平均比率。（拉伸的音频是一类已扩展的音频，可在检测到丢弃的网络数据包时帮助保持呼叫质量。）高值指示抖动造成的显著的样本拉伸级别，从而导致音频听起来很机械或失真。</span><span class="sxs-lookup"><span data-stu-id="b42e5-p123">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b42e5-240"><strong>修复程序压缩比率</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-240"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-241">是</span><span class="sxs-lookup"><span data-stu-id="b42e5-241">Yes</span></span></p></td>
<td><p><span data-ttu-id="b42e5-p124">压缩的音频样本与样本总数的平均比率。（压缩的音频是一类已压缩的音频，可在检测到丢弃的网络数据包时帮助保持呼叫质量。）高值指示抖动造成的显著的样本压缩级别，从而导致音频听起来像是已加速或失真。</span><span class="sxs-lookup"><span data-stu-id="b42e5-p124">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-video-call-summary"></a><span data-ttu-id="b42e5-244">服务器性能报告指标：视频呼叫摘要</span><span class="sxs-lookup"><span data-stu-id="b42e5-244">Server Performance Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b42e5-245">名称</span><span class="sxs-lookup"><span data-stu-id="b42e5-245">Name</span></span></th>
<th><span data-ttu-id="b42e5-246">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="b42e5-246">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b42e5-247">说明</span><span class="sxs-lookup"><span data-stu-id="b42e5-247">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b42e5-248"><strong>呼叫类型/终结点类型</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-248"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-249">否</span><span class="sxs-lookup"><span data-stu-id="b42e5-249">No</span></span></p></td>
<td><p><span data-ttu-id="b42e5-p125">当您单击此项时，该报告会显示有关基于这个类型的呼叫的详细信息。呼叫类型包括：</span><span class="sxs-lookup"><span data-stu-id="b42e5-p125">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="b42e5-252">UC 对等呼叫</span><span class="sxs-lookup"><span data-stu-id="b42e5-252">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="b42e5-253">UC 会议会话</span><span class="sxs-lookup"><span data-stu-id="b42e5-253">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="b42e5-254">PSTN 会议会话</span><span class="sxs-lookup"><span data-stu-id="b42e5-254">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="b42e5-255">PSTN 呼叫: 媒体旁路</span><span class="sxs-lookup"><span data-stu-id="b42e5-255">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="b42e5-256">PSTN 呼叫(无旁路): UC 线路</span><span class="sxs-lookup"><span data-stu-id="b42e5-256">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="b42e5-257">PSTN 呼叫(无旁路): 网关线路</span><span class="sxs-lookup"><span data-stu-id="b42e5-257">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="b42e5-258">其他呼叫类型</span><span class="sxs-lookup"><span data-stu-id="b42e5-258">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b42e5-259"><strong>呼叫量</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-259"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-260">否</span><span class="sxs-lookup"><span data-stu-id="b42e5-260">No</span></span></p></td>
<td><p><span data-ttu-id="b42e5-261">每个呼叫类型的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="b42e5-261">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b42e5-262"><strong>质量欠佳的呼叫百分比</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-262"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-263">否</span><span class="sxs-lookup"><span data-stu-id="b42e5-263">No</span></span></p></td>
<td><p><span data-ttu-id="b42e5-p126">归类为质量欠佳的呼叫的总数。质量欠佳的呼叫是指至少一项测量指标超过允许的值的任何呼叫（例如，信号极不稳定的呼叫）。</span><span class="sxs-lookup"><span data-stu-id="b42e5-p126">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b42e5-266"><strong>呼叫量(无线呼叫)</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-266"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-267">否</span><span class="sxs-lookup"><span data-stu-id="b42e5-267">No</span></span></p></td>
<td><p><span data-ttu-id="b42e5-268">使用了无线连接的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="b42e5-268">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b42e5-269"><strong>呼叫量(VPN 呼叫)</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-269"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-270">否</span><span class="sxs-lookup"><span data-stu-id="b42e5-270">No</span></span></p></td>
<td><p><span data-ttu-id="b42e5-271">使用了 VPN 连接的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="b42e5-271">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b42e5-272"><strong>呼叫量(外部呼叫)</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-272"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-273">否</span><span class="sxs-lookup"><span data-stu-id="b42e5-273">No</span></span></p></td>
<td><p><span data-ttu-id="b42e5-274">使用了外部连接（即内部网络外部的连接）的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="b42e5-274">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b42e5-275"><strong>平均比特率(Kb/s)</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-275"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-276">否</span><span class="sxs-lookup"><span data-stu-id="b42e5-276">No</span></span></p></td>
<td><p><span data-ttu-id="b42e5-277">平均视频比特率 (Kb/s)。</span><span class="sxs-lookup"><span data-stu-id="b42e5-277">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b42e5-278"><strong>低比特率百分比</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-278"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-279">否</span><span class="sxs-lookup"><span data-stu-id="b42e5-279">No</span></span></p></td>
<td><p><span data-ttu-id="b42e5-280">比特率较低的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="b42e5-280">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b42e5-281"><strong>出站数据包丢失</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-281"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-282">否</span><span class="sxs-lookup"><span data-stu-id="b42e5-282">No</span></span></p></td>
<td><p><span data-ttu-id="b42e5-283">出站数据包的实时传输协议 (RTP) 数据包丢失率。</span><span class="sxs-lookup"><span data-stu-id="b42e5-283">Real-Time Transport Protocol (RTP) packet loss for outbound packets.</span></span> <span data-ttu-id="b42e5-284">如果 RTP 数据包（用于通过 Internet 传输音频和视频的协议）无法到达其目标，则会发生 (数据包丢失。 ) 高丢失率通常是由拥塞造成的;缺少带宽;无线拥塞或干扰;或重载的媒体服务器。</span><span class="sxs-lookup"><span data-stu-id="b42e5-284">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="b42e5-285">数据包丢失通常导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="b42e5-285">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b42e5-286"><strong>冻结帧百分比</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-286"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-287">否</span><span class="sxs-lookup"><span data-stu-id="b42e5-287">No</span></span></p></td>
<td><p><span data-ttu-id="b42e5-p128">“冻结”帧的百分比。在一个冻结帧中，视频将停止前进，而呼叫的音频部分将继续。</span><span class="sxs-lookup"><span data-stu-id="b42e5-p128">Percentage of “frozen” frames. In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b42e5-290"><strong>出站平均帧速率</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-290"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-291">否</span><span class="sxs-lookup"><span data-stu-id="b42e5-291">No</span></span></p></td>
<td><p><span data-ttu-id="b42e5-292">呼叫期间的出站传输的平均帧速率。</span><span class="sxs-lookup"><span data-stu-id="b42e5-292">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b42e5-293"><strong>入站平均帧速率</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-293"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-294">否</span><span class="sxs-lookup"><span data-stu-id="b42e5-294">No</span></span></p></td>
<td><p><span data-ttu-id="b42e5-295">呼叫期间的入站传输的平均帧速率。</span><span class="sxs-lookup"><span data-stu-id="b42e5-295">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b42e5-296"><strong>入站低帧速率(%)</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-296"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-297">否</span><span class="sxs-lookup"><span data-stu-id="b42e5-297">No</span></span></p></td>
<td><p><span data-ttu-id="b42e5-298">传入视频的比特率较低的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="b42e5-298">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b42e5-299"><strong>客户端健康状态百分比</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-299"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b42e5-300">指示呼叫期间客户端设备的相对健康状态。</span><span class="sxs-lookup"><span data-stu-id="b42e5-300">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="b42e5-301">服务器性能报告指标：应用程序共享呼叫摘要</span><span class="sxs-lookup"><span data-stu-id="b42e5-301">Server Performance Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b42e5-302">名称</span><span class="sxs-lookup"><span data-stu-id="b42e5-302">Name</span></span></th>
<th><span data-ttu-id="b42e5-303">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="b42e5-303">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b42e5-304">说明</span><span class="sxs-lookup"><span data-stu-id="b42e5-304">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b42e5-305"><strong>呼叫类型/终结点类型</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-305"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-306">否</span><span class="sxs-lookup"><span data-stu-id="b42e5-306">No</span></span></p></td>
<td><p><span data-ttu-id="b42e5-p129">当您单击此项时，该报告会显示有关基于这个类型的呼叫的详细信息。呼叫类型包括：</span><span class="sxs-lookup"><span data-stu-id="b42e5-p129">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="b42e5-309">UC 对等呼叫</span><span class="sxs-lookup"><span data-stu-id="b42e5-309">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="b42e5-310">UC 会议会话</span><span class="sxs-lookup"><span data-stu-id="b42e5-310">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="b42e5-311">PSTN 会议会话</span><span class="sxs-lookup"><span data-stu-id="b42e5-311">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="b42e5-312">PSTN 呼叫: 媒体旁路</span><span class="sxs-lookup"><span data-stu-id="b42e5-312">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="b42e5-313">PSTN 呼叫(无旁路): UC 线路</span><span class="sxs-lookup"><span data-stu-id="b42e5-313">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="b42e5-314">PSTN 呼叫(无旁路): 网关线路</span><span class="sxs-lookup"><span data-stu-id="b42e5-314">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="b42e5-315">其他呼叫类型</span><span class="sxs-lookup"><span data-stu-id="b42e5-315">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b42e5-316"><strong>呼叫量</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-316"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-317">否</span><span class="sxs-lookup"><span data-stu-id="b42e5-317">No</span></span></p></td>
<td><p><span data-ttu-id="b42e5-318">每个呼叫类型的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="b42e5-318">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b42e5-319"><strong>质量欠佳的呼叫百分比</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-319"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-320">否</span><span class="sxs-lookup"><span data-stu-id="b42e5-320">No</span></span></p></td>
<td><p><span data-ttu-id="b42e5-p130">归类为质量欠佳的呼叫的总数。质量欠佳的呼叫是指至少一项测量指标超过允许的值的任何呼叫（例如，信号极不稳定的呼叫）。</span><span class="sxs-lookup"><span data-stu-id="b42e5-p130">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b42e5-323"><strong>呼叫量(无线呼叫)</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-323"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-324">否</span><span class="sxs-lookup"><span data-stu-id="b42e5-324">No</span></span></p></td>
<td><p><span data-ttu-id="b42e5-325">使用了无线连接的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="b42e5-325">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b42e5-326"><strong>呼叫量(VPN 呼叫)</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-326"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-327">否</span><span class="sxs-lookup"><span data-stu-id="b42e5-327">No</span></span></p></td>
<td><p><span data-ttu-id="b42e5-328">使用了 VPN 连接的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="b42e5-328">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b42e5-329"><strong>呼叫量(外部呼叫)</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-329"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-330">否</span><span class="sxs-lookup"><span data-stu-id="b42e5-330">No</span></span></p></td>
<td><p><span data-ttu-id="b42e5-331">使用了外部连接（即内部网络外部的连接）的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="b42e5-331">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b42e5-332"><strong>抖动(毫秒)</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-332"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-333">否</span><span class="sxs-lookup"><span data-stu-id="b42e5-333">No</span></span></p></td>
<td><p><span data-ttu-id="b42e5-334">在 RTP 数据包到达之间检查到的平均抖动率。</span><span class="sxs-lookup"><span data-stu-id="b42e5-334">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="b42e5-335"> (抖动是 shakiness 的衡量指标 &quot; &quot; 。 ) 高抖动值通常由拥塞或过载的媒体服务器引起，并导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="b42e5-335">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b42e5-336"><strong>相对单向平均值</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-336"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-337">否</span><span class="sxs-lookup"><span data-stu-id="b42e5-337">No</span></span></p></td>
<td><p><span data-ttu-id="b42e5-p132">两个媒体终结点之间的平均相对单向延迟。这是单跃点延迟度量。</span><span class="sxs-lookup"><span data-stu-id="b42e5-p132">Average relative one-way delay between two media endpoints. This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b42e5-340"><strong>平均 RDP 图块处理延迟</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-340"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-341">否</span><span class="sxs-lookup"><span data-stu-id="b42e5-341">No</span></span></p></td>
<td><p><span data-ttu-id="b42e5-p133">查看会话持续时间内 AS 会议服务器中的平均 RDP 图块处理延迟。此指标不涉及网络延迟。高平均值反映了查看体验中的延迟较长。过载的会议服务器可能会遇到更长的平均延迟。</span><span class="sxs-lookup"><span data-stu-id="b42e5-p133">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session. This metric does not cover network latency. A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b42e5-346"><strong>总损坏图块百分比</strong></span><span class="sxs-lookup"><span data-stu-id="b42e5-346"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="b42e5-347">否</span><span class="sxs-lookup"><span data-stu-id="b42e5-347">No</span></span></p></td>
<td><p><span data-ttu-id="b42e5-348">已损坏 RDP 图块的总百分比。</span><span class="sxs-lookup"><span data-stu-id="b42e5-348">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

