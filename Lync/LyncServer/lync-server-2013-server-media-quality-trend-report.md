---
title: Lync Server 2013：服务器媒体质量趋势报表
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
ms.openlocfilehash: c4efb7e2f29c1da75a81f4df4ec586c396d77d3d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732432"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-media-quality-trend-report-in-lync-server-2013"></a><span data-ttu-id="b47ff-102">Lync Server 2013 中的 "服务器媒体质量趋势" 报表</span><span class="sxs-lookup"><span data-stu-id="b47ff-102">Server Media Quality Trend Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b47ff-103">_**主题上次修改时间：** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="b47ff-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="b47ff-104">服务器媒体质量趋势报告提供了一种以图形方式比较多达5台服务器的方式，如呼叫音量、通话百分比差、数据包丢失和抖动等。</span><span class="sxs-lookup"><span data-stu-id="b47ff-104">The Server Media Quality Trend Report provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span> <span data-ttu-id="b47ff-105">这使得执行标识性能不佳的服务器、未充分利用的服务器或使用过度的服务器之类的操作变得更简单。</span><span class="sxs-lookup"><span data-stu-id="b47ff-105">This makes it easier to do such things as identify servers that are performing poorly, identify servers that are underutilized, or identify servers that are being overused.</span></span>

<div>

## <a name="accessing-the-server-media-quality-trend-report"></a><span data-ttu-id="b47ff-106">访问服务器媒体质量趋势报告</span><span class="sxs-lookup"><span data-stu-id="b47ff-106">Accessing the Server Media Quality Trend Report</span></span>

<span data-ttu-id="b47ff-107">服务器媒体质量趋势报告可从下列任一报告进行访问：</span><span class="sxs-lookup"><span data-stu-id="b47ff-107">The Server Media Quality Trend Report can be accessed from either one of the following report:</span></span>

  - <span data-ttu-id="b47ff-108">[Lync server 2013 中的服务器性能报告](lync-server-2013-server-performance-report.md)（通过单击趋势指标）</span><span class="sxs-lookup"><span data-stu-id="b47ff-108">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Trend metric)</span></span>

  - <span data-ttu-id="b47ff-109">[Lync server 2013 中的 "呼叫详细信息" 报告](lync-server-2013-call-detail-report.md)（通过单击 "A/V 边缘" 服务器指标）。</span><span class="sxs-lookup"><span data-stu-id="b47ff-109">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) (by clicking the A/V edge server metric.</span></span> <span data-ttu-id="b47ff-110">如果呼叫者或被叫方是服务器，您也可以通过单击终结点名称来到达 "服务器质量" 媒体趋势报告。</span><span class="sxs-lookup"><span data-stu-id="b47ff-110">If the caller or callee is a server, you can also reach the Server Quality Media Trend Report by clicking the endpoint name.)</span></span>

</div>

<div>

## <a name="making-the-best-use-of-server-media-quality-trend-report"></a><span data-ttu-id="b47ff-111">充分利用服务器媒体质量趋势报告</span><span class="sxs-lookup"><span data-stu-id="b47ff-111">Making the Best Use of Server Media Quality Trend Report</span></span>

<span data-ttu-id="b47ff-112">单击特定服务器的[Lync server 2013 中的 "服务器性能报告](lync-server-2013-server-performance-report.md)" 上的 "趋势指标" 时，将打开 "服务器媒体质量" 趋势报告。</span><span class="sxs-lookup"><span data-stu-id="b47ff-112">When you click the Trend metric on the [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) for a specific server, the Server Media Quality Trend Report will open.</span></span> <span data-ttu-id="b47ff-113">但是，您只会看到该报告的一个空白实例；您在服务器性能报告上选择的服务器将不会显示在屏幕上。</span><span class="sxs-lookup"><span data-stu-id="b47ff-113">However, you will see only a blank instance of that report; the server you selected on the Server Performance Report will not be displayed onscreen.</span></span> <span data-ttu-id="b47ff-114">相反，您需要从“服务器”下拉列表中选择服务器。</span><span class="sxs-lookup"><span data-stu-id="b47ff-114">Instead, you will need to select that server from the Servers dropdown.</span></span> <span data-ttu-id="b47ff-115">还要注意，“服务器”下拉列表包含“全选”选项。</span><span class="sxs-lookup"><span data-stu-id="b47ff-115">Note, too that the Servers dropdown includes a Select All option.</span></span> <span data-ttu-id="b47ff-116">此选项在您具有 5 台以上的服务器时不起作用；服务器媒体质量趋势报告一次最多只能显示 5 台服务器的数据。</span><span class="sxs-lookup"><span data-stu-id="b47ff-116">This option will not work if you have more than 5 servers; the Server Media Quality Trend Report can only display data for a maximum of 5 servers at a time.</span></span>

<span data-ttu-id="b47ff-117">在 "服务器媒体质量趋势" 报表显示的图形上，标记为 "呼叫音量" 和 "差通话百分比" 的点为 hotlinks。单击图表上的某个点将[在 Lync Server 2013 中打开 "呼叫列表" 报表](lync-server-2013-call-list-report.md)的一个实例，显示指定时间段内的总调用（或较差的调用）。</span><span class="sxs-lookup"><span data-stu-id="b47ff-117">On the graphs displayed by the Server Media Quality Trend Report, the points labeled Call Volume and Poor Call Percentage are hotlinks; clicking a point on the graph will open an instance of the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) showing the total calls (or poor calls) for the specified time period.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="b47ff-118">筛选器</span><span class="sxs-lookup"><span data-stu-id="b47ff-118">Filters</span></span>

