---
title: Lync Server 2013：呼叫列表报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call List Report
ms:assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615020(v=OCS.15)
ms:contentKeyID: 48184921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d9d437b32907108d5666ef9e1b175c170030585
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526289"
---
# <a name="call-list-report-in-lync-server-2013"></a><span data-ttu-id="39442-102">Lync Server 2013 中的呼叫列表报告</span><span class="sxs-lookup"><span data-stu-id="39442-102">Call List Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39442-103">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="39442-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="39442-104">呼叫列表报告提供了针对您组织中发出和接收的单个呼叫的用户体验质量 (QoE) 指标。</span><span class="sxs-lookup"><span data-stu-id="39442-104">The Call List Report provides Quality of Experience (QoE) metrics for individual calls made and received in your organization.</span></span> <span data-ttu-id="39442-105">请注意，报告的实际指标将取决于您访问呼叫列表报告的方式。</span><span class="sxs-lookup"><span data-stu-id="39442-105">Note that the actual metrics reported will depend on how you access the Call List report.</span></span> <span data-ttu-id="39442-106">例如，如果从 [Lync Server 2013 中的设备报告](lync-server-2013-device-report.md)打开报告，将会看到以下指标，这些指标也会在设备报告中报告：</span><span class="sxs-lookup"><span data-stu-id="39442-106">For example, if you open the report from the [Device Report in Lync Server 2013](lync-server-2013-device-report.md), you'll see metrics such as the following, metrics that are also reported on the Device Report:</span></span>

  - <span data-ttu-id="39442-107">呼叫者的麦克风</span><span class="sxs-lookup"><span data-stu-id="39442-107">Caller's microphone</span></span>

  - <span data-ttu-id="39442-108">呼叫者的扬声器</span><span class="sxs-lookup"><span data-stu-id="39442-108">Caller's speaker</span></span>

  - <span data-ttu-id="39442-109">被叫方的麦克风</span><span class="sxs-lookup"><span data-stu-id="39442-109">Callee's microphone</span></span>

  - <span data-ttu-id="39442-110">被叫方的扬声器</span><span class="sxs-lookup"><span data-stu-id="39442-110">Callee's speaker</span></span>

  - <span data-ttu-id="39442-111">语音切换时间比率</span><span class="sxs-lookup"><span data-stu-id="39442-111">Ratio of voice switch time</span></span>

<span data-ttu-id="39442-112">但是，如果在 [Lync Server 2013 的 "位置" 报告中](lync-server-2013-location-report.md)打开呼叫列表报告，则不会看到这些指标中的任何一个。相反，你将看到如下所示的指标：</span><span class="sxs-lookup"><span data-stu-id="39442-112">However, if you open the Call List Report from the [Location Report in Lync Server 2013](lync-server-2013-location-report.md), you won't see any of those metrics; instead, you'll see metrics like these:</span></span>

  - <span data-ttu-id="39442-113">来回行程(毫秒)</span><span class="sxs-lookup"><span data-stu-id="39442-113">Round trip (ms)</span></span>

  - <span data-ttu-id="39442-114">性能降低(MOS)</span><span class="sxs-lookup"><span data-stu-id="39442-114">Degradation (MOS)</span></span>

  - <span data-ttu-id="39442-115">数据包丢失</span><span class="sxs-lookup"><span data-stu-id="39442-115">Packet loss</span></span>

  - <span data-ttu-id="39442-116">抖动(毫秒)</span><span class="sxs-lookup"><span data-stu-id="39442-116">Jitter (ms)</span></span>

<span data-ttu-id="39442-p102">这些是在位置报告上报告的指标。但是，您始终能够从呼叫列表报告中单击“详细信息”指标来提供任何呼叫的完整 QoE 信息。</span><span class="sxs-lookup"><span data-stu-id="39442-p102">Those are the metrics reported on the Location Report. However, from the Call List Report you can always click the Detail metric to provide complete QoE information for any call.</span></span>

<div>

## <a name="accessing-the-call-list-report"></a><span data-ttu-id="39442-119">访问呼叫列表报告</span><span class="sxs-lookup"><span data-stu-id="39442-119">Accessing the Call List Report</span></span>

