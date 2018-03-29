---
title: Skype for Business Server 2015 中的 P2P 摘要子报告
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
description: 摘要： 了解业务服务器 2015年的 Skype P2P 摘要子报表。
ms.openlocfilehash: db610f21eda9b4decd01facf55f69699c48aa9f2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="p2p-summary-subreport-in-skype-for-business-server-2015"></a><span data-ttu-id="9ce4f-103">Skype for Business Server 2015 中的 P2P 摘要子报告</span><span class="sxs-lookup"><span data-stu-id="9ce4f-103">P2P Summary Subreport in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9ce4f-104">**摘要：**了解业务服务器 2015 Skype P2P 摘要子报表。</span><span class="sxs-lookup"><span data-stu-id="9ce4f-104">**Summary:** Learn about the P2P Summary Subreport in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="9ce4f-105">P2P 摘要子报表对失败对等通信会话提供一个总体视图。</span><span class="sxs-lookup"><span data-stu-id="9ce4f-105">The P2P Summary Subreport provides an overall view of your failed peer-to-peer communication sessions.</span></span>
  
## <a name="filters"></a><span data-ttu-id="9ce4f-106">筛选器</span><span class="sxs-lookup"><span data-stu-id="9ce4f-106">Filters</span></span>

<span data-ttu-id="9ce4f-p101">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。下表列出了可用于 P2P 摘要子报表的筛选器。</span><span class="sxs-lookup"><span data-stu-id="9ce4f-p101">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the P2P Summary Subreport.</span></span>
  
<span data-ttu-id="9ce4f-109">**P2P 摘要子报表筛选器**</span><span class="sxs-lookup"><span data-stu-id="9ce4f-109">**P2P Summary Subreport Filters**</span></span>

|<span data-ttu-id="9ce4f-110">**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="9ce4f-110">**Name**</span></span>|<span data-ttu-id="9ce4f-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="9ce4f-111">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9ce4f-112">**从**</span><span class="sxs-lookup"><span data-stu-id="9ce4f-112">**From**</span></span> <br/> |<span data-ttu-id="9ce4f-p102">时间范围的开始日期和时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="9ce4f-p102">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span>  <br/> <span data-ttu-id="9ce4f-115">2015/7/7 13:00</span><span class="sxs-lookup"><span data-stu-id="9ce4f-115">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="9ce4f-p103">如果您未输入开始时间，该报告会自动将将某个特定日期的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="9ce4f-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="9ce4f-118">2015/7/7</span><span class="sxs-lookup"><span data-stu-id="9ce4f-118">7/7/2015</span></span>  <br/> <span data-ttu-id="9ce4f-119">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="9ce4f-119">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="9ce4f-120">2015/7/3</span><span class="sxs-lookup"><span data-stu-id="9ce4f-120">7/3/2015</span></span>  <br/> <span data-ttu-id="9ce4f-121">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="9ce4f-121">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="9ce4f-122">**到**</span><span class="sxs-lookup"><span data-stu-id="9ce4f-122">**To**</span></span> <br/> |<span data-ttu-id="9ce4f-p104">时间范围的结束日期和时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="9ce4f-p104">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span>  <br/> <span data-ttu-id="9ce4f-125">2015/7/7 13:00</span><span class="sxs-lookup"><span data-stu-id="9ce4f-125">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="9ce4f-p105">如果您未输入结束时间，该报告会自动将某个特定日期的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="9ce4f-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="9ce4f-128">2015/7/7</span><span class="sxs-lookup"><span data-stu-id="9ce4f-128">7/7/2015</span></span>  <br/> <span data-ttu-id="9ce4f-129">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="9ce4f-129">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="9ce4f-130">2015/7/3</span><span class="sxs-lookup"><span data-stu-id="9ce4f-130">7/3/2015</span></span>  <br/> <span data-ttu-id="9ce4f-131">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="9ce4f-131">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="9ce4f-132">**池**</span><span class="sxs-lookup"><span data-stu-id="9ce4f-132">**Pool**</span></span> <br/> |<span data-ttu-id="9ce4f-p106">注册器池或边缘服务器的完全限定域名 (FQDN)。可以选择单个池，也可以单击“**[所有]**”查看所有池的数据。系统根据数据库中的记录自动为您填充该下拉列表。</span><span class="sxs-lookup"><span data-stu-id="9ce4f-p106">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click **[All]** to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database. </span></span><br/> |
   
