---
title: 使用 CQD 数据在 Power BI 中查看 Microsoft 团队的利用率
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: 使用 "团队使用 Power BI BI 报表" 访问 Microsoft 团队通话质量仪表板 (CQD) 数据以跟踪您的组织中的 Microsoft 团队使用情况。
ms.openlocfilehash: bda89f3715997016e6c1bea242dcf6b8b182c6bf
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581543"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a><span data-ttu-id="b49ae-103">使用 CQD 数据在 Power BI 中查看 Microsoft 团队的利用率</span><span class="sxs-lookup"><span data-stu-id="b49ae-103">View Microsoft Teams utilization in Power BI using CQD data</span></span>

<span data-ttu-id="b49ae-104">2020年3月新增功能，我们已将团队使用情况报告添加到可下载[的 POWER BI 查询模板 FOR CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="b49ae-104">New in March 2020, we've added a Teams Utilization report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 

<span data-ttu-id="b49ae-105">这一新的团队使用情况报告让你可以通过访问团队通话质量仪表板 (CQD) 数据，了解 (和你的用户使用 Microsoft 团队) 的程度。</span><span class="sxs-lookup"><span data-stu-id="b49ae-105">This new Teams Utilization reports lets you see how (and how much) your users are using Microsoft Teams by accessing Teams Call Quality Dashboard (CQD) data.</span></span> <span data-ttu-id="b49ae-106">这些报表旨在作为中心位置，供管理员和业务负责人快速访问此数据。</span><span class="sxs-lookup"><span data-stu-id="b49ae-106">These reports are intended to be a centralized location that both administrators and business leaders can quickly go to for this data.</span></span>

<span data-ttu-id="b49ae-107">"团队利用率 Power BI" 报表包含两个主要报表： "**[通话计数摘要](#call-count-summary-report)**" 和 "**[音频分钟摘要](#audio-minutes-summary-report)**"。</span><span class="sxs-lookup"><span data-stu-id="b49ae-107">The Teams Utilization Power BI report consists of two primary reports: **[Call Count Summary](#call-count-summary-report)** and **[Audio Minutes Summary](#audio-minutes-summary-report)**.</span></span> <span data-ttu-id="b49ae-108">[每日使用情况](#daily-usage)、[区域音频详细信息](#regional-audio-details)、[会议详细信息](#conference-details)和[用户列表](#user-list)报告在用户利用分级式报告（如下所述的说明）中时，将会播放。</span><span class="sxs-lookup"><span data-stu-id="b49ae-108">The [Daily Usage](#daily-usage), [Regional Audio Details](#regional-audio-details), [Conference Details](#conference-details) and [User List](#user-list) reports come into play when a user takes advantage of the drill-down reports, noted in the descriptions below.</span></span>

> [!NOTE]
> <span data-ttu-id="b49ae-109">必须填充构建和子网数据才能提供区域和网络筛选功能。</span><span class="sxs-lookup"><span data-stu-id="b49ae-109">Building and subnet data must be populated to provide regional and network filtering capabilities.</span></span>

## <a name="call-count-summary-report"></a><span data-ttu-id="b49ae-110">通话计数摘要报告</span><span class="sxs-lookup"><span data-stu-id="b49ae-110">Call Count Summary Report</span></span>

<span data-ttu-id="b49ae-111">主页面 ("呼叫计数摘要") 立即提供最近30日和90天内的音频、视频和屏幕共享会话数（如节标题中所述）。</span><span class="sxs-lookup"><span data-stu-id="b49ae-111">The main page (Call Count Summary) immediately provides the number of audio, video and screen sharing sessions over the last 30 and 90 days as noted in the section title.</span></span> <span data-ttu-id="b49ae-112">最初显示的数据适用于整个组织，并且可以使用页面左侧的切片器下拉选项进行筛选。</span><span class="sxs-lookup"><span data-stu-id="b49ae-112">The data initially displayed is for the organization as a whole and can be filtered using the slicer dropdown options on the left side of the page.</span></span>

![屏幕截图：团队使用率报告](media/CQD-teams-utilization-report1.png)

1. <span data-ttu-id="b49ae-114">在切片器下拉的右侧，媒体类型的调用次数将在过去30天内分解为内部/外部视图。</span><span class="sxs-lookup"><span data-stu-id="b49ae-114">To the right of the slicer dropdowns, the number of calls by media type is broken down to an internal/external view over the past thirty days.</span></span> <span data-ttu-id="b49ae-115">通过上面的屏幕截图，我们可以看到来自外部组织位置的更多通话，这对考虑当前的全球环境很有意义。</span><span class="sxs-lookup"><span data-stu-id="b49ae-115">We can see through the above screenshot that there are more calls happening from outside organizational locations, which makes sense considering the current global environment.</span></span>
  <span data-ttu-id="b49ae-116">![屏幕截图：团队使用率报告](media/CQD-teams-utilization-report2.png)</span><span class="sxs-lookup"><span data-stu-id="b49ae-116">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report2.png)</span></span>

1. <span data-ttu-id="b49ae-117">在 "媒体类型计数" 框的右侧，我们有 "每月通话计数"，"媒体类型" 是过去90天的媒体类型。</span><span class="sxs-lookup"><span data-stu-id="b49ae-117">To the right of the media type count box, we have the Monthly Call Count by Media Type for the last 90 days.</span></span> <span data-ttu-id="b49ae-118">每个列和媒体类型都可以悬停在上方，以显示上个月或当前月份的计数，从而提供使用趋势信息。</span><span class="sxs-lookup"><span data-stu-id="b49ae-118">Each column and media type can be hovered over to display the count for a previous month or the current month to date, providing usage trend information.</span></span>
  <span data-ttu-id="b49ae-119">![屏幕截图：团队使用率报告](media/CQD-teams-utilization-report3.png)</span><span class="sxs-lookup"><span data-stu-id="b49ae-119">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report3.png)</span></span>
 

