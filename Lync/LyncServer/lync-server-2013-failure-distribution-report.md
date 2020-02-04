---
title: Lync Server 2013：失败分发报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failure Distribution Report
ms:assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558635(v=OCS.15)
ms:contentKeyID: 48183849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5250b03aef3fb77de2cbeefa4688a150c9b4a302
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765170"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failure-distribution-report-in-lync-server-2013"></a><span data-ttu-id="0326b-102">Lync Server 2013 中的失败分配报告</span><span class="sxs-lookup"><span data-stu-id="0326b-102">Failure Distribution Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0326b-103">_**主题上次修改时间：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="0326b-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="0326b-104">故障分布报告按以下类别对失败会话进行分级：</span><span class="sxs-lookup"><span data-stu-id="0326b-104">The Failure Distribution Report ranks failed sessions in the following categories:</span></span>

  - <span data-ttu-id="0326b-105">主要诊断原因</span><span class="sxs-lookup"><span data-stu-id="0326b-105">Top diagnostic reasons</span></span>

  - <span data-ttu-id="0326b-106">主要形式</span><span class="sxs-lookup"><span data-stu-id="0326b-106">Top modalities</span></span>

  - <span data-ttu-id="0326b-107">主要池</span><span class="sxs-lookup"><span data-stu-id="0326b-107">Top pools</span></span>

  - <span data-ttu-id="0326b-108">主要来源</span><span class="sxs-lookup"><span data-stu-id="0326b-108">Top sources</span></span>

  - <span data-ttu-id="0326b-109">主要组件</span><span class="sxs-lookup"><span data-stu-id="0326b-109">Top components</span></span>

  - <span data-ttu-id="0326b-110">主要来源用户</span><span class="sxs-lookup"><span data-stu-id="0326b-110">Top from users</span></span>

  - <span data-ttu-id="0326b-111">主要目标用户</span><span class="sxs-lookup"><span data-stu-id="0326b-111">Top to users</span></span>

  - <span data-ttu-id="0326b-112">主要来源用户代理</span><span class="sxs-lookup"><span data-stu-id="0326b-112">Top from user agents</span></span>

<span data-ttu-id="0326b-p101">可以使用这些类别准确确定出现问题的位置，在某些情况下还可准确确定出现问题的原因。例如，假设您在指定的一天内记录了 242 个失败的音频/视频会话。如果您查看故障分布报告，它可能会指示这些失败会话中有 237 个发生在您的 Dublin 池中。在跟踪和诊断出现这些故障的原因时，这为您提供了一个良好的开端。如果单击“**主要池**”类别下的 Dublin 池，即可看到该池的故障分布报告。然后您可以开始分析 Dublin 池为何出现如此多的问题。</span><span class="sxs-lookup"><span data-stu-id="0326b-p101">You can use these categories to determine exactly where a problem is occurring and, in some cases, why the problem is occurring. For example, suppose you recorded 242 failed audio/video sessions during a given day. If you look at the Failure Distribution Report, it might show that 237 of those failed sessions took place in your Dublin pool. That gives you a good place to start when it comes to tracking down and diagnosing the causes behind those failures. If you click on the Dublin pool under the **Top pools** category, you will see a Failure Distribution Report just for that pool. You can then begin analyzing why the Dublin pool was experiencing so many difficulties.</span></span>

<div>

## <a name="viewing-the-failure-distribution-report"></a><span data-ttu-id="0326b-119">查看故障分布报告</span><span class="sxs-lookup"><span data-stu-id="0326b-119">Viewing the Failure Distribution Report</span></span>

