---
title: 为业务 Server Skype 中呼叫列表报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
description: 摘要： 了解用于在 Skype 业务服务器的呼叫列表报告。
ms.openlocfilehash: 3e9b115edc92c911029570c6b69d589db64533af
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902760"
---
# <a name="call-list-report-in-skype-for-business-server"></a><span data-ttu-id="03b88-103">为业务 Server Skype 中呼叫列表报告</span><span class="sxs-lookup"><span data-stu-id="03b88-103">Call List Report in Skype for Business Server</span></span>
 
<span data-ttu-id="03b88-104">**摘要：** 了解有关呼叫列表报告中 Skype 用于业务服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="03b88-104">**Summary:** Learn about the Call List Report used in Skype for Business Server.</span></span>
  
<span data-ttu-id="03b88-105">呼叫列表报告提供了针对您组织中发出和接收的单个呼叫的用户体验质量 (QoE) 指标。</span><span class="sxs-lookup"><span data-stu-id="03b88-105">The Call List Report provides Quality of Experience (QoE) metrics for individual calls made and received in your organization.</span></span> <span data-ttu-id="03b88-106">请注意，报告的实际指标将取决于您访问呼叫列表报告的方式。</span><span class="sxs-lookup"><span data-stu-id="03b88-106">Note that the actual metrics reported will depend on how you access the Call List report.</span></span> <span data-ttu-id="03b88-107">例如，如果从[设备报告中的业务服务器 Skype](device-report.md)打开报告，您将看到以下内容，Device Report 也会报告的指标等指标：</span><span class="sxs-lookup"><span data-stu-id="03b88-107">For example, if you open the report from the [Device Report in Skype for Business Server](device-report.md), you'll see metrics such as the following, metrics that are also reported on the Device Report:</span></span>
  
- <span data-ttu-id="03b88-108">呼叫者的麦克风</span><span class="sxs-lookup"><span data-stu-id="03b88-108">Caller's microphone</span></span>
    
- <span data-ttu-id="03b88-109">呼叫者的扬声器</span><span class="sxs-lookup"><span data-stu-id="03b88-109">Caller's speaker</span></span>
    
- <span data-ttu-id="03b88-110">被叫方的麦克风</span><span class="sxs-lookup"><span data-stu-id="03b88-110">Callee's microphone</span></span>
    
- <span data-ttu-id="03b88-111">被叫方的扬声器</span><span class="sxs-lookup"><span data-stu-id="03b88-111">Callee's speaker</span></span>
    
- <span data-ttu-id="03b88-112">语音切换时间比率</span><span class="sxs-lookup"><span data-stu-id="03b88-112">Ratio of voice switch time</span></span> 
    
<span data-ttu-id="03b88-113">但是，如果您从[Location Report 中的业务服务器 Skype](location-report.md)打开呼叫列表报告，您将看任何这些指标;相反，您将看到指标类似于：</span><span class="sxs-lookup"><span data-stu-id="03b88-113">However, if you open the Call List Report from the [Location Report in Skype for Business Server](location-report.md), you won't see any of those metrics; instead, you'll see metrics like these:</span></span>
  
- <span data-ttu-id="03b88-114">来回行程（毫秒）</span><span class="sxs-lookup"><span data-stu-id="03b88-114">Round trip (ms)</span></span>
    
- <span data-ttu-id="03b88-115">性能降低 (MOS)</span><span class="sxs-lookup"><span data-stu-id="03b88-115">Degradation (MOS)</span></span>
    
- <span data-ttu-id="03b88-116">数据包丢失</span><span class="sxs-lookup"><span data-stu-id="03b88-116">Packet loss</span></span>
    
- <span data-ttu-id="03b88-117">抖动（毫秒）</span><span class="sxs-lookup"><span data-stu-id="03b88-117">Jitter (ms)</span></span>
    
<span data-ttu-id="03b88-p102">这些是在位置报告上报告的指标。但是，您始终能够从呼叫列表报告中单击“详细信息”指标来提供任何呼叫的完整 QoE 信息。</span><span class="sxs-lookup"><span data-stu-id="03b88-p102">Those are the metrics reported on the Location Report. However, from the Call List Report you can always click the Detail metric to provide complete QoE information for any call.</span></span>
  
## <a name="accessing-the-call-list-report"></a><span data-ttu-id="03b88-120">访问呼叫列表报告</span><span class="sxs-lookup"><span data-stu-id="03b88-120">Accessing the Call List Report</span></span>

<span data-ttu-id="03b88-121">可从以下任一报告访问呼叫列表报告：</span><span class="sxs-lookup"><span data-stu-id="03b88-121">The Call List Report can be accessed from any of the following reports:</span></span>
  
