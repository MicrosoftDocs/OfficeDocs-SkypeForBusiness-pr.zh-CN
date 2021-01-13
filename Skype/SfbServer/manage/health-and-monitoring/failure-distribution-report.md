---
title: Skype for Business Server 中的故障分布报告
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
ms.assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
description: 摘要：了解 Skype for Business Server 中的故障分布报告。
ms.openlocfilehash: 251cf8e2017312d9e42e0d1aebcfe5d1d9bd3568
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823522"
---
# <a name="failure-distribution-report-in-skype-for-business-server"></a><span data-ttu-id="d15cf-103">Skype for Business Server 中的故障分布报告</span><span class="sxs-lookup"><span data-stu-id="d15cf-103">Failure Distribution Report in Skype for Business Server</span></span>
 
<span data-ttu-id="d15cf-104">**摘要：** 了解 Skype for Business Server 中的故障分布报告。</span><span class="sxs-lookup"><span data-stu-id="d15cf-104">**Summary:** Learn about the Failure Distribution Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="d15cf-105">故障分布报告按以下类别对失败会话进行分级：</span><span class="sxs-lookup"><span data-stu-id="d15cf-105">The Failure Distribution Report ranks failed sessions in the following categories:</span></span>
  
- <span data-ttu-id="d15cf-106">主要诊断原因</span><span class="sxs-lookup"><span data-stu-id="d15cf-106">Top diagnostic reasons</span></span>
    
- <span data-ttu-id="d15cf-107">主要形式</span><span class="sxs-lookup"><span data-stu-id="d15cf-107">Top modalities</span></span>
    
- <span data-ttu-id="d15cf-108">主要池</span><span class="sxs-lookup"><span data-stu-id="d15cf-108">Top pools</span></span>
    
- <span data-ttu-id="d15cf-109">主要来源</span><span class="sxs-lookup"><span data-stu-id="d15cf-109">Top sources</span></span>
    
- <span data-ttu-id="d15cf-110">主要组件</span><span class="sxs-lookup"><span data-stu-id="d15cf-110">Top components</span></span>
    
- <span data-ttu-id="d15cf-111">主要来源用户</span><span class="sxs-lookup"><span data-stu-id="d15cf-111">Top from users</span></span>
    
- <span data-ttu-id="d15cf-112">主要目标用户</span><span class="sxs-lookup"><span data-stu-id="d15cf-112">Top to users</span></span>
    
- <span data-ttu-id="d15cf-113">主要来源用户代理</span><span class="sxs-lookup"><span data-stu-id="d15cf-113">Top from user agents</span></span>
    
<span data-ttu-id="d15cf-p101">可以使用这些类别准确确定出现问题的位置，在某些情况下还可准确确定出现问题的原因。例如，假设您在指定的一天内记录了 242 个失败的音频/视频会话。如果您查看故障分布报告，它可能会指示这些失败会话中有 237 个发生在您的 Dublin 池中。在跟踪和诊断出现这些故障的原因时，这为您提供了一个良好的开端。如果单击“主要池”类别下的 Dublin 池，即可看到该池的故障分布报告。然后您可以开始分析 Dublin 池为何出现如此多的问题。</span><span class="sxs-lookup"><span data-stu-id="d15cf-p101">You can use these categories to determine exactly where a problem is occurring and, in some cases, why the problem is occurring. For example, suppose you recorded 242 failed audio/video sessions during a given day. If you look at the Failure Distribution Report, it might show that 237 of those failed sessions took place in your Dublin pool. That gives you a good place to start when it comes to tracking down and diagnosing the causes behind those failures. If you click on the Dublin pool under the **Top pools** category, you will see a Failure Distribution Report just for that pool. You can then begin analyzing why the Dublin pool was experiencing so many difficulties.</span></span>
  
## <a name="viewing-the-failure-distribution-report"></a><span data-ttu-id="d15cf-120">查看故障分布报告</span><span class="sxs-lookup"><span data-stu-id="d15cf-120">Viewing the Failure Distribution Report</span></span>

<span data-ttu-id="d15cf-121">您可以通过单击“预期失败量”或“意外失败量”指标，从以下任意报告中访问故障分布报告：</span><span class="sxs-lookup"><span data-stu-id="d15cf-121">You can access the Failure Distribution Report from any of the following reports by clicking either the **Expected failure volume** or the **Unexpected failure volume** metric:</span></span>
  
- [<span data-ttu-id="d15cf-122">Skype for Business Server 中的热门故障报告</span><span class="sxs-lookup"><span data-stu-id="d15cf-122">Top Failures Report in Skype for Business Server</span></span>](top-failures-report.md)
    