<span data-ttu-id="0326b-120">您可以通过单击“**预期失败量**”或“**意外失败量**”指标，从以下任意报告中访问故障分布报告：</span><span class="sxs-lookup"><span data-stu-id="0326b-120">You can access the Failure Distribution Report from any of the following reports by clicking either the **Expected failure volume** or the **Unexpected failure volume** metric:</span></span>

  - [<span data-ttu-id="0326b-121">Lync Server 2013 中的 "热门故障" 报表</span><span class="sxs-lookup"><span data-stu-id="0326b-121">Top Failures Report in Lync Server 2013</span></span>](lync-server-2013-top-failures-report.md)

  - [<span data-ttu-id="0326b-122">Lync Server 2013 中的会议诊断报告</span><span class="sxs-lookup"><span data-stu-id="0326b-122">Conference Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-conference-diagnostic-report.md)

  - [<span data-ttu-id="0326b-123">Lync Server 2013 中的对等活动诊断报告</span><span class="sxs-lookup"><span data-stu-id="0326b-123">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)

<span data-ttu-id="0326b-124">在 "失败分发" 报表中，可以单击以下任一指标，以[在 Lync Server 2013 中查看 "失败列表" 报表](lync-server-2013-failure-list-report.md)：</span><span class="sxs-lookup"><span data-stu-id="0326b-124">From the Failure Distribution Report, you can click any of the following metrics to view the [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md):</span></span>

  - <span data-ttu-id="0326b-125">主要诊断原因（会话）</span><span class="sxs-lookup"><span data-stu-id="0326b-125">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="0326b-126">主要形式（会话）</span><span class="sxs-lookup"><span data-stu-id="0326b-126">Top modalities (sessions)</span></span>

  - <span data-ttu-id="0326b-127">主要池（会话）</span><span class="sxs-lookup"><span data-stu-id="0326b-127">Top pools (sessions)</span></span>

  - <span data-ttu-id="0326b-128">主要来源（会话）</span><span class="sxs-lookup"><span data-stu-id="0326b-128">Top sources (sessions)</span></span>

  - <span data-ttu-id="0326b-129">主要组件（会话）</span><span class="sxs-lookup"><span data-stu-id="0326b-129">Top components (sessions)</span></span>

  - <span data-ttu-id="0326b-130">主要来源用户（会话）</span><span class="sxs-lookup"><span data-stu-id="0326b-130">Top from users (sessions)</span></span>

  - <span data-ttu-id="0326b-131">主要目标用户（会话）</span><span class="sxs-lookup"><span data-stu-id="0326b-131">Top to users (sessions)</span></span>

  - <span data-ttu-id="0326b-132">主要来源用户代理（会话）</span><span class="sxs-lookup"><span data-stu-id="0326b-132">Top from user agents (sessions)</span></span>

</div>

<div>

## <a name="using-the-failure-distribution-report"></a><span data-ttu-id="0326b-133">使用故障分布报告</span><span class="sxs-lookup"><span data-stu-id="0326b-133">Using the Failure Distribution Report</span></span>

<span data-ttu-id="0326b-p102">根据您的监视器尺寸和屏幕分辨率，当您在屏幕上查看故障分布报告中显示的某些数据时，这些数据可能会被截断。用户代理（可能具有很长的标签）等指标尤其可能出现这种情况。例如，具有类似“UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)”的名称的用户代理可能只会部分显示在屏幕上：</span><span class="sxs-lookup"><span data-stu-id="0326b-p102">Depending on your monitor size and screen resolution, it's possible that some of the data shown in the Failure Distribution Report might be truncated when you view it onscreen. This is especially true for metrics such as user agents, which can have very long labels. For example, a user agent with a name like "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" might only partially appear onscreen:</span></span>

<span data-ttu-id="0326b-137">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span><span class="sxs-lookup"><span data-stu-id="0326b-137">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span></span>

<span data-ttu-id="0326b-138">幸运的是，只需将鼠标指针停留在截断值上方即可查看整个标签。</span><span class="sxs-lookup"><span data-stu-id="0326b-138">Fortunately, you can see the entire label simply by holding your mouse over the truncated value.</span></span>

