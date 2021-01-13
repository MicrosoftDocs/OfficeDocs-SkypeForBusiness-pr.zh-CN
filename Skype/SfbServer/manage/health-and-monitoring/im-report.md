---
title: Skype for Business Server 中的对等 IM 报告
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
ms.assetid: 19ec0145-2398-437b-8989-f780c179b798
description: 摘要：了解 Skype for Business Server 中的对等 IM 报告。
ms.openlocfilehash: 1962d2d39ce23b6cdfeaedf7db6a3ada3b1e8eab
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823492"
---
# <a name="peer-to-peer-im-report-in-skype-for-business-server"></a><span data-ttu-id="146a7-103">Skype for Business Server 中的对等 IM 报告</span><span class="sxs-lookup"><span data-stu-id="146a7-103">Peer-to-Peer IM Report in Skype for Business Server</span></span>
 
<span data-ttu-id="146a7-104">**摘要：** 了解 Skype for Business Server 中的对等 IM 报告。</span><span class="sxs-lookup"><span data-stu-id="146a7-104">**Summary:** Learn about the Peer-to-Peer IM Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="146a7-p101">对等 IM 报告提供了有关按池和身份验证类型分类的对等即时消息 (IM) 会话的趋势信息。该报告可以显示在指定时间段内（例如，每天或每小时）进行的会话总数或显示在该时间段内发送的即时消息总数。</span><span class="sxs-lookup"><span data-stu-id="146a7-p101">The Peer-to-Peer IM Report provides trend information about peer-to-peer instant messaging (IM) sessions, broken down by pool and by authentication type. The report can show either the total number of sessions held during the specified time period (for example, day-by-day or hour-by-hour), or it can show the total number of instant messages sent during that time period.</span></span>
  
## <a name="accessing-the-peer-to-peer-im-report"></a><span data-ttu-id="146a7-107">访问对等 IM 报告</span><span class="sxs-lookup"><span data-stu-id="146a7-107">Accessing the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="146a7-108">只有打开 [Skype for Business Server](peer-to-peer-activity-summary-report.md) 中的对等活动摘要报告，然后单击以下指标之一，才能访问对等 IM 报告：</span><span class="sxs-lookup"><span data-stu-id="146a7-108">You can access the Peer-to-Peer IM Report only by opening the [Peer-to-Peer Activity Summary Report in Skype for Business Server](peer-to-peer-activity-summary-report.md) and then clicking either of the following metrics:</span></span>
  
- <span data-ttu-id="146a7-109">对等 IM 会话总数</span><span class="sxs-lookup"><span data-stu-id="146a7-109">Total peer-to-peer IM sessions</span></span>
    
- <span data-ttu-id="146a7-110">对等 IM 消息总数</span><span class="sxs-lookup"><span data-stu-id="146a7-110">Total peer-to-peer IM messages</span></span>
    
## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a><span data-ttu-id="146a7-111">充分利用对等 IM 报告</span><span class="sxs-lookup"><span data-stu-id="146a7-111">Making the Best Use of the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="146a7-p102">默认情况下，对等 IM 报告显示每小时（或每天，具体取决于设置）的消息计数。但是，还可以选择按每小时会话数来查看日期。为此，请单击“报告”窗口右上角的“隐藏/显示参数”，然后从“报告依据”列表中单击“会话计数”。</span><span class="sxs-lookup"><span data-stu-id="146a7-p102">By default, the Peer-to-Peer IM Report shows you the message count per-hour (or day, depending on your settings). However, you can also choose to view the day by sessions per hour. To do that, click **Hide/Show Parameters** in the upper-right corner of the Reports window, and then click **Session Count** from the **Report by** list.</span></span>
  
## <a name="filters"></a><span data-ttu-id="146a7-115">筛选器</span><span class="sxs-lookup"><span data-stu-id="146a7-115">Filters</span></span>

<span data-ttu-id="146a7-p103">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。下表列出了可用于对等 IM 报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="146a7-p103">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Peer-to-Peer IM Report.</span></span>
  
<span data-ttu-id="146a7-118">**点对点 IM 报告筛选器**</span><span class="sxs-lookup"><span data-stu-id="146a7-118">**Peer-to-Peer IM Report Filters**</span></span>