- [<span data-ttu-id="d15cf-123">Skype for Business Server 中的会议诊断报告</span><span class="sxs-lookup"><span data-stu-id="d15cf-123">Conference Diagnostic Report in Skype for Business Server</span></span>](conference-diagnostic-report.md)
    
- [<span data-ttu-id="d15cf-124">Skype for Business Server 中的对等活动诊断报告</span><span class="sxs-lookup"><span data-stu-id="d15cf-124">Peer-to-Peer Activity Diagnostic Report in Skype for Business Server</span></span>](peer-to-peer-activity-diagnostic-report.md)
    
<span data-ttu-id="d15cf-125">从故障分布报告中，可以单击以下任一指标以查看 Skype for Business Server 中的故障 [列表报告](failure-list-report.md)：</span><span class="sxs-lookup"><span data-stu-id="d15cf-125">From the Failure Distribution Report, you can click any of the following metrics to view the [Failure List Report in Skype for Business Server](failure-list-report.md):</span></span>
  
- <span data-ttu-id="d15cf-126">主要诊断原因（会话）</span><span class="sxs-lookup"><span data-stu-id="d15cf-126">Top diagnostic reasons (sessions)</span></span>
    
- <span data-ttu-id="d15cf-127">主要形式（会话）</span><span class="sxs-lookup"><span data-stu-id="d15cf-127">Top modalities (sessions)</span></span>
    
- <span data-ttu-id="d15cf-128">主要池（会话）</span><span class="sxs-lookup"><span data-stu-id="d15cf-128">Top pools (sessions)</span></span>
    
- <span data-ttu-id="d15cf-129">主要来源（会话）</span><span class="sxs-lookup"><span data-stu-id="d15cf-129">Top sources (sessions)</span></span>
    
- <span data-ttu-id="d15cf-130">主要组件（会话）</span><span class="sxs-lookup"><span data-stu-id="d15cf-130">Top components (sessions)</span></span>
    
- <span data-ttu-id="d15cf-131">主要来源用户（会话）</span><span class="sxs-lookup"><span data-stu-id="d15cf-131">Top from users (sessions)</span></span>
    
- <span data-ttu-id="d15cf-132">主要目标用户（会话）</span><span class="sxs-lookup"><span data-stu-id="d15cf-132">Top to users (sessions)</span></span>
    
- <span data-ttu-id="d15cf-133">主要来源用户代理（会话）</span><span class="sxs-lookup"><span data-stu-id="d15cf-133">Top from user agents (sessions)</span></span>
    
## <a name="using-the-failure-distribution-report"></a><span data-ttu-id="d15cf-134">使用故障分布报告</span><span class="sxs-lookup"><span data-stu-id="d15cf-134">Using the Failure Distribution Report</span></span>

<span data-ttu-id="d15cf-p102">根据您的监视器尺寸和屏幕分辨率，当您在屏幕上查看故障分布报告中显示的某些数据时，这些数据可能会被截断。用户代理（可能具有很长的标签）等指标尤其可能出现这种情况。例如，具有类似“UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)”的名称的用户代理可能只会部分显示在屏幕上：</span><span class="sxs-lookup"><span data-stu-id="d15cf-p102">Depending on your monitor size and screen resolution, it's possible that some of the data shown in the Failure Distribution Report might be truncated when you view it onscreen. This is especially true for metrics such as user agents, which can have very long labels. For example, a user agent with a name like "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" might only partially appear onscreen:</span></span> 
  
<span data-ttu-id="d15cf-138">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span><span class="sxs-lookup"><span data-stu-id="d15cf-138">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span></span>
  
<span data-ttu-id="d15cf-139">幸运的是，只需将鼠标指针停留在截断值上方即可查看整个标签。</span><span class="sxs-lookup"><span data-stu-id="d15cf-139">Fortunately, you can see the entire label simply by holding your mouse over the truncated value.</span></span>
  
<span data-ttu-id="d15cf-p103">可以使用故障分布报告按其进行筛选的一个有用指标是诊断 ID。如果您看到其他报告中出现相同的诊断 ID，则可以在故障分布报告中按此 ID 进行筛选，并获得有关失败会话期间报告此 ID 的准确位置及频率的十分详细的信息。</span><span class="sxs-lookup"><span data-stu-id="d15cf-p103">One interesting metric that you can filter on by using the Failure Distribution Report is Diagnostic ID. If you see the same Diagnostic ID cropping up in other reports you can filter on that ID in the Failure Distribution Report and get a very detailed look at exactly where, and how often, that ID has been reported during a failed session.</span></span>
  
## <a name="filters"></a><span data-ttu-id="d15cf-142">筛选器</span><span class="sxs-lookup"><span data-stu-id="d15cf-142">Filters</span></span>

