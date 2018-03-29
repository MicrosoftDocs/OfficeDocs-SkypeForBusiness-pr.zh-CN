---
title: Skype for Business Server 2015 中的呼叫详情报告
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38862e35-3fec-41b9-a035-0b301942d446
description: 摘要： 了解使用 Skype 业务服务器 2015年呼叫详细信息报告。
ms.openlocfilehash: 942562ed33462506c9da137b3e4377e102d0ec98
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="call-detail-report-in-skype-for-business-server-2015"></a><span data-ttu-id="49dd9-103">Skype for Business Server 2015 中的呼叫详情报告</span><span class="sxs-lookup"><span data-stu-id="49dd9-103">Call Detail Report in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="49dd9-104">**摘要：**了解有关使用 Skype 业务服务器 2015年呼叫详细信息报告。</span><span class="sxs-lookup"><span data-stu-id="49dd9-104">**Summary:** Learn about the Call Detail Report used in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="49dd9-105">呼叫详细信息报告提供了详细地观察单个调用;该报告包括几乎所有质量经验指标和统计数据收集通过 Skype 的业务服务器 2015，如划分为报表节：</span><span class="sxs-lookup"><span data-stu-id="49dd9-105">The Call Detail Report provides a detailed look at an individual call; the report includes nearly all the Quality of Experience metrics and statistics collected by Skype for Business Server 2015, divided into report sections such as:</span></span>
  
- <span data-ttu-id="49dd9-106">呼叫信息</span><span class="sxs-lookup"><span data-stu-id="49dd9-106">Call Information</span></span> 
    
- <span data-ttu-id="49dd9-107">呼叫者设备和信号指标</span><span class="sxs-lookup"><span data-stu-id="49dd9-107">Caller Device and Signal Metrics</span></span>
    
- <span data-ttu-id="49dd9-108">被叫方设备和信号指标</span><span class="sxs-lookup"><span data-stu-id="49dd9-108">Callee Device and Signal metrics</span></span>
    
- <span data-ttu-id="49dd9-109">呼叫者客户端事件</span><span class="sxs-lookup"><span data-stu-id="49dd9-109">Caller Client Event</span></span>
    
- <span data-ttu-id="49dd9-110">被叫方客户端事件</span><span class="sxs-lookup"><span data-stu-id="49dd9-110">Callee Client Event</span></span>
    
- <span data-ttu-id="49dd9-111">音频流（呼叫者到被叫方）</span><span class="sxs-lookup"><span data-stu-id="49dd9-111">Audio Stream (Caller to Callee)</span></span>
    
- <span data-ttu-id="49dd9-112">视频流（呼叫者到被叫方）</span><span class="sxs-lookup"><span data-stu-id="49dd9-112">Video Stream (Caller to Callee)</span></span>
    
- <span data-ttu-id="49dd9-113">音频流（被叫方到呼叫者）</span><span class="sxs-lookup"><span data-stu-id="49dd9-113">Audio Stream (Callee to Caller)</span></span>
    
- <span data-ttu-id="49dd9-114">视频流（被叫方到呼叫者）</span><span class="sxs-lookup"><span data-stu-id="49dd9-114">Video Stream (Callee to Caller)</span></span>
    
<span data-ttu-id="49dd9-p101">请记住，您在指定报告上看到的类别和指标取决于两个因素：会话类型和会话中使用的终结点类型。例如，纯音频呼叫不会报告视频流的相关指标；这是因为该呼叫没有视频流。同样，您的报告可能列出了呼叫者统计信息，而没有列出被叫方统计信息。这通常是因为被叫方没有使用符合 SIP 的设备。终结点负责在呼叫结束时报告统计信息；但是，移动电话（不了解有关 SIP 或 SIP 统计信息的任何情况）无法报告此类信息。如果您呼叫某人且此人用其移动电话应答您的呼叫，则呼叫结束时您将不会获得来自该移动电话的报告。</span><span class="sxs-lookup"><span data-stu-id="49dd9-p101">Keep in mind that the categories and the metrics you see on a given report depend on two things: the type of session and the type of endpoints used in the session. For example, an audio-only call will not report metrics for video streams; that's because the call didn't have a video stream. Likewise, you might have a report that lists caller statistics but not callee statistics. That's typically because the callee was not using a SIP-compliant device. Endpoints are responsible for reporting statistics at the end of a call; however, a cell phone (which knows nothing about SIP or SIP statistics) is unable to report that kind of information. If you call someone and they answer you on their cell phone, you will not get a report from that cell phone when the call ends.</span></span>
  
