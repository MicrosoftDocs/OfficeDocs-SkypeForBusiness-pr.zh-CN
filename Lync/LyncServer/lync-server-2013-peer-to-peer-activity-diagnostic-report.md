---
title: Lync Server 2013：对等活动诊断报告
description: Lync Server 2013：对等活动诊断报告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Activity Diagnostic Report
ms:assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558602(v=OCS.15)
ms:contentKeyID: 48183242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80172c5e0f8b23bf05fad6ec300f0d1ffefb3327
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557348"
---
# <a name="peer-to-peer-activity-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="e4f5a-103">Lync Server 2013 中的对等活动诊断报告</span><span class="sxs-lookup"><span data-stu-id="e4f5a-103">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4f5a-104">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e4f5a-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e4f5a-105">点对点活动诊断报告提供有关成功和失败的点对点通信会话的信息。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-105">The Peer-to-Peer Activity Diagnostic Report provides information about the success and failure of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="e4f5a-106">请注意，Microsoft Lync Server 2013 区分不同类型的故障：</span><span class="sxs-lookup"><span data-stu-id="e4f5a-106">Note that Microsoft Lync Server 2013 distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="e4f5a-107">**预期失败**。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-107">**Expected failure**.</span></span> <span data-ttu-id="e4f5a-108">预期失败通常指纯技术意义上的失败。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-108">An expected failure is typically a failure only in the most technical sense.</span></span> <span data-ttu-id="e4f5a-109">例如，假设您呼叫某人，但他或她不在办公室，因此无法接听电话。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-109">For example, suppose you call someone, but he or she is away from the office and is unable to answer the phone.</span></span> <span data-ttu-id="e4f5a-110">此呼叫未应答，因而在技术上视为失败。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-110">Because the call was not answered, the call is technically considered a failure.</span></span> <span data-ttu-id="e4f5a-111">另一方面，这是一种预期故障： Microsoft Lync Server 2013 不希望你应答电话（如果你不能应答电话）。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-111">On the other hand, this was an expected failure: Microsoft Lync Server 2013 does not expect you to answer the phone if you're not available to answer the phone.</span></span> <span data-ttu-id="e4f5a-112">同样地，如果您尝试发送一条即时消息给某人，而对方处于脱机状态，或者对方只登录到不支持即时消息的电话时，也会发生预期失败。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-112">Likewise, an expected failure will occur if you attempt to send an instant message to a user who is offline, or is logged on only to a phone that does not support instant messaging.</span></span>

  - <span data-ttu-id="e4f5a-113">**意外失败**。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-113">**Unexpected failure**.</span></span> <span data-ttu-id="e4f5a-114">意外错误完全可顾名思义为：您预期不会发生的一种基于环境的错误。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-114">An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur.</span></span> <span data-ttu-id="e4f5a-115">例如，假设您呼叫某人，并且该人可用于应答呼叫;但是，当 Lync Server 2013 尝试将呼叫路由到语音邮件时，调用失败，因为与 Exchange 统一消息的连接已丢失。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-115">For example, suppose you call someone and that person is available to answer the call; however, when Lync Server 2013 tries to route your call to voicemail the call fails because connectivity to Exchange Unified Messaging has been lost.</span></span> <span data-ttu-id="e4f5a-116">这是一个意外错误：您原以为呼叫总是能路由到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-116">That's an unexpected error: you would expect that calls could always be routed to voicemail.</span></span> <span data-ttu-id="e4f5a-117">一般说来，意外失败是真正的失败：不能通过用户培训或类似措施加以补救。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-117">As a general rule, unexpected failures are true failures: they are problems that likely cannot be remedied through user education or similar measures.</span></span>

