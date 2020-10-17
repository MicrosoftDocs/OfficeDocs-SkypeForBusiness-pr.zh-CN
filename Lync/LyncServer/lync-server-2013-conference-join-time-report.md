---
title: Lync Server 2013：会议加入时间报告
description: Lync Server 2013：会议加入时间报告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Join Time Report
ms:assetid: e64dc89a-25e4-4cb8-bcb1-51712e69ba5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205344(v=OCS.15)
ms:contentKeyID: 48185686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd4aa5d21a8109a323bb953c7196f43715d51413
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542788"
---
# <a name="conference-join-time-report-in-lync-server-2013"></a><span data-ttu-id="e046c-103">Lync Server 2013 中的会议加入时间报告</span><span class="sxs-lookup"><span data-stu-id="e046c-103">Conference Join Time Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e046c-104">_**上次修改的主题：** 2014-04-23_</span><span class="sxs-lookup"><span data-stu-id="e046c-104">_**Topic Last Modified:** 2014-04-23_</span></span>

<span data-ttu-id="e046c-105">会议加入时间摘要使您能够确定用户加入会议所需的时间。</span><span class="sxs-lookup"><span data-stu-id="e046c-105">The Conference Join Time Summary enables you to determine how long it takes your users to join a conference.</span></span> <span data-ttu-id="e046c-106">该报告显示平均联接时间 (以毫秒) 为单位，还提供了一个细分，以便您知道在2秒或更短的时间内可以加入会议的用户数，在2秒到5秒之间需要多少用户加入会议等等。</span><span class="sxs-lookup"><span data-stu-id="e046c-106">The report shows the average join time (in milliseconds), and also provides a breakdown that lets you know how many users were able to join a conference in 2 seconds or less, how many users required between 2 and 5 seconds to join the conference, and so on.</span></span>

<div>

## <a name="accessing-the-conference-join-time-report"></a><span data-ttu-id="e046c-107">访问会议加入时间报告</span><span class="sxs-lookup"><span data-stu-id="e046c-107">Accessing the Conference Join Time Report</span></span>

<span data-ttu-id="e046c-108">可以从 "监控报告" 主页访问会议加入时间报告。</span><span class="sxs-lookup"><span data-stu-id="e046c-108">The Conference Join Time Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="e046c-109">筛选器</span><span class="sxs-lookup"><span data-stu-id="e046c-109">Filters</span></span>

