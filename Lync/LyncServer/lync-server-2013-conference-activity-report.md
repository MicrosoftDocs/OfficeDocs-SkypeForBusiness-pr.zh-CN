---
title: Lync Server 2013：会议活动报告
description: Lync Server 2013：会议活动报告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Activity Report
ms:assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558627(v=OCS.15)
ms:contentKeyID: 48183618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7a2b23a08970defaec62b98d075ad1167527fd7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577648"
---
# <a name="conference-activity-report-in-lync-server-2013"></a><span data-ttu-id="1c0db-103">Lync Server 2013 中的会议活动报告</span><span class="sxs-lookup"><span data-stu-id="1c0db-103">Conference Activity Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c0db-104">_**上次修改的主题：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="1c0db-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="1c0db-105">会议活动报告使您能够轻松地回答以下问题：每天举行的会议数是多少，何时正在举行这些会议？</span><span class="sxs-lookup"><span data-stu-id="1c0db-105">The Conference Activity Report makes it easy for you to answer questions like these: how many conferences are being held each day, and when are those conferences being held?</span></span> <span data-ttu-id="1c0db-106">此类信息不仅适用于自己的权限，而且也是一种故障排除工具。</span><span class="sxs-lookup"><span data-stu-id="1c0db-106">Information like this is useful not only in its own right, but also as a troubleshooting tool.</span></span> <span data-ttu-id="1c0db-107">例如，假设用户抱怨，网络在一天中似乎非常缓慢。</span><span class="sxs-lookup"><span data-stu-id="1c0db-107">For example, suppose users are complaining that the network seems particularly slow in the middle of the day.</span></span> <span data-ttu-id="1c0db-108">若要快速浏览会议活动报告，可能会提出一个可能的原因：在任何其他时间，在 10:00 AM 和 2:00 PM 之间安排的会议量超过该时间。</span><span class="sxs-lookup"><span data-stu-id="1c0db-108">A quick glance at the Conference Activity reports might suggest one possible reason: far more conferences are being scheduled between the hours of 10:00 AM and 2:00 PM then at any other time.</span></span>

<span data-ttu-id="1c0db-109">如果因网速慢而导致出现问题，您可以鼓励用户将他们的一些会议重新安排在一天中流量较少的时段。</span><span class="sxs-lookup"><span data-stu-id="1c0db-109">If the slow network is causing problems, you can encourage users to reschedule some of their conferences during the less-heavily trafficked times of the day.</span></span>

<div>

## <a name="accessing-the-conference-activity-report"></a><span data-ttu-id="1c0db-110">访问会议活动报告</span><span class="sxs-lookup"><span data-stu-id="1c0db-110">Accessing the Conference Activity Report</span></span>

<span data-ttu-id="1c0db-111">可通过单击以下任一指标 [在 Lync Server 2013 中的 "会议摘要" 报告中](lync-server-2013-conference-summary-report.md) 访问会议活动报告：</span><span class="sxs-lookup"><span data-stu-id="1c0db-111">The Conference Activity Report is accessed from the [Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md) by clicking either one of the following metrics:</span></span>

  - <span data-ttu-id="1c0db-112">会议总数</span><span class="sxs-lookup"><span data-stu-id="1c0db-112">Total conferences</span></span>

  - <span data-ttu-id="1c0db-113">参与者总数</span><span class="sxs-lookup"><span data-stu-id="1c0db-113">Total participants</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-activity-report"></a><span data-ttu-id="1c0db-114">充分利用会议活动报告</span><span class="sxs-lookup"><span data-stu-id="1c0db-114">Making the Best Use of the Conference Activity Report</span></span>