<span data-ttu-id="b47ff-p104">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。下表列出了可用于服务器媒体质量趋势报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="b47ff-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-filters"></a><span data-ttu-id="b47ff-121">服务器媒体质量趋势报告筛选器</span><span class="sxs-lookup"><span data-stu-id="b47ff-121">Server Media Quality Trend Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b47ff-122">名称</span><span class="sxs-lookup"><span data-stu-id="b47ff-122">Name</span></span></th>
<th><span data-ttu-id="b47ff-123">说明</span><span class="sxs-lookup"><span data-stu-id="b47ff-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b47ff-124"><strong>从</strong></span><span class="sxs-lookup"><span data-stu-id="b47ff-124"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="b47ff-p105">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b47ff-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="b47ff-127">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="b47ff-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b47ff-p106">如果您未输入开始时间，该报告会自动将将某个特定日期的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="b47ff-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b47ff-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b47ff-130">7/7/2012</span></span></p>
<p><span data-ttu-id="b47ff-131">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="b47ff-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b47ff-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b47ff-132">7/3/2012</span></span></p>
<p><span data-ttu-id="b47ff-133">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="b47ff-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b47ff-134"><strong>到</strong></span><span class="sxs-lookup"><span data-stu-id="b47ff-134"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="b47ff-p107">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b47ff-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="b47ff-137">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="b47ff-137">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b47ff-p108">如果您未输入结束时间，该报告会自动将某个特定日期的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="b47ff-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b47ff-140">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b47ff-140">7/7/2012</span></span></p>
<p><span data-ttu-id="b47ff-141">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="b47ff-141">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b47ff-142">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b47ff-142">7/3/2012</span></span></p>
<p><span data-ttu-id="b47ff-143">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="b47ff-143">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b47ff-144"><strong>间隔</strong></span><span class="sxs-lookup"><span data-stu-id="b47ff-144"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="b47ff-p109">时间间隔。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="b47ff-p109">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b47ff-147">每小时（最多可显示 25 个小时）</span><span class="sxs-lookup"><span data-stu-id="b47ff-147">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="b47ff-148">每天（最多可显示 31 天）</span><span class="sxs-lookup"><span data-stu-id="b47ff-148">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="b47ff-149">每周（最多可显示 12 周）</span><span class="sxs-lookup"><span data-stu-id="b47ff-149">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="b47ff-150">如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。</span><span class="sxs-lookup"><span data-stu-id="b47ff-150">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="b47ff-151">例如，如果选择 "开始日期 8/7/2012" 和 "结束日期 9/28/2012" 的 "每日间隔"，则会显示 8/7/2012 12:00 AM 到 9/7/2012 12:00 AM 的数据（即，总共31天的数据）。</span><span class="sxs-lookup"><span data-stu-id="b47ff-151">For example, if you select the Daily interval with a start date of 8/7/2012 and an end date of 9/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b47ff-152"><strong>服务器类型</strong></span><span class="sxs-lookup"><span data-stu-id="b47ff-152"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="b47ff-p111">呼叫中涉及的服务器类型。允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="b47ff-p111">Type of server involved in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="b47ff-155">中介服务器</span><span class="sxs-lookup"><span data-stu-id="b47ff-155">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="b47ff-156">A/V 会议服务器</span><span class="sxs-lookup"><span data-stu-id="b47ff-156">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="b47ff-157">A/V 边缘服务器</span><span class="sxs-lookup"><span data-stu-id="b47ff-157">A/V Edge Server</span></span></p></li>
<li><p><span data-ttu-id="b47ff-158">网关（中介服务器）</span><span class="sxs-lookup"><span data-stu-id="b47ff-158">Gateway (Mediation Server)</span></span></p></li>
<li><p><span data-ttu-id="b47ff-159">网关（中介服务器旁路）</span><span class="sxs-lookup"><span data-stu-id="b47ff-159">Gateway (Mediation Server Bypass)</span></span></p></li>
<li><p><span data-ttu-id="b47ff-160">AS 会议服务器</span><span class="sxs-lookup"><span data-stu-id="b47ff-160">AS Conferencing Server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b47ff-161"><strong>服务器</strong></span><span class="sxs-lookup"><span data-stu-id="b47ff-161"><strong>Servers</strong></span></span></p></td>
<td><p><span data-ttu-id="b47ff-p112">会话中涉及的服务器的名称；此下拉列表将基于服务器类型筛选器的值自动为您填充。编译报告时最多可选择 5 台不同的服务器。</span><span class="sxs-lookup"><span data-stu-id="b47ff-p112">Name of the server involved in the session; this dropdown list is automatically populated for you based on the value of the Server type filter. You can select up to 5 different servers when compiling a report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b47ff-164"><strong>访问类型</strong></span><span class="sxs-lookup"><span data-stu-id="b47ff-164"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="b47ff-p113">指示参与者是登录到内部网络还是从外部网络登录。允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="b47ff-p113">Indicates whether the participant was logged on to the internal network or from the external network. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="b47ff-167">[所有]</span><span class="sxs-lookup"><span data-stu-id="b47ff-167">[All]</span></span></p></li>
<li><p><span data-ttu-id="b47ff-168">内部</span><span class="sxs-lookup"><span data-stu-id="b47ff-168">Internal</span></span></p></li>
<li><p><span data-ttu-id="b47ff-169">外部</span><span class="sxs-lookup"><span data-stu-id="b47ff-169">External</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b47ff-170"><strong>网络类型</strong></span><span class="sxs-lookup"><span data-stu-id="b47ff-170"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="b47ff-p114">指示参与者连接到的网络的类型。允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="b47ff-p114">Indicates the type of network the participant was connected to. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="b47ff-173">[所有]</span><span class="sxs-lookup"><span data-stu-id="b47ff-173">[All]</span></span></p></li>
<li><p><span data-ttu-id="b47ff-174">有线</span><span class="sxs-lookup"><span data-stu-id="b47ff-174">Wired</span></span></p></li>
<li><p><span data-ttu-id="b47ff-175">无线</span><span class="sxs-lookup"><span data-stu-id="b47ff-175">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b47ff-176"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="b47ff-176"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="b47ff-p115">指示外部参与者在会话期间使用的是否是虚拟专用网 (VPN) 连接。允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="b47ff-p115">Indicates whether an external participant was using a virtual private network (VPN) connection during the session. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="b47ff-179">[所有]</span><span class="sxs-lookup"><span data-stu-id="b47ff-179">[All]</span></span></p></li>
<li><p><span data-ttu-id="b47ff-180">VPN</span><span class="sxs-lookup"><span data-stu-id="b47ff-180">VPN</span></span></p></li>
<li><p><span data-ttu-id="b47ff-181">非 VPN</span><span class="sxs-lookup"><span data-stu-id="b47ff-181">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="b47ff-182">指标</span><span class="sxs-lookup"><span data-stu-id="b47ff-182">Metrics</span></span>

