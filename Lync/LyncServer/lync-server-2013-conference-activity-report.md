---
title: 'Lync Server 2013: 会议活动报告'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Activity Report
ms:assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558627(v=OCS.15)
ms:contentKeyID: 48183618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f96ddc5dfda18fa1d96903eb5755481f76853c06
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837504"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-activity-report-in-lync-server-2013"></a><span data-ttu-id="81cb1-102">Lync Server 2013 中的 "会议活动" 报表</span><span class="sxs-lookup"><span data-stu-id="81cb1-102">Conference Activity Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81cb1-103">_**主题上次修改时间:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="81cb1-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="81cb1-104">会议活动报表使你可以轻松地回答以下问题: 每天保持多少个会议以及何时保留这些会议？</span><span class="sxs-lookup"><span data-stu-id="81cb1-104">The Conference Activity Report makes it easy for you to answer questions like these: how many conferences are being held each day, and when are those conferences being held?</span></span> <span data-ttu-id="81cb1-105">此类信息不仅非常有用, 还可以作为疑难解答工具使用。</span><span class="sxs-lookup"><span data-stu-id="81cb1-105">Information like this is useful not only in its own right, but also as a troubleshooting tool.</span></span> <span data-ttu-id="81cb1-106">例如, 假设用户抱怨, 网络在一天的中间似乎非常慢。</span><span class="sxs-lookup"><span data-stu-id="81cb1-106">For example, suppose users are complaining that the network seems particularly slow in the middle of the day.</span></span> <span data-ttu-id="81cb1-107">快速浏览会议活动报表可能会提出一个可能的原因: 在 10:00 AM 和 2:00 PM 之间安排的会议时间比现在更多。</span><span class="sxs-lookup"><span data-stu-id="81cb1-107">A quick glance at the Conference Activity reports might suggest one possible reason: far more conferences are being scheduled between the hours of 10:00 AM and 2:00 PM then at any other time.</span></span>

<span data-ttu-id="81cb1-108">如果因网速慢而导致出现问题，您可以鼓励用户将他们的一些会议重新安排在一天中流量较少的时段。</span><span class="sxs-lookup"><span data-stu-id="81cb1-108">If the slow network is causing problems, you can encourage users to reschedule some of their conferences during the less-heavily trafficked times of the day.</span></span>

<div>

## <a name="accessing-the-conference-activity-report"></a><span data-ttu-id="81cb1-109">访问会议活动报告</span><span class="sxs-lookup"><span data-stu-id="81cb1-109">Accessing the Conference Activity Report</span></span>

<span data-ttu-id="81cb1-110">通过单击以下任一指标, 可从[Lync Server 2013 中的 "会议摘要" 报告](lync-server-2013-conference-summary-report.md)访问会议活动报告:</span><span class="sxs-lookup"><span data-stu-id="81cb1-110">The Conference Activity Report is accessed from the [Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md) by clicking either one of the following metrics:</span></span>

  - <span data-ttu-id="81cb1-111">会议总数</span><span class="sxs-lookup"><span data-stu-id="81cb1-111">Total conferences</span></span>

  - <span data-ttu-id="81cb1-112">参与者总数</span><span class="sxs-lookup"><span data-stu-id="81cb1-112">Total participants</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-activity-report"></a><span data-ttu-id="81cb1-113">充分利用会议活动报告</span><span class="sxs-lookup"><span data-stu-id="81cb1-113">Making the Best Use of the Conference Activity Report</span></span>

<span data-ttu-id="81cb1-p102">默认情况下，会议活动报告向您显示指定时段内的会议总数（例如，每天的会议总数或每小时的会议总数）。但是，您还可以选择显示该时段内与会者的总数或总参与分钟数。为此，请单击“显示/隐藏参数”按钮以显示筛选选项，然后从“报告依据”下拉列表中选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="81cb1-p102">By default the Conference Activity Report shows you the total number of conferences for the specified time period (for example, the total number of conferences per day, or the total number of conferences per hour of the day). However, you can also choose to display the total number of participants for that time period or the total number of participant minutes. To do that, click the Show/Hide Parameters button to display the filtering options, and then select one of the following from the Report by dropdown list:</span></span>

  - <span data-ttu-id="81cb1-117">参与者计数</span><span class="sxs-lookup"><span data-stu-id="81cb1-117">Participant count</span></span>

  - <span data-ttu-id="81cb1-118">参与分钟数</span><span class="sxs-lookup"><span data-stu-id="81cb1-118">Participant minutes</span></span>

  - <span data-ttu-id="81cb1-119">会议计数</span><span class="sxs-lookup"><span data-stu-id="81cb1-119">Conference count</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="81cb1-120">筛选器</span><span class="sxs-lookup"><span data-stu-id="81cb1-120">Filters</span></span>

