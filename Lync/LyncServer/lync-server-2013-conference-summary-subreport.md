---
title: Lync Server 2013：会议摘要子报告
description: Lync Server 2013：会议摘要子报告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Summary Subreport
ms:assetid: 2fc1d2bf-34f5-4093-a6e2-250ec1f1b004
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204779(v=OCS.15)
ms:contentKeyID: 48183742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0612ce1adb8a6b0fdea5e3bf70b88346f7c08044
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550688"
---
# <a name="conference-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="22ac3-103">Lync Server 2013 中的会议摘要子报告</span><span class="sxs-lookup"><span data-stu-id="22ac3-103">Conference Summary Subreport in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22ac3-104">_**上次修改的主题：** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="22ac3-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="22ac3-p101">会议摘要子报告提供了失败的会议会话的总体概述。这些失败的会话按以下会话类型进一步细分：焦点会话和 MCU 会话。</span><span class="sxs-lookup"><span data-stu-id="22ac3-p101">The Conference Summary Subreport provides an overall view of failed conference sessions. These failed sessions are further broken down by session type: Focus sessions and MCU sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="22ac3-107">筛选器</span><span class="sxs-lookup"><span data-stu-id="22ac3-107">Filters</span></span>

<span data-ttu-id="22ac3-p102">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。下表列出了可用于会议摘要子报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="22ac3-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-filters"></a><span data-ttu-id="22ac3-110">会议摘要子报告筛选器</span><span class="sxs-lookup"><span data-stu-id="22ac3-110">Conference Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="22ac3-111">名称</span><span class="sxs-lookup"><span data-stu-id="22ac3-111">Name</span></span></th>
<th><span data-ttu-id="22ac3-112">说明</span><span class="sxs-lookup"><span data-stu-id="22ac3-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="22ac3-113"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="22ac3-113"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="22ac3-p103">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="22ac3-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="22ac3-116">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="22ac3-116">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="22ac3-p104">如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="22ac3-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="22ac3-119">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="22ac3-119">7/7/2012</span></span></p>
<p><span data-ttu-id="22ac3-120">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="22ac3-120">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="22ac3-121">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="22ac3-121">7/3/2012</span></span></p>
<p><span data-ttu-id="22ac3-122">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="22ac3-122">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22ac3-123"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="22ac3-123"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="22ac3-p105">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="22ac3-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="22ac3-126">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="22ac3-126">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="22ac3-p106">如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="22ac3-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="22ac3-129">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="22ac3-129">7/7/2012</span></span></p>
<p><span data-ttu-id="22ac3-130">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="22ac3-130">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="22ac3-131">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="22ac3-131">7/3/2012</span></span></p>
<p><span data-ttu-id="22ac3-132">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="22ac3-132">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22ac3-133"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="22ac3-133"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="22ac3-p107">注册器池或边缘服务器的完全限定域名 (FQDN)。可以选择单个池，也可以单击“[所有]”<strong></strong>查看所有池的数据。系统根据数据库中的记录自动为您填充该下拉列表。</span><span class="sxs-lookup"><span data-stu-id="22ac3-p107">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="22ac3-137">指标</span><span class="sxs-lookup"><span data-stu-id="22ac3-137">Metrics</span></span>

