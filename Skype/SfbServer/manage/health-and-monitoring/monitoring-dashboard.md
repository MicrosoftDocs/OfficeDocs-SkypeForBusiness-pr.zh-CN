---
title: 在 Skype for Business Server 中使用监控仪表板
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
ms.assetid: e00e5783-116f-481f-ad17-3af847d6769a
description: 摘要：了解 Skype for Business Server 中的监视仪表板。
ms.openlocfilehash: 83a04a60e63deb39666ee4d042f74973b7d16d0b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118601"
---
# <a name="using-the-monitoring-dashboard-in-skype-for-business-server"></a><span data-ttu-id="1cd5e-103">在 Skype for Business Server 中使用监控仪表板</span><span class="sxs-lookup"><span data-stu-id="1cd5e-103">Using the Monitoring Dashboard in Skype for Business Server</span></span>
 
<span data-ttu-id="1cd5e-104">**摘要：** 了解 Skype for Business Server 中的监控仪表板。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-104">**Summary:** Learn about the Monitoring Dashboard in Skype for Business Server.</span></span>
  
<span data-ttu-id="1cd5e-105">监控仪表板为管理员提供了 Skype for Business Server 系统运行状况和系统使用情况的快速概述。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-105">The Monitoring Dashboard provides administrators with a quick overview of their Skype for Business Server system health and system usage.</span></span> <span data-ttu-id="1cd5e-106">仪表板旨在显示关键系统指标的聚合视图，并且通过显示以下任一项来实现此目标：</span><span class="sxs-lookup"><span data-stu-id="1cd5e-106">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>
  
- <span data-ttu-id="1cd5e-107">当前天的总计。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-107">Totals for the current day.</span></span> <span data-ttu-id="1cd5e-108">请注意，当前天显示的值表示从午夜到当前时间记录的数据 (报告服务器记录的本地时间) 。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-108">Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server).</span></span> <span data-ttu-id="1cd5e-109">这意味着你通常会查看部分日期的数据，而不是 24 小时的数据。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-109">That means that you will typically be viewing data for a partial day and not for a 24-hour period.</span></span> <span data-ttu-id="1cd5e-110">例如，如果服务器的本地时间是上午 8：00，则会看到 8 个小时的数据，因为午夜和当前时间上午 8：00 之间有 8 个小时。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-110">For example, if the local time of the server is 8:00 AM, you see eight hours' worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>
    
- <span data-ttu-id="1cd5e-111">一周汇总，以及过去六周的趋势汇总。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-111">Totals for the week, and trend totals for the past six weeks.</span></span>
    
- <span data-ttu-id="1cd5e-112">当月总计和过去六个月的趋势总计 (系统使用情况) 。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-112">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>
    
<span data-ttu-id="1cd5e-113">请注意，您可以使用 [Get-CsReportingConfiguration](/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) cmdlet 返回用于访问 Skype for Business Server 监控报告的 URL：</span><span class="sxs-lookup"><span data-stu-id="1cd5e-113">Note that you can use the [Get-CsReportingConfiguration](/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) cmdlet to return the URL used for accessing Skype for Business Server Monitoring Reports:</span></span>
  
```PowerShell
Get-CsReportingConfiguration
```

<span data-ttu-id="1cd5e-114">默认情况下，监控仪表板显示本周的以下指标 (过去六周的趋势汇总) ：</span><span class="sxs-lookup"><span data-stu-id="1cd5e-114">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>
  
## <a name="system-usage-metrics"></a><span data-ttu-id="1cd5e-115">系统使用情况指标</span><span class="sxs-lookup"><span data-stu-id="1cd5e-115">System Usage Metrics</span></span>

 <span data-ttu-id="1cd5e-116">**Registration**</span><span class="sxs-lookup"><span data-stu-id="1cd5e-116">**Registration**</span></span>
  
- <span data-ttu-id="1cd5e-117">唯一用户登录</span><span class="sxs-lookup"><span data-stu-id="1cd5e-117">Unique user logons</span></span>
    
  <span data-ttu-id="1cd5e-118">**对等**</span><span class="sxs-lookup"><span data-stu-id="1cd5e-118">**Peer-to-peer**</span></span>
  
- <span data-ttu-id="1cd5e-119">会话总数</span><span class="sxs-lookup"><span data-stu-id="1cd5e-119">Total sessions</span></span>
    
