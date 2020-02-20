---
title: Lync Server 2013：会议摘要报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Summary Report
ms:assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558656(v=OCS.15)
ms:contentKeyID: 48184299
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5092bb6e2ae1a76ad878a28365515b470df031d2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145170"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-summary-report-in-lync-server-2013"></a><span data-ttu-id="6c8ce-102">Lync Server 2013 中的会议摘要报告</span><span class="sxs-lookup"><span data-stu-id="6c8ce-102">Conference Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c8ce-103">_**上次修改的主题：** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="6c8ce-103">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="6c8ce-104">会议摘要报告提供了联机会议会话的整体视图。</span><span class="sxs-lookup"><span data-stu-id="6c8ce-104">The Conference Summary Report provides an overall view of your online conferencing sessions.</span></span> <span data-ttu-id="6c8ce-105">会议通常涉及2个以上的用户，并且需要使用 Microsoft Lync Server 2013 会议服务。</span><span class="sxs-lookup"><span data-stu-id="6c8ce-105">A conference typically involves more than 2 users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="6c8ce-106">相比之下，对等会话一般仅涉及 2 个用户并且不需要使用 Lync Server 的会议服务。</span><span class="sxs-lookup"><span data-stu-id="6c8ce-106">By comparison, a peer-to-peer session typically involves just 2 users and does not require the use of Lync Server's conferencing services.</span></span> <span data-ttu-id="6c8ce-107">对等活动在[Lync Server 2013 中的对等活动摘要报告](lync-server-2013-peer-to-peer-activity-summary-report.md)上报告。</span><span class="sxs-lookup"><span data-stu-id="6c8ce-107">Peer-to-peer activities are reported on the [Peer-to-Peer Activity Summary Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md).</span></span>

<span data-ttu-id="6c8ce-108">会议摘要报告不仅告诉你在指定时间段（每小时、每天、每周、每月）期间召开了多少会议，还告诉你参与这些会议的人员总数以及唯一会议的总数者.</span><span class="sxs-lookup"><span data-stu-id="6c8ce-108">The Conference Summary Report not only tells you how many conferences were held during a given time period (hourly, daily, weekly, monthly) but also tells you the total number of people who took part in those conferences, and the total number of unique conference organizers.</span></span>

<span data-ttu-id="6c8ce-p102">“唯一”组织者是计划了至少一场会议的任何人。例如，如果 Pilar Ackerman 计划了一场会议，则她将算为一个唯一组织者。如果 Ken Myer 计划了 148 场会议，则他也将算为一个唯一组织者。例如，下表显示了计划的 8 场会议，但仅 3 个唯一组织者（Ken Myer、Pilar Ackerman 和 David Ahs）。</span><span class="sxs-lookup"><span data-stu-id="6c8ce-p102">A "unique” organizer is anyone who schedules at least one conference. For example, if Pilar Ackerman schedules one conference she counts as one unique organizer. If Ken Myer schedules 148 conferences he, too counts as one unique organizer. For example, the table below shows 8 conferences scheduled, but just three unique organizers (Ken Myer, Pilar Ackerman, and David Ahs).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6c8ce-113">会议组织者</span><span class="sxs-lookup"><span data-stu-id="6c8ce-113">Conference Organizer</span></span></th>
<th><span data-ttu-id="6c8ce-114">会议日期</span><span class="sxs-lookup"><span data-stu-id="6c8ce-114">Conference Date</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6c8ce-115">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="6c8ce-115">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="6c8ce-116">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="6c8ce-116">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8ce-117">David Ahs</span><span class="sxs-lookup"><span data-stu-id="6c8ce-117">David Ahs</span></span></p></td>
<td><p><span data-ttu-id="6c8ce-118">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="6c8ce-118">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8ce-119">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="6c8ce-119">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="6c8ce-120">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="6c8ce-120">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8ce-121">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="6c8ce-121">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="6c8ce-122">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="6c8ce-122">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8ce-123">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="6c8ce-123">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="6c8ce-124">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="6c8ce-124">7/7/2012 1:00 PM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8ce-125">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="6c8ce-125">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="6c8ce-126">7/7/2012 2:00 PM</span><span class="sxs-lookup"><span data-stu-id="6c8ce-126">7/7/2012 2:00 PM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8ce-127">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="6c8ce-127">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="6c8ce-128">7/2/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="6c8ce-128">7/2/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8ce-129">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="6c8ce-129">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="6c8ce-130">7/2/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="6c8ce-130">7/2/2012 10:00 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6c8ce-131">会议摘要报告还指示了包含音频和/或视频的会议数量。</span><span class="sxs-lookup"><span data-stu-id="6c8ce-131">The Conference Summary Report also indicates how many conferences included audio and/or video.</span></span>

