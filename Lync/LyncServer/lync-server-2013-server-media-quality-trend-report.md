---
title: Lync Server 2013：服务器媒体质量趋势报告
description: Lync Server 2013：服务器媒体质量趋势报告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server Media Quality Trend Report
ms:assetid: 8a51fd13-1487-4632-b5ec-f7ae2abe8ed4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205071(v=OCS.15)
ms:contentKeyID: 48184760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7ac2482b967aab230c5522c2b6a76e10ced28e7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578130"
---
# <a name="server-media-quality-trend-report-in-lync-server-2013"></a><span data-ttu-id="e0231-103">Lync Server 2013 中的服务器媒体质量趋势报告</span><span class="sxs-lookup"><span data-stu-id="e0231-103">Server Media Quality Trend Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0231-104">_**上次修改的主题：** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="e0231-104">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="e0231-p101">利用服务器媒体质量趋势报告的方式，您可以图形方式比较多达 5 台服务器的用户体验质量指标（如呼叫量、质量欠佳的呼叫百分比、数据包丢失和抖动）。这使得执行标识性能不佳的服务器、未充分利用的服务器或使用过度的服务器之类的操作变得更简单。</span><span class="sxs-lookup"><span data-stu-id="e0231-p101">The Server Media Quality Trend Report provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter. This makes it easier to do such things as identify servers that are performing poorly, identify servers that are underutilized, or identify servers that are being overused.</span></span>

<div>

## <a name="accessing-the-server-media-quality-trend-report"></a><span data-ttu-id="e0231-107">访问服务器媒体质量趋势报告</span><span class="sxs-lookup"><span data-stu-id="e0231-107">Accessing the Server Media Quality Trend Report</span></span>

<span data-ttu-id="e0231-108">服务器媒体质量趋势报告可从下列任一报告进行访问：</span><span class="sxs-lookup"><span data-stu-id="e0231-108">The Server Media Quality Trend Report can be accessed from either one of the following report:</span></span>

  - <span data-ttu-id="e0231-109">[Lync server 2013 (中的 "服务器性能" 报告](lync-server-2013-server-performance-report.md) 单击 "趋势" 指标) </span><span class="sxs-lookup"><span data-stu-id="e0231-109">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Trend metric)</span></span>

  - <span data-ttu-id="e0231-110">通过单击 A/V 边缘服务器指标， [Lync Server 2013 (中的呼叫详细信息报告](lync-server-2013-call-detail-report.md)。</span><span class="sxs-lookup"><span data-stu-id="e0231-110">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) (by clicking the A/V edge server metric.</span></span> <span data-ttu-id="e0231-111">如果呼叫者或被叫方是服务器，则还可以通过单击终结点名称来访问服务器质量媒体趋势报告。 ) </span><span class="sxs-lookup"><span data-stu-id="e0231-111">If the caller or callee is a server, you can also reach the Server Quality Media Trend Report by clicking the endpoint name.)</span></span>

</div>

<div>

## <a name="making-the-best-use-of-server-media-quality-trend-report"></a><span data-ttu-id="e0231-112">充分利用服务器媒体质量趋势报告</span><span class="sxs-lookup"><span data-stu-id="e0231-112">Making the Best Use of Server Media Quality Trend Report</span></span>

<span data-ttu-id="e0231-113">当您单击特定服务器的 " [Lync server 2013 中的服务器性能报告](lync-server-2013-server-performance-report.md) " 上的 "趋势跃点数" 时，将打开 "服务器媒体质量趋势" 报告。</span><span class="sxs-lookup"><span data-stu-id="e0231-113">When you click the Trend metric on the [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) for a specific server, the Server Media Quality Trend Report will open.</span></span> <span data-ttu-id="e0231-114">但是，您只会看到该报告的一个空白实例；您在服务器性能报告上选择的服务器将不会显示在屏幕上。</span><span class="sxs-lookup"><span data-stu-id="e0231-114">However, you will see only a blank instance of that report; the server you selected on the Server Performance Report will not be displayed onscreen.</span></span> <span data-ttu-id="e0231-115">相反，您需要从“服务器”下拉列表中选择服务器。</span><span class="sxs-lookup"><span data-stu-id="e0231-115">Instead, you will need to select that server from the Servers dropdown.</span></span> <span data-ttu-id="e0231-116">还要注意，“服务器”下拉列表包含“全选”选项。</span><span class="sxs-lookup"><span data-stu-id="e0231-116">Note, too that the Servers dropdown includes a Select All option.</span></span> <span data-ttu-id="e0231-117">此选项在您具有 5 台以上的服务器时不起作用；服务器媒体质量趋势报告一次最多只能显示 5 台服务器的数据。</span><span class="sxs-lookup"><span data-stu-id="e0231-117">This option will not work if you have more than 5 servers; the Server Media Quality Trend Report can only display data for a maximum of 5 servers at a time.</span></span>

