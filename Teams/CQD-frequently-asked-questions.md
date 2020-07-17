---
title: 通话质量仪表板（CQD）常见问题（FAQ）
ms.author: lolaj
author: LolaJacobsen
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
description: 阅读常见问题（FAQ）和有关 Microsoft 团队通话质量仪表板（CQD）的解答。
ms.openlocfilehash: f33d66d9c8abb465c6680bacbbd2ff200cf930c6
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086168"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a><span data-ttu-id="be20a-103">通话质量仪表板（CQD）常见问题（FAQ）</span><span class="sxs-lookup"><span data-stu-id="be20a-103">Call Quality Dashboard (CQD) Frequently asked questions (FAQ)</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="be20a-104">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="be20a-104">Frequently asked questions</span></span>

[<span data-ttu-id="be20a-105">如果一个或多个会议参与者的体验不好，CQD 为什么将呼叫标记为 "正常"？</span><span class="sxs-lookup"><span data-stu-id="be20a-105">Why does CQD mark a call as "Good" if one or more meeting participants had a poor experience?</span></span>](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[<span data-ttu-id="be20a-106">为什么在度量值和用户计数值上看到最多0.2% 的差异以及如何获取最准确的卷？</span><span class="sxs-lookup"><span data-stu-id="be20a-106">Why do I see up to 0.2% difference in call and user count values on measures and how to get most accurate volumes? </span></span>](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[<span data-ttu-id="be20a-107">为什么 CQD v2 报表数据看起来与 CQD v3 报表数据不同？</span><span class="sxs-lookup"><span data-stu-id="be20a-107">Why does my CQD v2 report data look different than the CQD v3 report data? </span></span>](#why-does-my-cqd-v2-report-data-look-different-than-the-cqd-v3-report-data)

[<span data-ttu-id="be20a-108">为什么 Skype for Business 中的 CQD 数据与来自团队的 CQD 数据不同？</span><span class="sxs-lookup"><span data-stu-id="be20a-108">Why is CQD data from Skype for Business different than CQD data from Teams? </span></span>](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[<span data-ttu-id="be20a-109">为什么我在 CQD 中看不到 EUII？</span><span class="sxs-lookup"><span data-stu-id="be20a-109">Why can't I see EUII in CQD?</span></span>](#why-cant-i-see-euii-in-cqd)

[<span data-ttu-id="be20a-110">为什么我仅当我筛选了团队时，我在 CQD 中看到 Skype for Business 信息？</span><span class="sxs-lookup"><span data-stu-id="be20a-110">Why am I seeing Skype for Business information in CQD when I've filtered for Teams only?</span></span>](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a><span data-ttu-id="be20a-111">如果一个或多个会议参与者的体验不好，CQD 为什么将呼叫标记为 "正常"？</span><span class="sxs-lookup"><span data-stu-id="be20a-111">Why does CQD mark a call as "Good" if one or more meeting participants had a poor experience?</span></span>

<span data-ttu-id="be20a-112">查看[流分类](stream-classification-in-call-quality-dashboard.md)CQD 使用的规则。</span><span class="sxs-lookup"><span data-stu-id="be20a-112">Check out the rules CQD uses for [stream classification](stream-classification-in-call-quality-dashboard.md).</span></span>
 
<span data-ttu-id="be20a-113">对于音频流，任何5个分类器（根据调用的平均长度计算）都可能位于 "良好" 参数中。</span><span class="sxs-lookup"><span data-stu-id="be20a-113">For audio streams, any of the 5 classifiers, which are calculated for the average based on the length of the call, could all be within "good" parameters.</span></span> <span data-ttu-id="be20a-114">这并不意味着用户不会遇到对音频的丢弃、静态或故障的内容。</span><span class="sxs-lookup"><span data-stu-id="be20a-114">It doesn't mean the users didn't experience something that contributed to an audio drop out, static, or glitch.</span></span> 

<span data-ttu-id="be20a-115">若要确定是否是网络问题，请查看会话平均值与最大值之间的增量。</span><span class="sxs-lookup"><span data-stu-id="be20a-115">To determine if it was a network problem, look at the delta between the average values for the session and the max values.</span></span> <span data-ttu-id="be20a-116">最大值是会话期间检测和报告的最大值。</span><span class="sxs-lookup"><span data-stu-id="be20a-116">Max values are the maximum detected and reported during the session.</span></span>
 
<span data-ttu-id="be20a-117">下面是如何解决这种情况的示例。</span><span class="sxs-lookup"><span data-stu-id="be20a-117">Here's an example of how to troubleshoot this situation.</span></span> <span data-ttu-id="be20a-118">假设你在呼叫过程中获取网络跟踪，并且前20分钟，没有丢失数据包，但你的数据包的间隔为1.5 秒，然后就可以在通话的其余部分中使用。</span><span class="sxs-lookup"><span data-stu-id="be20a-118">Let's say you take a network trace during a call and the first 20 minutes there are no lost packets but then you have a gap of 1.5 seconds of packets and then good for the remainder of the call.</span></span> <span data-ttu-id="be20a-119">平均 <10% （0.1）数据包丢失，即使在 Wireshark 跟踪 RTP 分析中也是如此。</span><span class="sxs-lookup"><span data-stu-id="be20a-119">The average is going to be <10% (0.1) Packet loss even in a Wireshark trace RTP analysis.</span></span> <span data-ttu-id="be20a-120">最大数据包丢失程度是多少？</span><span class="sxs-lookup"><span data-stu-id="be20a-120">What was the Max Packet Loss?</span></span> <span data-ttu-id="be20a-121">5秒内的1.5 秒将是30% （0.3）。</span><span class="sxs-lookup"><span data-stu-id="be20a-121">1.5 Seconds in a 5-second period would be 30% (0.3).</span></span> <span data-ttu-id="be20a-122">在五秒的采样周期内发生（也许还是可以在采样周期内拆分）？</span><span class="sxs-lookup"><span data-stu-id="be20a-122">Did that occur within the five second sampling period (maybe or it could be split over the sampling period)?</span></span>
 
<span data-ttu-id="be20a-123">如果网络指标在平均值和最大值中看起来很好，请查看其他遥测数据：</span><span class="sxs-lookup"><span data-stu-id="be20a-123">If network metrics look good in the averages and max values, then look to other telemetry data:</span></span> 
- <span data-ttu-id="be20a-124">检查 CPU 的事件比率不足，查看检测到的 CPU 资源是否不足，导致质量较差。</span><span class="sxs-lookup"><span data-stu-id="be20a-124">Check CPU Insufficient Event Ratio to see if the detected CPU resources available were insufficient and caused poor quality.</span></span> 
- <span data-ttu-id="be20a-125">音频设备是否处于半双工模式下，以防止因麦克风接近扬声器而导致的反馈？</span><span class="sxs-lookup"><span data-stu-id="be20a-125">Was the audio device in Half Duplex mode to prevent feedback due to microphones that are to close to speakers?</span></span> 
- <span data-ttu-id="be20a-126">检查 Device 半双工 AEC 事件比率。</span><span class="sxs-lookup"><span data-stu-id="be20a-126">Check the Device Half Duplex AEC Event Ratio.</span></span> <span data-ttu-id="be20a-127">当插入集线器或坞站时，设备 glitching 或麦克风 glitching 引入噪音或静态信号的原因如下：</span><span class="sxs-lookup"><span data-stu-id="be20a-127">Was the device glitching or the microphone glitching introducing noise or static due to USB Audio Drop outs when plugged into a Hub or Docking Station:</span></span>  
- <span data-ttu-id="be20a-128">检查设备故障和麦克风故障事件比率。</span><span class="sxs-lookup"><span data-stu-id="be20a-128">Check the Device Glitches and Microphone glitches event ratios.</span></span> <span data-ttu-id="be20a-129">设备本身是否正常工作？</span><span class="sxs-lookup"><span data-stu-id="be20a-129">Was the device itself functioning properly?</span></span>  
- <span data-ttu-id="be20a-130">检查捕获和呈现设备无法正常工作的事件比率。</span><span class="sxs-lookup"><span data-stu-id="be20a-130">Check the Capture and Render Device Not Functioning Event Ratios.</span></span>


<span data-ttu-id="be20a-131">有关 CQD 遥测中可用的维度和度量值的详细信息，请参阅[通话质量仪表板中可用的维度和度量](dimensions-and-measures-available-in-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="be20a-131">For more on dimensions and measures available in CQD telemetry, read [Dimensions and measurements available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>

<span data-ttu-id="be20a-132">对于背景噪音，请选中 "静音事件比率" 以查看参与者静音的时间长度。</span><span class="sxs-lookup"><span data-stu-id="be20a-132">For background noise, check mute event ratio to see the length of time participants were muted.</span></span>
 
<span data-ttu-id="be20a-133">在 CQD 中创建详细报表，并筛选会议 ID 以查看会议中的所有用户和流并添加感兴趣的字段。</span><span class="sxs-lookup"><span data-stu-id="be20a-133">Create detailed reports in CQD and filter on Meeting ID to look at all users and streams in a meeting and add the fields you are interested in.</span></span> <span data-ttu-id="be20a-134">报告问题的用户可能不是遇到该问题的用户。</span><span class="sxs-lookup"><span data-stu-id="be20a-134">A user reporting the issue may not be the one that was having the issue.</span></span> <span data-ttu-id="be20a-135">他们只是报告体验。</span><span class="sxs-lookup"><span data-stu-id="be20a-135">They are just reporting the experience.</span></span>
 
<span data-ttu-id="be20a-136">遥测不一定会解决该问题，但它可以帮助您更好地了解在何处查看和通知您的决策。</span><span class="sxs-lookup"><span data-stu-id="be20a-136">The telemetry will not necessarily call out the issue, but it can help you better understand where to look and inform your decisions.</span></span> <span data-ttu-id="be20a-137">是网络、设备、驱动程序还是固件更新、使用或用户？</span><span class="sxs-lookup"><span data-stu-id="be20a-137">Is it network, device, driver or firmware updates, usage, or user?</span></span>

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a><span data-ttu-id="be20a-138">为什么在度量值和用户计数值上看到最多0.2% 的差异以及如何获取最准确的卷？</span><span class="sxs-lookup"><span data-stu-id="be20a-138">Why do I see up to 0.2% difference in call and user count values on measures and how to get most accurate volumes?</span></span> 
<span data-ttu-id="be20a-139">若要计算 "呼叫计数" 和 "用户计数" 度量值，请对数据集中的调用或用户标识符执行不同的 countif 操作。</span><span class="sxs-lookup"><span data-stu-id="be20a-139">To compute call count and user count measures, a distinct countif operation is performed against the call or user identifiers in the data set.</span></span> <span data-ttu-id="be20a-140">在大型数据集上，具有不同的 countif 操作固有的最大0.2% 错误。</span><span class="sxs-lookup"><span data-stu-id="be20a-140">On large data sets, there is an up to 0.2% error inherent with the distinct countif operation.</span></span> <span data-ttu-id="be20a-141">对于最准确的卷，你应该依赖流计数度量值，因为它们不依赖于此不同的 countif 操作。</span><span class="sxs-lookup"><span data-stu-id="be20a-141">For the most accurate volume, you should rely on stream count measures since they do not rely on this distinct countif operation.</span></span> <span data-ttu-id="be20a-142">筛选以减少数据量可能会减少错误，但可能无法在不同的调用和用户计数中消除此错误来源。</span><span class="sxs-lookup"><span data-stu-id="be20a-142">Filtering to reduce the data volume may reduce the error but may not eliminate this source of error in distinct call and user counts.</span></span> <span data-ttu-id="be20a-143">请参阅["呼叫质量" 仪表板中可用的尺寸和测量](dimensions-and-measures-available-in-call-quality-dashboard.md)值，这些测量受影响。</span><span class="sxs-lookup"><span data-stu-id="be20a-143">Refer to [Dimensions and measurements available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md) for which measures are impacted.</span></span>

### <a name="why-does-my-cqd-v2-report-data-look-different-than-the-cqd-v3-report-data"></a><span data-ttu-id="be20a-144">为什么 CQD v2 报表数据看起来与 CQD v3 报表数据不同？</span><span class="sxs-lookup"><span data-stu-id="be20a-144">Why does my CQD v2 report data look different than the CQD v3 report data?</span></span> 

<span data-ttu-id="be20a-145">如果你看到 CQD v2 和 v3 之间的数据差异，请确保在 "苹果" 和 "窄" 级别（而不是聚合级别）上执行数据比较或验证。</span><span class="sxs-lookup"><span data-stu-id="be20a-145">If you see data differences between CQD v2 and v3, make sure that data comparison or validation is done on an 'apples-to-apples'  and narrow level, not an aggregated level.</span></span> <span data-ttu-id="be20a-146">例如，如果你筛选 MSIT "建筑物 30" WiFi 团队桌面客户端数据的两个报表，则 v2 和 v3 的低质量百分比应该相同。</span><span class="sxs-lookup"><span data-stu-id="be20a-146">For example, if you filter both reports for MSIT 'Building 30' WiFi Teams Desktop client data, the Percentage of Poor Quality should be the same between v2 and v3.</span></span>

<span data-ttu-id="be20a-147">CallSetup 失败的 CQDv2 分类仅考虑 "音频" 模态，在 CQDv3 中，对每个模态（音频、视频和应用共享）进行分类，并在各自的模态流中表示。</span><span class="sxs-lookup"><span data-stu-id="be20a-147">CQDv2 classification for CallSetup failure is only considered for "Audio" modality, in CQDv3 this classification happens for every modality (Audio, Video and Appsharing) and is represented in the respective modality stream.</span></span> 

<span data-ttu-id="be20a-148">对于团队，CQDv2 将相同的用户反馈应用到所有形式 CQDv3 应用针对团队的模态的反馈基础。</span><span class="sxs-lookup"><span data-stu-id="be20a-148">For Teams, CQDv2 applies the same user feedback to all modalities CQDv3 applies feedback base on modality for Teams.</span></span>

<span data-ttu-id="be20a-149">CQD V3 包括</span><span class="sxs-lookup"><span data-stu-id="be20a-149">CQD V3 includes</span></span> 
1. <span data-ttu-id="be20a-150">Skype for Business Server 2019 通话，</span><span class="sxs-lookup"><span data-stu-id="be20a-150">Skype for Business Server 2019 calls,</span></span> 
2. <span data-ttu-id="be20a-151">Skype 机器人呼叫，例如：自动助理、呼叫队列、会议通知服务</span><span class="sxs-lookup"><span data-stu-id="be20a-151">Skype Bot calls, such as:auto attendant, call queue, conference announcement service,</span></span> 
3. <span data-ttu-id="be20a-152">虚拟桌面界面，</span><span class="sxs-lookup"><span data-stu-id="be20a-152">Virtual Desktop Interface,</span></span>
4. <span data-ttu-id="be20a-153">会议视频互操作，</span><span class="sxs-lookup"><span data-stu-id="be20a-153">Conference Video Interop,</span></span>
3. <span data-ttu-id="be20a-154">实时事件发布者和演示者通话，以及</span><span class="sxs-lookup"><span data-stu-id="be20a-154">Live Events Publisher and Presenter calls, and</span></span> 
4. <span data-ttu-id="be20a-155">PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="be20a-155">PSTN calls.</span></span> 

<span data-ttu-id="be20a-156">若要了解如何使用这些 Power BI 模板分析和报告你的 CQD 数据，请参阅[使用 POWER BI FOR CQD 报表](cqd-power-bi-query-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="be20a-156">To learn how to use these Power BI templates to analyze and report your CQD data, read [Use Power BI for CQD reports](cqd-power-bi-query-templates.md).</span></span>


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a><span data-ttu-id="be20a-157">为什么 Skype for Business 中的 CQD 数据与来自团队的 CQD 数据不同？</span><span class="sxs-lookup"><span data-stu-id="be20a-157">Why is CQD data from Skype for Business different than CQD data from Teams?</span></span> 


> [!IMPORTANT]
> <span data-ttu-id="be20a-158">从2020年7月1日起，较早的 CQD 访问最新 CQD 中的数据。</span><span class="sxs-lookup"><span data-stu-id="be20a-158">As of July 1, 2020, the older CQD accesses data from the latest CQD.</span></span> <span data-ttu-id="be20a-159">较旧的 CQD 数据不再可用，并且您不能导出您的建筑物或报表数据。</span><span class="sxs-lookup"><span data-stu-id="be20a-159">The older CQD data is no longer available, and you can't export your building or report data.</span></span>


<span data-ttu-id="be20a-160">如果您尝试比较旧 CQD 之间的数据与 Skype for Business 旧式门户（cqd.lync.com）和团队管理中心（cqd.teams.microsoft.com）中的最新 CQD，您将很快发现数据不匹配。</span><span class="sxs-lookup"><span data-stu-id="be20a-160">If you're trying to compare data between the older CQD from the Skype for Business legacy portal (cqd.lync.com) and the latest CQD from the Teams admin center (cqd.teams.microsoft.com), you'll quickly notice that the data doesn't match.</span></span> <span data-ttu-id="be20a-161">这是因为最新的 CQD 报告了许多额外的通话方案。</span><span class="sxs-lookup"><span data-stu-id="be20a-161">That's because the latest CQD reports on many additional calling scenarios.</span></span> <span data-ttu-id="be20a-162">如果您仍在使用来自较旧 CQD 的报表，请使用本文帮助解释这些报表： " [Skype for business" 服务器的 "呼叫质量" 仪表板](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard)。</span><span class="sxs-lookup"><span data-stu-id="be20a-162">If you're still using reports from the older CQD, use this article to help you interpret those reports: [Call Quality Dashboard for Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard).</span></span>



<span data-ttu-id="be20a-163">下面是一个应用特定筛选器以比较 CQD v2 和 CQD v3 数据的示例：</span><span class="sxs-lookup"><span data-stu-id="be20a-163">Here's an example of applying specific filters to compare CQD v2 and CQD v3 data:</span></span>

1. <span data-ttu-id="be20a-164">QoE 记录可用 = True</span><span class="sxs-lookup"><span data-stu-id="be20a-164">QoE Record Available = True</span></span>

2. <span data-ttu-id="be20a-165">Add 是服务器对筛选器，其值：客户端：客户端和客户端：服务器。</span><span class="sxs-lookup"><span data-stu-id="be20a-165">Add Is Server Pair filter with value: Client:Client and Client:Server.</span></span> <span data-ttu-id="be20a-166">大多数租户更喜欢排除服务器：服务器调用。</span><span class="sxs-lookup"><span data-stu-id="be20a-166">Most tenants prefer to exclude Server:Server calls.</span></span>

3. <span data-ttu-id="be20a-167">为用户代理类别添加筛选器并筛选出自动助理、呼叫队列、Bot、房间系统、MediationServer、会议公告服务、VDI 等。</span><span class="sxs-lookup"><span data-stu-id="be20a-167">Add a filter for User Agent Category and filter out Auto Attendant, Call Queue, Bot, Room system, MediationServer, Conference Announcement service, VDI, etc.</span></span>

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard1.png" alt-text="在 CQD v3 中应用特定筛选器的屏幕截图":::

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard2.png" alt-text="在 CQD v2 中应用特定筛选器的屏幕截图":::

#### <a name="other-expected-differences-between-cqd-v2-and-cqd-v3"></a><span data-ttu-id="be20a-170">CQD v2 和 CQD v3 之间的其他预期差异</span><span class="sxs-lookup"><span data-stu-id="be20a-170">Other expected differences between CQD v2 and CQD v3</span></span>

<span data-ttu-id="be20a-171">若要了解有关旧的和最新 CQD 之间的差异的详细信息，请阅读2019年11月5日的 "[高级通话质量" 仪表板博客简介](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Introducing-the-Advanced-Call-Quality-Dashboard/ba-p/972586)。</span><span class="sxs-lookup"><span data-stu-id="be20a-171">To learn more about the differences between the older and latest CQD, read the [Introducing the Advanced Call Quality Dashboard](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Introducing-the-Advanced-Call-Quality-Dashboard/ba-p/972586) blog, from November 5, 2019.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="be20a-172">从2020年7月1日起，较早的 CQD 访问最新 CQD 中的数据。</span><span class="sxs-lookup"><span data-stu-id="be20a-172">As of July 1, 2020, the older CQD accesses data from the latest CQD.</span></span> <span data-ttu-id="be20a-173">较旧的 CQD 数据不再可用，并且您不能导出您的建筑物或报表数据。</span><span class="sxs-lookup"><span data-stu-id="be20a-173">The older CQD data is no longer available, and you can't export your building or report data.</span></span>

<span data-ttu-id="be20a-174">在 "聚合" 或 "摘要" 级别上，您可能会看到您的旧的和较新的 CQD 报表之间有更多数据差异</span><span class="sxs-lookup"><span data-stu-id="be20a-174">You’ll likely see more data differences between your older and newer CQD reports at the aggregated or summary level.</span></span> <span data-ttu-id="be20a-175">如果比较粒度级别的数据，将获得 "横向到横向" 比较。</span><span class="sxs-lookup"><span data-stu-id="be20a-175">If you compare data at a more granular level, you’ll get an “apples-to-apples” comparison.</span></span> <span data-ttu-id="be20a-176">例如，如果你要查看单个建筑物的数据，则较旧的 CQD 报表的质量不佳的百分比应该是相同的。</span><span class="sxs-lookup"><span data-stu-id="be20a-176">For example, if you’re looking at data for an individual building, the Percentage of Poor Quality should be the same between both the older and new CQD reports.</span></span>

- <span data-ttu-id="be20a-177">选择具有紧密焦点的方案，如企业有线连接、Windows 桌面或单个区域或建筑物。</span><span class="sxs-lookup"><span data-stu-id="be20a-177">Pick a scenario with a tight focus, such as corporate wired connections, Windows Desktops, or a single region or building.</span></span>
- <span data-ttu-id="be20a-178">检查团队 MR、TR 或 MP IP 范围。</span><span class="sxs-lookup"><span data-stu-id="be20a-178">Check the Teams MR, TR, or MP IP ranges.</span></span> <span data-ttu-id="be20a-179">团队范围比 Skype for business Online 更新，这可能会导致与防火墙的连接问题。</span><span class="sxs-lookup"><span data-stu-id="be20a-179">The Teams ranges are newer than Skype for Business Online, and that can cause connectivity issues involving firewalls.</span></span>
- <span data-ttu-id="be20a-180">不要比较汇总或顶级数字。</span><span class="sxs-lookup"><span data-stu-id="be20a-180">Don't compare summary or top-level numbers.</span></span> <span data-ttu-id="be20a-181">这些比较将使你能够将企业有线连接上的 Skype for business Online 通话的大型通话量与 LTE 或专用网络上的一小大量团队通话进行比较。</span><span class="sxs-lookup"><span data-stu-id="be20a-181">These comparisons will lead you to compare a large call volume of Skype for Business Online calls on a corporate wired connection to a small volume of Teams calls on an LTE or private network.</span></span>
- <span data-ttu-id="be20a-182">注意位置偏向和人口差异：有许多比较过于不同的比较非常有用：</span><span class="sxs-lookup"><span data-stu-id="be20a-182">Beware of location bias and population differences: There are many comparisons that are too dissimilar to be useful:</span></span>
  - <span data-ttu-id="be20a-183">NOAM： APAC</span><span class="sxs-lookup"><span data-stu-id="be20a-183">NOAM : APAC</span></span>
  - <span data-ttu-id="be20a-184">纽约州： Goa</span><span class="sxs-lookup"><span data-stu-id="be20a-184">NY : Goa</span></span>
  - <span data-ttu-id="be20a-185">有线 : wifi</span><span class="sxs-lookup"><span data-stu-id="be20a-185">Wired : wifi</span></span>
  - <span data-ttu-id="be20a-186">公司网络：家庭网络</span><span class="sxs-lookup"><span data-stu-id="be20a-186">Corporate network : home network</span></span>
  
### <a name="why-cant-i-see-euii-in-cqd"></a><span data-ttu-id="be20a-187">为什么我在 CQD 中看不到 EUII？</span><span class="sxs-lookup"><span data-stu-id="be20a-187">Why can't I see EUII in CQD?</span></span>

<span data-ttu-id="be20a-188">这些管理员角色可以访问 CQD，但不能查看 EUII （最终用户身份信息）：</span><span class="sxs-lookup"><span data-stu-id="be20a-188">These admin roles can access CQD, but they can't view EUII (end-user identifiable information):</span></span>
- <span data-ttu-id="be20a-189">Microsoft 365 报表读者</span><span class="sxs-lookup"><span data-stu-id="be20a-189">Microsoft 365 Reports Reader</span></span>
- <span data-ttu-id="be20a-190">团队沟通支持专家</span><span class="sxs-lookup"><span data-stu-id="be20a-190">Teams Communications Support Specialist</span></span>

<span data-ttu-id="be20a-191">若要了解有关可访问 CQD 的角色的详细信息-包括 EUII-读取[分配角色以访问 CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)。</span><span class="sxs-lookup"><span data-stu-id="be20a-191">To learn more about roles that can access CQD - including EUII - read [Assign roles for accessing CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).</span></span>

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a><span data-ttu-id="be20a-192">为什么我仅当我筛选了团队时，我在 CQD 中看到 Skype for Business 信息？</span><span class="sxs-lookup"><span data-stu-id="be20a-192">Why am I seeing Skype for Business information in CQD when I've filtered for Teams only?</span></span>

<span data-ttu-id="be20a-193">当仅在 CQD 报表（isTeams = 1）中筛选团队时，将筛选*第一个终结点*为团队的所有调用。</span><span class="sxs-lookup"><span data-stu-id="be20a-193">When you filter for Teams only in CQD reports (isTeams = 1), you're filtering for all calls where the *first endpoint* is Teams.</span></span> <span data-ttu-id="be20a-194">如果*第二个终结点*是 Skype for business，则该信息将显示在您的 CQD 报告中。</span><span class="sxs-lookup"><span data-stu-id="be20a-194">If the *second endpoint* is Skype for Business, that information will show up in your CQD report.</span></span>

<span data-ttu-id="be20a-195">CQDv2 和 CQDv3 将始终具有不同的总数，因为 CQDv3 将具有 CQDv2 没有的新方案。</span><span class="sxs-lookup"><span data-stu-id="be20a-195">CQDv2 and CQDv3 will always have different total counts since CQDv3 will have new scenarios that CQDv2 will not have.</span></span> <span data-ttu-id="be20a-196">这就是比较 "摘要总数" 或 "不带筛选器的聚合的所有数字" 的原因将具有这些预期的差异。</span><span class="sxs-lookup"><span data-stu-id="be20a-196">That’s why comparing Summary Total or Aggregated all-up numbers with no filters will have these expected differences.</span></span>  

<span data-ttu-id="be20a-197">根据客户的情形，CQDv3 将包括 SFB 2019 本地呼叫（如果 SFB 2019 与数据连接器一起使用）、Skype 机器人呼叫（AA、CVI、VDI）、实时事件和 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="be20a-197">Depending on Customers’ scenario, CQDv3 will include SFB 2019 on-premises calls (if SFB 2019 is used with a data connector), Skype Bot calls (AA, CVI, VDI), Live Events and PSTN calls.</span></span> <span data-ttu-id="be20a-198">适用于客户的方案/功能，但其数据不在 CQD V2 中。</span><span class="sxs-lookup"><span data-stu-id="be20a-198">Scenarios/Features which are available for the customers, but their data are not in CQD V2.</span></span>

<span data-ttu-id="be20a-199">例如，预计你的客户和你将看到200000音频流，并且 CQD V2 摘要报告中出现5000故障。300000音频流与5500故障的对比2019（来自 CQD V3 中的本地呼叫、CVI 呼叫、PSTN 呼叫等）。</span><span class="sxs-lookup"><span data-stu-id="be20a-199">For instance, it is expected that your customers and you will see 200,000 audio streams, with 5000 failures in CQD V2 Summary Report; versus 300,000 audio streams with 5500 failures (coming from 2019 on-prem calls, CVI calls, PSTN calls etc) in CQD V3.</span></span>

<span data-ttu-id="be20a-200">为了确定是否存在任何意外的差异，您必须查看整个数据的各种细目。</span><span class="sxs-lookup"><span data-stu-id="be20a-200">In order to determine, if there are any unexpected differences, you must look at various breakdowns of the overall data.</span></span>  <span data-ttu-id="be20a-201">与意向进行比较。</span><span class="sxs-lookup"><span data-stu-id="be20a-201">Compare with intent.</span></span>  <span data-ttu-id="be20a-202">按用户代理类别对数据进行切片是我们建议的第一项。</span><span class="sxs-lookup"><span data-stu-id="be20a-202">Slicing the data by User Agent Category Pair is one of the first things we recommend.</span></span>  <span data-ttu-id="be20a-203">*第一种产品*和*第二种产品*也是良好的切片器。</span><span class="sxs-lookup"><span data-stu-id="be20a-203">*First Product* and *Second Product* are also good slicers.</span></span>  


## <a name="related-topics"></a><span data-ttu-id="be20a-204">相关主题</span><span class="sxs-lookup"><span data-stu-id="be20a-204">Related topics</span></span>

[<span data-ttu-id="be20a-205">改善和监控团队的通话质量</span><span class="sxs-lookup"><span data-stu-id="be20a-205">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="be20a-206">什么是 CQD？</span><span class="sxs-lookup"><span data-stu-id="be20a-206">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="be20a-207">设置通话质量仪表板（CQD）</span><span class="sxs-lookup"><span data-stu-id="be20a-207">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="be20a-208">上载租户和生成数据</span><span class="sxs-lookup"><span data-stu-id="be20a-208">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="be20a-209">CQD 数据和报告</span><span class="sxs-lookup"><span data-stu-id="be20a-209">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="be20a-210">使用 CQD 管理通话和会议质量</span><span class="sxs-lookup"><span data-stu-id="be20a-210">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="be20a-211">CQD 中可用的维度和度量值</span><span class="sxs-lookup"><span data-stu-id="be20a-211">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="be20a-212">CQD 中的流分类</span><span class="sxs-lookup"><span data-stu-id="be20a-212">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="be20a-213">使用 Power BI 分析 CQD 数据</span><span class="sxs-lookup"><span data-stu-id="be20a-213">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)

[<span data-ttu-id="be20a-214">Teams 疑难解答</span><span class="sxs-lookup"><span data-stu-id="be20a-214">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)