<span data-ttu-id="e4f5a-p104">请注意，“成功”、“预期失败”、“意外失败”度量值加起来可能并不等于“会话总数”度量值。例如，在前面的说明中，我们获得以下值：</span><span class="sxs-lookup"><span data-stu-id="e4f5a-p104">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric. For example, in the preceding illustration, we have the following values:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4f5a-120">成功</span><span class="sxs-lookup"><span data-stu-id="e4f5a-120">Successes</span></span></th>
<th><span data-ttu-id="e4f5a-121">预期失败</span><span class="sxs-lookup"><span data-stu-id="e4f5a-121">Expected failures</span></span></th>
<th><span data-ttu-id="e4f5a-122">意外失败</span><span class="sxs-lookup"><span data-stu-id="e4f5a-122">Unexpected failures</span></span></th>
<th><span data-ttu-id="e4f5a-123">会话总数</span><span class="sxs-lookup"><span data-stu-id="e4f5a-123">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4f5a-124">2024</span><span class="sxs-lookup"><span data-stu-id="e4f5a-124">2024</span></span></p></td>
<td><p><span data-ttu-id="e4f5a-125">469</span><span class="sxs-lookup"><span data-stu-id="e4f5a-125">469</span></span></p></td>
<td><p><span data-ttu-id="e4f5a-126">16 </span><span class="sxs-lookup"><span data-stu-id="e4f5a-126">16</span></span></p></td>
<td><p><span data-ttu-id="e4f5a-127">2521</span><span class="sxs-lookup"><span data-stu-id="e4f5a-127">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e4f5a-128">2024 + 469 + 16 将获得总共 2,509 个会话，而“会话总数”列显示总共 2,521 个会话。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-128">If you add 2024 + 469 + 16 you get a total of 2,509 sessions, yet the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="e4f5a-129">“丢失的”12 个会话是系统无法归类为是成功还是失败的会话。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-129">The "missing" 12 sessions are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="e4f5a-130">当第三方产品引入 Lync Server 不熟悉的新诊断代码时，有时会出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-130">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Lync Server.</span></span> <span data-ttu-id="e4f5a-131">这时，使用该产品并报告该诊断代码的呼叫并非总是能归类为“成功”、“预期失败”或“意外失败”。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-131">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="e4f5a-132">访问点对点活动诊断报告</span><span class="sxs-lookup"><span data-stu-id="e4f5a-132">Accessing the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="e4f5a-133">可以从“监控报告”主页访问点对点诊断报告。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-133">The Peer-to-Peer Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="e4f5a-134">您可以通过单击以下任一指标来访问 [Lync Server 2013 中的故障分布报告](lync-server-2013-failure-distribution-report.md) ：</span><span class="sxs-lookup"><span data-stu-id="e4f5a-134">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="e4f5a-135">意外失败量</span><span class="sxs-lookup"><span data-stu-id="e4f5a-135">Unexpected failure volume</span></span>

  - <span data-ttu-id="e4f5a-136">预期失败量</span><span class="sxs-lookup"><span data-stu-id="e4f5a-136">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="e4f5a-137">充分利用点对点活动诊断报告</span><span class="sxs-lookup"><span data-stu-id="e4f5a-137">Making the Best Use of the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="e4f5a-p107">虽然可以通过多种方法来筛选点对点活动诊断报告，但默认情况下，那些筛选选项在视图中是隐藏的。若要查看您可以使用的筛选选项，请单击报告窗口右上角中的“显示/隐藏参数”按钮。然后，即可使用筛选选项。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-p107">There are a number of ways you can filter the Peer-to-Peer Activity Diagnostic Report but, by default, those filtering options are hidden from view. To view the filtering options available to you, click the Show/Hide Parameters button in the upper right-hand corner of the report window. Once you do that the filtering options will be available for use.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="e4f5a-141">筛选器</span><span class="sxs-lookup"><span data-stu-id="e4f5a-141">Filters</span></span>

<span data-ttu-id="e4f5a-p108">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，点对点活动诊断报告允许您根据会话形式（例如，即时消息、文件传输或应用程序共享）等内容进行筛选。您还可以选择数据的分组方式。在此示例中，将按小时、天、周或月对呼叫进行分组。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-p108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Peer-to-Peer Activity Diagnostic Report enables you to filter on such things as the session modality (for example, instant messaging, file transfer, or application sharing). You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="e4f5a-146">下表列出了可用于点对点活动诊断报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-146">The following table lists the filters that you can use with the Peer-to-Peer Activity Diagnostic Report.</span></span>