- <span data-ttu-id="1cd5e-120">IM 会话</span><span class="sxs-lookup"><span data-stu-id="1cd5e-120">IM sessions</span></span>
    
- <span data-ttu-id="1cd5e-121">音频会话</span><span class="sxs-lookup"><span data-stu-id="1cd5e-121">Audio sessions</span></span>
    
- <span data-ttu-id="1cd5e-122">视频会话</span><span class="sxs-lookup"><span data-stu-id="1cd5e-122">Video sessions</span></span>
    
- <span data-ttu-id="1cd5e-123">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="1cd5e-123">Application sharing</span></span>
    
- <span data-ttu-id="1cd5e-124">音频会话总分钟数</span><span class="sxs-lookup"><span data-stu-id="1cd5e-124">Total audio session minutes</span></span>
    
- <span data-ttu-id="1cd5e-125">平均音频会话分钟数</span><span class="sxs-lookup"><span data-stu-id="1cd5e-125">Avg. audio session minutes</span></span>
    
  <span data-ttu-id="1cd5e-126">**Conference**</span><span class="sxs-lookup"><span data-stu-id="1cd5e-126">**Conference**</span></span>
  
- <span data-ttu-id="1cd5e-127">会议总数</span><span class="sxs-lookup"><span data-stu-id="1cd5e-127">Total conferences</span></span>
    
- <span data-ttu-id="1cd5e-128">IM 会议</span><span class="sxs-lookup"><span data-stu-id="1cd5e-128">IM conferences</span></span>
    
- <span data-ttu-id="1cd5e-129">A/V 会议</span><span class="sxs-lookup"><span data-stu-id="1cd5e-129">A/V conferences</span></span>
    
- <span data-ttu-id="1cd5e-130">应用程序共享会议</span><span class="sxs-lookup"><span data-stu-id="1cd5e-130">Application sharing conferences</span></span>
    
- <span data-ttu-id="1cd5e-131">Web 会议</span><span class="sxs-lookup"><span data-stu-id="1cd5e-131">Web conferences</span></span>
    
- <span data-ttu-id="1cd5e-132">组织者总数</span><span class="sxs-lookup"><span data-stu-id="1cd5e-132">Total organizers</span></span>
    
- <span data-ttu-id="1cd5e-133">A/V 会议总分钟数</span><span class="sxs-lookup"><span data-stu-id="1cd5e-133">Total A/V conference minutes</span></span>
    
- <span data-ttu-id="1cd5e-134">Avg.A/V 会议分钟数</span><span class="sxs-lookup"><span data-stu-id="1cd5e-134">Avg. A/V conference minutes</span></span>
    
- <span data-ttu-id="1cd5e-135">PSTN 会议总数</span><span class="sxs-lookup"><span data-stu-id="1cd5e-135">Total PSTN conferences</span></span>
    
- <span data-ttu-id="1cd5e-136">PSTN 参与者总数</span><span class="sxs-lookup"><span data-stu-id="1cd5e-136">Total PSTN participants</span></span>
    
- <span data-ttu-id="1cd5e-137">PSTN 参与者总分钟数</span><span class="sxs-lookup"><span data-stu-id="1cd5e-137">Total PSTN participant minutes</span></span>
    
