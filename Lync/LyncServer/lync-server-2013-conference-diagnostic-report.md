---
title: 'Lync Server 2013: 会议诊断报告'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Diagnostic Report
ms:assetid: e9edc23c-8ce8-4ab8-8786-9d22e1e51e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615042(v=OCS.15)
ms:contentKeyID: 48185901
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 279d844a4c67d3b09b35fff92f6868cae8971059
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837500"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="52127-102">Lync Server 2013 中的会议诊断报告</span><span class="sxs-lookup"><span data-stu-id="52127-102">Conference Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52127-103">_**主题上次修改时间:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="52127-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="52127-104">会议诊断报告提供有关所有会议会话成功和失败的信息。</span><span class="sxs-lookup"><span data-stu-id="52127-104">The Conference Diagnostic Report provides information about the success and failure of all conferencing sessions.</span></span> <span data-ttu-id="52127-105">请注意, Microsoft Lync Server 区分不同类型的故障:</span><span class="sxs-lookup"><span data-stu-id="52127-105">Note that Microsoft Lync Server distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="52127-p102">**预期失败**。预期失败通常仅是大多数技术意义上的失败。例如，假定有人启动会议，但在任何人可加入前挂起。技术上的失败：会议已启动，但没有完成。但是，以下是预期发生的失败：如果任何人可加入前组织取消会议，则将不会预期会议要完成。</span><span class="sxs-lookup"><span data-stu-id="52127-p102">**Expected failure**. An expected failure is typically a failure only in the most technical sense. For example, suppose someone starts a conference but hangs up before anyone can join. Technically that's a failure: the conference was initiated, but not completed. However, that's a failure that you would expect to happen: if the organizer cancels the conference before anyone can join then you would not expect that conference to be completed.</span></span>

  - <span data-ttu-id="52127-p103">**意外失败**。意外错误完全可顾名思义为：您预期不会发生的一种基于环境的错误。例如，假如因无法检索组织的会议策略而无法举行会议。那就是意外错误：毕竟，您应该始终能够检索用户的会议策略。</span><span class="sxs-lookup"><span data-stu-id="52127-p103">**Unexpected failure**. An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur. For example, suppose a conference could not be held because the organizer's meeting policy could not be retrieved. That's an unexpected error: after all, you should always be able to retrieve a user's meeting policy.</span></span>

<span data-ttu-id="52127-p104">请注意，成功、预期失败和意外失败指标可能无法添加到总会话数指标。例如，可能会看到报告中的下列值：</span><span class="sxs-lookup"><span data-stu-id="52127-p104">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric. For example, you might see the following values in the Report:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52127-117">成功</span><span class="sxs-lookup"><span data-stu-id="52127-117">Successes</span></span></th>
<th><span data-ttu-id="52127-118">预期失败</span><span class="sxs-lookup"><span data-stu-id="52127-118">Expected failures</span></span></th>
<th><span data-ttu-id="52127-119">意外失败</span><span class="sxs-lookup"><span data-stu-id="52127-119">Unexpected failures</span></span></th>
<th><span data-ttu-id="52127-120">会话总数</span><span class="sxs-lookup"><span data-stu-id="52127-120">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52127-121">2024</span><span class="sxs-lookup"><span data-stu-id="52127-121">2024</span></span></p></td>
<td><p><span data-ttu-id="52127-122">469</span><span class="sxs-lookup"><span data-stu-id="52127-122">469</span></span></p></td>
<td><p><span data-ttu-id="52127-123">utf-16</span><span class="sxs-lookup"><span data-stu-id="52127-123">16</span></span></p></td>
<td><p><span data-ttu-id="52127-124">2521</span><span class="sxs-lookup"><span data-stu-id="52127-124">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="52127-125">如果 2024 + 469 + 16 得到 2,509 个会话，而总会话列显示 2,521 个总会话数。</span><span class="sxs-lookup"><span data-stu-id="52127-125">If you add 2024 + 469 + 16 you get a total of 2,509 sessions and yet, the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="52127-126">“丢失的”12 个会话是系统无法作为成功或失败进行分类的会话。</span><span class="sxs-lookup"><span data-stu-id="52127-126">The "missing" 12 sessions for are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="52127-127">在第三方产品引入了监视服务器不熟悉的新诊断代码时, 有时会出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="52127-127">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Monitoring Server.</span></span> <span data-ttu-id="52127-128">如果发生这种情况，使用该产品制定的呼叫和报告该诊断代码的呼叫无法总是作为成功、预期失败或意外失败进行分类。</span><span class="sxs-lookup"><span data-stu-id="52127-128">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-conference-diagnostic-report"></a><span data-ttu-id="52127-129">访问会议诊断报告</span><span class="sxs-lookup"><span data-stu-id="52127-129">Accessing the Conference Diagnostic Report</span></span>

