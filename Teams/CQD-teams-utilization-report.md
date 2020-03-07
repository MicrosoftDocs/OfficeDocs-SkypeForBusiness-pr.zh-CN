---
title: 使用 CQD 数据在 Power BI 中查看 Microsoft 团队的利用率
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: 使用 "团队利用率 Power BI" 报表跟踪组织中的 Microsoft 团队使用情况。
ms.openlocfilehash: d22f37bb230ecbaa3cf6c33c2ba43f5ea92afaad
ms.sourcegitcommit: 98fcfc03c55917d0aca48b7bd97988f81e8930c1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2020
ms.locfileid: "42559387"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a><span data-ttu-id="9c05d-103">使用 CQD 数据在 Power BI 中查看 Microsoft 团队的利用率</span><span class="sxs-lookup"><span data-stu-id="9c05d-103">View Microsoft Teams utilization in Power BI using CQD data</span></span>

<span data-ttu-id="9c05d-104">2020年3月新增功能，我们已将团队使用情况报告添加到可下载[的 POWER BI 查询模板 FOR CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="9c05d-104">New in March 2020, we've added a Teams Utilization report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 

<span data-ttu-id="9c05d-105">此新团队使用情况报表使你可以查看你的用户使用 Microsoft 团队的方式（以及多少）。</span><span class="sxs-lookup"><span data-stu-id="9c05d-105">This new Teams Utilization reports lets you see how (and how much) your users are using Microsoft Teams.</span></span> <span data-ttu-id="9c05d-106">这些报表旨在作为中心位置，供管理员和业务负责人快速访问此数据。</span><span class="sxs-lookup"><span data-stu-id="9c05d-106">These reports are intended to be a centralized location that both administrators and business leaders can quickly go to for this data.</span></span>

<span data-ttu-id="9c05d-107">"团队利用率 Power BI" 报表包含两个主要报表： "**[通话计数摘要](#call-count-summary-report)**" 和 "**[音频分钟摘要](#audio-minutes-summary-report)**"。</span><span class="sxs-lookup"><span data-stu-id="9c05d-107">The Teams Utilization Power BI report consists of two primary reports: **[Call Count Summary](#call-count-summary-report)** and **[Audio Minutes Summary](#audio-minutes-summary-report)**.</span></span> <span data-ttu-id="9c05d-108">当用户利用分级式报告时，将在 "[每日使用情况](#daily-usage)" 和 "[区域音频详细信息](#regional-audio-details)" 报告中进行播放，请注意下面的说明。</span><span class="sxs-lookup"><span data-stu-id="9c05d-108">The [Daily Usage](#daily-usage) and [Regional Audio Details](#regional-audio-details) reports come into play when a user takes advantage of the drill-down reports, noted in the descriptions below.</span></span>

> [!NOTE]
> <span data-ttu-id="9c05d-109">必须填充构建和子网数据才能提供区域和网络筛选功能。</span><span class="sxs-lookup"><span data-stu-id="9c05d-109">Building and subnet data must be populated to provide regional and network filtering capabilities.</span></span>

## <a name="call-count-summary-report"></a><span data-ttu-id="9c05d-110">通话计数摘要报告</span><span class="sxs-lookup"><span data-stu-id="9c05d-110">Call Count Summary Report</span></span>

<span data-ttu-id="9c05d-111">主页面（"呼叫计数摘要"）立即提供最近30日和90天内的音频、视频和屏幕共享会话数，如部分标题中所述。</span><span class="sxs-lookup"><span data-stu-id="9c05d-111">The main page (Call Count Summary) immediately provides the number of audio, video and screen sharing sessions over the last 30 and 90 days as noted in the section title.</span></span> <span data-ttu-id="9c05d-112">最初显示的数据适用于整个组织，并且可以使用页面左侧的切片器下拉选项进行筛选。</span><span class="sxs-lookup"><span data-stu-id="9c05d-112">The data initially displayed is for the organization as a whole and can be filtered using the slicer dropdown options on the left side of the page.</span></span>

![屏幕截图：拨打县摘要报告](media/CQD-teams-utilization-report1.png)

1. <span data-ttu-id="9c05d-114">在切片器下拉的右侧，媒体类型的调用次数将在过去30天内分解为内部/外部视图。</span><span class="sxs-lookup"><span data-stu-id="9c05d-114">To the right of the slicer dropdowns, the number of calls by media type is broken down to an internal/external view over the past thirty days.</span></span> <span data-ttu-id="9c05d-115">通过上面的屏幕截图，我们可以看到来自外部组织位置的更多通话，这对考虑当前的全球环境很有意义。</span><span class="sxs-lookup"><span data-stu-id="9c05d-115">We can see through the above screenshot that there are more calls happening from outside organizational locations, which makes sense considering the current global environment.</span></span>
  <span data-ttu-id="9c05d-116">![屏幕截图：拨打县摘要报告](media/CQD-teams-utilization-report2.png)</span><span class="sxs-lookup"><span data-stu-id="9c05d-116">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report2.png)</span></span>

1. <span data-ttu-id="9c05d-117">在 "媒体类型计数" 框的右侧，我们有 "每月通话计数"，"媒体类型" 是过去90天的媒体类型。</span><span class="sxs-lookup"><span data-stu-id="9c05d-117">To the right of the media type count box, we have the Monthly Call Count by Media Type for the last 90 days.</span></span> <span data-ttu-id="9c05d-118">每个列和媒体类型都可以悬停在上方，以显示上个月或当前月份的计数，从而提供使用趋势信息。</span><span class="sxs-lookup"><span data-stu-id="9c05d-118">Each column and media type can be hovered over to display the count for a previous month or the current month to date, providing usage trend information.</span></span>
  <span data-ttu-id="9c05d-119">![屏幕截图：拨打县摘要报告](media/CQD-teams-utilization-report3.png)</span><span class="sxs-lookup"><span data-stu-id="9c05d-119">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report3.png)</span></span>