<span data-ttu-id="1cd5e-138">除了"系统使用情况"指标之外，如果选择"周视图) "，则以下指标显示当天和前六天 (如果选择了"周视图) "，或者如果选择"每月视图"，则显示当前周和过去六周的总 **时间**。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-138">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>
  
## <a name="per-user-call-diagnostics"></a><span data-ttu-id="1cd5e-139">Per-User呼叫诊断</span><span class="sxs-lookup"><span data-stu-id="1cd5e-139">Per-User Call Diagnostics</span></span>

 <span data-ttu-id="1cd5e-140">**呼叫失败的用户**</span><span class="sxs-lookup"><span data-stu-id="1cd5e-140">**Users with call failures**</span></span>
  
- <span data-ttu-id="1cd5e-141">呼叫失败的用户总数</span><span class="sxs-lookup"><span data-stu-id="1cd5e-141">Total users with call failures</span></span>
    
- <span data-ttu-id="1cd5e-142">呼叫失败的会议组织者</span><span class="sxs-lookup"><span data-stu-id="1cd5e-142">Conference organizers with call failures</span></span>
    
  <span data-ttu-id="1cd5e-143">**通话质量欠佳的用户**</span><span class="sxs-lookup"><span data-stu-id="1cd5e-143">**Users with poor quality calls**</span></span>
  
- <span data-ttu-id="1cd5e-144">质量欠佳呼叫的用户总数</span><span class="sxs-lookup"><span data-stu-id="1cd5e-144">Total users with poor quality calls</span></span>
    
## <a name="call-diagnostics"></a><span data-ttu-id="1cd5e-145">呼叫诊断</span><span class="sxs-lookup"><span data-stu-id="1cd5e-145">Call Diagnostics</span></span>

<span data-ttu-id="1cd5e-146">对等</span><span class="sxs-lookup"><span data-stu-id="1cd5e-146">Peer-to-peer</span></span>
  
- <span data-ttu-id="1cd5e-147">总失败数</span><span class="sxs-lookup"><span data-stu-id="1cd5e-147">Total failures</span></span>
    
- <span data-ttu-id="1cd5e-148">总体故障率</span><span class="sxs-lookup"><span data-stu-id="1cd5e-148">Overall failure rate</span></span>
    
- <span data-ttu-id="1cd5e-149">IM 故障率</span><span class="sxs-lookup"><span data-stu-id="1cd5e-149">IM failure rate</span></span>
    
- <span data-ttu-id="1cd5e-150">音频故障率</span><span class="sxs-lookup"><span data-stu-id="1cd5e-150">Audio failure rate</span></span>
    
- <span data-ttu-id="1cd5e-151">应用程序共享失败率</span><span class="sxs-lookup"><span data-stu-id="1cd5e-151">Application sharing failure rate</span></span>
    
<span data-ttu-id="1cd5e-152">会议</span><span class="sxs-lookup"><span data-stu-id="1cd5e-152">Conference</span></span>
  
- <span data-ttu-id="1cd5e-153">总失败数</span><span class="sxs-lookup"><span data-stu-id="1cd5e-153">Total failures</span></span>
    
- <span data-ttu-id="1cd5e-154">总体故障率</span><span class="sxs-lookup"><span data-stu-id="1cd5e-154">Overall failure rate</span></span>
    
- <span data-ttu-id="1cd5e-155">IM 故障率</span><span class="sxs-lookup"><span data-stu-id="1cd5e-155">IM failure rate</span></span>
    
- <span data-ttu-id="1cd5e-156">A/V 故障率</span><span class="sxs-lookup"><span data-stu-id="1cd5e-156">A/V failure rate</span></span>
    
- <span data-ttu-id="1cd5e-157">应用程序共享失败率</span><span class="sxs-lookup"><span data-stu-id="1cd5e-157">Application sharing failure rate</span></span>
    
<span data-ttu-id="1cd5e-158">按失败会话数排名前五的服务器</span><span class="sxs-lookup"><span data-stu-id="1cd5e-158">Top five servers by failed sessions</span></span>
  
## <a name="media-quality-diagnostics"></a><span data-ttu-id="1cd5e-159">媒体质量诊断</span><span class="sxs-lookup"><span data-stu-id="1cd5e-159">Media Quality Diagnostics</span></span>

<span data-ttu-id="1cd5e-160">对等</span><span class="sxs-lookup"><span data-stu-id="1cd5e-160">Peer-to-peer</span></span>
  
- <span data-ttu-id="1cd5e-161">质量欠佳的呼叫总数</span><span class="sxs-lookup"><span data-stu-id="1cd5e-161">Total poor quality calls</span></span>
    
- <span data-ttu-id="1cd5e-162">质量欠佳的呼叫百分比</span><span class="sxs-lookup"><span data-stu-id="1cd5e-162">Poor quality call percentage</span></span>
    
- <span data-ttu-id="1cd5e-163">质量较差的 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="1cd5e-163">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="1cd5e-164">会议</span><span class="sxs-lookup"><span data-stu-id="1cd5e-164">Conference</span></span>
  
- <span data-ttu-id="1cd5e-165">质量欠佳的呼叫总数</span><span class="sxs-lookup"><span data-stu-id="1cd5e-165">Total poor quality calls</span></span>
    
- <span data-ttu-id="1cd5e-166">质量欠佳的呼叫百分比</span><span class="sxs-lookup"><span data-stu-id="1cd5e-166">Poor quality call percentage</span></span>
    
- <span data-ttu-id="1cd5e-167">质量较差的 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="1cd5e-167">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="1cd5e-168">质量欠佳的呼叫百分比表示最差的服务器</span><span class="sxs-lookup"><span data-stu-id="1cd5e-168">Top worst servers by poor quality call percentage</span></span>
  
## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="1cd5e-169">使用监控仪表板</span><span class="sxs-lookup"><span data-stu-id="1cd5e-169">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="1cd5e-170">如前所述，默认情况下显示本周汇总，并显示过去六周的趋势值。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-170">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks.</span></span> <span data-ttu-id="1cd5e-171">如果更希望查看当月 (以及) 过去六个月的趋势值，请单击仪表板右上角的"每月视图"链接。 </span><span class="sxs-lookup"><span data-stu-id="1cd5e-171">If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard.</span></span> <span data-ttu-id="1cd5e-172">如果你决定查看每月总计，链接文本将更改为每周 **视图**。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-172">If you decide to view monthly totals, the link text will change to **Weekly View**.</span></span> <span data-ttu-id="1cd5e-173">可以通过单击该链接切换回每周视图。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-173">You can switch back to the weekly view by clicking that link.</span></span>
  
> [!TIP]
> <span data-ttu-id="1cd5e-174">监控仪表板限制您查看当前周 (或) 的汇总以及过去六周或)  (的趋势) 。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-174">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months).</span></span> <span data-ttu-id="1cd5e-175">您不能更改这些日期和时间。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-175">You cannot change these dates and times.</span></span> <span data-ttu-id="1cd5e-176">例如，不能使用仪表板查看从 9 个月之前开始的时间段的报告总计。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-176">For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span> 
  
