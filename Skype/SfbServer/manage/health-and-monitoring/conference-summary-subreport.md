---
title: Skype for Business Server 中的会议摘要子报告
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2fc1d2bf-34f5-4093-a6e2-250ec1f1b004
description: 摘要：了解 Skype for Business Server 中的会议摘要子报告。
ms.openlocfilehash: 9a42e16bc22f01f196274f1e25396d8516e26af2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826472"
---
# <a name="conference-summary-subreport-in-skype-for-business-server"></a><span data-ttu-id="1120e-103">Skype for Business Server 中的会议摘要子报告</span><span class="sxs-lookup"><span data-stu-id="1120e-103">Conference Summary Subreport in Skype for Business Server</span></span>
 
<span data-ttu-id="1120e-104">**摘要：** 了解 Skype for Business Server 中的会议摘要子报告。</span><span class="sxs-lookup"><span data-stu-id="1120e-104">**Summary:** Learn about the Conference Summary Subreport in Skype for Business Server.</span></span>
  
<span data-ttu-id="1120e-p101">会议摘要子报告提供了失败的会议会话的总体概述。这些失败的会话按以下会话类型进一步细分：焦点会话和 MCU 会话。</span><span class="sxs-lookup"><span data-stu-id="1120e-p101">The Conference Summary Subreport provides an overall view of failed conference sessions. These failed sessions are further broken down by session type: Focus sessions and MCU sessions.</span></span>
  
## <a name="filters"></a><span data-ttu-id="1120e-107">筛选器</span><span class="sxs-lookup"><span data-stu-id="1120e-107">Filters</span></span>

<span data-ttu-id="1120e-p102">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。下表列出了可用于会议摘要子报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="1120e-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Summary Subreport.</span></span>
  
<span data-ttu-id="1120e-110">**会议摘要子报告筛选器**</span><span class="sxs-lookup"><span data-stu-id="1120e-110">**Conference Summary Subreport Filters**</span></span>

|<span data-ttu-id="1120e-111">**名称**</span><span class="sxs-lookup"><span data-stu-id="1120e-111">**Name**</span></span>|<span data-ttu-id="1120e-112">**说明**</span><span class="sxs-lookup"><span data-stu-id="1120e-112">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1120e-113">**From**</span><span class="sxs-lookup"><span data-stu-id="1120e-113">**From**</span></span> <br/> |<span data-ttu-id="1120e-p103">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1120e-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span>  <br/> <span data-ttu-id="1120e-116">7/7/2015 1：00 PM</span><span class="sxs-lookup"><span data-stu-id="1120e-116">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="1120e-p104">如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="1120e-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="1120e-119">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="1120e-119">7/7/2015</span></span>  <br/> <span data-ttu-id="1120e-120">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="1120e-120">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="1120e-121">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="1120e-121">7/3/2015</span></span>  <br/> <span data-ttu-id="1120e-122">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="1120e-122">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="1120e-123">"自"</span><span class="sxs-lookup"><span data-stu-id="1120e-123">**To**</span></span> <br/> |<span data-ttu-id="1120e-p105">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1120e-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span>  <br/> <span data-ttu-id="1120e-126">7/7/2015 1：00 PM</span><span class="sxs-lookup"><span data-stu-id="1120e-126">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="1120e-p106">如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="1120e-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="1120e-129">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="1120e-129">7/7/2015</span></span>  <br/> <span data-ttu-id="1120e-130">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="1120e-130">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="1120e-131">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="1120e-131">7/3/2015</span></span>  <br/> <span data-ttu-id="1120e-132">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="1120e-132">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="1120e-133">**Pool**</span><span class="sxs-lookup"><span data-stu-id="1120e-133">**Pool**</span></span> <br/> |<span data-ttu-id="1120e-p107">注册器池或边缘服务器的完全限定域名 (FQDN)。可以选择单个池，也可以单击“[所有]”查看所有池的数据。系统根据数据库中的记录自动为您填充该下拉列表。</span><span class="sxs-lookup"><span data-stu-id="1120e-p107">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click **[All]** to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database. </span></span><br/> |
   
## <a name="metrics"></a><span data-ttu-id="1120e-137">指标</span><span class="sxs-lookup"><span data-stu-id="1120e-137">Metrics</span></span>

<span data-ttu-id="1120e-138">下表列出了会议摘要子报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="1120e-138">The following table lists the information provided in the Conference Summary Subreport.</span></span>
  
<span data-ttu-id="1120e-139">**会议摘要子报告指标**</span><span class="sxs-lookup"><span data-stu-id="1120e-139">**Conference Summary Subreport Metrics**</span></span>