1. <span data-ttu-id="9c05d-120">中间图按90天的图表运行，但它提供过去30天的 "每日使用状况" 视图，并允许用户右键单击并向下钻取特定日期的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9c05d-120">The middle graph functions as the 90-day graph does, however it provides a daily usage view for the past 30 days and allows a user to right click and drill down into details for a specific day.</span></span>
  <span data-ttu-id="9c05d-121">![屏幕截图：拨打县摘要报告](media/CQD-teams-utilization-report4.png)</span><span class="sxs-lookup"><span data-stu-id="9c05d-121">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report4.png)</span></span>

<span data-ttu-id="9c05d-122">在页面的左下部分，你将找到一个表，其中提供了过去一年的每种媒体类型的总值。</span><span class="sxs-lookup"><span data-stu-id="9c05d-122">On the bottom left section of the page, you'll find a table providing total values for each media type over the past year.</span></span> 
    <span data-ttu-id="9c05d-123">![屏幕截图：拨打县摘要报告](media/CQD-teams-utilization-report5.png)</span><span class="sxs-lookup"><span data-stu-id="9c05d-123">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report5.png)</span></span>
  
<span data-ttu-id="9c05d-124">该表还有一个可用的向下钻取功能，您可以在其中看到区域数据细目。</span><span class="sxs-lookup"><span data-stu-id="9c05d-124">The table also has an available drill down where you can see a regional data breakdown.</span></span>
    <span data-ttu-id="9c05d-125">![屏幕截图：拨打县摘要报告](media/CQD-teams-utilization-report6.png)</span><span class="sxs-lookup"><span data-stu-id="9c05d-125">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report6.png)</span></span>

<span data-ttu-id="9c05d-126">在表右侧，条形图显示过去30天内最常用的客户端（"调用/流"）。</span><span class="sxs-lookup"><span data-stu-id="9c05d-126">To the right of the table, a bar chart shows clients with the most use (calls/streams) for the past 30 days.</span></span>
   <span data-ttu-id="9c05d-127">![屏幕截图：拨打县摘要报告](media/CQD-teams-utilization-report7.png)</span><span class="sxs-lookup"><span data-stu-id="9c05d-127">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report7.png)</span></span>


