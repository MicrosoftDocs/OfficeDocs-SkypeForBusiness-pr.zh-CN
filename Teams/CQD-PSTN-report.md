---
title: 使用 CQD PSTN 直接路由报告
ms.author: lolaj
author: LolaJacobsen
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
description: 使用 CQD PSTN 直接路由报告监控 Microsoft 团队中的 PSTN 呼叫并进行故障排除。
ms.openlocfilehash: a3a7d84a21858b8cb2039f3f5bb6efde6b9adaaa
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221746"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a><span data-ttu-id="5d308-103">使用 CQD PSTN 直接路由报告</span><span class="sxs-lookup"><span data-stu-id="5d308-103">Using the CQD PSTN Direct Routing report</span></span>

<span data-ttu-id="5d308-104">2020年3月新增，我们已将 CQD PSTN 直接路由报告添加到可下载[的 POWER BI 查询模板 FOR CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="5d308-104">New in March 2020, we've added a CQD PSTN Direct Routing report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


<span data-ttu-id="5d308-105">CQD PSTN 直接路由报告（CQD PSTN 直接路由报告 pbit）可帮助你了解 PSTN 服务的使用模式和质量。</span><span class="sxs-lookup"><span data-stu-id="5d308-105">The CQD PSTN Direct Routing report (CQD PSTN Direct Routing Report.pbit) helps you understand the usage patterns and quality of your PSTN services.</span></span> <span data-ttu-id="5d308-106">使用此报告可监视服务使用情况、有关会话边界控制器（SBC）、电话服务、网络参数和网络有效性比率详细信息的信息。</span><span class="sxs-lookup"><span data-stu-id="5d308-106">Use this report to monitor service usage, information about your Session Border Controller (SBC), the telephony service, network parameters, and Network Effectiveness Ratio details.</span></span> <span data-ttu-id="5d308-107">此信息可帮助你识别问题，包括断开呼叫的原因。</span><span class="sxs-lookup"><span data-stu-id="5d308-107">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="5d308-108">例如，你将能够查看何时丢弃卷，或查看受影响的通话次数以及原因。</span><span class="sxs-lookup"><span data-stu-id="5d308-108">For example, you'll be able to see when volume drops, or how many calls get affected and for what reason.</span></span>


<span data-ttu-id="5d308-109">CQD PSTN 直接路由报告包含四个部分：</span><span class="sxs-lookup"><span data-stu-id="5d308-109">The CQD PSTN Direct Routing Report has four sections:</span></span>

  - [<span data-ttu-id="5d308-110">PSTN 概述</span><span class="sxs-lookup"><span data-stu-id="5d308-110">PSTN Overview</span></span>](#pstn-overview)

  - [<span data-ttu-id="5d308-111">服务详细信息</span><span class="sxs-lookup"><span data-stu-id="5d308-111">Service Details</span></span>](#service-details)

  - [<span data-ttu-id="5d308-112">网络有效性比率</span><span class="sxs-lookup"><span data-stu-id="5d308-112">Network Effectiveness Ratio</span></span>](#network-effectiveness-ratio)

  - [<span data-ttu-id="5d308-113">网络参数</span><span class="sxs-lookup"><span data-stu-id="5d308-113">Network Parameters</span></span>](#network-parameters)

## <a name="highlights"></a><span data-ttu-id="5d308-114">讲述</span><span class="sxs-lookup"><span data-stu-id="5d308-114">Highlights</span></span>

1. <span data-ttu-id="5d308-115">按呼叫类型、SBC、呼叫方和被叫方国家分析</span><span class="sxs-lookup"><span data-stu-id="5d308-115">Analyze by call type, SBC, caller and callee country</span></span>

   <span data-ttu-id="5d308-116">CQD PSTN 直接路由报告将租户上所有 SBCs 的可靠性和使用指标聚合到最近7天、30天或180天（6个月）。</span><span class="sxs-lookup"><span data-stu-id="5d308-116">The CQD PSTN Direct Routing report aggregates reliability and usage metrics for all SBCs on your tenant for the last 7, 30, or 180 days (6 months).</span></span> <span data-ttu-id="5d308-117">你可以按呼叫类型、SBC、呼叫方和被叫方国家/地区分析数据。</span><span class="sxs-lookup"><span data-stu-id="5d308-117">You can analyze data by call type, SBC, caller and callee country.</span></span> <span data-ttu-id="5d308-118">如果你对特定的 SBC 或国家感兴趣，你将能够识别所选时间范围内趋势的变化。</span><span class="sxs-lookup"><span data-stu-id="5d308-118">If you're interested in a particular SBC or country, you'll be able to identify changes in trends over the selected time range.</span></span>
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="CQD PSTN 直接路由报告中提供的筛选器的屏幕截图":::
   
2. <span data-ttu-id="5d308-120">跟踪趋势</span><span class="sxs-lookup"><span data-stu-id="5d308-120">Track trends</span></span>

    <span data-ttu-id="5d308-121">当您尝试了解服务使用情况和可靠性时，趋势分析非常重要。</span><span class="sxs-lookup"><span data-stu-id="5d308-121">Trends analysis is essential when trying to understand service usage and reliability.</span></span> <span data-ttu-id="5d308-122">每小时趋势可提供一种密切了解的日常性能，可帮助确定实时事件。</span><span class="sxs-lookup"><span data-stu-id="5d308-122">Hourly trends provide a close look at daily performance, which helps identify real-time incidents.</span></span> <span data-ttu-id="5d308-123">每日趋势让你可以从长期角度查看你的服务运行状况。</span><span class="sxs-lookup"><span data-stu-id="5d308-123">Daily trends let you see your service health from a long-term perspective.</span></span> <span data-ttu-id="5d308-124">在这两种模式之间进行移位非常重要，因为它具有适当的数据粒度。</span><span class="sxs-lookup"><span data-stu-id="5d308-124">It's important to be able to shift between those two modes with appropriate data granularity.</span></span> <span data-ttu-id="5d308-125">CQD PSTN 直接路由报告提供6个月的趋势概述、7天和30天的每日趋势以及每小时趋势，以便你可以在每个级别分析性能。</span><span class="sxs-lookup"><span data-stu-id="5d308-125">The CQD PSTN Direct Routing report provides 6-month trends overview, 7- and 30-day daily trends, and hourly trends so you can analyze performance at each level.</span></span>
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="CQD PSTN 直接路由报告中趋势图的屏幕截图":::

3. <span data-ttu-id="5d308-127">钻取至 SBC 或用户级别</span><span class="sxs-lookup"><span data-stu-id="5d308-127">Drill through to SBC or user level</span></span>

   <span data-ttu-id="5d308-128">我们已在 CQD 中构建了许多数据类别的钻取功能，这使你能够快速了解 SBC 或用户级别的使用情况或可靠性分布。</span><span class="sxs-lookup"><span data-stu-id="5d308-128">We've been building in drill-through capability on many data categories in CQD, which lets you quickly understand usage or reliability distribution at the SBC or user level.</span></span> <span data-ttu-id="5d308-129">通过使用钻取，你可以快速 poinpoint 问题并了解实际的用户影响。</span><span class="sxs-lookup"><span data-stu-id="5d308-129">By using drill through, you can quickly poinpoint issues and understand real user impact.</span></span> <span data-ttu-id="5d308-130">CQD PSTN 直接路由报告功能将在 "服务详细信息" 和 "网络有效性比率" 指标中进行钻取。</span><span class="sxs-lookup"><span data-stu-id="5d308-130">The CQD PSTN Direct Routing report features drill through on the Service Detail and Network Effectiveness Ratio metrics.</span></span> <span data-ttu-id="5d308-131">单击你感兴趣的数据点以钻取到 SBC 或用户级别的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5d308-131">Click the data point you're interested in to drill through to SBC- or user-level details.</span></span>
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="显示数据点上的钻取功能的屏幕截图":::


## <a name="pstn-overview"></a><span data-ttu-id="5d308-133">PSTN 概述</span><span class="sxs-lookup"><span data-stu-id="5d308-133">PSTN Overview</span></span>

<span data-ttu-id="5d308-134">CQD PSTN 直接路由报告提供有关过去180天内服务的整体运行状况的以下信息。</span><span class="sxs-lookup"><span data-stu-id="5d308-134">The CQD PSTN Direct Routing Report provides the following information related to overall health of the service for the past 180 days.</span></span>
<span data-ttu-id="5d308-135">![屏幕截图： PSTN CQD 报表](media/CQD-PSTN-report1.png)</span><span class="sxs-lookup"><span data-stu-id="5d308-135">![Screenshot: PSTN CQD report](media/CQD-PSTN-report1.png)</span></span>

<span data-ttu-id="5d308-136">例如，如果你对通过 SBC abc.bca.adatum.biz 进行的所有入站呼叫的整体使用和运行状况感兴趣，我们作为内部国家/地区：</span><span class="sxs-lookup"><span data-stu-id="5d308-136">For example, if you are interested in the overall usage and health about all inbound calls going through SBC abc.bca.adatum.biz with US as the internal country:</span></span>

| <span data-ttu-id="5d308-137">**拨出**</span><span class="sxs-lookup"><span data-stu-id="5d308-137">**Call Out**</span></span> | <span data-ttu-id="5d308-138">**说明**</span><span class="sxs-lookup"><span data-stu-id="5d308-138">**Description**</span></span>                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="5d308-139">1</span><span class="sxs-lookup"><span data-stu-id="5d308-139">1</span></span>            | <span data-ttu-id="5d308-140">你可以使用顶部的筛选器向下钻取，并选择 "ByotIn" 作为 "呼叫类型"、"abc.bca.contoso.com" 作为 "会话 Boarder" 控制器和 "美国内部国家"。</span><span class="sxs-lookup"><span data-stu-id="5d308-140">You can use the filters at the top to drill down and select ByotIn as call type, abc.bca.contoso.com as Session Boarder Controller, and US as internal country.</span></span> |
| <span data-ttu-id="5d308-141">2</span><span class="sxs-lookup"><span data-stu-id="5d308-141">2</span></span>            | <span data-ttu-id="5d308-142">过去180天的使用趋势。</span><span class="sxs-lookup"><span data-stu-id="5d308-142">Usage trend for the past 180 days.</span></span> <span data-ttu-id="5d308-143">你可以在服务详细信息页面上找到使用率详细信息报表。</span><span class="sxs-lookup"><span data-stu-id="5d308-143">You can find usage detail report on Service Detail page.</span></span>                                                                     |
| <span data-ttu-id="5d308-144">3</span><span class="sxs-lookup"><span data-stu-id="5d308-144">3</span></span>            | <span data-ttu-id="5d308-145">过去180天后的拨号延迟、延迟、抖动和数据包损失趋势。</span><span class="sxs-lookup"><span data-stu-id="5d308-145">Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days.</span></span> <span data-ttu-id="5d308-146">你可以在 "网络参数" 页面上找到详细报告。</span><span class="sxs-lookup"><span data-stu-id="5d308-146">You can find detail report on Network Parameters page.</span></span>                           |
| <span data-ttu-id="5d308-147">4</span><span class="sxs-lookup"><span data-stu-id="5d308-147">4</span></span>            | <span data-ttu-id="5d308-148">过去180天内的同时通话和每日活动用户趋势。</span><span class="sxs-lookup"><span data-stu-id="5d308-148">Concurrent Call and Daily Active User trend for the past 180 days.</span></span> <span data-ttu-id="5d308-149">此图可帮助你了解服务的最大数量。</span><span class="sxs-lookup"><span data-stu-id="5d308-149">This chart can help you understand the max volume of the service.</span></span>                            |
| <span data-ttu-id="5d308-150">5</span><span class="sxs-lookup"><span data-stu-id="5d308-150">5</span></span>            | <span data-ttu-id="5d308-151">最大通话结束原因过去180天受影响的服务质量。</span><span class="sxs-lookup"><span data-stu-id="5d308-151">Top Call End Reason affected service quality for the past 180 days.</span></span> <span data-ttu-id="5d308-152">你可以在 "网络有效比率（NER）" 页面上找到服务运行状况详细信息。</span><span class="sxs-lookup"><span data-stu-id="5d308-152">You can find service health detail on Network Effective Ratio(NER) page.</span></span>                    |

## <a name="service-details"></a><span data-ttu-id="5d308-153">服务详细信息</span><span class="sxs-lookup"><span data-stu-id="5d308-153">Service Details</span></span>

<span data-ttu-id="5d308-154">此页面提供每天的服务使用趋势和用户反馈按地理位置划分。</span><span class="sxs-lookup"><span data-stu-id="5d308-154">This page provides service usage trends per day and user feedback breakdown by geographic.</span></span>

  - <span data-ttu-id="5d308-155">**总尝试通话–** 总尝试在该时间范围内调用，包括成功和失败的调用</span><span class="sxs-lookup"><span data-stu-id="5d308-155">**Total Attempt Calls –** Total attempt calls in that time range, including both success and failed calls</span></span>

  - <span data-ttu-id="5d308-156">**已连接的通话总数-** 该时间范围内已连接的通话总数</span><span class="sxs-lookup"><span data-stu-id="5d308-156">**Total Connected Calls -** Total connected calls in that time range</span></span>

  - <span data-ttu-id="5d308-157">**总分钟数-** 该时间范围内的总分钟使用率</span><span class="sxs-lookup"><span data-stu-id="5d308-157">**Total Minutes –** Total minute usage in that time range</span></span>

  - <span data-ttu-id="5d308-158">**每日活动用户（DAU）-** 一天内至少进行一次连接通话的每日活动用户计数</span><span class="sxs-lookup"><span data-stu-id="5d308-158">**Daily Active Users(DAU) –** Count of daily active user who made at least one connected call in that day</span></span>

  - <span data-ttu-id="5d308-159">**同时拨打-** 一分钟内最多同时进行活动通话</span><span class="sxs-lookup"><span data-stu-id="5d308-159">**Concurrent Calls –** Max of simultaneous active calls in a minute</span></span>

  - <span data-ttu-id="5d308-160">**用户反馈-**"评价我的通话" 分数来自用户。</span><span class="sxs-lookup"><span data-stu-id="5d308-160">**User Feedback –** "Rate My Call" score comes from the user.</span></span> <span data-ttu-id="5d308-161">3-5 被视为一种良好的通话。</span><span class="sxs-lookup"><span data-stu-id="5d308-161">3-5 is considered as a good call.</span></span> <span data-ttu-id="5d308-162">1-2 被视为错误调用。</span><span class="sxs-lookup"><span data-stu-id="5d308-162">1-2 is considered as a bad call.</span></span>

![屏幕截图： PSTN CQD 报表](media/CQD-PSTN-report2.png)

<span data-ttu-id="5d308-164">例如：</span><span class="sxs-lookup"><span data-stu-id="5d308-164">For example:</span></span>

1.  <span data-ttu-id="5d308-165">如果在02/14/2020 中看到 "平均呼叫持续时间" 为0，则可以首先检查呼叫音量是否正常，并查看总连接呼叫和总尝试呼叫之间是否存在重大差异。</span><span class="sxs-lookup"><span data-stu-id="5d308-165">If you see average call duration drops to 0 at 02/14/2020, you can first check if the call volume looks normal and see if there is a big discrepancy between total connect calls and total attempt calls.</span></span> <span data-ttu-id="5d308-166">然后转到 "网络有效性比率" 页面以投资于呼叫失败原因。</span><span class="sxs-lookup"><span data-stu-id="5d308-166">Then go to Network Effectiveness Ratio page to invest on call failure reasons.</span></span>

2.  <span data-ttu-id="5d308-167">如果看到用户反馈图上增加了红色点，则可以转到 "网络有效性比率" 页面和 "网络" 参数以查看是否存在任何异常，并且你可以使用 MS 服务台提升票证。</span><span class="sxs-lookup"><span data-stu-id="5d308-167">If you see increasing red spots on the user feedback map, you could go to Network Effectiveness Ratio page and Network Parameter to see if there are any anomalies and you could raise a ticket using MS Service Desk.</span></span>

## <a name="network-effectiveness-ratio"></a><span data-ttu-id="5d308-168">网络有效性比率</span><span class="sxs-lookup"><span data-stu-id="5d308-168">Network Effectiveness Ratio</span></span>

<span data-ttu-id="5d308-169">这是 "整体运行状况" 仪表板上显示的相同指标。</span><span class="sxs-lookup"><span data-stu-id="5d308-169">This is the same metric that appears on the Overall Health dashboard.</span></span> <span data-ttu-id="5d308-170">您可以在每小时的网络有效性比率下查看具有受影响的通话方向（入站/出站）的每小时 NER 号码和通话结束原因图表。</span><span class="sxs-lookup"><span data-stu-id="5d308-170">You can check hourly NER number with affected calls detail for both call directions (inbound/outbound) on the Hourly network effectiveness ratio and call ending reason chart below.</span></span>

  - <span data-ttu-id="5d308-171">**NER** -功能（%）通过测量发送的呼叫数与发送给收件人的呼叫次数进行通话的网络。</span><span class="sxs-lookup"><span data-stu-id="5d308-171">**NER** - The ability (%) of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>

  - <span data-ttu-id="5d308-172">**SIP 响应代码**-一个三位整数响应代码显示呼叫状态。</span><span class="sxs-lookup"><span data-stu-id="5d308-172">**SIP response code**- A three-digit integer response code shows the call status.</span></span>

  - <span data-ttu-id="5d308-173">**Microsoft 响应代码**-从 Microsoft 组件发出的响应代码。</span><span class="sxs-lookup"><span data-stu-id="5d308-173">**Microsoft response code**-A response code sent out from Microsoft component.</span></span>

  - <span data-ttu-id="5d308-174">**说明**-对应于 SIP 响应代码和 Microsoft 响应代码的 "原因" 阶段。</span><span class="sxs-lookup"><span data-stu-id="5d308-174">**Description** – The reason phase that corresponding to the SIP response code and Microsoft response code.</span></span>

  - <span data-ttu-id="5d308-175">**受影响的通话数**-在所选时间范围内，通话总次数受到影响。</span><span class="sxs-lookup"><span data-stu-id="5d308-175">**Number of calls affected** – The total number of calls got affected during the selected time range.</span></span>

> ![屏幕截图： PSTN CQD 报表](media/CQD-PSTN-report3.png)
> 
<span data-ttu-id="5d308-177">例如：</span><span class="sxs-lookup"><span data-stu-id="5d308-177">For example:</span></span>

![屏幕截图： PSTN CQD 报表](media/CQD-PSTN-report4.png)

<span data-ttu-id="5d308-179">如果每日 NER 在02/05/2020 上有一个 dip，则可以单击日期，其他图表将缩放到该特定日期。</span><span class="sxs-lookup"><span data-stu-id="5d308-179">If Daily NER has a dip on 02/05/2020, you can click on the date and other charts will zoom to that specific date.</span></span>

![屏幕截图： PSTN CQD 报表](media/CQD-PSTN-report5.png)

<span data-ttu-id="5d308-181">根据每小时 NER 的有效百分比，你可以发现在21:00 附近发生了 dip。</span><span class="sxs-lookup"><span data-stu-id="5d308-181">From the NER Good Percentage Hourly Trend, you can find the dip happens around 21:00.</span></span> <span data-ttu-id="5d308-182">然后再次单击以缩放到小时21并查看受影响的通话详细信息，查看该小时内的通话失败的次数以及呼叫结束原因。</span><span class="sxs-lookup"><span data-stu-id="5d308-182">Then click again to zoom to hour 21 and check Effected Call Details to see how many calls failed in that hour and what are the call end reasons.</span></span> <span data-ttu-id="5d308-183">如果问题与 SBC 无关，则可以在任何 SBC 问题或向服务台报告时开始进行自我诊断。</span><span class="sxs-lookup"><span data-stu-id="5d308-183">You can start with self-trouble shooting on any SBC problems or report to Service Desk if the problem is not related to SBC.</span></span>

## <a name="network-parameters"></a><span data-ttu-id="5d308-184">网络参数</span><span class="sxs-lookup"><span data-stu-id="5d308-184">Network Parameters</span></span>

<span data-ttu-id="5d308-185">所有网络参数都通过直接路由接口测量到会话边界控制器。</span><span class="sxs-lookup"><span data-stu-id="5d308-185">All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="5d308-186">有关推荐值的信息，请参阅为[Microsoft 团队准备组织的网络](prepare-network.md)，并查看客户边缘到 microsoft Edge 推荐值。</span><span class="sxs-lookup"><span data-stu-id="5d308-186">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

  - <span data-ttu-id="5d308-187">**抖动**——使用 RTCP （RTP 控制协议）在两个终结点之间计算的网络传播延迟时间变化的毫秒度量。</span><span class="sxs-lookup"><span data-stu-id="5d308-187">**Jitter** – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

  - <span data-ttu-id="5d308-188">**数据包丢失**-这是一种无法送达数据包的指标;它在两个终结点之间进行计算。</span><span class="sxs-lookup"><span data-stu-id="5d308-188">**Packet Loss** – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

  - <span data-ttu-id="5d308-189">**滞后**时间（也称为往返行程时间）是发送信号所需的时间长度加上接收该信号所需的时间长度。</span><span class="sxs-lookup"><span data-stu-id="5d308-189">**Latency** - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="5d308-190">此时间延迟由信号的两个点之间的传播时间组成。</span><span class="sxs-lookup"><span data-stu-id="5d308-190">This time delay consists of the propagation times between the two points of a signal.</span></span>

> ![屏幕截图： PSTN CQD 报表](media/CQD-PSTN-report6.png)

<span data-ttu-id="5d308-192">例如：</span><span class="sxs-lookup"><span data-stu-id="5d308-192">For example:</span></span>

<span data-ttu-id="5d308-193">如果在四个图表（延迟、抖动、程序包丢失率、Post 延迟）上看到一个峰值，例如，在02/14/2020 上的延迟，请单击日期点。</span><span class="sxs-lookup"><span data-stu-id="5d308-193">If you see a spike on any of the four charts (Latency, Jitter, Package Loss Rate, Post Dial Delay) for a specific date, for example, Latency on 02/14/2020, click on the date point.</span></span> <span data-ttu-id="5d308-194">并且底部的每小时趋势图将刷新以显示小时数。</span><span class="sxs-lookup"><span data-stu-id="5d308-194">And the hourly trend chart at the bottom will refresh to show the hourly number.</span></span> <span data-ttu-id="5d308-195">你可以检查 SBCs 或使用 MS 服务台提升票证。</span><span class="sxs-lookup"><span data-stu-id="5d308-195">You can check the SBCs or raise a ticket with MS Service Desk.</span></span>

![屏幕截图： PSTN CQD 报表](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a><span data-ttu-id="5d308-197">相关主题</span><span class="sxs-lookup"><span data-stu-id="5d308-197">Related topics</span></span>

[<span data-ttu-id="5d308-198">使用 Power BI 分析 Microsoft 团队的 CQD 数据</span><span class="sxs-lookup"><span data-stu-id="5d308-198">Use Power BI to analyze CQD data for Microsoft Teams</span></span>](CQD-PSTN-report.md)