<span data-ttu-id="52127-130">可从监控报告主页访问会议诊断报告。</span><span class="sxs-lookup"><span data-stu-id="52127-130">The Conference Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="52127-131">您可以通过单击以下任一指标来访问[Lync Server 2013 中的失败分发报告](lync-server-2013-failure-distribution-report.md):</span><span class="sxs-lookup"><span data-stu-id="52127-131">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="52127-132">意外失败量</span><span class="sxs-lookup"><span data-stu-id="52127-132">Unexpected failure volume</span></span>

  - <span data-ttu-id="52127-133">预期失败量</span><span class="sxs-lookup"><span data-stu-id="52127-133">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-diagnostic-report"></a><span data-ttu-id="52127-134">充分利用会议诊断报告</span><span class="sxs-lookup"><span data-stu-id="52127-134">Making the Best Use of the Conference Diagnostic Report</span></span>

<span data-ttu-id="52127-135">会议诊断报告包括一系列图形。</span><span class="sxs-lookup"><span data-stu-id="52127-135">The Conference Diagnostic Report includes a series of graphs.</span></span> <span data-ttu-id="52127-136">图形中显示的每个列实际是个超链接。</span><span class="sxs-lookup"><span data-stu-id="52127-136">Each of the columns shown in the graph is actually a hyperlink.</span></span> <span data-ttu-id="52127-137">如果单击某一列, 您将向下钻取到[Lync Server 2013 中的 "失败分配" 报表](lync-server-2013-failure-distribution-report.md), 了解该时间段以及该会议类型。</span><span class="sxs-lookup"><span data-stu-id="52127-137">If you click a column, you'll drill down to the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) for that time period and that conference type.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="52127-138">筛选器</span><span class="sxs-lookup"><span data-stu-id="52127-138">Filters</span></span>

<span data-ttu-id="52127-p108">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，会议诊断报告允许您依据举行的会议类型（例如，基于会议状态中心的会议）或会议使用的边缘服务器等条件进行筛选。您还可以选择数据的分组方式。在此示例中，将按小时、日、周或月对会议进行分组。</span><span class="sxs-lookup"><span data-stu-id="52127-p108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Conference Diagnostic Report enables you to filter on such things as the type of conference being conducted (for example, a Focus-based conference) or by the Edge Server used in the conference. You can also choose how data should be grouped. In this case, conferences are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="52127-143">下表列出了可用于会议诊断报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="52127-143">The following table lists the filters that you can use with the Conference Diagnostic Report.</span></span>