<span data-ttu-id="9c05d-128">此页面的最后一组图表分别显示每种媒体类型，并显示 "会议和 P2P 使用情况" 细目。</span><span class="sxs-lookup"><span data-stu-id="9c05d-128">The last set of charts for this page show each media type individually, with a breakdown showing conference and P2P usage.</span></span> <span data-ttu-id="9c05d-129">下面的图表显示，与 P2P 相比，有明显更高的会议使用次数。</span><span class="sxs-lookup"><span data-stu-id="9c05d-129">The charts below show that there is a significantly higher number of conference usage as compared to P2P.</span></span>
  <span data-ttu-id="9c05d-130">![屏幕截图：拨打县摘要报告](media/CQD-teams-utilization-report8.png)</span><span class="sxs-lookup"><span data-stu-id="9c05d-130">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report8.png)</span></span>

## <a name="audio-minutes-summary-report"></a><span data-ttu-id="9c05d-131">音频分钟摘要报告</span><span class="sxs-lookup"><span data-stu-id="9c05d-131">Audio Minutes Summary Report</span></span>

<span data-ttu-id="9c05d-132">在 "音频分钟使用情况" 报表上，通过几种不同的视图提供总分钟使用率。</span><span class="sxs-lookup"><span data-stu-id="9c05d-132">On the Audio Minutes usage report, the total minute usage is provided through a few different views.</span></span> 

<span data-ttu-id="9c05d-133">我们在切片器的旁边显示了三十天的使用摘要，很容易使用文本框。</span><span class="sxs-lookup"><span data-stu-id="9c05d-133">We have the thirty-day usage summary shown next to the slicers as easy to consume text boxes.</span></span> <span data-ttu-id="9c05d-134">顶部数字显示三十天的合计，其中包含内部和外部细目。</span><span class="sxs-lookup"><span data-stu-id="9c05d-134">The top number shows the thirty-day total, with internal and external breakdowns below that.</span></span>

![屏幕截图：拨打县摘要报告](media/CQD-teams-utilization-report9.png)

<span data-ttu-id="9c05d-136">顶部右上条图提供了一个 yearlong 的会议音频使用视图。</span><span class="sxs-lookup"><span data-stu-id="9c05d-136">The top right bar graph provides a yearlong view of conference audio usage.</span></span> <span data-ttu-id="9c05d-137">将鼠标悬停在月份上可显示会议音频分钟数。</span><span class="sxs-lookup"><span data-stu-id="9c05d-137">Hover over the month to show the conference audio minutes.</span></span>

<span data-ttu-id="9c05d-138">为了显示 P2P 和会议音频的差异，底部左图获取过去一年的所有音频，并将其在两种类型之间分隔。</span><span class="sxs-lookup"><span data-stu-id="9c05d-138">To show the difference in P2P and conference audio, the bottom left chart takes all audio for the past year and breaks it up between the two types.</span></span>

<span data-ttu-id="9c05d-139">![屏幕截图：拨打 "县](media/CQD-teams-utilization-report10.png) " 摘要报告 "音频分钟" 页面的最后一个图表显示全局地图覆盖上的音频分钟使用率。</span><span class="sxs-lookup"><span data-stu-id="9c05d-139">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report10.png) The last chart for the Audio minutes page shows audio minute usage on a global map overlay.</span></span> <span data-ttu-id="9c05d-140">只有在将生成和子网数据上载到租户时，此图表才起作用。</span><span class="sxs-lookup"><span data-stu-id="9c05d-140">This chart will only work if building and subnet data is uploaded to the tenant.</span></span> <span data-ttu-id="9c05d-141">可以深化地图上的饼图覆盖层，然后提供区域音频使用。</span><span class="sxs-lookup"><span data-stu-id="9c05d-141">The pie chart overlay on the map can be drilled into, subsequently providing regional audio usage.</span></span>