<span data-ttu-id="81cb1-p103">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。下表列出了可用于会议活动报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="81cb1-p103">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Activity Report.</span></span>

### <a name="conference-activity-report-filters"></a><span data-ttu-id="81cb1-123">会议活动报告筛选器</span><span class="sxs-lookup"><span data-stu-id="81cb1-123">Conference Activity Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81cb1-124">名称</span><span class="sxs-lookup"><span data-stu-id="81cb1-124">Name</span></span></th>
<th><span data-ttu-id="81cb1-125">说明</span><span class="sxs-lookup"><span data-stu-id="81cb1-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81cb1-126"><strong>从</strong></span><span class="sxs-lookup"><span data-stu-id="81cb1-126"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="81cb1-p104">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="81cb1-p104">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="81cb1-129">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="81cb1-129">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="81cb1-p105">如果您未输入开始时间，该报告会自动将将某个特定日期的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="81cb1-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="81cb1-132">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="81cb1-132">7/7/2012</span></span></p>
<p><span data-ttu-id="81cb1-133">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="81cb1-133">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="81cb1-134">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="81cb1-134">7/3/2012</span></span></p>
<p><span data-ttu-id="81cb1-135">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="81cb1-135">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81cb1-136"><strong>到</strong></span><span class="sxs-lookup"><span data-stu-id="81cb1-136"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="81cb1-p106">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="81cb1-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="81cb1-139">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="81cb1-139">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="81cb1-p107">如果您未输入结束时间，该报告会自动将某个特定日期的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="81cb1-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="81cb1-142">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="81cb1-142">7/7/2012</span></span></p>
<p><span data-ttu-id="81cb1-143">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="81cb1-143">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="81cb1-144">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="81cb1-144">7/3/2012</span></span></p>
<p><span data-ttu-id="81cb1-145">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="81cb1-145">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81cb1-146"><strong>间隔</strong></span><span class="sxs-lookup"><span data-stu-id="81cb1-146"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="81cb1-p108">时间间隔。选择下列任意选项：</span><span class="sxs-lookup"><span data-stu-id="81cb1-p108">Time interval. Select any of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="81cb1-149">每小时（最多可显示 25 个小时）</span><span class="sxs-lookup"><span data-stu-id="81cb1-149">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="81cb1-150">每天（最多可显示 31 天）</span><span class="sxs-lookup"><span data-stu-id="81cb1-150">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="81cb1-151">每周（最多可显示 12 周）</span><span class="sxs-lookup"><span data-stu-id="81cb1-151">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="81cb1-152">每月（最多可显示 12 个月）</span><span class="sxs-lookup"><span data-stu-id="81cb1-152">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="81cb1-153">如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。</span><span class="sxs-lookup"><span data-stu-id="81cb1-153">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="81cb1-154">例如, 如果选择 "开始日期 7/7/2012" 和 "结束日期 2/28/2012" 的 "每日间隔", 则会显示 8/7/2012 12:00 AM 到 9/7/2012 12:00 AM 的数据 (即, 总共31天的数据)。</span><span class="sxs-lookup"><span data-stu-id="81cb1-154">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81cb1-155"><strong>报告依据</strong></span><span class="sxs-lookup"><span data-stu-id="81cb1-155"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="81cb1-p110">指示要在报告中使用的值。可选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="81cb1-p110">Indicates the values to be used in the report. You can select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="81cb1-158">参与者计数</span><span class="sxs-lookup"><span data-stu-id="81cb1-158">Participant Count</span></span></p></li>
<li><p><span data-ttu-id="81cb1-159">参与分钟数</span><span class="sxs-lookup"><span data-stu-id="81cb1-159">Participant Minutes</span></span></p></li>
<li><p><span data-ttu-id="81cb1-160">会议计数</span><span class="sxs-lookup"><span data-stu-id="81cb1-160">Conference Count</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="81cb1-161">按池分类的会议的指标</span><span class="sxs-lookup"><span data-stu-id="81cb1-161">Metrics for Conferences by Pool</span></span>

<span data-ttu-id="81cb1-162">下表列出了每个池的会议活动报告中的信息。</span><span class="sxs-lookup"><span data-stu-id="81cb1-162">The following table lists the information in the Conference Activity Report for each pool.</span></span>

