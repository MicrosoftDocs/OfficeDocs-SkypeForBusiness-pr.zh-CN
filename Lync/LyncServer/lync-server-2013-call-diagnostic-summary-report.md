---
title: Lync Server 2013：呼叫诊断摘要报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Diagnostic Summary Report
ms:assetid: 9091de56-13e6-440e-9353-f57c10c906fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615016(v=OCS.15)
ms:contentKeyID: 48184789
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 112a21dbb131e0bd34729584b8fb58399b192f70
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044484"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-summary-report-in-lync-server-2013"></a><span data-ttu-id="e0078-102">Lync Server 2013 中的呼叫诊断摘要报告</span><span class="sxs-lookup"><span data-stu-id="e0078-102">Call Diagnostic Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0078-103">_**上次修改的主题：** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="e0078-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="e0078-p101">呼叫诊断摘要报告提供失败的点对点会话和会议会话的整体情况。该报告显示了两种类型的会话的整体故障率，并按以下会话形式类型进一步为故障信息分类：</span><span class="sxs-lookup"><span data-stu-id="e0078-p101">The Call Diagnostic Summary Report provides an overall look at failed peer-to-peer and conferencing sessions. The report shows the overall failure rate for both types of sessions, and further breaks the failure information down by session modality type:</span></span>

  - <span data-ttu-id="e0078-106">即时消息</span><span class="sxs-lookup"><span data-stu-id="e0078-106">Instant messaging</span></span>

  - <span data-ttu-id="e0078-107">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="e0078-107">Application sharing</span></span>

  - <span data-ttu-id="e0078-108">文件传输</span><span class="sxs-lookup"><span data-stu-id="e0078-108">File transfer</span></span>

  - <span data-ttu-id="e0078-109">音频</span><span class="sxs-lookup"><span data-stu-id="e0078-109">Audio</span></span>

  - <span data-ttu-id="e0078-110">视频</span><span class="sxs-lookup"><span data-stu-id="e0078-110">Video</span></span>

<div>

## <a name="accessing-the-call-diagnostic-summary-report"></a><span data-ttu-id="e0078-111">访问呼叫诊断摘要报告</span><span class="sxs-lookup"><span data-stu-id="e0078-111">Accessing the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="e0078-112">呼叫诊断摘要报告是从监控报告主页访问的。</span><span class="sxs-lookup"><span data-stu-id="e0078-112">The Call Diagnostic Summary Report is accessed from the Monitoring Reports Home page.</span></span> <span data-ttu-id="e0078-113">在呼叫诊断摘要报告中，您可以通过单击报告的 "对等会话摘要" 部分下的 "故障率" 指标，[在 Lync Server 2013 中访问对等活动诊断报告](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)。</span><span class="sxs-lookup"><span data-stu-id="e0078-113">From the Call Diagnostic Summary Report you can access the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) by clicking the Failure rate metric under the Peer-to-Peer Session Summary section of the report.</span></span> <span data-ttu-id="e0078-114">您还可以通过单击以下任一会议指标，[在 Lync Server 2013 中访问会议诊断报告](lync-server-2013-conference-diagnostic-report.md)：</span><span class="sxs-lookup"><span data-stu-id="e0078-114">You can also access the [Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) by clicking any of the following conference metrics:</span></span>

  - <span data-ttu-id="e0078-115">总体会话故障率</span><span class="sxs-lookup"><span data-stu-id="e0078-115">Overall session failure rate</span></span>

  - <span data-ttu-id="e0078-116">焦点故障率</span><span class="sxs-lookup"><span data-stu-id="e0078-116">Focus failure rate</span></span>

  - <span data-ttu-id="e0078-117">MCU 故障率</span><span class="sxs-lookup"><span data-stu-id="e0078-117">MCU failure rate</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a><span data-ttu-id="e0078-118">充分利用呼叫诊断摘要报告</span><span class="sxs-lookup"><span data-stu-id="e0078-118">Making the Best Use of the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="e0078-119">呼叫诊断摘要报告包含的图表将对 Microsoft Lync Server 2013 中使用的各种形式的故障率进行比较。</span><span class="sxs-lookup"><span data-stu-id="e0078-119">The Call Diagnostic Summary Report includes graphs that compare failure rates for the various modalities used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="e0078-120">这些图形中的列实际上是 hotlinks;例如，如果单击对等会话的 "即时消息" 列，则将向下钻取到[Lync Server 2013 中对等活动诊断报告](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)的实例，该报告提供了有关呼叫诊断摘要报告中包括的所有即时消息会话的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="e0078-120">The columns in these graphs are actually hotlinks; for example, if you click the Instant messaging column for peer-to-peer sessions, you'll drill down to an instance of the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md), a report that provides additional details about all the instant messaging sessions included in the Call Diagnostic Summary Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="e0078-121">筛选器</span><span class="sxs-lookup"><span data-stu-id="e0078-121">Filters</span></span>

