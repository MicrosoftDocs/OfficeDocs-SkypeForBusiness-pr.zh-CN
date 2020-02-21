---
title: Lync Server 2013：呼叫详细信息报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Detail Report
ms:assetid: 38862e35-3fec-41b9-a035-0b301942d446
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558637(v=OCS.15)
ms:contentKeyID: 48183843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb57cde990e4c4218297c69aeb3c8933f9a3fd92
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196365"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-detail-report-in-lync-server-2013"></a><span data-ttu-id="5feaa-102">Lync Server 2013 中的呼叫详细信息报告</span><span class="sxs-lookup"><span data-stu-id="5feaa-102">Call Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5feaa-103">_**上次修改的主题：** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="5feaa-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="5feaa-104">呼叫详细信息报告提供了单个呼叫的详细介绍;报告包括几乎所有的经验指标和由 Lync Server 收集的统计信息，分为以下报告部分：</span><span class="sxs-lookup"><span data-stu-id="5feaa-104">The Call Detail Report provides a detailed look at an individual call; the report includes nearly all the Quality of Experience metrics and statistics collected by Lync Server, divided into report sections such as:</span></span>

  - <span data-ttu-id="5feaa-105">呼叫信息</span><span class="sxs-lookup"><span data-stu-id="5feaa-105">Call Information</span></span>

  - <span data-ttu-id="5feaa-106">呼叫者设备和信号指标</span><span class="sxs-lookup"><span data-stu-id="5feaa-106">Caller Device and Signal Metrics</span></span>

  - <span data-ttu-id="5feaa-107">被叫方设备和信号指标</span><span class="sxs-lookup"><span data-stu-id="5feaa-107">Callee Device and Signal metrics</span></span>

  - <span data-ttu-id="5feaa-108">呼叫者客户端事件</span><span class="sxs-lookup"><span data-stu-id="5feaa-108">Caller Client Event</span></span>

  - <span data-ttu-id="5feaa-109">被叫方客户端事件</span><span class="sxs-lookup"><span data-stu-id="5feaa-109">Callee Client Event</span></span>

  - <span data-ttu-id="5feaa-110">音频流（呼叫者到被叫方）</span><span class="sxs-lookup"><span data-stu-id="5feaa-110">Audio Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="5feaa-111">视频流（呼叫者到被叫方）</span><span class="sxs-lookup"><span data-stu-id="5feaa-111">Video Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="5feaa-112">视频流（被叫方到呼叫者）</span><span class="sxs-lookup"><span data-stu-id="5feaa-112">Audio Stream (Callee to Caller)</span></span>

  - <span data-ttu-id="5feaa-113">视频流（被叫方到呼叫者）</span><span class="sxs-lookup"><span data-stu-id="5feaa-113">Video Stream (Callee to Caller)</span></span>

<span data-ttu-id="5feaa-p101">请记住，您在指定报告上看到的类别和指标取决于两个因素：会话类型和会话中使用的终结点类型。例如，纯音频呼叫不会报告视频流的相关指标；这是因为该呼叫没有视频流。同样，您的报告可能列出了呼叫者统计信息，而没有列出被叫方统计信息。这通常是因为被叫方没有使用符合 SIP 的设备。终结点负责在呼叫结束时报告统计信息；但是，移动电话（不了解有关 SIP 或 SIP 统计信息的任何情况）无法报告此类信息。如果您呼叫某人且此人用其移动电话应答您的呼叫，则呼叫结束时您将不会获得来自该移动电话的报告。</span><span class="sxs-lookup"><span data-stu-id="5feaa-p101">Keep in mind that the categories and the metrics you see on a given report depend on two things: the type of session and the type of endpoints used in the session. For example, an audio-only call will not report metrics for video streams; that's because the call didn't have a video stream. Likewise, you might have a report that lists caller statistics but not callee statistics. That's typically because the callee was not using a SIP-compliant device. Endpoints are responsible for reporting statistics at the end of a call; however, a cell phone (which knows nothing about SIP or SIP statistics) is unable to report that kind of information. If you call someone and they answer you on their cell phone, you will not get a report from that cell phone when the call ends.</span></span>

<span data-ttu-id="5feaa-120">呼叫详情报告在您尝试准确确定指定呼叫遇到媒体质量问题的原因时最为有用。</span><span class="sxs-lookup"><span data-stu-id="5feaa-120">The Call Detail Report is most useful when you are trying to determine exactly why a given call experienced media quality problems.</span></span>

