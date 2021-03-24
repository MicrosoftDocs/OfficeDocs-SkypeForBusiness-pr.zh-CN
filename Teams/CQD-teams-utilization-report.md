---
title: 使用 CQD 数据查看 Power BI 中的 Microsoft Teams 利用率
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
description: 使用 Teams 使用率 Power BI 报表访问 Microsoft Teams 呼叫质量仪表板 (CQD) 数据来跟踪组织中 Microsoft Teams 的使用情况。
ms.openlocfilehash: 719f02ce7a5cd36e96ed7fd563c259c6e77764fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095036"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a><span data-ttu-id="fec96-103">使用 CQD 数据查看 Power BI 中的 Microsoft Teams 利用率</span><span class="sxs-lookup"><span data-stu-id="fec96-103">View Microsoft Teams utilization in Power BI using CQD data</span></span>

<span data-ttu-id="fec96-104">2020 年 3 月新增功能，我们已将 Teams 使用率报告添加到 [CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)的可下载 Power BI 查询模板。</span><span class="sxs-lookup"><span data-stu-id="fec96-104">New in March 2020, we've added a Teams Utilization report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 

<span data-ttu-id="fec96-105">通过此新的 Teams 使用率报告， (访问 Teams 呼叫质量仪表板) CQD (使用 Microsoft Teams) 多少。</span><span class="sxs-lookup"><span data-stu-id="fec96-105">This new Teams Utilization reports lets you see how (and how much) your users are using Microsoft Teams by accessing Teams Call Quality Dashboard (CQD) data.</span></span> <span data-ttu-id="fec96-106">这些报告旨在成为管理员和业务领导都可以快速转到此数据的集中位置。</span><span class="sxs-lookup"><span data-stu-id="fec96-106">These reports are intended to be a centralized location that both administrators and business leaders can quickly go to for this data.</span></span>

<span data-ttu-id="fec96-107">Teams 使用率 Power BI 报告由两个主要报告组成： **[通话计数摘要](#call-count-summary-report)** 和 **[音频分钟数摘要](#audio-minutes-summary-report)**。</span><span class="sxs-lookup"><span data-stu-id="fec96-107">The Teams Utilization Power BI report consists of two primary reports: **[Call Count Summary](#call-count-summary-report)** and **[Audio Minutes Summary](#audio-minutes-summary-report)**.</span></span> <span data-ttu-id="fec96-108">当用户[利用下面](#daily-usage)说明中记下的向下[](#conference-details)钻取报表[](#user-list)时，"每日使用情况、区域音频详细信息、会议详细信息和用户列表"报告将发挥作用。 [](#regional-audio-details)</span><span class="sxs-lookup"><span data-stu-id="fec96-108">The [Daily Usage](#daily-usage), [Regional Audio Details](#regional-audio-details), [Conference Details](#conference-details) and [User List](#user-list) reports come into play when a user takes advantage of the drill-down reports, noted in the descriptions below.</span></span>

> [!NOTE]
> <span data-ttu-id="fec96-109">必须填充生成和子网数据，以提供区域和网络筛选功能。</span><span class="sxs-lookup"><span data-stu-id="fec96-109">Building and subnet data must be populated to provide regional and network filtering capabilities.</span></span>

## <a name="call-count-summary-report"></a><span data-ttu-id="fec96-110">呼叫计数摘要报告</span><span class="sxs-lookup"><span data-stu-id="fec96-110">Call Count Summary Report</span></span>

<span data-ttu-id="fec96-111">呼叫 (摘要) 主页立即提供过去 30 天和 90 天内的音频、视频和屏幕共享会话数，如部分标题所述。</span><span class="sxs-lookup"><span data-stu-id="fec96-111">The main page (Call Count Summary) immediately provides the number of audio, video and screen sharing sessions over the last 30 and 90 days as noted in the section title.</span></span> <span data-ttu-id="fec96-112">最初显示的数据适用于整个组织，可以使用页面左侧的切片器下拉选项进行筛选。</span><span class="sxs-lookup"><span data-stu-id="fec96-112">The data initially displayed is for the organization as a whole and can be filtered using the slicer dropdown options on the left side of the page.</span></span>

![屏幕截图：Teams 使用率报告](media/CQD-teams-utilization-report1.png)

1. <span data-ttu-id="fec96-114">切片器下拉列表右侧按媒体类型细分为过去 30 天内的内部/外部视图。</span><span class="sxs-lookup"><span data-stu-id="fec96-114">To the right of the slicer dropdowns, the number of calls by media type is broken down to an internal/external view over the past thirty days.</span></span> <span data-ttu-id="fec96-115">通过上面的屏幕截图，可以看到，从组织外部位置发生的调用越来越多，考虑到当前的全局环境，这很有意义。</span><span class="sxs-lookup"><span data-stu-id="fec96-115">We can see through the above screenshot that there are more calls happening from outside organizational locations, which makes sense considering the current global environment.</span></span>
  <span data-ttu-id="fec96-116">![屏幕截图：Teams 使用率报告](media/CQD-teams-utilization-report2.png)</span><span class="sxs-lookup"><span data-stu-id="fec96-116">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report2.png)</span></span>