![屏幕截图：拨打县摘要报告](media/CQD-teams-utilization-report11.png)

## <a name="drill-through-capabilities"></a><span data-ttu-id="9c05d-143">钻取功能</span><span class="sxs-lookup"><span data-stu-id="9c05d-143">Drill-through capabilities</span></span>

<span data-ttu-id="9c05d-144">如前面所述，用户可以深入查看每日和地区使用情况报告。</span><span class="sxs-lookup"><span data-stu-id="9c05d-144">As previously noted, users can drill into the daily and regional usage reports.</span></span>

### <a name="daily-usage"></a><span data-ttu-id="9c05d-145">每日使用</span><span class="sxs-lookup"><span data-stu-id="9c05d-145">Daily Usage</span></span>

<span data-ttu-id="9c05d-146">"每日使用情况" 报表允许管理员通过一天的时间标识高峰期。</span><span class="sxs-lookup"><span data-stu-id="9c05d-146">The Daily Usage report allows an administrator to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="9c05d-147">除了使用，我们还能够捕获整个用户情绪和该天的反馈。</span><span class="sxs-lookup"><span data-stu-id="9c05d-147">In addition to usage, we are also able to capture overall user sentiment and feedback for that day.</span></span>

![屏幕截图：拨打县摘要报告](media/CQD-teams-utilization-report12.png)

<span data-ttu-id="9c05d-149">此数据可用于识别在高峰使用期间出现问题的区域。</span><span class="sxs-lookup"><span data-stu-id="9c05d-149">This data can be used to identify regions having problems during peak consumption times.</span></span>

1.  <span data-ttu-id="9c05d-150">在 "通话计数摘要" 页面上，在特定日期钻取。</span><span class="sxs-lookup"><span data-stu-id="9c05d-150">On the Call Count Summary page, drill-through on a specific date.</span></span> <span data-ttu-id="9c05d-151">查看每天的每小时趋势，了解高峰使用率。</span><span class="sxs-lookup"><span data-stu-id="9c05d-151">Look at the hourly trend that day to find the peak utilization.</span></span>
  <span data-ttu-id="9c05d-152">![屏幕截图：拨打县摘要报告](media/CQD-teams-utilization-report13.png)</span><span class="sxs-lookup"><span data-stu-id="9c05d-152">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report13.png)</span></span>

2.  <span data-ttu-id="9c05d-153">单击该日期的列以显示该小时的度量值。</span><span class="sxs-lookup"><span data-stu-id="9c05d-153">Click on the column for that day to display metrics for that hour.</span></span>
  <span data-ttu-id="9c05d-154">![屏幕截图：拨打县摘要报告](media/CQD-teams-utilization-report14.png)</span><span class="sxs-lookup"><span data-stu-id="9c05d-154">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report14.png)</span></span>
    
    1.  <span data-ttu-id="9c05d-155">图表下方的表将显示该小时的度量值。</span><span class="sxs-lookup"><span data-stu-id="9c05d-155">The table below the chart will display the metrics for that hour.</span></span> <span data-ttu-id="9c05d-156">这可以按任何列标题进行排序;但是，我们会对查找有问题的区域感兴趣。</span><span class="sxs-lookup"><span data-stu-id="9c05d-156">This can be sorted by any column header; however, we would be interested in finding problematic areas.</span></span>  
        ![屏幕截图：拨打县摘要报告](media/CQD-teams-utilization-report15.png)
    
    2.  <span data-ttu-id="9c05d-158">我们看到，在此时间范围内，IND 区域在会议中的视频性能很差。</span><span class="sxs-lookup"><span data-stu-id="9c05d-158">We see that the IND region is experiencing poor video performance in conferences during this time frame.</span></span> <span data-ttu-id="9c05d-159">随后，CQD QER Microsoft 报表可用于缩小有问题的位置，因为区域和时间框架已确定。</span><span class="sxs-lookup"><span data-stu-id="9c05d-159">Subsequently, the CQD QER Microsoft reports can be used to narrow down the problematic location as the region and time frame has been identified.</span></span>