1. <span data-ttu-id="b49ae-120">中间图按90天的图表运行，但它提供过去30天的 "每日使用状况" 视图，并允许用户右键单击并向下钻取特定日期的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b49ae-120">The middle graph functions as the 90-day graph does, however it provides a daily usage view for the past 30 days and allows a user to right click and drill down into details for a specific day.</span></span>
  <span data-ttu-id="b49ae-121">![屏幕截图：团队使用率报告](media/CQD-teams-utilization-report4.png)</span><span class="sxs-lookup"><span data-stu-id="b49ae-121">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report4.png)</span></span>

<span data-ttu-id="b49ae-122">在页面的左下部分，你将找到一个表，其中提供了过去一年的每种媒体类型的总值。</span><span class="sxs-lookup"><span data-stu-id="b49ae-122">On the bottom left section of the page, you'll find a table providing total values for each media type over the past year.</span></span> 
    <span data-ttu-id="b49ae-123">![屏幕截图：团队利用率报告 ](media/CQD-teams-utilization-report5.png) ![ 屏幕截图：团队利用率报告](media/CQD-teams-utilization-report6.png)</span><span class="sxs-lookup"><span data-stu-id="b49ae-123">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report5.png) ![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report6.png)</span></span>   

<span data-ttu-id="b49ae-124">在表的右侧，条形图显示过去30天内最常使用 (通话/流) 的客户。</span><span class="sxs-lookup"><span data-stu-id="b49ae-124">To the right of the table, a bar chart shows clients with the most use (calls/streams) for the past 30 days.</span></span>
   <span data-ttu-id="b49ae-125">![屏幕截图：团队使用率报告](media/CQD-teams-utilization-report7.png)</span><span class="sxs-lookup"><span data-stu-id="b49ae-125">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report7.png)</span></span>

<span data-ttu-id="b49ae-126">此页面的最后一组图表分别显示每种媒体类型，并显示 "会议和 P2P 使用情况" 细目。</span><span class="sxs-lookup"><span data-stu-id="b49ae-126">The last set of charts for this page show each media type individually, with a breakdown showing conference and P2P usage.</span></span> <span data-ttu-id="b49ae-127">下面的图表显示，与 P2P 相比，有明显更高的会议使用次数。</span><span class="sxs-lookup"><span data-stu-id="b49ae-127">The charts below show that there is a significantly higher number of conference usage as compared to P2P.</span></span>
  <span data-ttu-id="b49ae-128">![屏幕截图：团队使用率报告](media/CQD-teams-utilization-report8.png)</span><span class="sxs-lookup"><span data-stu-id="b49ae-128">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report8.png)</span></span>

## <a name="audio-minutes-summary-report"></a><span data-ttu-id="b49ae-129">音频分钟摘要报告</span><span class="sxs-lookup"><span data-stu-id="b49ae-129">Audio Minutes Summary Report</span></span>