<span data-ttu-id="d15cf-p104">利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，故障分布报告允许您依据活动类型（点对点会话还是会议会话）或每个失败会话附带的诊断 ID 等条件进行筛选。</span><span class="sxs-lookup"><span data-stu-id="d15cf-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Failed Distribution Report enables you to filter on such things as the activity type (peer-to-peer session or conferencing session) or by the diagnostic ID that accompanied each failed session.</span></span>
  
<span data-ttu-id="d15cf-145">下表列出了可用于故障分布报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="d15cf-145">The following table lists the filters that you can use with the Failure Distribution Report.</span></span>
  
<span data-ttu-id="d15cf-146">**故障分布报告筛选器**</span><span class="sxs-lookup"><span data-stu-id="d15cf-146">**Failure Distribution Report Filters**</span></span>

|<span data-ttu-id="d15cf-147">**名称**</span><span class="sxs-lookup"><span data-stu-id="d15cf-147">**Name**</span></span>|<span data-ttu-id="d15cf-148">**说明**</span><span class="sxs-lookup"><span data-stu-id="d15cf-148">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d15cf-149">**From**</span><span class="sxs-lookup"><span data-stu-id="d15cf-149">**From**</span></span> <br/> |<span data-ttu-id="d15cf-p105">时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d15cf-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span>  <br/> <span data-ttu-id="d15cf-152">7/7/2015 1：00 PM</span><span class="sxs-lookup"><span data-stu-id="d15cf-152">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="d15cf-p106">如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="d15cf-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="d15cf-155">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="d15cf-155">7/7/2015</span></span>  <br/> <span data-ttu-id="d15cf-156">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="d15cf-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="d15cf-157">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="d15cf-157">7/3/2015</span></span>  <br/> <span data-ttu-id="d15cf-158">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="d15cf-158">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="d15cf-159">"自"</span><span class="sxs-lookup"><span data-stu-id="d15cf-159">**To**</span></span> <br/> |<span data-ttu-id="d15cf-p107">时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d15cf-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span>  <br/> <span data-ttu-id="d15cf-162">7/7/2015 1：00 PM</span><span class="sxs-lookup"><span data-stu-id="d15cf-162">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="d15cf-p108">如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</span><span class="sxs-lookup"><span data-stu-id="d15cf-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="d15cf-165">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="d15cf-165">7/7/2015</span></span>  <br/> <span data-ttu-id="d15cf-166">若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="d15cf-166">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="d15cf-167">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="d15cf-167">7/3/2015</span></span>  <br/> <span data-ttu-id="d15cf-168">一周始终是从星期日开始至星期六结束。</span><span class="sxs-lookup"><span data-stu-id="d15cf-168">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="d15cf-169">**Pool**</span><span class="sxs-lookup"><span data-stu-id="d15cf-169">**Pool**</span></span> <br/> |<span data-ttu-id="d15cf-p109">注册器池或边缘服务器的完全限定域名 (FQDN)。可以选择单个池，也可以单击“[所有]”查看所有池的数据。系统根据数据库中的记录自动为您填充该下拉列表。</span><span class="sxs-lookup"><span data-stu-id="d15cf-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click **[All]** to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database. </span></span><br/> |
|<span data-ttu-id="d15cf-173">**活动类型**</span><span class="sxs-lookup"><span data-stu-id="d15cf-173">**Activity type**</span></span> <br/> | <span data-ttu-id="d15cf-p110">要筛选的活动类型。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="d15cf-p110">Type of activity to filter on. Select one of the following:</span></span> <br/>  <span data-ttu-id="d15cf-176">[全部]</span><span class="sxs-lookup"><span data-stu-id="d15cf-176">[All]</span></span> <br/>  <span data-ttu-id="d15cf-177">对等</span><span class="sxs-lookup"><span data-stu-id="d15cf-177">Peer-to-peer</span></span> <br/>  <span data-ttu-id="d15cf-178">会议</span><span class="sxs-lookup"><span data-stu-id="d15cf-178">Conference</span></span> <br/> |
|<span data-ttu-id="d15cf-179">**会话类别**</span><span class="sxs-lookup"><span data-stu-id="d15cf-179">**Session category**</span></span> <br/> | <span data-ttu-id="d15cf-p111">指示相应活动已成功还是失败。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="d15cf-p111">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span> <br/>  <span data-ttu-id="d15cf-182">[全部]</span><span class="sxs-lookup"><span data-stu-id="d15cf-182">[All]</span></span> <br/>  <span data-ttu-id="d15cf-183">成功</span><span class="sxs-lookup"><span data-stu-id="d15cf-183">Success</span></span> <br/>  <span data-ttu-id="d15cf-184">预期失败</span><span class="sxs-lookup"><span data-stu-id="d15cf-184">Expected failure</span></span> <br/>  <span data-ttu-id="d15cf-185">意外失败</span><span class="sxs-lookup"><span data-stu-id="d15cf-185">Unexpected failure</span></span> <br/>  <span data-ttu-id="d15cf-p112">“预期失败”是指预计会出现的失败情况。例如，如果用户将其状态设置为“请勿打扰”，那么向该用户发出的任何呼叫应该都会失败。“意外失败”是指在本该正常运行的系统中出现的失败情况。例如，如果呼叫者处于呼叫等待状态，则不应该终止呼叫。如果终止，则会被标记为意外失败。</span><span class="sxs-lookup"><span data-stu-id="d15cf-p112">An "expected failure" is a failure that is expected to happen. For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail. An "unexpected failure" is a failure that occurs in what would appear to be an otherwise healthy system. For example, a call should not be terminated if the caller is placed on hold. If that occurs, that would be flagged as an unexpected failure.</span></span> <br/> |
|<span data-ttu-id="d15cf-191">**诊断 ID**</span><span class="sxs-lookup"><span data-stu-id="d15cf-191">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="d15cf-p113">附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。诊断标头是可选的（SIP 会话可以不包含这些标头），并且只对遇到此类问题的会话报告诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="d15cf-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span>  <br/> |
   