|<span data-ttu-id="1120e-140">**名称**</span><span class="sxs-lookup"><span data-stu-id="1120e-140">**Name**</span></span>|<span data-ttu-id="1120e-141">**是否可按此项排序？**</span><span class="sxs-lookup"><span data-stu-id="1120e-141">**Can you sort on this item?**</span></span>|<span data-ttu-id="1120e-142">**说明**</span><span class="sxs-lookup"><span data-stu-id="1120e-142">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1120e-143">**会议总数**</span><span class="sxs-lookup"><span data-stu-id="1120e-143">**Total conferences**</span></span> <br/> |<span data-ttu-id="1120e-144">否</span><span class="sxs-lookup"><span data-stu-id="1120e-144">No</span></span>  <br/> |<span data-ttu-id="1120e-145">举行的会议总数。</span><span class="sxs-lookup"><span data-stu-id="1120e-145">Total number of conferences held.</span></span>  <br/> |
|<span data-ttu-id="1120e-146">**会议会话总数**</span><span class="sxs-lookup"><span data-stu-id="1120e-146">**Total conference sessions**</span></span> <br/> |<span data-ttu-id="1120e-147">否</span><span class="sxs-lookup"><span data-stu-id="1120e-147">No</span></span>  <br/> |<span data-ttu-id="1120e-p108">会议会话总数。单个会议可以具有多个会话；例如，会议可能同时包括焦点会话和 MCU 会话。</span><span class="sxs-lookup"><span data-stu-id="1120e-p108">Total number of conference sessions. A single conference can have multiple sessions; for example, a conference might include both a Focus session and an MCU session.</span></span>  <br/> |
|<span data-ttu-id="1120e-150">**总体会话故障率**</span><span class="sxs-lookup"><span data-stu-id="1120e-150">**Overall session failure rate**</span></span> <br/> |<span data-ttu-id="1120e-151">否</span><span class="sxs-lookup"><span data-stu-id="1120e-151">No</span></span>  <br/> |<span data-ttu-id="1120e-152">所有失败会议的百分比。</span><span class="sxs-lookup"><span data-stu-id="1120e-152">Percentage of all conferences that failed.</span></span>  <br/> |
|<span data-ttu-id="1120e-153">**焦点会话**</span><span class="sxs-lookup"><span data-stu-id="1120e-153">**Focus sessions**</span></span> <br/> |<span data-ttu-id="1120e-154">否</span><span class="sxs-lookup"><span data-stu-id="1120e-154">No</span></span>  <br/> |<span data-ttu-id="1120e-155">焦点会话总数。</span><span class="sxs-lookup"><span data-stu-id="1120e-155">Total number of Focus sessions.</span></span>  <br/> |
|<span data-ttu-id="1120e-156">**焦点故障率**</span><span class="sxs-lookup"><span data-stu-id="1120e-156">**Focus failure rate**</span></span> <br/> |<span data-ttu-id="1120e-157">否</span><span class="sxs-lookup"><span data-stu-id="1120e-157">No</span></span>  <br/> |<span data-ttu-id="1120e-158">失败的焦点会话的百分比。</span><span class="sxs-lookup"><span data-stu-id="1120e-158">Percentage of Focus sessions that failed.</span></span>  <br/> |
|<span data-ttu-id="1120e-159">MCU 会话</span><span class="sxs-lookup"><span data-stu-id="1120e-159">MCU sessions</span></span>  <br/> |<span data-ttu-id="1120e-160">否</span><span class="sxs-lookup"><span data-stu-id="1120e-160">No</span></span>  <br/> |<span data-ttu-id="1120e-161">MCU 会话总数。
</span><span class="sxs-lookup"><span data-stu-id="1120e-161">Total number of MCU sessions.</span></span>  <br/> |
|<span data-ttu-id="1120e-162">**MCU 故障率**</span><span class="sxs-lookup"><span data-stu-id="1120e-162">**MCU failure rate**</span></span> <br/> |<span data-ttu-id="1120e-163">否</span><span class="sxs-lookup"><span data-stu-id="1120e-163">No</span></span>  <br/> |<span data-ttu-id="1120e-164">失败的 MCU 会话的百分比。</span><span class="sxs-lookup"><span data-stu-id="1120e-164">Percentage of MCU sessions that failed.</span></span>  <br/> |
|<span data-ttu-id="1120e-165">**按形式列出的 MCU 会话**</span><span class="sxs-lookup"><span data-stu-id="1120e-165">**MCU sessions by modality**</span></span> <br/> |<span data-ttu-id="1120e-166">否</span><span class="sxs-lookup"><span data-stu-id="1120e-166">No</span></span>  <br/> |<span data-ttu-id="1120e-167">按形式分组的 MCU 会话总数（例如，IM 会议）。</span><span class="sxs-lookup"><span data-stu-id="1120e-167">Total number of MCU sessions, grouped by modality (for example, IM conferencing).</span></span>  <br/> |
|<span data-ttu-id="1120e-168">**按形式列出的故障率**</span><span class="sxs-lookup"><span data-stu-id="1120e-168">**Failure rate by modality**</span></span> <br/> |<span data-ttu-id="1120e-169">否</span><span class="sxs-lookup"><span data-stu-id="1120e-169">No</span></span>  <br/> |<span data-ttu-id="1120e-170">按形式分组的失败的 MCU 会话的百分比（例如，IM 会议）。</span><span class="sxs-lookup"><span data-stu-id="1120e-170">Percentage of MCU sessions that failed, grouped by modality (for example, IM conferencing).</span></span>  <br/> |
   