<span data-ttu-id="b49ae-130">在 "音频分钟使用情况" 报表上，通过几种不同的视图提供总分钟使用率。</span><span class="sxs-lookup"><span data-stu-id="b49ae-130">On the Audio Minutes usage report, the total minute usage is provided through a few different views.</span></span> 

<span data-ttu-id="b49ae-131">我们在切片器的旁边显示了三十天的使用摘要，很容易使用文本框。</span><span class="sxs-lookup"><span data-stu-id="b49ae-131">We have the thirty-day usage summary shown next to the slicers as easy to consume text boxes.</span></span> <span data-ttu-id="b49ae-132">顶部数字显示三十天的合计，其中包含内部和外部细目。</span><span class="sxs-lookup"><span data-stu-id="b49ae-132">The top number shows the thirty-day total, with internal and external breakdowns below that.</span></span>

![屏幕截图：团队使用率报告](media/CQD-teams-utilization-report9.png)

<span data-ttu-id="b49ae-134">顶部右上条图提供了一个 yearlong 的会议音频使用视图。</span><span class="sxs-lookup"><span data-stu-id="b49ae-134">The top right bar graph provides a yearlong view of conference audio usage.</span></span> <span data-ttu-id="b49ae-135">将鼠标悬停在月份上可显示会议音频分钟数。</span><span class="sxs-lookup"><span data-stu-id="b49ae-135">Hover over the month to show the conference audio minutes.</span></span>

<span data-ttu-id="b49ae-136">为了显示 P2P 和会议音频的差异，底部左图获取过去一年的所有音频，并将其在两种类型之间分隔。</span><span class="sxs-lookup"><span data-stu-id="b49ae-136">To show the difference in P2P and conference audio, the bottom left chart takes all audio for the past year and breaks it up between the two types.</span></span>

![屏幕截图：团队使用率报告](media/CQD-teams-utilization-report10.png)

<span data-ttu-id="b49ae-138">"音频分钟" 页面的最后一个图表显示全局地图覆盖上的音频分钟使用率。</span><span class="sxs-lookup"><span data-stu-id="b49ae-138">The last chart for the Audio minutes page shows audio minute usage on a global map overlay.</span></span> <span data-ttu-id="b49ae-139">只有在将生成和子网数据上载到租户时，此图表才起作用。</span><span class="sxs-lookup"><span data-stu-id="b49ae-139">This chart will only work if building and subnet data is uploaded to the tenant.</span></span> <span data-ttu-id="b49ae-140">可以深化地图上的饼图覆盖层，然后提供区域音频使用。</span><span class="sxs-lookup"><span data-stu-id="b49ae-140">The pie chart overlay on the map can be drilled into, subsequently providing regional audio usage.</span></span>

