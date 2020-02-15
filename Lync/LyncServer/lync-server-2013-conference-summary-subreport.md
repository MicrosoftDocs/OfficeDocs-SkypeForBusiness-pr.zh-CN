---
title: Lync Server 2013：会议摘要子报告
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
ms.openlocfilehash: d2c31c614298112b91874882df1e4945845b74bd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="f2791-102">Lync Server 2013 中的会议摘要子报告</span><span class="sxs-lookup"><span data-stu-id="f2791-102">Conference Summary Subreport in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2791-103">_**上次修改的主题：** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="f2791-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="f2791-p101">会议摘要子报告提供了失败的会议会话的总体概述。这些失败的会话按以下会话类型进一步细分：焦点会话和 MCU 会话。</span><span class="sxs-lookup"><span data-stu-id="f2791-p101">The Conference Summary Subreport provides an overall view of failed conference sessions. These failed sessions are further broken down by session type: Focus sessions and MCU sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="f2791-106">筛选器</span><span class="sxs-lookup"><span data-stu-id="f2791-106">Filters</span></span>

<span data-ttu-id="f2791-p102">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。下表列出了可用于会议摘要子报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="f2791-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-filters"></a><span data-ttu-id="f2791-109">会议摘要子报告筛选器</span><span class="sxs-lookup"><span data-stu-id="f2791-109">Conference Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2791-110">名称</span><span class="sxs-lookup"><span data-stu-id="f2791-110">Name</span></span></th>
<th><span data-ttu-id="f2791-111">说明</span><span class="sxs-lookup"><span data-stu-id="f2791-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2791-112"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="f2791-112"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="f2791-p103">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f2791-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="f2791-115">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="f2791-115">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="f2791-p104">如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="f2791-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="f2791-118">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="f2791-118">7/7/2012</span></span></p>
<p><span data-ttu-id="f2791-119">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="f2791-119">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="f2791-120">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="f2791-120">7/3/2012</span></span></p>
<p><span data-ttu-id="f2791-121">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="f2791-121">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2791-122"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="f2791-122"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="f2791-p105">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f2791-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="f2791-125">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="f2791-125">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="f2791-p106">如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="f2791-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="f2791-128">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="f2791-128">7/7/2012</span></span></p>
<p><span data-ttu-id="f2791-129">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="f2791-129">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="f2791-130">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="f2791-130">7/3/2012</span></span></p>
<p><span data-ttu-id="f2791-131">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="f2791-131">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2791-132"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="f2791-132"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="f2791-p107">注册器池或边缘服务器的完全限定域名 (FQDN)。可以选择单个池，也可以单击“[所有]”<strong></strong>查看所有池的数据。系统根据数据库中的记录自动为您填充该下拉列表。</span><span class="sxs-lookup"><span data-stu-id="f2791-p107">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="f2791-136">指标</span><span class="sxs-lookup"><span data-stu-id="f2791-136">Metrics</span></span>

<span data-ttu-id="f2791-137">下表列出了会议摘要子报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="f2791-137">The following table lists the information provided in the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-metrics"></a><span data-ttu-id="f2791-138">会议摘要子报告指标</span><span class="sxs-lookup"><span data-stu-id="f2791-138">Conference Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2791-139">名称</span><span class="sxs-lookup"><span data-stu-id="f2791-139">Name</span></span></th>
<th><span data-ttu-id="f2791-140">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="f2791-140">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="f2791-141">说明</span><span class="sxs-lookup"><span data-stu-id="f2791-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2791-142"><strong>会议总数</strong></span><span class="sxs-lookup"><span data-stu-id="f2791-142"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="f2791-143">否</span><span class="sxs-lookup"><span data-stu-id="f2791-143">No</span></span></p></td>
<td><p><span data-ttu-id="f2791-144">举行的会议总数。</span><span class="sxs-lookup"><span data-stu-id="f2791-144">Total number of conferences held.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2791-145"><strong>会议会话总数</strong></span><span class="sxs-lookup"><span data-stu-id="f2791-145"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="f2791-146">否</span><span class="sxs-lookup"><span data-stu-id="f2791-146">No</span></span></p></td>
<td><p><span data-ttu-id="f2791-p108">会议会话总数。单个会议可以具有多个会话；例如，会议可能同时包括焦点会话和 MCU 会话。</span><span class="sxs-lookup"><span data-stu-id="f2791-p108">Total number of conference sessions. A single conference can have multiple sessions; for example, a conference might include both a Focus session and an MCU session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2791-149"><strong>总体会话故障率</strong></span><span class="sxs-lookup"><span data-stu-id="f2791-149"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="f2791-150">否</span><span class="sxs-lookup"><span data-stu-id="f2791-150">No</span></span></p></td>
<td><p><span data-ttu-id="f2791-151">所有失败会议的百分比。</span><span class="sxs-lookup"><span data-stu-id="f2791-151">Percentage of all conferences that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2791-152"><strong>焦点会话</strong></span><span class="sxs-lookup"><span data-stu-id="f2791-152"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="f2791-153">否</span><span class="sxs-lookup"><span data-stu-id="f2791-153">No</span></span></p></td>
<td><p><span data-ttu-id="f2791-154">焦点会话总数。</span><span class="sxs-lookup"><span data-stu-id="f2791-154">Total number of Focus sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2791-155"><strong>焦点故障率</strong></span><span class="sxs-lookup"><span data-stu-id="f2791-155"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="f2791-156">否</span><span class="sxs-lookup"><span data-stu-id="f2791-156">No</span></span></p></td>
<td><p><span data-ttu-id="f2791-157">失败的焦点会话的百分比。</span><span class="sxs-lookup"><span data-stu-id="f2791-157">Percentage of Focus sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2791-158">MCU 会话</span><span class="sxs-lookup"><span data-stu-id="f2791-158">MCU sessions</span></span></p></td>
<td><p><span data-ttu-id="f2791-159">否</span><span class="sxs-lookup"><span data-stu-id="f2791-159">No</span></span></p></td>
<td><p><span data-ttu-id="f2791-160">MCU 会话总数。
</span><span class="sxs-lookup"><span data-stu-id="f2791-160">Total number of MCU sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2791-161"><strong>MCU 故障率</strong></span><span class="sxs-lookup"><span data-stu-id="f2791-161"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="f2791-162">否</span><span class="sxs-lookup"><span data-stu-id="f2791-162">No</span></span></p></td>
<td><p><span data-ttu-id="f2791-163">失败的 MCU 会话的百分比。</span><span class="sxs-lookup"><span data-stu-id="f2791-163">Percentage of MCU sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2791-164"><strong>按形式列出的 MCU 会话</strong></span><span class="sxs-lookup"><span data-stu-id="f2791-164"><strong>MCU sessions by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="f2791-165">否</span><span class="sxs-lookup"><span data-stu-id="f2791-165">No</span></span></p></td>
<td><p><span data-ttu-id="f2791-166">按形式分组的 MCU 会话总数（例如，IM 会议）。</span><span class="sxs-lookup"><span data-stu-id="f2791-166">Total number of MCU sessions, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2791-167"><strong>按形式列出的故障率</strong></span><span class="sxs-lookup"><span data-stu-id="f2791-167"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="f2791-168">否</span><span class="sxs-lookup"><span data-stu-id="f2791-168">No</span></span></p></td>
<td><p><span data-ttu-id="f2791-169">按形式分组的失败的 MCU 会话的百分比（例如，IM 会议）。</span><span class="sxs-lookup"><span data-stu-id="f2791-169">Percentage of MCU sessions that failed, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