- <span data-ttu-id="03b88-122">[Skype 业务服务器中的 Location Report](location-report.md) （通过单击呼叫量或质量欠佳的呼叫百分比指标）</span><span class="sxs-lookup"><span data-stu-id="03b88-122">The [Location Report in Skype for Business Server](location-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>
    
- <span data-ttu-id="03b88-123">[Skype 业务服务器中的 Device Report](device-report.md) （通过单击呼叫量或质量欠佳的呼叫百分比指标）</span><span class="sxs-lookup"><span data-stu-id="03b88-123">The [Device Report in Skype for Business Server](device-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>
    
- <span data-ttu-id="03b88-124">[Skype 业务服务器中的 Media Quality Summary Report](summary.md) （通过单击呼叫量或质量欠佳的呼叫百分比指标）</span><span class="sxs-lookup"><span data-stu-id="03b88-124">The [Media Quality Summary Report in Skype for Business Server](summary.md) (by clicking the Call volume or Poor call percentage metric)</span></span>
    
- <span data-ttu-id="03b88-125">[Skype 业务服务器中的 Server Performance Report](server-performance.md) （通过单击呼叫量或质量欠佳的呼叫百分比指标）</span><span class="sxs-lookup"><span data-stu-id="03b88-125">The [Server Performance Report in Skype for Business Server](server-performance.md) (by clicking the Call volume or Poor call percentage metric)</span></span>
    
<span data-ttu-id="03b88-126">从呼叫列表报告中可以访问[呼叫详情报告添加 Skype 业务服务器中](call-detail-report.md)通过单击详细信息指标。</span><span class="sxs-lookup"><span data-stu-id="03b88-126">From within the Call List Report you can access the [Call Detail Report in Skype for Business Server](call-detail-report.md) by clicking the Detail metric.</span></span>
  
## <a name="making-the-best-use-of-the-call-list-report"></a><span data-ttu-id="03b88-127">最充分地利用呼叫列表报告</span><span class="sxs-lookup"><span data-stu-id="03b88-127">Making the Best Use of the Call List Report</span></span>

<span data-ttu-id="03b88-128">如果您记不住实际度量哪些呼叫列表报告指标（例如语音切换时间比率），请将鼠标指针悬停在指标标签的上方；这将显示一个工具提示，它为您简述了此指标。</span><span class="sxs-lookup"><span data-stu-id="03b88-128">If you can't remember what some of the Call List Report metrics (such as Ratio voice switch time) actually measure, hold your mouse over the metric label; a tool tip will then appear giving you a brief description of the metric.</span></span>
  
## <a name="filters"></a><span data-ttu-id="03b88-129">筛选器</span><span class="sxs-lookup"><span data-stu-id="03b88-129">Filters</span></span>

<span data-ttu-id="03b88-p103">无。您无法筛选呼叫列表报告。</span><span class="sxs-lookup"><span data-stu-id="03b88-p103">None. You cannot filter the Call List Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="03b88-132">指标</span><span class="sxs-lookup"><span data-stu-id="03b88-132">Metrics</span></span>

<span data-ttu-id="03b88-133">下表列出了呼叫列表报告中提供的有关每个呼叫的信息。</span><span class="sxs-lookup"><span data-stu-id="03b88-133">The following table lists the information provided in the Call List Report for each call.</span></span>
  
<span data-ttu-id="03b88-134">**呼叫列表报告指标**</span><span class="sxs-lookup"><span data-stu-id="03b88-134">**Call List Report Metrics**</span></span>

|<span data-ttu-id="03b88-135">**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="03b88-135">**Name**</span></span>|<span data-ttu-id="03b88-136">**是否可按此项排序？**</span><span class="sxs-lookup"><span data-stu-id="03b88-136">**Can you sort on this item?**</span></span>|<span data-ttu-id="03b88-137">**说明**</span><span class="sxs-lookup"><span data-stu-id="03b88-137">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="03b88-138">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="03b88-138">**Details**</span></span> <br/> |<span data-ttu-id="03b88-139">否</span><span class="sxs-lookup"><span data-stu-id="03b88-139">No</span></span>  <br/> |<span data-ttu-id="03b88-140">单击此项时，报告将显示有关呼叫的其他信息。</span><span class="sxs-lookup"><span data-stu-id="03b88-140">When you click this item, the report shows additional information on the call.</span></span>  <br/> |
|<span data-ttu-id="03b88-141">**呼叫者**</span><span class="sxs-lookup"><span data-stu-id="03b88-141">**Caller**</span></span> <br/> |<span data-ttu-id="03b88-142">是</span><span class="sxs-lookup"><span data-stu-id="03b88-142">Yes</span></span>  <br/> |<span data-ttu-id="03b88-143">发起呼叫的人的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="03b88-143">SIP address of the person who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="03b88-144">**被叫方**</span><span class="sxs-lookup"><span data-stu-id="03b88-144">**Callee**</span></span> <br/> |<span data-ttu-id="03b88-145">是</span><span class="sxs-lookup"><span data-stu-id="03b88-145">Yes</span></span>  <br/> |<span data-ttu-id="03b88-146">被呼叫的人的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="03b88-146">SIP address of the person who was called.</span></span>  <br/> |
|<span data-ttu-id="03b88-147">**开始时间**</span><span class="sxs-lookup"><span data-stu-id="03b88-147">**Start time**</span></span> <br/> |<span data-ttu-id="03b88-148">是</span><span class="sxs-lookup"><span data-stu-id="03b88-148">Yes</span></span>  <br/> |<span data-ttu-id="03b88-149">呼叫开始的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="03b88-149">Date and time that the call started.</span></span>  <br/> |
|<span data-ttu-id="03b88-150">**结束时间**</span><span class="sxs-lookup"><span data-stu-id="03b88-150">**End time**</span></span> <br/> |<span data-ttu-id="03b88-151">是</span><span class="sxs-lookup"><span data-stu-id="03b88-151">Yes</span></span>  <br/> |<span data-ttu-id="03b88-152">呼叫结束的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="03b88-152">Date and time that the call ended.</span></span>  <br/> |
|<span data-ttu-id="03b88-153">**呼叫者用户代理**</span><span class="sxs-lookup"><span data-stu-id="03b88-153">**Caller user agent**</span></span> <br/> |<span data-ttu-id="03b88-154">是</span><span class="sxs-lookup"><span data-stu-id="03b88-154">Yes</span></span>  <br/> |<span data-ttu-id="03b88-155">发出呼叫的人的终结点使用的软件。</span><span class="sxs-lookup"><span data-stu-id="03b88-155">Software used by the endpoint of the person who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="03b88-156">**被叫方用户代理**</span><span class="sxs-lookup"><span data-stu-id="03b88-156">**Callee user agent**</span></span> <br/> |<span data-ttu-id="03b88-157">是</span><span class="sxs-lookup"><span data-stu-id="03b88-157">Yes</span></span>  <br/> |<span data-ttu-id="03b88-158">被呼叫的人的终结点使用的软件。</span><span class="sxs-lookup"><span data-stu-id="03b88-158">Software used by the endpoint of the person who was called.</span></span>  <br/> |
|<span data-ttu-id="03b88-159">**来回行程（毫秒）**</span><span class="sxs-lookup"><span data-stu-id="03b88-159">**Round trip (ms)**</span></span> <br/> |<span data-ttu-id="03b88-160">是</span><span class="sxs-lookup"><span data-stu-id="03b88-160">Yes</span></span>  <br/> |<span data-ttu-id="03b88-p104">实时传输协议 (RTP) 数据包来往于另一个终结点所需的平均时间量（以毫秒为单位）。来回行程的时间小于或等于 100 毫秒被视为质量可接受。</span><span class="sxs-lookup"><span data-stu-id="03b88-p104">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span>  <br/> <span data-ttu-id="03b88-p105">高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。</span><span class="sxs-lookup"><span data-stu-id="03b88-p105">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span>  <br/> |
|<span data-ttu-id="03b88-165">**性能降低 (MOS)**</span><span class="sxs-lookup"><span data-stu-id="03b88-165">**Degradation (MOS)**</span></span> <br/> |<span data-ttu-id="03b88-166">是</span><span class="sxs-lookup"><span data-stu-id="03b88-166">Yes</span></span>  <br/> |<span data-ttu-id="03b88-167">呼叫过程中遇到的性能降低的平均意见得分 (MOS) 的平均值。</span><span class="sxs-lookup"><span data-stu-id="03b88-167">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="03b88-168">性能降低值的范围介于 0.0 和 5.0 之间。</span><span class="sxs-lookup"><span data-stu-id="03b88-168">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="03b88-169">该值小于或等于 0.5 表示可接受的性能降低。</span><span class="sxs-lookup"><span data-stu-id="03b88-169">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="03b88-170">过去，平均意见得分是通过让用户对呼叫质量进行评级（范围为 1 到 5）来计算得出的。</span><span class="sxs-lookup"><span data-stu-id="03b88-170">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="03b88-171">在业务服务器 Skype，一算法预测如何将具有用户分级呼叫。</span><span class="sxs-lookup"><span data-stu-id="03b88-171">In Skype for Business Server, a set of algorithms predict how users would have rated a call.</span></span>  <br/> <span data-ttu-id="03b88-p107">高性能降低值可能是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器或终结点超载造成的，从而导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="03b88-p107">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span>  <br/> |
|<span data-ttu-id="03b88-174">**数据包丢失**</span><span class="sxs-lookup"><span data-stu-id="03b88-174">**Packet loss**</span></span> <br/> |<span data-ttu-id="03b88-175">是</span><span class="sxs-lookup"><span data-stu-id="03b88-175">Yes</span></span>  <br/> |<span data-ttu-id="03b88-p108">平均 RTP 数据包丢失率。（当 RTP 数据包（一项用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时将发生数据包丢失。）高丢失率通常是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器超载造成的，从而导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="03b88-p108">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span>  <br/> |
|<span data-ttu-id="03b88-179">**抖动**</span><span class="sxs-lookup"><span data-stu-id="03b88-179">**Jitter**</span></span> <br/> |<span data-ttu-id="03b88-180">是</span><span class="sxs-lookup"><span data-stu-id="03b88-180">Yes</span></span>  <br/> |<span data-ttu-id="03b88-p109">在 RTP 数据包到达之间检测到的平均抖动率。（抖动是针对呼叫的“不稳定性”的度量。）高抖动值通常是由拥塞或媒体服务器超载造成的，从而导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="03b88-p109">Average jitter detected between RTP packet arrivals. (Jitter is a measure of the "shakiness" of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span>  <br/> |
|<span data-ttu-id="03b88-183">**修复程序隐藏比率**</span><span class="sxs-lookup"><span data-stu-id="03b88-183">**Healer concealed ratio**</span></span> <br/> |<span data-ttu-id="03b88-184">是</span><span class="sxs-lookup"><span data-stu-id="03b88-184">Yes</span></span>  <br/> |<span data-ttu-id="03b88-p110">隐藏的音频样本与样本总数的平均比率。（隐藏的音频样本是一项技术，用于消除通常由丢弃的网络数据包造成的意外转换。）高值指示数据包丢失或抖动造成的显著的丢失隐藏级别，从而导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="03b88-p110">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span>  <br/> |
|<span data-ttu-id="03b88-187">**修复程序拉伸比率**</span><span class="sxs-lookup"><span data-stu-id="03b88-187">**Healer stretched ratio**</span></span> <br/> |<span data-ttu-id="03b88-188">是</span><span class="sxs-lookup"><span data-stu-id="03b88-188">Yes</span></span>  <br/> |<span data-ttu-id="03b88-p111">拉伸的音频样本数与样本总数的平均比率。（拉伸的音频是一类已扩展的音频，可在检测到丢弃的网络数据包时帮助保持呼叫质量。）高值指示抖动造成的显著的样本拉伸级别，从而导致音频听起来很机械或失真。</span><span class="sxs-lookup"><span data-stu-id="03b88-p111">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span>  <br/> |
|<span data-ttu-id="03b88-191">**修复程序压缩比率**</span><span class="sxs-lookup"><span data-stu-id="03b88-191">**Healer compressed ratio**</span></span> <br/> |<span data-ttu-id="03b88-192">是</span><span class="sxs-lookup"><span data-stu-id="03b88-192">Yes</span></span>  <br/> |<span data-ttu-id="03b88-p112">压缩的音频样本与样本总数的平均比率。（压缩的音频是一类已压缩的音频，可在检测到丢弃的网络数据包时帮助保持呼叫质量。）高值指示抖动造成的显著的样本压缩级别，从而导致音频听起来像是已加速或失真。</span><span class="sxs-lookup"><span data-stu-id="03b88-p112">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span>  <br/> |
|<span data-ttu-id="03b88-195">**连接**</span><span class="sxs-lookup"><span data-stu-id="03b88-195">**Connectivity**</span></span> <br/> |<span data-ttu-id="03b88-196">是</span><span class="sxs-lookup"><span data-stu-id="03b88-196">Yes</span></span>  <br/> | <span data-ttu-id="03b88-p113">无线通信链路的类型。通常，这是以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="03b88-p113">Type of wireless communication link. Typically, this is one of the following:</span></span> <br/>  <span data-ttu-id="03b88-199">中继</span><span class="sxs-lookup"><span data-stu-id="03b88-199">Relay</span></span> <br/>  <span data-ttu-id="03b88-200">直接</span><span class="sxs-lookup"><span data-stu-id="03b88-200">Direct</span></span> <br/> |
   