![屏幕截图：团队使用率报告](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a><span data-ttu-id="b49ae-142">钻取功能</span><span class="sxs-lookup"><span data-stu-id="b49ae-142">Drill-through capabilities</span></span>

<span data-ttu-id="b49ae-143">如前面所述，用户可以深入查看每日和地区使用情况报告。</span><span class="sxs-lookup"><span data-stu-id="b49ae-143">As previously noted, users can drill into the daily and regional usage reports.</span></span>

### <a name="daily-usage"></a><span data-ttu-id="b49ae-144">每日使用</span><span class="sxs-lookup"><span data-stu-id="b49ae-144">Daily Usage</span></span>

<span data-ttu-id="b49ae-145">"每日使用情况" 报表允许管理员通过一天的时间标识高峰期。</span><span class="sxs-lookup"><span data-stu-id="b49ae-145">The Daily Usage report allows an administrator to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="b49ae-146">除了使用，我们还能够捕获整个用户情绪和该天的反馈。</span><span class="sxs-lookup"><span data-stu-id="b49ae-146">In addition to usage, we are also able to capture overall user sentiment and feedback for that day.</span></span>

![屏幕截图：团队使用率报告](media/CQD-teams-utilization-report12.png)

<span data-ttu-id="b49ae-148">"每日使用情况" 报表显示选定日期的音频、视频和屏幕共享的数量，并添加了在内部和外部连接之间进行区分的功能。</span><span class="sxs-lookup"><span data-stu-id="b49ae-148">The Daily usage report displays the number of Audio, Video and Screen shares for the selected day with the added ability to differentiate between internal and external connectivity.</span></span> <span data-ttu-id="b49ae-149">会议和对等细分位于 "分类汇总" 框的紧右侧。</span><span class="sxs-lookup"><span data-stu-id="b49ae-149">A Conference and Peer to Peer breakdown is to the immediate right of the modality total box.</span></span> <span data-ttu-id="b49ae-150">报表的右上角提供一组会议及其关联的 ID 和参与者。</span><span class="sxs-lookup"><span data-stu-id="b49ae-150">The top right of the report provides a list of conferences with their associated ID and participants for the day.</span></span> <span data-ttu-id="b49ae-151">"会议列表" 还提供了进一步的向下钻取到 "会议详细信息" 报表的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b49ae-151">The conference list provides an additional drill down to the Conference Details report as well.</span></span> <span data-ttu-id="b49ae-152">替换图形</span><span class="sxs-lookup"><span data-stu-id="b49ae-152">REPLACE GRAPHIC</span></span>

![屏幕截图：团队使用率报告](media/CQD-teams-utilization-report13.png)

<span data-ttu-id="b49ae-154">中心区域中的条形图允许用户通过一天内标识高峰期使用期。</span><span class="sxs-lookup"><span data-stu-id="b49ae-154">The bar graph in the center area allows the user to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="b49ae-155">用户可以向下钻取到显示在该小时的 "用户列表" 报表的图表上的小时。</span><span class="sxs-lookup"><span data-stu-id="b49ae-155">Users may drill down into the hour represented on the graph which will present the User List report for the hour.</span></span>

<span data-ttu-id="b49ae-156">在条形图的右侧，用户反馈以可视格式显示。</span><span class="sxs-lookup"><span data-stu-id="b49ae-156">To the right of the bar graph, User Feedback is presented in a visual format.</span></span> <span data-ttu-id="b49ae-157">尽管用户情绪可以进行主观，但它提供了可用于识别潜在问题的洞察力。</span><span class="sxs-lookup"><span data-stu-id="b49ae-157">While user sentiment can be subjective, it does provide insight that can be used to identify potential issues.</span></span>

<span data-ttu-id="b49ae-158">下表提供了一系列指标。</span><span class="sxs-lookup"><span data-stu-id="b49ae-158">The bottom table provides a range of metrics for the day.</span></span> <span data-ttu-id="b49ae-159">较差的百分比与故障率一起可为管理员提供潜在改进领域。</span><span class="sxs-lookup"><span data-stu-id="b49ae-159">Poor percentages along with failure rates can provide an administrator with potential areas of improvement.</span></span> <span data-ttu-id="b49ae-160">还可以单独选择每个小时，如下所示。</span><span class="sxs-lookup"><span data-stu-id="b49ae-160">Each hour can also be selected individually as shown below.</span></span>

<span data-ttu-id="b49ae-161">此数据可用于识别在高峰使用期间出现问题的区域。</span><span class="sxs-lookup"><span data-stu-id="b49ae-161">This data can be used to identify regions having problems during peak consumption times.</span></span>


<span data-ttu-id="b49ae-162">单击该日期的列以显示该小时的度量值。</span><span class="sxs-lookup"><span data-stu-id="b49ae-162">Click on the column for that day to display metrics for that hour.</span></span>
<span data-ttu-id="b49ae-163">![屏幕截图：团队使用率报告](media/CQD-teams-utilization-report14.png)</span><span class="sxs-lookup"><span data-stu-id="b49ae-163">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report14.png)</span></span>
  
  1.  <span data-ttu-id="b49ae-164">图表下方的表将显示该小时的度量值。</span><span class="sxs-lookup"><span data-stu-id="b49ae-164">The table below the chart will display the metrics for that hour.</span></span> <span data-ttu-id="b49ae-165">这可以按任何列标题进行排序;但是，我们会对查找有问题的区域感兴趣。</span><span class="sxs-lookup"><span data-stu-id="b49ae-165">This can be sorted by any column header; however, we would be interested in finding problematic areas.</span></span>  
    ![屏幕截图：团队使用率报告](media/CQD-teams-utilization-report15.png)
    
  2.  <span data-ttu-id="b49ae-167">我们看到，在此时间范围内，IND 区域在会议中的视频性能很差。</span><span class="sxs-lookup"><span data-stu-id="b49ae-167">We see that the IND region is experiencing poor video performance in conferences during this time frame.</span></span> <span data-ttu-id="b49ae-168">随后，CQD QER Microsoft 报表可用于缩小有问题的位置，因为区域和时间框架已确定。</span><span class="sxs-lookup"><span data-stu-id="b49ae-168">Subsequently, the CQD QER Microsoft reports can be used to narrow down the problematic location as the region and time frame has been identified.</span></span>

