---
title: Lync Server 2013：热门故障报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Top Failures Report
ms:assetid: 438942e2-580a-4b67-9d42-f116111fb26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558640(v=OCS.15)
ms:contentKeyID: 48184021
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 972c9e97015f5a39ace3cf1fc68051cc0afcc988
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193635"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="top-failures-report-in-lync-server-2013"></a><span data-ttu-id="cbbeb-102">Lync Server 2013 中的热门故障报告</span><span class="sxs-lookup"><span data-stu-id="cbbeb-102">Top Failures Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbbeb-103">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="cbbeb-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="cbbeb-p101">主要故障报告说明了最常报告的故障及其在一段时间内的趋势。故障基于以下两项指标的组合：</span><span class="sxs-lookup"><span data-stu-id="cbbeb-p101">The Top Failures Report provides a look at the most-commonly reported failures and their trends over time. Failures are based on a combination of the following two metrics:</span></span>

  - <span data-ttu-id="cbbeb-p102">**诊断 ID**。附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式）。诊断 ID 提供的信息在解决与呼叫相关的问题时很有用。</span><span class="sxs-lookup"><span data-stu-id="cbbeb-p102">**Diagnostic ID**. Unique identifier (in the form of an ms-diagnostics header) that is attached to a SIP message. Diagnostic IDs provide information useful in troubleshooting call-related problems.</span></span>

  - <span data-ttu-id="cbbeb-109">**响应代码**。</span><span class="sxs-lookup"><span data-stu-id="cbbeb-109">**Response code**.</span></span> <span data-ttu-id="cbbeb-110">响应代码在 SIP 通信会话中用来响应 SIP 请求。</span><span class="sxs-lookup"><span data-stu-id="cbbeb-110">Response codes are used in SIP communication sessions to respond to SIP requests.</span></span> <span data-ttu-id="cbbeb-111">例如，假定 Ken 将 INVITE 请求发送给 Pilar Ackerman（即，假定 Ken Myer 呼叫 Pilar Ackerman）。</span><span class="sxs-lookup"><span data-stu-id="cbbeb-111">For example, suppose Ken sends the INVITE request to Pilar Ackerman (that is, suppose Ken Myer calls Pilar Ackerman).</span></span> <span data-ttu-id="cbbeb-112">如果 Pilar 应答，则她的电话将发送响应代码 200（确定），以便让 Ken 的电话获知 Pilar 已应答。</span><span class="sxs-lookup"><span data-stu-id="cbbeb-112">If Pilar answers, her phone will send the response code 200 (OK), letting Ken's phone know that Pilar has answered.</span></span> <span data-ttu-id="cbbeb-113">顶级故障报告仅包括在响应呼叫失败时发送的响应代码。Lync Server 不会跟踪在呼叫过程中发出的所有响应代码。</span><span class="sxs-lookup"><span data-stu-id="cbbeb-113">The Top Failures Report only includes response codes that were sent in response to a call failure; Lync Server does not keep track of all the response codes issued during the course of a call.</span></span>

<span data-ttu-id="cbbeb-114">不仅将报告与出现故障的会话的总数相关的信息，而且还将报告与受故障影响的用户总数相关的信息。</span><span class="sxs-lookup"><span data-stu-id="cbbeb-114">Information is reported not only for the total number of sessions where a failure occurred but also for the total number of users who were impacted by the failure.</span></span>

<div>

## <a name="accessing-the-top-failures-report"></a><span data-ttu-id="cbbeb-115">访问主要故障报告</span><span class="sxs-lookup"><span data-stu-id="cbbeb-115">Accessing the Top Failures Report</span></span>