<span data-ttu-id="e046c-110">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。</span><span class="sxs-lookup"><span data-stu-id="e046c-110">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="e046c-111">下表列出了可用于会议加入时间报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="e046c-111">The following table lists the filters that you can use with the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-filters"></a><span data-ttu-id="e046c-112">会议加入时间报告筛选器</span><span class="sxs-lookup"><span data-stu-id="e046c-112">Conference Join Time Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e046c-113">名称</span><span class="sxs-lookup"><span data-stu-id="e046c-113">Name</span></span></th>
<th><span data-ttu-id="e046c-114">说明</span><span class="sxs-lookup"><span data-stu-id="e046c-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e046c-115"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="e046c-115"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="e046c-p103">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e046c-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="e046c-118">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="e046c-118">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e046c-p104">如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="e046c-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e046c-121">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e046c-121">7/7/2012</span></span></p>
<p><span data-ttu-id="e046c-122">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="e046c-122">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e046c-123">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e046c-123">7/3/2012</span></span></p>
<p><span data-ttu-id="e046c-124">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="e046c-124">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e046c-125"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="e046c-125"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="e046c-p105">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e046c-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="e046c-128">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="e046c-128">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e046c-p106">如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="e046c-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e046c-131">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e046c-131">7/7/2012</span></span></p>
<p><span data-ttu-id="e046c-132">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="e046c-132">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e046c-133">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e046c-133">7/3/2012</span></span></p>
<p><span data-ttu-id="e046c-134">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="e046c-134">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e046c-135"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="e046c-135"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="e046c-p107">时间间隔。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="e046c-p107">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e046c-138">每小时（最多可显示 25 个小时）</span><span class="sxs-lookup"><span data-stu-id="e046c-138">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="e046c-139">每天（最多可显示 31 天）</span><span class="sxs-lookup"><span data-stu-id="e046c-139">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="e046c-140">每周（最多可显示 12 周）</span><span class="sxs-lookup"><span data-stu-id="e046c-140">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="e046c-141">每月（最多可显示 12 个月）</span><span class="sxs-lookup"><span data-stu-id="e046c-141">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="e046c-p108">如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。例如，如果选择的开始日期为 8/7/2012、结束日期为 9/28/2012、间隔为“每天”，则显示从 8/7/2012 12:00 AM 到 9/7/2012 12:00 AM 这些天的数据（即总共 31 天的数据）。</span><span class="sxs-lookup"><span data-stu-id="e046c-p108">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e046c-144"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="e046c-144"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="e046c-p109">注册器池或边缘服务器的完全限定域名 (FQDN)。可以选择单个池，也可以单击“[所有]”<strong></strong>查看所有池的数据。系统根据数据库中的记录自动为您填充该下拉列表。</span><span class="sxs-lookup"><span data-stu-id="e046c-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e046c-148"><strong>会议会话</strong></span><span class="sxs-lookup"><span data-stu-id="e046c-148"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="e046c-149">会话类型。</span><span class="sxs-lookup"><span data-stu-id="e046c-149">Type of session.</span></span> <span data-ttu-id="e046c-150">允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="e046c-150">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="e046c-151">各种</span><span class="sxs-lookup"><span data-stu-id="e046c-151">[All]</span></span></p></li>
<li><p><span data-ttu-id="e046c-152">焦点会话 (焦点是联机会议的中心策略和状态管理器，并协调会议的各个方面</span><span class="sxs-lookup"><span data-stu-id="e046c-152">Focus sessions (the Focus is the central policy and state manager for online meetings and coordinates all aspects of A conference</span></span></p></li>
<li><p><span data-ttu-id="e046c-153">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="e046c-153">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="e046c-154">A/V 会议</span><span class="sxs-lookup"><span data-stu-id="e046c-154">A/V conferencing</span></span></p></li>
</ul>
<p><span data-ttu-id="e046c-155">如果选择 "[所有]"，会议总加入时间将显示在报告的顶部。</span><span class="sxs-lookup"><span data-stu-id="e046c-155">If you select [All], the total conference join time will be displayed at the top of the report.</span></span> <span data-ttu-id="e046c-156">请注意，这些总和仅适用于通过使用 Microsoft Exchange 或 Microsoft Outlook 安排的会议。</span><span class="sxs-lookup"><span data-stu-id="e046c-156">Note that these totals are only for conferences which were scheduled by using Microsoft Exchange or Microsoft Outlook.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="e046c-157">指标</span><span class="sxs-lookup"><span data-stu-id="e046c-157">Metrics</span></span>

<span data-ttu-id="e046c-158">下表列出了会议加入时间报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="e046c-158">The following table lists the information provided in the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-metrics"></a><span data-ttu-id="e046c-159">会议加入时间报告指标</span><span class="sxs-lookup"><span data-stu-id="e046c-159">Conference Join Time Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e046c-160">名称</span><span class="sxs-lookup"><span data-stu-id="e046c-160">Name</span></span></th>
<th><span data-ttu-id="e046c-161">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="e046c-161">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e046c-162">说明</span><span class="sxs-lookup"><span data-stu-id="e046c-162">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e046c-163"><strong>Date</strong></span><span class="sxs-lookup"><span data-stu-id="e046c-163"><strong>Date</strong></span></span></p>
<p><span data-ttu-id="e046c-164">此指标的实际标题将根据所选的间隔而有所不同。</span><span class="sxs-lookup"><span data-stu-id="e046c-164">The actual title for this metric will vary depending on the Interval that was selected.</span></span></p></td>
<td><p><span data-ttu-id="e046c-165">否</span><span class="sxs-lookup"><span data-stu-id="e046c-165">No</span></span></p></td>
<td><p><span data-ttu-id="e046c-166">会议发生的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="e046c-166">Date and time that the conference took place.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e046c-167"><strong>会话总数</strong></span><span class="sxs-lookup"><span data-stu-id="e046c-167"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="e046c-168">否</span><span class="sxs-lookup"><span data-stu-id="e046c-168">No</span></span></p></td>
<td><p><span data-ttu-id="e046c-169">会话的总数，包括成功的会话、失败的会话（预期失败和意外失败）及未归类的会话。</span><span class="sxs-lookup"><span data-stu-id="e046c-169">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e046c-170"><strong>平均 (ms) </strong></span><span class="sxs-lookup"><span data-stu-id="e046c-170"><strong>Average (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="e046c-171">否</span><span class="sxs-lookup"><span data-stu-id="e046c-171">No</span></span></p></td>
<td><p><span data-ttu-id="e046c-172">参与者加入会议所需的平均时间量（以毫秒为单位）)  (。</span><span class="sxs-lookup"><span data-stu-id="e046c-172">Average amount of time (in milliseconds) that it took participants to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e046c-173"><strong>会话 &lt; 2 秒，批量</strong></span><span class="sxs-lookup"><span data-stu-id="e046c-173"><strong>Sessions &lt; 2 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="e046c-174">否</span><span class="sxs-lookup"><span data-stu-id="e046c-174">No</span></span></p></td>
<td><p><span data-ttu-id="e046c-175">能够在不到2秒的时间内加入会议的参与者的人数。</span><span class="sxs-lookup"><span data-stu-id="e046c-175">Number of participants who were able to join the conference in less than 2 seconds.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e046c-176"><strong>会话 &lt; 2 秒，百分比</strong></span><span class="sxs-lookup"><span data-stu-id="e046c-176"><strong>Sessions &lt; 2 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="e046c-177">否</span><span class="sxs-lookup"><span data-stu-id="e046c-177">No</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e046c-178"><strong>会话2-5 秒，卷</strong></span><span class="sxs-lookup"><span data-stu-id="e046c-178"><strong>Sessions 2-5 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="e046c-179">否</span><span class="sxs-lookup"><span data-stu-id="e046c-179">No</span></span></p></td>
<td><p><span data-ttu-id="e046c-180">在2秒到5秒之间加入会议的参与者的人数。</span><span class="sxs-lookup"><span data-stu-id="e046c-180">Number of participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e046c-181"><strong>会话2-5 秒，百分比</strong></span><span class="sxs-lookup"><span data-stu-id="e046c-181"><strong>Sessions 2-5 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="e046c-182">否</span><span class="sxs-lookup"><span data-stu-id="e046c-182">No</span></span></p></td>
<td><p><span data-ttu-id="e046c-183">在2秒到5秒之间加入会议的呼叫参与者总数的百分比。</span><span class="sxs-lookup"><span data-stu-id="e046c-183">Percentage of the total call participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e046c-184"><strong>会话5-10 秒，卷</strong></span><span class="sxs-lookup"><span data-stu-id="e046c-184"><strong>Sessions 5-10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="e046c-185">否</span><span class="sxs-lookup"><span data-stu-id="e046c-185">No</span></span></p></td>
<td><p><span data-ttu-id="e046c-186">在5秒和10秒之间加入会议的参与者的人数。</span><span class="sxs-lookup"><span data-stu-id="e046c-186">Number of participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e046c-187"><strong>会话5-10 秒，百分比</strong></span><span class="sxs-lookup"><span data-stu-id="e046c-187"><strong>Sessions 5-10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="e046c-188">否</span><span class="sxs-lookup"><span data-stu-id="e046c-188">No</span></span></p></td>
<td><p><span data-ttu-id="e046c-189">在5秒和10秒之间加入会议的总呼叫参与者的百分比。</span><span class="sxs-lookup"><span data-stu-id="e046c-189">Percentage of the total call participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e046c-190"><strong>会话 &gt; 10 秒，批量</strong></span><span class="sxs-lookup"><span data-stu-id="e046c-190"><strong>Sessions &gt; 10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="e046c-191">否</span><span class="sxs-lookup"><span data-stu-id="e046c-191">No</span></span></p></td>
<td><p><span data-ttu-id="e046c-192">需要10秒以上加入会议的参与者的人数。</span><span class="sxs-lookup"><span data-stu-id="e046c-192">Number of participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e046c-193"><strong>会话 &gt; 10 秒，百分比</strong></span><span class="sxs-lookup"><span data-stu-id="e046c-193"><strong>Sessions &gt; 10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="e046c-194">否</span><span class="sxs-lookup"><span data-stu-id="e046c-194">No</span></span></p></td>
<td><p><span data-ttu-id="e046c-195">需要10秒以上加入会议的总呼叫参与者的百分比。</span><span class="sxs-lookup"><span data-stu-id="e046c-195">Percentage of the total call participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

