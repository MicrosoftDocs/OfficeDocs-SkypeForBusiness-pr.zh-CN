---
title: 'Lync Server 2013: 会议加入时间报表'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Join Time Report
ms:assetid: e64dc89a-25e4-4cb8-bcb1-51712e69ba5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205344(v=OCS.15)
ms:contentKeyID: 48185686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fac854b9e296d744473593562f32430c6e21fc87
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837493"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-join-time-report-in-lync-server-2013"></a><span data-ttu-id="c10bb-102">Lync Server 2013 中的会议加入时间报表</span><span class="sxs-lookup"><span data-stu-id="c10bb-102">Conference Join Time Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c10bb-103">_**主题上次修改时间:** 2014-04-23_</span><span class="sxs-lookup"><span data-stu-id="c10bb-103">_**Topic Last Modified:** 2014-04-23_</span></span>

<span data-ttu-id="c10bb-p101">会议加入时间摘要可使您确定用户要花多长时间才能加入会议。该报告显示平均加入时间（以毫秒计），同时提供一个细目，让您知道有多少用户在 2 秒或更少时间内加入了会议，有多少用户要求在 2 秒和 5 秒间加入会议等。</span><span class="sxs-lookup"><span data-stu-id="c10bb-p101">The Conference Join Time Summary enables you to determine how long it takes your users to join a conference. The report shows the average join time (in milliseconds), and also provides a breakdown that lets you know how many users were able to join a conference in 2 seconds or less, how many users required between 2 and 5 seconds to join the conference, and so on.</span></span>

<div>

## <a name="accessing-the-conference-join-time-report"></a><span data-ttu-id="c10bb-106">访问会议加入时间报告</span><span class="sxs-lookup"><span data-stu-id="c10bb-106">Accessing the Conference Join Time Report</span></span>

<span data-ttu-id="c10bb-107">可从监控报告主页访问会议加入时间报告。</span><span class="sxs-lookup"><span data-stu-id="c10bb-107">The Conference Join Time Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="c10bb-108">筛选器</span><span class="sxs-lookup"><span data-stu-id="c10bb-108">Filters</span></span>