## <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="d15cf-194">主要诊断原因的指标</span><span class="sxs-lookup"><span data-stu-id="d15cf-194">Metrics for Top Diagnostic Reasons</span></span>

<span data-ttu-id="d15cf-195">下表列出了故障分布报告中基于最常见的诊断 ID 提供的信息。</span><span class="sxs-lookup"><span data-stu-id="d15cf-195">The following table lists the information provided in the Failure Distribution Report based on the most frequently reported diagnostic ID.</span></span>
  
<span data-ttu-id="d15cf-196">**主要诊断原因的指标**</span><span class="sxs-lookup"><span data-stu-id="d15cf-196">**Metrics for Top Diagnostic Reasons**</span></span>

|<span data-ttu-id="d15cf-197">**名称**</span><span class="sxs-lookup"><span data-stu-id="d15cf-197">**Name**</span></span>|<span data-ttu-id="d15cf-198">**是否可按此项排序？**</span><span class="sxs-lookup"><span data-stu-id="d15cf-198">**Can you sort on this item?**</span></span>|<span data-ttu-id="d15cf-199">**说明**</span><span class="sxs-lookup"><span data-stu-id="d15cf-199">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d15cf-200">**Rank**</span><span class="sxs-lookup"><span data-stu-id="d15cf-200">**Rank**</span></span> <br/> |<span data-ttu-id="d15cf-201">否</span><span class="sxs-lookup"><span data-stu-id="d15cf-201">No</span></span>  <br/> |<span data-ttu-id="d15cf-p114">失败会话的相对等级，根据诊断 ID 确定。诊断 ID 是附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。</span><span class="sxs-lookup"><span data-stu-id="d15cf-p114">Relative ranking of failed sessions based on diagnostic IDs. The diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="d15cf-204">**主要诊断原因**</span><span class="sxs-lookup"><span data-stu-id="d15cf-204">**Top diagnostic reasons**</span></span> <br/> |<span data-ttu-id="d15cf-205">否</span><span class="sxs-lookup"><span data-stu-id="d15cf-205">No</span></span>  <br/> |<span data-ttu-id="d15cf-206">会话中生成的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="d15cf-206">Diagnostic ID generated in a session.</span></span>  <br/> |
|<span data-ttu-id="d15cf-207">**会话**</span><span class="sxs-lookup"><span data-stu-id="d15cf-207">**Sessions**</span></span> <br/> |<span data-ttu-id="d15cf-208">否</span><span class="sxs-lookup"><span data-stu-id="d15cf-208">No</span></span>  <br/> |<span data-ttu-id="d15cf-209">生成了指定诊断 ID 的失败会话总数。</span><span class="sxs-lookup"><span data-stu-id="d15cf-209">Total number of failed sessions where the specified diagnostic ID was generated.</span></span>  <br/> |
   
## <a name="metrics-for-top-modalities"></a><span data-ttu-id="d15cf-210">主要形式的指标</span><span class="sxs-lookup"><span data-stu-id="d15cf-210">Metrics for Top Modalities</span></span>

<span data-ttu-id="d15cf-211">下表列出了故障分布报告中基于所遇故障最多的会话形式提供的信息。</span><span class="sxs-lookup"><span data-stu-id="d15cf-211">The following table lists the information provided in the Failure Distribution Report based on the session modalities that experienced the most failures.</span></span>
  
<span data-ttu-id="d15cf-212">**主要形式的指标**</span><span class="sxs-lookup"><span data-stu-id="d15cf-212">**Metrics for Top Modalities**</span></span>