<span data-ttu-id="b47ff-183">下表列出了服务器媒体质量趋势报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="b47ff-183">The following table lists the information provided in the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-metrics"></a><span data-ttu-id="b47ff-184">服务器媒体质量趋势报告指标</span><span class="sxs-lookup"><span data-stu-id="b47ff-184">Server Media Quality Trend Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b47ff-185">名称</span><span class="sxs-lookup"><span data-stu-id="b47ff-185">Name</span></span></th>
<th><span data-ttu-id="b47ff-186">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="b47ff-186">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b47ff-187">描述</span><span class="sxs-lookup"><span data-stu-id="b47ff-187">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b47ff-188"><strong>呼叫量</strong></span><span class="sxs-lookup"><span data-stu-id="b47ff-188"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="b47ff-189">否</span><span class="sxs-lookup"><span data-stu-id="b47ff-189">No</span></span></p></td>
<td><p><span data-ttu-id="b47ff-190">呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="b47ff-190">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b47ff-191"><strong>性能降低 (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="b47ff-191"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="b47ff-192">否</span><span class="sxs-lookup"><span data-stu-id="b47ff-192">No</span></span></p></td>
<td><p><span data-ttu-id="b47ff-193">呼叫过程中遇到的性能降低的 MOS（平均意见得分）的平均值。</span><span class="sxs-lookup"><span data-stu-id="b47ff-193">Average amount of MOS (mean option score) degradation experienced during a call.</span></span> <span data-ttu-id="b47ff-194">性能降低值的范围介于 0.0 和 5.0 之间；该值小于或等于 0.5 表示可接受的性能降低。</span><span class="sxs-lookup"><span data-stu-id="b47ff-194">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="b47ff-195">过去，平均意见得分是通过让用户对呼叫质量进行评级（范围为 1 到 5）来计算得出的。</span><span class="sxs-lookup"><span data-stu-id="b47ff-195">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="b47ff-196">Lync 服务器使用一组算法来预测用户对呼叫的评分。</span><span class="sxs-lookup"><span data-stu-id="b47ff-196">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="b47ff-p117">高性能降低值可能是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器或终结点超载造成的，从而导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="b47ff-p117">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b47ff-199"><strong>质量欠佳的呼叫百分比</strong></span><span class="sxs-lookup"><span data-stu-id="b47ff-199"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="b47ff-200">否</span><span class="sxs-lookup"><span data-stu-id="b47ff-200">No</span></span></p></td>
<td><p><span data-ttu-id="b47ff-p118">归类为质量欠佳的呼叫的总数。质量欠佳的呼叫是指至少一项测量指标超过允许的值的任何呼叫（例如，信号极不稳定的呼叫）。</span><span class="sxs-lookup"><span data-stu-id="b47ff-p118">The total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b47ff-203"><strong>来回行程（毫秒）</strong></span><span class="sxs-lookup"><span data-stu-id="b47ff-203"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="b47ff-204">否</span><span class="sxs-lookup"><span data-stu-id="b47ff-204">No</span></span></p></td>
<td><p><span data-ttu-id="b47ff-p119">实时传输协议数据包来往于一个终结点所需的平均时间量（以毫秒为单位）。来回行程的时间小于或等于 200 毫秒被视为质量可接受。</span><span class="sxs-lookup"><span data-stu-id="b47ff-p119">Average amount of time (in milliseconds) required for a Real-Time Transport Protocol packet to travel to one endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="b47ff-p120">高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。</span><span class="sxs-lookup"><span data-stu-id="b47ff-p120">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b47ff-209"><strong>数据包丢失</strong></span><span class="sxs-lookup"><span data-stu-id="b47ff-209"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="b47ff-210">否</span><span class="sxs-lookup"><span data-stu-id="b47ff-210">No</span></span></p></td>
<td><p><span data-ttu-id="b47ff-p121">平均实时传输协议 (RTP) 数据包丢失率。（当 RTP 数据包（一项用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时，即发生数据包丢失。）高丢失率通常是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器超载造成的。数据包丢失通常导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="b47ff-p121">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b47ff-214"><strong>抖动（毫秒）</strong></span><span class="sxs-lookup"><span data-stu-id="b47ff-214"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="b47ff-215">否</span><span class="sxs-lookup"><span data-stu-id="b47ff-215">No</span></span></p></td>
<td><p><span data-ttu-id="b47ff-216">在 RTP 数据包到达之间检测到的平均抖动率。</span><span class="sxs-lookup"><span data-stu-id="b47ff-216">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="b47ff-217">（抖动是&quot;shakiness&quot;通话的衡量。）高抖动值通常由拥塞或过载的媒体服务器导致，并导致失真或丢失的音频。</span><span class="sxs-lookup"><span data-stu-id="b47ff-217">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b47ff-218"><strong>修复程序隐藏比率</strong></span><span class="sxs-lookup"><span data-stu-id="b47ff-218"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="b47ff-219">否</span><span class="sxs-lookup"><span data-stu-id="b47ff-219">No</span></span></p></td>
<td><p><span data-ttu-id="b47ff-p123">隐藏的音频样本与样本总数的平均比率。（隐藏的音频样本是一项技术，用于消除通常由丢弃的网络数据包造成的意外转换。）高值指示数据包丢失或抖动造成的显著的丢失隐藏级别，从而导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="b47ff-p123">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b47ff-222"><strong>修复程序拉伸比率</strong></span><span class="sxs-lookup"><span data-stu-id="b47ff-222"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="b47ff-223">否</span><span class="sxs-lookup"><span data-stu-id="b47ff-223">No</span></span></p></td>
<td><p><span data-ttu-id="b47ff-p124">拉伸的音频样本数与样本总数的平均比率。（拉伸的音频是一类已扩展的音频，可在检测到丢弃的网络数据包时帮助保持呼叫质量。）高值指示抖动造成的显著的样本拉伸级别，从而导致音频听起来很机械或失真。</span><span class="sxs-lookup"><span data-stu-id="b47ff-p124">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b47ff-226"><strong>修复程序压缩比率</strong></span><span class="sxs-lookup"><span data-stu-id="b47ff-226"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="b47ff-227">否</span><span class="sxs-lookup"><span data-stu-id="b47ff-227">No</span></span></p></td>
<td><p><span data-ttu-id="b47ff-p125">压缩的音频样本与样本总数的平均比率。（压缩的音频是一类已压缩的音频，可在检测到丢弃的网络数据包时帮助保持呼叫质量。）高值指示抖动造成的显著的样本压缩级别，从而导致音频听起来像是已加速或失真。</span><span class="sxs-lookup"><span data-stu-id="b47ff-p125">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