<div>

## <a name="accessing-the-call-detail-report"></a><span data-ttu-id="5feaa-121">访问呼叫详情报告</span><span class="sxs-lookup"><span data-stu-id="5feaa-121">Accessing the Call Detail Report</span></span>

<span data-ttu-id="5feaa-122">可以从下列任意报告中访问呼叫详情报告：</span><span class="sxs-lookup"><span data-stu-id="5feaa-122">The Call Detail Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="5feaa-123">[Lync Server 2013 中的位置报告](lync-server-2013-location-report.md)（单击 "呼叫量" 或 "较差呼叫百分比" 指标）</span><span class="sxs-lookup"><span data-stu-id="5feaa-123">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking either the Call volume or the Poor call percentage metric)</span></span>

  - <span data-ttu-id="5feaa-124">[Lync Server 2013 中的媒体质量摘要报告](lync-server-2013-media-quality-summary-report.md)（通过单击 "呼叫量" 或 "不良呼叫百分比" 指标）</span><span class="sxs-lookup"><span data-stu-id="5feaa-124">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="5feaa-125">[Lync server 2013 中的媒体质量比较报告](lync-server-2013-media-quality-comparison-report.md)（通过单击[lync server 2013 中的呼叫列表报告](lync-server-2013-call-list-report.md)，然后单击详细信息指标）。</span><span class="sxs-lookup"><span data-stu-id="5feaa-125">The [Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md) (by clicking the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) and then clicking the Detail metric).</span></span>

  - <span data-ttu-id="5feaa-126">[Lync server 2013 中的服务器性能报告](lync-server-2013-server-performance-report.md)（单击 "呼叫量" 或 "较差的呼叫百分比" 指标）</span><span class="sxs-lookup"><span data-stu-id="5feaa-126">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="5feaa-127">[Lync Server 2013 中的呼叫列表报告](lync-server-2013-call-list-report.md)（通过单击 "详细信息" 指标）</span><span class="sxs-lookup"><span data-stu-id="5feaa-127">The [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) (by clicking the Detail metric)</span></span>

