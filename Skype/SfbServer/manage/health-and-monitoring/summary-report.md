---
title: Skype for Business Server 中的呼叫诊断摘要报告
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
ms.assetid: 9091de56-13e6-440e-9353-f57c10c906fe
description: 摘要：了解 Skype for Business Server 中使用的呼叫诊断摘要报告。
ms.openlocfilehash: a0e024abfc083588a755a0d922c0eca23e526058
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810152"
---
# <a name="call-diagnostic-summary-report-in-skype-for-business-server"></a><span data-ttu-id="7ac5a-103">Skype for Business Server 中的呼叫诊断摘要报告</span><span class="sxs-lookup"><span data-stu-id="7ac5a-103">Call Diagnostic Summary Report in Skype for Business Server</span></span>
 
<span data-ttu-id="7ac5a-104">**摘要：** 了解 Skype for Business Server 中使用的呼叫诊断摘要报告。</span><span class="sxs-lookup"><span data-stu-id="7ac5a-104">**Summary:** Learn about the Call Diagnostic Summary Report used in Skype for Business Server.</span></span>
  
<span data-ttu-id="7ac5a-p101">呼叫诊断摘要报告提供失败的点对点会话和会议会话的整体情况。该报告显示了两种类型的会话的整体故障率，并按以下会话形式类型进一步为故障信息分类：</span><span class="sxs-lookup"><span data-stu-id="7ac5a-p101">The Call Diagnostic Summary Report provides an overall look at failed peer-to-peer and conferencing sessions. The report shows the overall failure rate for both types of sessions, and further breaks the failure information down by session modality type:</span></span>
  
- <span data-ttu-id="7ac5a-107">即时消息</span><span class="sxs-lookup"><span data-stu-id="7ac5a-107">Instant messaging</span></span>
    
- <span data-ttu-id="7ac5a-108">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="7ac5a-108">Application sharing</span></span>
    
- <span data-ttu-id="7ac5a-109">文件传输</span><span class="sxs-lookup"><span data-stu-id="7ac5a-109">File transfer</span></span>
    
- <span data-ttu-id="7ac5a-110">音频</span><span class="sxs-lookup"><span data-stu-id="7ac5a-110">Audio</span></span>
    
- <span data-ttu-id="7ac5a-111">视频</span><span class="sxs-lookup"><span data-stu-id="7ac5a-111">Video</span></span>
    
## <a name="accessing-the-call-diagnostic-summary-report"></a><span data-ttu-id="7ac5a-112">访问呼叫诊断摘要报告</span><span class="sxs-lookup"><span data-stu-id="7ac5a-112">Accessing the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="7ac5a-113">呼叫诊断摘要报告是从监控报告主页访问的。</span><span class="sxs-lookup"><span data-stu-id="7ac5a-113">The Call Diagnostic Summary Report is accessed from the Monitoring Reports Home page.</span></span> <span data-ttu-id="7ac5a-114">从呼叫诊断摘要报告中，可以通过单击报告的"对等会话摘要"部分下的失败率指标来访问 [Skype for Business Server](peer-to-peer-activity-diagnostic-report.md) 中的对等活动诊断报告。</span><span class="sxs-lookup"><span data-stu-id="7ac5a-114">From the Call Diagnostic Summary Report you can access the [Peer-to-Peer Activity Diagnostic Report in Skype for Business Server](peer-to-peer-activity-diagnostic-report.md) by clicking the Failure rate metric under the Peer-to-Peer Session Summary section of the report.</span></span> <span data-ttu-id="7ac5a-115">您还可以通过单击以下任一会议指标来访问 [Skype for Business Server](conference-diagnostic-report.md) 中的会议诊断报告：</span><span class="sxs-lookup"><span data-stu-id="7ac5a-115">You can also access the [Conference Diagnostic Report in Skype for Business Server](conference-diagnostic-report.md) by clicking any of the following conference metrics:</span></span>
  
- <span data-ttu-id="7ac5a-116">总体会话故障率</span><span class="sxs-lookup"><span data-stu-id="7ac5a-116">Overall session failure rate</span></span>
    
- <span data-ttu-id="7ac5a-117">焦点故障率</span><span class="sxs-lookup"><span data-stu-id="7ac5a-117">Focus failure rate</span></span>
    
- <span data-ttu-id="7ac5a-118">MCU 故障率</span><span class="sxs-lookup"><span data-stu-id="7ac5a-118">MCU failure rate</span></span>
    
## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a><span data-ttu-id="7ac5a-119">充分利用呼叫诊断摘要报告</span><span class="sxs-lookup"><span data-stu-id="7ac5a-119">Making the Best Use of the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="7ac5a-120">呼叫诊断摘要报告包括比较 Skype for Business Server 中各种形式故障率的图形。</span><span class="sxs-lookup"><span data-stu-id="7ac5a-120">The Call Diagnostic Summary Report includes graphs that compare failure rates for the various modalities used in Skype for Business Server.</span></span> <span data-ttu-id="7ac5a-121">这些图中的列实际上是热链接;例如，如果你单击对等会话的即时消息列，你将深入到 [Skype for Business Server](peer-to-peer-activity-diagnostic-report.md)中的对等活动诊断报告的实例，该报告提供有关呼叫诊断摘要报告中包括的所有即时消息会话的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="7ac5a-121">The columns in these graphs are actually hotlinks; for example, if you click the Instant messaging column for peer-to-peer sessions, you'll drill down to an instance of the [Peer-to-Peer Activity Diagnostic Report in Skype for Business Server](peer-to-peer-activity-diagnostic-report.md), a report that provides additional details about all the instant messaging sessions included in the Call Diagnostic Summary Report.</span></span>
  
## <a name="filters"></a><span data-ttu-id="7ac5a-122">筛选器</span><span class="sxs-lookup"><span data-stu-id="7ac5a-122">Filters</span></span>

<span data-ttu-id="7ac5a-p104">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，呼叫诊断摘要报告允许您依据会话中使用的注册器池或边缘服务器等条件进行筛选。您还可以选择数据的分组方式。在此示例中，将按小时、天、周或月对呼叫进行分组。</span><span class="sxs-lookup"><span data-stu-id="7ac5a-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Call Diagnostic Summary Report enables you to filter on such things as the Registrar pool or Edge Server used in the session. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>
  
<span data-ttu-id="7ac5a-127">下表列出了可用于呼叫诊断摘要报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="7ac5a-127">The following table lists the filters that you can use with the Call Diagnostic Summary Report.</span></span>
  
<span data-ttu-id="7ac5a-128">**呼叫诊断摘要报告筛选器**</span><span class="sxs-lookup"><span data-stu-id="7ac5a-128">**Call Diagnostic Summary Report Filters**</span></span>