1. <span data-ttu-id="fec96-117">在媒体类型计数框的右侧，我们按媒体类型显示过去 90 天的每月呼叫计数。</span><span class="sxs-lookup"><span data-stu-id="fec96-117">To the right of the media type count box, we have the Monthly Call Count by Media Type for the last 90 days.</span></span> <span data-ttu-id="fec96-118">可以将每个列和媒体类型悬停在上方以显示上个月或当前月份到目前为止的计数，从而提供使用趋势信息。</span><span class="sxs-lookup"><span data-stu-id="fec96-118">Each column and media type can be hovered over to display the count for a previous month or the current month to date, providing usage trend information.</span></span>
  <span data-ttu-id="fec96-119">![屏幕截图：Teams 使用率报告](media/CQD-teams-utilization-report3.png)</span><span class="sxs-lookup"><span data-stu-id="fec96-119">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report3.png)</span></span>
 

1. <span data-ttu-id="fec96-120">中间图的作用与 90 天图一样，但它提供过去 30 天的每日使用情况视图，允许用户右键单击并向下钻取特定日期的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fec96-120">The middle graph functions as the 90-day graph does, however it provides a daily usage view for the past 30 days and allows a user to right click and drill down into details for a specific day.</span></span>
  <span data-ttu-id="fec96-121">![屏幕截图：Teams 使用率报告](media/CQD-teams-utilization-report4.png)</span><span class="sxs-lookup"><span data-stu-id="fec96-121">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report4.png)</span></span>

<span data-ttu-id="fec96-122">在页面左下角，可找到一个表，其中提供了过去一年每种媒体类型的总计值。</span><span class="sxs-lookup"><span data-stu-id="fec96-122">On the bottom left section of the page, you'll find a table providing total values for each media type over the past year.</span></span> 
    <span data-ttu-id="fec96-123">![屏幕截图：Teams 使用率报告 ](media/CQD-teams-utilization-report5.png) ![ 屏幕截图：团队利用率报告](media/CQD-teams-utilization-report6.png)</span><span class="sxs-lookup"><span data-stu-id="fec96-123">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report5.png) ![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report6.png)</span></span>   

<span data-ttu-id="fec96-124">在表格右侧，条形图显示过去 30 天内 (通话/流) 的客户端。</span><span class="sxs-lookup"><span data-stu-id="fec96-124">To the right of the table, a bar chart shows clients with the most use (calls/streams) for the past 30 days.</span></span>
   <span data-ttu-id="fec96-125">![屏幕截图：Teams 使用率报告](media/CQD-teams-utilization-report7.png)</span><span class="sxs-lookup"><span data-stu-id="fec96-125">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report7.png)</span></span>

<span data-ttu-id="fec96-126">此页面的最后一组图表分别显示每种媒体类型，其中显示了会议的细目和 P2P 使用情况。</span><span class="sxs-lookup"><span data-stu-id="fec96-126">The last set of charts for this page show each media type individually, with a breakdown showing conference and P2P usage.</span></span> <span data-ttu-id="fec96-127">下面的图表显示，与 P2P 相比，会议使用量要高得多。</span><span class="sxs-lookup"><span data-stu-id="fec96-127">The charts below show that there is a significantly higher number of conference usage as compared to P2P.</span></span>
  <span data-ttu-id="fec96-128">![屏幕截图：Teams 使用率报告](media/CQD-teams-utilization-report8.png)</span><span class="sxs-lookup"><span data-stu-id="fec96-128">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report8.png)</span></span>