<span data-ttu-id="cbbeb-116">可从监控报告主页访问主要故障报告。</span><span class="sxs-lookup"><span data-stu-id="cbbeb-116">The Top Failures Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="cbbeb-117">单击报告的会话指标将转到[Lync Server 2013 中的故障分布报告](lync-server-2013-failure-distribution-report.md)。</span><span class="sxs-lookup"><span data-stu-id="cbbeb-117">Clicking the Reported sessions metric will take you to the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-top-failures-report"></a><span data-ttu-id="cbbeb-118">最充分地利用主要故障报告</span><span class="sxs-lookup"><span data-stu-id="cbbeb-118">Making the Best Use of the Top Failures Report</span></span>

<span data-ttu-id="cbbeb-p105">主要故障报告有一个与众不同的方面：它允许您一次性对最多 5 个诊断 ID 进行筛选。（通常，您一次只能筛选一项 - 例如，一个用户 SIP 地址。）若要对多个诊断 ID 进行筛选，只需在诊断 ID 框中输入每个 ID，并使用逗号分隔这些 ID。（如果需要，您可以在每个逗号后面保留一个空格。）例如：</span><span class="sxs-lookup"><span data-stu-id="cbbeb-p105">The Top Failures Report is unusual in one regard: it allows you to filter on as many as 5 diagnostic IDs at once. (Typically you can only filter on one item – such as one user SIP address – at a time.) To filter on multiple diagnostic IDs, simply enter each ID in the Diagnostic IDs box, separating the IDs by using commas. (If you want to, you can leave a blank space after each comma.) For example:</span></span>

<span data-ttu-id="cbbeb-122">1011, 2412, 1033, 52116, 1008</span><span class="sxs-lookup"><span data-stu-id="cbbeb-122">1011, 2412, 1033, 52116, 1008</span></span>

<span data-ttu-id="cbbeb-123">这样一来，将仅显示报告了这五个诊断 ID 中的至少一个 ID 的失败呼叫。</span><span class="sxs-lookup"><span data-stu-id="cbbeb-123">Do that, and only failed calls that reported at least one of those five diagnostic IDs will be displayed.</span></span>

<span data-ttu-id="cbbeb-p106">如果您将鼠标指针悬停在响应代码的上方，则将显示一个工具提示，告知您有问题的响应代码的含义。例如，如果您将鼠标指针悬停在响应代码 486 的上方，则将显示以下消息：</span><span class="sxs-lookup"><span data-stu-id="cbbeb-p106">If you hold your mouse over a Response code you'll see a tooltip that tells you what the Response code in question means. For example, if you hold the mouse over the Response code 486 you'll see this message:</span></span>

<span data-ttu-id="cbbeb-126">此处忙碌。</span><span class="sxs-lookup"><span data-stu-id="cbbeb-126">Busy Here.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="cbbeb-127">筛选器</span><span class="sxs-lookup"><span data-stu-id="cbbeb-127">Filters</span></span>

<span data-ttu-id="cbbeb-p107">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，主要故障报告允许您基于活动类型（点对点会话还是会议会话）或失败会话附带的 SIP 响应代码等条件筛选返回的数据。您还可以选择数据的分组方式。在此示例中，将按小时、日、周或月对使用情况进行分组。</span><span class="sxs-lookup"><span data-stu-id="cbbeb-p107">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Top Failures Report enables you to filter the returned data based on such things as the activity type (peer-to-peer session or conferencing session) or by the SIP response code that accompanied the failed session. You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="cbbeb-132">下表列出了可用于主要故障报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="cbbeb-132">The following table lists the filters that you can use with the Top Failures Report.</span></span>