### <a name="regional-audio-details"></a><span data-ttu-id="9c05d-160">区域音频详细信息</span><span class="sxs-lookup"><span data-stu-id="9c05d-160">Regional Audio Details</span></span>

<span data-ttu-id="9c05d-161">区域音频详细信息 "向下钻取" 特别显示所选区域的音频分钟用量。</span><span class="sxs-lookup"><span data-stu-id="9c05d-161">The Regional Audio Details drill down specifically shows the audio minute usage for the selected region.</span></span> <span data-ttu-id="9c05d-162">具有 CQD 访问权限的用户可以查看所选区域内的 P2P 和会议音频的使用趋势。</span><span class="sxs-lookup"><span data-stu-id="9c05d-162">Users with access to CQD can see usage trends for both P2P and conference audio within the selected region.</span></span>

1.  <span data-ttu-id="9c05d-163">在 "通话计数摘要" 页面上，通过表格钻取到 "特定区域"。</span><span class="sxs-lookup"><span data-stu-id="9c05d-163">On the Call Count Summary page, drill-through to as specific region through the table.</span></span>
  <span data-ttu-id="9c05d-164">![屏幕截图：拨打县摘要报告](media/CQD-teams-utilization-report16.png)</span><span class="sxs-lookup"><span data-stu-id="9c05d-164">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report16.png)</span></span>

2.  <span data-ttu-id="9c05d-165">选择需要其他区域信息的行。</span><span class="sxs-lookup"><span data-stu-id="9c05d-165">Select the row with the region additional information is needed for.</span></span>
  <span data-ttu-id="9c05d-166">![屏幕截图：拨打县摘要报告](media/CQD-teams-utilization-report17.png)</span><span class="sxs-lookup"><span data-stu-id="9c05d-166">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report17.png)</span></span>

3.  <span data-ttu-id="9c05d-167">数据趋势显示在内部网络上使用了很长的分钟数，并且会议的 P2P 使用远达超越 P2P。</span><span class="sxs-lookup"><span data-stu-id="9c05d-167">The data trends show a significant number of minutes being used on the internal network, with conferencing far surpassing P2P use.</span></span>
  <span data-ttu-id="9c05d-168">![屏幕截图：拨打县摘要报告](media/CQD-teams-utilization-report18.png)</span><span class="sxs-lookup"><span data-stu-id="9c05d-168">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report18.png)</span></span>

<span data-ttu-id="9c05d-169">区域音频趋势可用于显示世界上的外部影响对用户有何影响。</span><span class="sxs-lookup"><span data-stu-id="9c05d-169">The regional audio trend can be used to show how users are impacted by external influences in the world.</span></span> <span data-ttu-id="9c05d-170">具体地说，我们将看到 EMEA 地区和 APAC 地区的外部使用情况，以便与要求远程工作的人一起增加。</span><span class="sxs-lookup"><span data-stu-id="9c05d-170">Specifically, right now, we would expect to see the external usage for the EMEA and APAC regions to increase with people being asked to work remotely.</span></span>



## <a name="related-topics"></a><span data-ttu-id="9c05d-171">相关主题</span><span class="sxs-lookup"><span data-stu-id="9c05d-171">Related topics</span></span>

[<span data-ttu-id="9c05d-172">通话质量仪表板中可用的维度和衡量指标</span><span class="sxs-lookup"><span data-stu-id="9c05d-172">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="9c05d-173">通话质量仪表板中的流分类</span><span class="sxs-lookup"><span data-stu-id="9c05d-173">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="9c05d-174">设置 Skype for Business 通话分析</span><span class="sxs-lookup"><span data-stu-id="9c05d-174">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="9c05d-175">使用通话分析来排查通话质量不良问题</span><span class="sxs-lookup"><span data-stu-id="9c05d-175">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="9c05d-176">通话分析和通话质量仪表板</span><span class="sxs-lookup"><span data-stu-id="9c05d-176">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)
 