<span data-ttu-id="1cd5e-177">"本周、本月"或"今天"列中显示的值将链接至有关该项目的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-177">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item.</span></span> <span data-ttu-id="1cd5e-178">请记住，列名称和显示在该列中的值通常因选择的指标以及选择每周视图还是按月视图而不同。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-178">Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view.</span></span> <span data-ttu-id="1cd5e-179">例如，如果单击"唯一用户登录数"指标显示的总计，将看到指定时间段的用户注册报告。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-179">For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period.</span></span> <span data-ttu-id="1cd5e-180">通过单击"仪表板"，您随时都可以返回到监控 **仪表板**。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-180">You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>
  
> [!TIP]
> <span data-ttu-id="1cd5e-181">您还可以通过单击仪表板右上角的"报告"链接访问监控服务器报告主页。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-181">You can also access the Monitoring Server Reports home page by clicking the **Reports** link in the upper right corner of the Dashboard.</span></span>
  
<span data-ttu-id="1cd5e-182">" **趋势** "列显示一个简单的直线图，显示过去六周或过去六 (，或者根据指标和时间间隔，显示过去六天或过去六个月的) 。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-182">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months).</span></span> <span data-ttu-id="1cd5e-183">这些简单的线图针对每个时间段显示一个未标记的 (例如，过去六周内每个时间段的一个未标记) 。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-183">These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks).</span></span> <span data-ttu-id="1cd5e-184">但是，可以通过将鼠标指针悬停在图形上来检索这些图形的实际值。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-184">However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph.</span></span> <span data-ttu-id="1cd5e-185">在这种情况下，工具提示会显示图形中的最大值和最小值。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-185">In that case, a tool tip shows you the maximum and minimum values in the graph.</span></span>
  
## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="1cd5e-186">从监控仪表板导出数据</span><span class="sxs-lookup"><span data-stu-id="1cd5e-186">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="1cd5e-187">监控仪表板提供了多种导出当前仪表板视图的方法。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-187">The Monitoring Dashboard provides a number of ways to export the current dashboard view.</span></span> <span data-ttu-id="1cd5e-188">在仪表板工具栏上，你将看到一个看起来像软盘的图标，并附带一个绿色箭头。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-188">On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it.</span></span> <span data-ttu-id="1cd5e-189">如果单击此图标，将显示一个下拉列表，为您提供以下数据导出格式：</span><span class="sxs-lookup"><span data-stu-id="1cd5e-189">If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>
  
- <span data-ttu-id="1cd5e-190">具有报告数据的 XML 文件</span><span class="sxs-lookup"><span data-stu-id="1cd5e-190">XML file with report data</span></span>
    