<span data-ttu-id="1c0db-p102">默认情况下，会议活动报告向您显示指定时段内的会议总数（例如，每天的会议总数或每小时的会议总数）。但是，您还可以选择显示该时段内与会者的总数或总参与分钟数。为此，请单击“显示/隐藏参数”按钮以显示筛选选项，然后从“报告依据”下拉列表中选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="1c0db-p102">By default the Conference Activity Report shows you the total number of conferences for the specified time period (for example, the total number of conferences per day, or the total number of conferences per hour of the day). However, you can also choose to display the total number of participants for that time period or the total number of participant minutes. To do that, click the Show/Hide Parameters button to display the filtering options, and then select one of the following from the Report by dropdown list:</span></span>

  - <span data-ttu-id="1c0db-118">参与者计数</span><span class="sxs-lookup"><span data-stu-id="1c0db-118">Participant count</span></span>

  - <span data-ttu-id="1c0db-119">参与分钟数</span><span class="sxs-lookup"><span data-stu-id="1c0db-119">Participant minutes</span></span>

  - <span data-ttu-id="1c0db-120">会议计数</span><span class="sxs-lookup"><span data-stu-id="1c0db-120">Conference count</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="1c0db-121">筛选器</span><span class="sxs-lookup"><span data-stu-id="1c0db-121">Filters</span></span>

<span data-ttu-id="1c0db-p103">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。下表列出了可用于会议活动报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="1c0db-p103">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Activity Report.</span></span>

### <a name="conference-activity-report-filters"></a><span data-ttu-id="1c0db-124">会议活动报告筛选器</span><span class="sxs-lookup"><span data-stu-id="1c0db-124">Conference Activity Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1c0db-125">名称</span><span class="sxs-lookup"><span data-stu-id="1c0db-125">Name</span></span></th>
<th><span data-ttu-id="1c0db-126">说明</span><span class="sxs-lookup"><span data-stu-id="1c0db-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c0db-127"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="1c0db-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="1c0db-p104">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1c0db-p104">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="1c0db-130">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="1c0db-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1c0db-p105">如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="1c0db-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1c0db-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1c0db-133">7/7/2012</span></span></p>
<p><span data-ttu-id="1c0db-134">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="1c0db-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1c0db-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1c0db-135">7/3/2012</span></span></p>
<p><span data-ttu-id="1c0db-136">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="1c0db-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c0db-137"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="1c0db-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="1c0db-p106">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1c0db-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="1c0db-140">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="1c0db-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1c0db-p107">如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="1c0db-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1c0db-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1c0db-143">7/7/2012</span></span></p>
<p><span data-ttu-id="1c0db-144">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="1c0db-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1c0db-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1c0db-145">7/3/2012</span></span></p>
<p><span data-ttu-id="1c0db-146">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="1c0db-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c0db-147"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="1c0db-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="1c0db-p108">时间间隔。选择下列任意选项：</span><span class="sxs-lookup"><span data-stu-id="1c0db-p108">Time interval. Select any of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1c0db-150">每小时（最多可显示 25 个小时）</span><span class="sxs-lookup"><span data-stu-id="1c0db-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="1c0db-151">每天（最多可显示 31 天）</span><span class="sxs-lookup"><span data-stu-id="1c0db-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="1c0db-152">每周（最多可显示 12 周）</span><span class="sxs-lookup"><span data-stu-id="1c0db-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="1c0db-153">每月（最多可显示 12 个月）</span><span class="sxs-lookup"><span data-stu-id="1c0db-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="1c0db-p109">如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。例如，如果选择的开始日期为 8/7/2012、结束日期为 9/28/2012、间隔为“每天”，则显示从 8/7/2012 12:00 AM 到 9/7/2012 12:00 AM 这些天的数据（即总共 31 天的数据）。</span><span class="sxs-lookup"><span data-stu-id="1c0db-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c0db-156"><strong>报告依据</strong></span><span class="sxs-lookup"><span data-stu-id="1c0db-156"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="1c0db-p110">指示要在报告中使用的值。可选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="1c0db-p110">Indicates the values to be used in the report. You can select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1c0db-159">参与者计数</span><span class="sxs-lookup"><span data-stu-id="1c0db-159">Participant Count</span></span></p></li>
<li><p><span data-ttu-id="1c0db-160">参与分钟数</span><span class="sxs-lookup"><span data-stu-id="1c0db-160">Participant Minutes</span></span></p></li>
<li><p><span data-ttu-id="1c0db-161">会议计数</span><span class="sxs-lookup"><span data-stu-id="1c0db-161">Conference Count</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="1c0db-162">按池分类的会议的指标</span><span class="sxs-lookup"><span data-stu-id="1c0db-162">Metrics for Conferences by Pool</span></span>

<span data-ttu-id="1c0db-163">下表列出了每个池的会议活动报告中的信息。</span><span class="sxs-lookup"><span data-stu-id="1c0db-163">The following table lists the information in the Conference Activity Report for each pool.</span></span>

