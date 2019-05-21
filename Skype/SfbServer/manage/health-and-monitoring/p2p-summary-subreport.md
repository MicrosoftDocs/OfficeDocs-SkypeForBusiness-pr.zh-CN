---
title: Skype for Business 服务器中的 P2P 摘要子报表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
description: '摘要: 了解 Skype for Business 服务器中的 P2P 摘要子报告。'
ms.openlocfilehash: 5238e910896a6af956285235d7e1234fe17fe005
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279912"
---
# <a name="p2p-summary-subreport-in-skype-for-business-server"></a><span data-ttu-id="13481-103">Skype for Business 服务器中的 P2P 摘要子报表</span><span class="sxs-lookup"><span data-stu-id="13481-103">P2P Summary Subreport in Skype for Business Server</span></span>
 
<span data-ttu-id="13481-104">**摘要:** 了解 Skype for Business 服务器中的 P2P 摘要子报告。</span><span class="sxs-lookup"><span data-stu-id="13481-104">**Summary:** Learn about the P2P Summary Subreport in Skype for Business Server.</span></span>
  
<span data-ttu-id="13481-105">P2P 摘要子报表对失败对等通信会话提供一个总体视图。</span><span class="sxs-lookup"><span data-stu-id="13481-105">The P2P Summary Subreport provides an overall view of your failed peer-to-peer communication sessions.</span></span>
  
## <a name="filters"></a><span data-ttu-id="13481-106">筛选器</span><span class="sxs-lookup"><span data-stu-id="13481-106">Filters</span></span>

<span data-ttu-id="13481-p101">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。下表列出了可用于 P2P 摘要子报表的筛选器。</span><span class="sxs-lookup"><span data-stu-id="13481-p101">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the P2P Summary Subreport.</span></span>
  
<span data-ttu-id="13481-109">**P2P 摘要子报表筛选器**</span><span class="sxs-lookup"><span data-stu-id="13481-109">**P2P Summary Subreport Filters**</span></span>

|<span data-ttu-id="13481-110">**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="13481-110">**Name**</span></span>|<span data-ttu-id="13481-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="13481-111">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="13481-112">**从**</span><span class="sxs-lookup"><span data-stu-id="13481-112">**From**</span></span> <br/> |<span data-ttu-id="13481-p102">时间范围的开始日期和时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="13481-p102">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span>  <br/> <span data-ttu-id="13481-115">2015/7/7 13:00</span><span class="sxs-lookup"><span data-stu-id="13481-115">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="13481-p103">如果您未输入开始时间，该报告会自动将将某个特定日期的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="13481-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="13481-118">2015/7/7</span><span class="sxs-lookup"><span data-stu-id="13481-118">7/7/2015</span></span>  <br/> <span data-ttu-id="13481-119">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="13481-119">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="13481-120">2015/7/3</span><span class="sxs-lookup"><span data-stu-id="13481-120">7/3/2015</span></span>  <br/> <span data-ttu-id="13481-121">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="13481-121">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="13481-122">**到**</span><span class="sxs-lookup"><span data-stu-id="13481-122">**To**</span></span> <br/> |<span data-ttu-id="13481-p104">时间范围的结束日期和时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="13481-p104">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span>  <br/> <span data-ttu-id="13481-125">2015/7/7 13:00</span><span class="sxs-lookup"><span data-stu-id="13481-125">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="13481-p105">如果您未输入结束时间，该报告会自动将某个特定日期的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="13481-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="13481-128">2015/7/7</span><span class="sxs-lookup"><span data-stu-id="13481-128">7/7/2015</span></span>  <br/> <span data-ttu-id="13481-129">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="13481-129">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="13481-130">2015/7/3</span><span class="sxs-lookup"><span data-stu-id="13481-130">7/3/2015</span></span>  <br/> <span data-ttu-id="13481-131">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="13481-131">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="13481-132">**池**</span><span class="sxs-lookup"><span data-stu-id="13481-132">**Pool**</span></span> <br/> |<span data-ttu-id="13481-p106">注册器池或边缘服务器的完全限定域名 (FQDN)。可以选择单个池，也可以单击“**[所有]**”查看所有池的数据。系统根据数据库中的记录自动为您填充该下拉列表。</span><span class="sxs-lookup"><span data-stu-id="13481-p106">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click **[All]** to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database. </span></span><br/> |
   
## <a name="metrics"></a><span data-ttu-id="13481-136">指标</span><span class="sxs-lookup"><span data-stu-id="13481-136">Metrics</span></span>

<span data-ttu-id="13481-137">下表列出了 P2P 摘要子报表中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="13481-137">The following table lists the information provided in the P2P Summary Subreport.</span></span>
  
<span data-ttu-id="13481-138">**P2P 摘要子报告指标**</span><span class="sxs-lookup"><span data-stu-id="13481-138">**P2P Summary Subreport Metrics**</span></span>

|<span data-ttu-id="13481-139">**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="13481-139">**Name**</span></span>|<span data-ttu-id="13481-140">**是否可按此项排序？**</span><span class="sxs-lookup"><span data-stu-id="13481-140">**Can you sort on this item?**</span></span>|<span data-ttu-id="13481-141">**说明**</span><span class="sxs-lookup"><span data-stu-id="13481-141">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="13481-142">**会话总数**</span><span class="sxs-lookup"><span data-stu-id="13481-142">**Total sessions**</span></span> <br/> |<span data-ttu-id="13481-143">否</span><span class="sxs-lookup"><span data-stu-id="13481-143">No</span></span>  <br/> |<span data-ttu-id="13481-144">会话的总数，包括成功的会话、失败的会话（预期失败和意外失败）及未归类的会话。</span><span class="sxs-lookup"><span data-stu-id="13481-144">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span>  <br/> |
|<span data-ttu-id="13481-145">**故障率**</span><span class="sxs-lookup"><span data-stu-id="13481-145">**Failure rate**</span></span> <br/> |<span data-ttu-id="13481-146">否</span><span class="sxs-lookup"><span data-stu-id="13481-146">No</span></span>  <br/> |<span data-ttu-id="13481-147">失败的对等会话百分比。</span><span class="sxs-lookup"><span data-stu-id="13481-147">Percentage of peer-to-peer sessions that failed.</span></span>  <br/> |
|<span data-ttu-id="13481-148">**按形式列出的会话**</span><span class="sxs-lookup"><span data-stu-id="13481-148">**Sessions by Modality**</span></span> <br/> |<span data-ttu-id="13481-149">否</span><span class="sxs-lookup"><span data-stu-id="13481-149">No</span></span>  <br/> |<span data-ttu-id="13481-150">按形式分组的会话总数（例如，即时消息）。</span><span class="sxs-lookup"><span data-stu-id="13481-150">Total number of sessions grouped by modality (for example, instant messaging).</span></span>  <br/> |
|<span data-ttu-id="13481-151">**按形式列出的故障率**</span><span class="sxs-lookup"><span data-stu-id="13481-151">**Failure rate by modality**</span></span> <br/> |<span data-ttu-id="13481-152">否</span><span class="sxs-lookup"><span data-stu-id="13481-152">No</span></span>  <br/> |<span data-ttu-id="13481-153">按形式分组的失败会话总数（例如，即时消息）。</span><span class="sxs-lookup"><span data-stu-id="13481-153">Total number of failed sessions grouped by modality (for example, instant messaging).</span></span>  <br/> |
   