<span data-ttu-id="0326b-p103">可以使用故障分布报告按其进行筛选的一个有用指标是诊断 ID。如果您看到其他报告中出现相同的诊断 ID，则可以在故障分布报告中按此 ID 进行筛选，并获得有关失败会话期间报告此 ID 的准确位置及频率的十分详细的信息。</span><span class="sxs-lookup"><span data-stu-id="0326b-p103">One interesting metric that you can filter on by using the Failure Distribution Report is Diagnostic ID. If you see the same Diagnostic ID cropping up in other reports you can filter on that ID in the Failure Distribution Report and get a very detailed look at exactly where, and how often, that ID has been reported during a failed session.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="0326b-141">筛选器</span><span class="sxs-lookup"><span data-stu-id="0326b-141">Filters</span></span>

<span data-ttu-id="0326b-p104">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，故障分布报告允许您依据活动类型（对等会话还是会议会话）或每个失败会话附带的诊断 ID 等条件进行筛选。</span><span class="sxs-lookup"><span data-stu-id="0326b-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Failed Distribution Report enables you to filter on such things as the activity type (peer-to-peer session or conferencing session) or by the diagnostic ID that accompanied each failed session.</span></span>

<span data-ttu-id="0326b-144">下表列出了可用于故障分布报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="0326b-144">The following table lists the filters that you can use with the Failure Distribution Report.</span></span>

### <a name="failure-distribution-report-filters"></a><span data-ttu-id="0326b-145">故障分布报告筛选器</span><span class="sxs-lookup"><span data-stu-id="0326b-145">Failure Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0326b-146">名称</span><span class="sxs-lookup"><span data-stu-id="0326b-146">Name</span></span></th>
<th><span data-ttu-id="0326b-147">说明</span><span class="sxs-lookup"><span data-stu-id="0326b-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0326b-148"><strong>从</strong></span><span class="sxs-lookup"><span data-stu-id="0326b-148"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="0326b-p105">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0326b-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="0326b-151">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="0326b-151">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="0326b-p106">如果您未输入开始时间，该报告会自动将将某个特定日期的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="0326b-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0326b-154">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="0326b-154">7/7/2012</span></span></p>
<p><span data-ttu-id="0326b-155">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="0326b-155">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0326b-156">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="0326b-156">7/3/2012</span></span></p>
<p><span data-ttu-id="0326b-157">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="0326b-157">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0326b-158"><strong>到</strong></span><span class="sxs-lookup"><span data-stu-id="0326b-158"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="0326b-p107">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0326b-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="0326b-161">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="0326b-161">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="0326b-p108">如果您未输入结束时间，该报告会自动将某个特定日期的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="0326b-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0326b-164">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="0326b-164">7/7/2012</span></span></p>
<p><span data-ttu-id="0326b-165">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="0326b-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0326b-166">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="0326b-166">7/3/2012</span></span></p>
<p><span data-ttu-id="0326b-167">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="0326b-167">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0326b-168"><strong>池</strong></span><span class="sxs-lookup"><span data-stu-id="0326b-168"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="0326b-p109">注册器池或边缘服务器的完全限定域名 (FQDN)。可以选择单个池，也可以单击“<strong>[所有]</strong>”查看所有池的数据。系统根据数据库中的记录自动为您填充该下拉列表。</span><span class="sxs-lookup"><span data-stu-id="0326b-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0326b-172"><strong>活动类型</strong></span><span class="sxs-lookup"><span data-stu-id="0326b-172"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="0326b-p110">要筛选的活动类型。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="0326b-p110">Type of activity to filter on. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0326b-175">[所有]</span><span class="sxs-lookup"><span data-stu-id="0326b-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="0326b-176">对等</span><span class="sxs-lookup"><span data-stu-id="0326b-176">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="0326b-177">会议</span><span class="sxs-lookup"><span data-stu-id="0326b-177">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0326b-178"><strong>会话类别</strong></span><span class="sxs-lookup"><span data-stu-id="0326b-178"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="0326b-p111">指示相应活动已成功还是失败。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="0326b-p111">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0326b-181">[所有]</span><span class="sxs-lookup"><span data-stu-id="0326b-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="0326b-182">成功</span><span class="sxs-lookup"><span data-stu-id="0326b-182">Success</span></span></p></li>
<li><p><span data-ttu-id="0326b-183">预期失败</span><span class="sxs-lookup"><span data-stu-id="0326b-183">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="0326b-184">意外失败</span><span class="sxs-lookup"><span data-stu-id="0326b-184">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="0326b-185">&quot;预期的故障&quot;是预期发生的故障。</span><span class="sxs-lookup"><span data-stu-id="0326b-185">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="0326b-186">例如，如果用户将其状态设置为“请勿打扰”，那么向该用户发出的任何呼叫应该都会失败。</span><span class="sxs-lookup"><span data-stu-id="0326b-186">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="0326b-187">&quot;意外故障&quot;是指出现在其他正常运行的系统中的故障。</span><span class="sxs-lookup"><span data-stu-id="0326b-187">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="0326b-188">例如，如果呼叫者处于呼叫等待状态，则不应该终止呼叫。</span><span class="sxs-lookup"><span data-stu-id="0326b-188">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="0326b-189">如果终止，则会被标记为意外失败。</span><span class="sxs-lookup"><span data-stu-id="0326b-189">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0326b-190"><strong>诊断 ID</strong></span><span class="sxs-lookup"><span data-stu-id="0326b-190"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="0326b-p113">附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。诊断标头是可选的（SIP 会话可以不包含这些标头），并且只对遇到此类问题的会话报告诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="0326b-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="0326b-193">主要诊断原因的指标</span><span class="sxs-lookup"><span data-stu-id="0326b-193">Metrics for Top Diagnostic Reasons</span></span>