### <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="81cb1-163">按池分类的会议的指标</span><span class="sxs-lookup"><span data-stu-id="81cb1-163">Metrics for Conferences by Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81cb1-164">名称</span><span class="sxs-lookup"><span data-stu-id="81cb1-164">Name</span></span></th>
<th><span data-ttu-id="81cb1-165">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="81cb1-165">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="81cb1-166">描述</span><span class="sxs-lookup"><span data-stu-id="81cb1-166">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81cb1-167"><strong>池</strong></span><span class="sxs-lookup"><span data-stu-id="81cb1-167"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="81cb1-168">否</span><span class="sxs-lookup"><span data-stu-id="81cb1-168">No</span></span></p></td>
<td><p><span data-ttu-id="81cb1-169">会议中使用的注册器池或边缘服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="81cb1-169">Name of the Registrar pool or Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81cb1-170"><strong>日期/时间</strong></span><span class="sxs-lookup"><span data-stu-id="81cb1-170"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="81cb1-171">否</span><span class="sxs-lookup"><span data-stu-id="81cb1-171">No</span></span></p></td>
<td><p><span data-ttu-id="81cb1-172">召开会议的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="81cb1-172">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81cb1-173"><strong>总计</strong></span><span class="sxs-lookup"><span data-stu-id="81cb1-173"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="81cb1-174">否</span><span class="sxs-lookup"><span data-stu-id="81cb1-174">No</span></span></p></td>
<td><p><span data-ttu-id="81cb1-175">参与者总数、总参与时间（以分钟计）或会议总数。</span><span class="sxs-lookup"><span data-stu-id="81cb1-175">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="81cb1-176">按服务器类型分类的会议的指标</span><span class="sxs-lookup"><span data-stu-id="81cb1-176">Metrics for Conferences by Server Type</span></span>

<span data-ttu-id="81cb1-177">下表列出了每种服务器类型的会议活动报告中的信息。</span><span class="sxs-lookup"><span data-stu-id="81cb1-177">The following table lists the information in the Conference Activity Report for each type of server.</span></span>

### <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="81cb1-178">按服务器类型分类的会议的指标</span><span class="sxs-lookup"><span data-stu-id="81cb1-178">Metrics for Conferences by Server Type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81cb1-179">名称</span><span class="sxs-lookup"><span data-stu-id="81cb1-179">Name</span></span></th>
<th><span data-ttu-id="81cb1-180">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="81cb1-180">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="81cb1-181">描述</span><span class="sxs-lookup"><span data-stu-id="81cb1-181">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81cb1-182"><strong>会议服务器类型</strong></span><span class="sxs-lookup"><span data-stu-id="81cb1-182"><strong>Conferencing server type</strong></span></span></p></td>
<td><p><span data-ttu-id="81cb1-183">否</span><span class="sxs-lookup"><span data-stu-id="81cb1-183">No</span></span></p></td>
<td><p><span data-ttu-id="81cb1-184">会议中使用的服务器的类型，通常为下列类型之一：</span><span class="sxs-lookup"><span data-stu-id="81cb1-184">Type of server used in the conference, typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="81cb1-185">Web 会议服务器</span><span class="sxs-lookup"><span data-stu-id="81cb1-185">Web Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="81cb1-186">IM 会议服务器</span><span class="sxs-lookup"><span data-stu-id="81cb1-186">IM Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="81cb1-187">电话会议服务器</span><span class="sxs-lookup"><span data-stu-id="81cb1-187">Telephony Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="81cb1-188">AV 会议服务器</span><span class="sxs-lookup"><span data-stu-id="81cb1-188">AV Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="81cb1-189">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="81cb1-189">Application Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81cb1-190"><strong>日期/时间</strong></span><span class="sxs-lookup"><span data-stu-id="81cb1-190"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="81cb1-191">否</span><span class="sxs-lookup"><span data-stu-id="81cb1-191">No</span></span></p></td>
<td><p><span data-ttu-id="81cb1-192">召开会议的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="81cb1-192">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81cb1-193"><strong>总计</strong></span><span class="sxs-lookup"><span data-stu-id="81cb1-193"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="81cb1-194">否</span><span class="sxs-lookup"><span data-stu-id="81cb1-194">No</span></span></p></td>
<td><p><span data-ttu-id="81cb1-195">参与者总数、总参与时间（以分钟计）或会议总数。</span><span class="sxs-lookup"><span data-stu-id="81cb1-195">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