### <a name="conference-diagnostic-report-filters"></a><span data-ttu-id="52127-144">会议诊断报告筛选器</span><span class="sxs-lookup"><span data-stu-id="52127-144">Conference Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52127-145">名称</span><span class="sxs-lookup"><span data-stu-id="52127-145">Name</span></span></th>
<th><span data-ttu-id="52127-146">说明</span><span class="sxs-lookup"><span data-stu-id="52127-146">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52127-147"><strong>从</strong></span><span class="sxs-lookup"><span data-stu-id="52127-147"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="52127-p109">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="52127-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="52127-150">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="52127-150">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="52127-p110">如果您未输入开始时间，该报告会自动将将某个特定日期的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="52127-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="52127-153">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="52127-153">7/7/2012</span></span></p>
<p><span data-ttu-id="52127-154">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="52127-154">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="52127-155">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="52127-155">7/3/2012</span></span></p>
<p><span data-ttu-id="52127-156">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="52127-156">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52127-157"><strong>到</strong></span><span class="sxs-lookup"><span data-stu-id="52127-157"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="52127-p111">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="52127-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="52127-160">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="52127-160">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="52127-p112">如果您未输入结束时间，该报告会自动将某个特定日期的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="52127-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="52127-163">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="52127-163">7/7/2012</span></span></p>
<p><span data-ttu-id="52127-164">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="52127-164">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="52127-165">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="52127-165">7/3/2012</span></span></p>
<p><span data-ttu-id="52127-166">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="52127-166">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52127-167"><strong>间隔</strong></span><span class="sxs-lookup"><span data-stu-id="52127-167"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="52127-p113">时间间隔。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="52127-p113">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="52127-170">每小时（最多可显示 25 个小时）</span><span class="sxs-lookup"><span data-stu-id="52127-170">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="52127-171">每天（最多可显示 31 天）</span><span class="sxs-lookup"><span data-stu-id="52127-171">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="52127-172">每周（最多可显示 12 周）</span><span class="sxs-lookup"><span data-stu-id="52127-172">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="52127-173">每月（最多可显示 12 个月）</span><span class="sxs-lookup"><span data-stu-id="52127-173">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="52127-174">如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。</span><span class="sxs-lookup"><span data-stu-id="52127-174">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="52127-175">例如, 如果选择 "开始日期 7/7/2012" 和 "结束日期 2/28/2012" 的 "每日间隔", 则会显示 8/7/2012 12:00 AM 到 9/7/2012 12:00 AM 的数据 (即, 总共31天的数据)。</span><span class="sxs-lookup"><span data-stu-id="52127-175">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52127-176"><strong>池</strong></span><span class="sxs-lookup"><span data-stu-id="52127-176"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="52127-p115">注册器池或边缘服务器的完全限定域名 (FQDN)。可以选择单个池，也可以单击“<strong>[所有]</strong>”查看所有池的数据。系统根据数据库中的记录自动为您填充该下拉列表。</span><span class="sxs-lookup"><span data-stu-id="52127-p115">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52127-180"><strong>会议会话</strong></span><span class="sxs-lookup"><span data-stu-id="52127-180"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="52127-p116">指示会议会话的类型。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="52127-p116">Indicates the type of conferencing session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="52127-183">[所有]</span><span class="sxs-lookup"><span data-stu-id="52127-183">[All]</span></span></p></li>
<li><p><span data-ttu-id="52127-184">焦点会话</span><span class="sxs-lookup"><span data-stu-id="52127-184">Focus sessions</span></span></p></li>
<li><p><span data-ttu-id="52127-185">所有 MCU 会话</span><span class="sxs-lookup"><span data-stu-id="52127-185">All MCU sessions</span></span></p></li>
<li><p><span data-ttu-id="52127-186">IM 会议</span><span class="sxs-lookup"><span data-stu-id="52127-186">IM conferencing</span></span></p></li>
<li><p><span data-ttu-id="52127-187">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="52127-187">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="52127-188">A/V 会议</span><span class="sxs-lookup"><span data-stu-id="52127-188">A/V conferencing</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="52127-189">指标</span><span class="sxs-lookup"><span data-stu-id="52127-189">Metrics</span></span>

<span data-ttu-id="52127-190">下表列出了每种会议会话的会议诊断报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="52127-190">The following table lists the information provided in the Conference Diagnostic Report for each type of conferencing session.</span></span>