### <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="1c0db-164">按池分类的会议的指标</span><span class="sxs-lookup"><span data-stu-id="1c0db-164">Metrics for Conferences by Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1c0db-165">名称</span><span class="sxs-lookup"><span data-stu-id="1c0db-165">Name</span></span></th>
<th><span data-ttu-id="1c0db-166">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="1c0db-166">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1c0db-167">说明</span><span class="sxs-lookup"><span data-stu-id="1c0db-167">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c0db-168"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="1c0db-168"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="1c0db-169">否</span><span class="sxs-lookup"><span data-stu-id="1c0db-169">No</span></span></p></td>
<td><p><span data-ttu-id="1c0db-170">会议中使用的注册器池或边缘服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="1c0db-170">Name of the Registrar pool or Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c0db-171"><strong>日期/时间</strong></span><span class="sxs-lookup"><span data-stu-id="1c0db-171"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="1c0db-172">否</span><span class="sxs-lookup"><span data-stu-id="1c0db-172">No</span></span></p></td>
<td><p><span data-ttu-id="1c0db-173">召开会议的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="1c0db-173">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c0db-174"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="1c0db-174"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="1c0db-175">否</span><span class="sxs-lookup"><span data-stu-id="1c0db-175">No</span></span></p></td>
<td><p><span data-ttu-id="1c0db-176">参与者总数、总参与时间（以分钟计）或会议总数。</span><span class="sxs-lookup"><span data-stu-id="1c0db-176">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="1c0db-177">按服务器类型分类的会议的指标</span><span class="sxs-lookup"><span data-stu-id="1c0db-177">Metrics for Conferences by Server Type</span></span>

<span data-ttu-id="1c0db-178">下表列出了每种服务器类型的会议活动报告中的信息。</span><span class="sxs-lookup"><span data-stu-id="1c0db-178">The following table lists the information in the Conference Activity Report for each type of server.</span></span>

### <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="1c0db-179">按服务器类型分类的会议的指标</span><span class="sxs-lookup"><span data-stu-id="1c0db-179">Metrics for Conferences by Server Type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1c0db-180">名称</span><span class="sxs-lookup"><span data-stu-id="1c0db-180">Name</span></span></th>
<th><span data-ttu-id="1c0db-181">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="1c0db-181">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1c0db-182">说明</span><span class="sxs-lookup"><span data-stu-id="1c0db-182">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c0db-183"><strong>会议服务器类型</strong></span><span class="sxs-lookup"><span data-stu-id="1c0db-183"><strong>Conferencing server type</strong></span></span></p></td>
<td><p><span data-ttu-id="1c0db-184">否</span><span class="sxs-lookup"><span data-stu-id="1c0db-184">No</span></span></p></td>
<td><p><span data-ttu-id="1c0db-185">会议中使用的服务器的类型，通常为下列类型之一：</span><span class="sxs-lookup"><span data-stu-id="1c0db-185">Type of server used in the conference, typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1c0db-186">Web 会议服务器</span><span class="sxs-lookup"><span data-stu-id="1c0db-186">Web Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="1c0db-187">IM 会议服务器</span><span class="sxs-lookup"><span data-stu-id="1c0db-187">IM Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="1c0db-188">电话会议服务器</span><span class="sxs-lookup"><span data-stu-id="1c0db-188">Telephony Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="1c0db-189">AV 会议服务器</span><span class="sxs-lookup"><span data-stu-id="1c0db-189">AV Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="1c0db-190">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="1c0db-190">Application Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c0db-191"><strong>日期/时间</strong></span><span class="sxs-lookup"><span data-stu-id="1c0db-191"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="1c0db-192">否</span><span class="sxs-lookup"><span data-stu-id="1c0db-192">No</span></span></p></td>
<td><p><span data-ttu-id="1c0db-193">召开会议的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="1c0db-193">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c0db-194"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="1c0db-194"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="1c0db-195">否</span><span class="sxs-lookup"><span data-stu-id="1c0db-195">No</span></span></p></td>
<td><p><span data-ttu-id="1c0db-196">参与者总数、总参与时间（以分钟计）或会议总数。</span><span class="sxs-lookup"><span data-stu-id="1c0db-196">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