|<span data-ttu-id="d15cf-213">**名称**</span><span class="sxs-lookup"><span data-stu-id="d15cf-213">**Name**</span></span>|<span data-ttu-id="d15cf-214">**是否可按此项排序？**</span><span class="sxs-lookup"><span data-stu-id="d15cf-214">**Can you sort on this item?**</span></span>|<span data-ttu-id="d15cf-215">**说明**</span><span class="sxs-lookup"><span data-stu-id="d15cf-215">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d15cf-216">**Rank**</span><span class="sxs-lookup"><span data-stu-id="d15cf-216">**Rank**</span></span> <br/> |<span data-ttu-id="d15cf-217">否</span><span class="sxs-lookup"><span data-stu-id="d15cf-217">No</span></span>  <br/> |<span data-ttu-id="d15cf-218">失败会话的相对等级，根据会话类型（例如，音频/视频会议或点对点文件传输会话）确定。</span><span class="sxs-lookup"><span data-stu-id="d15cf-218">Relative ranking based of failed session based on session type (for example, an audio/video conference or a peer-to-peer file transfer session).</span></span>  <br/> |
|<span data-ttu-id="d15cf-219">**主要形式**</span><span class="sxs-lookup"><span data-stu-id="d15cf-219">**Top modalities**</span></span> <br/> |<span data-ttu-id="d15cf-220">否</span><span class="sxs-lookup"><span data-stu-id="d15cf-220">No</span></span>  <br/> |<span data-ttu-id="d15cf-221">会话类型。</span><span class="sxs-lookup"><span data-stu-id="d15cf-221">Session type.</span></span>  <br/> |
|<span data-ttu-id="d15cf-222">**会话**</span><span class="sxs-lookup"><span data-stu-id="d15cf-222">**Sessions**</span></span> <br/> |<span data-ttu-id="d15cf-223">否</span><span class="sxs-lookup"><span data-stu-id="d15cf-223">No</span></span>  <br/> |<span data-ttu-id="d15cf-224">涉及指定形式的失败会话总数。</span><span class="sxs-lookup"><span data-stu-id="d15cf-224">Total number of failed sessions involving the specified modality.</span></span>  <br/> |
   
## <a name="metrics-for-top-pools"></a><span data-ttu-id="d15cf-225">主要池的指标</span><span class="sxs-lookup"><span data-stu-id="d15cf-225">Metrics for Top Pools</span></span>

<span data-ttu-id="d15cf-226">下表列出了故障分布报告中基于所遇故障最多的池提供的信息。</span><span class="sxs-lookup"><span data-stu-id="d15cf-226">The following table lists the information provided in the Failure Distribution Report based on the pools that experienced the most failures.</span></span>
  
<span data-ttu-id="d15cf-227">**主要池的指标**</span><span class="sxs-lookup"><span data-stu-id="d15cf-227">**Metrics for Top Pools**</span></span>

|<span data-ttu-id="d15cf-228">**名称**</span><span class="sxs-lookup"><span data-stu-id="d15cf-228">**Name**</span></span>|<span data-ttu-id="d15cf-229">**是否可按此项排序？**</span><span class="sxs-lookup"><span data-stu-id="d15cf-229">**Can you sort on this item?**</span></span>|<span data-ttu-id="d15cf-230">**说明**</span><span class="sxs-lookup"><span data-stu-id="d15cf-230">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d15cf-231">**Rank**</span><span class="sxs-lookup"><span data-stu-id="d15cf-231">**Rank**</span></span> <br/> |<span data-ttu-id="d15cf-232">否</span><span class="sxs-lookup"><span data-stu-id="d15cf-232">No</span></span>  <br/> |<span data-ttu-id="d15cf-233">失败会话的相对等级，基于执行会话的注册器池或边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="d15cf-233">Relative ranking of failed sessions based on the Registrar pool or Edge Server where the session was conducted.</span></span>  <br/> |
|<span data-ttu-id="d15cf-234">**主要池**</span><span class="sxs-lookup"><span data-stu-id="d15cf-234">**Top pools**</span></span> <br/> |<span data-ttu-id="d15cf-235">否</span><span class="sxs-lookup"><span data-stu-id="d15cf-235">No</span></span>  <br/> |<span data-ttu-id="d15cf-236">注册器池或边缘服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="d15cf-236">Name of the Registrar pool or Edge Server.</span></span>  <br/> |
|<span data-ttu-id="d15cf-237">**会话**</span><span class="sxs-lookup"><span data-stu-id="d15cf-237">**Sessions**</span></span> <br/> |<span data-ttu-id="d15cf-238">否</span><span class="sxs-lookup"><span data-stu-id="d15cf-238">No</span></span>  <br/> |<span data-ttu-id="d15cf-239">每个注册器池或边缘服务器的失败会话总数。</span><span class="sxs-lookup"><span data-stu-id="d15cf-239">Total number of failed sessions per Registrar pool or Edge Server.</span></span>  <br/> |
   