### <a name="conference-diagnostic-report-metrics"></a><span data-ttu-id="52127-191">会议诊断报告指标</span><span class="sxs-lookup"><span data-stu-id="52127-191">Conference Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52127-192">名称</span><span class="sxs-lookup"><span data-stu-id="52127-192">Name</span></span></th>
<th><span data-ttu-id="52127-193">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="52127-193">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="52127-194">描述</span><span class="sxs-lookup"><span data-stu-id="52127-194">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52127-195"><strong>成功量</strong></span><span class="sxs-lookup"><span data-stu-id="52127-195"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="52127-196">否</span><span class="sxs-lookup"><span data-stu-id="52127-196">No</span></span></p></td>
<td><p><span data-ttu-id="52127-197">成功的会议总数。</span><span class="sxs-lookup"><span data-stu-id="52127-197">Total number of successful conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52127-198"><strong>成功百分比</strong></span><span class="sxs-lookup"><span data-stu-id="52127-198"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="52127-199">否</span><span class="sxs-lookup"><span data-stu-id="52127-199">No</span></span></p></td>
<td><p><span data-ttu-id="52127-p117">已完成且没有严重问题的会议百分比。计算方法是“成功量”除以“会话总数”。</span><span class="sxs-lookup"><span data-stu-id="52127-p117">Percentage of conferences that completed with significant problems. Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52127-202"><strong>预期失败量</strong></span><span class="sxs-lookup"><span data-stu-id="52127-202"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="52127-203">否</span><span class="sxs-lookup"><span data-stu-id="52127-203">No</span></span></p></td>
<td><p><span data-ttu-id="52127-204">&quot;预计发生故障&quot;的会议的总数。</span><span class="sxs-lookup"><span data-stu-id="52127-204">Total number of conferences where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="52127-p118">预期失败是指预计会出现的失败情况。例如，如果用户将其状态设置为“请勿打扰”，那么向该用户发出的任何呼叫应该都会失败。</span><span class="sxs-lookup"><span data-stu-id="52127-p118">An expected failure is a failure that is expected to happen. For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52127-207"><strong>预期失败百分比</strong></span><span class="sxs-lookup"><span data-stu-id="52127-207"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="52127-208">否</span><span class="sxs-lookup"><span data-stu-id="52127-208">No</span></span></p></td>
<td><p><span data-ttu-id="52127-p119">遇到预期错误的会议百分比。计算方法是“预期失败量”除以“会话总数”。</span><span class="sxs-lookup"><span data-stu-id="52127-p119">Percentage of conferences that experienced an expected error. Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52127-211"><strong>意外失败量</strong></span><span class="sxs-lookup"><span data-stu-id="52127-211"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="52127-212">否</span><span class="sxs-lookup"><span data-stu-id="52127-212">No</span></span></p></td>
<td><p><span data-ttu-id="52127-213">发生&quot;意外失败&quot;的会议的总数。</span><span class="sxs-lookup"><span data-stu-id="52127-213">Total number of conferences where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="52127-p120">意外失败是指在本该正常运行的系统中出现的失败情况。例如，如果呼叫者处于呼叫等待状态，则不应该终止呼叫。如果终止，则会被标记为意外失败。</span><span class="sxs-lookup"><span data-stu-id="52127-p120">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system. For example, a call should not be terminated if the caller is placed on hold. If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52127-217"><strong>意外失败百分比</strong></span><span class="sxs-lookup"><span data-stu-id="52127-217"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="52127-218">否</span><span class="sxs-lookup"><span data-stu-id="52127-218">No</span></span></p></td>
<td><p><span data-ttu-id="52127-p121">遇到意外错误的会议百分比。计算方法是“意外失败量”除以“会话总数”。</span><span class="sxs-lookup"><span data-stu-id="52127-p121">Percentage of conferences that experienced an unexpected error. Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52127-221"><strong>会话总数</strong></span><span class="sxs-lookup"><span data-stu-id="52127-221"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="52127-222">否</span><span class="sxs-lookup"><span data-stu-id="52127-222">No</span></span></p></td>
<td><p><span data-ttu-id="52127-223">会议总数，包括成功的会议、失败的会议（预期失败和意外失败）和未归类的会议。</span><span class="sxs-lookup"><span data-stu-id="52127-223">Total number of conferences, including successful conferences, failed conferences (both expected failures and unexpected failures), and uncategorized conferences.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

