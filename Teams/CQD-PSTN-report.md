---
title: 使用 CQD PSTN 直接路由报告
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: siunies, fan.fan
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
description: 使用 Microsoft Teams 呼叫质量仪表板 (PSTN) ) 路由报告来监视和排查 Microsoft Teams 中的 PSTN 呼叫问题。
ms.openlocfilehash: f2b63f991f42aa4de9e0e4474137f7f992f95c53
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094976"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a><span data-ttu-id="df1b7-103">使用 CQD PSTN 直接路由报告</span><span class="sxs-lookup"><span data-stu-id="df1b7-103">Using the CQD PSTN Direct Routing report</span></span>

<span data-ttu-id="df1b7-104">我们于 2020 年 3 月新增了一个 Microsoft Teams 呼叫质量仪表板 (CQD) PSTN 直接路由报告，该报表已添加到 [CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)的可下载 Power BI 查询模板中。</span><span class="sxs-lookup"><span data-stu-id="df1b7-104">New in March 2020, we've added a Microsoft Teams Call Quality Dashboard (CQD) PSTN Direct Routing report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


<span data-ttu-id="df1b7-105">CQD PSTN 直接路由报告 (CQD PSTN 直接路由报告.pbit) 可帮助你了解 PSTN 服务的使用模式和质量。</span><span class="sxs-lookup"><span data-stu-id="df1b7-105">The CQD PSTN Direct Routing report (CQD PSTN Direct Routing Report.pbit) helps you understand the usage patterns and quality of your PSTN services.</span></span> <span data-ttu-id="df1b7-106">使用此报告可以监视服务使用情况、有关会话边界控制器 (SBC) 、电话服务、网络参数和网络有效性比详细信息。</span><span class="sxs-lookup"><span data-stu-id="df1b7-106">Use this report to monitor service usage, information about your Session Border Controller (SBC), the telephony service, network parameters, and Network Effectiveness Ratio details.</span></span> <span data-ttu-id="df1b7-107">此信息可帮助你识别问题，包括通话中断的原因。</span><span class="sxs-lookup"><span data-stu-id="df1b7-107">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="df1b7-108">例如，你将能够查看音量下降时间、受影响的调用数量以及原因。</span><span class="sxs-lookup"><span data-stu-id="df1b7-108">For example, you'll be able to see when volume drops, or how many calls get affected and for what reason.</span></span>