## <a name="metrics-for-top-sources"></a><span data-ttu-id="d15cf-240">主要来源的指标</span><span class="sxs-lookup"><span data-stu-id="d15cf-240">Metrics for Top Sources</span></span>

<span data-ttu-id="d15cf-241">下表列出了故障分布报告中基于所遇故障最多的计算机提供的信息。</span><span class="sxs-lookup"><span data-stu-id="d15cf-241">The following table lists the information provided in the Failure Distribution Report based on the computers that experienced the most failures.</span></span>
  
<span data-ttu-id="d15cf-242">**主要来源的指标**</span><span class="sxs-lookup"><span data-stu-id="d15cf-242">**Metrics for Top Sources**</span></span>

|<span data-ttu-id="d15cf-243">**名称**</span><span class="sxs-lookup"><span data-stu-id="d15cf-243">**Name**</span></span>|<span data-ttu-id="d15cf-244">**是否可按此项排序？**</span><span class="sxs-lookup"><span data-stu-id="d15cf-244">**Can you sort on this item?**</span></span>|<span data-ttu-id="d15cf-245">**说明**</span><span class="sxs-lookup"><span data-stu-id="d15cf-245">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d15cf-246">**Rank**</span><span class="sxs-lookup"><span data-stu-id="d15cf-246">**Rank**</span></span> <br/> |<span data-ttu-id="d15cf-247">否</span><span class="sxs-lookup"><span data-stu-id="d15cf-247">No</span></span>  <br/> |<span data-ttu-id="d15cf-248">失败会话的相对等级，根据计算机确定。</span><span class="sxs-lookup"><span data-stu-id="d15cf-248">Relative ranking failed sessions per computer.</span></span>  <br/> |
|<span data-ttu-id="d15cf-249">**主要来源**</span><span class="sxs-lookup"><span data-stu-id="d15cf-249">**Top sources**</span></span> <br/> |<span data-ttu-id="d15cf-250">否</span><span class="sxs-lookup"><span data-stu-id="d15cf-250">No</span></span>  <br/> |<span data-ttu-id="d15cf-251">失败会话所涉及的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="d15cf-251">Name of the computer involved in the failed session.</span></span>  <br/> |
|<span data-ttu-id="d15cf-252">**会话**</span><span class="sxs-lookup"><span data-stu-id="d15cf-252">**Sessions**</span></span> <br/> |<span data-ttu-id="d15cf-253">否</span><span class="sxs-lookup"><span data-stu-id="d15cf-253">No</span></span>  <br/> |<span data-ttu-id="d15cf-254">每台计算机的失败会话总数。</span><span class="sxs-lookup"><span data-stu-id="d15cf-254">Total number of failed sessions per computer.</span></span>  <br/> |
   
## <a name="metrics-for-top-components"></a><span data-ttu-id="d15cf-255">主要组件的指标</span><span class="sxs-lookup"><span data-stu-id="d15cf-255">Metrics for Top Components</span></span>

<span data-ttu-id="d15cf-256">下表列出了故障分布报告中基于故障最多的组件提供的信息。</span><span class="sxs-lookup"><span data-stu-id="d15cf-256">The following table lists the information provided in the Failure Distribution Report based on the components that experienced the most failures.</span></span>
  
<span data-ttu-id="d15cf-257">**主要组件的指标**</span><span class="sxs-lookup"><span data-stu-id="d15cf-257">**Metrics for Top Components**</span></span>

|<span data-ttu-id="d15cf-258">**名称**</span><span class="sxs-lookup"><span data-stu-id="d15cf-258">**Name**</span></span>|<span data-ttu-id="d15cf-259">**是否可按此项排序？**</span><span class="sxs-lookup"><span data-stu-id="d15cf-259">**Can you sort on this item?**</span></span>|<span data-ttu-id="d15cf-260">**说明**</span><span class="sxs-lookup"><span data-stu-id="d15cf-260">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d15cf-261">**Rank**</span><span class="sxs-lookup"><span data-stu-id="d15cf-261">**Rank**</span></span> <br/> |<span data-ttu-id="d15cf-262">否</span><span class="sxs-lookup"><span data-stu-id="d15cf-262">No</span></span>  <br/> |<span data-ttu-id="d15cf-263">失败会话的相对等级，基于组件 (例如 ExumRouting、GroupChat 或 MediationServer) 。</span><span class="sxs-lookup"><span data-stu-id="d15cf-263">Relative ranking of failed sessions based on component (for example, ExumRouting, GroupChat, or MediationServer).</span></span>  <br/> |
|<span data-ttu-id="d15cf-264">**主要组件**</span><span class="sxs-lookup"><span data-stu-id="d15cf-264">**Top components**</span></span> <br/> |<span data-ttu-id="d15cf-265">否</span><span class="sxs-lookup"><span data-stu-id="d15cf-265">No</span></span>  <br/> |<span data-ttu-id="d15cf-266">失败会话所涉及的组件的名称。</span><span class="sxs-lookup"><span data-stu-id="d15cf-266">Name of the component involved in the failed session.</span></span>  <br/> |
|<span data-ttu-id="d15cf-267">**会话**</span><span class="sxs-lookup"><span data-stu-id="d15cf-267">**Sessions**</span></span> <br/> |<span data-ttu-id="d15cf-268">否</span><span class="sxs-lookup"><span data-stu-id="d15cf-268">No</span></span>  <br/> |<span data-ttu-id="d15cf-269">每个组件的失败会话总数。</span><span class="sxs-lookup"><span data-stu-id="d15cf-269">Total number of failed sessions per component.</span></span>  <br/> |
   