## <a name="audio-minutes-summary-report"></a><span data-ttu-id="fec96-129">音频分钟数摘要报告</span><span class="sxs-lookup"><span data-stu-id="fec96-129">Audio Minutes Summary Report</span></span>

<span data-ttu-id="fec96-130">在"音频分钟数使用情况"报表上，通过几个不同的视图提供总分钟数使用情况。</span><span class="sxs-lookup"><span data-stu-id="fec96-130">On the Audio Minutes usage report, the total minute usage is provided through a few different views.</span></span> 

<span data-ttu-id="fec96-131">切片器旁边显示了易于使用的文本框的 30 天使用情况摘要。</span><span class="sxs-lookup"><span data-stu-id="fec96-131">We have the thirty-day usage summary shown next to the slicers as easy to consume text boxes.</span></span> <span data-ttu-id="fec96-132">顶部数字显示 30 天总计，内部和外部细目低于该数字。</span><span class="sxs-lookup"><span data-stu-id="fec96-132">The top number shows the thirty-day total, with internal and external breakdowns below that.</span></span>

![屏幕截图：Teams 使用率报告](media/CQD-teams-utilization-report9.png)

<span data-ttu-id="fec96-134">右上方的条形图提供会议音频使用情况的一年视图。</span><span class="sxs-lookup"><span data-stu-id="fec96-134">The top right bar graph provides a yearlong view of conference audio usage.</span></span> <span data-ttu-id="fec96-135">将鼠标悬停在一个月内以显示会议音频分钟数。</span><span class="sxs-lookup"><span data-stu-id="fec96-135">Hover over the month to show the conference audio minutes.</span></span>

<span data-ttu-id="fec96-136">为了显示 P2P 和会议音频的差异，左下角的图表采用过去一年的所有音频，并在这两种类型之间进行分解。</span><span class="sxs-lookup"><span data-stu-id="fec96-136">To show the difference in P2P and conference audio, the bottom left chart takes all audio for the past year and breaks it up between the two types.</span></span>

![屏幕截图：Teams 使用率报告](media/CQD-teams-utilization-report10.png)

<span data-ttu-id="fec96-138">"音频分钟数"页的最后一个图表显示全局地图覆盖层上的音频分钟数使用情况。</span><span class="sxs-lookup"><span data-stu-id="fec96-138">The last chart for the Audio minutes page shows audio minute usage on a global map overlay.</span></span> <span data-ttu-id="fec96-139">只有在将生成和子网数据上传到租户时，此图表才工作。</span><span class="sxs-lookup"><span data-stu-id="fec96-139">This chart will only work if building and subnet data is uploaded to the tenant.</span></span> <span data-ttu-id="fec96-140">可以钻取地图上的饼图覆盖层，随后提供区域音频使用情况。</span><span class="sxs-lookup"><span data-stu-id="fec96-140">The pie chart overlay on the map can be drilled into, subsequently providing regional audio usage.</span></span>