<div>

## <a name="accessing-the-conference-summary-report"></a><span data-ttu-id="6c8ce-132">访问会议摘要报告</span><span class="sxs-lookup"><span data-stu-id="6c8ce-132">Accessing the Conference Summary Report</span></span>

<span data-ttu-id="6c8ce-p103">会议摘要报告是通过“监控报告”主页进行访问的。您可通过单击下列任一指标向下钻取至会议活动报告：</span><span class="sxs-lookup"><span data-stu-id="6c8ce-p103">The Conference Summary Report is accessed from the Monitoring Reports home page. You can drill down to the Conference Activity report by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="6c8ce-135">会议总数</span><span class="sxs-lookup"><span data-stu-id="6c8ce-135">Total conferences</span></span>

  - <span data-ttu-id="6c8ce-136">参与者总数</span><span class="sxs-lookup"><span data-stu-id="6c8ce-136">Total participants</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-summary-report"></a><span data-ttu-id="6c8ce-137">充分利用会议摘要报告</span><span class="sxs-lookup"><span data-stu-id="6c8ce-137">Making the Best Use of the Conference Summary Report</span></span>

<span data-ttu-id="6c8ce-p104">会议摘要报告上使用的大部分指标的合计值都可在此报告的底部找到；向下滚动可看到指定时间段内举行的会议总数以及参与这些会议的总人数等值。此报告底部未进行合计的一个指标是唯一会议组织者的总数。为什么不进行合计？以下是一个理由。假如您正查看一个月的数据。第 1 天，您有 34 个唯一会议组织者；第 2 天，您有 27 个唯一会议组织者。这是否意味着您在这两天有 61 个唯一会议组织者？不一定。毕竟第 2 天组织了会议的所有 27 个人可能就在第 1 天组织了会议的 34 个人中。例如，在以下简单的报告中，请注意，Ken Myer 和 Pilar Ackerman 在 7/7/2012 和 7/2/2012 这两天均组织了会议：</span><span class="sxs-lookup"><span data-stu-id="6c8ce-p104">Total values for most of the metrics used on the Conference Summary Report can be found at the bottom of the report; scroll down to see values such as the total number of conferences held during the specified time period, and the total number of people who participated in those conferences. One metric that is not totaled at the bottom of the report is Total unique conference organizers. Why not? Here’s one reason. Suppose you are looking at a month's worth of data. On day 1 you had 34 unique conference organizers; on day 2 you had 27 unique conference organizers. Does that mean you had 61 unique conference organizers for those two days? Not necessarily. After all, all 27 people who organized conferences on day 2 might be among the 34 people who organized conferences on day 1. For example, in this simple report, note that Ken Myer and Pilar Ackerman scheduled conferences both on 7/7/2012 and on 7/2/2012:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6c8ce-148">会议组织者</span><span class="sxs-lookup"><span data-stu-id="6c8ce-148">Conference Organizer</span></span></th>
<th><span data-ttu-id="6c8ce-149">会议日期</span><span class="sxs-lookup"><span data-stu-id="6c8ce-149">Conference Date</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6c8ce-150">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="6c8ce-150">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="6c8ce-151">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="6c8ce-151">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8ce-152">David Ahs</span><span class="sxs-lookup"><span data-stu-id="6c8ce-152">David Ahs</span></span></p></td>
<td><p><span data-ttu-id="6c8ce-153">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="6c8ce-153">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8ce-154">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="6c8ce-154">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="6c8ce-155">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="6c8ce-155">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8ce-156">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="6c8ce-156">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="6c8ce-157">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="6c8ce-157">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8ce-158">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="6c8ce-158">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="6c8ce-159">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="6c8ce-159">7/7/2012 1:00 PM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8ce-160">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="6c8ce-160">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="6c8ce-161">7/7/2012 2:00 PM</span><span class="sxs-lookup"><span data-stu-id="6c8ce-161">7/7/2012 2:00 PM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8ce-162">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="6c8ce-162">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="6c8ce-163">7/2/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="6c8ce-163">7/2/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8ce-164">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="6c8ce-164">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="6c8ce-165">7/2/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="6c8ce-165">7/2/2012 10:00 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6c8ce-166">若要更好地了解组织了会议的唯一用户的总数，请更改您的时间间隔；例如，按月而不是按天查看数据。</span><span class="sxs-lookup"><span data-stu-id="6c8ce-166">To get a better idea of the total number of unique users who organized conferences, change your time interval; for example, look at the data by month instead of by day.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="6c8ce-167">筛选器</span><span class="sxs-lookup"><span data-stu-id="6c8ce-167">Filters</span></span>