### <a name="top-failures-report-filters"></a><span data-ttu-id="cbbeb-133">主要故障报告筛选器</span><span class="sxs-lookup"><span data-stu-id="cbbeb-133">Top Failures Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cbbeb-134">名称</span><span class="sxs-lookup"><span data-stu-id="cbbeb-134">Name</span></span></th>
<th><span data-ttu-id="cbbeb-135">说明</span><span class="sxs-lookup"><span data-stu-id="cbbeb-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cbbeb-136"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="cbbeb-136"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="cbbeb-p108">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cbbeb-p108">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="cbbeb-139">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="cbbeb-139">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="cbbeb-p109">如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="cbbeb-p109">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="cbbeb-142">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="cbbeb-142">7/7/2012</span></span></p>
<p><span data-ttu-id="cbbeb-143">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="cbbeb-143">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="cbbeb-144">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="cbbeb-144">7/3/2012</span></span></p>
<p><span data-ttu-id="cbbeb-145">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="cbbeb-145">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbbeb-146"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="cbbeb-146"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="cbbeb-p110">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cbbeb-p110">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="cbbeb-149">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="cbbeb-149">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="cbbeb-p111">如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="cbbeb-p111">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="cbbeb-152">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="cbbeb-152">7/7/2012</span></span></p>
<p><span data-ttu-id="cbbeb-153">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="cbbeb-153">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="cbbeb-154">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="cbbeb-154">7/3/2012</span></span></p>
<p><span data-ttu-id="cbbeb-155">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="cbbeb-155">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbbeb-156"><strong>活动类型</strong></span><span class="sxs-lookup"><span data-stu-id="cbbeb-156"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="cbbeb-p112">活动的类型。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="cbbeb-p112">Type of activity. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="cbbeb-159">各种</span><span class="sxs-lookup"><span data-stu-id="cbbeb-159">[All]</span></span></p></li>
<li><p><span data-ttu-id="cbbeb-160">对等</span><span class="sxs-lookup"><span data-stu-id="cbbeb-160">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="cbbeb-161">发布会</span><span class="sxs-lookup"><span data-stu-id="cbbeb-161">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbbeb-162"><strong>模态</strong></span><span class="sxs-lookup"><span data-stu-id="cbbeb-162"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="cbbeb-163">在这里，只能选择“[所有]”<strong></strong>选项。</span><span class="sxs-lookup"><span data-stu-id="cbbeb-163">At this time the only option available is <strong>[All]</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbbeb-164"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="cbbeb-164"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="cbbeb-p113">注册器池或边缘服务器的完全限定域名 (FQDN)。可以选择单个池，也可以单击“[所有]”<strong></strong>查看所有池的数据。系统根据数据库中的记录自动为您填充该下拉列表。</span><span class="sxs-lookup"><span data-stu-id="cbbeb-p113">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbbeb-168"><strong>类别</strong></span><span class="sxs-lookup"><span data-stu-id="cbbeb-168"><strong>Category</strong></span></span></p></td>
<td><p><span data-ttu-id="cbbeb-p114">遇到的故障的类型。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="cbbeb-p114">Type of failure experienced. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="cbbeb-171">预期失败和意外失败</span><span class="sxs-lookup"><span data-stu-id="cbbeb-171">Both expected and unexpected failure</span></span></p></li>
<li><p><span data-ttu-id="cbbeb-172">意外失败</span><span class="sxs-lookup"><span data-stu-id="cbbeb-172">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="cbbeb-173">&quot;预期故障&quot;是预期发生的故障。</span><span class="sxs-lookup"><span data-stu-id="cbbeb-173">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="cbbeb-174">例如，如果用户将其状态设置为“请勿打扰”，那么向该用户发出的任何呼叫应该都会失败。</span><span class="sxs-lookup"><span data-stu-id="cbbeb-174">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="cbbeb-175">&quot;意外故障&quot;是指看起来好像是以其他正常运行的系统出现的故障。</span><span class="sxs-lookup"><span data-stu-id="cbbeb-175">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="cbbeb-176">例如，如果呼叫者处于呼叫等待状态，则不应该终止呼叫。</span><span class="sxs-lookup"><span data-stu-id="cbbeb-176">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="cbbeb-177">如果终止，则会被标记为意外失败。</span><span class="sxs-lookup"><span data-stu-id="cbbeb-177">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbbeb-178"><strong>响应代码</strong></span><span class="sxs-lookup"><span data-stu-id="cbbeb-178"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="cbbeb-p116">会议失败时发送的 SIP 响应代码。请输入完整的响应代码。例如：</span><span class="sxs-lookup"><span data-stu-id="cbbeb-p116">SIP response code sent when the conference failed. Enter the entire response code For example:</span></span></p>
<p><span data-ttu-id="cbbeb-181">400</span><span class="sxs-lookup"><span data-stu-id="cbbeb-181">400</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbbeb-182"><strong>诊断 ID</strong></span><span class="sxs-lookup"><span data-stu-id="cbbeb-182"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="cbbeb-p117">附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。诊断标头是可选的（SIP 会话可以不包含这些标头），并且只对遇到此类问题的会话报告诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="cbbeb-p117">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="cbbeb-185">指标</span><span class="sxs-lookup"><span data-stu-id="cbbeb-185">Metrics</span></span>