- <span data-ttu-id="1cd5e-191">CSV（逗号分隔）</span><span class="sxs-lookup"><span data-stu-id="1cd5e-191">CSV (comma delimited)</span></span>
    
- <span data-ttu-id="1cd5e-192">PDF</span><span class="sxs-lookup"><span data-stu-id="1cd5e-192">PDF</span></span>
    
- <span data-ttu-id="1cd5e-193">MHTML（Web 存档）</span><span class="sxs-lookup"><span data-stu-id="1cd5e-193">MHTML (web archive)</span></span>
    
- <span data-ttu-id="1cd5e-194">Excel</span><span class="sxs-lookup"><span data-stu-id="1cd5e-194">Excel</span></span>
    
- <span data-ttu-id="1cd5e-195">TIFF 文件</span><span class="sxs-lookup"><span data-stu-id="1cd5e-195">TIFF file</span></span>
    
- <span data-ttu-id="1cd5e-196">Word</span><span class="sxs-lookup"><span data-stu-id="1cd5e-196">Word</span></span>
    
<span data-ttu-id="1cd5e-197">若要导出当前仪表板视图 (及其值) ，请单击所需的导出选项。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-197">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="1cd5e-198">Skype for Business Server 生成指定格式的报告，然后为您提供打开或保存该报告的选项。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-198">Skype for Business Server generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="1cd5e-199">请注意，默认情况下，Skype for Business Server 将报告标题设置为"监控仪表板"，并保存到"下载"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-199">Note that, by default, Skype for Business Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="1cd5e-200">若要为报表指定其他名称或将其存储在不同的文件夹中，请单击"保存"按钮旁边的箭头，然后单击"另 **存为"。**</span><span class="sxs-lookup"><span data-stu-id="1cd5e-200">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="1cd5e-201">如果名称监控仪表板和将报告保存在"下载"文件夹中，只需单击"保存 **"** 按钮即可。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-201">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>
  
<span data-ttu-id="1cd5e-202">当您尝试导出仪表板数据时，可能会显示"安全警报"对话框以及消息"当前设置不允许下载此文件"。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-202">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded."</span></span> <span data-ttu-id="1cd5e-203">如果发生这种情况，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="1cd5e-203">If that occurs, do the following:</span></span>
  
- <span data-ttu-id="1cd5e-204">在Internet Explorer中，选择 **"Internet 选项"。**</span><span class="sxs-lookup"><span data-stu-id="1cd5e-204">In Internet Explorer, select **Internet Options**.</span></span>
    
- <span data-ttu-id="1cd5e-205">在 **"Internet 选项**"对话框中的"安全"选项卡上，单击"**受信任的** 站点"，然后单击"站点 **"。**</span><span class="sxs-lookup"><span data-stu-id="1cd5e-205">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>
    
- <span data-ttu-id="1cd5e-206">在"**受信任的站点"** 对话框中，单击"添加"以将运行 Skype for Business Server 报表的 Skype for Business Server 添加到受信任网站的集合。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-206">In the **Trusted sites** dialog box, click **Add** to add the Skype for Business Server that is running Skype for Business Server Reports to the collections of trusted websites.</span></span>
    
- <span data-ttu-id="1cd5e-207">单击 **"关闭**"，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="1cd5e-207">Click **Close** and then click **OK**.</span></span>
    
<span data-ttu-id="1cd5e-208">然后，您需要刷新监控仪表板，更改才能生效。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-208">You will then need to refresh the Monitoring Dashboard before the changes take effect.</span></span> <span data-ttu-id="1cd5e-209">为此，请按 F5 或单击仪表板工具栏中的 **"** 刷新"图标。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-209">To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar.</span></span> <span data-ttu-id="1cd5e-210"> (**刷新图标** 是一个圆形，其中有一对绿色箭头。) </span><span class="sxs-lookup"><span data-stu-id="1cd5e-210">(The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>
  
<span data-ttu-id="1cd5e-211">还可以创建包含实时数据源的 Excel 电子表格，其中包含指向最新监控仪表板数据的链接。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-211">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data.</span></span> <span data-ttu-id="1cd5e-212">若要创建实时数据馈送文件，请单击工具栏中的橙色 **"导出到数据源** "图标。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-212">To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>
  
<span data-ttu-id="1cd5e-213">如果希望打印当前仪表板，请单击工具栏中的打印机图标。</span><span class="sxs-lookup"><span data-stu-id="1cd5e-213">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>