![屏幕截图：Teams 使用率报告](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a><span data-ttu-id="fec96-142">钻取功能</span><span class="sxs-lookup"><span data-stu-id="fec96-142">Drill-through capabilities</span></span>

<span data-ttu-id="fec96-143">如前所述，用户可以深入了解每日和区域使用情况报告。</span><span class="sxs-lookup"><span data-stu-id="fec96-143">As previously noted, users can drill into the daily and regional usage reports.</span></span>

### <a name="daily-usage"></a><span data-ttu-id="fec96-144">每日使用情况</span><span class="sxs-lookup"><span data-stu-id="fec96-144">Daily Usage</span></span>

<span data-ttu-id="fec96-145">"每日使用情况"报表允许管理员确定一天中的高峰使用时段。</span><span class="sxs-lookup"><span data-stu-id="fec96-145">The Daily Usage report allows an administrator to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="fec96-146">除了使用情况，我们还能够捕获当天的总体用户情绪和反馈。</span><span class="sxs-lookup"><span data-stu-id="fec96-146">In addition to usage, we are also able to capture overall user sentiment and feedback for that day.</span></span>

![屏幕截图：Teams 使用率报告](media/CQD-teams-utilization-report12.png)

<span data-ttu-id="fec96-148">"每日使用情况"报表显示所选天的音频、视频和屏幕共享数，添加了区分内部和外部连接的能力。</span><span class="sxs-lookup"><span data-stu-id="fec96-148">The Daily usage report displays the number of Audio, Video and Screen shares for the selected day with the added ability to differentiate between internal and external connectivity.</span></span> <span data-ttu-id="fec96-149">"会议"和"对等"细分位于"形式总计"框的右下角。</span><span class="sxs-lookup"><span data-stu-id="fec96-149">A Conference and Peer to Peer breakdown is to the immediate right of the modality total box.</span></span> <span data-ttu-id="fec96-150">报表的右上方提供了一个会议列表，其中列出了当天的关联 ID 和参与者。</span><span class="sxs-lookup"><span data-stu-id="fec96-150">The top right of the report provides a list of conferences with their associated ID and participants for the day.</span></span> <span data-ttu-id="fec96-151">会议列表还提供对"会议详细信息"报告的其他向下钻取。</span><span class="sxs-lookup"><span data-stu-id="fec96-151">The conference list provides an additional drill down to the Conference Details report as well.</span></span> <span data-ttu-id="fec96-152">替换图形</span><span class="sxs-lookup"><span data-stu-id="fec96-152">REPLACE GRAPHIC</span></span>

![屏幕截图：Teams 使用率报告](media/CQD-teams-utilization-report13.png)

<span data-ttu-id="fec96-154">中心区域中的条形图允许用户确定一天中的高峰使用时段。</span><span class="sxs-lookup"><span data-stu-id="fec96-154">The bar graph in the center area allows the user to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="fec96-155">用户可以向下钻取图表上表示的小时，该小时将显示"用户列表"报告。</span><span class="sxs-lookup"><span data-stu-id="fec96-155">Users may drill down into the hour represented on the graph which will present the User List report for the hour.</span></span>

<span data-ttu-id="fec96-156">在条形图右侧，以可视格式显示用户反馈。</span><span class="sxs-lookup"><span data-stu-id="fec96-156">To the right of the bar graph, User Feedback is presented in a visual format.</span></span> <span data-ttu-id="fec96-157">虽然用户情绪可能是主观的，但它确实提供可用于识别潜在问题的见解。</span><span class="sxs-lookup"><span data-stu-id="fec96-157">While user sentiment can be subjective, it does provide insight that can be used to identify potential issues.</span></span>

<span data-ttu-id="fec96-158">底部表提供当天的指标范围。</span><span class="sxs-lookup"><span data-stu-id="fec96-158">The bottom table provides a range of metrics for the day.</span></span> <span data-ttu-id="fec96-159">较差的百分比和失败率可为管理员提供潜在的改进领域。</span><span class="sxs-lookup"><span data-stu-id="fec96-159">Poor percentages along with failure rates can provide an administrator with potential areas of improvement.</span></span> <span data-ttu-id="fec96-160">也可以单独选择每小时，如下所示。</span><span class="sxs-lookup"><span data-stu-id="fec96-160">Each hour can also be selected individually as shown below.</span></span>

<span data-ttu-id="fec96-161">此数据可用于识别在高峰使用时段出现问题的区域。</span><span class="sxs-lookup"><span data-stu-id="fec96-161">This data can be used to identify regions having problems during peak consumption times.</span></span>


<span data-ttu-id="fec96-162">单击该天的列以显示该小时的指标。</span><span class="sxs-lookup"><span data-stu-id="fec96-162">Click on the column for that day to display metrics for that hour.</span></span>
<span data-ttu-id="fec96-163">![屏幕截图：Teams 使用率报告](media/CQD-teams-utilization-report14.png)</span><span class="sxs-lookup"><span data-stu-id="fec96-163">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report14.png)</span></span>
  
  1.  <span data-ttu-id="fec96-164">图表下方的表格将显示该小时的指标。</span><span class="sxs-lookup"><span data-stu-id="fec96-164">The table below the chart will display the metrics for that hour.</span></span> <span data-ttu-id="fec96-165">这可以通过任何列标题进行排序;但是，我们希望找到有问题的领域。</span><span class="sxs-lookup"><span data-stu-id="fec96-165">This can be sorted by any column header; however, we would be interested in finding problematic areas.</span></span>  
    ![屏幕截图：Teams 使用率报告](media/CQD-teams-utilization-report15.png)
    
  2.  <span data-ttu-id="fec96-167">在此时间帧内，我们看到 IND 区域在会议中遇到较差的视频性能。</span><span class="sxs-lookup"><span data-stu-id="fec96-167">We see that the IND region is experiencing poor video performance in conferences during this time frame.</span></span> <span data-ttu-id="fec96-168">随后，可以使用 CQD QER Microsoft 报告缩小有问题的位置范围，因为已识别到该区域和时间范围。</span><span class="sxs-lookup"><span data-stu-id="fec96-168">Subsequently, the CQD QER Microsoft reports can be used to narrow down the problematic location as the region and time frame has been identified.</span></span>

