---
title: Lync Server 2013： P2P 摘要子报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: P2P Summary Subreport
ms:assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205416(v=OCS.15)
ms:contentKeyID: 48185950
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 345a659d3edfe8542391719ed4b90717b45a3c35
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215778"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="p2p-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="a422c-102">Lync Server 2013 中的 P2P 摘要子报告</span><span class="sxs-lookup"><span data-stu-id="a422c-102">P2P Summary Subreport in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a422c-103">_**上次修改的主题：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="a422c-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="a422c-104">P2P 摘要子报表对失败点对点通信会话提供一个总体视图。</span><span class="sxs-lookup"><span data-stu-id="a422c-104">The P2P Summary Subreport provides an overall view of your failed peer-to-peer communication sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="a422c-105">筛选器</span><span class="sxs-lookup"><span data-stu-id="a422c-105">Filters</span></span>

<span data-ttu-id="a422c-p101">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。下表列出了可用于 P2P 摘要子报表的筛选器。</span><span class="sxs-lookup"><span data-stu-id="a422c-p101">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-filters"></a><span data-ttu-id="a422c-108">P2P 摘要子报表筛选器</span><span class="sxs-lookup"><span data-stu-id="a422c-108">P2P Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a422c-109">名称</span><span class="sxs-lookup"><span data-stu-id="a422c-109">Name</span></span></th>
<th><span data-ttu-id="a422c-110">说明</span><span class="sxs-lookup"><span data-stu-id="a422c-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a422c-111"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="a422c-111"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="a422c-p102">时间范围的开始日期和时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a422c-p102">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="a422c-114">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="a422c-114">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="a422c-p103">如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="a422c-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a422c-117">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="a422c-117">7/7/2012</span></span></p>
<p><span data-ttu-id="a422c-118">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="a422c-118">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a422c-119">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="a422c-119">7/3/2012</span></span></p>
<p><span data-ttu-id="a422c-120">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="a422c-120">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a422c-121"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="a422c-121"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="a422c-p104">时间范围的结束日期和时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a422c-p104">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="a422c-124">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="a422c-124">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="a422c-p105">如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="a422c-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a422c-127">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="a422c-127">7/7/2012</span></span></p>
<p><span data-ttu-id="a422c-128">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="a422c-128">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a422c-129">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="a422c-129">7/3/2012</span></span></p>
<p><span data-ttu-id="a422c-130">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="a422c-130">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a422c-131"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="a422c-131"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="a422c-p106">注册器池或边缘服务器的完全限定域名 (FQDN)。可以选择单个池，也可以单击“[所有]”<strong></strong>查看所有池的数据。系统根据数据库中的记录自动为您填充该下拉列表。</span><span class="sxs-lookup"><span data-stu-id="a422c-p106">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="a422c-135">指标</span><span class="sxs-lookup"><span data-stu-id="a422c-135">Metrics</span></span>

<span data-ttu-id="a422c-136">下表列出了 P2P 摘要子报表中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="a422c-136">The following table lists the information provided in the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-metrics"></a><span data-ttu-id="a422c-137">P2P 摘要子报告指标</span><span class="sxs-lookup"><span data-stu-id="a422c-137">P2P Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a422c-138">名称</span><span class="sxs-lookup"><span data-stu-id="a422c-138">Name</span></span></th>
<th><span data-ttu-id="a422c-139">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="a422c-139">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a422c-140">说明</span><span class="sxs-lookup"><span data-stu-id="a422c-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a422c-141"><strong>会话总数</strong></span><span class="sxs-lookup"><span data-stu-id="a422c-141"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="a422c-142">否</span><span class="sxs-lookup"><span data-stu-id="a422c-142">No</span></span></p></td>
<td><p><span data-ttu-id="a422c-143">会话的总数，包括成功的会话、失败的会话（预期失败和意外失败）及未归类的会话。</span><span class="sxs-lookup"><span data-stu-id="a422c-143">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a422c-144"><strong>故障率</strong></span><span class="sxs-lookup"><span data-stu-id="a422c-144"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="a422c-145">否</span><span class="sxs-lookup"><span data-stu-id="a422c-145">No</span></span></p></td>
<td><p><span data-ttu-id="a422c-146">失败的点对点会话百分比。</span><span class="sxs-lookup"><span data-stu-id="a422c-146">Percentage of peer-to-peer sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a422c-147"><strong>按形式列出的会话</strong></span><span class="sxs-lookup"><span data-stu-id="a422c-147"><strong>Sessions by Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="a422c-148">否</span><span class="sxs-lookup"><span data-stu-id="a422c-148">No</span></span></p></td>
<td><p><span data-ttu-id="a422c-149">按形式分组的会话总数（例如，即时消息）。</span><span class="sxs-lookup"><span data-stu-id="a422c-149">Total number of sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a422c-150"><strong>按形式列出的故障率</strong></span><span class="sxs-lookup"><span data-stu-id="a422c-150"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="a422c-151">否</span><span class="sxs-lookup"><span data-stu-id="a422c-151">No</span></span></p></td>
<td><p><span data-ttu-id="a422c-152">按形式分组的失败会话总数（例如，即时消息）。</span><span class="sxs-lookup"><span data-stu-id="a422c-152">Total number of failed sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