### <a name="peer-to-peer-activity-diagnostic-report-filters"></a><span data-ttu-id="e4f5a-147">点对点活动诊断报告筛选器</span><span class="sxs-lookup"><span data-stu-id="e4f5a-147">Peer-to-Peer Activity Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4f5a-148">名称</span><span class="sxs-lookup"><span data-stu-id="e4f5a-148">Name</span></span></th>
<th><span data-ttu-id="e4f5a-149">说明</span><span class="sxs-lookup"><span data-stu-id="e4f5a-149">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4f5a-150"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="e4f5a-150"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f5a-p109">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e4f5a-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="e4f5a-153">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="e4f5a-153">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e4f5a-p110">如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="e4f5a-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e4f5a-156">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e4f5a-156">7/7/2012</span></span></p>
<p><span data-ttu-id="e4f5a-157">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="e4f5a-157">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e4f5a-158">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e4f5a-158">7/3/2012</span></span></p>
<p><span data-ttu-id="e4f5a-159">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-159">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4f5a-160"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="e4f5a-160"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f5a-p111">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e4f5a-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="e4f5a-163">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="e4f5a-163">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e4f5a-p112">如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="e4f5a-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e4f5a-166">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e4f5a-166">7/7/2012</span></span></p>
<p><span data-ttu-id="e4f5a-167">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="e4f5a-167">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e4f5a-168">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e4f5a-168">7/3/2012</span></span></p>
<p><span data-ttu-id="e4f5a-169">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-169">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4f5a-170"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="e4f5a-170"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f5a-p113">时间间隔。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="e4f5a-p113">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e4f5a-173">每小时（最多可显示 25 个小时）</span><span class="sxs-lookup"><span data-stu-id="e4f5a-173">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="e4f5a-174">每天（最多可显示 31 天）</span><span class="sxs-lookup"><span data-stu-id="e4f5a-174">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="e4f5a-175">每周（最多可显示 12 周）</span><span class="sxs-lookup"><span data-stu-id="e4f5a-175">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="e4f5a-176">每月（最多可显示 12 个月）</span><span class="sxs-lookup"><span data-stu-id="e4f5a-176">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="e4f5a-p114">如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。例如，如果选择的开始日期为 8/7/2012、结束日期为 9/28/2012、间隔为“每天”，则显示从 8/7/2012 12:00 AM 到 9/7/2012 12:00 AM 这些天的数据（即总共 31 天的数据）。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-p114">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4f5a-179"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="e4f5a-179"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f5a-p115">注册器池或边缘服务器的完全限定域名 (FQDN)。可以选择单个池，也可以单击“[所有]”<strong></strong>查看所有池的数据。系统根据数据库中的记录自动为您填充该下拉列表。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-p115">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4f5a-183"><strong>模态</strong></span><span class="sxs-lookup"><span data-stu-id="e4f5a-183"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f5a-p116">指示发生的通信活动的类型。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="e4f5a-p116">Indicates the type of communication activity that took place. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e4f5a-186">各种</span><span class="sxs-lookup"><span data-stu-id="e4f5a-186">[All]</span></span></p></li>
<li><p><span data-ttu-id="e4f5a-187">即时消息</span><span class="sxs-lookup"><span data-stu-id="e4f5a-187">Instant messaging</span></span></p></li>
<li><p><span data-ttu-id="e4f5a-188">文件传输</span><span class="sxs-lookup"><span data-stu-id="e4f5a-188">File transfer</span></span></p></li>
<li><p><span data-ttu-id="e4f5a-189">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="e4f5a-189">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="e4f5a-190">音频</span><span class="sxs-lookup"><span data-stu-id="e4f5a-190">Audio</span></span></p></li>
<li><p><span data-ttu-id="e4f5a-191">视频</span><span class="sxs-lookup"><span data-stu-id="e4f5a-191">Video</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-per-modality"></a><span data-ttu-id="e4f5a-192">每种形式的指标</span><span class="sxs-lookup"><span data-stu-id="e4f5a-192">Metrics (per modality)</span></span>

<span data-ttu-id="e4f5a-193">下表列出了每种形式的点对点活动诊断报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-193">The following table lists the information provided in the Peer-to-Peer Activity Diagnostic Report for each modality.</span></span>