### <a name="conference-details"></a><span data-ttu-id="fec96-169">会议详细信息</span><span class="sxs-lookup"><span data-stu-id="fec96-169">Conference Details</span></span>

<span data-ttu-id="fec96-170">"会议详细信息"报告提供会议的其他见解，从与会者列表到会话期间使用的媒体类型。</span><span class="sxs-lookup"><span data-stu-id="fec96-170">The Conference Details report provides additional insight for meetings, from an attendee list, to the media types used during the session.</span></span>

<span data-ttu-id="fec96-171">右键单击"每日使用状况"页面上会议 ID 图表中的参与者栏，向下钻取会议详细信息。</span><span class="sxs-lookup"><span data-stu-id="fec96-171">Right click a conference the participant bar in the conference ID chart on the Daily usage page to drill down into the conference details.</span></span>

![屏幕截图：Teams 使用率报告](media/CQD-teams-utilization-report24.png)

![屏幕截图：Teams 使用率报告](media/CQD-teams-utilization-report25.png)
  

<span data-ttu-id="fec96-174">我们可以看到会议参与者以及数据包丢失和抖动的所有相关信息，以帮助在底部表格中进行潜在的故障排除工作。</span><span class="sxs-lookup"><span data-stu-id="fec96-174">We can see the participants in the conference as well as all the pertinent information down to packet loss and jitter to assist with potential troubleshooting efforts in the bottom table.</span></span>

![屏幕截图：Teams 使用率报告](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a><span data-ttu-id="fec96-176">区域音频详细信息</span><span class="sxs-lookup"><span data-stu-id="fec96-176">Regional Audio Details</span></span>

<span data-ttu-id="fec96-177">"区域音频详细信息"向下钻取专门显示所选区域的音频分钟数使用情况。</span><span class="sxs-lookup"><span data-stu-id="fec96-177">The Regional Audio Details drill down specifically shows the audio minute usage for the selected region.</span></span> <span data-ttu-id="fec96-178">有权访问 CQD 的用户可以在所选区域查看 P2P 和会议音频的使用趋势。</span><span class="sxs-lookup"><span data-stu-id="fec96-178">Users with access to CQD can see usage trends for both P2P and conference audio within the selected region.</span></span>

1.  <span data-ttu-id="fec96-179">在"呼叫计数摘要"页上，通过表钻取到作为特定区域。</span><span class="sxs-lookup"><span data-stu-id="fec96-179">On the Call Count Summary page, drill-through to as specific region through the table.</span></span>
  <span data-ttu-id="fec96-180">![屏幕截图：Teams 使用率报告](media/CQD-teams-utilization-report16.png)</span><span class="sxs-lookup"><span data-stu-id="fec96-180">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report16.png)</span></span>

2.  <span data-ttu-id="fec96-181">选择包含区域的其他信息的行。</span><span class="sxs-lookup"><span data-stu-id="fec96-181">Select the row with the region additional information is needed for.</span></span>
  <span data-ttu-id="fec96-182">![屏幕截图：Teams 使用率报告](media/CQD-teams-utilization-report17.png)</span><span class="sxs-lookup"><span data-stu-id="fec96-182">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report17.png)</span></span>

3.  <span data-ttu-id="fec96-183">数据趋势显示内部网络上使用大量分钟数，会议远超 P2P 使用。</span><span class="sxs-lookup"><span data-stu-id="fec96-183">The data trends show a significant number of minutes being used on the internal network, with conferencing far surpassing P2P use.</span></span>
  <span data-ttu-id="fec96-184">![屏幕截图：Teams 使用率报告](media/CQD-teams-utilization-report18.png)</span><span class="sxs-lookup"><span data-stu-id="fec96-184">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report18.png)</span></span>

