---
title: '呼叫质量仪表板 (CQD) 常见问题解答 (常见问题) '
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
description: 阅读常见问题解答 (常见问题) 和有关 CQD Microsoft Teams呼叫质量 (的) 。
ms.openlocfilehash: ad718df893b69b333dd63d224663238879fda8c7
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2021
ms.locfileid: "52718003"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a><span data-ttu-id="35a08-103">呼叫质量仪表板 (CQD) 常见问题解答 (常见问题) </span><span class="sxs-lookup"><span data-stu-id="35a08-103">Call Quality Dashboard (CQD) Frequently asked questions (FAQ)</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="35a08-104">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="35a08-104">Frequently asked questions</span></span>

[<span data-ttu-id="35a08-105">如果一个或多个会议参与者体验不佳，CQD 为何将通话标记为"良好"？</span><span class="sxs-lookup"><span data-stu-id="35a08-105">Why does CQD mark a call as "Good" if one or more meeting participants had a poor experience?</span></span>](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[<span data-ttu-id="35a08-106">为什么在度量值上，调用和用户计数值的差异最大为 0.2%，如何获取最准确的音量？ </span><span class="sxs-lookup"><span data-stu-id="35a08-106">Why do I see up to 0.2% difference in call and user count values on measures and how to get most accurate volumes? </span></span>](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[<span data-ttu-id="35a08-107">为什么来自 Skype for Business 的 CQD 数据与来自 Teams 的 CQD 数据？</span><span class="sxs-lookup"><span data-stu-id="35a08-107">Why is CQD data from Skype for Business different than CQD data from Teams? </span></span>](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[<span data-ttu-id="35a08-108">为什么我在 CQD 中看不到 EUII？</span><span class="sxs-lookup"><span data-stu-id="35a08-108">Why can't I see EUII in CQD?</span></span>](#why-cant-i-see-euii-in-cqd)

[<span data-ttu-id="35a08-109">为什么在仅Skype for Business筛选后，CQD 中Teams信息？</span><span class="sxs-lookup"><span data-stu-id="35a08-109">Why am I seeing Skype for Business information in CQD when I've filtered for Teams only?</span></span>](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[<span data-ttu-id="35a08-110">为什么我的自定义报表最多只返回 10，000 行，当我知道应该有更多的条目时？</span><span class="sxs-lookup"><span data-stu-id="35a08-110">Why do my custom reports only return a maximum of 10,000 rows when I know there should be more entries?</span></span>](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

[<span data-ttu-id="35a08-111">为什么 WiFi VPN 连接显示为"有线"而不是"WiFi"？</span><span class="sxs-lookup"><span data-stu-id="35a08-111">Why do WiFi VPN connections show as Wired instead of WiFi?</span></span>](#why-do-wifi-vpn-connections-show-as-wired-instead-of-wifi)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a><span data-ttu-id="35a08-112">如果一个或多个会议参与者体验不佳，CQD 为何将通话标记为"良好"？</span><span class="sxs-lookup"><span data-stu-id="35a08-112">Why does CQD mark a call as "Good" if one or more meeting participants had a poor experience?</span></span>

<span data-ttu-id="35a08-113">查看 CQD 用于流分类 [的规则](stream-classification-in-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="35a08-113">Check out the rules CQD uses for [stream classification](stream-classification-in-call-quality-dashboard.md).</span></span>
 
<span data-ttu-id="35a08-114">对于音频流，根据调用长度计算平均值的五个分类器中的任意一个都可能是"良好"参数。</span><span class="sxs-lookup"><span data-stu-id="35a08-114">For audio streams, any of the five classifiers, which are calculated for the average based on the length of the call, could all be within "good" parameters.</span></span> <span data-ttu-id="35a08-115">这并不意味着用户未遇到导致音频掉线、静态或故障的问题。</span><span class="sxs-lookup"><span data-stu-id="35a08-115">It doesn't mean the users didn't experience something that contributed to an audio drop out, static, or glitch.</span></span> 

<span data-ttu-id="35a08-116">若要确定它是网络问题，请看会话的平均值与最大值之间的增量。</span><span class="sxs-lookup"><span data-stu-id="35a08-116">To determine if it was a network problem, look at the delta between the average values for the session and the max values.</span></span> <span data-ttu-id="35a08-117">最大值是会话期间检测到并报告的最大值。</span><span class="sxs-lookup"><span data-stu-id="35a08-117">Max values are the maximum detected and reported during the session.</span></span>
 
<span data-ttu-id="35a08-118">下面是如何排查这种情况的示例。</span><span class="sxs-lookup"><span data-stu-id="35a08-118">Here's an example of how to troubleshoot this situation.</span></span> <span data-ttu-id="35a08-119">假设你在调用期间进行网络跟踪，并且前 20 分钟没有丢失数据包，但随后你有 1.5 秒数据包的间隙，然后适合通话的其余部分。</span><span class="sxs-lookup"><span data-stu-id="35a08-119">Let's say you take a network trace during a call and the first 20 minutes there are no lost packets but then you have a gap of 1.5 seconds of packets and then good for the remainder of the call.</span></span> <span data-ttu-id="35a08-120">即使在 Wireshark 跟踪 RTP 分析 (，平均丢包率<10%) 0.1。</span><span class="sxs-lookup"><span data-stu-id="35a08-120">The average is going to be <10% (0.1) Packet loss even in a Wireshark trace RTP analysis.</span></span> <span data-ttu-id="35a08-121">最大数据包丢失是什么？</span><span class="sxs-lookup"><span data-stu-id="35a08-121">What was the Max Packet Loss?</span></span> <span data-ttu-id="35a08-122">5 秒的 1.5 秒为 0.3 (30%) 。</span><span class="sxs-lookup"><span data-stu-id="35a08-122">1.5 Seconds in a 5-second period would be 30% (0.3).</span></span> <span data-ttu-id="35a08-123">这是在 5 秒采样期内发生的 (，还是可以在采样期间拆分) ？</span><span class="sxs-lookup"><span data-stu-id="35a08-123">Did that occur within the 5-second sampling period (maybe or it could be split over the sampling period)?</span></span>
 
<span data-ttu-id="35a08-124">如果网络指标在平均值和最大值中看起来不错，则查看其他遥测数据：</span><span class="sxs-lookup"><span data-stu-id="35a08-124">If network metrics look good in the averages and max values, then look to other telemetry data:</span></span> 
- <span data-ttu-id="35a08-125">检查"CPU 不足事件比率"，查看检测到的可用 CPU 资源是否不足，导致质量差。</span><span class="sxs-lookup"><span data-stu-id="35a08-125">Check CPU Insufficient Event Ratio to see if the detected CPU resources available were insufficient and caused poor quality.</span></span> 
- <span data-ttu-id="35a08-126">音频设备是否由于麦克风接近扬声器而以半双工模式阻止反馈？</span><span class="sxs-lookup"><span data-stu-id="35a08-126">Was the audio device in Half Duplex mode to prevent feedback due to microphones that are to close to speakers?</span></span> 
- <span data-ttu-id="35a08-127">检查设备半双工 AEC 事件比率。</span><span class="sxs-lookup"><span data-stu-id="35a08-127">Check the Device Half Duplex AEC Event Ratio.</span></span> <span data-ttu-id="35a08-128">插入集线器或扩展坞时，设备故障或麦克风故障是否由于 USB 音频输出而引入噪音或静态？</span><span class="sxs-lookup"><span data-stu-id="35a08-128">Was the device glitching or the microphone glitching introducing noise or static due to USB Audio Drop outs when plugged into a Hub or Docking Station?</span></span>  
- <span data-ttu-id="35a08-129">检查"设备故障"和"麦克风故障"事件比率。</span><span class="sxs-lookup"><span data-stu-id="35a08-129">Check the Device Glitches and Microphone glitches event ratios.</span></span> <span data-ttu-id="35a08-130">设备本身是否正常运行？</span><span class="sxs-lookup"><span data-stu-id="35a08-130">Was the device itself functioning properly?</span></span>  
- <span data-ttu-id="35a08-131">检查捕获和呈现设备无法正常工作的事件比率。</span><span class="sxs-lookup"><span data-stu-id="35a08-131">Check the Capture and Render Device Not Functioning Event Ratios.</span></span>


<span data-ttu-id="35a08-132">有关 CQD 遥测中可用的维度和度量的更多内容，请阅读呼叫质量仪表板中提供的维度 [和度量](dimensions-and-measures-available-in-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="35a08-132">For more on dimensions and measures available in CQD telemetry, read [Dimensions and measurements available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>

<span data-ttu-id="35a08-133">对于背景噪音，请检查静音事件比率以查看参与者静音的时间长度。</span><span class="sxs-lookup"><span data-stu-id="35a08-133">For background noise, check mute event ratio to see the length of time participants were muted.</span></span>
 
<span data-ttu-id="35a08-134">在 CQD 中创建详细报表，并筛选会议 ID，查看会议中的所有用户和流，并添加您感兴趣的字段。</span><span class="sxs-lookup"><span data-stu-id="35a08-134">Create detailed reports in CQD and filter on Meeting ID to look at all users and streams in a meeting and add the fields you are interested in.</span></span> <span data-ttu-id="35a08-135">报告该问题的用户可能不是遇到该问题的用户。</span><span class="sxs-lookup"><span data-stu-id="35a08-135">A user reporting the issue may not be the one that was having the issue.</span></span> <span data-ttu-id="35a08-136">他们只是报告体验。</span><span class="sxs-lookup"><span data-stu-id="35a08-136">They are just reporting the experience.</span></span>
 
<span data-ttu-id="35a08-137">遥测数据不一定会指出问题，但可以帮助你更好地了解在何处查找和通知你的决策。</span><span class="sxs-lookup"><span data-stu-id="35a08-137">The telemetry will not necessarily call out the issue, but it can help you better understand where to look and inform your decisions.</span></span> <span data-ttu-id="35a08-138">是网络、设备、驱动程序或固件更新、使用情况还是用户？</span><span class="sxs-lookup"><span data-stu-id="35a08-138">Is it network, device, driver or firmware updates, usage, or user?</span></span>

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a><span data-ttu-id="35a08-139">为什么在度量值上，调用和用户计数值的差异最大为 0.2%，如何获取最准确的音量？</span><span class="sxs-lookup"><span data-stu-id="35a08-139">Why do I see up to 0.2% difference in call and user count values on measures and how to get most accurate volumes?</span></span> 
<span data-ttu-id="35a08-140">若要计算调用计数和用户计数度量值，请对数据集中的调用或用户标识符执行不同的 countif 操作。</span><span class="sxs-lookup"><span data-stu-id="35a08-140">To compute call count and user count measures, a distinct countif operation is performed against the call or user identifiers in the data set.</span></span> <span data-ttu-id="35a08-141">在大型数据集上，非重复 countif 操作本身存在最多 0.2% 的错误。</span><span class="sxs-lookup"><span data-stu-id="35a08-141">On large data sets, there is an up to 0.2% error inherent with the distinct countif operation.</span></span> <span data-ttu-id="35a08-142">对于最准确的卷，应依赖于流计数度量值，因为它们不依赖于此不同的 countif 操作。</span><span class="sxs-lookup"><span data-stu-id="35a08-142">For the most accurate volume, you should rely on stream count measures since they do not rely on this distinct countif operation.</span></span> <span data-ttu-id="35a08-143">减少数据量的筛选可以减少错误，但可能无法消除不同调用和用户计数中的此错误源。</span><span class="sxs-lookup"><span data-stu-id="35a08-143">Filtering to reduce the data volume may reduce the error but may not eliminate this source of error in distinct call and user counts.</span></span> <span data-ttu-id="35a08-144">请参阅 [呼叫质量仪表板](dimensions-and-measures-available-in-call-quality-dashboard.md) 中提供的维度和度量，这些度量值会受到影响。</span><span class="sxs-lookup"><span data-stu-id="35a08-144">Refer to [Dimensions and measurements available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md) for which measures are impacted.</span></span>


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a><span data-ttu-id="35a08-145">为什么来自 Skype for Business 的 CQD 数据与来自 Teams 的 CQD 数据？</span><span class="sxs-lookup"><span data-stu-id="35a08-145">Why is CQD data from Skype for Business different than CQD data from Teams?</span></span> 


> [!IMPORTANT]
> <span data-ttu-id="35a08-146">从 2020 年 7 月 1 日开始，较旧的 CQD (CQD.lync.com) 使用来自最新 CQD (CQD 的数据。Teams.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="35a08-146">As of July 1, 2020, the older CQD (CQD.lync.com) uses data from the latest CQD (CQD.Teams.microsoft.com).</span></span> <span data-ttu-id="35a08-147">旧 CQD 数据不再可用，并且无法导出建筑物或报表数据。</span><span class="sxs-lookup"><span data-stu-id="35a08-147">The older CQD data is no longer available, and you can't export your building or report data.</span></span> <span data-ttu-id="35a08-148">你仍然可以使用 CQD.lync.com (管理中心Skype for Business的) ，但我们将很快关闭对 CQD.lync.com 的访问权限，因此应移动到 CQD。Teams.microsoft.com，如果尚未这样做。</span><span class="sxs-lookup"><span data-stu-id="35a08-148">You can still use CQD.lync.com (available from the Skype for Business admin center), but we'll turn off access to CQD.lync.com soon, so you should move to CQD.Teams.microsoft.com if you haven't already done so.</span></span>


<span data-ttu-id="35a08-149">如果尝试比较 Skype for Business 旧门户 (cqd.lync.com) 中较旧的 CQD 与 Teams 管理中心 (cqd.teams.microsoft.com) 的最新 CQD 之间的数据，则很快就会注意到数据不匹配。</span><span class="sxs-lookup"><span data-stu-id="35a08-149">If you're trying to compare data between the older CQD from the Skype for Business legacy portal (cqd.lync.com) and the latest CQD from the Teams admin center (cqd.teams.microsoft.com), you'll quickly notice that the data doesn't match.</span></span> <span data-ttu-id="35a08-150">这是因为最新的 CQD 报告有关许多其他调用方案。</span><span class="sxs-lookup"><span data-stu-id="35a08-150">That's because the latest CQD reports on many additional calling scenarios.</span></span> <span data-ttu-id="35a08-151">如果仍在使用来自较旧 CQD 的报告，请使用本文来帮助解释这些报告：呼叫质量仪表板[Skype for Business Server。](/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard)</span><span class="sxs-lookup"><span data-stu-id="35a08-151">If you're still using reports from the older CQD, use this article to help you interpret those reports: [Call Quality Dashboard for Skype for Business Server](/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard).</span></span>


  
### <a name="why-cant-i-see-euii-in-cqd"></a><span data-ttu-id="35a08-152">为什么我在 CQD 中看不到 EUII？</span><span class="sxs-lookup"><span data-stu-id="35a08-152">Why can't I see EUII in CQD?</span></span>

<span data-ttu-id="35a08-153">这些管理员角色可以访问 CQD，但无法查看 EUII (最终用户可识别信息) ：</span><span class="sxs-lookup"><span data-stu-id="35a08-153">These admin roles can access CQD, but they can't view EUII (end-user identifiable information):</span></span>
- <span data-ttu-id="35a08-154">Microsoft 365报表读者</span><span class="sxs-lookup"><span data-stu-id="35a08-154">Microsoft 365 Reports Reader</span></span>
- <span data-ttu-id="35a08-155">Teams通信支持专家</span><span class="sxs-lookup"><span data-stu-id="35a08-155">Teams Communications Support Specialist</span></span>

<span data-ttu-id="35a08-156">若要详细了解可以访问 CQD 的角色（包括 EUII），请阅读 [分配用于访问 CQD 的角色](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)。</span><span class="sxs-lookup"><span data-stu-id="35a08-156">To learn more about roles that can access CQD - including EUII - read [Assign roles for accessing CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).</span></span>

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a><span data-ttu-id="35a08-157">为什么在仅Skype for Business筛选后，CQD 中Teams信息？</span><span class="sxs-lookup"><span data-stu-id="35a08-157">Why am I seeing Skype for Business information in CQD when I've filtered for Teams only?</span></span>

<span data-ttu-id="35a08-158">仅在 Teams isTeams = 1 (的 CQD 报告中筛选) 筛选第一终结点为第一终结点的所有Teams。 </span><span class="sxs-lookup"><span data-stu-id="35a08-158">When you filter for Teams only in CQD reports (isTeams = 1), you're filtering for all calls where the *first endpoint* is Teams.</span></span> <span data-ttu-id="35a08-159">如果 *第二终结点* Skype for Business，该信息会显示在 CQD 报告中。</span><span class="sxs-lookup"><span data-stu-id="35a08-159">If the *second endpoint* is Skype for Business, that information will show up in your CQD report.</span></span>

<span data-ttu-id="35a08-160">CQDv2 和 CQDv3 始终具有不同的总计计数，因为 CQDv3 将具有 CQDv2 不会具有的新方案。</span><span class="sxs-lookup"><span data-stu-id="35a08-160">CQDv2 and CQDv3 will always have different total counts since CQDv3 will have new scenarios that CQDv2 will not have.</span></span> <span data-ttu-id="35a08-161">正因如此，比较"汇总总计"或"聚合全部数字"（没有筛选器）将具有这些预期差异的原因。</span><span class="sxs-lookup"><span data-stu-id="35a08-161">That’s why comparing Summary Total or Aggregated all-up numbers with no filters will have these expected differences.</span></span>  

<span data-ttu-id="35a08-162">如果 SFB 2019 与数据连接器) 一起使用，则 CQDv3 将包括 SFB 2019 本地呼叫 (、Skype 机器人呼叫 (AA、CVI、VDI) 、实时事件和 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="35a08-162">Depending on Customers’ scenario, CQDv3 will include SFB 2019 on-premises calls (if SFB 2019 is used with a data connector), Skype Bot calls (AA, CVI, VDI), Live Events and PSTN calls.</span></span> <span data-ttu-id="35a08-163">客户可用的方案/功能，但其数据不在 CQD V2 中。</span><span class="sxs-lookup"><span data-stu-id="35a08-163">Scenarios/Features which are available for the customers, but their data are not in CQD V2.</span></span>

<span data-ttu-id="35a08-164">例如，预期客户和你将看到 200，000 个音频流，CQD V2 摘要报告中有 5000 个失败;与 300，000 个音频流相比，5500 次失败 (来自 CQD V3 中的 2019 个就地呼叫、CVI 呼叫、PSTN 呼叫等 ) 。</span><span class="sxs-lookup"><span data-stu-id="35a08-164">For instance, it is expected that your customers and you will see 200,000 audio streams, with 5000 failures in CQD V2 Summary Report; versus 300,000 audio streams with 5500 failures (coming from 2019 on-prem calls, CVI calls, PSTN calls, etc.) in CQD V3.</span></span>

<span data-ttu-id="35a08-165">若要确定如果存在任何意外的差异，则必须查看总体数据的各种细分。</span><span class="sxs-lookup"><span data-stu-id="35a08-165">In order to determine, if there are any unexpected differences, you must look at various breakdowns of the overall data.</span></span>  <span data-ttu-id="35a08-166">与意向进行比较。</span><span class="sxs-lookup"><span data-stu-id="35a08-166">Compare with intent.</span></span>  <span data-ttu-id="35a08-167">按用户代理类别对切片数据是建议的第一项操作之一。</span><span class="sxs-lookup"><span data-stu-id="35a08-167">Slicing the data by User Agent Category Pair is one of the first things we recommend.</span></span>  <span data-ttu-id="35a08-168">*第一* 个 *产品和第二* 个产品也是很好的切片器。</span><span class="sxs-lookup"><span data-stu-id="35a08-168">*First Product* and *Second Product* are also good slicers.</span></span>  

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a><span data-ttu-id="35a08-169">为什么我的自定义报表最多只返回 10，000 行，当我知道应该有更多的条目时？</span><span class="sxs-lookup"><span data-stu-id="35a08-169">Why do my custom reports only return a maximum of 10,000 rows when I know there should be more entries?</span></span>

<span data-ttu-id="35a08-170">CQD 设计用于汇总数据查询，不用于数据导出。</span><span class="sxs-lookup"><span data-stu-id="35a08-170">CQD is designed for summarized data queries, and is not designed for data export.</span></span> <span data-ttu-id="35a08-171">我们建议尽可能重建报表，以防止超过 10，000 行的限制。</span><span class="sxs-lookup"><span data-stu-id="35a08-171">We recommend restructuring your reports, where possible, to prevent the 10,000 row limit from being exceeded.</span></span> <span data-ttu-id="35a08-172">首先，使用更大、基数较低的维度（如月、年、日期、区域、国家/地区等）查看 KPI。从该维度中，可以向下钻取到基数越高的维度。</span><span class="sxs-lookup"><span data-stu-id="35a08-172">Start by looking at your KPIs using broader, lower-cardinality dimensions, such as Month, Year, Date, Region, Country, etc. From there, you can drill down into increasingly higher-cardinality dimensions.</span></span> <span data-ttu-id="35a08-173">支持人员报表Location-Enhanced报表都提供了此向下钻取工作流的良好示例。</span><span class="sxs-lookup"><span data-stu-id="35a08-173">The Helpdesk and Location-Enhanced Reports both provide good examples of this drill down workflow.</span></span>

### <a name="why-do-wifi-vpn-connections-show-as-wired-instead-of-wifi"></a><span data-ttu-id="35a08-174">为什么 WiFi VPN 连接显示为"有线"而不是"WiFi"？</span><span class="sxs-lookup"><span data-stu-id="35a08-174">Why do WiFi VPN connections show as Wired instead of WiFi?</span></span>

<span data-ttu-id="35a08-175">这是正常情况。</span><span class="sxs-lookup"><span data-stu-id="35a08-175">This is expected.</span></span> <span data-ttu-id="35a08-176">VPN 供应商创建了一个虚拟以太网适配器，该适配器被视为有线连接。</span><span class="sxs-lookup"><span data-stu-id="35a08-176">The VPN vendor created a virtual ethernet adapter which is treated like a wired connection.</span></span> <span data-ttu-id="35a08-177">由于未正确标记，操作系统不知道它是 WiFi 连接，并报告为有线连接。</span><span class="sxs-lookup"><span data-stu-id="35a08-177">Since it's not properly labeled, the operating system doesn't know it's a WiFi connection and reports it as wired.</span></span>

## <a name="related-topics"></a><span data-ttu-id="35a08-178">相关主题</span><span class="sxs-lookup"><span data-stu-id="35a08-178">Related topics</span></span>

[<span data-ttu-id="35a08-179">改进和监视呼叫质量Teams</span><span class="sxs-lookup"><span data-stu-id="35a08-179">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="35a08-180">什么是 CQD？</span><span class="sxs-lookup"><span data-stu-id="35a08-180">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="35a08-181">使用 CQD (设置呼叫质量) </span><span class="sxs-lookup"><span data-stu-id="35a08-181">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="35a08-182">Upload租户和建筑物数据</span><span class="sxs-lookup"><span data-stu-id="35a08-182">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="35a08-183">CQD 数据和报表</span><span class="sxs-lookup"><span data-stu-id="35a08-183">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="35a08-184">使用 CQD 管理呼叫和会议质量</span><span class="sxs-lookup"><span data-stu-id="35a08-184">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="35a08-185">CQD 中可用的维度和度量值</span><span class="sxs-lookup"><span data-stu-id="35a08-185">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="35a08-186">CQD 中的流分类</span><span class="sxs-lookup"><span data-stu-id="35a08-186">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="35a08-187">使用Power BI分析 CQD 数据</span><span class="sxs-lookup"><span data-stu-id="35a08-187">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)

[<span data-ttu-id="35a08-188">Teams 疑难解答</span><span class="sxs-lookup"><span data-stu-id="35a08-188">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