<span data-ttu-id="0326b-194">下表列出了故障分布报告中基于最常见的诊断 ID 提供的信息。</span><span class="sxs-lookup"><span data-stu-id="0326b-194">The following table lists the information provided in the Failure Distribution Report based on the most frequently reported diagnostic ID.</span></span>

### <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="0326b-195">主要诊断原因的指标</span><span class="sxs-lookup"><span data-stu-id="0326b-195">Metrics for Top Diagnostic Reasons</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0326b-196">名称</span><span class="sxs-lookup"><span data-stu-id="0326b-196">Name</span></span></th>
<th><span data-ttu-id="0326b-197">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="0326b-197">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0326b-198">描述</span><span class="sxs-lookup"><span data-stu-id="0326b-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0326b-199"><strong>等级</strong></span><span class="sxs-lookup"><span data-stu-id="0326b-199"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="0326b-200">否</span><span class="sxs-lookup"><span data-stu-id="0326b-200">No</span></span></p></td>
<td><p><span data-ttu-id="0326b-p114">失败会话的相对等级，根据诊断 ID 确定。诊断 ID 是附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。</span><span class="sxs-lookup"><span data-stu-id="0326b-p114">Relative ranking of failed sessions based on diagnostic IDs. The diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0326b-203"><strong>主要诊断原因</strong></span><span class="sxs-lookup"><span data-stu-id="0326b-203"><strong>Top diagnostic reasons</strong></span></span></p></td>
<td><p><span data-ttu-id="0326b-204">否</span><span class="sxs-lookup"><span data-stu-id="0326b-204">No</span></span></p></td>
<td><p><span data-ttu-id="0326b-205">会话中生成的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="0326b-205">Diagnostic ID generated in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0326b-206"><strong>会话数</strong></span><span class="sxs-lookup"><span data-stu-id="0326b-206"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0326b-207">否</span><span class="sxs-lookup"><span data-stu-id="0326b-207">No</span></span></p></td>
<td><p><span data-ttu-id="0326b-208">生成了指定诊断 ID 的失败会话总数。</span><span class="sxs-lookup"><span data-stu-id="0326b-208">Total number of failed sessions where the specified diagnostic ID was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-modalities"></a><span data-ttu-id="0326b-209">主要形式的指标</span><span class="sxs-lookup"><span data-stu-id="0326b-209">Metrics for Top Modalities</span></span>

<span data-ttu-id="0326b-210">下表列出了故障分布报告中基于所遇故障最多的会话形式提供的信息。</span><span class="sxs-lookup"><span data-stu-id="0326b-210">The following table lists the information provided in the Failure Distribution Report based on the session modalities that experienced the most failures.</span></span>