<span data-ttu-id="e0078-p104">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，呼叫诊断摘要报告允许您依据会话中使用的注册器池或边缘服务器等条件进行筛选。您还可以选择数据的分组方式。在此示例中，将按小时、天、周或月对呼叫进行分组。</span><span class="sxs-lookup"><span data-stu-id="e0078-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Call Diagnostic Summary Report enables you to filter on such things as the Registrar pool or Edge Server used in the session. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="e0078-126">下表列出了可用于呼叫诊断摘要报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="e0078-126">The following table lists the filters that you can use with the Call Diagnostic Summary Report.</span></span>

### <a name="call-diagnostic-summary-report-filters"></a><span data-ttu-id="e0078-127">呼叫诊断摘要报告筛选器</span><span class="sxs-lookup"><span data-stu-id="e0078-127">Call Diagnostic Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0078-128">名称</span><span class="sxs-lookup"><span data-stu-id="e0078-128">Name</span></span></th>
<th><span data-ttu-id="e0078-129">说明</span><span class="sxs-lookup"><span data-stu-id="e0078-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0078-130"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="e0078-130"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="e0078-p105">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e0078-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="e0078-133">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="e0078-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e0078-p106">如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="e0078-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e0078-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e0078-136">7/7/2012</span></span></p>
<p><span data-ttu-id="e0078-137">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="e0078-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e0078-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e0078-138">7/3/2012</span></span></p>
<p><span data-ttu-id="e0078-139">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="e0078-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0078-140"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="e0078-140"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="e0078-p107">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e0078-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="e0078-143">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="e0078-143">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e0078-p108">如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="e0078-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e0078-146">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e0078-146">7/7/2012</span></span></p>
<p><span data-ttu-id="e0078-147">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="e0078-147">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e0078-148">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e0078-148">7/3/2012</span></span></p>
<p><span data-ttu-id="e0078-149">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="e0078-149">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0078-150"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="e0078-150"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="e0078-p109">时间间隔。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="e0078-p109">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e0078-153">每小时（最多可显示 25 个小时）</span><span class="sxs-lookup"><span data-stu-id="e0078-153">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="e0078-154">每天（最多可显示 31 天）</span><span class="sxs-lookup"><span data-stu-id="e0078-154">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="e0078-155">每周（最多可显示 12 周）</span><span class="sxs-lookup"><span data-stu-id="e0078-155">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="e0078-156">每月（最多可显示 12 个月）</span><span class="sxs-lookup"><span data-stu-id="e0078-156">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="e0078-p110">如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。例如，如果选择的开始日期为 8/7/2012、结束日期为 9/28/2012、间隔为“每天”，则显示从 8/7/2012 12:00 AM 到 9/7/2012 12:00 AM 这些天的数据（即总共 31 天的数据）。</span><span class="sxs-lookup"><span data-stu-id="e0078-p110">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0078-159"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="e0078-159"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="e0078-p111">注册器池或边缘服务器的完全限定域名 (FQDN)。可以选择单个池，也可以单击“[所有]”<strong></strong>查看所有池的数据。系统根据数据库中的记录自动为您填充该下拉列表。</span><span class="sxs-lookup"><span data-stu-id="e0078-p111">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="e0078-163">点对点会话的指标</span><span class="sxs-lookup"><span data-stu-id="e0078-163">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="e0078-164">下表列出了点对点会话（即，只涉及两个参与者的会话）的呼叫诊断摘要报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="e0078-164">The following table lists the information provided in the Call Diagnostic Summary Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="e0078-165">点对点会话的指标</span><span class="sxs-lookup"><span data-stu-id="e0078-165">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0078-166">名称</span><span class="sxs-lookup"><span data-stu-id="e0078-166">Name</span></span></th>
<th><span data-ttu-id="e0078-167">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="e0078-167">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e0078-168">说明</span><span class="sxs-lookup"><span data-stu-id="e0078-168">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0078-169"><strong>会话总数</strong></span><span class="sxs-lookup"><span data-stu-id="e0078-169"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="e0078-170">否</span><span class="sxs-lookup"><span data-stu-id="e0078-170">No</span></span></p></td>
<td><p><span data-ttu-id="e0078-171">发起的点对点会话总数。</span><span class="sxs-lookup"><span data-stu-id="e0078-171">Total number of peer-to-peer sessions conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0078-172"><strong>故障率</strong></span><span class="sxs-lookup"><span data-stu-id="e0078-172"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="e0078-173">否</span><span class="sxs-lookup"><span data-stu-id="e0078-173">No</span></span></p></td>
<td><p><span data-ttu-id="e0078-p112">失败的点对点会话百分比。单击此项时，报告将显示点对点活动诊断报告，其中显示有关失败的点对点会话的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e0078-p112">Percentage of peer-to-peer sessions that failed. When you click this item, the report shows the Peer-to-Peer Activity Diagnostic report, which displays more detailed information about the failed peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="e0078-176">会议会话的指标</span><span class="sxs-lookup"><span data-stu-id="e0078-176">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="e0078-177">下表列出了会议会话（即，涉及三个或更多参与者的会话）的呼叫诊断报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="e0078-177">The following table lists the information provided in the Call Diagnostic Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="e0078-178">会议会话的指标</span><span class="sxs-lookup"><span data-stu-id="e0078-178">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0078-179">名称</span><span class="sxs-lookup"><span data-stu-id="e0078-179">Name</span></span></th>
<th><span data-ttu-id="e0078-180">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="e0078-180">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e0078-181">说明</span><span class="sxs-lookup"><span data-stu-id="e0078-181">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0078-182"><strong>会议总数</strong></span><span class="sxs-lookup"><span data-stu-id="e0078-182"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="e0078-183">否</span><span class="sxs-lookup"><span data-stu-id="e0078-183">No</span></span></p></td>
<td><p><span data-ttu-id="e0078-184">举行的会议总数。</span><span class="sxs-lookup"><span data-stu-id="e0078-184">Total number of conferences conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0078-185"><strong>会议会话总数</strong></span><span class="sxs-lookup"><span data-stu-id="e0078-185"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="e0078-186">否</span><span class="sxs-lookup"><span data-stu-id="e0078-186">No</span></span></p></td>
<td><p><span data-ttu-id="e0078-187">发起的会议会话总数。</span><span class="sxs-lookup"><span data-stu-id="e0078-187">Total number of conferencing sessions conducted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0078-188"><strong>总体会话故障率</strong></span><span class="sxs-lookup"><span data-stu-id="e0078-188"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="e0078-189">否</span><span class="sxs-lookup"><span data-stu-id="e0078-189">No</span></span></p></td>
<td><p><span data-ttu-id="e0078-190">失败的会议会话百分比。</span><span class="sxs-lookup"><span data-stu-id="e0078-190">Percentage of the total conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0078-191"><strong>焦点会话</strong></span><span class="sxs-lookup"><span data-stu-id="e0078-191"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="e0078-192">否</span><span class="sxs-lookup"><span data-stu-id="e0078-192">No</span></span></p></td>
<td><p><span data-ttu-id="e0078-193">失败的基于会议状态中心的会议会话总数。</span><span class="sxs-lookup"><span data-stu-id="e0078-193">Total number of Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0078-194"><strong>焦点故障率</strong></span><span class="sxs-lookup"><span data-stu-id="e0078-194"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="e0078-195">否</span><span class="sxs-lookup"><span data-stu-id="e0078-195">No</span></span></p></td>
<td><p><span data-ttu-id="e0078-196">失败的基于会议状态中心的会议会话百分比。</span><span class="sxs-lookup"><span data-stu-id="e0078-196">Percentage of the Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0078-197"><strong>MCU 会话</strong></span><span class="sxs-lookup"><span data-stu-id="e0078-197"><strong>MCU sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="e0078-198">否</span><span class="sxs-lookup"><span data-stu-id="e0078-198">No</span></span></p></td>
<td><p><span data-ttu-id="e0078-199">失败的基于会议服务器（以前称为多点控制单元，简称 MCU）的会议总数。</span><span class="sxs-lookup"><span data-stu-id="e0078-199">Total number of conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0078-200"><strong>MCU 故障率</strong></span><span class="sxs-lookup"><span data-stu-id="e0078-200"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="e0078-201">否</span><span class="sxs-lookup"><span data-stu-id="e0078-201">No</span></span></p></td>
<td><p><span data-ttu-id="e0078-202">失败的基于会议服务器（以前称为多点控制单元，简称 MCU）的会议百分比。</span><span class="sxs-lookup"><span data-stu-id="e0078-202">Percentage of the conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