### <a name="metrics-per-modality"></a><span data-ttu-id="e4f5a-194">每种形式的指标</span><span class="sxs-lookup"><span data-stu-id="e4f5a-194">Metrics (per modality)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4f5a-195">名称</span><span class="sxs-lookup"><span data-stu-id="e4f5a-195">Name</span></span></th>
<th><span data-ttu-id="e4f5a-196">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="e4f5a-196">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e4f5a-197">说明</span><span class="sxs-lookup"><span data-stu-id="e4f5a-197">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4f5a-198"><strong>成功量</strong></span><span class="sxs-lookup"><span data-stu-id="e4f5a-198"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f5a-199">否</span><span class="sxs-lookup"><span data-stu-id="e4f5a-199">No</span></span></p></td>
<td><p><span data-ttu-id="e4f5a-200">成功的点对点会话总数。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-200">Total number of successful peer-to-peer sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4f5a-201"><strong>成功百分比</strong></span><span class="sxs-lookup"><span data-stu-id="e4f5a-201"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f5a-202">否</span><span class="sxs-lookup"><span data-stu-id="e4f5a-202">No</span></span></p></td>
<td><p><span data-ttu-id="e4f5a-p117">已完成且没有严重问题的点对点会话百分比。计算方法是“成功量”除以“会话总数”。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-p117">Percentage of peer-to-peer sessions that completed with significant problems. Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4f5a-205"><strong>预期失败量</strong></span><span class="sxs-lookup"><span data-stu-id="e4f5a-205"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f5a-206">否</span><span class="sxs-lookup"><span data-stu-id="e4f5a-206">No</span></span></p></td>
<td><p><span data-ttu-id="e4f5a-207">预期失败发生的会话总数 &quot; &quot; 。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-207">Total number of sessions where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="e4f5a-p118">预期失败是指预计会出现的失败情况。例如，如果用户将其状态设置为“请勿打扰”，那么向该用户发出的任何呼叫应该都会失败。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-p118">An expected failure is a failure that is expected to happen. For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4f5a-210"><strong>预期失败百分比</strong></span><span class="sxs-lookup"><span data-stu-id="e4f5a-210"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f5a-211">否</span><span class="sxs-lookup"><span data-stu-id="e4f5a-211">No</span></span></p></td>
<td><p><span data-ttu-id="e4f5a-p119">遇到预期错误的点对点会话百分比。计算方法是“预期失败量”除以“会话总数”。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-p119">Percentage of peer-to-peer sessions that experienced an expected error. Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4f5a-214"><strong>意外失败量</strong></span><span class="sxs-lookup"><span data-stu-id="e4f5a-214"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f5a-215">否</span><span class="sxs-lookup"><span data-stu-id="e4f5a-215">No</span></span></p></td>
<td><p><span data-ttu-id="e4f5a-216">发生意外故障的会话总数 &quot; &quot; 。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-216">Total number of sessions where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="e4f5a-p120">意外失败是指在本该正常运行的系统中出现的失败情况。例如，如果呼叫者处于呼叫等待状态，则不应该终止呼叫。如果终止，则会被标记为意外失败。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-p120">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system. For example, a call should not be terminated if the caller is placed on hold. If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4f5a-220"><strong>意外失败百分比</strong></span><span class="sxs-lookup"><span data-stu-id="e4f5a-220"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f5a-221">否</span><span class="sxs-lookup"><span data-stu-id="e4f5a-221">No</span></span></p></td>
<td><p><span data-ttu-id="e4f5a-p121">遇到意外错误的点对点会话百分比。计算方法是“意外失败量”除以“会话总数”。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-p121">Percentage of peer-to-peer sessions that experienced an unexpected error. Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4f5a-224"><strong>会话总数</strong></span><span class="sxs-lookup"><span data-stu-id="e4f5a-224"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="e4f5a-225">否</span><span class="sxs-lookup"><span data-stu-id="e4f5a-225">No</span></span></p></td>
<td><p><span data-ttu-id="e4f5a-226">会话的总数，包括成功的会话、失败的会话（预期失败和意外失败）及未归类的会话。</span><span class="sxs-lookup"><span data-stu-id="e4f5a-226">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