### <a name="metrics-for-top-modalities"></a><span data-ttu-id="0326b-211">主要形式的指标</span><span class="sxs-lookup"><span data-stu-id="0326b-211">Metrics for Top Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0326b-212">名称</span><span class="sxs-lookup"><span data-stu-id="0326b-212">Name</span></span></th>
<th><span data-ttu-id="0326b-213">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="0326b-213">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0326b-214">描述</span><span class="sxs-lookup"><span data-stu-id="0326b-214">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0326b-215"><strong>等级</strong></span><span class="sxs-lookup"><span data-stu-id="0326b-215"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="0326b-216">否</span><span class="sxs-lookup"><span data-stu-id="0326b-216">No</span></span></p></td>
<td><p><span data-ttu-id="0326b-217">失败会话的相对等级，根据会话类型（例如，音频/视频会议或对等文件传输会话）确定。</span><span class="sxs-lookup"><span data-stu-id="0326b-217">Relative ranking based of failed session based on session type (for example, an audio/video conference or a peer-to-peer file transfer session).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0326b-218"><strong>主要形式</strong></span><span class="sxs-lookup"><span data-stu-id="0326b-218"><strong>Top modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="0326b-219">否</span><span class="sxs-lookup"><span data-stu-id="0326b-219">No</span></span></p></td>
<td><p><span data-ttu-id="0326b-220">会话类型。</span><span class="sxs-lookup"><span data-stu-id="0326b-220">Session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0326b-221"><strong>会话数</strong></span><span class="sxs-lookup"><span data-stu-id="0326b-221"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0326b-222">否</span><span class="sxs-lookup"><span data-stu-id="0326b-222">No</span></span></p></td>
<td><p><span data-ttu-id="0326b-223">涉及指定形式的失败会话总数。</span><span class="sxs-lookup"><span data-stu-id="0326b-223">Total number of failed sessions involving the specified modality.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-pools"></a><span data-ttu-id="0326b-224">主要池的指标</span><span class="sxs-lookup"><span data-stu-id="0326b-224">Metrics for Top Pools</span></span>

<span data-ttu-id="0326b-225">下表列出了故障分布报告中基于所遇故障最多的池提供的信息。</span><span class="sxs-lookup"><span data-stu-id="0326b-225">The following table lists the information provided in the Failure Distribution Report based on the pools that experienced the most failures.</span></span>

### <a name="metrics-for-top-pools"></a><span data-ttu-id="0326b-226">主要池的指标</span><span class="sxs-lookup"><span data-stu-id="0326b-226">Metrics for Top Pools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0326b-227">名称</span><span class="sxs-lookup"><span data-stu-id="0326b-227">Name</span></span></th>
<th><span data-ttu-id="0326b-228">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="0326b-228">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0326b-229">描述</span><span class="sxs-lookup"><span data-stu-id="0326b-229">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0326b-230"><strong>等级</strong></span><span class="sxs-lookup"><span data-stu-id="0326b-230"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="0326b-231">否</span><span class="sxs-lookup"><span data-stu-id="0326b-231">No</span></span></p></td>
<td><p><span data-ttu-id="0326b-232">基于执行会话的注册池或边缘服务器的失败会话的相对级别。</span><span class="sxs-lookup"><span data-stu-id="0326b-232">Relative ranking of failed sessions based on the Registrar pool or Edge Server where the session was conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0326b-233"><strong>主要池</strong></span><span class="sxs-lookup"><span data-stu-id="0326b-233"><strong>Top pools</strong></span></span></p></td>
<td><p><span data-ttu-id="0326b-234">否</span><span class="sxs-lookup"><span data-stu-id="0326b-234">No</span></span></p></td>
<td><p><span data-ttu-id="0326b-235">注册机构池或边缘服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="0326b-235">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0326b-236"><strong>会话数</strong></span><span class="sxs-lookup"><span data-stu-id="0326b-236"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0326b-237">否</span><span class="sxs-lookup"><span data-stu-id="0326b-237">No</span></span></p></td>
<td><p><span data-ttu-id="0326b-238">每个注册池或边缘服务器的失败会话总数。</span><span class="sxs-lookup"><span data-stu-id="0326b-238">Total number of failed sessions per Registrar pool or Edge Server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-sources"></a><span data-ttu-id="0326b-239">主要来源的指标</span><span class="sxs-lookup"><span data-stu-id="0326b-239">Metrics for Top Sources</span></span>