## <a name="metrics-for-top-from-users"></a><span data-ttu-id="d15cf-270">主要来源用户的指标</span><span class="sxs-lookup"><span data-stu-id="d15cf-270">Metrics for Top From Users</span></span>

<span data-ttu-id="d15cf-271">下表列出了故障分布报告中基于尝试呼叫其他人时所遇故障最多的用户提供的信息，尝试呼叫其他人的用户称为“来源”用户。</span><span class="sxs-lookup"><span data-stu-id="d15cf-271">The following table lists the information provided in the Failure Distribution Report based on users who experienced the most failures when they tried to call someone else (known as "From" users).</span></span>
  
<span data-ttu-id="d15cf-272">**主要来源用户的指标**</span><span class="sxs-lookup"><span data-stu-id="d15cf-272">**Metrics for Top From Users**</span></span>

|<span data-ttu-id="d15cf-273">**名称**</span><span class="sxs-lookup"><span data-stu-id="d15cf-273">**Name**</span></span>|<span data-ttu-id="d15cf-274">**是否可按此项排序？**</span><span class="sxs-lookup"><span data-stu-id="d15cf-274">**Can you sort on this item?**</span></span>|<span data-ttu-id="d15cf-275">**说明**</span><span class="sxs-lookup"><span data-stu-id="d15cf-275">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d15cf-276">**Rank**</span><span class="sxs-lookup"><span data-stu-id="d15cf-276">**Rank**</span></span> <br/> |<span data-ttu-id="d15cf-277">否</span><span class="sxs-lookup"><span data-stu-id="d15cf-277">No</span></span>  <br/> |<span data-ttu-id="d15cf-278">失败会话的相对等级，根据受邀加入会话的用户确定。</span><span class="sxs-lookup"><span data-stu-id="d15cf-278">Relative ranking of failed sessions based on the user who was invited to join the session.</span></span>  <br/> |
|<span data-ttu-id="d15cf-279">**主要来源用户**</span><span class="sxs-lookup"><span data-stu-id="d15cf-279">**Top from users**</span></span> <br/> |<span data-ttu-id="d15cf-280">否</span><span class="sxs-lookup"><span data-stu-id="d15cf-280">No</span></span>  <br/> |<span data-ttu-id="d15cf-281">受邀加入会话的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="d15cf-281">SIP address of the user invited to join the session.</span></span>  <br/> |
|<span data-ttu-id="d15cf-282">**会话**</span><span class="sxs-lookup"><span data-stu-id="d15cf-282">**Sessions**</span></span> <br/> |<span data-ttu-id="d15cf-283">否</span><span class="sxs-lookup"><span data-stu-id="d15cf-283">No</span></span>  <br/> |<span data-ttu-id="d15cf-284">每个用户的失败会话总数。</span><span class="sxs-lookup"><span data-stu-id="d15cf-284">Total number of failed sessions per user.</span></span>  <br/> |
   
## <a name="metrics-for-top-to-users"></a><span data-ttu-id="d15cf-285">主要目标用户的指标</span><span class="sxs-lookup"><span data-stu-id="d15cf-285">Metrics for Top To Users</span></span>

<span data-ttu-id="d15cf-286">下表列出了故障分布报告中基于其他人尝试呼叫的所遇故障最多的用户提供的信息，其他人尝试呼叫的用户称为“目标”用户。</span><span class="sxs-lookup"><span data-stu-id="d15cf-286">The following table lists the information provided in the Failure Distribution Report based on the users who experienced the most failures when another user tried to call them (known as "To" users).</span></span>
  