<span data-ttu-id="6c8ce-p105">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，会议摘要报告允许您选择数据的分组方式。在此示例中，将按小时、日、周或月对会议进行分组。</span><span class="sxs-lookup"><span data-stu-id="6c8ce-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Conference Summary Report enables you to choose how data should be grouped. In this case, conferences grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="6c8ce-171">下表列出了可用于会议摘要报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="6c8ce-171">The following table lists the filters that you can use with the Conference Summary Report.</span></span>

### <a name="conference-summary-report-filters"></a><span data-ttu-id="6c8ce-172">会议摘要报告筛选器</span><span class="sxs-lookup"><span data-stu-id="6c8ce-172">Conference Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6c8ce-173">名称</span><span class="sxs-lookup"><span data-stu-id="6c8ce-173">Name</span></span></th>
<th><span data-ttu-id="6c8ce-174">说明</span><span class="sxs-lookup"><span data-stu-id="6c8ce-174">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6c8ce-175"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="6c8ce-175"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="6c8ce-p106">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6c8ce-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="6c8ce-178">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="6c8ce-178">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="6c8ce-p107">如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="6c8ce-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="6c8ce-181">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="6c8ce-181">7/7/2012</span></span></p>
<p><span data-ttu-id="6c8ce-182">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="6c8ce-182">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="6c8ce-183">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="6c8ce-183">7/3/2012</span></span></p>
<p><span data-ttu-id="6c8ce-184">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="6c8ce-184">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8ce-185"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="6c8ce-185"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="6c8ce-p108">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6c8ce-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="6c8ce-188">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="6c8ce-188">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="6c8ce-p109">如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="6c8ce-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="6c8ce-191">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="6c8ce-191">7/7/2012</span></span></p>
<p><span data-ttu-id="6c8ce-192">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="6c8ce-192">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="6c8ce-193">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="6c8ce-193">7/3/2012</span></span></p>
<p><span data-ttu-id="6c8ce-194">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="6c8ce-194">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8ce-195"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="6c8ce-195"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="6c8ce-p110">时间间隔。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="6c8ce-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6c8ce-198">每小时（最多可显示 25 个小时）</span><span class="sxs-lookup"><span data-stu-id="6c8ce-198">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="6c8ce-199">每天（最多可显示 31 天）</span><span class="sxs-lookup"><span data-stu-id="6c8ce-199">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="6c8ce-200">每周（最多可显示 12 周）</span><span class="sxs-lookup"><span data-stu-id="6c8ce-200">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="6c8ce-201">每月（最多可显示 12 个月）</span><span class="sxs-lookup"><span data-stu-id="6c8ce-201">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="6c8ce-p111">如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。例如，如果选择的开始日期为 8/7/2012、结束日期为 9/28/2012、间隔为“每天”，则显示从 8/7/2012 12:00 AM 到 9/7/2012 12:00 AM 这些天的数据（即总共 31 天的数据）。</span><span class="sxs-lookup"><span data-stu-id="6c8ce-p111">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) are displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="6c8ce-204">指标</span><span class="sxs-lookup"><span data-stu-id="6c8ce-204">Metrics</span></span>