<span data-ttu-id="df1b7-109">CQD PSTN 直接路由报告包含四个部分：</span><span class="sxs-lookup"><span data-stu-id="df1b7-109">The CQD PSTN Direct Routing Report has four sections:</span></span>

  - [<span data-ttu-id="df1b7-110">PSTN 概述</span><span class="sxs-lookup"><span data-stu-id="df1b7-110">PSTN Overview</span></span>](#pstn-overview)

  - [<span data-ttu-id="df1b7-111">服务详细信息</span><span class="sxs-lookup"><span data-stu-id="df1b7-111">Service Details</span></span>](#service-details)

  - [<span data-ttu-id="df1b7-112">网络有效性比</span><span class="sxs-lookup"><span data-stu-id="df1b7-112">Network Effectiveness Ratio</span></span>](#network-effectiveness-ratio)

  - [<span data-ttu-id="df1b7-113">网络参数</span><span class="sxs-lookup"><span data-stu-id="df1b7-113">Network Parameters</span></span>](#network-parameters)

## <a name="highlights"></a><span data-ttu-id="df1b7-114">突出显示</span><span class="sxs-lookup"><span data-stu-id="df1b7-114">Highlights</span></span>

1. <span data-ttu-id="df1b7-115">按呼叫类型、SBC、呼叫方和被叫方国家/地区进行分析</span><span class="sxs-lookup"><span data-stu-id="df1b7-115">Analyze by call type, SBC, caller and callee country</span></span>

   <span data-ttu-id="df1b7-116">CQD PSTN 直接路由报告聚合租户上 6 个月过去 7、30 或 180 (180 天的所有 SDC 的可靠性与使用情况) 。</span><span class="sxs-lookup"><span data-stu-id="df1b7-116">The CQD PSTN Direct Routing report aggregates reliability and usage metrics for all SBCs on your tenant for the last 7, 30, or 180 days (6 months).</span></span> <span data-ttu-id="df1b7-117">可以按呼叫类型、SBC、呼叫方和被调用方国家/地区分析数据。</span><span class="sxs-lookup"><span data-stu-id="df1b7-117">You can analyze data by call type, SBC, caller and callee country.</span></span> <span data-ttu-id="df1b7-118">如果对特定 SBC 或国家/地区感兴趣，将能够识别所选时间范围内的趋势变化。</span><span class="sxs-lookup"><span data-stu-id="df1b7-118">If you're interested in a particular SBC or country, you'll be able to identify changes in trends over the selected time range.</span></span>
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="CQD PSTN 直接路由报告中可用的筛选器的屏幕截图":::
   
2. <span data-ttu-id="df1b7-120">跟踪趋势</span><span class="sxs-lookup"><span data-stu-id="df1b7-120">Track trends</span></span>

    <span data-ttu-id="df1b7-121">在尝试了解服务使用情况和可靠性时，趋势分析至关重要。</span><span class="sxs-lookup"><span data-stu-id="df1b7-121">Trends analysis is essential when trying to understand service usage and reliability.</span></span> <span data-ttu-id="df1b7-122">每小时趋势提供每日性能的仔细查看，帮助识别实时事件。</span><span class="sxs-lookup"><span data-stu-id="df1b7-122">Hourly trends provide a close look at daily performance, which helps identify real-time incidents.</span></span> <span data-ttu-id="df1b7-123">每日趋势允许从长期角度查看服务运行状况。</span><span class="sxs-lookup"><span data-stu-id="df1b7-123">Daily trends let you see your service health from a long-term perspective.</span></span> <span data-ttu-id="df1b7-124">必须能够在具有适当数据粒度的这两种模式之间切换。</span><span class="sxs-lookup"><span data-stu-id="df1b7-124">It's important to be able to shift between those two modes with appropriate data granularity.</span></span> <span data-ttu-id="df1b7-125">CQD PSTN 直接路由报告提供 6 个月趋势概述、7 天和 30 天每日趋势以及每小时趋势，以便分析每个级别的性能。</span><span class="sxs-lookup"><span data-stu-id="df1b7-125">The CQD PSTN Direct Routing report provides 6-month trends overview, 7- and 30-day daily trends, and hourly trends so you can analyze performance at each level.</span></span>
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="CQD PSTN 直接路由报告中的趋势图的屏幕截图":::

3. <span data-ttu-id="df1b7-127">钻取到 SBC 或用户级别</span><span class="sxs-lookup"><span data-stu-id="df1b7-127">Drill through to SBC or user level</span></span>

   <span data-ttu-id="df1b7-128">我们一直在 CQD 中的许多数据类别上构建钻取功能，让你快速了解 SBC 或用户级别的使用情况或可靠性分布。</span><span class="sxs-lookup"><span data-stu-id="df1b7-128">We've been building in drill-through capability on many data categories in CQD, which lets you quickly understand usage or reliability distribution at the SBC or user level.</span></span> <span data-ttu-id="df1b7-129">通过使用钻取，可以快速发现问题并了解实际用户的影响。</span><span class="sxs-lookup"><span data-stu-id="df1b7-129">By using drill through, you can quickly poinpoint issues and understand real user impact.</span></span> <span data-ttu-id="df1b7-130">CQD PSTN 直接路由报告功能钻取服务详细信息和网络有效性比指标。</span><span class="sxs-lookup"><span data-stu-id="df1b7-130">The CQD PSTN Direct Routing report features drill through on the Service Detail and Network Effectiveness Ratio metrics.</span></span> <span data-ttu-id="df1b7-131">单击感兴趣的数据点，钻取 SBC 或用户级别的详细信息。</span><span class="sxs-lookup"><span data-stu-id="df1b7-131">Click the data point you're interested in to drill through to SBC- or user-level details.</span></span>
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="屏幕截图显示一个数据点上的钻取功能":::


## <a name="pstn-overview"></a><span data-ttu-id="df1b7-133">PSTN 概述</span><span class="sxs-lookup"><span data-stu-id="df1b7-133">PSTN Overview</span></span>

<span data-ttu-id="df1b7-134">CQD PSTN 直接路由报告提供与过去 180 天服务总体运行状况相关的以下信息。</span><span class="sxs-lookup"><span data-stu-id="df1b7-134">The CQD PSTN Direct Routing Report provides the following information related to overall health of the service for the past 180 days.</span></span>
<span data-ttu-id="df1b7-135">![屏幕截图：PSTN CQD 报告](media/CQD-PSTN-report1.png)</span><span class="sxs-lookup"><span data-stu-id="df1b7-135">![Screenshot: PSTN CQD report](media/CQD-PSTN-report1.png)</span></span>

<span data-ttu-id="df1b7-136">例如，如果对通过 SBC 的所有入站呼叫的总体使用情况和运行状况感兴趣，abc.bca.adatum.biz 美国作为内部国家/地区：</span><span class="sxs-lookup"><span data-stu-id="df1b7-136">For example, if you are interested in the overall usage and health about all inbound calls going through SBC abc.bca.adatum.biz with US as the internal country:</span></span>

| <span data-ttu-id="df1b7-137">**呼叫**</span><span class="sxs-lookup"><span data-stu-id="df1b7-137">**Call Out**</span></span> | <span data-ttu-id="df1b7-138">**说明**</span><span class="sxs-lookup"><span data-stu-id="df1b7-138">**Description**</span></span>                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="df1b7-139">1</span><span class="sxs-lookup"><span data-stu-id="df1b7-139">1</span></span>            | <span data-ttu-id="df1b7-140">可以使用顶部的筛选器向下钻取并选择"ByotIn"作为呼叫类型，abc.bca.contoso.com"会话板控制器"和"美国"作为内部国家/地区。</span><span class="sxs-lookup"><span data-stu-id="df1b7-140">You can use the filters at the top to drill down and select ByotIn as call type, abc.bca.contoso.com as Session Boarder Controller, and US as internal country.</span></span> |
| <span data-ttu-id="df1b7-141">2</span><span class="sxs-lookup"><span data-stu-id="df1b7-141">2</span></span>            | <span data-ttu-id="df1b7-142">过去 180 天的使用趋势。</span><span class="sxs-lookup"><span data-stu-id="df1b7-142">Usage trend for the past 180 days.</span></span> <span data-ttu-id="df1b7-143">可以在"服务详细信息"页上找到使用情况详细信息报表。</span><span class="sxs-lookup"><span data-stu-id="df1b7-143">You can find usage detail report on Service Detail page.</span></span>                                                                     |
| <span data-ttu-id="df1b7-144">3</span><span class="sxs-lookup"><span data-stu-id="df1b7-144">3</span></span>            | <span data-ttu-id="df1b7-145">过去 180 天的后拨号延迟、延迟、抖动和数据包丢失趋势。</span><span class="sxs-lookup"><span data-stu-id="df1b7-145">Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days.</span></span> <span data-ttu-id="df1b7-146">可以在"网络参数"页上找到详细报告。</span><span class="sxs-lookup"><span data-stu-id="df1b7-146">You can find detail report on Network Parameters page.</span></span>                           |
| <span data-ttu-id="df1b7-147">4</span><span class="sxs-lookup"><span data-stu-id="df1b7-147">4</span></span>            | <span data-ttu-id="df1b7-148">过去 180 天的并发呼叫和每日活动用户趋势。</span><span class="sxs-lookup"><span data-stu-id="df1b7-148">Concurrent Call and Daily Active User trend for the past 180 days.</span></span> <span data-ttu-id="df1b7-149">此图表可帮助你了解服务的最大容量。</span><span class="sxs-lookup"><span data-stu-id="df1b7-149">This chart can help you understand the max volume of the service.</span></span>                            |
| <span data-ttu-id="df1b7-150">5</span><span class="sxs-lookup"><span data-stu-id="df1b7-150">5</span></span>            | <span data-ttu-id="df1b7-151">呼叫结束原因影响过去 180 天的服务质量。</span><span class="sxs-lookup"><span data-stu-id="df1b7-151">Top Call End Reason affected service quality for the past 180 days.</span></span> <span data-ttu-id="df1b7-152">可以在网络有效比率和 NER (页上) 运行状况详细信息。</span><span class="sxs-lookup"><span data-stu-id="df1b7-152">You can find service health detail on Network Effective Ratio(NER) page.</span></span>                    |

## <a name="service-details"></a><span data-ttu-id="df1b7-153">服务详细信息</span><span class="sxs-lookup"><span data-stu-id="df1b7-153">Service Details</span></span>

<span data-ttu-id="df1b7-154">此页提供每天的服务使用趋势，以及按地理划分的用户反馈明细。</span><span class="sxs-lookup"><span data-stu-id="df1b7-154">This page provides service usage trends per day and user feedback breakdown by geographic.</span></span>

  - <span data-ttu-id="df1b7-155">**总尝试次数 –** 该时间范围内尝试调用总数，包括成功和失败的调用</span><span class="sxs-lookup"><span data-stu-id="df1b7-155">**Total Attempt Calls –** Total attempt calls in that time range, including both success and failed calls</span></span>

  - <span data-ttu-id="df1b7-156">**已连接呼叫总数 -** 该时间范围内已连接呼叫总数</span><span class="sxs-lookup"><span data-stu-id="df1b7-156">**Total Connected Calls -** Total connected calls in that time range</span></span>

  - <span data-ttu-id="df1b7-157">**总分钟数 –** 该时间范围内分钟使用量总计</span><span class="sxs-lookup"><span data-stu-id="df1b7-157">**Total Minutes –** Total minute usage in that time range</span></span>

  - <span data-ttu-id="df1b7-158">**每日活动用户 (DAU) –** 当天至少进行了一次已连接呼叫的每日活动用户的计数</span><span class="sxs-lookup"><span data-stu-id="df1b7-158">**Daily Active Users(DAU) –** Count of daily active user who made at least one connected call in that day</span></span>

  - <span data-ttu-id="df1b7-159">**并发调用 –** 一分钟内同时进行的活动呼叫的最大数量</span><span class="sxs-lookup"><span data-stu-id="df1b7-159">**Concurrent Calls –** Max of simultaneous active calls in a minute</span></span>

  - <span data-ttu-id="df1b7-160">**用户反馈 –** "评价我的通话"分数来自用户。</span><span class="sxs-lookup"><span data-stu-id="df1b7-160">**User Feedback –** "Rate My Call" score comes from the user.</span></span> <span data-ttu-id="df1b7-161">3-5 被认为是一个很好的调用。</span><span class="sxs-lookup"><span data-stu-id="df1b7-161">3-5 is considered as a good call.</span></span> <span data-ttu-id="df1b7-162">1-2 被视为错误调用。</span><span class="sxs-lookup"><span data-stu-id="df1b7-162">1-2 is considered as a bad call.</span></span>

![屏幕截图：PSTN CQD 报告](media/CQD-PSTN-report2.png)

<span data-ttu-id="df1b7-164">例如：</span><span class="sxs-lookup"><span data-stu-id="df1b7-164">For example:</span></span>

1.  <span data-ttu-id="df1b7-165">如果看到平均呼叫持续时间在 2020 年 2 月 14 日下降到 0，可以首先检查呼叫量是否正常，并查看总连接呼叫与总尝试呼叫之间是否存在很大差异。</span><span class="sxs-lookup"><span data-stu-id="df1b7-165">If you see average call duration drops to 0 at 02/14/2020, you can first check if the call volume looks normal and see if there is a big discrepancy between total connect calls and total attempt calls.</span></span> <span data-ttu-id="df1b7-166">然后转到"网络有效性比"页，对呼叫失败原因进行投资。</span><span class="sxs-lookup"><span data-stu-id="df1b7-166">Then go to Network Effectiveness Ratio page to invest on call failure reasons.</span></span>

2.  <span data-ttu-id="df1b7-167">如果在用户反馈地图上看到红点不断增加，可以转到"网络有效性比"页和网络参数，查看是否有异常，并且可以使用 MS 服务台提出票证。</span><span class="sxs-lookup"><span data-stu-id="df1b7-167">If you see increasing red spots on the user feedback map, you could go to Network Effectiveness Ratio page and Network Parameter to see if there are any anomalies and you could raise a ticket using MS Service Desk.</span></span>

## <a name="network-effectiveness-ratio"></a><span data-ttu-id="df1b7-168">网络有效性比</span><span class="sxs-lookup"><span data-stu-id="df1b7-168">Network Effectiveness Ratio</span></span>

<span data-ttu-id="df1b7-169">这是"总体运行状况"仪表板上显示的指标。</span><span class="sxs-lookup"><span data-stu-id="df1b7-169">This is the same metric that appears on the Overall Health dashboard.</span></span> <span data-ttu-id="df1b7-170">可以在下面的"每小时网络有效率"和"呼叫结束原因"图表上查看具有受影响呼叫详细信息的每小时 NER (入站/出站) 。</span><span class="sxs-lookup"><span data-stu-id="df1b7-170">You can check hourly NER number with affected calls detail for both call directions (inbound/outbound) on the Hourly network effectiveness ratio and call ending reason chart below.</span></span>

  - <span data-ttu-id="df1b7-171">**NER** - (%) 通过测量已发送的呼叫数与发送给收件人的呼叫数来传送呼叫。</span><span class="sxs-lookup"><span data-stu-id="df1b7-171">**NER** - The ability (%) of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>

  - <span data-ttu-id="df1b7-172">**SIP 响应代码**- 三位数整数响应代码显示呼叫状态。</span><span class="sxs-lookup"><span data-stu-id="df1b7-172">**SIP response code**- A three-digit integer response code shows the call status.</span></span>

  - <span data-ttu-id="df1b7-173">**Microsoft 响应代码**- 从 Microsoft 组件发送的响应代码。</span><span class="sxs-lookup"><span data-stu-id="df1b7-173">**Microsoft response code**-A response code sent out from Microsoft component.</span></span>

  - <span data-ttu-id="df1b7-174">**说明** - 对应于 SIP 响应代码和 Microsoft 响应代码的原因阶段。</span><span class="sxs-lookup"><span data-stu-id="df1b7-174">**Description** – The reason phase that corresponding to the SIP response code and Microsoft response code.</span></span>

  - <span data-ttu-id="df1b7-175">**受影响的呼叫数** - 所选时间范围内受影响的呼叫总数。</span><span class="sxs-lookup"><span data-stu-id="df1b7-175">**Number of calls affected** – The total number of calls got affected during the selected time range.</span></span>

> ![屏幕截图：PSTN CQD 报告](media/CQD-PSTN-report3.png)
> 
<span data-ttu-id="df1b7-177">例如：</span><span class="sxs-lookup"><span data-stu-id="df1b7-177">For example:</span></span>

![屏幕截图：PSTN CQD 报告](media/CQD-PSTN-report4.png)

<span data-ttu-id="df1b7-179">如果"每日 NER"在 2020 年 2 月 5 日下降，可以单击日期，其他图表将缩放到该特定日期。</span><span class="sxs-lookup"><span data-stu-id="df1b7-179">If Daily NER has a dip on 02/05/2020, you can click on the date and other charts will zoom to that specific date.</span></span>

![屏幕截图：PSTN CQD 报告](media/CQD-PSTN-report5.png)

<span data-ttu-id="df1b7-181">从"NER 良好百分比每小时趋势"中，可发现低值发生在大约 21：00。</span><span class="sxs-lookup"><span data-stu-id="df1b7-181">From the NER Good Percentage Hourly Trend, you can find the dip happens around 21:00.</span></span> <span data-ttu-id="df1b7-182">然后再次单击以缩放到第 21 小时，并选中"影响呼叫详细信息"以查看该小时内失败的呼叫数以及呼叫结束原因。</span><span class="sxs-lookup"><span data-stu-id="df1b7-182">Then click again to zoom to hour 21 and check Effected Call Details to see how many calls failed in that hour and what are the call end reasons.</span></span> <span data-ttu-id="df1b7-183">如果问题与 SBC 不相关，可以从解决任何 SBC 问题开始自行解决问题，或者向服务台报告。</span><span class="sxs-lookup"><span data-stu-id="df1b7-183">You can start with self-trouble shooting on any SBC problems or report to Service Desk if the problem is not related to SBC.</span></span>

## <a name="network-parameters"></a><span data-ttu-id="df1b7-184">网络参数</span><span class="sxs-lookup"><span data-stu-id="df1b7-184">Network Parameters</span></span>

<span data-ttu-id="df1b7-185">从直接路由接口到会话边界控制器测量所有网络参数。</span><span class="sxs-lookup"><span data-stu-id="df1b7-185">All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="df1b7-186">有关建议值的信息，请参阅为 [Microsoft Teams](prepare-network.md)准备组织的网络，并查看客户边缘到 Microsoft Edge 的建议值。</span><span class="sxs-lookup"><span data-stu-id="df1b7-186">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

  - <span data-ttu-id="df1b7-187">**抖动** - 是使用 RTCP 和 RTP 控制协议在两个终结点之间计算的网络传播延迟 (毫秒) 。</span><span class="sxs-lookup"><span data-stu-id="df1b7-187">**Jitter** – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

  - <span data-ttu-id="df1b7-188">**数据包丢失** – 是未能到达的数据包的度量值;它是在两个终结点之间计算的。</span><span class="sxs-lookup"><span data-stu-id="df1b7-188">**Packet Loss** – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

  - <span data-ttu-id="df1b7-189">延迟 **-** (也称为往返时间) 是发送信号所花的时间长度加上接收该信号的确认所花的时间长度。</span><span class="sxs-lookup"><span data-stu-id="df1b7-189">**Latency** - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="df1b7-190">此时间延迟由信号的两个点之间的传播时间组成。</span><span class="sxs-lookup"><span data-stu-id="df1b7-190">This time delay consists of the propagation times between the two points of a signal.</span></span>

> ![屏幕截图：PSTN CQD 报告](media/CQD-PSTN-report6.png)

<span data-ttu-id="df1b7-192">例如：</span><span class="sxs-lookup"><span data-stu-id="df1b7-192">For example:</span></span>

<span data-ttu-id="df1b7-193">如果看到特定日期的四个图表（例如，2020/02/14 的延迟）中的任意一个图表出现峰值 (延迟、抖动、程序包丢失率、后拨号延迟) ，请单击日期点。</span><span class="sxs-lookup"><span data-stu-id="df1b7-193">If you see a spike on any of the four charts (Latency, Jitter, Package Loss Rate, Post Dial Delay) for a specific date, for example, Latency on 02/14/2020, click on the date point.</span></span> <span data-ttu-id="df1b7-194">底部的每小时趋势图表将刷新以显示每小时数字。</span><span class="sxs-lookup"><span data-stu-id="df1b7-194">And the hourly trend chart at the bottom will refresh to show the hourly number.</span></span> <span data-ttu-id="df1b7-195">可以通过 MS 服务台检查 SDC 或提出票证。</span><span class="sxs-lookup"><span data-stu-id="df1b7-195">You can check the SBCs or raise a ticket with MS Service Desk.</span></span>

![屏幕截图：PSTN CQD 报告](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a><span data-ttu-id="df1b7-197">相关主题</span><span class="sxs-lookup"><span data-stu-id="df1b7-197">Related topics</span></span>

[<span data-ttu-id="df1b7-198">使用 Power BI 分析 Microsoft Teams 的 CQD 数据</span><span class="sxs-lookup"><span data-stu-id="df1b7-198">Use Power BI to analyze CQD data for Microsoft Teams</span></span>](CQD-PSTN-report.md)

[<span data-ttu-id="df1b7-199">Teams 疑难解答</span><span class="sxs-lookup"><span data-stu-id="df1b7-199">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)