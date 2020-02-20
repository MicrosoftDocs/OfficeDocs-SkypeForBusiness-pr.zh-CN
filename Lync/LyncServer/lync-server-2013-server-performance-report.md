---
title: Lync Server 2013：服务器性能报告
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
ms.openlocfilehash: 05c1e366c797eb0c626d00744ef6f0088d28e465
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-performance-report-in-lync-server-2013"></a><span data-ttu-id="b2b94-102">Lync Server 2013 中的服务器性能报告</span><span class="sxs-lookup"><span data-stu-id="b2b94-102">Server Performance Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2b94-103">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="b2b94-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="b2b94-104">Server Performance Report 提供了 Microsoft Lync Server 2013 服务器的列表，这些服务器已经历最高百分比的较差呼叫。</span><span class="sxs-lookup"><span data-stu-id="b2b94-104">The Server Performance Report provides a list of Microsoft Lync Server 2013 servers that have experienced the highest-percentage of poor calls.</span></span> <span data-ttu-id="b2b94-105">该报告按服务器类型划分服务器，报告针对以下类型的单独统计信息：</span><span class="sxs-lookup"><span data-stu-id="b2b94-105">The report breaks down servers by server type, reporting separate statistics for the following types:</span></span>

  - <span data-ttu-id="b2b94-106">中介服务器</span><span class="sxs-lookup"><span data-stu-id="b2b94-106">Mediation Server</span></span>

  - <span data-ttu-id="b2b94-107">A/V 会议服务器</span><span class="sxs-lookup"><span data-stu-id="b2b94-107">A/V Conferencing Server</span></span>

  - <span data-ttu-id="b2b94-108">A/V 边缘服务器</span><span class="sxs-lookup"><span data-stu-id="b2b94-108">A/V Edge Server</span></span>

  - <span data-ttu-id="b2b94-109">网关（中介服务器）</span><span class="sxs-lookup"><span data-stu-id="b2b94-109">Gateway (Mediation Server)</span></span>

  - <span data-ttu-id="b2b94-110">网关（中介服务器旁路）</span><span class="sxs-lookup"><span data-stu-id="b2b94-110">Gateway (Mediation Server bypass)</span></span>

  - <span data-ttu-id="b2b94-111">视频（包括 A/V 会议服务器和 A/V 边缘服务器的视频指标）</span><span class="sxs-lookup"><span data-stu-id="b2b94-111">Video (including video metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

  - <span data-ttu-id="b2b94-112">应用程序共享（包括 A/V 会议服务器和 A/V 边缘服务器的应用程序共享指标）</span><span class="sxs-lookup"><span data-stu-id="b2b94-112">Application Sharing (including application sharing metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

<span data-ttu-id="b2b94-113">请注意，此报告中显示的排名是相对排名，这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="b2b94-113">It’s important to note that the ranking shown in this report as relative rankings.</span></span> <span data-ttu-id="b2b94-114">例如，假设性能最差的服务器在其1000发出的呼叫中有一个较差的呼叫。</span><span class="sxs-lookup"><span data-stu-id="b2b94-114">For example, suppose your worst-performing server had one poor call among its 1,000 placed calls.</span></span> <span data-ttu-id="b2b94-115">这是一个超过1% 的可接受百分比。</span><span class="sxs-lookup"><span data-stu-id="b2b94-115">That's a more-than-acceptable percentage of .1%.</span></span> <span data-ttu-id="b2b94-116">但是，如果这是性能最差的服务器（即，如果所有其他服务器的呼叫百分比低于0.1%），则该服务器将仍显示在服务器性能报告中。</span><span class="sxs-lookup"><span data-stu-id="b2b94-116">However, if that's the worst-performing server you have (that is, if all your other servers have a poor call percentage even lower than .1%), then that server will still appear on the Server Performance Report.</span></span>

<div>

## <a name="accessing-the-server-performance-report"></a><span data-ttu-id="b2b94-117">访问服务器性能报告</span><span class="sxs-lookup"><span data-stu-id="b2b94-117">Accessing the Server Performance Report</span></span>

<span data-ttu-id="b2b94-118">可以从 "监控报告" 主页访问服务器性能报告。</span><span class="sxs-lookup"><span data-stu-id="b2b94-118">The Server Performance Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="b2b94-119">您可以通过单击以下任一指标深入到[Lync Server 2013 中的呼叫列表报告](lync-server-2013-call-list-report.md)：</span><span class="sxs-lookup"><span data-stu-id="b2b94-119">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="b2b94-120">呼叫量</span><span class="sxs-lookup"><span data-stu-id="b2b94-120">Call volume</span></span>

  - <span data-ttu-id="b2b94-121">质量欠佳的呼叫百分比</span><span class="sxs-lookup"><span data-stu-id="b2b94-121">Poor call percentage</span></span>

<span data-ttu-id="b2b94-122">此外，您还可以通过单击以下指标深入到 "服务器媒体质量趋势" 报告：</span><span class="sxs-lookup"><span data-stu-id="b2b94-122">In addition, you can drill down to the Server Media Quality Trend Report by clicking the following metric:</span></span>

  - <span data-ttu-id="b2b94-123">趋势</span><span class="sxs-lookup"><span data-stu-id="b2b94-123">Trend</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-server-performance-report"></a><span data-ttu-id="b2b94-124">充分利用服务器性能报告</span><span class="sxs-lookup"><span data-stu-id="b2b94-124">Making the Best Use of the Server Performance Report</span></span>

<span data-ttu-id="b2b94-125">服务器性能报告提供了多种筛选数据的方法;例如，您可以筛选网络类型（通过有线连接进行的呼叫与从无线连接发出的呼叫）和访问类型（从防火墙内部发出的呼叫与从防火墙外部发出的呼叫）。</span><span class="sxs-lookup"><span data-stu-id="b2b94-125">The Server Performance Report provides a number of ways to filter data; for example, you can filter on network type (calls made from a wired connection vs. calls made from a wireless connection) and access type (calls made from inside the firewall vs. calls made from outside the firewall).</span></span> <span data-ttu-id="b2b94-126">查看服务器性能报告以使用这些筛选器是一个不错的主意。</span><span class="sxs-lookup"><span data-stu-id="b2b94-126">It's a good idea when viewing the server performance report to make use of these filters.</span></span> <span data-ttu-id="b2b94-127">例如，假设您的中介服务器的呼叫百分比差为3.24%。</span><span class="sxs-lookup"><span data-stu-id="b2b94-127">For example, suppose you have a Mediation Server that has a poor call percentage of 3.24%.</span></span> <span data-ttu-id="b2b94-128">如果只查看无线呼叫，则同一台服务器可能会有接近20% 的呼叫百分比较差。</span><span class="sxs-lookup"><span data-stu-id="b2b94-128">If you look solely at wireless calls, that same server might have a poor call percentage approaching 20%.</span></span> <span data-ttu-id="b2b94-129">这意味着服务器在无线呼叫中遇到困难，这是由于服务器没有有线呼叫的问题而部分遮住的问题。</span><span class="sxs-lookup"><span data-stu-id="b2b94-129">That means that the server was having difficulty with wireless calls, a problem that is partially obscured because the server was not having problems with wired calls.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="b2b94-130">筛选器</span><span class="sxs-lookup"><span data-stu-id="b2b94-130">Filters</span></span>

<span data-ttu-id="b2b94-131">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。</span><span class="sxs-lookup"><span data-stu-id="b2b94-131">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="b2b94-132">例如，通过服务器性能报告，您可以按服务器类型或网络类型（即有线或无线）筛选返回的数据，从而执行此操作。</span><span class="sxs-lookup"><span data-stu-id="b2b94-132">For example, the Server Performance Report enables you to do such things as filter the returned data by server type or by network type (that is, wired or wireless).</span></span> <span data-ttu-id="b2b94-133">您还可以选择数据的分组方式。</span><span class="sxs-lookup"><span data-stu-id="b2b94-133">You can also choose how data should be grouped.</span></span> <span data-ttu-id="b2b94-134">在这种情况下，将按小时、日、周或月对数据进行分组。</span><span class="sxs-lookup"><span data-stu-id="b2b94-134">In this case, data is grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="b2b94-135">下表列出了可用于服务器性能报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="b2b94-135">The following table lists the filters that you can use with the Server Performance Report.</span></span>

### <a name="server-performance-report-filters"></a><span data-ttu-id="b2b94-136">服务器性能报告筛选器</span><span class="sxs-lookup"><span data-stu-id="b2b94-136">Server Performance Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2b94-137">名称</span><span class="sxs-lookup"><span data-stu-id="b2b94-137">Name</span></span></th>
<th><span data-ttu-id="b2b94-138">说明</span><span class="sxs-lookup"><span data-stu-id="b2b94-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2b94-139"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-139"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-p106">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b2b94-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="b2b94-142">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="b2b94-142">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b2b94-p107">如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="b2b94-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b2b94-145">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b2b94-145">7/7/2012</span></span></p>
<p><span data-ttu-id="b2b94-146">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="b2b94-146">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b2b94-147">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b2b94-147">7/3/2012</span></span></p>
<p><span data-ttu-id="b2b94-148">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="b2b94-148">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2b94-149"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-149"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-p108">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b2b94-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="b2b94-152">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="b2b94-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b2b94-p109">如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="b2b94-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b2b94-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b2b94-155">7/7/2012</span></span></p>
<p><span data-ttu-id="b2b94-156">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="b2b94-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b2b94-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b2b94-157">7/3/2012</span></span></p>
<p><span data-ttu-id="b2b94-158">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="b2b94-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2b94-159"><strong>服务器类型</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-159"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-160">指示应报告其性能的服务器的类型。</span><span class="sxs-lookup"><span data-stu-id="b2b94-160">Indicates the type of server whose performance should be reported.</span></span> <span data-ttu-id="b2b94-161">选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="b2b94-161">Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="b2b94-162">各种</span><span class="sxs-lookup"><span data-stu-id="b2b94-162">[All]</span></span></p></li>
<li><p><span data-ttu-id="b2b94-163">中介服务器</span><span class="sxs-lookup"><span data-stu-id="b2b94-163">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="b2b94-164">A/V 会议服务器</span><span class="sxs-lookup"><span data-stu-id="b2b94-164">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="b2b94-165">A/V 边缘服务器</span><span class="sxs-lookup"><span data-stu-id="b2b94-165">A/V Edge Server</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2b94-166"><strong>前 N 个</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-166"><strong>Top N</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-167">指示每个类别中显示的服务器数（基于其低呼叫百分比）。</span><span class="sxs-lookup"><span data-stu-id="b2b94-167">Indicates the number of servers (based on their poor call percentage) to be displayed in each category.</span></span> <span data-ttu-id="b2b94-168">例如，如果选择 " <strong>5</strong> "，则会显示五个 poorest 服务器。</span><span class="sxs-lookup"><span data-stu-id="b2b94-168">For example, if you select <strong>5</strong> then the five poorest-performing servers are displayed.</span></span> <span data-ttu-id="b2b94-169">选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="b2b94-169">Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="b2b94-170">各种</span><span class="sxs-lookup"><span data-stu-id="b2b94-170">[All]</span></span></p></li>
<li><p><span data-ttu-id="b2b94-171">5</span><span class="sxs-lookup"><span data-stu-id="b2b94-171">5</span></span></p></li>
<li><p><span data-ttu-id="b2b94-172">10 </span><span class="sxs-lookup"><span data-stu-id="b2b94-172">10</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2b94-173"><strong>访问类型</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-173"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-p112">指示客户端在发起呼叫时已登录到内部网络还是外部网络。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="b2b94-p112">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="b2b94-176">各种</span><span class="sxs-lookup"><span data-stu-id="b2b94-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="b2b94-177">内部</span><span class="sxs-lookup"><span data-stu-id="b2b94-177">Internal</span></span></p></li>
<li><p><span data-ttu-id="b2b94-178">外部</span><span class="sxs-lookup"><span data-stu-id="b2b94-178">External</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2b94-179"><strong>网络类型</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-179"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-p113">指示客户端在发起呼叫时已连接到的网络的类型。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="b2b94-p113">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="b2b94-182">各种</span><span class="sxs-lookup"><span data-stu-id="b2b94-182">[All]</span></span></p></li>
<li><p><span data-ttu-id="b2b94-183">有线</span><span class="sxs-lookup"><span data-stu-id="b2b94-183">Wired</span></span></p></li>
<li><p><span data-ttu-id="b2b94-184">无线</span><span class="sxs-lookup"><span data-stu-id="b2b94-184">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2b94-185"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-185"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-p114">指示外部客户端在发起呼叫时是否使用了虚拟专用网 (VPN) 连接。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="b2b94-p114">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="b2b94-188">各种</span><span class="sxs-lookup"><span data-stu-id="b2b94-188">[All]</span></span></p></li>
<li><p><span data-ttu-id="b2b94-189">VPN</span><span class="sxs-lookup"><span data-stu-id="b2b94-189">VPN</span></span></p></li>
<li><p><span data-ttu-id="b2b94-190">非 VPN</span><span class="sxs-lookup"><span data-stu-id="b2b94-190">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="b2b94-191">指标</span><span class="sxs-lookup"><span data-stu-id="b2b94-191">Metrics</span></span>

<span data-ttu-id="b2b94-192">下表列出了服务器性能报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="b2b94-192">The following table lists the information provided in the Server Performance Report.</span></span>

### <a name="server-performance-report-metrics-audio-call-summary"></a><span data-ttu-id="b2b94-193">服务器性能报告指标：音频呼叫摘要</span><span class="sxs-lookup"><span data-stu-id="b2b94-193">Server Performance Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2b94-194">名称</span><span class="sxs-lookup"><span data-stu-id="b2b94-194">Name</span></span></th>
<th><span data-ttu-id="b2b94-195">可以按</span><span class="sxs-lookup"><span data-stu-id="b2b94-195">Can Sort On</span></span></th>
<th><span data-ttu-id="b2b94-196">说明</span><span class="sxs-lookup"><span data-stu-id="b2b94-196">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2b94-197"><strong>服务器</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-197"><strong>Server</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-198">否</span><span class="sxs-lookup"><span data-stu-id="b2b94-198">No</span></span></p></td>
<td><p><span data-ttu-id="b2b94-199">服务器的名称/IP 地址。</span><span class="sxs-lookup"><span data-stu-id="b2b94-199">Name/IP address of the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2b94-200"><strong>呼叫量</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-200"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-201">否</span><span class="sxs-lookup"><span data-stu-id="b2b94-201">No</span></span></p></td>
<td><p><span data-ttu-id="b2b94-202">发出的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="b2b94-202">Total number of calls made.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2b94-203"><strong>质量欠佳的呼叫百分比</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-203"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-204">否</span><span class="sxs-lookup"><span data-stu-id="b2b94-204">No</span></span></p></td>
<td><p><span data-ttu-id="b2b94-p115">归类为质量欠佳的呼叫的总数。质量欠佳的呼叫是指至少一项测量指标超过允许的值的任何呼叫（例如，信号极不稳定的呼叫）。</span><span class="sxs-lookup"><span data-stu-id="b2b94-p115">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2b94-207"><strong>来回行程(毫秒)</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-207"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-208">是</span><span class="sxs-lookup"><span data-stu-id="b2b94-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="b2b94-p116">实时传输协议 (RTP) 数据包来往于另一个终结点所需的平均时间量（以毫秒为单位）。来回行程的时间小于或等于 100 毫秒被视为质量可接受。</span><span class="sxs-lookup"><span data-stu-id="b2b94-p116">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="b2b94-p117">高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。</span><span class="sxs-lookup"><span data-stu-id="b2b94-p117">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2b94-213"><strong>性能降低(MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-213"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-214">是</span><span class="sxs-lookup"><span data-stu-id="b2b94-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="b2b94-215">呼叫过程中遇到的性能降低的平均意见得分 (MOS) 的平均值。</span><span class="sxs-lookup"><span data-stu-id="b2b94-215">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="b2b94-216">性能降低值的范围介于 0.0 和 5.0 之间。</span><span class="sxs-lookup"><span data-stu-id="b2b94-216">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="b2b94-217">该值小于或等于 0.5 表示可接受的性能降低。</span><span class="sxs-lookup"><span data-stu-id="b2b94-217">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="b2b94-218">过去，平均意见得分是通过让用户对呼叫质量进行评级（范围为 1 到 5）来计算得出的。</span><span class="sxs-lookup"><span data-stu-id="b2b94-218">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="b2b94-219">在 Lync Server 中，监视服务器使用一组算法来预测用户对呼叫进行评级的方式。</span><span class="sxs-lookup"><span data-stu-id="b2b94-219">In Lync Server, the Monitoring Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="b2b94-p119">高性能降低值可能是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器或终结点超载造成的，从而导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="b2b94-p119">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2b94-222"><strong>数据包丢失</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-222"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-223">是</span><span class="sxs-lookup"><span data-stu-id="b2b94-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="b2b94-224">实时传输协议（RTP）数据包丢失的平均速率。</span><span class="sxs-lookup"><span data-stu-id="b2b94-224">Average rate of real-time transport protocol (RTP) packet loss.</span></span> <span data-ttu-id="b2b94-225">（当 RTP 数据包（用于通过 Internet 传输音频和视频的协议）无法到达其目标时，将发生数据包丢失。较高的丢失率通常是由拥塞、带宽不足、无线拥塞或干扰或过载的媒体服务器造成的。</span><span class="sxs-lookup"><span data-stu-id="b2b94-225">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server.</span></span> <span data-ttu-id="b2b94-226">数据包丢失通常导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="b2b94-226">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2b94-227"><strong>抖动(毫秒)</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-227"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-228">是</span><span class="sxs-lookup"><span data-stu-id="b2b94-228">Yes</span></span></p></td>
<td><p><span data-ttu-id="b2b94-229">在 RTP 数据包到达之间检查到的平均抖动率。</span><span class="sxs-lookup"><span data-stu-id="b2b94-229">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="b2b94-230">（抖动是对&quot;shakiness&quot;的衡量。高抖动值通常是由拥塞或过载的媒体服务器引起的，并导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="b2b94-230">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2b94-231"><strong>修复程序隐藏比率</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-231"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-232">是</span><span class="sxs-lookup"><span data-stu-id="b2b94-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="b2b94-p122">隐藏的音频样本与样本总数的平均比率。（隐藏的音频样本是一项技术，用于消除通常由丢弃的网络数据包造成的意外转换。）高值指示数据包丢失或抖动造成的显著的丢失隐藏级别，从而导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="b2b94-p122">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2b94-235"><strong>修复程序拉伸比率</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-235"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-236">是</span><span class="sxs-lookup"><span data-stu-id="b2b94-236">Yes</span></span></p></td>
<td><p><span data-ttu-id="b2b94-p123">拉伸的音频样本数与样本总数的平均比率。（拉伸的音频是一类已扩展的音频，可在检测到丢弃的网络数据包时帮助保持呼叫质量。）高值指示抖动造成的显著的样本拉伸级别，从而导致音频听起来很机械或失真。</span><span class="sxs-lookup"><span data-stu-id="b2b94-p123">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2b94-239"><strong>修复程序压缩比率</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-239"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-240">是</span><span class="sxs-lookup"><span data-stu-id="b2b94-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="b2b94-p124">压缩的音频样本与样本总数的平均比率。（压缩的音频是一类已压缩的音频，可在检测到丢弃的网络数据包时帮助保持呼叫质量。）高值指示抖动造成的显著的样本压缩级别，从而导致音频听起来像是已加速或失真。</span><span class="sxs-lookup"><span data-stu-id="b2b94-p124">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-video-call-summary"></a><span data-ttu-id="b2b94-243">服务器性能报告指标：视频呼叫摘要</span><span class="sxs-lookup"><span data-stu-id="b2b94-243">Server Performance Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2b94-244">名称</span><span class="sxs-lookup"><span data-stu-id="b2b94-244">Name</span></span></th>
<th><span data-ttu-id="b2b94-245">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="b2b94-245">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b2b94-246">说明</span><span class="sxs-lookup"><span data-stu-id="b2b94-246">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2b94-247"><strong>呼叫类型/终结点类型</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-247"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-248">否</span><span class="sxs-lookup"><span data-stu-id="b2b94-248">No</span></span></p></td>
<td><p><span data-ttu-id="b2b94-p125">当您单击此项时，该报告会显示有关基于这个类型的呼叫的详细信息。呼叫类型包括：</span><span class="sxs-lookup"><span data-stu-id="b2b94-p125">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="b2b94-251">UC 对等呼叫</span><span class="sxs-lookup"><span data-stu-id="b2b94-251">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="b2b94-252">UC 会议会话</span><span class="sxs-lookup"><span data-stu-id="b2b94-252">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="b2b94-253">PSTN 会议会话</span><span class="sxs-lookup"><span data-stu-id="b2b94-253">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="b2b94-254">PSTN 呼叫: 媒体旁路</span><span class="sxs-lookup"><span data-stu-id="b2b94-254">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="b2b94-255">PSTN 呼叫(无旁路): UC 线路</span><span class="sxs-lookup"><span data-stu-id="b2b94-255">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="b2b94-256">PSTN 呼叫(无旁路): 网关线路</span><span class="sxs-lookup"><span data-stu-id="b2b94-256">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="b2b94-257">其他呼叫类型</span><span class="sxs-lookup"><span data-stu-id="b2b94-257">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2b94-258"><strong>呼叫量</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-258"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-259">否</span><span class="sxs-lookup"><span data-stu-id="b2b94-259">No</span></span></p></td>
<td><p><span data-ttu-id="b2b94-260">每个呼叫类型的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="b2b94-260">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2b94-261"><strong>质量欠佳的呼叫百分比</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-261"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-262">否</span><span class="sxs-lookup"><span data-stu-id="b2b94-262">No</span></span></p></td>
<td><p><span data-ttu-id="b2b94-p126">归类为质量欠佳的呼叫的总数。质量欠佳的呼叫是指至少一项测量指标超过允许的值的任何呼叫（例如，信号极不稳定的呼叫）。</span><span class="sxs-lookup"><span data-stu-id="b2b94-p126">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2b94-265"><strong>呼叫量(无线呼叫)</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-265"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-266">否</span><span class="sxs-lookup"><span data-stu-id="b2b94-266">No</span></span></p></td>
<td><p><span data-ttu-id="b2b94-267">使用了无线连接的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="b2b94-267">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2b94-268"><strong>呼叫量(VPN 呼叫)</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-268"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-269">否</span><span class="sxs-lookup"><span data-stu-id="b2b94-269">No</span></span></p></td>
<td><p><span data-ttu-id="b2b94-270">使用了 VPN 连接的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="b2b94-270">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2b94-271"><strong>呼叫量(外部呼叫)</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-271"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-272">否</span><span class="sxs-lookup"><span data-stu-id="b2b94-272">No</span></span></p></td>
<td><p><span data-ttu-id="b2b94-273">使用了外部连接（即内部网络外部的连接）的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="b2b94-273">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2b94-274"><strong>平均比特率(Kb/s)</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-274"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-275">否</span><span class="sxs-lookup"><span data-stu-id="b2b94-275">No</span></span></p></td>
<td><p><span data-ttu-id="b2b94-276">平均视频比特率 (Kb/s)。</span><span class="sxs-lookup"><span data-stu-id="b2b94-276">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2b94-277"><strong>低比特率百分比</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-277"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-278">否</span><span class="sxs-lookup"><span data-stu-id="b2b94-278">No</span></span></p></td>
<td><p><span data-ttu-id="b2b94-279">比特率较低的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="b2b94-279">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2b94-280"><strong>出站数据包丢失</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-280"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-281">否</span><span class="sxs-lookup"><span data-stu-id="b2b94-281">No</span></span></p></td>
<td><p><span data-ttu-id="b2b94-282">出站数据包的实时传输协议 (RTP) 数据包丢失率。</span><span class="sxs-lookup"><span data-stu-id="b2b94-282">Real-Time Transport Protocol (RTP) packet loss for outbound packets.</span></span> <span data-ttu-id="b2b94-283">（当 RTP 数据包（用于通过 Internet 传输音频和视频的协议）无法到达其目标时，将发生数据包丢失。较高的丢失率通常是由拥塞引起的;缺少带宽;无线拥塞或干扰;或重载的媒体服务器。</span><span class="sxs-lookup"><span data-stu-id="b2b94-283">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="b2b94-284">数据包丢失通常导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="b2b94-284">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2b94-285"><strong>冻结帧百分比</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-285"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-286">否</span><span class="sxs-lookup"><span data-stu-id="b2b94-286">No</span></span></p></td>
<td><p><span data-ttu-id="b2b94-p128">“冻结”帧的百分比。在一个冻结帧中，视频将停止前进，而呼叫的音频部分将继续。</span><span class="sxs-lookup"><span data-stu-id="b2b94-p128">Percentage of “frozen” frames. In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2b94-289"><strong>出站平均帧速率</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-289"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-290">否</span><span class="sxs-lookup"><span data-stu-id="b2b94-290">No</span></span></p></td>
<td><p><span data-ttu-id="b2b94-291">呼叫期间的出站传输的平均帧速率。</span><span class="sxs-lookup"><span data-stu-id="b2b94-291">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2b94-292"><strong>入站平均帧速率</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-292"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-293">否</span><span class="sxs-lookup"><span data-stu-id="b2b94-293">No</span></span></p></td>
<td><p><span data-ttu-id="b2b94-294">呼叫期间的入站传输的平均帧速率。</span><span class="sxs-lookup"><span data-stu-id="b2b94-294">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2b94-295"><strong>入站低帧速率(%)</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-295"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-296">否</span><span class="sxs-lookup"><span data-stu-id="b2b94-296">No</span></span></p></td>
<td><p><span data-ttu-id="b2b94-297">传入视频的比特率较低的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="b2b94-297">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2b94-298"><strong>客户端健康状态百分比</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-298"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2b94-299">指示呼叫期间客户端设备的相对健康状态。</span><span class="sxs-lookup"><span data-stu-id="b2b94-299">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="b2b94-300">服务器性能报告指标：应用程序共享呼叫摘要</span><span class="sxs-lookup"><span data-stu-id="b2b94-300">Server Performance Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2b94-301">名称</span><span class="sxs-lookup"><span data-stu-id="b2b94-301">Name</span></span></th>
<th><span data-ttu-id="b2b94-302">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="b2b94-302">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b2b94-303">说明</span><span class="sxs-lookup"><span data-stu-id="b2b94-303">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2b94-304"><strong>呼叫类型/终结点类型</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-304"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-305">否</span><span class="sxs-lookup"><span data-stu-id="b2b94-305">No</span></span></p></td>
<td><p><span data-ttu-id="b2b94-p129">当您单击此项时，该报告会显示有关基于这个类型的呼叫的详细信息。呼叫类型包括：</span><span class="sxs-lookup"><span data-stu-id="b2b94-p129">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="b2b94-308">UC 对等呼叫</span><span class="sxs-lookup"><span data-stu-id="b2b94-308">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="b2b94-309">UC 会议会话</span><span class="sxs-lookup"><span data-stu-id="b2b94-309">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="b2b94-310">PSTN 会议会话</span><span class="sxs-lookup"><span data-stu-id="b2b94-310">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="b2b94-311">PSTN 呼叫: 媒体旁路</span><span class="sxs-lookup"><span data-stu-id="b2b94-311">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="b2b94-312">PSTN 呼叫(无旁路): UC 线路</span><span class="sxs-lookup"><span data-stu-id="b2b94-312">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="b2b94-313">PSTN 呼叫(无旁路): 网关线路</span><span class="sxs-lookup"><span data-stu-id="b2b94-313">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="b2b94-314">其他呼叫类型</span><span class="sxs-lookup"><span data-stu-id="b2b94-314">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2b94-315"><strong>呼叫量</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-315"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-316">否</span><span class="sxs-lookup"><span data-stu-id="b2b94-316">No</span></span></p></td>
<td><p><span data-ttu-id="b2b94-317">每个呼叫类型的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="b2b94-317">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2b94-318"><strong>质量欠佳的呼叫百分比</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-318"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-319">否</span><span class="sxs-lookup"><span data-stu-id="b2b94-319">No</span></span></p></td>
<td><p><span data-ttu-id="b2b94-p130">归类为质量欠佳的呼叫的总数。质量欠佳的呼叫是指至少一项测量指标超过允许的值的任何呼叫（例如，信号极不稳定的呼叫）。</span><span class="sxs-lookup"><span data-stu-id="b2b94-p130">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2b94-322"><strong>呼叫量(无线呼叫)</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-322"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-323">否</span><span class="sxs-lookup"><span data-stu-id="b2b94-323">No</span></span></p></td>
<td><p><span data-ttu-id="b2b94-324">使用了无线连接的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="b2b94-324">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2b94-325"><strong>呼叫量(VPN 呼叫)</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-325"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-326">否</span><span class="sxs-lookup"><span data-stu-id="b2b94-326">No</span></span></p></td>
<td><p><span data-ttu-id="b2b94-327">使用了 VPN 连接的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="b2b94-327">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2b94-328"><strong>呼叫量(外部呼叫)</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-328"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-329">否</span><span class="sxs-lookup"><span data-stu-id="b2b94-329">No</span></span></p></td>
<td><p><span data-ttu-id="b2b94-330">使用了外部连接（即内部网络外部的连接）的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="b2b94-330">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2b94-331"><strong>抖动(毫秒)</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-331"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-332">否</span><span class="sxs-lookup"><span data-stu-id="b2b94-332">No</span></span></p></td>
<td><p><span data-ttu-id="b2b94-333">在 RTP 数据包到达之间检查到的平均抖动率。</span><span class="sxs-lookup"><span data-stu-id="b2b94-333">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="b2b94-334">（抖动是对&quot;shakiness&quot;的衡量。高抖动值通常是由拥塞或过载的媒体服务器引起的，并导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="b2b94-334">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2b94-335"><strong>相对单向平均值</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-335"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-336">否</span><span class="sxs-lookup"><span data-stu-id="b2b94-336">No</span></span></p></td>
<td><p><span data-ttu-id="b2b94-p132">两个媒体终结点之间的平均相对单向延迟。这是单跃点延迟度量。</span><span class="sxs-lookup"><span data-stu-id="b2b94-p132">Average relative one-way delay between two media endpoints. This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2b94-339"><strong>平均 RDP 图块处理延迟</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-339"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-340">否</span><span class="sxs-lookup"><span data-stu-id="b2b94-340">No</span></span></p></td>
<td><p><span data-ttu-id="b2b94-p133">查看会话持续时间内 AS 会议服务器中的平均 RDP 图块处理延迟。此指标不涉及网络延迟。高平均值反映了查看体验中的延迟较长。过载的会议服务器可能会遇到更长的平均延迟。</span><span class="sxs-lookup"><span data-stu-id="b2b94-p133">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session. This metric does not cover network latency. A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2b94-345"><strong>总损坏图块百分比</strong></span><span class="sxs-lookup"><span data-stu-id="b2b94-345"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="b2b94-346">否</span><span class="sxs-lookup"><span data-stu-id="b2b94-346">No</span></span></p></td>
<td><p><span data-ttu-id="b2b94-347">已损坏 RDP 图块的总百分比。</span><span class="sxs-lookup"><span data-stu-id="b2b94-347">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