<span data-ttu-id="49dd9-121">呼叫详情报告在您尝试准确确定指定呼叫遇到媒体质量问题的原因时最为有用。</span><span class="sxs-lookup"><span data-stu-id="49dd9-121">The Call Detail Report is most useful when you are trying to determine exactly why a given call experienced media quality problems.</span></span>
  
## <a name="accessing-the-call-detail-report"></a><span data-ttu-id="49dd9-122">访问呼叫详情报告</span><span class="sxs-lookup"><span data-stu-id="49dd9-122">Accessing the Call Detail Report</span></span>

<span data-ttu-id="49dd9-123">可以从下列任意报告中访问呼叫详情报告：</span><span class="sxs-lookup"><span data-stu-id="49dd9-123">The Call Detail Report can be accessed from any of the following reports:</span></span>
  
- <span data-ttu-id="49dd9-124">（通过单击调用卷或较差的呼叫百分比度量）[中业务服务器 2015年的 Skype 的位置报告](location-report.md)</span><span class="sxs-lookup"><span data-stu-id="49dd9-124">The [Location Report in Skype for Business Server 2015](location-report.md) (by clicking either the Call volume or the Poor call percentage metric)</span></span>
    
- <span data-ttu-id="49dd9-125">[媒体质量摘要报表中的业务服务器 2015 Skype](summary.md) （通过单击呼叫或差呼叫百分比度量）</span><span class="sxs-lookup"><span data-stu-id="49dd9-125">The [Media Quality Summary Report in Skype for Business Server 2015](summary.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>
    
- <span data-ttu-id="49dd9-126">[媒体质量比较报表中的业务服务器 2015年的 Skype](comparison.md) （通过单击[在业务服务器 2015年的 Skype 呼叫列表报表](call-list-report-0.md)，然后单击详细信息度量）。</span><span class="sxs-lookup"><span data-stu-id="49dd9-126">The [Media Quality Comparison Report in Skype for Business Server 2015](comparison.md) (by clicking the [Call List Report in Skype for Business Server 2015](call-list-report-0.md) and then clicking the Detail metric).</span></span>
    
- <span data-ttu-id="49dd9-127">（通过单击呼叫或差呼叫百分比度量）[中的业务服务器 2015 Skype 的服务器性能报告](server-performance.md)</span><span class="sxs-lookup"><span data-stu-id="49dd9-127">The [Server Performance Report in Skype for Business Server 2015](server-performance.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>
    
- <span data-ttu-id="49dd9-128">（通过单击详细信息度量）[中的业务服务器 2015 Skype 呼叫列表报告](call-list-report-0.md)</span><span class="sxs-lookup"><span data-stu-id="49dd9-128">The [Call List Report in Skype for Business Server 2015](call-list-report-0.md) (by clicking the Detail metric)</span></span>
    
<span data-ttu-id="49dd9-129">从呼叫详细信息报表中可以访问[在 Skype 的业务服务器 2015年设备报告](device-report.md)通过单击以下指标：</span><span class="sxs-lookup"><span data-stu-id="49dd9-129">From within the Call Detail Report you can access the [Device Report in Skype for Business Server 2015](device-report.md) by clicking either of the following metrics:</span></span>
  
- <span data-ttu-id="49dd9-130">捕获设备</span><span class="sxs-lookup"><span data-stu-id="49dd9-130">Capture device</span></span>
    
- <span data-ttu-id="49dd9-131">呈现设备</span><span class="sxs-lookup"><span data-stu-id="49dd9-131">Render device</span></span>
    
<span data-ttu-id="49dd9-132">您还可以通过单击“A/V 边缘服务器”指标访问服务器媒体质量趋势报告。</span><span class="sxs-lookup"><span data-stu-id="49dd9-132">You can also access the Server Media Quality Trend Report by clicking the A/V edge server metric.</span></span>
  
## <a name="making-the-best-use-of-the-call-detail-report"></a><span data-ttu-id="49dd9-133">充分利用呼叫详情报告</span><span class="sxs-lookup"><span data-stu-id="49dd9-133">Making the Best Use of the Call Detail Report</span></span>

<span data-ttu-id="49dd9-p102">呼叫详情报告通常包括 250 多个不同的指标，其中包括麦克风时间戳偏移、低 SNR 时间和近端回声时间等项目。如果您不记得所有这些指标实际度量的内容，请尝试将鼠标指针置于指标标签上方；通常，将显示描述该指标的工具提示。</span><span class="sxs-lookup"><span data-stu-id="49dd9-p102">The Call Detail Report typically includes over 250 different metrics, including such items as Microphone timestamp drift, Low SNR time, and Near end to echo time. If you can't remember what all of these metrics actually measure, try holding your mouse over the metric label; often-times, a tooltip will appear describing that metric.</span></span>
  
<span data-ttu-id="49dd9-p103">如果查找指标时遇到问题，请在搜索框中键入指标标签的部分内容，然后单击“**查找**”。例如，如果你无法找到“低 SNR 时间”指标，请在搜索框中键入“SNR”，然后单击“**查找**”。</span><span class="sxs-lookup"><span data-stu-id="49dd9-p103">If you have problems locating a metric, type part of the metric label in the search box, and then click **Find**. For example, if you can't find the Low SNR time metric, type SNR in the search box, and then click **Find**.</span></span>
  
<span data-ttu-id="49dd9-p104">请注意，报告仅跟踪关于呼叫的信息。不记录呼叫本身。</span><span class="sxs-lookup"><span data-stu-id="49dd9-p104">Note that the report only tracks information about a call. The call itself is not recorded.</span></span>
  
## <a name="filters"></a><span data-ttu-id="49dd9-140">筛选器</span><span class="sxs-lookup"><span data-stu-id="49dd9-140">Filters</span></span>

<span data-ttu-id="49dd9-p105">无。您无法筛选呼叫详情报告。</span><span class="sxs-lookup"><span data-stu-id="49dd9-p105">None. You cannot filter the Call Detail Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="49dd9-143">指标</span><span class="sxs-lookup"><span data-stu-id="49dd9-143">Metrics</span></span>

<span data-ttu-id="49dd9-144">下表列出了每个呼叫的呼叫详情报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="49dd9-144">The following table lists the information provided in the Call Detail Report for each call.</span></span>
  
<span data-ttu-id="49dd9-145">**呼叫详细信息报告统计数据**</span><span class="sxs-lookup"><span data-stu-id="49dd9-145">**Call Detail Report Metrics**</span></span>

|<span data-ttu-id="49dd9-146">**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="49dd9-146">**Name**</span></span>|<span data-ttu-id="49dd9-147">**可以在此项上进行排序？**</span><span class="sxs-lookup"><span data-stu-id="49dd9-147">**Can you sort on this item?**</span></span>|<span data-ttu-id="49dd9-148">**说明**</span><span class="sxs-lookup"><span data-stu-id="49dd9-148">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="49dd9-149">**呼叫者 PAI**</span><span class="sxs-lookup"><span data-stu-id="49dd9-149">**Caller PAI**</span></span> <br/> |<span data-ttu-id="49dd9-150">否</span><span class="sxs-lookup"><span data-stu-id="49dd9-150">No</span></span>  <br/> |<span data-ttu-id="49dd9-p106">发起呼叫的用户的 P-Asserted-Identity。P-Asserted-Identity 用于传达受信任网络内用户经验证的身份。</span><span class="sxs-lookup"><span data-stu-id="49dd9-p106">P-Asserted-Identity of the user who initiated the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span>  <br/> |
|<span data-ttu-id="49dd9-153">**呼叫者 URI**</span><span class="sxs-lookup"><span data-stu-id="49dd9-153">**Caller URI**</span></span> <br/> |<span data-ttu-id="49dd9-154">否</span><span class="sxs-lookup"><span data-stu-id="49dd9-154">No</span></span>  <br/> |<span data-ttu-id="49dd9-155">发起呼叫的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="49dd9-155">SIP address of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="49dd9-156">**呼叫者终结点**</span><span class="sxs-lookup"><span data-stu-id="49dd9-156">**Caller endpoint**</span></span> <br/> |<span data-ttu-id="49dd9-157">否</span><span class="sxs-lookup"><span data-stu-id="49dd9-157">No</span></span>  <br/> |<span data-ttu-id="49dd9-158">用于发出呼叫的设备。</span><span class="sxs-lookup"><span data-stu-id="49dd9-158">Device used to make the call.</span></span>  <br/> |
|<span data-ttu-id="49dd9-159">**呼叫者用户代理**</span><span class="sxs-lookup"><span data-stu-id="49dd9-159">**Caller user agent**</span></span> <br/> |<span data-ttu-id="49dd9-160">否</span><span class="sxs-lookup"><span data-stu-id="49dd9-160">No</span></span>  <br/> |<span data-ttu-id="49dd9-161">发出呼叫的设备上使用的软件。</span><span class="sxs-lookup"><span data-stu-id="49dd9-161">Software used on the device that made the call.</span></span>  <br/> |
|<span data-ttu-id="49dd9-162">**呼叫开始**</span><span class="sxs-lookup"><span data-stu-id="49dd9-162">**Call start**</span></span> <br/> |<span data-ttu-id="49dd9-163">否</span><span class="sxs-lookup"><span data-stu-id="49dd9-163">No</span></span>  <br/> |<span data-ttu-id="49dd9-164">最初发出呼叫的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="49dd9-164">Date and time that the call was initially placed.</span></span>  <br/> |
|<span data-ttu-id="49dd9-165">**中介服务器旁路呼叫**</span><span class="sxs-lookup"><span data-stu-id="49dd9-165">**Mediation Server bypass call**</span></span> <br/> |<span data-ttu-id="49dd9-166">否</span><span class="sxs-lookup"><span data-stu-id="49dd9-166">No</span></span>  <br/> |<span data-ttu-id="49dd9-167">指示呼叫是否在不通过中介服务器的情况下连接到 PSTN 语音网关或合格的 IP-PBX。</span><span class="sxs-lookup"><span data-stu-id="49dd9-167">Indicates whether the call connected to a PSTN voice gateway or qualified IP-PBX without passing through the Mediation Server.</span></span>  <br/> |
|<span data-ttu-id="49dd9-168">**呼叫者 OS**</span><span class="sxs-lookup"><span data-stu-id="49dd9-168">**Caller OS**</span></span> <br/> |<span data-ttu-id="49dd9-169">否</span><span class="sxs-lookup"><span data-stu-id="49dd9-169">No</span></span>  <br/> |<span data-ttu-id="49dd9-170">呼叫者计算机的操作系统。</span><span class="sxs-lookup"><span data-stu-id="49dd9-170">Operating system of the caller's computer.</span></span>  <br/> |
|<span data-ttu-id="49dd9-171">**呼叫者 CPU**</span><span class="sxs-lookup"><span data-stu-id="49dd9-171">**Caller CPU**</span></span> <br/> |<span data-ttu-id="49dd9-172">否</span><span class="sxs-lookup"><span data-stu-id="49dd9-172">No</span></span>  <br/> |<span data-ttu-id="49dd9-173">发起呼叫的用户的计算机中安装的 CPU。</span><span class="sxs-lookup"><span data-stu-id="49dd9-173">CPU installed in the computer of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="49dd9-174">**呼叫者 CPU 内核数**</span><span class="sxs-lookup"><span data-stu-id="49dd9-174">**Caller CPU core number**</span></span> <br/> |<span data-ttu-id="49dd9-175">否</span><span class="sxs-lookup"><span data-stu-id="49dd9-175">No</span></span>  <br/> |<span data-ttu-id="49dd9-176">发起呼叫的人员使用的计算机中的处理器数量。</span><span class="sxs-lookup"><span data-stu-id="49dd9-176">Processor number in the computer used by the person who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="49dd9-177">**呼叫者 CPU 速度**</span><span class="sxs-lookup"><span data-stu-id="49dd9-177">**Caller CPU speed**</span></span> <br/> |<span data-ttu-id="49dd9-178">否</span><span class="sxs-lookup"><span data-stu-id="49dd9-178">No</span></span>  <br/> |<span data-ttu-id="49dd9-179">发起呼叫的人员使用的计算机的 CPU 时钟频率。</span><span class="sxs-lookup"><span data-stu-id="49dd9-179">Clock speed of the CPU of the computer used by the person who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="49dd9-180">**呼叫者 CPU 虚拟化**</span><span class="sxs-lookup"><span data-stu-id="49dd9-180">**Caller CPU virtualization**</span></span> <br/> |<span data-ttu-id="49dd9-181">否</span><span class="sxs-lookup"><span data-stu-id="49dd9-181">No</span></span>  <br/> |<span data-ttu-id="49dd9-182">发起呼叫的人员使用的计算机上使用的虚拟化（如果有）。</span><span class="sxs-lookup"><span data-stu-id="49dd9-182">Virtualization (if any) used on the computer used by the person who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="49dd9-183">**被叫方 PAI**</span><span class="sxs-lookup"><span data-stu-id="49dd9-183">**Callee PAI**</span></span> <br/> |<span data-ttu-id="49dd9-184">否</span><span class="sxs-lookup"><span data-stu-id="49dd9-184">No</span></span>  <br/> |<span data-ttu-id="49dd9-p107">受邀加入呼叫的用户的 P-Asserted-Identity。P-Asserted-Identity 用于传达受信任网络内用户经验证的身份。</span><span class="sxs-lookup"><span data-stu-id="49dd9-p107">P-Asserted-Identity of the user who was invited to join the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span>  <br/> |
|<span data-ttu-id="49dd9-187">**被叫方 URI**</span><span class="sxs-lookup"><span data-stu-id="49dd9-187">**Callee URI**</span></span> <br/> |<span data-ttu-id="49dd9-188">否</span><span class="sxs-lookup"><span data-stu-id="49dd9-188">No</span></span>  <br/> |<span data-ttu-id="49dd9-189">被叫的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="49dd9-189">SIP address of the user who was called.</span></span>  <br/> |
|<span data-ttu-id="49dd9-190">**被叫方终结点**</span><span class="sxs-lookup"><span data-stu-id="49dd9-190">**Callee endpoint**</span></span> <br/> |<span data-ttu-id="49dd9-191">否</span><span class="sxs-lookup"><span data-stu-id="49dd9-191">No</span></span>  <br/> |<span data-ttu-id="49dd9-192">用于接收呼叫的设备。</span><span class="sxs-lookup"><span data-stu-id="49dd9-192">Device used to receive the call.</span></span>  <br/> |
|<span data-ttu-id="49dd9-193">**被叫方用户代理**</span><span class="sxs-lookup"><span data-stu-id="49dd9-193">**Callee user agent**</span></span> <br/> |<span data-ttu-id="49dd9-194">否</span><span class="sxs-lookup"><span data-stu-id="49dd9-194">No</span></span>  <br/> |<span data-ttu-id="49dd9-195">接收呼叫的设备上使用的软件。</span><span class="sxs-lookup"><span data-stu-id="49dd9-195">Software used on the device that received the call.</span></span>  <br/> |
|<span data-ttu-id="49dd9-196">**持续时间**</span><span class="sxs-lookup"><span data-stu-id="49dd9-196">**Duration**</span></span> <br/> |<span data-ttu-id="49dd9-197">否</span><span class="sxs-lookup"><span data-stu-id="49dd9-197">No</span></span>  <br/> |<span data-ttu-id="49dd9-198">呼叫的时长。</span><span class="sxs-lookup"><span data-stu-id="49dd9-198">Length of time for the call.</span></span>  <br/> |
|<span data-ttu-id="49dd9-199">**媒体旁路警告标记**</span><span class="sxs-lookup"><span data-stu-id="49dd9-199">**Media bypass warning flag**</span></span> <br/> |<span data-ttu-id="49dd9-200">否</span><span class="sxs-lookup"><span data-stu-id="49dd9-200">No</span></span>  <br/> |<span data-ttu-id="49dd9-201">在绕过中介服务器时发出的警告。</span><span class="sxs-lookup"><span data-stu-id="49dd9-201">Warning issued when the Mediation Server was bypassed.</span></span>  <br/> |
|<span data-ttu-id="49dd9-202">**被叫方 OS**</span><span class="sxs-lookup"><span data-stu-id="49dd9-202">**Callee OS**</span></span> <br/> |<span data-ttu-id="49dd9-203">否</span><span class="sxs-lookup"><span data-stu-id="49dd9-203">No</span></span>  <br/> |<span data-ttu-id="49dd9-204">被叫用户的计算机的操作系统。</span><span class="sxs-lookup"><span data-stu-id="49dd9-204">Operating system of the computer for the user who was called.</span></span>  <br/> |
|<span data-ttu-id="49dd9-205">**被叫方 CPU**</span><span class="sxs-lookup"><span data-stu-id="49dd9-205">**Callee CPU**</span></span> <br/> |<span data-ttu-id="49dd9-206">否</span><span class="sxs-lookup"><span data-stu-id="49dd9-206">No</span></span>  <br/> |<span data-ttu-id="49dd9-207">被叫用户的计算机中安装的 CPU。</span><span class="sxs-lookup"><span data-stu-id="49dd9-207">CPU installed in the computer of the user who was called.</span></span>  <br/> |
|<span data-ttu-id="49dd9-208">**被叫方内核数**</span><span class="sxs-lookup"><span data-stu-id="49dd9-208">**Callee core number**</span></span> <br/> |<span data-ttu-id="49dd9-209">否</span><span class="sxs-lookup"><span data-stu-id="49dd9-209">No</span></span>  <br/> |<span data-ttu-id="49dd9-210">被叫人员使用的计算机中的处理器数量。</span><span class="sxs-lookup"><span data-stu-id="49dd9-210">Processor number in the computer used by the person who was called.</span></span>  <br/> |
|<span data-ttu-id="49dd9-211">**被叫方 CPU 速度**</span><span class="sxs-lookup"><span data-stu-id="49dd9-211">**Callee CPU speed**</span></span> <br/> |<span data-ttu-id="49dd9-212">否</span><span class="sxs-lookup"><span data-stu-id="49dd9-212">No</span></span>  <br/> |<span data-ttu-id="49dd9-213">被叫人员使用的计算机的 CPU 时钟频率。</span><span class="sxs-lookup"><span data-stu-id="49dd9-213">Clock speed of the CPU of the computer used by the person who was called.</span></span>  <br/> |
|<span data-ttu-id="49dd9-214">**被叫方 CPU 虚拟化**</span><span class="sxs-lookup"><span data-stu-id="49dd9-214">**Callee CPU virtualization**</span></span> <br/> |<span data-ttu-id="49dd9-215">否</span><span class="sxs-lookup"><span data-stu-id="49dd9-215">No</span></span>  <br/> |<span data-ttu-id="49dd9-216">被叫人员使用的计算机上使用的虚拟化（如果有）。</span><span class="sxs-lookup"><span data-stu-id="49dd9-216">Virtualization (if any) used on the computer used by the person who was called.</span></span>  <br/> |
   