|<span data-ttu-id="d15cf-287">**名称**</span><span class="sxs-lookup"><span data-stu-id="d15cf-287">**Name**</span></span>|<span data-ttu-id="d15cf-288">**是否可按此项排序？**</span><span class="sxs-lookup"><span data-stu-id="d15cf-288">**Can you sort on this item?**</span></span>|<span data-ttu-id="d15cf-289">**说明**</span><span class="sxs-lookup"><span data-stu-id="d15cf-289">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d15cf-290">**Rank**</span><span class="sxs-lookup"><span data-stu-id="d15cf-290">**Rank**</span></span> <br/> |<span data-ttu-id="d15cf-291">否</span><span class="sxs-lookup"><span data-stu-id="d15cf-291">No</span></span>  <br/> |<span data-ttu-id="d15cf-292">失败会话的相对等级，根据发起会话的用户确定。</span><span class="sxs-lookup"><span data-stu-id="d15cf-292">Relative ranking of failed sessions based on the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="d15cf-293">**主要目标用户**</span><span class="sxs-lookup"><span data-stu-id="d15cf-293">**Top to users**</span></span> <br/> |<span data-ttu-id="d15cf-294">否</span><span class="sxs-lookup"><span data-stu-id="d15cf-294">No</span></span>  <br/> |<span data-ttu-id="d15cf-295">发起会话的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="d15cf-295">SIP address of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="d15cf-296">**会话**</span><span class="sxs-lookup"><span data-stu-id="d15cf-296">**Sessions**</span></span> <br/> |<span data-ttu-id="d15cf-297">否</span><span class="sxs-lookup"><span data-stu-id="d15cf-297">No</span></span>  <br/> |<span data-ttu-id="d15cf-298">每个用户的失败会话总数。</span><span class="sxs-lookup"><span data-stu-id="d15cf-298">Total number of failed sessions per user.</span></span>  <br/> |
   
## <a name="metrics-for-top-user-agents"></a><span data-ttu-id="d15cf-299">主要用户代理的指标</span><span class="sxs-lookup"><span data-stu-id="d15cf-299">Metrics for Top User Agents</span></span>

<span data-ttu-id="d15cf-300">下表列出了故障分布报告中基于所遇故障最多的终结点软件提供的信息。</span><span class="sxs-lookup"><span data-stu-id="d15cf-300">The following table lists the information provided in the Failure Distribution Report based on the endpoint software that experienced the most failures.</span></span>
  
<span data-ttu-id="d15cf-301">**主要用户代理的指标**</span><span class="sxs-lookup"><span data-stu-id="d15cf-301">**Metrics for Top User Agents**</span></span>

|<span data-ttu-id="d15cf-302">**名称**</span><span class="sxs-lookup"><span data-stu-id="d15cf-302">**Name**</span></span>|<span data-ttu-id="d15cf-303">**是否可按此项排序？**</span><span class="sxs-lookup"><span data-stu-id="d15cf-303">**Can you sort on this item?**</span></span>|<span data-ttu-id="d15cf-304">**说明**</span><span class="sxs-lookup"><span data-stu-id="d15cf-304">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d15cf-305">**Rank**</span><span class="sxs-lookup"><span data-stu-id="d15cf-305">**Rank**</span></span> <br/> |<span data-ttu-id="d15cf-306">否</span><span class="sxs-lookup"><span data-stu-id="d15cf-306">No</span></span>  <br/> |<span data-ttu-id="d15cf-p115">失败会话的相对等级，根据会话所涉及的用户代理（软件）确定。例如：RTCC/4.0.0.0 Inbound Routing/4.0.0.0。</span><span class="sxs-lookup"><span data-stu-id="d15cf-p115">Relative ranking of failed sessions based on the user agent (software) involved in the session. For example: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span></span>  <br/> |
|<span data-ttu-id="d15cf-309">**主要用户代理**</span><span class="sxs-lookup"><span data-stu-id="d15cf-309">**Top user agents**</span></span> <br/> |<span data-ttu-id="d15cf-310">否</span><span class="sxs-lookup"><span data-stu-id="d15cf-310">No</span></span>  <br/> |<span data-ttu-id="d15cf-311">失败会话所涉及的用户代理的名称。</span><span class="sxs-lookup"><span data-stu-id="d15cf-311">Name of the user agent involved in the failed session.</span></span>  <br/> |
|<span data-ttu-id="d15cf-312">**会话**</span><span class="sxs-lookup"><span data-stu-id="d15cf-312">**Sessions**</span></span> <br/> |<span data-ttu-id="d15cf-313">否</span><span class="sxs-lookup"><span data-stu-id="d15cf-313">No</span></span>  <br/> |<span data-ttu-id="d15cf-314">每个用户代理的失败会话总数。</span><span class="sxs-lookup"><span data-stu-id="d15cf-314">Total number of failed sessions per user agent.</span></span>  <br/> |
   