<span data-ttu-id="0326b-240">下表列出了故障分布报告中基于所遇故障最多的计算机提供的信息。</span><span class="sxs-lookup"><span data-stu-id="0326b-240">The following table lists the information provided in the Failure Distribution Report based on the computers that experienced the most failures.</span></span>

### <a name="metrics-for-top-sources"></a><span data-ttu-id="0326b-241">主要来源的指标</span><span class="sxs-lookup"><span data-stu-id="0326b-241">Metrics for Top Sources</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0326b-242">名称</span><span class="sxs-lookup"><span data-stu-id="0326b-242">Name</span></span></th>
<th><span data-ttu-id="0326b-243">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="0326b-243">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0326b-244">描述</span><span class="sxs-lookup"><span data-stu-id="0326b-244">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0326b-245"><strong>等级</strong></span><span class="sxs-lookup"><span data-stu-id="0326b-245"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="0326b-246">否</span><span class="sxs-lookup"><span data-stu-id="0326b-246">No</span></span></p></td>
<td><p><span data-ttu-id="0326b-247">失败会话的相对等级，根据计算机确定。</span><span class="sxs-lookup"><span data-stu-id="0326b-247">Relative ranking failed sessions per computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0326b-248"><strong>主要来源</strong></span><span class="sxs-lookup"><span data-stu-id="0326b-248"><strong>Top sources</strong></span></span></p></td>
<td><p><span data-ttu-id="0326b-249">否</span><span class="sxs-lookup"><span data-stu-id="0326b-249">No</span></span></p></td>
<td><p><span data-ttu-id="0326b-250">失败会话所涉及的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="0326b-250">Name of the computer involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0326b-251"><strong>会话数</strong></span><span class="sxs-lookup"><span data-stu-id="0326b-251"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0326b-252">否</span><span class="sxs-lookup"><span data-stu-id="0326b-252">No</span></span></p></td>
<td><p><span data-ttu-id="0326b-253">每台计算机的失败会话总数。</span><span class="sxs-lookup"><span data-stu-id="0326b-253">Total number of failed sessions per computer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-components"></a><span data-ttu-id="0326b-254">主要组件的指标</span><span class="sxs-lookup"><span data-stu-id="0326b-254">Metrics for Top Components</span></span>

<span data-ttu-id="0326b-255">下表列出了故障分布报告中提供的信息，这些信息基于遇到最多失败的 Microsoft Lync Server 2010 组件。</span><span class="sxs-lookup"><span data-stu-id="0326b-255">The following table lists the information provided in the Failure Distribution Report based on the Microsoft Lync Server 2010 components that experienced the most failures.</span></span>

