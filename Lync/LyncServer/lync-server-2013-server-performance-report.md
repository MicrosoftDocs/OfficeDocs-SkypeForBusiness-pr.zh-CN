---
title: 'Lync Server 2013: 服务器性能报告'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server Performance Report
ms:assetid: 942bb39a-1790-498e-9d99-8f6ce2d155c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615018(v=OCS.15)
ms:contentKeyID: 48184879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c5a08104f33fc07d6a0ec1c3241a7f14fa1227a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822375"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-performance-report-in-lync-server-2013"></a><span data-ttu-id="38ee0-102">Lync Server 2013 中的服务器性能报告</span><span class="sxs-lookup"><span data-stu-id="38ee0-102">Server Performance Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38ee0-103">_**主题上次修改时间:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="38ee0-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="38ee0-104">服务器性能报告提供了已经历最高的通话不佳百分比的 Microsoft Lync Server 2013 服务器列表。</span><span class="sxs-lookup"><span data-stu-id="38ee0-104">The Server Performance Report provides a list of Microsoft Lync Server 2013 servers that have experienced the highest-percentage of poor calls.</span></span> <span data-ttu-id="38ee0-105">该报告按服务器类型对服务器进行了分类，并为以下类型报告了单独的统计信息：</span><span class="sxs-lookup"><span data-stu-id="38ee0-105">The report breaks down servers by server type, reporting separate statistics for the following types:</span></span>

  - <span data-ttu-id="38ee0-106">中介服务器</span><span class="sxs-lookup"><span data-stu-id="38ee0-106">Mediation Server</span></span>

  - <span data-ttu-id="38ee0-107">A/V 会议服务器</span><span class="sxs-lookup"><span data-stu-id="38ee0-107">A/V Conferencing Server</span></span>

  - <span data-ttu-id="38ee0-108">A/V 边缘服务器</span><span class="sxs-lookup"><span data-stu-id="38ee0-108">A/V Edge Server</span></span>

  - <span data-ttu-id="38ee0-109">网关（中介服务器）</span><span class="sxs-lookup"><span data-stu-id="38ee0-109">Gateway (Mediation Server)</span></span>

  - <span data-ttu-id="38ee0-110">网关（中介服务器旁路）</span><span class="sxs-lookup"><span data-stu-id="38ee0-110">Gateway (Mediation Server bypass)</span></span>

  - <span data-ttu-id="38ee0-111">视频（包括 A/V 会议服务器和 A/V 边缘服务器的视频指标）</span><span class="sxs-lookup"><span data-stu-id="38ee0-111">Video (including video metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

  - <span data-ttu-id="38ee0-112">应用程序共享（包括 A/V 会议服务器和 A/V 边缘服务器的应用程序共享指标）</span><span class="sxs-lookup"><span data-stu-id="38ee0-112">Application Sharing (including application sharing metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

<span data-ttu-id="38ee0-p102">请务必记住，此报告中显示的等级是相对等级。例如，假定您的性能最差的服务器的 1,000 个已发出的呼叫中有一个质量欠佳的呼叫。此百分比为 .1%，它超出了可接受的百分比。但是，如果这是您性能最差的服务器（即，如果您所有其他服务器的质量欠佳的呼叫的百分比甚至低于 .1%），则该服务器仍会显示在服务器性能报告中。</span><span class="sxs-lookup"><span data-stu-id="38ee0-p102">It’s important to note that the ranking shown in this report as relative rankings. For example, suppose your worst-performing server had one poor call among its 1,000 placed calls. That's a more-than-acceptable percentage of .1%. However, if that's the worst-performing server you have (that is, if all your other servers have a poor call percentage even lower than .1%), then that server will still appear on the Server Performance Report.</span></span>

<div>

## <a name="accessing-the-server-performance-report"></a><span data-ttu-id="38ee0-117">访问服务器性能报告</span><span class="sxs-lookup"><span data-stu-id="38ee0-117">Accessing the Server Performance Report</span></span>

<span data-ttu-id="38ee0-118">服务器性能报告是从监控报告主页访问的。</span><span class="sxs-lookup"><span data-stu-id="38ee0-118">The Server Performance Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="38ee0-119">您可以通过单击以下任一指标, 向下钻取到[Lync Server 2013 中的 "通话清单" 报告](lync-server-2013-call-list-report.md):</span><span class="sxs-lookup"><span data-stu-id="38ee0-119">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="38ee0-120">呼叫量</span><span class="sxs-lookup"><span data-stu-id="38ee0-120">Call volume</span></span>

  - <span data-ttu-id="38ee0-121">质量欠佳的呼叫百分比</span><span class="sxs-lookup"><span data-stu-id="38ee0-121">Poor call percentage</span></span>

<span data-ttu-id="38ee0-122">此外，您还可以通过单击以下任一指标向下钻取到服务器媒体质量趋势报告：</span><span class="sxs-lookup"><span data-stu-id="38ee0-122">In addition, you can drill down to the Server Media Quality Trend Report by clicking the following metric:</span></span>

  - <span data-ttu-id="38ee0-123">趋势</span><span class="sxs-lookup"><span data-stu-id="38ee0-123">Trend</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-server-performance-report"></a><span data-ttu-id="38ee0-124">充分利用服务器性能报告</span><span class="sxs-lookup"><span data-stu-id="38ee0-124">Making the Best Use of the Server Performance Report</span></span>

<span data-ttu-id="38ee0-p104">服务器性能报告提供了很多筛选数据的方式；例如，您可以基于网络类型（从有线连接发出的呼叫与从无线连接发出的呼叫）和访问类型（从防火墙内发出的呼叫与从防火墙外发出的呼叫）进行筛选。最好在查看服务器性能报告时利用这些筛选器。例如，假设您有一台中介服务器，该服务器的质量欠佳的呼叫的百分比是 3.24%。如果您只查看无线呼叫，同一服务器的质量欠佳的呼叫的百分比可能接近 20%。这意味着服务器进行无线呼叫有困难，由于服务器的无线呼叫没有问题，此问题被部分掩盖了。</span><span class="sxs-lookup"><span data-stu-id="38ee0-p104">The Server Performance Report provides a number of ways to filter data; for example, you can filter on network type (calls made from a wired connection vs. calls made from a wireless connection) and access type (calls made from inside the firewall vs. calls made from outside the firewall). It's a good idea when viewing the server performance report to make use of these filters. For example, suppose you have a Mediation Server that has a poor call percentage of 3.24%. If you look solely at wireless calls, that same server might have a poor call percentage approaching 20%. That means that the server was having difficulty with wireless calls, a problem that is partially obscured because the server was not having problems with wired calls.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="38ee0-130">筛选器</span><span class="sxs-lookup"><span data-stu-id="38ee0-130">Filters</span></span>

<span data-ttu-id="38ee0-p105">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，服务器性能报告使您能够执行按服务器类型或按网络类型（即有线或无线）筛选返回的数据之类的操作。您还可以选择数据的分组方式。在此示例中，将按小时、日、周或月对数据进行分组。</span><span class="sxs-lookup"><span data-stu-id="38ee0-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Server Performance Report enables you to do such things as filter the returned data by server type or by network type (that is, wired or wireless). You can also choose how data should be grouped. In this case, data is grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="38ee0-135">下表列出了可用于服务器性能报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="38ee0-135">The following table lists the filters that you can use with the Server Performance Report.</span></span>

### <a name="server-performance-report-filters"></a><span data-ttu-id="38ee0-136">服务器性能报告筛选器</span><span class="sxs-lookup"><span data-stu-id="38ee0-136">Server Performance Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38ee0-137">名称</span><span class="sxs-lookup"><span data-stu-id="38ee0-137">Name</span></span></th>
<th><span data-ttu-id="38ee0-138">说明</span><span class="sxs-lookup"><span data-stu-id="38ee0-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38ee0-139"><strong>从</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-139"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-p106">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="38ee0-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="38ee0-142">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="38ee0-142">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="38ee0-p107">如果您未输入开始时间，该报告会自动将将某个特定日期的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="38ee0-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="38ee0-145">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="38ee0-145">7/7/2012</span></span></p>
<p><span data-ttu-id="38ee0-146">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="38ee0-146">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="38ee0-147">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="38ee0-147">7/3/2012</span></span></p>
<p><span data-ttu-id="38ee0-148">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="38ee0-148">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38ee0-149"><strong>到</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-149"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-p108">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="38ee0-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="38ee0-152">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="38ee0-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="38ee0-p109">如果您未输入结束时间，该报告会自动将某个特定日期的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="38ee0-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="38ee0-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="38ee0-155">7/7/2012</span></span></p>
<p><span data-ttu-id="38ee0-156">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="38ee0-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="38ee0-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="38ee0-157">7/3/2012</span></span></p>
<p><span data-ttu-id="38ee0-158">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="38ee0-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38ee0-159"><strong>服务器类型</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-159"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-p110">指示应报告其性能的服务器的类型。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="38ee0-p110">Indicates the type of server whose performance should be reported. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="38ee0-162">[所有]</span><span class="sxs-lookup"><span data-stu-id="38ee0-162">[All]</span></span></p></li>
<li><p><span data-ttu-id="38ee0-163">中介服务器</span><span class="sxs-lookup"><span data-stu-id="38ee0-163">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="38ee0-164">A/V 会议服务器</span><span class="sxs-lookup"><span data-stu-id="38ee0-164">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="38ee0-165">A/V 边缘服务器</span><span class="sxs-lookup"><span data-stu-id="38ee0-165">A/V Edge Server</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38ee0-166"><strong>前 N 个</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-166"><strong>Top N</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-p111">指示每个类别中将显示的服务器数（基于其质量欠佳的呼叫百分比）。例如，如果您选择“<strong>5</strong>”，则将显示 5 个性能最差的服务器。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="38ee0-p111">Indicates the number of servers (based on their poor call percentage) to be displayed in each category. For example, if you select <strong>5</strong> then the five poorest-performing servers are displayed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="38ee0-170">[所有]</span><span class="sxs-lookup"><span data-stu-id="38ee0-170">[All]</span></span></p></li>
<li><p><span data-ttu-id="38ee0-171">5</span><span class="sxs-lookup"><span data-stu-id="38ee0-171">5</span></span></p></li>
<li><p><span data-ttu-id="38ee0-172">10</span><span class="sxs-lookup"><span data-stu-id="38ee0-172">10</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38ee0-173"><strong>访问类型</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-173"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-p112">指示客户端在发起呼叫时已登录到内部网络还是外部网络。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="38ee0-p112">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="38ee0-176">[所有]</span><span class="sxs-lookup"><span data-stu-id="38ee0-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="38ee0-177">内部</span><span class="sxs-lookup"><span data-stu-id="38ee0-177">Internal</span></span></p></li>
<li><p><span data-ttu-id="38ee0-178">外部</span><span class="sxs-lookup"><span data-stu-id="38ee0-178">External</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38ee0-179"><strong>网络类型</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-179"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-p113">指示客户端在发起呼叫时已连接到的网络的类型。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="38ee0-p113">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="38ee0-182">[所有]</span><span class="sxs-lookup"><span data-stu-id="38ee0-182">[All]</span></span></p></li>
<li><p><span data-ttu-id="38ee0-183">有线</span><span class="sxs-lookup"><span data-stu-id="38ee0-183">Wired</span></span></p></li>
<li><p><span data-ttu-id="38ee0-184">无线</span><span class="sxs-lookup"><span data-stu-id="38ee0-184">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38ee0-185"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-185"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-p114">指示外部客户端在发起呼叫时是否使用了虚拟专用网 (VPN) 连接。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="38ee0-p114">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="38ee0-188">[所有]</span><span class="sxs-lookup"><span data-stu-id="38ee0-188">[All]</span></span></p></li>
<li><p><span data-ttu-id="38ee0-189">VPN</span><span class="sxs-lookup"><span data-stu-id="38ee0-189">VPN</span></span></p></li>
<li><p><span data-ttu-id="38ee0-190">非 VPN</span><span class="sxs-lookup"><span data-stu-id="38ee0-190">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="38ee0-191">指标</span><span class="sxs-lookup"><span data-stu-id="38ee0-191">Metrics</span></span>

<span data-ttu-id="38ee0-192">下表列出了服务器性能报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="38ee0-192">The following table lists the information provided in the Server Performance Report.</span></span>

### <a name="server-performance-report-metrics-audio-call-summary"></a><span data-ttu-id="38ee0-193">服务器性能报告指标：音频呼叫摘要</span><span class="sxs-lookup"><span data-stu-id="38ee0-193">Server Performance Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38ee0-194">名称</span><span class="sxs-lookup"><span data-stu-id="38ee0-194">Name</span></span></th>
<th><span data-ttu-id="38ee0-195">是否可用作排序依据</span><span class="sxs-lookup"><span data-stu-id="38ee0-195">Can Sort On</span></span></th>
<th><span data-ttu-id="38ee0-196">描述</span><span class="sxs-lookup"><span data-stu-id="38ee0-196">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38ee0-197"><strong>服务器</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-197"><strong>Server</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-198">否</span><span class="sxs-lookup"><span data-stu-id="38ee0-198">No</span></span></p></td>
<td><p><span data-ttu-id="38ee0-199">服务器的名称/IP 地址。</span><span class="sxs-lookup"><span data-stu-id="38ee0-199">Name/IP address of the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38ee0-200"><strong>呼叫量</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-200"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-201">否</span><span class="sxs-lookup"><span data-stu-id="38ee0-201">No</span></span></p></td>
<td><p><span data-ttu-id="38ee0-202">进行的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="38ee0-202">Total number of calls made.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38ee0-203"><strong>质量欠佳的呼叫百分比</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-203"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-204">否</span><span class="sxs-lookup"><span data-stu-id="38ee0-204">No</span></span></p></td>
<td><p><span data-ttu-id="38ee0-p115">归类为质量欠佳的呼叫的总数。质量欠佳的呼叫是指至少一项测量指标超过允许的值的任何呼叫（例如，信号极不稳定的呼叫）。</span><span class="sxs-lookup"><span data-stu-id="38ee0-p115">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38ee0-207"><strong>来回行程（毫秒）</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-207"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-208">是</span><span class="sxs-lookup"><span data-stu-id="38ee0-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="38ee0-p116">实时传输协议 (RTP) 数据包来往于另一个终结点所需的平均时间量（以毫秒为单位）。来回行程的时间小于或等于 100 毫秒被视为质量可接受。</span><span class="sxs-lookup"><span data-stu-id="38ee0-p116">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="38ee0-p117">高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。</span><span class="sxs-lookup"><span data-stu-id="38ee0-p117">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38ee0-213"><strong>性能降低 (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-213"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-214">是</span><span class="sxs-lookup"><span data-stu-id="38ee0-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="38ee0-215">呼叫过程中遇到的性能降低的平均意见得分 (MOS) 的平均值。</span><span class="sxs-lookup"><span data-stu-id="38ee0-215">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="38ee0-216">性能降低值的范围介于 0.0 和 5.0 之间。</span><span class="sxs-lookup"><span data-stu-id="38ee0-216">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="38ee0-217">该值小于或等于 0.5 表示可接受的性能降低。</span><span class="sxs-lookup"><span data-stu-id="38ee0-217">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="38ee0-218">过去，平均意见得分是通过让用户对呼叫质量进行评级（范围为 1 到 5）来计算得出的。</span><span class="sxs-lookup"><span data-stu-id="38ee0-218">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="38ee0-219">在 Lync Server 中, 监视服务器使用一组算法来预测用户对呼叫的评分。</span><span class="sxs-lookup"><span data-stu-id="38ee0-219">In Lync Server, the Monitoring Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="38ee0-p119">高性能降低值可能是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器或终结点超载造成的，从而导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="38ee0-p119">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38ee0-222"><strong>数据包丢失</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-222"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-223">是</span><span class="sxs-lookup"><span data-stu-id="38ee0-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="38ee0-p120">平均实时传输协议 (RTP) 数据包丢失率。（当 RTP 数据包（一项用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时，即发生数据包丢失。）高丢失率通常是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器超载造成的。数据包丢失通常导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="38ee0-p120">Average rate of real-time transport protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38ee0-227"><strong>抖动（毫秒）</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-227"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-228">是</span><span class="sxs-lookup"><span data-stu-id="38ee0-228">Yes</span></span></p></td>
<td><p><span data-ttu-id="38ee0-229">在 RTP 数据包到达之间检测到的平均抖动率。</span><span class="sxs-lookup"><span data-stu-id="38ee0-229">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="38ee0-230">(抖动是&quot;shakiness&quot;通话的衡量。)高抖动值通常由拥塞或过载的媒体服务器导致, 并导致失真或丢失的音频。</span><span class="sxs-lookup"><span data-stu-id="38ee0-230">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38ee0-231"><strong>修复程序隐藏比率</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-231"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-232">是</span><span class="sxs-lookup"><span data-stu-id="38ee0-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="38ee0-p122">隐藏的音频样本与样本总数的平均比率。（隐藏的音频样本是一项技术，用于消除通常由丢弃的网络数据包造成的意外转换。）高值指示数据包丢失或抖动造成的显著的丢失隐藏级别，从而导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="38ee0-p122">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38ee0-235"><strong>修复程序拉伸比率</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-235"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-236">是</span><span class="sxs-lookup"><span data-stu-id="38ee0-236">Yes</span></span></p></td>
<td><p><span data-ttu-id="38ee0-p123">拉伸的音频样本数与样本总数的平均比率。（拉伸的音频是一类已扩展的音频，可在检测到丢弃的网络数据包时帮助保持呼叫质量。）高值指示抖动造成的显著的样本拉伸级别，从而导致音频听起来很机械或失真。</span><span class="sxs-lookup"><span data-stu-id="38ee0-p123">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38ee0-239"><strong>修复程序压缩比率</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-239"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-240">是</span><span class="sxs-lookup"><span data-stu-id="38ee0-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="38ee0-p124">压缩的音频样本与样本总数的平均比率。（压缩的音频是一类已压缩的音频，可在检测到丢弃的网络数据包时帮助保持呼叫质量。）高值指示抖动造成的显著的样本压缩级别，从而导致音频听起来像是已加速或失真。</span><span class="sxs-lookup"><span data-stu-id="38ee0-p124">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-video-call-summary"></a><span data-ttu-id="38ee0-243">服务器性能报告指标：视频呼叫摘要</span><span class="sxs-lookup"><span data-stu-id="38ee0-243">Server Performance Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38ee0-244">名称</span><span class="sxs-lookup"><span data-stu-id="38ee0-244">Name</span></span></th>
<th><span data-ttu-id="38ee0-245">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="38ee0-245">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="38ee0-246">描述</span><span class="sxs-lookup"><span data-stu-id="38ee0-246">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38ee0-247"><strong>呼叫类型/终结点类型</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-247"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-248">否</span><span class="sxs-lookup"><span data-stu-id="38ee0-248">No</span></span></p></td>
<td><p><span data-ttu-id="38ee0-p125">当您单击此项时，该报告会显示有关基于这个类型的呼叫的详细信息。呼叫类型包括：</span><span class="sxs-lookup"><span data-stu-id="38ee0-p125">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="38ee0-251">UC 对等呼叫</span><span class="sxs-lookup"><span data-stu-id="38ee0-251">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="38ee0-252">UC 会议会话</span><span class="sxs-lookup"><span data-stu-id="38ee0-252">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="38ee0-253">PSTN 会议会话</span><span class="sxs-lookup"><span data-stu-id="38ee0-253">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="38ee0-254">PSTN 呼叫: 媒体旁路</span><span class="sxs-lookup"><span data-stu-id="38ee0-254">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="38ee0-255">PSTN 呼叫(无旁路): UC 线路</span><span class="sxs-lookup"><span data-stu-id="38ee0-255">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="38ee0-256">PSTN 呼叫(无旁路): 网关线路</span><span class="sxs-lookup"><span data-stu-id="38ee0-256">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="38ee0-257">其他呼叫类型</span><span class="sxs-lookup"><span data-stu-id="38ee0-257">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38ee0-258"><strong>呼叫量</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-258"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-259">否</span><span class="sxs-lookup"><span data-stu-id="38ee0-259">No</span></span></p></td>
<td><p><span data-ttu-id="38ee0-260">每个呼叫类型的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="38ee0-260">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38ee0-261"><strong>质量欠佳的呼叫百分比</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-261"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-262">否</span><span class="sxs-lookup"><span data-stu-id="38ee0-262">No</span></span></p></td>
<td><p><span data-ttu-id="38ee0-p126">归类为质量欠佳的呼叫的总数。质量欠佳的呼叫是指至少一项测量指标超过允许的值的任何呼叫（例如，信号极不稳定的呼叫）。</span><span class="sxs-lookup"><span data-stu-id="38ee0-p126">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38ee0-265"><strong>呼叫量（无线呼叫）</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-265"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-266">否</span><span class="sxs-lookup"><span data-stu-id="38ee0-266">No</span></span></p></td>
<td><p><span data-ttu-id="38ee0-267">使用了无线连接的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="38ee0-267">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38ee0-268"><strong>呼叫量（VPN 呼叫）</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-268"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-269">否</span><span class="sxs-lookup"><span data-stu-id="38ee0-269">No</span></span></p></td>
<td><p><span data-ttu-id="38ee0-270">使用了 VPN 连接的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="38ee0-270">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38ee0-271"><strong>呼叫量（外部呼叫）</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-271"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-272">否</span><span class="sxs-lookup"><span data-stu-id="38ee0-272">No</span></span></p></td>
<td><p><span data-ttu-id="38ee0-273">使用了外部连接（即内部网络外部的连接）的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="38ee0-273">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38ee0-274"><strong>平均比特率 (Kb/s)</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-274"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-275">否</span><span class="sxs-lookup"><span data-stu-id="38ee0-275">No</span></span></p></td>
<td><p><span data-ttu-id="38ee0-276">平均视频比特率 (Kb/s)。</span><span class="sxs-lookup"><span data-stu-id="38ee0-276">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38ee0-277"><strong>低比特率百分比</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-277"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-278">否</span><span class="sxs-lookup"><span data-stu-id="38ee0-278">No</span></span></p></td>
<td><p><span data-ttu-id="38ee0-279">比特率较低的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="38ee0-279">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38ee0-280"><strong>出站数据包丢失</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-280"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-281">否</span><span class="sxs-lookup"><span data-stu-id="38ee0-281">No</span></span></p></td>
<td><p><span data-ttu-id="38ee0-p127">出站数据包的实时传输协议 (RTP) 数据包丢失率。（当 RTP 数据包（一项用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时，即发生数据包丢失。）高丢失率通常是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器超载造成的。数据包丢失通常导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="38ee0-p127">Real-Time Transport Protocol (RTP) packet loss for outbound packets. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38ee0-285"><strong>冻结帧百分比</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-285"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-286">否</span><span class="sxs-lookup"><span data-stu-id="38ee0-286">No</span></span></p></td>
<td><p><span data-ttu-id="38ee0-p128">“冻结”帧的百分比。在一个冻结帧中，视频将停止前进，而呼叫的音频部分将继续。</span><span class="sxs-lookup"><span data-stu-id="38ee0-p128">Percentage of “frozen” frames. In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38ee0-289"><strong>出站平均帧速率</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-289"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-290">否</span><span class="sxs-lookup"><span data-stu-id="38ee0-290">No</span></span></p></td>
<td><p><span data-ttu-id="38ee0-291">呼叫期间的出站传输的平均帧速率。</span><span class="sxs-lookup"><span data-stu-id="38ee0-291">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38ee0-292"><strong>入站平均帧速率</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-292"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-293">否</span><span class="sxs-lookup"><span data-stu-id="38ee0-293">No</span></span></p></td>
<td><p><span data-ttu-id="38ee0-294">呼叫期间的入站传输的平均帧速率。</span><span class="sxs-lookup"><span data-stu-id="38ee0-294">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38ee0-295"><strong>入站低帧速率百分比</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-295"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-296">否</span><span class="sxs-lookup"><span data-stu-id="38ee0-296">No</span></span></p></td>
<td><p><span data-ttu-id="38ee0-297">传入视频的比特率较低的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="38ee0-297">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38ee0-298"><strong>客户端健康状态百分比</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-298"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38ee0-299">指示呼叫期间客户端设备的相对健康状态。</span><span class="sxs-lookup"><span data-stu-id="38ee0-299">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="38ee0-300">服务器性能报告指标：应用程序共享呼叫摘要</span><span class="sxs-lookup"><span data-stu-id="38ee0-300">Server Performance Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38ee0-301">名称</span><span class="sxs-lookup"><span data-stu-id="38ee0-301">Name</span></span></th>
<th><span data-ttu-id="38ee0-302">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="38ee0-302">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="38ee0-303">描述</span><span class="sxs-lookup"><span data-stu-id="38ee0-303">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38ee0-304"><strong>呼叫类型/终结点类型</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-304"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-305">否</span><span class="sxs-lookup"><span data-stu-id="38ee0-305">No</span></span></p></td>
<td><p><span data-ttu-id="38ee0-p129">当您单击此项时，该报告会显示有关基于这个类型的呼叫的详细信息。呼叫类型包括：</span><span class="sxs-lookup"><span data-stu-id="38ee0-p129">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="38ee0-308">UC 对等呼叫</span><span class="sxs-lookup"><span data-stu-id="38ee0-308">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="38ee0-309">UC 会议会话</span><span class="sxs-lookup"><span data-stu-id="38ee0-309">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="38ee0-310">PSTN 会议会话</span><span class="sxs-lookup"><span data-stu-id="38ee0-310">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="38ee0-311">PSTN 呼叫: 媒体旁路</span><span class="sxs-lookup"><span data-stu-id="38ee0-311">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="38ee0-312">PSTN 呼叫(无旁路): UC 线路</span><span class="sxs-lookup"><span data-stu-id="38ee0-312">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="38ee0-313">PSTN 呼叫(无旁路): 网关线路</span><span class="sxs-lookup"><span data-stu-id="38ee0-313">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="38ee0-314">其他呼叫类型</span><span class="sxs-lookup"><span data-stu-id="38ee0-314">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38ee0-315"><strong>呼叫量</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-315"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-316">否</span><span class="sxs-lookup"><span data-stu-id="38ee0-316">No</span></span></p></td>
<td><p><span data-ttu-id="38ee0-317">每个呼叫类型的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="38ee0-317">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38ee0-318"><strong>质量欠佳的呼叫百分比</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-318"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-319">否</span><span class="sxs-lookup"><span data-stu-id="38ee0-319">No</span></span></p></td>
<td><p><span data-ttu-id="38ee0-p130">归类为质量欠佳的呼叫的总数。质量欠佳的呼叫是指至少一项测量指标超过允许的值的任何呼叫（例如，信号极不稳定的呼叫）。</span><span class="sxs-lookup"><span data-stu-id="38ee0-p130">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38ee0-322"><strong>呼叫量（无线呼叫）</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-322"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-323">否</span><span class="sxs-lookup"><span data-stu-id="38ee0-323">No</span></span></p></td>
<td><p><span data-ttu-id="38ee0-324">使用了无线连接的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="38ee0-324">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38ee0-325"><strong>呼叫量（VPN 呼叫）</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-325"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-326">否</span><span class="sxs-lookup"><span data-stu-id="38ee0-326">No</span></span></p></td>
<td><p><span data-ttu-id="38ee0-327">使用了 VPN 连接的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="38ee0-327">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38ee0-328"><strong>呼叫量（外部呼叫）</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-328"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-329">否</span><span class="sxs-lookup"><span data-stu-id="38ee0-329">No</span></span></p></td>
<td><p><span data-ttu-id="38ee0-330">使用了外部连接（即内部网络外部的连接）的呼叫的总数。</span><span class="sxs-lookup"><span data-stu-id="38ee0-330">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38ee0-331"><strong>抖动（毫秒）</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-331"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-332">否</span><span class="sxs-lookup"><span data-stu-id="38ee0-332">No</span></span></p></td>
<td><p><span data-ttu-id="38ee0-333">在 RTP 数据包到达之间检测到的平均抖动率。</span><span class="sxs-lookup"><span data-stu-id="38ee0-333">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="38ee0-334">(抖动是&quot;shakiness&quot;通话的衡量。)高抖动值通常由拥塞或过载的媒体服务器导致, 并导致失真或丢失的音频。</span><span class="sxs-lookup"><span data-stu-id="38ee0-334">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38ee0-335"><strong>相对单向平均值</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-335"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-336">否</span><span class="sxs-lookup"><span data-stu-id="38ee0-336">No</span></span></p></td>
<td><p><span data-ttu-id="38ee0-p132">两个媒体终结点之间的平均相对单向延迟。这是单跃点延迟度量。</span><span class="sxs-lookup"><span data-stu-id="38ee0-p132">Average relative one-way delay between two media endpoints. This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38ee0-339"><strong>平均 RDP 图块处理延迟</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-339"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-340">否</span><span class="sxs-lookup"><span data-stu-id="38ee0-340">No</span></span></p></td>
<td><p><span data-ttu-id="38ee0-p133">查看会话持续时间内 AS 会议服务器中的平均 RDP 图块处理延迟。此指标不涉及网络延迟。高平均值反映了查看体验中的延迟较长。过载的会议服务器可能会遇到更长的平均延迟。</span><span class="sxs-lookup"><span data-stu-id="38ee0-p133">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session. This metric does not cover network latency. A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38ee0-345"><strong>总损坏图块百分比</strong></span><span class="sxs-lookup"><span data-stu-id="38ee0-345"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="38ee0-346">否</span><span class="sxs-lookup"><span data-stu-id="38ee0-346">No</span></span></p></td>
<td><p><span data-ttu-id="38ee0-347">已损坏 RDP 图块的总百分比。</span><span class="sxs-lookup"><span data-stu-id="38ee0-347">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