### <a name="conference-details"></a><span data-ttu-id="b49ae-169">会议详细信息</span><span class="sxs-lookup"><span data-stu-id="b49ae-169">Conference Details</span></span>

<span data-ttu-id="b49ae-170">"会议详细信息" 报表向会话期间使用的媒体类型提供对会议（来自与会者列表）的其他见解。</span><span class="sxs-lookup"><span data-stu-id="b49ae-170">The Conference Details report provides additional insight for meetings, from an attendee list, to the media types used during the session.</span></span>

<span data-ttu-id="b49ae-171">右键单击会议 "日常使用" 页面上的 "会议 ID" 图表中的参与者栏可向下钻取到会议详细信息。</span><span class="sxs-lookup"><span data-stu-id="b49ae-171">Right click a conference the participant bar in the conference ID chart on the Daily usage page to drill down into the conference details.</span></span>

![屏幕截图：团队使用率报告](media/CQD-teams-utilization-report24.png)

![屏幕截图：团队使用率报告](media/CQD-teams-utilization-report25.png)
  

<span data-ttu-id="b49ae-174">我们可以查看会议中的参与者，并向下表中的所有相关信息减少数据包丢失和抖动，以帮助在下表中进行潜在的疑难解答工作。</span><span class="sxs-lookup"><span data-stu-id="b49ae-174">We can see the participants in the conference as well as all the pertinent information down to packet loss and jitter to assist with potential troubleshooting efforts in the bottom table.</span></span>

![屏幕截图：团队使用率报告](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a><span data-ttu-id="b49ae-176">区域音频详细信息</span><span class="sxs-lookup"><span data-stu-id="b49ae-176">Regional Audio Details</span></span>

<span data-ttu-id="b49ae-177">区域音频详细信息 "向下钻取" 特别显示所选区域的音频分钟用量。</span><span class="sxs-lookup"><span data-stu-id="b49ae-177">The Regional Audio Details drill down specifically shows the audio minute usage for the selected region.</span></span> <span data-ttu-id="b49ae-178">具有 CQD 访问权限的用户可以查看所选区域内的 P2P 和会议音频的使用趋势。</span><span class="sxs-lookup"><span data-stu-id="b49ae-178">Users with access to CQD can see usage trends for both P2P and conference audio within the selected region.</span></span>

1.  <span data-ttu-id="b49ae-179">在 "通话计数摘要" 页面上，通过表格钻取到 "特定区域"。</span><span class="sxs-lookup"><span data-stu-id="b49ae-179">On the Call Count Summary page, drill-through to as specific region through the table.</span></span>
  <span data-ttu-id="b49ae-180">![屏幕截图：团队使用率报告](media/CQD-teams-utilization-report16.png)</span><span class="sxs-lookup"><span data-stu-id="b49ae-180">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report16.png)</span></span>

2.  <span data-ttu-id="b49ae-181">选择需要其他区域信息的行。</span><span class="sxs-lookup"><span data-stu-id="b49ae-181">Select the row with the region additional information is needed for.</span></span>
  <span data-ttu-id="b49ae-182">![屏幕截图：团队使用率报告](media/CQD-teams-utilization-report17.png)</span><span class="sxs-lookup"><span data-stu-id="b49ae-182">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report17.png)</span></span>

3.  <span data-ttu-id="b49ae-183">数据趋势显示在内部网络上使用了很长的分钟数，并且会议的 P2P 使用远达超越 P2P。</span><span class="sxs-lookup"><span data-stu-id="b49ae-183">The data trends show a significant number of minutes being used on the internal network, with conferencing far surpassing P2P use.</span></span>
  <span data-ttu-id="b49ae-184">![屏幕截图：团队使用率报告](media/CQD-teams-utilization-report18.png)</span><span class="sxs-lookup"><span data-stu-id="b49ae-184">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report18.png)</span></span>