### <a name="metrics-for-top-components"></a><span data-ttu-id="0326b-256">主要组件的指标</span><span class="sxs-lookup"><span data-stu-id="0326b-256">Metrics for Top Components</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0326b-257">名称</span><span class="sxs-lookup"><span data-stu-id="0326b-257">Name</span></span></th>
<th><span data-ttu-id="0326b-258">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="0326b-258">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0326b-259">描述</span><span class="sxs-lookup"><span data-stu-id="0326b-259">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0326b-260"><strong>等级</strong></span><span class="sxs-lookup"><span data-stu-id="0326b-260"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="0326b-261">否</span><span class="sxs-lookup"><span data-stu-id="0326b-261">No</span></span></p></td>
<td><p><span data-ttu-id="0326b-262">基于 Lync Server 2010 组件（如 ExumRouting、GroupChat 或 MediationServer）的失败会话的相对级别。</span><span class="sxs-lookup"><span data-stu-id="0326b-262">Relative ranking of failed sessions based on Lync Server 2010 component (for example, ExumRouting, GroupChat, or MediationServer).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0326b-263"><strong>主要组件</strong></span><span class="sxs-lookup"><span data-stu-id="0326b-263"><strong>Top components</strong></span></span></p></td>
<td><p><span data-ttu-id="0326b-264">否</span><span class="sxs-lookup"><span data-stu-id="0326b-264">No</span></span></p></td>
<td><p><span data-ttu-id="0326b-265">失败会话所涉及的组件的名称。</span><span class="sxs-lookup"><span data-stu-id="0326b-265">Name of the component involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0326b-266"><strong>会话数</strong></span><span class="sxs-lookup"><span data-stu-id="0326b-266"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0326b-267">否</span><span class="sxs-lookup"><span data-stu-id="0326b-267">No</span></span></p></td>
<td><p><span data-ttu-id="0326b-268">每个组件的失败会话总数。</span><span class="sxs-lookup"><span data-stu-id="0326b-268">Total number of failed sessions per component.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-from-users"></a><span data-ttu-id="0326b-269">主要来源用户的指标</span><span class="sxs-lookup"><span data-stu-id="0326b-269">Metrics for Top From Users</span></span>

<span data-ttu-id="0326b-270">下表列出了故障分布报告中基于尝试呼叫其他人时所遇故障最多的用户提供的信息，尝试呼叫其他人的用户称为“来源”用户。</span><span class="sxs-lookup"><span data-stu-id="0326b-270">The following table lists the information provided in the Failure Distribution Report based on users who experienced the most failures when they tried to call someone else (known as "From" users).</span></span>

### <a name="metrics-for-top-from-users"></a><span data-ttu-id="0326b-271">主要来源用户的指标</span><span class="sxs-lookup"><span data-stu-id="0326b-271">Metrics for Top From Users</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0326b-272">名称</span><span class="sxs-lookup"><span data-stu-id="0326b-272">Name</span></span></th>
<th><span data-ttu-id="0326b-273">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="0326b-273">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0326b-274">描述</span><span class="sxs-lookup"><span data-stu-id="0326b-274">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0326b-275"><strong>等级</strong></span><span class="sxs-lookup"><span data-stu-id="0326b-275"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="0326b-276">否</span><span class="sxs-lookup"><span data-stu-id="0326b-276">No</span></span></p></td>
<td><p><span data-ttu-id="0326b-277">失败会话的相对等级，根据受邀加入会话的用户确定。</span><span class="sxs-lookup"><span data-stu-id="0326b-277">Relative ranking of failed sessions based on the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0326b-278"><strong>主要来源用户</strong></span><span class="sxs-lookup"><span data-stu-id="0326b-278"><strong>Top from users</strong></span></span></p></td>
<td><p><span data-ttu-id="0326b-279">否</span><span class="sxs-lookup"><span data-stu-id="0326b-279">No</span></span></p></td>
<td><p><span data-ttu-id="0326b-280">受邀加入会话的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="0326b-280">SIP address of the user invited to join the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0326b-281"><strong>会话数</strong></span><span class="sxs-lookup"><span data-stu-id="0326b-281"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0326b-282">否</span><span class="sxs-lookup"><span data-stu-id="0326b-282">No</span></span></p></td>
<td><p><span data-ttu-id="0326b-283">每个用户的失败会话总数。</span><span class="sxs-lookup"><span data-stu-id="0326b-283">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-to-users"></a><span data-ttu-id="0326b-284">主要目标用户的指标</span><span class="sxs-lookup"><span data-stu-id="0326b-284">Metrics for Top To Users</span></span>

