---
title: '通话质量仪表板 (CQD) 常见问题 (常见问题) '
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: 阅读常见问题 (常见问题) 和有关 Microsoft 团队通话质量仪表板 (CQD) 的解答。
ms.openlocfilehash: 8ad0a1745799194ec11284f8f7aaabd76bd30d05
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "46584021"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a><span data-ttu-id="e2588-103">通话质量仪表板 (CQD) 常见问题 (常见问题) </span><span class="sxs-lookup"><span data-stu-id="e2588-103">Call Quality Dashboard (CQD) Frequently asked questions (FAQ)</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="e2588-104">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="e2588-104">Frequently asked questions</span></span>

[<span data-ttu-id="e2588-105">如果一个或多个会议参与者的体验不好，CQD 为什么将呼叫标记为 "正常"？</span><span class="sxs-lookup"><span data-stu-id="e2588-105">Why does CQD mark a call as "Good" if one or more meeting participants had a poor experience?</span></span>](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[<span data-ttu-id="e2588-106">为什么在度量值和用户计数值上看到最多0.2% 的差异以及如何获取最准确的卷？</span><span class="sxs-lookup"><span data-stu-id="e2588-106">Why do I see up to 0.2% difference in call and user count values on measures and how to get most accurate volumes? </span></span>](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[<span data-ttu-id="e2588-107">为什么 Skype for Business 中的 CQD 数据与来自团队的 CQD 数据不同？</span><span class="sxs-lookup"><span data-stu-id="e2588-107">Why is CQD data from Skype for Business different than CQD data from Teams? </span></span>](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[<span data-ttu-id="e2588-108">为什么我在 CQD 中看不到 EUII？</span><span class="sxs-lookup"><span data-stu-id="e2588-108">Why can't I see EUII in CQD?</span></span>](#why-cant-i-see-euii-in-cqd)

[<span data-ttu-id="e2588-109">为什么我仅当我筛选了团队时，我在 CQD 中看到 Skype for Business 信息？</span><span class="sxs-lookup"><span data-stu-id="e2588-109">Why am I seeing Skype for Business information in CQD when I've filtered for Teams only?</span></span>](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a><span data-ttu-id="e2588-110">如果一个或多个会议参与者的体验不好，CQD 为什么将呼叫标记为 "正常"？</span><span class="sxs-lookup"><span data-stu-id="e2588-110">Why does CQD mark a call as "Good" if one or more meeting participants had a poor experience?</span></span>

<span data-ttu-id="e2588-111">查看[流分类](stream-classification-in-call-quality-dashboard.md)CQD 使用的规则。</span><span class="sxs-lookup"><span data-stu-id="e2588-111">Check out the rules CQD uses for [stream classification](stream-classification-in-call-quality-dashboard.md).</span></span>
 
<span data-ttu-id="e2588-112">对于音频流，任何5个分类器（根据调用的平均长度计算）都可能位于 "良好" 参数中。</span><span class="sxs-lookup"><span data-stu-id="e2588-112">For audio streams, any of the 5 classifiers, which are calculated for the average based on the length of the call, could all be within "good" parameters.</span></span> <span data-ttu-id="e2588-113">这并不意味着用户不会遇到对音频的丢弃、静态或故障的内容。</span><span class="sxs-lookup"><span data-stu-id="e2588-113">It doesn't mean the users didn't experience something that contributed to an audio drop out, static, or glitch.</span></span> 

<span data-ttu-id="e2588-114">若要确定是否是网络问题，请查看会话平均值与最大值之间的增量。</span><span class="sxs-lookup"><span data-stu-id="e2588-114">To determine if it was a network problem, look at the delta between the average values for the session and the max values.</span></span> <span data-ttu-id="e2588-115">最大值是会话期间检测和报告的最大值。</span><span class="sxs-lookup"><span data-stu-id="e2588-115">Max values are the maximum detected and reported during the session.</span></span>
 
<span data-ttu-id="e2588-116">下面是如何解决这种情况的示例。</span><span class="sxs-lookup"><span data-stu-id="e2588-116">Here's an example of how to troubleshoot this situation.</span></span> <span data-ttu-id="e2588-117">假设你在呼叫过程中获取网络跟踪，并且前20分钟，没有丢失数据包，但你的数据包的间隔为1.5 秒，然后就可以在通话的其余部分中使用。</span><span class="sxs-lookup"><span data-stu-id="e2588-117">Let's say you take a network trace during a call and the first 20 minutes there are no lost packets but then you have a gap of 1.5 seconds of packets and then good for the remainder of the call.</span></span> <span data-ttu-id="e2588-118">平均 <10% (0.1) 数据包丢失，即使在 Wireshark 跟踪 RTP 分析中也是如此。</span><span class="sxs-lookup"><span data-stu-id="e2588-118">The average is going to be <10% (0.1) Packet loss even in a Wireshark trace RTP analysis.</span></span> <span data-ttu-id="e2588-119">最大数据包丢失程度是多少？</span><span class="sxs-lookup"><span data-stu-id="e2588-119">What was the Max Packet Loss?</span></span> <span data-ttu-id="e2588-120">5秒内的1.5 秒将 (0.3) 30%。</span><span class="sxs-lookup"><span data-stu-id="e2588-120">1.5 Seconds in a 5-second period would be 30% (0.3).</span></span> <span data-ttu-id="e2588-121">在五秒的采样期内发生的情况 (可能还是可以在) 抽样期间拆分？</span><span class="sxs-lookup"><span data-stu-id="e2588-121">Did that occur within the five second sampling period (maybe or it could be split over the sampling period)?</span></span>
 
<span data-ttu-id="e2588-122">如果网络指标在平均值和最大值中看起来很好，请查看其他遥测数据：</span><span class="sxs-lookup"><span data-stu-id="e2588-122">If network metrics look good in the averages and max values, then look to other telemetry data:</span></span> 
- <span data-ttu-id="e2588-123">检查 CPU 的事件比率不足，查看检测到的 CPU 资源是否不足，导致质量较差。</span><span class="sxs-lookup"><span data-stu-id="e2588-123">Check CPU Insufficient Event Ratio to see if the detected CPU resources available were insufficient and caused poor quality.</span></span> 
- <span data-ttu-id="e2588-124">音频设备是否处于半双工模式下，以防止因麦克风接近扬声器而导致的反馈？</span><span class="sxs-lookup"><span data-stu-id="e2588-124">Was the audio device in Half Duplex mode to prevent feedback due to microphones that are to close to speakers?</span></span> 
- <span data-ttu-id="e2588-125">检查 Device 半双工 AEC 事件比率。</span><span class="sxs-lookup"><span data-stu-id="e2588-125">Check the Device Half Duplex AEC Event Ratio.</span></span> <span data-ttu-id="e2588-126">当插入集线器或坞站时，设备 glitching 或麦克风 glitching 引入噪音或静态信号的原因如下：</span><span class="sxs-lookup"><span data-stu-id="e2588-126">Was the device glitching or the microphone glitching introducing noise or static due to USB Audio Drop outs when plugged into a Hub or Docking Station:</span></span>  
- <span data-ttu-id="e2588-127">检查设备故障和麦克风故障事件比率。</span><span class="sxs-lookup"><span data-stu-id="e2588-127">Check the Device Glitches and Microphone glitches event ratios.</span></span> <span data-ttu-id="e2588-128">设备本身是否正常工作？</span><span class="sxs-lookup"><span data-stu-id="e2588-128">Was the device itself functioning properly?</span></span>  
- <span data-ttu-id="e2588-129">检查捕获和呈现设备无法正常工作的事件比率。</span><span class="sxs-lookup"><span data-stu-id="e2588-129">Check the Capture and Render Device Not Functioning Event Ratios.</span></span>


<span data-ttu-id="e2588-130">有关 CQD 遥测中可用的维度和度量值的详细信息，请参阅[通话质量仪表板中可用的维度和度量](dimensions-and-measures-available-in-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="e2588-130">For more on dimensions and measures available in CQD telemetry, read [Dimensions and measurements available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>

<span data-ttu-id="e2588-131">对于背景噪音，请选中 "静音事件比率" 以查看参与者静音的时间长度。</span><span class="sxs-lookup"><span data-stu-id="e2588-131">For background noise, check mute event ratio to see the length of time participants were muted.</span></span>
 
<span data-ttu-id="e2588-132">在 CQD 中创建详细报表，并筛选会议 ID 以查看会议中的所有用户和流并添加感兴趣的字段。</span><span class="sxs-lookup"><span data-stu-id="e2588-132">Create detailed reports in CQD and filter on Meeting ID to look at all users and streams in a meeting and add the fields you are interested in.</span></span> <span data-ttu-id="e2588-133">报告问题的用户可能不是遇到该问题的用户。</span><span class="sxs-lookup"><span data-stu-id="e2588-133">A user reporting the issue may not be the one that was having the issue.</span></span> <span data-ttu-id="e2588-134">他们只是报告体验。</span><span class="sxs-lookup"><span data-stu-id="e2588-134">They are just reporting the experience.</span></span>
 
<span data-ttu-id="e2588-135">遥测不一定会解决该问题，但它可以帮助您更好地了解在何处查看和通知您的决策。</span><span class="sxs-lookup"><span data-stu-id="e2588-135">The telemetry will not necessarily call out the issue, but it can help you better understand where to look and inform your decisions.</span></span> <span data-ttu-id="e2588-136">是网络、设备、驱动程序还是固件更新、使用或用户？</span><span class="sxs-lookup"><span data-stu-id="e2588-136">Is it network, device, driver or firmware updates, usage, or user?</span></span>

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a><span data-ttu-id="e2588-137">为什么在度量值和用户计数值上看到最多0.2% 的差异以及如何获取最准确的卷？</span><span class="sxs-lookup"><span data-stu-id="e2588-137">Why do I see up to 0.2% difference in call and user count values on measures and how to get most accurate volumes?</span></span> 
<span data-ttu-id="e2588-138">若要计算 "呼叫计数" 和 "用户计数" 度量值，请对数据集中的调用或用户标识符执行不同的 countif 操作。</span><span class="sxs-lookup"><span data-stu-id="e2588-138">To compute call count and user count measures, a distinct countif operation is performed against the call or user identifiers in the data set.</span></span> <span data-ttu-id="e2588-139">在大型数据集上，具有不同的 countif 操作固有的最大0.2% 错误。</span><span class="sxs-lookup"><span data-stu-id="e2588-139">On large data sets, there is an up to 0.2% error inherent with the distinct countif operation.</span></span> <span data-ttu-id="e2588-140">对于最准确的卷，你应该依赖流计数度量值，因为它们不依赖于此不同的 countif 操作。</span><span class="sxs-lookup"><span data-stu-id="e2588-140">For the most accurate volume, you should rely on stream count measures since they do not rely on this distinct countif operation.</span></span> <span data-ttu-id="e2588-141">筛选以减少数据量可能会减少错误，但可能无法在不同的调用和用户计数中消除此错误来源。</span><span class="sxs-lookup"><span data-stu-id="e2588-141">Filtering to reduce the data volume may reduce the error but may not eliminate this source of error in distinct call and user counts.</span></span> <span data-ttu-id="e2588-142">请参阅["呼叫质量" 仪表板中可用的尺寸和测量](dimensions-and-measures-available-in-call-quality-dashboard.md)值，这些测量受影响。</span><span class="sxs-lookup"><span data-stu-id="e2588-142">Refer to [Dimensions and measurements available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md) for which measures are impacted.</span></span>


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a><span data-ttu-id="e2588-143">为什么 Skype for Business 中的 CQD 数据与来自团队的 CQD 数据不同？</span><span class="sxs-lookup"><span data-stu-id="e2588-143">Why is CQD data from Skype for Business different than CQD data from Teams?</span></span> 


> [!IMPORTANT]
> <span data-ttu-id="e2588-144">从2020年7月1日起，较早的 CQD (CQD.lync.com) 使用最新 CQD (CQD 中的数据。Teams.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="e2588-144">As of July 1, 2020, the older CQD (CQD.lync.com) uses data from the latest CQD (CQD.Teams.microsoft.com).</span></span> <span data-ttu-id="e2588-145">较旧的 CQD 数据不再可用，并且您不能导出您的建筑物或报表数据。</span><span class="sxs-lookup"><span data-stu-id="e2588-145">The older CQD data is no longer available, and you can't export your building or report data.</span></span> <span data-ttu-id="e2588-146">您仍然可以使用 Skype for Business 管理中心) 的 CQD.lync.com (，但我们会立即关闭对 CQD.lync.com 的访问，因此应转到 CQD。Teams.microsoft.com 如果还未执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e2588-146">You can still use CQD.lync.com (available from the Skype for Business admin center), but we'll turn off access to CQD.lync.com soon, so you should move to CQD.Teams.microsoft.com if you haven't already done so.</span></span>


<span data-ttu-id="e2588-147">如果你尝试比较旧 CQD 之间的数据与 Skype for Business 旧门户 (cqd.lync.com) 和团队管理中心 (cqd.teams.microsoft.com) 中的最新 CQD，你将很快发现数据不匹配。</span><span class="sxs-lookup"><span data-stu-id="e2588-147">If you're trying to compare data between the older CQD from the Skype for Business legacy portal (cqd.lync.com) and the latest CQD from the Teams admin center (cqd.teams.microsoft.com), you'll quickly notice that the data doesn't match.</span></span> <span data-ttu-id="e2588-148">这是因为最新的 CQD 报告了许多额外的通话方案。</span><span class="sxs-lookup"><span data-stu-id="e2588-148">That's because the latest CQD reports on many additional calling scenarios.</span></span> <span data-ttu-id="e2588-149">如果您仍在使用来自较旧 CQD 的报表，请使用本文帮助解释这些报表： " [Skype for business" 服务器的 "呼叫质量" 仪表板](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard)。</span><span class="sxs-lookup"><span data-stu-id="e2588-149">If you're still using reports from the older CQD, use this article to help you interpret those reports: [Call Quality Dashboard for Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard).</span></span>


  
### <a name="why-cant-i-see-euii-in-cqd"></a><span data-ttu-id="e2588-150">为什么我在 CQD 中看不到 EUII？</span><span class="sxs-lookup"><span data-stu-id="e2588-150">Why can't I see EUII in CQD?</span></span>

<span data-ttu-id="e2588-151">这些管理员角色可以访问 CQD，但他们不能查看 EUII (最终用户可识别信息) ：</span><span class="sxs-lookup"><span data-stu-id="e2588-151">These admin roles can access CQD, but they can't view EUII (end-user identifiable information):</span></span>
- <span data-ttu-id="e2588-152">Microsoft 365 报表读者</span><span class="sxs-lookup"><span data-stu-id="e2588-152">Microsoft 365 Reports Reader</span></span>
- <span data-ttu-id="e2588-153">团队沟通支持专家</span><span class="sxs-lookup"><span data-stu-id="e2588-153">Teams Communications Support Specialist</span></span>

<span data-ttu-id="e2588-154">若要了解有关可访问 CQD 的角色的详细信息-包括 EUII-读取[分配角色以访问 CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)。</span><span class="sxs-lookup"><span data-stu-id="e2588-154">To learn more about roles that can access CQD - including EUII - read [Assign roles for accessing CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).</span></span>

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a><span data-ttu-id="e2588-155">为什么我仅当我筛选了团队时，我在 CQD 中看到 Skype for Business 信息？</span><span class="sxs-lookup"><span data-stu-id="e2588-155">Why am I seeing Skype for Business information in CQD when I've filtered for Teams only?</span></span>

<span data-ttu-id="e2588-156">仅在 CQD 报表中筛选团队时 (isTeams = 1) 中，你将筛选*第一个终结点*为团队的所有调用。</span><span class="sxs-lookup"><span data-stu-id="e2588-156">When you filter for Teams only in CQD reports (isTeams = 1), you're filtering for all calls where the *first endpoint* is Teams.</span></span> <span data-ttu-id="e2588-157">如果*第二个终结点*是 Skype for business，则该信息将显示在您的 CQD 报告中。</span><span class="sxs-lookup"><span data-stu-id="e2588-157">If the *second endpoint* is Skype for Business, that information will show up in your CQD report.</span></span>

<span data-ttu-id="e2588-158">CQDv2 和 CQDv3 将始终具有不同的总数，因为 CQDv3 将具有 CQDv2 没有的新方案。</span><span class="sxs-lookup"><span data-stu-id="e2588-158">CQDv2 and CQDv3 will always have different total counts since CQDv3 will have new scenarios that CQDv2 will not have.</span></span> <span data-ttu-id="e2588-159">这就是比较 "摘要总数" 或 "不带筛选器的聚合的所有数字" 的原因将具有这些预期的差异。</span><span class="sxs-lookup"><span data-stu-id="e2588-159">That’s why comparing Summary Total or Aggregated all-up numbers with no filters will have these expected differences.</span></span>  

<span data-ttu-id="e2588-160">根据客户的情形，CQDv3 将包括 SFB 2019 本地呼叫 (如果 SFB 2019 与数据连接器) 一起使用，则 Skype 机器人将 (AA、CVI、VDI) 、实时事件和 PSTN 呼叫中进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="e2588-160">Depending on Customers’ scenario, CQDv3 will include SFB 2019 on-premises calls (if SFB 2019 is used with a data connector), Skype Bot calls (AA, CVI, VDI), Live Events and PSTN calls.</span></span> <span data-ttu-id="e2588-161">适用于客户的方案/功能，但其数据不在 CQD V2 中。</span><span class="sxs-lookup"><span data-stu-id="e2588-161">Scenarios/Features which are available for the customers, but their data are not in CQD V2.</span></span>

<span data-ttu-id="e2588-162">例如，预计你的客户和你将看到200000音频流，并且 CQD V2 摘要报告中出现5000故障。5500故障与300000音频流的对比 (来自2019本地呼叫、CVI 呼叫、PSTN 呼叫等) CQD V3。</span><span class="sxs-lookup"><span data-stu-id="e2588-162">For instance, it is expected that your customers and you will see 200,000 audio streams, with 5000 failures in CQD V2 Summary Report; versus 300,000 audio streams with 5500 failures (coming from 2019 on-prem calls, CVI calls, PSTN calls etc) in CQD V3.</span></span>

<span data-ttu-id="e2588-163">为了确定是否存在任何意外的差异，您必须查看整个数据的各种细目。</span><span class="sxs-lookup"><span data-stu-id="e2588-163">In order to determine, if there are any unexpected differences, you must look at various breakdowns of the overall data.</span></span>  <span data-ttu-id="e2588-164">与意向进行比较。</span><span class="sxs-lookup"><span data-stu-id="e2588-164">Compare with intent.</span></span>  <span data-ttu-id="e2588-165">按用户代理类别对数据进行切片是我们建议的第一项。</span><span class="sxs-lookup"><span data-stu-id="e2588-165">Slicing the data by User Agent Category Pair is one of the first things we recommend.</span></span>  <span data-ttu-id="e2588-166">*第一种产品*和*第二种产品*也是良好的切片器。</span><span class="sxs-lookup"><span data-stu-id="e2588-166">*First Product* and *Second Product* are also good slicers.</span></span>  


## <a name="related-topics"></a><span data-ttu-id="e2588-167">相关主题</span><span class="sxs-lookup"><span data-stu-id="e2588-167">Related topics</span></span>

[<span data-ttu-id="e2588-168">改善和监控团队的通话质量</span><span class="sxs-lookup"><span data-stu-id="e2588-168">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="e2588-169">什么是 CQD？</span><span class="sxs-lookup"><span data-stu-id="e2588-169">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="e2588-170">设置通话质量仪表板 (CQD) </span><span class="sxs-lookup"><span data-stu-id="e2588-170">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="e2588-171">上载租户和生成数据</span><span class="sxs-lookup"><span data-stu-id="e2588-171">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="e2588-172">CQD 数据和报告</span><span class="sxs-lookup"><span data-stu-id="e2588-172">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="e2588-173">使用 CQD 管理通话和会议质量</span><span class="sxs-lookup"><span data-stu-id="e2588-173">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="e2588-174">CQD 中可用的维度和度量值</span><span class="sxs-lookup"><span data-stu-id="e2588-174">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="e2588-175">CQD 中的流分类</span><span class="sxs-lookup"><span data-stu-id="e2588-175">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="e2588-176">使用 Power BI 分析 CQD 数据</span><span class="sxs-lookup"><span data-stu-id="e2588-176">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)

[<span data-ttu-id="e2588-177">Teams 疑难解答</span><span class="sxs-lookup"><span data-stu-id="e2588-177">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)