<span data-ttu-id="cbbeb-186">下表列出了主要故障报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="cbbeb-186">The following table lists the information provided in the Top Failures Report.</span></span>

### <a name="top-failures-report-metrics"></a><span data-ttu-id="cbbeb-187">主要故障报告指标</span><span class="sxs-lookup"><span data-stu-id="cbbeb-187">Top Failures Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cbbeb-188">名称</span><span class="sxs-lookup"><span data-stu-id="cbbeb-188">Name</span></span></th>
<th><span data-ttu-id="cbbeb-189">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="cbbeb-189">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="cbbeb-190">说明</span><span class="sxs-lookup"><span data-stu-id="cbbeb-190">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cbbeb-191"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="cbbeb-191"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="cbbeb-192">是</span><span class="sxs-lookup"><span data-stu-id="cbbeb-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="cbbeb-193">基于报告的会话数确定的相对等级。</span><span class="sxs-lookup"><span data-stu-id="cbbeb-193">Relative rank based on the number of reported sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbbeb-194"><strong>报告的会话</strong></span><span class="sxs-lookup"><span data-stu-id="cbbeb-194"><strong>Reported sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="cbbeb-195">是</span><span class="sxs-lookup"><span data-stu-id="cbbeb-195">Yes</span></span></p></td>
<td><p><span data-ttu-id="cbbeb-196">基于诊断 ID 和 SIP 响应代码确定的失败会话总数。</span><span class="sxs-lookup"><span data-stu-id="cbbeb-196">Total number of failed sessions based on diagnostic ID and SIP response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbbeb-197"><strong>影响的用户</strong></span><span class="sxs-lookup"><span data-stu-id="cbbeb-197"><strong>Users impacted</strong></span></span></p></td>
<td><p><span data-ttu-id="cbbeb-198">是</span><span class="sxs-lookup"><span data-stu-id="cbbeb-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="cbbeb-199">失败会话影响的用户总数。</span><span class="sxs-lookup"><span data-stu-id="cbbeb-199">Total number of users affected by the failed session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbbeb-200"><strong>故障信息</strong></span><span class="sxs-lookup"><span data-stu-id="cbbeb-200"><strong>Failure information</strong></span></span></p></td>
<td><p><span data-ttu-id="cbbeb-201">否</span><span class="sxs-lookup"><span data-stu-id="cbbeb-201">No</span></span></p></td>
<td><p><span data-ttu-id="cbbeb-202">有关故障的详细信息，包括诊断 ID、SIP 响应代码和有关会话失败原因的说明。</span><span class="sxs-lookup"><span data-stu-id="cbbeb-202">Detailed information about the failure, including diagnostic ID, SIP response code, and description of why the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbbeb-203"><strong>过去的趋势</strong></span><span class="sxs-lookup"><span data-stu-id="cbbeb-203"><strong>Trend in the past</strong></span></span></p></td>
<td><p><span data-ttu-id="cbbeb-204">否</span><span class="sxs-lookup"><span data-stu-id="cbbeb-204">No</span></span></p></td>
<td><p><span data-ttu-id="cbbeb-205">以图形的形式显示失败会话在一段时间内的趋势。</span><span class="sxs-lookup"><span data-stu-id="cbbeb-205">Graphs failed sessions over time.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