|<span data-ttu-id="7ac5a-129">**名称**</span><span class="sxs-lookup"><span data-stu-id="7ac5a-129">**Name**</span></span>|<span data-ttu-id="7ac5a-130">**说明**</span><span class="sxs-lookup"><span data-stu-id="7ac5a-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7ac5a-131">**From**</span><span class="sxs-lookup"><span data-stu-id="7ac5a-131">**From**</span></span> <br/> |<span data-ttu-id="7ac5a-p105">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7ac5a-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span>  <br/> <span data-ttu-id="7ac5a-134">7/7/2015 1：00 PM</span><span class="sxs-lookup"><span data-stu-id="7ac5a-134">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="7ac5a-p106">如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="7ac5a-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="7ac5a-137">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="7ac5a-137">7/7/2015</span></span>  <br/> <span data-ttu-id="7ac5a-138">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="7ac5a-138">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="7ac5a-139">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="7ac5a-139">7/3/2015</span></span>  <br/> <span data-ttu-id="7ac5a-140">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="7ac5a-140">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="7ac5a-141">"自"</span><span class="sxs-lookup"><span data-stu-id="7ac5a-141">**To**</span></span> <br/> |<span data-ttu-id="7ac5a-p107">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7ac5a-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span>  <br/> <span data-ttu-id="7ac5a-144">7/7/2015 1：00 PM</span><span class="sxs-lookup"><span data-stu-id="7ac5a-144">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="7ac5a-p108">如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="7ac5a-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="7ac5a-147">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="7ac5a-147">7/7/2015</span></span>  <br/> <span data-ttu-id="7ac5a-148">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="7ac5a-148">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="7ac5a-149">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="7ac5a-149">7/3/2015</span></span>  <br/> <span data-ttu-id="7ac5a-150">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="7ac5a-150">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="7ac5a-151">**Interval**</span><span class="sxs-lookup"><span data-stu-id="7ac5a-151">**Interval**</span></span> <br/> | <span data-ttu-id="7ac5a-p109">时间间隔。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="7ac5a-p109">Time interval. Select one of the following:</span></span> <br/>  <span data-ttu-id="7ac5a-154">每小时（最多可显示 25 个小时）</span><span class="sxs-lookup"><span data-stu-id="7ac5a-154">Hourly (a maximum of 25 hours can be displayed)</span></span> <br/>  <span data-ttu-id="7ac5a-155">每天（最多可显示 31 天）</span><span class="sxs-lookup"><span data-stu-id="7ac5a-155">Daily (a maximum of 31 days can be displayed)</span></span> <br/>  <span data-ttu-id="7ac5a-156">每周（最多可显示 12 周）</span><span class="sxs-lookup"><span data-stu-id="7ac5a-156">Weekly (a maximum of 12 weeks can be displayed)</span></span> <br/>  <span data-ttu-id="7ac5a-157">每月（最多可显示 12 个月）</span><span class="sxs-lookup"><span data-stu-id="7ac5a-157">Monthly (a maximum of 12 months can be displayed)</span></span> <br/>  <span data-ttu-id="7ac5a-158">如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。</span><span class="sxs-lookup"><span data-stu-id="7ac5a-158">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="7ac5a-159">例如，如果您选择开始日期为 2015/7/7、结束日期为 2/28/2015 的"每天"间隔， 数据显示在 2015 年 8 月 7 日上午 12：00 到 2015 年 9 月 7 日上午 12：00 (即总共 31 天的数据) 。</span><span class="sxs-lookup"><span data-stu-id="7ac5a-159">For example, if you select the Daily interval with a start date of 7/7/2015 and an end date of 2/28/2015, data is displayed for the days 8/7/2015 12:00 AM to 9/7/2015 12:00 AM (that is, a total of 31 days' worth of data).</span></span> <br/> |
|<span data-ttu-id="7ac5a-160">**Pool**</span><span class="sxs-lookup"><span data-stu-id="7ac5a-160">**Pool**</span></span> <br/> |<span data-ttu-id="7ac5a-p111">注册器池或边缘服务器的完全限定域名 (FQDN)。可以选择单个池，也可以单击“[所有]”查看所有池的数据。系统根据数据库中的记录自动为您填充该下拉列表。</span><span class="sxs-lookup"><span data-stu-id="7ac5a-p111">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click **[All]** to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database. </span></span><br/> |
   
## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="7ac5a-164">点对点会话的指标</span><span class="sxs-lookup"><span data-stu-id="7ac5a-164">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="7ac5a-165">下表列出了点对点会话（即，只涉及两个参与者的会话）的呼叫诊断摘要报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="7ac5a-165">The following table lists the information provided in the Call Diagnostic Summary Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>
  
<span data-ttu-id="7ac5a-166">**点对点会话的指标**</span><span class="sxs-lookup"><span data-stu-id="7ac5a-166">**Metrics for Peer-to-Peer Sessions**</span></span>

|<span data-ttu-id="7ac5a-167">**名称**</span><span class="sxs-lookup"><span data-stu-id="7ac5a-167">**Name**</span></span>|<span data-ttu-id="7ac5a-168">**是否可按此项排序？**</span><span class="sxs-lookup"><span data-stu-id="7ac5a-168">**Can you sort on this item?**</span></span>|<span data-ttu-id="7ac5a-169">**说明**</span><span class="sxs-lookup"><span data-stu-id="7ac5a-169">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7ac5a-170">**会话总数**</span><span class="sxs-lookup"><span data-stu-id="7ac5a-170">**Total sessions**</span></span> <br/> |<span data-ttu-id="7ac5a-171">否</span><span class="sxs-lookup"><span data-stu-id="7ac5a-171">No</span></span>  <br/> |<span data-ttu-id="7ac5a-172">发起的点对点会话总数。</span><span class="sxs-lookup"><span data-stu-id="7ac5a-172">Total number of peer-to-peer sessions conducted.</span></span>  <br/> |
|<span data-ttu-id="7ac5a-173">**故障率**</span><span class="sxs-lookup"><span data-stu-id="7ac5a-173">**Failure rate**</span></span> <br/> |<span data-ttu-id="7ac5a-174">否</span><span class="sxs-lookup"><span data-stu-id="7ac5a-174">No</span></span>  <br/> |<span data-ttu-id="7ac5a-p112">失败的点对点会话百分比。单击此项时，报告将显示点对点活动诊断报告，其中显示有关失败的点对点会话的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7ac5a-p112">Percentage of peer-to-peer sessions that failed. When you click this item, the report shows the Peer-to-Peer Activity Diagnostic report, which displays more detailed information about the failed peer-to-peer sessions.</span></span>  <br/> |
   
## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="7ac5a-177">会议会话的指标</span><span class="sxs-lookup"><span data-stu-id="7ac5a-177">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="7ac5a-178">下表列出了会议会话（即，涉及三个或更多参与者的会话）的呼叫诊断报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="7ac5a-178">The following table lists the information provided in the Call Diagnostic Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>
  
<span data-ttu-id="7ac5a-179">**会议会话的指标**</span><span class="sxs-lookup"><span data-stu-id="7ac5a-179">**Metrics for Conferencing Sessions**</span></span>

|<span data-ttu-id="7ac5a-180">**名称**</span><span class="sxs-lookup"><span data-stu-id="7ac5a-180">**Name**</span></span>|<span data-ttu-id="7ac5a-181">**是否可按此项排序？**</span><span class="sxs-lookup"><span data-stu-id="7ac5a-181">**Can you sort on this item?**</span></span>|<span data-ttu-id="7ac5a-182">**说明**</span><span class="sxs-lookup"><span data-stu-id="7ac5a-182">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7ac5a-183">**会议总数**</span><span class="sxs-lookup"><span data-stu-id="7ac5a-183">**Total conferences**</span></span> <br/> |<span data-ttu-id="7ac5a-184">否</span><span class="sxs-lookup"><span data-stu-id="7ac5a-184">No</span></span>  <br/> |<span data-ttu-id="7ac5a-185">举行的会议总数。</span><span class="sxs-lookup"><span data-stu-id="7ac5a-185">Total number of conferences conducted.</span></span>  <br/> |
|<span data-ttu-id="7ac5a-186">**会议会话总数**</span><span class="sxs-lookup"><span data-stu-id="7ac5a-186">**Total conference sessions**</span></span> <br/> |<span data-ttu-id="7ac5a-187">否</span><span class="sxs-lookup"><span data-stu-id="7ac5a-187">No</span></span>  <br/> |<span data-ttu-id="7ac5a-188">发起的会议会话总数。</span><span class="sxs-lookup"><span data-stu-id="7ac5a-188">Total number of conferencing sessions conducted.</span></span>  <br/> |
|<span data-ttu-id="7ac5a-189">**总体会话故障率**</span><span class="sxs-lookup"><span data-stu-id="7ac5a-189">**Overall session failure rate**</span></span> <br/> |<span data-ttu-id="7ac5a-190">否</span><span class="sxs-lookup"><span data-stu-id="7ac5a-190">No</span></span>  <br/> |<span data-ttu-id="7ac5a-191">失败的会议会话百分比。</span><span class="sxs-lookup"><span data-stu-id="7ac5a-191">Percentage of the total conferencing sessions that failed.</span></span>  <br/> |
|<span data-ttu-id="7ac5a-192">**焦点会话**</span><span class="sxs-lookup"><span data-stu-id="7ac5a-192">**Focus sessions**</span></span> <br/> |<span data-ttu-id="7ac5a-193">否</span><span class="sxs-lookup"><span data-stu-id="7ac5a-193">No</span></span>  <br/> |<span data-ttu-id="7ac5a-194">失败的基于会议状态中心的会议会话总数。</span><span class="sxs-lookup"><span data-stu-id="7ac5a-194">Total number of Focus-based conferencing sessions that failed.</span></span>  <br/> |
|<span data-ttu-id="7ac5a-195">**焦点故障率**</span><span class="sxs-lookup"><span data-stu-id="7ac5a-195">**Focus failure rate**</span></span> <br/> |<span data-ttu-id="7ac5a-196">否</span><span class="sxs-lookup"><span data-stu-id="7ac5a-196">No</span></span>  <br/> |<span data-ttu-id="7ac5a-197">失败的基于会议状态中心的会议会话百分比。</span><span class="sxs-lookup"><span data-stu-id="7ac5a-197">Percentage of the Focus-based conferencing sessions that failed.</span></span>  <br/> |
|<span data-ttu-id="7ac5a-198">**MCU 会话**</span><span class="sxs-lookup"><span data-stu-id="7ac5a-198">**MCU sessions**</span></span> <br/> |<span data-ttu-id="7ac5a-199">否</span><span class="sxs-lookup"><span data-stu-id="7ac5a-199">No</span></span>  <br/> |<span data-ttu-id="7ac5a-200">失败的基于会议服务器（以前称为多点控制单元，简称 MCU）的会议总数。</span><span class="sxs-lookup"><span data-stu-id="7ac5a-200">Total number of conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span>  <br/> |
|<span data-ttu-id="7ac5a-201">**MCU 故障率**</span><span class="sxs-lookup"><span data-stu-id="7ac5a-201">**MCU failure rate**</span></span> <br/> |<span data-ttu-id="7ac5a-202">否</span><span class="sxs-lookup"><span data-stu-id="7ac5a-202">No</span></span>  <br/> |<span data-ttu-id="7ac5a-203">失败的基于会议服务器（以前称为多点控制单元，简称 MCU）的会议百分比。</span><span class="sxs-lookup"><span data-stu-id="7ac5a-203">Percentage of the conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span>  <br/> |
   