<span data-ttu-id="39442-120">可从以下任一报告访问呼叫列表报告：</span><span class="sxs-lookup"><span data-stu-id="39442-120">The Call List Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="39442-121">[Lync Server 2013 中的位置报告](lync-server-2013-location-report.md)通过单击 "呼叫量" 或 "差的呼叫百分比" 指标 () </span><span class="sxs-lookup"><span data-stu-id="39442-121">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="39442-122">[Lync Server 2013 中的设备报告](lync-server-2013-device-report.md)通过单击 "呼叫量" 或 "差的呼叫百分比" 指标 () </span><span class="sxs-lookup"><span data-stu-id="39442-122">The [Device Report in Lync Server 2013](lync-server-2013-device-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="39442-123">[Lync Server 2013 中的媒体质量摘要报告](lync-server-2013-media-quality-summary-report.md)通过单击 "呼叫量" 或 "差的呼叫百分比" 指标)  (</span><span class="sxs-lookup"><span data-stu-id="39442-123">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="39442-124">[Lync server 2013 中的服务器性能报告](lync-server-2013-server-performance-report.md)通过单击 "呼叫量" 或 "差的呼叫百分比" 指标) 来 (</span><span class="sxs-lookup"><span data-stu-id="39442-124">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

<span data-ttu-id="39442-125">从呼叫列表报告中，您可以通过单击详细信息指标来访问 [Lync Server 2013 中的呼叫详细信息报告](lync-server-2013-call-detail-report.md) 。</span><span class="sxs-lookup"><span data-stu-id="39442-125">From within the Call List Report you can access the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) by clicking the Detail metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a><span data-ttu-id="39442-126">最充分地利用呼叫列表报告</span><span class="sxs-lookup"><span data-stu-id="39442-126">Making the Best Use of the Call List Report</span></span>

<span data-ttu-id="39442-127">如果您记不住实际度量哪些呼叫列表报告指标（例如语音切换时间比率），请将鼠标指针悬停在指标标签的上方；这将显示一个工具提示，它为您简述了此指标。</span><span class="sxs-lookup"><span data-stu-id="39442-127">If you can't remember what some of the Call List Report metrics (such as Ratio voice switch time) actually measure, hold your mouse over the metric label; a tool tip will then appear giving you a brief description of the metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="39442-128">筛选器</span><span class="sxs-lookup"><span data-stu-id="39442-128">Filters</span></span>

<span data-ttu-id="39442-p103">无。您无法筛选呼叫列表报告。</span><span class="sxs-lookup"><span data-stu-id="39442-p103">None. You cannot filter the Call List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="39442-131">指标</span><span class="sxs-lookup"><span data-stu-id="39442-131">Metrics</span></span>

<span data-ttu-id="39442-132">下表列出了呼叫列表报告中提供的有关每个呼叫的信息。</span><span class="sxs-lookup"><span data-stu-id="39442-132">The following table lists the information provided in the Call List Report for each call.</span></span>