<span data-ttu-id="6c8ce-205">下表列出了由会议摘要报告提供的信息。</span><span class="sxs-lookup"><span data-stu-id="6c8ce-205">The following table the information provided by the Conferences Summary Report.</span></span>

### <a name="conference-summary-report-metrics"></a><span data-ttu-id="6c8ce-206">会议摘要报告指标</span><span class="sxs-lookup"><span data-stu-id="6c8ce-206">Conference Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6c8ce-207">名称</span><span class="sxs-lookup"><span data-stu-id="6c8ce-207">Name</span></span></th>
<th><span data-ttu-id="6c8ce-208">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="6c8ce-208">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="6c8ce-209">说明</span><span class="sxs-lookup"><span data-stu-id="6c8ce-209">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6c8ce-210"><strong>每小时</strong></span><span class="sxs-lookup"><span data-stu-id="6c8ce-210"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="6c8ce-211"><strong>每天</strong></span><span class="sxs-lookup"><span data-stu-id="6c8ce-211"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="6c8ce-212"><strong>每周</strong></span><span class="sxs-lookup"><span data-stu-id="6c8ce-212"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="6c8ce-213"><strong>每月</strong></span><span class="sxs-lookup"><span data-stu-id="6c8ce-213"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="6c8ce-214">否</span><span class="sxs-lookup"><span data-stu-id="6c8ce-214">No</span></span></p></td>
<td><p><span data-ttu-id="6c8ce-p112">指示在筛选器工具栏上选择的时间间隔。如果适用，可单击某一给定的时间间隔以查看该间隔的详细信息。例如，如果使用“每天”间隔并单击 7/7/2012，则可查看当日用户注册活动的每小时细分信息。</span><span class="sxs-lookup"><span data-stu-id="6c8ce-p112">Indicates the time interval that you selected on the filter toolbar. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8ce-218"><strong>会议总数</strong></span><span class="sxs-lookup"><span data-stu-id="6c8ce-218"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="6c8ce-219">否</span><span class="sxs-lookup"><span data-stu-id="6c8ce-219">No</span></span></p></td>
<td><p><span data-ttu-id="6c8ce-p113">举行的会议总数（不考虑会议类型）。单击此项时，报告将显示所选时间段的会议活动报告。</span><span class="sxs-lookup"><span data-stu-id="6c8ce-p113">Total number of conferences (regardless of conference type) that were held. When you click this item, the report shows you the Conference Activity Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8ce-222"><strong>参与者总数</strong></span><span class="sxs-lookup"><span data-stu-id="6c8ce-222"><strong>Total participants</strong></span></span></p></td>
<td><p><span data-ttu-id="6c8ce-223">否</span><span class="sxs-lookup"><span data-stu-id="6c8ce-223">No</span></span></p></td>
<td><p><span data-ttu-id="6c8ce-p114">参与会议的总人数。单击此项时，报告将显示所选时间段的会议活动报告。</span><span class="sxs-lookup"><span data-stu-id="6c8ce-p114">Total number of people who took part in the conferences. When you click this item, the report shows you the Conference Activity Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8ce-226"><strong>每个会议的平均参与者数</strong></span><span class="sxs-lookup"><span data-stu-id="6c8ce-226"><strong>Average participants per conference</strong></span></span></p></td>
<td><p><span data-ttu-id="6c8ce-227">否</span><span class="sxs-lookup"><span data-stu-id="6c8ce-227">No</span></span></p></td>
<td><p><span data-ttu-id="6c8ce-p115">参与给定会议的平均人数。计算方法是参与者总数除以会议总数。</span><span class="sxs-lookup"><span data-stu-id="6c8ce-p115">Average number of people who took part in a given conference. Determined by dividing the total conferences by the total participants.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8ce-230"><strong>A/V 会议总数</strong></span><span class="sxs-lookup"><span data-stu-id="6c8ce-230"><strong>Total A/V conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="6c8ce-231">否</span><span class="sxs-lookup"><span data-stu-id="6c8ce-231">No</span></span></p></td>
<td><p><span data-ttu-id="6c8ce-232">使用了音频或视频的会议总数。</span><span class="sxs-lookup"><span data-stu-id="6c8ce-232">Total number of conferences that included audio or video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8ce-233"><strong>A/V 会议总分钟数</strong></span><span class="sxs-lookup"><span data-stu-id="6c8ce-233"><strong>Total A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="6c8ce-234">否</span><span class="sxs-lookup"><span data-stu-id="6c8ce-234">No</span></span></p></td>
<td><p><span data-ttu-id="6c8ce-235">音频/视频会议的总分钟数。</span><span class="sxs-lookup"><span data-stu-id="6c8ce-235">Total number of minutes devoted to audio/video conferencing.</span></span></p>
<p><span data-ttu-id="6c8ce-236">Total A/V 会议纪要指标汇总了所有音频/视频会议类型，包括： A/V 会议;IM 会议;应用程序共享会议;数据会议;和 PSTN 会议。</span><span class="sxs-lookup"><span data-stu-id="6c8ce-236">The Total A/V conference minutes metric summarizes all the audio/visual conference types, including: A/V conferences; IM conferences; app sharing conferences; data conferences; and PSTN conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8ce-237"><strong>A/V 会议参与者总分钟数</strong></span><span class="sxs-lookup"><span data-stu-id="6c8ce-237"><strong>Total A/V conference participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="6c8ce-238">否</span><span class="sxs-lookup"><span data-stu-id="6c8ce-238">No</span></span></p></td>
<td><p><span data-ttu-id="6c8ce-p116">音频/视频会议的参与者总分钟数。例如，假定一个用户在音频/视频会议中花费了 5 分钟时间，另一个用户在同一会议中花费了 3 分钟时间，则参与者总分钟数为 8：5 分钟加上 3 分钟。</span><span class="sxs-lookup"><span data-stu-id="6c8ce-p116">Total number of participant minutes devoted to audio/video conferencing. For example, suppose one user spends 5 minutes in an audio/video conference and a second user spends 3 minutes in that same conference. That makes a total of 8 participant minutes: 5 minutes plus 3 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8ce-242"><strong>A/V 会议平均分钟数</strong></span><span class="sxs-lookup"><span data-stu-id="6c8ce-242"><strong>Average A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="6c8ce-243">否</span><span class="sxs-lookup"><span data-stu-id="6c8ce-243">No</span></span></p></td>
<td><p><span data-ttu-id="6c8ce-244">每个音频/视频会议的平均分钟数。</span><span class="sxs-lookup"><span data-stu-id="6c8ce-244">Average number of minutes per audio/video conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c8ce-245"><strong>唯一会议组织者总数</strong></span><span class="sxs-lookup"><span data-stu-id="6c8ce-245"><strong>Total number of unique organizers of conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="6c8ce-246">否</span><span class="sxs-lookup"><span data-stu-id="6c8ce-246">No</span></span></p></td>
<td><p><span data-ttu-id="6c8ce-p117">至少组织过一次会议的用户总数。与仅组织过一次会议的用户一样，组织过多次会议的用户算作一个唯一组织者。</span><span class="sxs-lookup"><span data-stu-id="6c8ce-p117">Total number of users who organized at least one conference. Users who organized more than one conference are counted as one unique organizer, just like users who only organized a single conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c8ce-249"><strong>会议消息总数</strong></span><span class="sxs-lookup"><span data-stu-id="6c8ce-249"><strong>Total conference messages</strong></span></span></p></td>
<td><p><span data-ttu-id="6c8ce-250">否</span><span class="sxs-lookup"><span data-stu-id="6c8ce-250">No</span></span></p></td>
<td><p><span data-ttu-id="6c8ce-251">会议期间发送的即时消息总数。</span><span class="sxs-lookup"><span data-stu-id="6c8ce-251">Total number of instant messages sent during the conferences.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