<span data-ttu-id="0326b-285">下表列出了故障分布报告中基于其他人尝试呼叫的所遇故障最多的用户提供的信息，其他人尝试呼叫的用户称为“目标”用户。</span><span class="sxs-lookup"><span data-stu-id="0326b-285">The following table lists the information provided in the Failure Distribution Report based on the users who experienced the most failures when another user tried to call them (known as "To" users).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0326b-286">名称</span><span class="sxs-lookup"><span data-stu-id="0326b-286">Name</span></span></th>
<th><span data-ttu-id="0326b-287">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="0326b-287">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0326b-288">描述</span><span class="sxs-lookup"><span data-stu-id="0326b-288">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0326b-289"><strong>等级</strong></span><span class="sxs-lookup"><span data-stu-id="0326b-289"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="0326b-290">否</span><span class="sxs-lookup"><span data-stu-id="0326b-290">No</span></span></p></td>
<td><p><span data-ttu-id="0326b-291">失败会话的相对等级，根据发起会话的用户确定。</span><span class="sxs-lookup"><span data-stu-id="0326b-291">Relative ranking of failed sessions based on the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0326b-292"><strong>主要目标用户</strong></span><span class="sxs-lookup"><span data-stu-id="0326b-292"><strong>Top to users</strong></span></span></p></td>
<td><p><span data-ttu-id="0326b-293">否</span><span class="sxs-lookup"><span data-stu-id="0326b-293">No</span></span></p></td>
<td><p><span data-ttu-id="0326b-294">发起会话的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="0326b-294">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0326b-295"><strong>会话数</strong></span><span class="sxs-lookup"><span data-stu-id="0326b-295"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0326b-296">否</span><span class="sxs-lookup"><span data-stu-id="0326b-296">No</span></span></p></td>
<td><p><span data-ttu-id="0326b-297">每个用户的失败会话总数。</span><span class="sxs-lookup"><span data-stu-id="0326b-297">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-user-agents"></a><span data-ttu-id="0326b-298">主要用户代理的指标</span><span class="sxs-lookup"><span data-stu-id="0326b-298">Metrics for Top User Agents</span></span>

<span data-ttu-id="0326b-299">下表列出了故障分布报告中基于所遇故障最多的终结点软件提供的信息。</span><span class="sxs-lookup"><span data-stu-id="0326b-299">The following table lists the information provided in the Failure Distribution Report based on the endpoint software that experienced the most failures.</span></span>

### <a name="metrics-for-top-user-agents"></a><span data-ttu-id="0326b-300">主要用户代理的指标</span><span class="sxs-lookup"><span data-stu-id="0326b-300">Metrics for Top User Agents</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0326b-301">名称</span><span class="sxs-lookup"><span data-stu-id="0326b-301">Name</span></span></th>
<th><span data-ttu-id="0326b-302">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="0326b-302">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0326b-303">描述</span><span class="sxs-lookup"><span data-stu-id="0326b-303">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0326b-304"><strong>等级</strong></span><span class="sxs-lookup"><span data-stu-id="0326b-304"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="0326b-305">否</span><span class="sxs-lookup"><span data-stu-id="0326b-305">No</span></span></p></td>
<td><p><span data-ttu-id="0326b-p115">失败会话的相对等级，根据会话所涉及的用户代理（软件）确定。例如：RTCC/4.0.0.0 Inbound Routing/4.0.0.0。</span><span class="sxs-lookup"><span data-stu-id="0326b-p115">Relative ranking of failed sessions based on the user agent (software) involved in the session. For example: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0326b-308"><strong>主要用户代理</strong></span><span class="sxs-lookup"><span data-stu-id="0326b-308"><strong>Top user agents</strong></span></span></p></td>
<td><p><span data-ttu-id="0326b-309">否</span><span class="sxs-lookup"><span data-stu-id="0326b-309">No</span></span></p></td>
<td><p><span data-ttu-id="0326b-310">失败会话所涉及的用户代理的名称。</span><span class="sxs-lookup"><span data-stu-id="0326b-310">Name of the user agent involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0326b-311"><strong>会话数</strong></span><span class="sxs-lookup"><span data-stu-id="0326b-311"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0326b-312">否</span><span class="sxs-lookup"><span data-stu-id="0326b-312">No</span></span></p></td>
<td><p><span data-ttu-id="0326b-313">每个用户代理的失败会话总数。</span><span class="sxs-lookup"><span data-stu-id="0326b-313">Total number of failed sessions per user agent.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