<span data-ttu-id="e0231-118">在服务器媒体质量趋势报告显示的关系图上，标记为 "呼叫音量" 和 "差呼叫百分比" 的点为 hotlinks。单击图上的点将 [在 Lync Server 2013 中打开呼叫列表报告](lync-server-2013-call-list-report.md) 的一个实例，其中显示在指定时间段内 (或较差呼叫) 的总呼叫数。</span><span class="sxs-lookup"><span data-stu-id="e0231-118">On the graphs displayed by the Server Media Quality Trend Report, the points labeled Call Volume and Poor Call Percentage are hotlinks; clicking a point on the graph will open an instance of the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) showing the total calls (or poor calls) for the specified time period.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="e0231-119">筛选器</span><span class="sxs-lookup"><span data-stu-id="e0231-119">Filters</span></span>

<span data-ttu-id="e0231-p104">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。下表列出了可用于服务器媒体质量趋势报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="e0231-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-filters"></a><span data-ttu-id="e0231-122">服务器媒体质量趋势报告筛选器</span><span class="sxs-lookup"><span data-stu-id="e0231-122">Server Media Quality Trend Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0231-123">名称</span><span class="sxs-lookup"><span data-stu-id="e0231-123">Name</span></span></th>
<th><span data-ttu-id="e0231-124">说明</span><span class="sxs-lookup"><span data-stu-id="e0231-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0231-125"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="e0231-125"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="e0231-p105">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e0231-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="e0231-128">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="e0231-128">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e0231-p106">如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="e0231-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e0231-131">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e0231-131">7/7/2012</span></span></p>
<p><span data-ttu-id="e0231-132">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="e0231-132">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e0231-133">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e0231-133">7/3/2012</span></span></p>
<p><span data-ttu-id="e0231-134">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="e0231-134">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0231-135"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="e0231-135"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="e0231-p107">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e0231-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="e0231-138">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="e0231-138">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e0231-p108">如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="e0231-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e0231-141">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e0231-141">7/7/2012</span></span></p>
<p><span data-ttu-id="e0231-142">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="e0231-142">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e0231-143">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e0231-143">7/3/2012</span></span></p>
<p><span data-ttu-id="e0231-144">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="e0231-144">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0231-145"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="e0231-145"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="e0231-p109">时间间隔。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="e0231-p109">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e0231-148">每小时（最多可显示 25 个小时）</span><span class="sxs-lookup"><span data-stu-id="e0231-148">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="e0231-149">每天（最多可显示 31 天）</span><span class="sxs-lookup"><span data-stu-id="e0231-149">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="e0231-150">每周（最多可显示 12 周）</span><span class="sxs-lookup"><span data-stu-id="e0231-150">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="e0231-p110">如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。例如，如果选择的开始日期为 8/7/2012、结束日期为 9/28/2012、间隔为“每天”，则显示从 8/7/2012 12:00 AM 到 9/7/2012 12:00 AM 这些天的数据（即总共 31 天的数据）。</span><span class="sxs-lookup"><span data-stu-id="e0231-p110">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 8/7/2012 and an end date of 9/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0231-153"><strong>服务器类型</strong></span><span class="sxs-lookup"><span data-stu-id="e0231-153"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="e0231-p111">呼叫中涉及的服务器类型。允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="e0231-p111">Type of server involved in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="e0231-156">中介服务器</span><span class="sxs-lookup"><span data-stu-id="e0231-156">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="e0231-157">A/V 会议服务器</span><span class="sxs-lookup"><span data-stu-id="e0231-157">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="e0231-158">A/V 边缘服务器</span><span class="sxs-lookup"><span data-stu-id="e0231-158">A/V Edge Server</span></span></p></li>
<li><p><span data-ttu-id="e0231-159">网关（中介服务器）</span><span class="sxs-lookup"><span data-stu-id="e0231-159">Gateway (Mediation Server)</span></span></p></li>
<li><p><span data-ttu-id="e0231-160">网关（中介服务器旁路）</span><span class="sxs-lookup"><span data-stu-id="e0231-160">Gateway (Mediation Server Bypass)</span></span></p></li>
<li><p><span data-ttu-id="e0231-161">AS 会议服务器</span><span class="sxs-lookup"><span data-stu-id="e0231-161">AS Conferencing Server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0231-162"><strong>Servers</strong></span><span class="sxs-lookup"><span data-stu-id="e0231-162"><strong>Servers</strong></span></span></p></td>
<td><p><span data-ttu-id="e0231-p112">会话中涉及的服务器的名称；此下拉列表将基于服务器类型筛选器的值自动为您填充。编译报告时最多可选择 5 台不同的服务器。</span><span class="sxs-lookup"><span data-stu-id="e0231-p112">Name of the server involved in the session; this dropdown list is automatically populated for you based on the value of the Server type filter. You can select up to 5 different servers when compiling a report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0231-165"><strong>访问类型</strong></span><span class="sxs-lookup"><span data-stu-id="e0231-165"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="e0231-p113">指示参与者是登录到内部网络还是从外部网络登录。允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="e0231-p113">Indicates whether the participant was logged on to the internal network or from the external network. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="e0231-168">各种</span><span class="sxs-lookup"><span data-stu-id="e0231-168">[All]</span></span></p></li>
<li><p><span data-ttu-id="e0231-169">内部</span><span class="sxs-lookup"><span data-stu-id="e0231-169">Internal</span></span></p></li>
<li><p><span data-ttu-id="e0231-170">外部</span><span class="sxs-lookup"><span data-stu-id="e0231-170">External</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0231-171"><strong>网络类型</strong></span><span class="sxs-lookup"><span data-stu-id="e0231-171"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="e0231-p114">指示参与者连接到的网络的类型。允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="e0231-p114">Indicates the type of network the participant was connected to. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="e0231-174">各种</span><span class="sxs-lookup"><span data-stu-id="e0231-174">[All]</span></span></p></li>
<li><p><span data-ttu-id="e0231-175">有线</span><span class="sxs-lookup"><span data-stu-id="e0231-175">Wired</span></span></p></li>
<li><p><span data-ttu-id="e0231-176">无线</span><span class="sxs-lookup"><span data-stu-id="e0231-176">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0231-177"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="e0231-177"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="e0231-p115">指示外部参与者在会话期间使用的是否是虚拟专用网 (VPN) 连接。允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="e0231-p115">Indicates whether an external participant was using a virtual private network (VPN) connection during the session. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="e0231-180">各种</span><span class="sxs-lookup"><span data-stu-id="e0231-180">[All]</span></span></p></li>
<li><p><span data-ttu-id="e0231-181">VPN</span><span class="sxs-lookup"><span data-stu-id="e0231-181">VPN</span></span></p></li>
<li><p><span data-ttu-id="e0231-182">非 VPN</span><span class="sxs-lookup"><span data-stu-id="e0231-182">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="e0231-183">指标</span><span class="sxs-lookup"><span data-stu-id="e0231-183">Metrics</span></span>