<span data-ttu-id="22ac3-138">下表列出了会议摘要子报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="22ac3-138">The following table lists the information provided in the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-metrics"></a><span data-ttu-id="22ac3-139">会议摘要子报告指标</span><span class="sxs-lookup"><span data-stu-id="22ac3-139">Conference Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="22ac3-140">名称</span><span class="sxs-lookup"><span data-stu-id="22ac3-140">Name</span></span></th>
<th><span data-ttu-id="22ac3-141">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="22ac3-141">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="22ac3-142">说明</span><span class="sxs-lookup"><span data-stu-id="22ac3-142">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="22ac3-143"><strong>会议总数</strong></span><span class="sxs-lookup"><span data-stu-id="22ac3-143"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="22ac3-144">否</span><span class="sxs-lookup"><span data-stu-id="22ac3-144">No</span></span></p></td>
<td><p><span data-ttu-id="22ac3-145">举行的会议总数。</span><span class="sxs-lookup"><span data-stu-id="22ac3-145">Total number of conferences held.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22ac3-146"><strong>会议会话总数</strong></span><span class="sxs-lookup"><span data-stu-id="22ac3-146"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="22ac3-147">否</span><span class="sxs-lookup"><span data-stu-id="22ac3-147">No</span></span></p></td>
<td><p><span data-ttu-id="22ac3-p108">会议会话总数。单个会议可以具有多个会话；例如，会议可能同时包括焦点会话和 MCU 会话。</span><span class="sxs-lookup"><span data-stu-id="22ac3-p108">Total number of conference sessions. A single conference can have multiple sessions; for example, a conference might include both a Focus session and an MCU session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22ac3-150"><strong>总体会话故障率</strong></span><span class="sxs-lookup"><span data-stu-id="22ac3-150"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="22ac3-151">否</span><span class="sxs-lookup"><span data-stu-id="22ac3-151">No</span></span></p></td>
<td><p><span data-ttu-id="22ac3-152">所有失败会议的百分比。</span><span class="sxs-lookup"><span data-stu-id="22ac3-152">Percentage of all conferences that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22ac3-153"><strong>焦点会话</strong></span><span class="sxs-lookup"><span data-stu-id="22ac3-153"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="22ac3-154">否</span><span class="sxs-lookup"><span data-stu-id="22ac3-154">No</span></span></p></td>
<td><p><span data-ttu-id="22ac3-155">焦点会话总数。</span><span class="sxs-lookup"><span data-stu-id="22ac3-155">Total number of Focus sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22ac3-156"><strong>焦点故障率</strong></span><span class="sxs-lookup"><span data-stu-id="22ac3-156"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="22ac3-157">否</span><span class="sxs-lookup"><span data-stu-id="22ac3-157">No</span></span></p></td>
<td><p><span data-ttu-id="22ac3-158">失败的焦点会话的百分比。</span><span class="sxs-lookup"><span data-stu-id="22ac3-158">Percentage of Focus sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22ac3-159">MCU 会话</span><span class="sxs-lookup"><span data-stu-id="22ac3-159">MCU sessions</span></span></p></td>
<td><p><span data-ttu-id="22ac3-160">否</span><span class="sxs-lookup"><span data-stu-id="22ac3-160">No</span></span></p></td>
<td><p><span data-ttu-id="22ac3-161">MCU 会话总数。
</span><span class="sxs-lookup"><span data-stu-id="22ac3-161">Total number of MCU sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22ac3-162"><strong>MCU 故障率</strong></span><span class="sxs-lookup"><span data-stu-id="22ac3-162"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="22ac3-163">否</span><span class="sxs-lookup"><span data-stu-id="22ac3-163">No</span></span></p></td>
<td><p><span data-ttu-id="22ac3-164">失败的 MCU 会话的百分比。</span><span class="sxs-lookup"><span data-stu-id="22ac3-164">Percentage of MCU sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22ac3-165"><strong>按形式列出的 MCU 会话</strong></span><span class="sxs-lookup"><span data-stu-id="22ac3-165"><strong>MCU sessions by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="22ac3-166">否</span><span class="sxs-lookup"><span data-stu-id="22ac3-166">No</span></span></p></td>
<td><p><span data-ttu-id="22ac3-167">按形式分组的 MCU 会话总数（例如，IM 会议）。</span><span class="sxs-lookup"><span data-stu-id="22ac3-167">Total number of MCU sessions, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22ac3-168"><strong>按形式列出的故障率</strong></span><span class="sxs-lookup"><span data-stu-id="22ac3-168"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="22ac3-169">否</span><span class="sxs-lookup"><span data-stu-id="22ac3-169">No</span></span></p></td>
<td><p><span data-ttu-id="22ac3-170">按形式分组的失败的 MCU 会话的百分比（例如，IM 会议）。</span><span class="sxs-lookup"><span data-stu-id="22ac3-170">Percentage of MCU sessions that failed, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