|<span data-ttu-id="146a7-119">**名称**</span><span class="sxs-lookup"><span data-stu-id="146a7-119">**Name**</span></span>|<span data-ttu-id="146a7-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="146a7-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="146a7-121">**From**</span><span class="sxs-lookup"><span data-stu-id="146a7-121">**From**</span></span> <br/> |<span data-ttu-id="146a7-p104">时间范围的开始日期和时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="146a7-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span>  <br/> <span data-ttu-id="146a7-124">7/7/2015 1：00 PM</span><span class="sxs-lookup"><span data-stu-id="146a7-124">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="146a7-p105">如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="146a7-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="146a7-127">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="146a7-127">7/7/2015</span></span>  <br/> <span data-ttu-id="146a7-128">若要按周或按月查看，请输入周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="146a7-128">To view by week or by month, enter a date that falls anywhere within the week or month (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="146a7-129">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="146a7-129">7/3/2015</span></span>  <br/> <span data-ttu-id="146a7-130">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="146a7-130">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="146a7-131">"自"</span><span class="sxs-lookup"><span data-stu-id="146a7-131">**To**</span></span> <br/> |<span data-ttu-id="146a7-p106">时间范围的结束日期和时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="146a7-p106">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span>  <br/> <span data-ttu-id="146a7-134">7/7/2015 1：00 PM</span><span class="sxs-lookup"><span data-stu-id="146a7-134">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="146a7-p107">如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="146a7-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="146a7-137">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="146a7-137">7/7/2015</span></span>  <br/> <span data-ttu-id="146a7-138">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="146a7-138">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="146a7-139">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="146a7-139">7/3/2015</span></span>  <br/> <span data-ttu-id="146a7-140">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="146a7-140">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="146a7-141">**Interval**</span><span class="sxs-lookup"><span data-stu-id="146a7-141">**Interval**</span></span> <br/> | <span data-ttu-id="146a7-p108">时间间隔。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="146a7-p108">Time interval. Select one of the following:</span></span> <br/>  <span data-ttu-id="146a7-144">每小时（最多可显示 25 个小时）</span><span class="sxs-lookup"><span data-stu-id="146a7-144">Hourly (a maximum of 25 hours can be displayed)</span></span> <br/>  <span data-ttu-id="146a7-145">每天（最多可显示 31 天）</span><span class="sxs-lookup"><span data-stu-id="146a7-145">Daily (a maximum of 31 days can be displayed)</span></span> <br/>  <span data-ttu-id="146a7-146">每周（最多可显示 12 周）</span><span class="sxs-lookup"><span data-stu-id="146a7-146">Weekly (a maximum of 12 weeks can be displayed)</span></span> <br/>  <span data-ttu-id="146a7-147">每月（最多可显示 12 个月）</span><span class="sxs-lookup"><span data-stu-id="146a7-147">Monthly (a maximum of 12 months can be displayed)</span></span> <br/>  <span data-ttu-id="146a7-148">如果开始日期和结束日期超出了所选间隔允许的最大值数，则仅显示最大值数（从开始日期开始）。</span><span class="sxs-lookup"><span data-stu-id="146a7-148">If the start and end dates exceed the maximum number of values allowed for the selected interval then only the maximum number of values (starting from the start date) are displayed.</span></span> <span data-ttu-id="146a7-149">例如，如果您选择开始日期为 2015/7/7、结束日期为 2/28/2015 的"每天"间隔， 数据显示在 2015 年 8 月 7 日上午 12：00 到 2015 年 9 月 7 日上午 12：00 (即总共 31 天的数据) 。</span><span class="sxs-lookup"><span data-stu-id="146a7-149">For example, if you select the Daily interval with a start date of 7/7/2015 and an end date of 2/28/2015, data is displayed for the days 8/7/2015 12:00 AM to 9/7/2015 12:00 AM (that is, a total of 31 days' worth of data).</span></span> <br/> |
|<span data-ttu-id="146a7-150">**报告依据**</span><span class="sxs-lookup"><span data-stu-id="146a7-150">**Report by**</span></span> <br/> | <span data-ttu-id="146a7-p110">指示要在报告中使用的值。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="146a7-p110">Indicates the values to be used in the report. Select one of the following:</span></span> <br/>  <span data-ttu-id="146a7-153">会话计数</span><span class="sxs-lookup"><span data-stu-id="146a7-153">Session count</span></span> <br/>  <span data-ttu-id="146a7-154">消息计数</span><span class="sxs-lookup"><span data-stu-id="146a7-154">Message count</span></span> <br/> |
   
## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a><span data-ttu-id="146a7-155">按池列出的点对点 IM 会话的指标</span><span class="sxs-lookup"><span data-stu-id="146a7-155">Metrics for Peer-to-Peer IM Session by Pool</span></span>

<span data-ttu-id="146a7-156">下表列出了点对点 IM 报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="146a7-156">The following table lists the information provided in the Peer-to-Peer IM Report.</span></span>
  
<span data-ttu-id="146a7-157">**按池列出的点对点 IM 会话的指标**</span><span class="sxs-lookup"><span data-stu-id="146a7-157">**Metrics for Peer-to-Peer IM Session by Pool**</span></span>

|<span data-ttu-id="146a7-158">**名称**</span><span class="sxs-lookup"><span data-stu-id="146a7-158">**Name**</span></span>|<span data-ttu-id="146a7-159">**是否可按此项排序？**</span><span class="sxs-lookup"><span data-stu-id="146a7-159">**Can you sort on this item?**</span></span>|<span data-ttu-id="146a7-160">**说明**</span><span class="sxs-lookup"><span data-stu-id="146a7-160">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="146a7-161">**Pool**</span><span class="sxs-lookup"><span data-stu-id="146a7-161">**Pool**</span></span> <br/> |<span data-ttu-id="146a7-162">否</span><span class="sxs-lookup"><span data-stu-id="146a7-162">No</span></span>  <br/> |<span data-ttu-id="146a7-163">注册器池或边缘服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="146a7-163">Name of the Registrar pool or Edge Server.</span></span>  <br/> |
|<span data-ttu-id="146a7-164">**日期/时间**</span><span class="sxs-lookup"><span data-stu-id="146a7-164">**Date/Time**</span></span> <br/> |<span data-ttu-id="146a7-165">否</span><span class="sxs-lookup"><span data-stu-id="146a7-165">No</span></span>  <br/> |<span data-ttu-id="146a7-166">会话发生的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="146a7-166">Date and time that the sessions took place.</span></span>  <br/> |
|<span data-ttu-id="146a7-167">**Total**</span><span class="sxs-lookup"><span data-stu-id="146a7-167">**Total**</span></span> <br/> |<span data-ttu-id="146a7-168">否</span><span class="sxs-lookup"><span data-stu-id="146a7-168">No</span></span>  <br/> |<span data-ttu-id="146a7-169">会话总数或消息总数。</span><span class="sxs-lookup"><span data-stu-id="146a7-169">Total number of sessions or total message count.</span></span>  <br/> |
   
## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a><span data-ttu-id="146a7-170">按身份验证类型列出的点对点 IM 会话的指标</span><span class="sxs-lookup"><span data-stu-id="146a7-170">Metrics for Peer-to-Peer IM Session by Authentication Type</span></span>

<span data-ttu-id="146a7-171">下表列出了点对点会话中的参与者所用各个身份验证类型的点对点 IM 报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="146a7-171">The following table lists the information provided in the Peer-to-Peer IM Report for each type of authentication used by the participants in a peer-to-peer session.</span></span>
  
<span data-ttu-id="146a7-172">**按身份验证类型列出的点对点 IM 会话的指标**</span><span class="sxs-lookup"><span data-stu-id="146a7-172">**Metrics for Peer-to-Peer IM Session by Authentication Type**</span></span>

|<span data-ttu-id="146a7-173">**名称**</span><span class="sxs-lookup"><span data-stu-id="146a7-173">**Name**</span></span>|<span data-ttu-id="146a7-174">**是否可按此项排序？**</span><span class="sxs-lookup"><span data-stu-id="146a7-174">**Can you sort on this item?**</span></span>|<span data-ttu-id="146a7-175">**说明**</span><span class="sxs-lookup"><span data-stu-id="146a7-175">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="146a7-176">**身份验证类型**</span><span class="sxs-lookup"><span data-stu-id="146a7-176">**Authentication type**</span></span> <br/> |<span data-ttu-id="146a7-177">否</span><span class="sxs-lookup"><span data-stu-id="146a7-177">No</span></span>  <br/> | <span data-ttu-id="146a7-p111">会话参与者使用的身份验证的类型。通常可指定下列值之一：</span><span class="sxs-lookup"><span data-stu-id="146a7-p111">Type of authentication used by the session participants. Values are typically one of the following:</span></span> <br/>  <span data-ttu-id="146a7-180">企业版</span><span class="sxs-lookup"><span data-stu-id="146a7-180">Enterprise</span></span> <br/>  <span data-ttu-id="146a7-181">联合</span><span class="sxs-lookup"><span data-stu-id="146a7-181">Federated</span></span> <br/>  <span data-ttu-id="146a7-182">PIC</span><span class="sxs-lookup"><span data-stu-id="146a7-182">PIC</span></span> <br/> |
|<span data-ttu-id="146a7-183">**日期/时间**</span><span class="sxs-lookup"><span data-stu-id="146a7-183">**Date/Time**</span></span> <br/> |<span data-ttu-id="146a7-184">否</span><span class="sxs-lookup"><span data-stu-id="146a7-184">No</span></span>  <br/> |<span data-ttu-id="146a7-185">会话发生的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="146a7-185">Date and time that the sessions took place.</span></span>  <br/> |
|<span data-ttu-id="146a7-186">**Total**</span><span class="sxs-lookup"><span data-stu-id="146a7-186">**Total**</span></span> <br/> |<span data-ttu-id="146a7-187">否</span><span class="sxs-lookup"><span data-stu-id="146a7-187">No</span></span>  <br/> |<span data-ttu-id="146a7-188">会话总数或消息总数。</span><span class="sxs-lookup"><span data-stu-id="146a7-188">Total number of sessions or total message count.</span></span>  <br/> |
   