<span data-ttu-id="e0231-184">下表列出了服务器媒体质量趋势报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="e0231-184">The following table lists the information provided in the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-metrics"></a><span data-ttu-id="e0231-185">服务器媒体质量趋势报告指标</span><span class="sxs-lookup"><span data-stu-id="e0231-185">Server Media Quality Trend Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0231-186">名称</span><span class="sxs-lookup"><span data-stu-id="e0231-186">Name</span></span></th>
<th><span data-ttu-id="e0231-187">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="e0231-187">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e0231-188">说明</span><span class="sxs-lookup"><span data-stu-id="e0231-188">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0231-189"><strong>呼叫量</strong></span><span class="sxs-lookup"><span data-stu-id="e0231-189"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="e0231-190">否</span><span class="sxs-lookup"><span data-stu-id="e0231-190">No</span></span></p></td>
<td><p><span data-ttu-id="e0231-191">呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="e0231-191">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0231-192"><strong>性能降低(MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="e0231-192"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="e0231-193">否</span><span class="sxs-lookup"><span data-stu-id="e0231-193">No</span></span></p></td>
<td><p><span data-ttu-id="e0231-194">呼叫过程中遇到的性能降低的 MOS（平均意见得分）的平均值。</span><span class="sxs-lookup"><span data-stu-id="e0231-194">Average amount of MOS (mean option score) degradation experienced during a call.</span></span> <span data-ttu-id="e0231-195">性能降低值的范围介于 0.0 和 5.0 之间；该值小于或等于 0.5 表示可接受的性能降低。</span><span class="sxs-lookup"><span data-stu-id="e0231-195">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="e0231-196">过去，平均意见得分是通过让用户对呼叫质量进行评级（范围为 1 到 5）来计算得出的。</span><span class="sxs-lookup"><span data-stu-id="e0231-196">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="e0231-197">Lync Server 使用一组算法来预测用户对呼叫进行评级的方式。</span><span class="sxs-lookup"><span data-stu-id="e0231-197">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="e0231-p117">高性能降低值可能是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器或终结点超载造成的，从而导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="e0231-p117">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0231-200"><strong>质量欠佳的呼叫百分比</strong></span><span class="sxs-lookup"><span data-stu-id="e0231-200"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="e0231-201">否</span><span class="sxs-lookup"><span data-stu-id="e0231-201">No</span></span></p></td>
<td><p><span data-ttu-id="e0231-p118">归类为质量欠佳的呼叫的总数。质量欠佳的呼叫是指至少一项测量指标超过允许的值的任何呼叫（例如，信号极不稳定的呼叫）。</span><span class="sxs-lookup"><span data-stu-id="e0231-p118">The total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0231-204"><strong>来回行程(毫秒)</strong></span><span class="sxs-lookup"><span data-stu-id="e0231-204"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="e0231-205">否</span><span class="sxs-lookup"><span data-stu-id="e0231-205">No</span></span></p></td>
<td><p><span data-ttu-id="e0231-p119">实时传输协议数据包来往于一个终结点所需的平均时间量（以毫秒为单位）。来回行程的时间小于或等于 200 毫秒被视为质量可接受。</span><span class="sxs-lookup"><span data-stu-id="e0231-p119">Average amount of time (in milliseconds) required for a Real-Time Transport Protocol packet to travel to one endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="e0231-p120">高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。</span><span class="sxs-lookup"><span data-stu-id="e0231-p120">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0231-210"><strong>数据包丢失</strong></span><span class="sxs-lookup"><span data-stu-id="e0231-210"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="e0231-211">否</span><span class="sxs-lookup"><span data-stu-id="e0231-211">No</span></span></p></td>
<td><p><span data-ttu-id="e0231-p121">平均 RTP 数据包丢失率。（当 RTP 数据包（一项用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时将发生数据包丢失。）高丢失率通常是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器超载造成的，从而导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="e0231-p121">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0231-215"><strong>抖动(毫秒)</strong></span><span class="sxs-lookup"><span data-stu-id="e0231-215"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="e0231-216">否</span><span class="sxs-lookup"><span data-stu-id="e0231-216">No</span></span></p></td>
<td><p><span data-ttu-id="e0231-217">在 RTP 数据包到达之间检查到的平均抖动率。</span><span class="sxs-lookup"><span data-stu-id="e0231-217">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="e0231-218"> (抖动是 shakiness 的衡量指标 &quot; &quot; 。 ) 高抖动值通常由拥塞或过载的媒体服务器引起，并导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="e0231-218">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0231-219"><strong>修复程序隐藏比率</strong></span><span class="sxs-lookup"><span data-stu-id="e0231-219"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="e0231-220">否</span><span class="sxs-lookup"><span data-stu-id="e0231-220">No</span></span></p></td>
<td><p><span data-ttu-id="e0231-p123">隐藏的音频样本与样本总数的平均比率。（隐藏的音频样本是一项技术，用于消除通常由丢弃的网络数据包造成的意外转换。）高值指示数据包丢失或抖动造成的显著的丢失隐藏级别，从而导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="e0231-p123">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0231-223"><strong>修复程序拉伸比率</strong></span><span class="sxs-lookup"><span data-stu-id="e0231-223"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="e0231-224">否</span><span class="sxs-lookup"><span data-stu-id="e0231-224">No</span></span></p></td>
<td><p><span data-ttu-id="e0231-p124">拉伸的音频样本数与样本总数的平均比率。（拉伸的音频是一类已扩展的音频，可在检测到丢弃的网络数据包时帮助保持呼叫质量。）高值指示抖动造成的显著的样本拉伸级别，从而导致音频听起来很机械或失真。</span><span class="sxs-lookup"><span data-stu-id="e0231-p124">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0231-227"><strong>修复程序压缩比率</strong></span><span class="sxs-lookup"><span data-stu-id="e0231-227"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="e0231-228">否</span><span class="sxs-lookup"><span data-stu-id="e0231-228">No</span></span></p></td>
<td><p><span data-ttu-id="e0231-p125">压缩的音频样本与样本总数的平均比率。（压缩的音频是一类已压缩的音频，可在检测到丢弃的网络数据包时帮助保持呼叫质量。）高值指示抖动造成的显著的样本压缩级别，从而导致音频听起来像是已加速或失真。</span><span class="sxs-lookup"><span data-stu-id="e0231-p125">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