<span data-ttu-id="b49ae-185">区域音频趋势可用于显示世界上的外部影响对用户有何影响。</span><span class="sxs-lookup"><span data-stu-id="b49ae-185">The regional audio trend can be used to show how users are impacted by external influences in the world.</span></span> <span data-ttu-id="b49ae-186">具体地说，我们将看到 EMEA 地区和 APAC 地区的外部使用情况，以便与要求远程工作的人一起增加。</span><span class="sxs-lookup"><span data-stu-id="b49ae-186">Specifically, right now, we would expect to see the external usage for the EMEA and APAC regions to increase with people being asked to work remotely.</span></span>


### <a name="user-list"></a><span data-ttu-id="b49ae-187">用户列表</span><span class="sxs-lookup"><span data-stu-id="b49ae-187">User List</span></span>

<span data-ttu-id="b49ae-188">用户列表向下钻取提供了一个特定时间的用户特定信息，这些信息由查看报表的人员选择。</span><span class="sxs-lookup"><span data-stu-id="b49ae-188">The User List drill down provides, as one might expect, user specific information for a specific hour selected by the person viewing the report.</span></span> <span data-ttu-id="b49ae-189">用户列表报表可通过 "每日使用情况" 报表上的 "每小时趋势" 图形中的向下钻取。</span><span class="sxs-lookup"><span data-stu-id="b49ae-189">The User List report is accessible through a drill down in the Hourly Trends graph on the Daily Usage report.</span></span> <span data-ttu-id="b49ae-190">右键单击需要的附加信息，然后选择 "钻取" 和 "用户列表"，如下所示。</span><span class="sxs-lookup"><span data-stu-id="b49ae-190">Right click on the hour additional information is needed for and select Drill through and User List, as shown below.</span></span>

![屏幕截图：团队使用率报告](media/CQD-teams-utilization-report19.png)

<span data-ttu-id="b49ae-192">"用户列表" 报表通过页面顶部中心的圆环图显示内部/外部连接。</span><span class="sxs-lookup"><span data-stu-id="b49ae-192">The User List report shows internal/external connectivity through the doughnut chart in the top center of the page.</span></span> <span data-ttu-id="b49ae-193">我们可以看到下面的图像中有大量参与公司网络外部的参与。</span><span class="sxs-lookup"><span data-stu-id="b49ae-193">We can see that there is a large amount of participation from Outside the corporate network in the below image.</span></span>

<span data-ttu-id="b49ae-194">图表的右上角显示该小时内每个用户所做的通话次数。</span><span class="sxs-lookup"><span data-stu-id="b49ae-194">The top right of the graph shows the number of calls made by each user within that hour.</span></span>

![屏幕截图：团队使用率报告](media/CQD-teams-utilization-report20.png)

<span data-ttu-id="b49ae-196">下表提供了每个用户在该时间内参与的会话的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b49ae-196">The bottom table provides detailed information for the sessions each user participated in during that hour.</span></span> <span data-ttu-id="b49ae-197">"失败类型" 列可用于确定导致调用丢弃的原因。</span><span class="sxs-lookup"><span data-stu-id="b49ae-197">The Failure Type column is useful in determining what caused a call to drop.</span></span> <span data-ttu-id="b49ae-198">"捕获" 和 "呈现设备" 列用于识别为什么报告通话质量较差的原因。</span><span class="sxs-lookup"><span data-stu-id="b49ae-198">The Capture and Render Device columns are useful in identifying why a call was reported having poor quality.</span></span>


## <a name="related-topics"></a><span data-ttu-id="b49ae-199">相关主题</span><span class="sxs-lookup"><span data-stu-id="b49ae-199">Related topics</span></span>

[<span data-ttu-id="b49ae-200">通话质量仪表板中可用的维度和衡量指标</span><span class="sxs-lookup"><span data-stu-id="b49ae-200">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="b49ae-201">通话质量仪表板中的流分类</span><span class="sxs-lookup"><span data-stu-id="b49ae-201">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="b49ae-202">设置 Skype for Business 通话分析</span><span class="sxs-lookup"><span data-stu-id="b49ae-202">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="b49ae-203">使用通话分析来排查通话质量不良问题</span><span class="sxs-lookup"><span data-stu-id="b49ae-203">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="b49ae-204">通话分析和通话质量仪表板</span><span class="sxs-lookup"><span data-stu-id="b49ae-204">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

[<span data-ttu-id="b49ae-205">Teams 疑难解答</span><span class="sxs-lookup"><span data-stu-id="b49ae-205">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
 