<span data-ttu-id="fec96-185">区域音频趋势可用于显示用户受到世界外部影响的影响。</span><span class="sxs-lookup"><span data-stu-id="fec96-185">The regional audio trend can be used to show how users are impacted by external influences in the world.</span></span> <span data-ttu-id="fec96-186">具体而言，目前我们预期 EMEA 和 APAC 区域的外部使用量会随着要求远程工作的人的增加而增加。</span><span class="sxs-lookup"><span data-stu-id="fec96-186">Specifically, right now, we would expect to see the external usage for the EMEA and APAC regions to increase with people being asked to work remotely.</span></span>


### <a name="user-list"></a><span data-ttu-id="fec96-187">用户列表</span><span class="sxs-lookup"><span data-stu-id="fec96-187">User List</span></span>

<span data-ttu-id="fec96-188">按预期，"用户列表"向下钻取提供查看报告的用户选择的特定小时的用户特定信息。</span><span class="sxs-lookup"><span data-stu-id="fec96-188">The User List drill down provides, as one might expect, user specific information for a specific hour selected by the person viewing the report.</span></span> <span data-ttu-id="fec96-189">可以通过每日使用情况报表上"每小时趋势"图中的向下钻取来访问用户列表报表。</span><span class="sxs-lookup"><span data-stu-id="fec96-189">The User List report is accessible through a drill down in the Hourly Trends graph on the Daily Usage report.</span></span> <span data-ttu-id="fec96-190">右键单击所需的小时其他信息，然后选择"钻取"和"用户列表"，如下所示。</span><span class="sxs-lookup"><span data-stu-id="fec96-190">Right click on the hour additional information is needed for and select Drill through and User List, as shown below.</span></span>

![屏幕截图：Teams 使用率报告](media/CQD-teams-utilization-report19.png)

<span data-ttu-id="fec96-192">"用户列表"报表通过页面顶部中心的圆环图显示内部/外部连接。</span><span class="sxs-lookup"><span data-stu-id="fec96-192">The User List report shows internal/external connectivity through the doughnut chart in the top center of the page.</span></span> <span data-ttu-id="fec96-193">如下图所示，企业网络外部存在大量参与活动。</span><span class="sxs-lookup"><span data-stu-id="fec96-193">We can see that there is a large amount of participation from Outside the corporate network in the below image.</span></span>

<span data-ttu-id="fec96-194">图的右上方显示每个用户在这一小时内进行调用的数量。</span><span class="sxs-lookup"><span data-stu-id="fec96-194">The top right of the graph shows the number of calls made by each user within that hour.</span></span>

![屏幕截图：Teams 使用率报告](media/CQD-teams-utilization-report20.png)

<span data-ttu-id="fec96-196">底部表提供每个用户在这一小时内参与的会话的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fec96-196">The bottom table provides detailed information for the sessions each user participated in during that hour.</span></span> <span data-ttu-id="fec96-197">"失败类型"列可用于确定导致调用删除的原因。</span><span class="sxs-lookup"><span data-stu-id="fec96-197">The Failure Type column is useful in determining what caused a call to drop.</span></span> <span data-ttu-id="fec96-198">"捕获"和"呈现设备"列可用于识别报告通话质量差的原因。</span><span class="sxs-lookup"><span data-stu-id="fec96-198">The Capture and Render Device columns are useful in identifying why a call was reported having poor quality.</span></span>


## <a name="related-topics"></a><span data-ttu-id="fec96-199">相关主题</span><span class="sxs-lookup"><span data-stu-id="fec96-199">Related topics</span></span>

[<span data-ttu-id="fec96-200">通话质量仪表板中可用的维度和衡量指标</span><span class="sxs-lookup"><span data-stu-id="fec96-200">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="fec96-201">通话质量仪表板中的流分类</span><span class="sxs-lookup"><span data-stu-id="fec96-201">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="fec96-202">设置 Skype for Business 通话分析</span><span class="sxs-lookup"><span data-stu-id="fec96-202">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="fec96-203">使用通话分析来排查通话质量不良问题</span><span class="sxs-lookup"><span data-stu-id="fec96-203">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="fec96-204">通话分析和通话质量仪表板</span><span class="sxs-lookup"><span data-stu-id="fec96-204">Call Analytics and Call Quality Dashboard</span></span>](./monitor-call-quality-qos.md)

[<span data-ttu-id="fec96-205">Teams 疑难解答</span><span class="sxs-lookup"><span data-stu-id="fec96-205">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