## <a name="metrics"></a><span data-ttu-id="9ce4f-136">指标</span><span class="sxs-lookup"><span data-stu-id="9ce4f-136">Metrics</span></span>

<span data-ttu-id="9ce4f-137">下表列出了 P2P 摘要子报表中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="9ce4f-137">The following table lists the information provided in the P2P Summary Subreport.</span></span>
  
<span data-ttu-id="9ce4f-138">**P2P 摘要子报表指标**</span><span class="sxs-lookup"><span data-stu-id="9ce4f-138">**P2P Summary Subreport Metrics**</span></span>

|<span data-ttu-id="9ce4f-139">**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="9ce4f-139">**Name**</span></span>|<span data-ttu-id="9ce4f-140">**可以在此项上进行排序？**</span><span class="sxs-lookup"><span data-stu-id="9ce4f-140">**Can you sort on this item?**</span></span>|<span data-ttu-id="9ce4f-141">**说明**</span><span class="sxs-lookup"><span data-stu-id="9ce4f-141">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9ce4f-142">**会话总数**</span><span class="sxs-lookup"><span data-stu-id="9ce4f-142">**Total sessions**</span></span> <br/> |<span data-ttu-id="9ce4f-143">否</span><span class="sxs-lookup"><span data-stu-id="9ce4f-143">No</span></span>  <br/> |<span data-ttu-id="9ce4f-144">会话的总数，包括成功的会话、失败的会话（预期失败和意外失败）及未归类的会话。</span><span class="sxs-lookup"><span data-stu-id="9ce4f-144">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span>  <br/> |
|<span data-ttu-id="9ce4f-145">**故障率**</span><span class="sxs-lookup"><span data-stu-id="9ce4f-145">**Failure rate**</span></span> <br/> |<span data-ttu-id="9ce4f-146">否</span><span class="sxs-lookup"><span data-stu-id="9ce4f-146">No</span></span>  <br/> |<span data-ttu-id="9ce4f-147">失败的对等会话百分比。</span><span class="sxs-lookup"><span data-stu-id="9ce4f-147">Percentage of peer-to-peer sessions that failed.</span></span>  <br/> |
|<span data-ttu-id="9ce4f-148">**按形式列出的会话**</span><span class="sxs-lookup"><span data-stu-id="9ce4f-148">**Sessions by Modality**</span></span> <br/> |<span data-ttu-id="9ce4f-149">否</span><span class="sxs-lookup"><span data-stu-id="9ce4f-149">No</span></span>  <br/> |<span data-ttu-id="9ce4f-150">按形式分组的会话总数（例如，即时消息）。</span><span class="sxs-lookup"><span data-stu-id="9ce4f-150">Total number of sessions grouped by modality (for example, instant messaging).</span></span>  <br/> |
|<span data-ttu-id="9ce4f-151">**按形式列出的故障率**</span><span class="sxs-lookup"><span data-stu-id="9ce4f-151">**Failure rate by modality**</span></span> <br/> |<span data-ttu-id="9ce4f-152">否</span><span class="sxs-lookup"><span data-stu-id="9ce4f-152">No</span></span>  <br/> |<span data-ttu-id="9ce4f-153">按形式分组的失败会话总数（例如，即时消息）。</span><span class="sxs-lookup"><span data-stu-id="9ce4f-153">Total number of failed sessions grouped by modality (for example, instant messaging).</span></span>  <br/> |
   