<span data-ttu-id="5feaa-128">从呼叫详细信息报告中，可通过单击以下任一指标[在 Lync Server 2013 中访问设备报告](lync-server-2013-device-report.md)：</span><span class="sxs-lookup"><span data-stu-id="5feaa-128">From within the Call Detail Report you can access the [Device Report in Lync Server 2013](lync-server-2013-device-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="5feaa-129">捕获设备</span><span class="sxs-lookup"><span data-stu-id="5feaa-129">Capture device</span></span>

  - <span data-ttu-id="5feaa-130">呈现设备</span><span class="sxs-lookup"><span data-stu-id="5feaa-130">Render device</span></span>

<span data-ttu-id="5feaa-131">您还可以通过单击“A/V 边缘服务器”指标访问服务器媒体质量趋势报告。</span><span class="sxs-lookup"><span data-stu-id="5feaa-131">You can also access the Server Media Quality Trend Report by clicking the A/V edge server metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-detail-report"></a><span data-ttu-id="5feaa-132">充分利用呼叫详情报告</span><span class="sxs-lookup"><span data-stu-id="5feaa-132">Making the Best Use of the Call Detail Report</span></span>

<span data-ttu-id="5feaa-p102">呼叫详情报告通常包括 250 多个不同的指标，其中包括麦克风时间戳偏移、低 SNR 时间和近端回声时间等项目。如果您不记得所有这些指标实际度量的内容，请尝试将鼠标指针置于指标标签上方；通常，将显示描述该指标的工具提示。</span><span class="sxs-lookup"><span data-stu-id="5feaa-p102">The Call Detail Report typically includes over 250 different metrics, including such items as Microphone timestamp drift, Low SNR time, and Near end to echo time. If you can't remember what all of these metrics actually measure, try holding your mouse over the metric label; often-times, a tooltip will appear describing that metric.</span></span>

<span data-ttu-id="5feaa-p103">如果查找指标时遇到问题，请在搜索框中键入指标标签的部分内容，然后单击“查找”。例如，如果您无法找到“低 SNR 时间”指标，请在搜索框中键入“SNR”，然后单击“查找”。</span><span class="sxs-lookup"><span data-stu-id="5feaa-p103">If you have problems locating a metric, type part of the metric label in the search box and then click Find. For example, if you can't find the Low SNR time metric, type SNR in the search box and then click Find.</span></span>

<span data-ttu-id="5feaa-137">请注意，报告仅跟踪有关呼叫的信息。</span><span class="sxs-lookup"><span data-stu-id="5feaa-137">Note that the report only tracks information about a call.</span></span> <span data-ttu-id="5feaa-138">不记录呼叫本身。</span><span class="sxs-lookup"><span data-stu-id="5feaa-138">The call itself is not recorded.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="5feaa-139">筛选器</span><span class="sxs-lookup"><span data-stu-id="5feaa-139">Filters</span></span>

<span data-ttu-id="5feaa-p105">无。您无法筛选呼叫详情报告。</span><span class="sxs-lookup"><span data-stu-id="5feaa-p105">None. You cannot filter the Call Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="5feaa-142">指标</span><span class="sxs-lookup"><span data-stu-id="5feaa-142">Metrics</span></span>

<span data-ttu-id="5feaa-143">下表列出了每个呼叫的呼叫详情报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="5feaa-143">The following table lists the information provided in the Call Detail Report for each call.</span></span>

### <a name="call-detail-report-metrics"></a><span data-ttu-id="5feaa-144">呼叫详情报告指标</span><span class="sxs-lookup"><span data-stu-id="5feaa-144">Call Detail Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5feaa-145">名称</span><span class="sxs-lookup"><span data-stu-id="5feaa-145">Name</span></span></th>
<th><span data-ttu-id="5feaa-146">是否可按此项排序？</span><span class="sxs-lookup"><span data-stu-id="5feaa-146">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="5feaa-147">说明</span><span class="sxs-lookup"><span data-stu-id="5feaa-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5feaa-148"><strong>呼叫者 PAI</strong></span><span class="sxs-lookup"><span data-stu-id="5feaa-148"><strong>Caller PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="5feaa-149">否</span><span class="sxs-lookup"><span data-stu-id="5feaa-149">No</span></span></p></td>
<td><p><span data-ttu-id="5feaa-p106">发起呼叫的用户的 P-Asserted-Identity。P-Asserted-Identity 用于传达受信任网络内用户经验证的身份。</span><span class="sxs-lookup"><span data-stu-id="5feaa-p106">P-Asserted-Identity of the user who initiated the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5feaa-152"><strong>呼叫者 URI</strong></span><span class="sxs-lookup"><span data-stu-id="5feaa-152"><strong>Caller URI</strong></span></span></p></td>
<td><p><span data-ttu-id="5feaa-153">否</span><span class="sxs-lookup"><span data-stu-id="5feaa-153">No</span></span></p></td>
<td><p><span data-ttu-id="5feaa-154">发起呼叫的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="5feaa-154">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5feaa-155"><strong>呼叫者终结点</strong></span><span class="sxs-lookup"><span data-stu-id="5feaa-155"><strong>Caller endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="5feaa-156">否</span><span class="sxs-lookup"><span data-stu-id="5feaa-156">No</span></span></p></td>
<td><p><span data-ttu-id="5feaa-157">用于发出呼叫的设备。</span><span class="sxs-lookup"><span data-stu-id="5feaa-157">Device used to make the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5feaa-158"><strong>呼叫者用户代理</strong></span><span class="sxs-lookup"><span data-stu-id="5feaa-158"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="5feaa-159">否</span><span class="sxs-lookup"><span data-stu-id="5feaa-159">No</span></span></p></td>
<td><p><span data-ttu-id="5feaa-160">发出呼叫的设备上使用的软件。</span><span class="sxs-lookup"><span data-stu-id="5feaa-160">Software used on the device that made the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5feaa-161"><strong>呼叫开始</strong></span><span class="sxs-lookup"><span data-stu-id="5feaa-161"><strong>Call start</strong></span></span></p></td>
<td><p><span data-ttu-id="5feaa-162">否</span><span class="sxs-lookup"><span data-stu-id="5feaa-162">No</span></span></p></td>
<td><p><span data-ttu-id="5feaa-163">最初发出呼叫的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="5feaa-163">Date and time that the call was initially placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5feaa-164"><strong>中介服务器旁路呼叫</strong></span><span class="sxs-lookup"><span data-stu-id="5feaa-164"><strong>Mediation Server bypass call</strong></span></span></p></td>
<td><p><span data-ttu-id="5feaa-165">否</span><span class="sxs-lookup"><span data-stu-id="5feaa-165">No</span></span></p></td>
<td><p><span data-ttu-id="5feaa-166">指示呼叫是否在不通过中介服务器的情况下连接到 PSTN 语音网关或合格的 IP-PBX。</span><span class="sxs-lookup"><span data-stu-id="5feaa-166">Indicates whether the call connected to a PSTN voice gateway or qualified IP-PBX without passing through the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5feaa-167"><strong>呼叫者 OS</strong></span><span class="sxs-lookup"><span data-stu-id="5feaa-167"><strong>Caller OS</strong></span></span></p></td>
<td><p><span data-ttu-id="5feaa-168">否</span><span class="sxs-lookup"><span data-stu-id="5feaa-168">No</span></span></p></td>
<td><p><span data-ttu-id="5feaa-169">呼叫者计算机的操作系统。</span><span class="sxs-lookup"><span data-stu-id="5feaa-169">Operating system of the caller's computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5feaa-170"><strong>呼叫者 CPU</strong></span><span class="sxs-lookup"><span data-stu-id="5feaa-170"><strong>Caller CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="5feaa-171">否</span><span class="sxs-lookup"><span data-stu-id="5feaa-171">No</span></span></p></td>
<td><p><span data-ttu-id="5feaa-172">发起呼叫的用户的计算机中安装的 CPU。</span><span class="sxs-lookup"><span data-stu-id="5feaa-172">CPU installed in the computer of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5feaa-173"><strong>呼叫者 CPU 内核数</strong></span><span class="sxs-lookup"><span data-stu-id="5feaa-173"><strong>Caller CPU core number</strong></span></span></p></td>
<td><p><span data-ttu-id="5feaa-174">否</span><span class="sxs-lookup"><span data-stu-id="5feaa-174">No</span></span></p></td>
<td><p><span data-ttu-id="5feaa-175">发起呼叫的人员使用的计算机中的处理器数量。</span><span class="sxs-lookup"><span data-stu-id="5feaa-175">Processor number in the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5feaa-176"><strong>呼叫者 CPU 速度</strong></span><span class="sxs-lookup"><span data-stu-id="5feaa-176"><strong>Caller CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="5feaa-177">否</span><span class="sxs-lookup"><span data-stu-id="5feaa-177">No</span></span></p></td>
<td><p><span data-ttu-id="5feaa-178">发起呼叫的人员使用的计算机的 CPU 时钟频率。</span><span class="sxs-lookup"><span data-stu-id="5feaa-178">Clock speed of the CPU of the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5feaa-179"><strong>呼叫者 CPU 虚拟化</strong></span><span class="sxs-lookup"><span data-stu-id="5feaa-179"><strong>Caller CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="5feaa-180">否</span><span class="sxs-lookup"><span data-stu-id="5feaa-180">No</span></span></p></td>
<td><p><span data-ttu-id="5feaa-181">发起呼叫的人员使用的计算机上使用的虚拟化（如果有）。</span><span class="sxs-lookup"><span data-stu-id="5feaa-181">Virtualization (if any) used on the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5feaa-182"><strong>被叫方 PAI</strong></span><span class="sxs-lookup"><span data-stu-id="5feaa-182"><strong>Callee PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="5feaa-183">否</span><span class="sxs-lookup"><span data-stu-id="5feaa-183">No</span></span></p></td>
<td><p><span data-ttu-id="5feaa-p107">受邀加入呼叫的用户的 P-Asserted-Identity。P-Asserted-Identity 用于传达受信任网络内用户经验证的身份。</span><span class="sxs-lookup"><span data-stu-id="5feaa-p107">P-Asserted-Identity of the user who was invited to join the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5feaa-186"><strong>被叫方 URI</strong></span><span class="sxs-lookup"><span data-stu-id="5feaa-186"><strong>Callee URI</strong></span></span></p></td>
<td><p><span data-ttu-id="5feaa-187">否</span><span class="sxs-lookup"><span data-stu-id="5feaa-187">No</span></span></p></td>
<td><p><span data-ttu-id="5feaa-188">被叫的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="5feaa-188">SIP address of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5feaa-189"><strong>被叫方终结点</strong></span><span class="sxs-lookup"><span data-stu-id="5feaa-189"><strong>Callee endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="5feaa-190">否</span><span class="sxs-lookup"><span data-stu-id="5feaa-190">No</span></span></p></td>
<td><p><span data-ttu-id="5feaa-191">用于接收呼叫的设备。</span><span class="sxs-lookup"><span data-stu-id="5feaa-191">Device used to receive the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5feaa-192"><strong>被叫方用户代理</strong></span><span class="sxs-lookup"><span data-stu-id="5feaa-192"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="5feaa-193">否</span><span class="sxs-lookup"><span data-stu-id="5feaa-193">No</span></span></p></td>
<td><p><span data-ttu-id="5feaa-194">接收呼叫的设备上使用的软件。</span><span class="sxs-lookup"><span data-stu-id="5feaa-194">Software used on the device that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5feaa-195"><strong>Duration</strong></span><span class="sxs-lookup"><span data-stu-id="5feaa-195"><strong>Duration</strong></span></span></p></td>
<td><p><span data-ttu-id="5feaa-196">否</span><span class="sxs-lookup"><span data-stu-id="5feaa-196">No</span></span></p></td>
<td><p><span data-ttu-id="5feaa-197">呼叫的时长。</span><span class="sxs-lookup"><span data-stu-id="5feaa-197">Length of time for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5feaa-198"><strong>媒体旁路警告标记</strong></span><span class="sxs-lookup"><span data-stu-id="5feaa-198"><strong>Media bypass warning flag</strong></span></span></p></td>
<td><p><span data-ttu-id="5feaa-199">否</span><span class="sxs-lookup"><span data-stu-id="5feaa-199">No</span></span></p></td>
<td><p><span data-ttu-id="5feaa-200">在绕过中介服务器时发出的警告。</span><span class="sxs-lookup"><span data-stu-id="5feaa-200">Warning issued when the Mediation Server was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5feaa-201"><strong>被叫方 OS</strong></span><span class="sxs-lookup"><span data-stu-id="5feaa-201"><strong>Callee OS</strong></span></span></p></td>
<td><p><span data-ttu-id="5feaa-202">否</span><span class="sxs-lookup"><span data-stu-id="5feaa-202">No</span></span></p></td>
<td><p><span data-ttu-id="5feaa-203">被叫用户的计算机的操作系统。</span><span class="sxs-lookup"><span data-stu-id="5feaa-203">Operating system of the computer for the user who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5feaa-204"><strong>被叫方 CPU</strong></span><span class="sxs-lookup"><span data-stu-id="5feaa-204"><strong>Callee CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="5feaa-205">否</span><span class="sxs-lookup"><span data-stu-id="5feaa-205">No</span></span></p></td>
<td><p><span data-ttu-id="5feaa-206">被叫用户的计算机中安装的 CPU。</span><span class="sxs-lookup"><span data-stu-id="5feaa-206">CPU installed in the computer of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5feaa-207"><strong>被叫方内核数</strong></span><span class="sxs-lookup"><span data-stu-id="5feaa-207"><strong>Callee core number</strong></span></span></p></td>
<td><p><span data-ttu-id="5feaa-208">否</span><span class="sxs-lookup"><span data-stu-id="5feaa-208">No</span></span></p></td>
<td><p><span data-ttu-id="5feaa-209">被叫人员使用的计算机中的处理器数量。</span><span class="sxs-lookup"><span data-stu-id="5feaa-209">Processor number in the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5feaa-210"><strong>被叫方 CPU 速度</strong></span><span class="sxs-lookup"><span data-stu-id="5feaa-210"><strong>Callee CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="5feaa-211">否</span><span class="sxs-lookup"><span data-stu-id="5feaa-211">No</span></span></p></td>
<td><p><span data-ttu-id="5feaa-212">被叫人员使用的计算机的 CPU 时钟频率。</span><span class="sxs-lookup"><span data-stu-id="5feaa-212">Clock speed of the CPU of the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5feaa-213"><strong>被叫方 CPU 虚拟化</strong></span><span class="sxs-lookup"><span data-stu-id="5feaa-213"><strong>Callee CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="5feaa-214">否</span><span class="sxs-lookup"><span data-stu-id="5feaa-214">No</span></span></p></td>
<td><p><span data-ttu-id="5feaa-215">被叫人员使用的计算机上使用的虚拟化（如果有）。</span><span class="sxs-lookup"><span data-stu-id="5feaa-215">Virtualization (if any) used on the computer used by the person who was called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