<span data-ttu-id="c10bb-p102">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。下表列出了可用于会议加入时间报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="c10bb-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-filters"></a><span data-ttu-id="c10bb-111">会议加入时间报告筛选器</span><span class="sxs-lookup"><span data-stu-id="c10bb-111">Conference Join Time Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c10bb-112">名称</span><span class="sxs-lookup"><span data-stu-id="c10bb-112">Name</span></span></th>
<th><span data-ttu-id="c10bb-113">说明</span><span class="sxs-lookup"><span data-stu-id="c10bb-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c10bb-114"><strong>从</strong></span><span class="sxs-lookup"><span data-stu-id="c10bb-114"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="c10bb-p103">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c10bb-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="c10bb-117">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="c10bb-117">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c10bb-p104">如果您未输入开始时间，该报告会自动将将某个特定日期的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="c10bb-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c10bb-120">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="c10bb-120">7/7/2012</span></span></p>
<p><span data-ttu-id="c10bb-121">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="c10bb-121">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c10bb-122">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="c10bb-122">7/3/2012</span></span></p>
<p><span data-ttu-id="c10bb-123">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="c10bb-123">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c10bb-124"><strong>到</strong></span><span class="sxs-lookup"><span data-stu-id="c10bb-124"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="c10bb-p105">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c10bb-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="c10bb-127">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="c10bb-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c10bb-p106">如果您未输入结束时间，该报告会自动将某个特定日期的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="c10bb-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c10bb-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="c10bb-130">7/7/2012</span></span></p>
<p><span data-ttu-id="c10bb-131">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="c10bb-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c10bb-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="c10bb-132">7/3/2012</span></span></p>
<p><span data-ttu-id="c10bb-133">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="c10bb-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c10bb-134"><strong>间隔</strong></span><span class="sxs-lookup"><span data-stu-id="c10bb-134"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="c10bb-p107">时间间隔。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="c10bb-p107">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c10bb-137">每小时（最多可显示 25 个小时）</span><span class="sxs-lookup"><span data-stu-id="c10bb-137">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="c10bb-138">每天（最多可显示 31 天）</span><span class="sxs-lookup"><span data-stu-id="c10bb-138">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="c10bb-139">每周（最多可显示 12 周）</span><span class="sxs-lookup"><span data-stu-id="c10bb-139">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="c10bb-140">每月（最多可显示 12 个月）</span><span class="sxs-lookup"><span data-stu-id="c10bb-140">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="c10bb-141">如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。</span><span class="sxs-lookup"><span data-stu-id="c10bb-141">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="c10bb-142">例如, 如果选择 "开始日期 7/7/2012" 和 "结束日期 2/28/2012" 的 "每日间隔", 则会显示 8/7/2012 12:00 AM 到 9/7/2012 12:00 AM 的数据 (即, 总共31天的数据)。</span><span class="sxs-lookup"><span data-stu-id="c10bb-142">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c10bb-143"><strong>池</strong></span><span class="sxs-lookup"><span data-stu-id="c10bb-143"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="c10bb-p109">注册器池或边缘服务器的完全限定域名 (FQDN)。可以选择单个池，也可以单击“<strong>[所有]</strong>”查看所有池的数据。系统根据数据库中的记录自动为您填充该下拉列表。</span><span class="sxs-lookup"><span data-stu-id="c10bb-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c10bb-147"><strong>会议会话</strong></span><span class="sxs-lookup"><span data-stu-id="c10bb-147"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c10bb-p110">会话类型。允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="c10bb-p110">Type of session. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="c10bb-150">[所有]</span><span class="sxs-lookup"><span data-stu-id="c10bb-150">[All]</span></span></p></li>
<li><p><span data-ttu-id="c10bb-151">焦点会话（“焦点”是联机会议的中央策略和状态管理者，负责协调会议的各个方面</span><span class="sxs-lookup"><span data-stu-id="c10bb-151">Focus sessions (the Focus is the central policy and state manager for online meetings and coordinates all aspects of A conference</span></span></p></li>
<li><p><span data-ttu-id="c10bb-152">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="c10bb-152">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="c10bb-153">A/V 会议</span><span class="sxs-lookup"><span data-stu-id="c10bb-153">A/V conferencing</span></span></p></li>
</ul>
<p><span data-ttu-id="c10bb-p111">如果选择 [所有]，则总会议加入时间将显示在报告的顶部。请注意，这些总数仅用于通过使用 Microsoft Exchange 或 Microsoft Outlook 安排的会议。</span><span class="sxs-lookup"><span data-stu-id="c10bb-p111">If you select [All], the total conference join time will be displayed at the top of the report. Note that these totals are only for conferences which were scheduled by using Microsoft Exchange or Microsoft Outlook.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="c10bb-156">指标</span><span class="sxs-lookup"><span data-stu-id="c10bb-156">Metrics</span></span>

<span data-ttu-id="c10bb-157">下表列出了会议加入时间报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="c10bb-157">The following table lists the information provided in the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-metrics"></a><span data-ttu-id="c10bb-158">会议加入时间报告标准</span><span class="sxs-lookup"><span data-stu-id="c10bb-158">Conference Join Time Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c10bb-159">名称</span><span class="sxs-lookup"><span data-stu-id="c10bb-159">Name</span></span></th>
<th><span data-ttu-id="c10bb-160">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="c10bb-160">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c10bb-161">描述</span><span class="sxs-lookup"><span data-stu-id="c10bb-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c10bb-162"><strong>日期</strong></span><span class="sxs-lookup"><span data-stu-id="c10bb-162"><strong>Date</strong></span></span></p>
<p><span data-ttu-id="c10bb-163">此指标的实际标题完全取决于所选的间隔。</span><span class="sxs-lookup"><span data-stu-id="c10bb-163">The actual title for this metric will vary depending on the Interval that was selected.</span></span></p></td>
<td><p><span data-ttu-id="c10bb-164">否</span><span class="sxs-lookup"><span data-stu-id="c10bb-164">No</span></span></p></td>
<td><p><span data-ttu-id="c10bb-165">会议发生的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="c10bb-165">Date and time that the conference took place.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c10bb-166"><strong>会话总数</strong></span><span class="sxs-lookup"><span data-stu-id="c10bb-166"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c10bb-167">否</span><span class="sxs-lookup"><span data-stu-id="c10bb-167">No</span></span></p></td>
<td><p><span data-ttu-id="c10bb-168">会话的总数，包括成功的会话、失败的会话（预期失败和意外失败）及未归类的会话。</span><span class="sxs-lookup"><span data-stu-id="c10bb-168">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c10bb-169"><strong>平均 (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="c10bb-169"><strong>Average (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="c10bb-170">否</span><span class="sxs-lookup"><span data-stu-id="c10bb-170">No</span></span></p></td>
<td><p><span data-ttu-id="c10bb-171">参与者加入会议花费的平均时间量（以毫秒计）。</span><span class="sxs-lookup"><span data-stu-id="c10bb-171">Average amount of time (in milliseconds) that it took participants to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c10bb-172"><strong>会话&lt; 2 秒, 卷</strong></span><span class="sxs-lookup"><span data-stu-id="c10bb-172"><strong>Sessions &lt; 2 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="c10bb-173">否</span><span class="sxs-lookup"><span data-stu-id="c10bb-173">No</span></span></p></td>
<td><p><span data-ttu-id="c10bb-174">在不到 2 秒的时间内加入会议的参与者的人数。</span><span class="sxs-lookup"><span data-stu-id="c10bb-174">Number of participants who were able to join the conference in less than 2 seconds.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c10bb-175"><strong>会话&lt; 2 秒, 百分比</strong></span><span class="sxs-lookup"><span data-stu-id="c10bb-175"><strong>Sessions &lt; 2 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="c10bb-176">否</span><span class="sxs-lookup"><span data-stu-id="c10bb-176">No</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c10bb-177"><strong>会话 2-5 秒，量</strong></span><span class="sxs-lookup"><span data-stu-id="c10bb-177"><strong>Sessions 2-5 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="c10bb-178">否</span><span class="sxs-lookup"><span data-stu-id="c10bb-178">No</span></span></p></td>
<td><p><span data-ttu-id="c10bb-179">在 2 秒到 5 秒之间加入到会议参与者的人数。</span><span class="sxs-lookup"><span data-stu-id="c10bb-179">Number of participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c10bb-180"><strong>会话 2-5 秒，百分比</strong></span><span class="sxs-lookup"><span data-stu-id="c10bb-180"><strong>Sessions 2-5 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="c10bb-181">否</span><span class="sxs-lookup"><span data-stu-id="c10bb-181">No</span></span></p></td>
<td><p><span data-ttu-id="c10bb-182">在 2 秒到 5 秒间加入会议的总呼叫参与者的百分比。</span><span class="sxs-lookup"><span data-stu-id="c10bb-182">Percentage of the total call participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c10bb-183"><strong>会话 5-10 秒，量</strong></span><span class="sxs-lookup"><span data-stu-id="c10bb-183"><strong>Sessions 5-10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="c10bb-184">否</span><span class="sxs-lookup"><span data-stu-id="c10bb-184">No</span></span></p></td>
<td><p><span data-ttu-id="c10bb-185">在 5 秒到 10 秒之间加入到会议参与者的人数。</span><span class="sxs-lookup"><span data-stu-id="c10bb-185">Number of participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c10bb-186"><strong>会话 5-10 秒，百分比</strong></span><span class="sxs-lookup"><span data-stu-id="c10bb-186"><strong>Sessions 5-10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="c10bb-187">否</span><span class="sxs-lookup"><span data-stu-id="c10bb-187">No</span></span></p></td>
<td><p><span data-ttu-id="c10bb-188">在 5 秒到 10 秒间加入会议的总呼叫参与者的百分比。</span><span class="sxs-lookup"><span data-stu-id="c10bb-188">Percentage of the total call participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c10bb-189"><strong>会话&gt; 10 秒, 卷</strong></span><span class="sxs-lookup"><span data-stu-id="c10bb-189"><strong>Sessions &gt; 10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="c10bb-190">否</span><span class="sxs-lookup"><span data-stu-id="c10bb-190">No</span></span></p></td>
<td><p><span data-ttu-id="c10bb-191">需要 10 秒之上加入会议的参与者人数。</span><span class="sxs-lookup"><span data-stu-id="c10bb-191">Number of participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c10bb-192"><strong>会话&gt; 10 秒, 百分比</strong></span><span class="sxs-lookup"><span data-stu-id="c10bb-192"><strong>Sessions &gt; 10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="c10bb-193">否</span><span class="sxs-lookup"><span data-stu-id="c10bb-193">No</span></span></p></td>
<td><p><span data-ttu-id="c10bb-194">需要 10 秒之上加入会议的总呼叫参与者百分比。</span><span class="sxs-lookup"><span data-stu-id="c10bb-194">Percentage of the total call participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

