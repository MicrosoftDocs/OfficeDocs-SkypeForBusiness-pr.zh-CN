---
title: Lync Server 2013： AudioSignal 表
description: Lync Server 2013： AudioSignal 表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioSignal table
ms:assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398064(v=OCS.15)
ms:contentKeyID: 48183217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82f3b3119eaccfe56c4706cff07469bc3434461f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568758"
---
# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="595de-103">Lync Server 2013 中的 AudioSignal 表</span><span class="sxs-lookup"><span data-stu-id="595de-103">AudioSignal table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="595de-104">_**上次修改的主题：** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="595de-104">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="595de-105">每个记录表示一个终结点的音频信号指标。</span><span class="sxs-lookup"><span data-stu-id="595de-105">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="595de-106">通常情况下，每个呼叫都有两个记录，一个用于呼叫者，另一个用于被叫方。</span><span class="sxs-lookup"><span data-stu-id="595de-106">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="595de-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="595de-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="595de-108"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="595de-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="595de-109"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="595de-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="595de-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="595de-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="595de-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="595de-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="595de-112">datetime</span><span class="sxs-lookup"><span data-stu-id="595de-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="595de-113">主</span><span class="sxs-lookup"><span data-stu-id="595de-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="595de-114"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="595de-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="595de-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="595de-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="595de-116">int</span><span class="sxs-lookup"><span data-stu-id="595de-116">int</span></span></p></td>
<td><p><span data-ttu-id="595de-117">主</span><span class="sxs-lookup"><span data-stu-id="595de-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="595de-118"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="595de-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="595de-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="595de-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="595de-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="595de-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="595de-121">主</span><span class="sxs-lookup"><span data-stu-id="595de-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="595de-122"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="595de-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="595de-123"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="595de-123"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="595de-124">位</span><span class="sxs-lookup"><span data-stu-id="595de-124">bit</span></span></p></td>
<td><p><span data-ttu-id="595de-125">主</span><span class="sxs-lookup"><span data-stu-id="595de-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="595de-126">0：被调用方的数据</span><span class="sxs-lookup"><span data-stu-id="595de-126">0: Callee’s data</span></span></p>
<p><span data-ttu-id="595de-127">1：呼叫者的数据</span><span class="sxs-lookup"><span data-stu-id="595de-127">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="595de-128"><strong>SendSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="595de-128"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="595de-129">int</span><span class="sxs-lookup"><span data-stu-id="595de-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="595de-130">表示模拟后增益控制音频信号级别。</span><span class="sxs-lookup"><span data-stu-id="595de-130">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="595de-131">此指标的单位为 dBmo。</span><span class="sxs-lookup"><span data-stu-id="595de-131">The unit for this metric is dBmo.</span></span> <span data-ttu-id="595de-132">为获得可接受的质量，至少应为 30 dBmo。</span><span class="sxs-lookup"><span data-stu-id="595de-132">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="595de-133">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="595de-133">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="595de-134"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="595de-134"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="595de-135">int</span><span class="sxs-lookup"><span data-stu-id="595de-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="595de-136">请参阅 SendSignalLevel。</span><span class="sxs-lookup"><span data-stu-id="595de-136">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="595de-137"><strong>SendNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="595de-137"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="595de-138">int</span><span class="sxs-lookup"><span data-stu-id="595de-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="595de-139">表示模拟后增益控制音频噪音级别。</span><span class="sxs-lookup"><span data-stu-id="595de-139">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="595de-140">此指标的单位为 dBmo。</span><span class="sxs-lookup"><span data-stu-id="595de-140">The unit for this metric is dBmo.</span></span> <span data-ttu-id="595de-141">为获得可接受的质量，它应小于 35 dBmo。</span><span class="sxs-lookup"><span data-stu-id="595de-141">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="595de-142">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="595de-142">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="595de-143"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="595de-143"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="595de-144">int</span><span class="sxs-lookup"><span data-stu-id="595de-144">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="595de-145">请参阅 SendNoiseLevel。</span><span class="sxs-lookup"><span data-stu-id="595de-145">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="595de-146"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="595de-146"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="595de-147">int</span><span class="sxs-lookup"><span data-stu-id="595de-147">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="595de-148">回显返回丢失增强指标。</span><span class="sxs-lookup"><span data-stu-id="595de-148">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="595de-149">此指标的单位为 dB。</span><span class="sxs-lookup"><span data-stu-id="595de-149">The unit for this metric is dB.</span></span> <span data-ttu-id="595de-150">值越低表示回显越少。</span><span class="sxs-lookup"><span data-stu-id="595de-150">Lower values represent less echo.</span></span> <span data-ttu-id="595de-151">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="595de-151">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="595de-152"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="595de-152"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="595de-153">int</span><span class="sxs-lookup"><span data-stu-id="595de-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="595de-154">扬声器呈现的每5分钟平均故障。</span><span class="sxs-lookup"><span data-stu-id="595de-154">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="595de-155">为了获得较高的质量，这应小于每五分钟一次。</span><span class="sxs-lookup"><span data-stu-id="595de-155">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="595de-156">不是由 A/V 会议服务器、中介服务器或 IP 电话报告。</span><span class="sxs-lookup"><span data-stu-id="595de-156">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="595de-157"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="595de-157"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="595de-158">int</span><span class="sxs-lookup"><span data-stu-id="595de-158">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="595de-159">麦克风捕获每5分钟的平均故障。</span><span class="sxs-lookup"><span data-stu-id="595de-159">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="595de-160">若要获得较高的质量，这应小于每5分钟一次。</span><span class="sxs-lookup"><span data-stu-id="595de-160">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="595de-161">不是由 A/V 会议服务器、中介服务器或 IP 电话报告。</span><span class="sxs-lookup"><span data-stu-id="595de-161">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="595de-162"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="595de-162"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="595de-163">十进制 (9，2) </span><span class="sxs-lookup"><span data-stu-id="595de-163">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="595de-164">麦克风设备时钟相对于 CPU 时钟的速度偏移速率。</span><span class="sxs-lookup"><span data-stu-id="595de-164">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="595de-165"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="595de-165"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="595de-166">十进制 (9，2) </span><span class="sxs-lookup"><span data-stu-id="595de-166">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="595de-167">扬声器设备时钟相对于 CPU 时钟的速度偏移速率。</span><span class="sxs-lookup"><span data-stu-id="595de-167">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="595de-168"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="595de-168"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="595de-169">十进制 (9，2) </span><span class="sxs-lookup"><span data-stu-id="595de-169">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="595de-170">扬声器设备时钟相对于 CPU 时钟的速度偏移速率。</span><span class="sxs-lookup"><span data-stu-id="595de-170">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="595de-171">呼叫的最后20秒内的麦克风捕获流的平均时间戳错误（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="595de-171">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="595de-172"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="595de-172"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="595de-173">十进制 (9，2) </span><span class="sxs-lookup"><span data-stu-id="595de-173">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="595de-174">平均扬声器在呼叫的最后20秒内呈现流时间戳错误（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="595de-174">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="595de-175"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="595de-175"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="595de-176">smallint</span><span class="sxs-lookup"><span data-stu-id="595de-176">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="595de-177">Voice switch 是一个半双工模式，具有更低的中断能力。</span><span class="sxs-lookup"><span data-stu-id="595de-177">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="595de-178">语音切换条目的原因：</span><span class="sxs-lookup"><span data-stu-id="595de-178">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="595de-179">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="595de-179">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="595de-180">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="595de-180">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="595de-181">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="595de-181">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="595de-182">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="595de-182">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="595de-183">原因可能是这些独立原因的组合。</span><span class="sxs-lookup"><span data-stu-id="595de-183">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="595de-184">仅可通过 regkey 为测试目的启用 ENTER_VS_FORCEORCONVERGENCE。</span><span class="sxs-lookup"><span data-stu-id="595de-184">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="595de-185">此列的数据类型在 Microsoft Lync Server 2013 中已更改。</span><span class="sxs-lookup"><span data-stu-id="595de-185">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="595de-186"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="595de-186"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="595de-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="595de-187">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="595de-188">Echo 事件的原因：</span><span class="sxs-lookup"><span data-stu-id="595de-188">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="595de-189">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="595de-189">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="595de-190">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="595de-190">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="595de-191">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="595de-191">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="595de-192">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="595de-192">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="595de-193">ECHO_EVENT_MIC_CLIPPING 0x10</span><span class="sxs-lookup"><span data-stu-id="595de-193">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="595de-194">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="595de-194">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="595de-195">原因可能是这些独立原因的组合。</span><span class="sxs-lookup"><span data-stu-id="595de-195">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="595de-196"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="595de-196"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="595de-197">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="595de-197">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="595de-198">在麦克风捕获流中检测到回显的时间的百分比。</span><span class="sxs-lookup"><span data-stu-id="595de-198">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="595de-199">通常情况下，耳机或话机的值较低，对于扬声器电话或独立扬声器，值较高。</span><span class="sxs-lookup"><span data-stu-id="595de-199">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="595de-200">对于支持板载音频回声取消的设备，高值表示回显泄漏。</span><span class="sxs-lookup"><span data-stu-id="595de-200">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="595de-201">对于其他设备，不应使用此指标来评估设备质量。</span><span class="sxs-lookup"><span data-stu-id="595de-201">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="595de-202"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="595de-202"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="595de-203">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="595de-203">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="595de-204">在发送的流中检测到回显的时间的百分比。</span><span class="sxs-lookup"><span data-stu-id="595de-204">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="595de-205">发送流中的高回显百分比指示回声泄漏。</span><span class="sxs-lookup"><span data-stu-id="595de-205">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="595de-206"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="595de-206"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="595de-207">int</span><span class="sxs-lookup"><span data-stu-id="595de-207">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="595de-208">从网关在中介服务器上接收到的信号级别;这仅适用于中介服务器。</span><span class="sxs-lookup"><span data-stu-id="595de-208">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="595de-209">此指标的单位为 dBoV。</span><span class="sxs-lookup"><span data-stu-id="595de-209">The unit of this metric is dBoV.</span></span> <span data-ttu-id="595de-210">为了获得良好的质量，可接受范围应为 [-30 至-18] dBoV。</span><span class="sxs-lookup"><span data-stu-id="595de-210">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="595de-211"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="595de-211"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="595de-212">int</span><span class="sxs-lookup"><span data-stu-id="595de-212">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="595de-213">从网关在中介服务器上接收到的信号级别。</span><span class="sxs-lookup"><span data-stu-id="595de-213">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="595de-214">这仅适用于中介服务器。</span><span class="sxs-lookup"><span data-stu-id="595de-214">This applies only to the Mediation Server.</span></span> <span data-ttu-id="595de-215">此指标的单位为 dBoV。</span><span class="sxs-lookup"><span data-stu-id="595de-215">The unit of this metric is dBoV.</span></span> <span data-ttu-id="595de-216">为了获得良好的质量，可接受的范围应小于-50 dBoV。</span><span class="sxs-lookup"><span data-stu-id="595de-216">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="595de-217"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="595de-217"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="595de-218">int</span><span class="sxs-lookup"><span data-stu-id="595de-218">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="595de-219">中介服务器端 (AGC) 的自动增益控制。</span><span class="sxs-lookup"><span data-stu-id="595de-219">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="595de-220"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="595de-220"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="595de-221">float</span><span class="sxs-lookup"><span data-stu-id="595de-221">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="595de-222">最高为呼叫的前30秒的传入信号的根平均平方 (RMS) 。</span><span class="sxs-lookup"><span data-stu-id="595de-222">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="595de-223"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="595de-223"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="595de-224">int</span><span class="sxs-lookup"><span data-stu-id="595de-224">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="595de-225">通道1上接收的信号级别。</span><span class="sxs-lookup"><span data-stu-id="595de-225">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="595de-226">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="595de-226">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="595de-227"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="595de-227"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="595de-228">int</span><span class="sxs-lookup"><span data-stu-id="595de-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="595de-229">通道2上接收的信号级别。</span><span class="sxs-lookup"><span data-stu-id="595de-229">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="595de-230">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="595de-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="595de-231"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="595de-231"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="595de-232">int</span><span class="sxs-lookup"><span data-stu-id="595de-232">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="595de-233">频道1上接收的噪音水平。</span><span class="sxs-lookup"><span data-stu-id="595de-233">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="595de-234">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="595de-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="595de-235"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="595de-235"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="595de-236">int</span><span class="sxs-lookup"><span data-stu-id="595de-236">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="595de-237">频道2上接收的噪音水平。</span><span class="sxs-lookup"><span data-stu-id="595de-237">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="595de-238">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="595de-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="595de-239"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="595de-239"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="595de-240">int</span><span class="sxs-lookup"><span data-stu-id="595de-240">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="595de-241">通道1上发送的信号级别。</span><span class="sxs-lookup"><span data-stu-id="595de-241">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="595de-242">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="595de-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="595de-243"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="595de-243"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="595de-244">int</span><span class="sxs-lookup"><span data-stu-id="595de-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="595de-245">通道2上发送的信号级别。</span><span class="sxs-lookup"><span data-stu-id="595de-245">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="595de-246">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="595de-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="595de-247"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="595de-247"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="595de-248">int</span><span class="sxs-lookup"><span data-stu-id="595de-248">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="595de-249">频道1上发送的噪音水平。</span><span class="sxs-lookup"><span data-stu-id="595de-249">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="595de-250">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="595de-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="595de-251"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="595de-251"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="595de-252">int</span><span class="sxs-lookup"><span data-stu-id="595de-252">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="595de-253">频道2上发送的噪音水平。</span><span class="sxs-lookup"><span data-stu-id="595de-253">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="595de-254">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="595de-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

