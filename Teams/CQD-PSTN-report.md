---
title: 使用 CQD PSTN 直接路由报告
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
description: 使用 CQD PSTN 直接路由报告监控 Microsoft 团队中的 PSTN 呼叫并进行故障排除。
ms.openlocfilehash: 32d91d56e51c5706c3e460029312f3b6bb6948c3
ms.sourcegitcommit: 98fcfc03c55917d0aca48b7bd97988f81e8930c1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2020
ms.locfileid: "42559388"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a><span data-ttu-id="d8a67-103">使用 CQD PSTN 直接路由报告</span><span class="sxs-lookup"><span data-stu-id="d8a67-103">Using the CQD PSTN Direct Routing Report</span></span>

<span data-ttu-id="d8a67-104">2020年3月新增，我们已将 CQD PSTN 直接路由报告添加到可下载[的 POWER BI 查询模板 FOR CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="d8a67-104">New in March 2020, we've added a CQD PSTN Direct Routing Report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


<span data-ttu-id="d8a67-105">CQD PSTN 直接路由报告可帮助客户了解其 PSTN 服务的使用模式和质量。有关 SBC、电话服务、网络参数和网络有效性比率的详细信息和用法的信息业务.</span><span class="sxs-lookup"><span data-stu-id="d8a67-105">The CQD PSTN Direct Routing Report helps customers to understand the usage patterns and quality of their PSTN services monitor information about your SBC, the telephony service, the network parameters, and Network Effectiveness Ratio details and usage of the service.</span></span> <span data-ttu-id="d8a67-106">此信息可帮助你识别问题，包括断开呼叫的原因。</span><span class="sxs-lookup"><span data-stu-id="d8a67-106">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="d8a67-107">例如，你将能够知道何时丢弃卷，多少通话受到了原因的影响。</span><span class="sxs-lookup"><span data-stu-id="d8a67-107">For example, you will be able to know when volume drops, how many calls get affected by what reason.</span></span>

<span data-ttu-id="d8a67-108">CQD PSTN 直接路由报告包含四个部分：</span><span class="sxs-lookup"><span data-stu-id="d8a67-108">The CQD PSTN Direct Routing Report has four sections:</span></span>

  - [<span data-ttu-id="d8a67-109">PSTN 概述</span><span class="sxs-lookup"><span data-stu-id="d8a67-109">PSTN Overview</span></span>](#pstn-overview)

  - [<span data-ttu-id="d8a67-110">服务详细信息</span><span class="sxs-lookup"><span data-stu-id="d8a67-110">Service Details</span></span>](#service-details)

  - [<span data-ttu-id="d8a67-111">网络有效性比率</span><span class="sxs-lookup"><span data-stu-id="d8a67-111">Network Effectiveness Ratio</span></span>](#network-effectiveness-ratio)

  - [<span data-ttu-id="d8a67-112">网络参数</span><span class="sxs-lookup"><span data-stu-id="d8a67-112">Network Parameters</span></span>](#network-parameters)

## <a name="pstn-overview"></a><span data-ttu-id="d8a67-113">PSTN 概述</span><span class="sxs-lookup"><span data-stu-id="d8a67-113">PSTN Overview</span></span>

<span data-ttu-id="d8a67-114">CQD PSTN 直接路由报告提供有关过去180天内服务的整体运行状况的以下信息。</span><span class="sxs-lookup"><span data-stu-id="d8a67-114">The CQD PSTN Direct Routing Report provides the following information related to overall health of the service for the past 180 days.</span></span>
<span data-ttu-id="d8a67-115">![屏幕截图： PSTN CQD 报表](media/CQD-PSTN-report1.png)</span><span class="sxs-lookup"><span data-stu-id="d8a67-115">![Screenshot: PSTN CQD report](media/CQD-PSTN-report1.png)</span></span>

<span data-ttu-id="d8a67-116">例如，如果你对通过 SBC abc.bca.adatum.biz 进行的所有入站呼叫的整体使用和运行状况感兴趣，我们作为内部国家/地区：</span><span class="sxs-lookup"><span data-stu-id="d8a67-116">For example, if you are interested in the overall usage and health about all inbound calls going through SBC abc.bca.adatum.biz with US as the internal country:</span></span>

| <span data-ttu-id="d8a67-117">**拨出**</span><span class="sxs-lookup"><span data-stu-id="d8a67-117">**Call Out**</span></span> | <span data-ttu-id="d8a67-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="d8a67-118">**Description**</span></span>                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="d8a67-119">1</span><span class="sxs-lookup"><span data-stu-id="d8a67-119">1</span></span>            | <span data-ttu-id="d8a67-120">你可以使用顶部的筛选器向下钻取，并选择 "ByotIn" 作为 "呼叫类型"、"abc.bca.contoso.com" 作为 "会话 Boarder" 控制器和 "美国内部国家"。</span><span class="sxs-lookup"><span data-stu-id="d8a67-120">You can use the filters at the top to drill down and select ByotIn as call type, abc.bca.contoso.com as Session Boarder Controller, and US as internal country.</span></span> |
| <span data-ttu-id="d8a67-121">ppls-2</span><span class="sxs-lookup"><span data-stu-id="d8a67-121">2</span></span>            | <span data-ttu-id="d8a67-122">过去180天的使用趋势。</span><span class="sxs-lookup"><span data-stu-id="d8a67-122">Usage trend for the past 180 days.</span></span> <span data-ttu-id="d8a67-123">你可以在服务详细信息页面上找到使用率详细信息报表。</span><span class="sxs-lookup"><span data-stu-id="d8a67-123">You can find usage detail report on Service Detail page.</span></span>                                                                     |
| <span data-ttu-id="d8a67-124">3</span><span class="sxs-lookup"><span data-stu-id="d8a67-124">3</span></span>            | <span data-ttu-id="d8a67-125">过去180天后的拨号延迟、延迟、抖动和数据包损失趋势。</span><span class="sxs-lookup"><span data-stu-id="d8a67-125">Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days.</span></span> <span data-ttu-id="d8a67-126">你可以在 "网络参数" 页面上找到详细报告。</span><span class="sxs-lookup"><span data-stu-id="d8a67-126">You can find detail report on Network Parameters page.</span></span>                           |
| <span data-ttu-id="d8a67-127">4</span><span class="sxs-lookup"><span data-stu-id="d8a67-127">4</span></span>            | <span data-ttu-id="d8a67-128">过去180天内的同时通话和每日活动用户趋势。</span><span class="sxs-lookup"><span data-stu-id="d8a67-128">Concurrent Call and Daily Active User trend for the past 180 days.</span></span> <span data-ttu-id="d8a67-129">此图可帮助你了解服务的最大数量。</span><span class="sxs-lookup"><span data-stu-id="d8a67-129">This chart can help you understand the max volume of the service.</span></span>                            |
| <span data-ttu-id="d8a67-130">5</span><span class="sxs-lookup"><span data-stu-id="d8a67-130">5</span></span>            | <span data-ttu-id="d8a67-131">最大通话结束原因过去180天受影响的服务质量。</span><span class="sxs-lookup"><span data-stu-id="d8a67-131">Top Call End Reason affected service quality for the past 180 days.</span></span> <span data-ttu-id="d8a67-132">你可以在 "网络有效比率（NER）" 页面上找到服务运行状况详细信息。</span><span class="sxs-lookup"><span data-stu-id="d8a67-132">You can find service health detail on Network Effective Ratio(NER) page.</span></span>                    |

## <a name="service-details"></a><span data-ttu-id="d8a67-133">服务详细信息</span><span class="sxs-lookup"><span data-stu-id="d8a67-133">Service Details</span></span>

<span data-ttu-id="d8a67-134">此页面提供每天的服务使用趋势和用户反馈按地理位置划分。</span><span class="sxs-lookup"><span data-stu-id="d8a67-134">This page provides service usage trends per day and user feedback breakdown by geographic.</span></span>

  - <span data-ttu-id="d8a67-135">**总尝试通话–** 总尝试在该时间范围内调用，包括成功和失败的调用</span><span class="sxs-lookup"><span data-stu-id="d8a67-135">**Total Attempt Calls –** Total attempt calls in that time range, including both success and failed calls</span></span>

  - <span data-ttu-id="d8a67-136">**已连接的通话总数-** 该时间范围内已连接的通话总数</span><span class="sxs-lookup"><span data-stu-id="d8a67-136">**Total Connected Calls -** Total connected calls in that time range</span></span>

  - <span data-ttu-id="d8a67-137">**总分钟数-** 该时间范围内的总分钟使用率</span><span class="sxs-lookup"><span data-stu-id="d8a67-137">**Total Minutes –** Total minute usage in that time range</span></span>

  - <span data-ttu-id="d8a67-138">**每日活动用户（DAU）-** 一天内至少进行一次连接通话的每日活动用户计数</span><span class="sxs-lookup"><span data-stu-id="d8a67-138">**Daily Active Users(DAU) –** Count of daily active user who made at least one connected call in that day</span></span>

  - <span data-ttu-id="d8a67-139">**同时拨打-** 一分钟内最多同时进行活动通话</span><span class="sxs-lookup"><span data-stu-id="d8a67-139">**Concurrent Calls –** Max of simultaneous active calls in a minute</span></span>

  - <span data-ttu-id="d8a67-140">**用户反馈-**"评价我的通话" 分数来自用户。</span><span class="sxs-lookup"><span data-stu-id="d8a67-140">**User Feedback –** "Rate My Call" score comes from the user.</span></span> <span data-ttu-id="d8a67-141">3-5 被视为一种良好的通话。</span><span class="sxs-lookup"><span data-stu-id="d8a67-141">3-5 is considered as a good call.</span></span> <span data-ttu-id="d8a67-142">1-2 被视为错误调用。</span><span class="sxs-lookup"><span data-stu-id="d8a67-142">1-2 is considered as a bad call.</span></span>

![屏幕截图： PSTN CQD 报表](media/CQD-PSTN-report2.png)

<span data-ttu-id="d8a67-144">例如：</span><span class="sxs-lookup"><span data-stu-id="d8a67-144">For example:</span></span>

1.  <span data-ttu-id="d8a67-145">如果在02/14/2020 中看到 "平均呼叫持续时间" 为0，则可以首先检查呼叫音量是否正常，并查看总连接呼叫和总尝试呼叫之间是否存在重大差异。</span><span class="sxs-lookup"><span data-stu-id="d8a67-145">If you see average call duration drops to 0 at 02/14/2020, you can first check if the call volume looks normal and see if there is a big discrepancy between total connect calls and total attempt calls.</span></span> <span data-ttu-id="d8a67-146">然后转到 "网络有效性比率" 页面以投资于呼叫失败原因。</span><span class="sxs-lookup"><span data-stu-id="d8a67-146">Then go to Network Effectiveness Ratio page to invest on call failure reasons.</span></span>

2.  <span data-ttu-id="d8a67-147">如果看到用户反馈图上增加了红色点，则可以转到 "网络有效性比率" 页面和 "网络" 参数以查看是否存在任何异常，并且你可以使用 MS 服务台提升票证。</span><span class="sxs-lookup"><span data-stu-id="d8a67-147">If you see increasing red spots on the user feedback map, you could go to Network Effectiveness Ratio page and Network Parameter to see if there are any anomalies and you could raise a ticket using MS Service Desk.</span></span>

## <a name="network-effectiveness-ratio"></a><span data-ttu-id="d8a67-148">网络有效性比率</span><span class="sxs-lookup"><span data-stu-id="d8a67-148">Network Effectiveness Ratio</span></span>

<span data-ttu-id="d8a67-149">这是 "整体运行状况" 仪表板上显示的相同指标。</span><span class="sxs-lookup"><span data-stu-id="d8a67-149">This is the same metric that appears on the Overall Health dashboard.</span></span> <span data-ttu-id="d8a67-150">您可以在每小时的网络有效性比率下查看具有受影响的通话方向（入站/出站）的每小时 NER 号码和通话结束原因图表。</span><span class="sxs-lookup"><span data-stu-id="d8a67-150">You can check hourly NER number with affected calls detail for both call directions (inbound/outbound) on the Hourly network effectiveness ratio and call ending reason chart below.</span></span>

  - <span data-ttu-id="d8a67-151">**NER** -功能（%）通过测量发送的呼叫数与发送给收件人的呼叫次数进行通话的网络。</span><span class="sxs-lookup"><span data-stu-id="d8a67-151">**NER** - The ability (%) of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>

  - <span data-ttu-id="d8a67-152">**SIP 响应代码**-一个三位整数响应代码显示呼叫状态。</span><span class="sxs-lookup"><span data-stu-id="d8a67-152">**SIP response code**- A three-digit integer response code shows the call status.</span></span>

  - <span data-ttu-id="d8a67-153">**Microsoft 响应代码**-从 Microsoft 组件发出的响应代码。</span><span class="sxs-lookup"><span data-stu-id="d8a67-153">**Microsoft response code**-A response code sent out from Microsoft component.</span></span>

  - <span data-ttu-id="d8a67-154">**说明**-对应于 SIP 响应代码和 Microsoft 响应代码的 "原因" 阶段。</span><span class="sxs-lookup"><span data-stu-id="d8a67-154">**Description** – The reason phase that corresponding to the SIP response code and Microsoft response code.</span></span>

  - <span data-ttu-id="d8a67-155">**受影响的通话数**-在所选时间范围内，通话总次数受到影响。</span><span class="sxs-lookup"><span data-stu-id="d8a67-155">**Number of calls affected** – The total number of calls got affected during the selected time range.</span></span>

> ![屏幕截图： PSTN CQD 报表](media/CQD-PSTN-report3.png)
> 
<span data-ttu-id="d8a67-157">例如：</span><span class="sxs-lookup"><span data-stu-id="d8a67-157">For example:</span></span>

![屏幕截图： PSTN CQD 报表](media/CQD-PSTN-report4.png)

<span data-ttu-id="d8a67-159">如果每日 NER 在02/05/2020 上有一个 dip，则可以单击日期，其他图表将缩放到该特定日期。</span><span class="sxs-lookup"><span data-stu-id="d8a67-159">If Daily NER has a dip on 02/05/2020, you can click on the date and other charts will zoom to that specific date.</span></span>

![屏幕截图： PSTN CQD 报表](media/CQD-PSTN-report5.png)

<span data-ttu-id="d8a67-161">根据每小时 NER 的有效百分比，你可以发现在21:00 附近发生了 dip。</span><span class="sxs-lookup"><span data-stu-id="d8a67-161">From the NER Good Percentage Hourly Trend, you can find the dip happens around 21:00.</span></span> <span data-ttu-id="d8a67-162">然后再次单击以缩放到小时21并查看受影响的通话详细信息，查看该小时内的通话失败的次数以及呼叫结束原因。</span><span class="sxs-lookup"><span data-stu-id="d8a67-162">Then click again to zoom to hour 21 and check Effected Call Details to see how many calls failed in that hour and what are the call end reasons.</span></span> <span data-ttu-id="d8a67-163">如果问题与 SBC 无关，则可以在任何 SBC 问题或向服务台报告时开始进行自我诊断。</span><span class="sxs-lookup"><span data-stu-id="d8a67-163">You can start with self-trouble shooting on any SBC problems or report to Service Desk if the problem is not related to SBC.</span></span>

## <a name="network-parameters"></a><span data-ttu-id="d8a67-164">网络参数</span><span class="sxs-lookup"><span data-stu-id="d8a67-164">Network Parameters</span></span>

<span data-ttu-id="d8a67-165">所有网络参数都通过直接路由接口测量到会话边界控制器。</span><span class="sxs-lookup"><span data-stu-id="d8a67-165">All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="d8a67-166">有关推荐值的信息，请参阅为[Microsoft 团队准备组织的网络](prepare-network.md)，并查看客户边缘到 microsoft Edge 推荐值。</span><span class="sxs-lookup"><span data-stu-id="d8a67-166">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

  - <span data-ttu-id="d8a67-167">**抖动**——使用 RTCP （RTP 控制协议）在两个终结点之间计算的网络传播延迟时间变化的毫秒度量。</span><span class="sxs-lookup"><span data-stu-id="d8a67-167">**Jitter** – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

  - <span data-ttu-id="d8a67-168">**数据包丢失**-这是一种无法送达数据包的指标;它在两个终结点之间进行计算。</span><span class="sxs-lookup"><span data-stu-id="d8a67-168">**Packet Loss** – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

  - <span data-ttu-id="d8a67-169">**滞后**时间（也称为往返行程时间）是发送信号所需的时间长度加上接收该信号所需的时间长度。</span><span class="sxs-lookup"><span data-stu-id="d8a67-169">**Latency** - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="d8a67-170">此时间延迟由信号的两个点之间的传播时间组成。</span><span class="sxs-lookup"><span data-stu-id="d8a67-170">This time delay consists of the propagation times between the two points of a signal.</span></span>

> ![屏幕截图： PSTN CQD 报表](media/CQD-PSTN-report6.png)

<span data-ttu-id="d8a67-172">例如：</span><span class="sxs-lookup"><span data-stu-id="d8a67-172">For example:</span></span>

<span data-ttu-id="d8a67-173">如果在四个图表（延迟、抖动、程序包丢失率、Post 延迟）上看到一个峰值，例如，在02/14/2020 上的延迟，请单击日期点。</span><span class="sxs-lookup"><span data-stu-id="d8a67-173">If you see a spike on any of the four charts (Latency, Jitter, Package Loss Rate, Post Dial Delay) for a specific date, for example, Latency on 02/14/2020, click on the date point.</span></span> <span data-ttu-id="d8a67-174">并且底部的每小时趋势图将刷新以显示小时数。</span><span class="sxs-lookup"><span data-stu-id="d8a67-174">And the hourly trend chart at the bottom will refresh to show the hourly number.</span></span> <span data-ttu-id="d8a67-175">你可以检查 SBCs 或使用 MS 服务台提升票证。</span><span class="sxs-lookup"><span data-stu-id="d8a67-175">You can check the SBCs or raise a ticket with MS Service Desk.</span></span>

![屏幕截图： PSTN CQD 报表](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a><span data-ttu-id="d8a67-177">相关主题</span><span class="sxs-lookup"><span data-stu-id="d8a67-177">Related topics</span></span>

[<span data-ttu-id="d8a67-178">使用 Power BI 分析 Microsoft 团队的 CQD 数据</span><span class="sxs-lookup"><span data-stu-id="d8a67-178">Use Power BI to analyze CQD data for Microsoft Teams</span></span>](CQD-PSTN-report.md)