### <a name="call-list-report-metrics"></a><span data-ttu-id="39442-133">呼叫列表报告指标</span><span class="sxs-lookup"><span data-stu-id="39442-133">Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39442-134">名称</span><span class="sxs-lookup"><span data-stu-id="39442-134">Name</span></span></th>
<th><span data-ttu-id="39442-135">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="39442-135">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="39442-136">说明</span><span class="sxs-lookup"><span data-stu-id="39442-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39442-137"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="39442-137"><strong>Details</strong></span></span></p></td>
<td><p><span data-ttu-id="39442-138">否</span><span class="sxs-lookup"><span data-stu-id="39442-138">No</span></span></p></td>
<td><p><span data-ttu-id="39442-139">单击此项时，报告将显示有关呼叫的其他信息。</span><span class="sxs-lookup"><span data-stu-id="39442-139">When you click this item, the report shows additional information on the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39442-140"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="39442-140"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="39442-141">是</span><span class="sxs-lookup"><span data-stu-id="39442-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="39442-142">发起呼叫的人的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="39442-142">SIP address of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39442-143"><strong>约定</strong></span><span class="sxs-lookup"><span data-stu-id="39442-143"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="39442-144">是</span><span class="sxs-lookup"><span data-stu-id="39442-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="39442-145">被呼叫的人的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="39442-145">SIP address of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39442-146"><strong>开始时间</strong></span><span class="sxs-lookup"><span data-stu-id="39442-146"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="39442-147">是</span><span class="sxs-lookup"><span data-stu-id="39442-147">Yes</span></span></p></td>
<td><p><span data-ttu-id="39442-148">呼叫开始的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="39442-148">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39442-149"><strong>结束时间</strong></span><span class="sxs-lookup"><span data-stu-id="39442-149"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="39442-150">是</span><span class="sxs-lookup"><span data-stu-id="39442-150">Yes</span></span></p></td>
<td><p><span data-ttu-id="39442-151">呼叫结束的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="39442-151">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39442-152"><strong>呼叫者用户代理</strong></span><span class="sxs-lookup"><span data-stu-id="39442-152"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="39442-153">是</span><span class="sxs-lookup"><span data-stu-id="39442-153">Yes</span></span></p></td>
<td><p><span data-ttu-id="39442-154">发出呼叫的人的终结点使用的软件。</span><span class="sxs-lookup"><span data-stu-id="39442-154">Software used by the endpoint of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39442-155"><strong>被叫方用户代理</strong></span><span class="sxs-lookup"><span data-stu-id="39442-155"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="39442-156">是</span><span class="sxs-lookup"><span data-stu-id="39442-156">Yes</span></span></p></td>
<td><p><span data-ttu-id="39442-157">被呼叫的人的终结点使用的软件。</span><span class="sxs-lookup"><span data-stu-id="39442-157">Software used by the endpoint of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39442-158"><strong>来回行程(毫秒)</strong></span><span class="sxs-lookup"><span data-stu-id="39442-158"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="39442-159">是</span><span class="sxs-lookup"><span data-stu-id="39442-159">Yes</span></span></p></td>
<td><p><span data-ttu-id="39442-p104">实时传输协议 (RTP) 数据包来往于另一个终结点所需的平均时间量（以毫秒为单位）。来回行程的时间小于或等于 100 毫秒被视为质量可接受。</span><span class="sxs-lookup"><span data-stu-id="39442-p104">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="39442-p105">高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。</span><span class="sxs-lookup"><span data-stu-id="39442-p105">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39442-164"><strong>性能降低(MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="39442-164"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="39442-165">是</span><span class="sxs-lookup"><span data-stu-id="39442-165">Yes</span></span></p></td>
<td><p><span data-ttu-id="39442-166">呼叫过程中遇到的性能降低的平均意见得分 (MOS) 的平均值。</span><span class="sxs-lookup"><span data-stu-id="39442-166">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="39442-167">性能降低值的范围介于 0.0 和 5.0 之间。</span><span class="sxs-lookup"><span data-stu-id="39442-167">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="39442-168">该值小于或等于 0.5 表示可接受的性能降低。</span><span class="sxs-lookup"><span data-stu-id="39442-168">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="39442-169">过去，平均意见得分是通过让用户对呼叫质量进行评级（范围为 1 到 5）来计算得出的。</span><span class="sxs-lookup"><span data-stu-id="39442-169">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="39442-170">在 Lync Server 中，Lync Server 使用一组算法来预测用户对呼叫进行评级的方式。</span><span class="sxs-lookup"><span data-stu-id="39442-170">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="39442-p107">高性能降低值可能是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器或终结点超载造成的，从而导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="39442-p107">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39442-173"><strong>数据包丢失</strong></span><span class="sxs-lookup"><span data-stu-id="39442-173"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="39442-174">是</span><span class="sxs-lookup"><span data-stu-id="39442-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="39442-p108">平均 RTP 数据包丢失率。（当 RTP 数据包（一项用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时将发生数据包丢失。）高丢失率通常是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器超载造成的，从而导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="39442-p108">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39442-178"><strong>抖动</strong></span><span class="sxs-lookup"><span data-stu-id="39442-178"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="39442-179">是</span><span class="sxs-lookup"><span data-stu-id="39442-179">Yes</span></span></p></td>
<td><p><span data-ttu-id="39442-180">在 RTP 数据包到达之间检查到的平均抖动率。</span><span class="sxs-lookup"><span data-stu-id="39442-180">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="39442-181"> (抖动是 shakiness 的衡量指标 &quot; &quot; 。 ) 高抖动值通常由拥塞或过载的媒体服务器引起，并导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="39442-181">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39442-182"><strong>修复程序隐藏比率</strong></span><span class="sxs-lookup"><span data-stu-id="39442-182"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="39442-183">是</span><span class="sxs-lookup"><span data-stu-id="39442-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="39442-p110">隐藏的音频样本与样本总数的平均比率。（隐藏的音频样本是一项技术，用于消除通常由丢弃的网络数据包造成的意外转换。）高值指示数据包丢失或抖动造成的显著的丢失隐藏级别，从而导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="39442-p110">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39442-186"><strong>修复程序拉伸比率</strong></span><span class="sxs-lookup"><span data-stu-id="39442-186"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="39442-187">是</span><span class="sxs-lookup"><span data-stu-id="39442-187">Yes</span></span></p></td>
<td><p><span data-ttu-id="39442-p111">拉伸的音频样本数与样本总数的平均比率。（拉伸的音频是一类已扩展的音频，可在检测到丢弃的网络数据包时帮助保持呼叫质量。）高值指示抖动造成的显著的样本拉伸级别，从而导致音频听起来很机械或失真。</span><span class="sxs-lookup"><span data-stu-id="39442-p111">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39442-190"><strong>修复程序压缩比率</strong></span><span class="sxs-lookup"><span data-stu-id="39442-190"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="39442-191">是</span><span class="sxs-lookup"><span data-stu-id="39442-191">Yes</span></span></p></td>
<td><p><span data-ttu-id="39442-p112">压缩的音频样本与样本总数的平均比率。（压缩的音频是一类已压缩的音频，可在检测到丢弃的网络数据包时帮助保持呼叫质量。）高值指示抖动造成的显著的样本压缩级别，从而导致音频听起来像是已加速或失真。</span><span class="sxs-lookup"><span data-stu-id="39442-p112">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39442-194"><strong>连接</strong></span><span class="sxs-lookup"><span data-stu-id="39442-194"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="39442-195">是</span><span class="sxs-lookup"><span data-stu-id="39442-195">Yes</span></span></p></td>
<td><p><span data-ttu-id="39442-p113">无线通信链路的类型。通常，这是以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="39442-p113">Type of wireless communication link. Typically, this is one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="39442-198">转接</span><span class="sxs-lookup"><span data-stu-id="39442-198">Relay</span></span></p></li>
<li><p><span data-ttu-id="39442-199">直射</span><span class="sxs-lookup"><span data-stu-id="39442-199">Direct</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

