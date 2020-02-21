---
title: Lync Server 2013： AudioSignal 表
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
ms.openlocfilehash: de07393ef9f43346d0c1b4c96dcfdcf33f00513a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="1a36c-102">Lync Server 2013 中的 AudioSignal 表</span><span class="sxs-lookup"><span data-stu-id="1a36c-102">AudioSignal table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a36c-103">_**上次修改的主题：** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="1a36c-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="1a36c-104">每个记录表示一个终结点的音频信号指标。</span><span class="sxs-lookup"><span data-stu-id="1a36c-104">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="1a36c-105">通常情况下，每个呼叫都有两个记录，一个用于呼叫者，另一个用于被叫方。</span><span class="sxs-lookup"><span data-stu-id="1a36c-105">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1a36c-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="1a36c-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="1a36c-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="1a36c-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1a36c-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1a36c-111">datetime</span><span class="sxs-lookup"><span data-stu-id="1a36c-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="1a36c-112">主</span><span class="sxs-lookup"><span data-stu-id="1a36c-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="1a36c-113"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="1a36c-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a36c-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1a36c-115">int</span><span class="sxs-lookup"><span data-stu-id="1a36c-115">int</span></span></p></td>
<td><p><span data-ttu-id="1a36c-116">主</span><span class="sxs-lookup"><span data-stu-id="1a36c-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="1a36c-117"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="1a36c-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a36c-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="1a36c-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="1a36c-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="1a36c-120">主</span><span class="sxs-lookup"><span data-stu-id="1a36c-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="1a36c-121"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="1a36c-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a36c-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="1a36c-123">位</span><span class="sxs-lookup"><span data-stu-id="1a36c-123">bit</span></span></p></td>
<td><p><span data-ttu-id="1a36c-124">主</span><span class="sxs-lookup"><span data-stu-id="1a36c-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="1a36c-125">0：被调用方的数据</span><span class="sxs-lookup"><span data-stu-id="1a36c-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="1a36c-126">1：呼叫者的数据</span><span class="sxs-lookup"><span data-stu-id="1a36c-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a36c-127"><strong>SendSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-127"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="1a36c-128">int</span><span class="sxs-lookup"><span data-stu-id="1a36c-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1a36c-129">表示模拟后增益控制音频信号级别。</span><span class="sxs-lookup"><span data-stu-id="1a36c-129">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="1a36c-130">此指标的单位为 dBmo。</span><span class="sxs-lookup"><span data-stu-id="1a36c-130">The unit for this metric is dBmo.</span></span> <span data-ttu-id="1a36c-131">为获得可接受的质量，至少应为 30 dBmo。</span><span class="sxs-lookup"><span data-stu-id="1a36c-131">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="1a36c-132">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="1a36c-132">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a36c-133"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-133"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="1a36c-134">int</span><span class="sxs-lookup"><span data-stu-id="1a36c-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1a36c-135">请参阅 SendSignalLevel。</span><span class="sxs-lookup"><span data-stu-id="1a36c-135">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a36c-136"><strong>SendNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-136"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="1a36c-137">int</span><span class="sxs-lookup"><span data-stu-id="1a36c-137">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1a36c-138">表示模拟后增益控制音频噪音级别。</span><span class="sxs-lookup"><span data-stu-id="1a36c-138">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="1a36c-139">此指标的单位为 dBmo。</span><span class="sxs-lookup"><span data-stu-id="1a36c-139">The unit for this metric is dBmo.</span></span> <span data-ttu-id="1a36c-140">为获得可接受的质量，它应小于 35 dBmo。</span><span class="sxs-lookup"><span data-stu-id="1a36c-140">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="1a36c-141">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="1a36c-141">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a36c-142"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-142"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="1a36c-143">int</span><span class="sxs-lookup"><span data-stu-id="1a36c-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1a36c-144">请参阅 SendNoiseLevel。</span><span class="sxs-lookup"><span data-stu-id="1a36c-144">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a36c-145"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-145"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="1a36c-146">int</span><span class="sxs-lookup"><span data-stu-id="1a36c-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1a36c-147">回显返回丢失增强指标。</span><span class="sxs-lookup"><span data-stu-id="1a36c-147">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="1a36c-148">此指标的单位为 dB。</span><span class="sxs-lookup"><span data-stu-id="1a36c-148">The unit for this metric is dB.</span></span> <span data-ttu-id="1a36c-149">值越低表示回显越少。</span><span class="sxs-lookup"><span data-stu-id="1a36c-149">Lower values represent less echo.</span></span> <span data-ttu-id="1a36c-150">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="1a36c-150">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a36c-151"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-151"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="1a36c-152">int</span><span class="sxs-lookup"><span data-stu-id="1a36c-152">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1a36c-153">扬声器呈现的每5分钟平均故障。</span><span class="sxs-lookup"><span data-stu-id="1a36c-153">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="1a36c-154">为了获得较高的质量，这应小于每五分钟一次。</span><span class="sxs-lookup"><span data-stu-id="1a36c-154">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="1a36c-155">不是由 A/V 会议服务器、中介服务器或 IP 电话报告。</span><span class="sxs-lookup"><span data-stu-id="1a36c-155">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a36c-156"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-156"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="1a36c-157">int</span><span class="sxs-lookup"><span data-stu-id="1a36c-157">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1a36c-158">麦克风捕获每5分钟的平均故障。</span><span class="sxs-lookup"><span data-stu-id="1a36c-158">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="1a36c-159">若要获得较高的质量，这应小于每5分钟一次。</span><span class="sxs-lookup"><span data-stu-id="1a36c-159">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="1a36c-160">不是由 A/V 会议服务器、中介服务器或 IP 电话报告。</span><span class="sxs-lookup"><span data-stu-id="1a36c-160">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a36c-161"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-161"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="1a36c-162">小数（9，2）</span><span class="sxs-lookup"><span data-stu-id="1a36c-162">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1a36c-163">麦克风设备时钟相对于 CPU 时钟的速度偏移速率。</span><span class="sxs-lookup"><span data-stu-id="1a36c-163">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a36c-164"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-164"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="1a36c-165">小数（9，2）</span><span class="sxs-lookup"><span data-stu-id="1a36c-165">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1a36c-166">扬声器设备时钟相对于 CPU 时钟的速度偏移速率。</span><span class="sxs-lookup"><span data-stu-id="1a36c-166">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a36c-167"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-167"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="1a36c-168">小数（9，2）</span><span class="sxs-lookup"><span data-stu-id="1a36c-168">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1a36c-169">扬声器设备时钟相对于 CPU 时钟的速度偏移速率。</span><span class="sxs-lookup"><span data-stu-id="1a36c-169">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="1a36c-170">呼叫的最后20秒内的麦克风捕获流的平均时间戳错误（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="1a36c-170">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a36c-171"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-171"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="1a36c-172">小数（9，2）</span><span class="sxs-lookup"><span data-stu-id="1a36c-172">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1a36c-173">平均扬声器在呼叫的最后20秒内呈现流时间戳错误（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="1a36c-173">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a36c-174"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-174"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="1a36c-175">smallint</span><span class="sxs-lookup"><span data-stu-id="1a36c-175">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1a36c-176">Voice switch 是一个半双工模式，具有更低的中断能力。</span><span class="sxs-lookup"><span data-stu-id="1a36c-176">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="1a36c-177">语音切换条目的原因：</span><span class="sxs-lookup"><span data-stu-id="1a36c-177">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="1a36c-178">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="1a36c-178">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="1a36c-179">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="1a36c-179">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="1a36c-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="1a36c-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="1a36c-181">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="1a36c-181">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="1a36c-182">原因可能是这些独立原因的组合。</span><span class="sxs-lookup"><span data-stu-id="1a36c-182">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="1a36c-183">仅可通过 regkey 为测试目的启用 ENTER_VS_FORCEORCONVERGENCE。</span><span class="sxs-lookup"><span data-stu-id="1a36c-183">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="1a36c-184">此列的数据类型在 Microsoft Lync Server 2013 中已更改。</span><span class="sxs-lookup"><span data-stu-id="1a36c-184">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a36c-185"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-185"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="1a36c-186">tinyint</span><span class="sxs-lookup"><span data-stu-id="1a36c-186">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1a36c-187">Echo 事件的原因：</span><span class="sxs-lookup"><span data-stu-id="1a36c-187">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="1a36c-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="1a36c-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="1a36c-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="1a36c-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="1a36c-190">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="1a36c-190">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="1a36c-191">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="1a36c-191">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="1a36c-192">ECHO_EVENT_MIC_CLIPPING 0x10</span><span class="sxs-lookup"><span data-stu-id="1a36c-192">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="1a36c-193">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="1a36c-193">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="1a36c-194">原因可能是这些独立原因的组合。</span><span class="sxs-lookup"><span data-stu-id="1a36c-194">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a36c-195"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-195"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="1a36c-196">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="1a36c-196">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1a36c-197">在麦克风捕获流中检测到回显的时间的百分比。</span><span class="sxs-lookup"><span data-stu-id="1a36c-197">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="1a36c-198">通常情况下，耳机或话机的值较低，对于扬声器电话或独立扬声器，值较高。</span><span class="sxs-lookup"><span data-stu-id="1a36c-198">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="1a36c-199">对于支持板载音频回声取消的设备，高值表示回显泄漏。</span><span class="sxs-lookup"><span data-stu-id="1a36c-199">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="1a36c-200">对于其他设备，不应使用此指标来评估设备质量。</span><span class="sxs-lookup"><span data-stu-id="1a36c-200">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a36c-201"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-201"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="1a36c-202">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="1a36c-202">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1a36c-203">在发送的流中检测到回显的时间的百分比。</span><span class="sxs-lookup"><span data-stu-id="1a36c-203">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="1a36c-204">发送流中的高回显百分比指示回声泄漏。</span><span class="sxs-lookup"><span data-stu-id="1a36c-204">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a36c-205"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-205"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="1a36c-206">int</span><span class="sxs-lookup"><span data-stu-id="1a36c-206">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1a36c-207">从网关在中介服务器上接收到的信号级别;这仅适用于中介服务器。</span><span class="sxs-lookup"><span data-stu-id="1a36c-207">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="1a36c-208">此指标的单位为 dBoV。</span><span class="sxs-lookup"><span data-stu-id="1a36c-208">The unit of this metric is dBoV.</span></span> <span data-ttu-id="1a36c-209">为了获得良好的质量，可接受范围应为 [-30 至-18] dBoV。</span><span class="sxs-lookup"><span data-stu-id="1a36c-209">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a36c-210"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-210"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="1a36c-211">int</span><span class="sxs-lookup"><span data-stu-id="1a36c-211">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1a36c-212">从网关在中介服务器上接收到的信号级别。</span><span class="sxs-lookup"><span data-stu-id="1a36c-212">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="1a36c-213">这仅适用于中介服务器。</span><span class="sxs-lookup"><span data-stu-id="1a36c-213">This applies only to the Mediation Server.</span></span> <span data-ttu-id="1a36c-214">此指标的单位为 dBoV。</span><span class="sxs-lookup"><span data-stu-id="1a36c-214">The unit of this metric is dBoV.</span></span> <span data-ttu-id="1a36c-215">为了获得良好的质量，可接受的范围应小于-50 dBoV。</span><span class="sxs-lookup"><span data-stu-id="1a36c-215">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a36c-216"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-216"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="1a36c-217">int</span><span class="sxs-lookup"><span data-stu-id="1a36c-217">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1a36c-218">中介服务器端的自动增益控制（AGC）。</span><span class="sxs-lookup"><span data-stu-id="1a36c-218">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a36c-219"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-219"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="1a36c-220">点数</span><span class="sxs-lookup"><span data-stu-id="1a36c-220">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1a36c-221">呼叫的前30秒内传入信号的根平均平方（RMS）。</span><span class="sxs-lookup"><span data-stu-id="1a36c-221">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a36c-222"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-222"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="1a36c-223">int</span><span class="sxs-lookup"><span data-stu-id="1a36c-223">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1a36c-224">通道1上接收的信号级别。</span><span class="sxs-lookup"><span data-stu-id="1a36c-224">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="1a36c-225">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="1a36c-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a36c-226"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-226"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="1a36c-227">int</span><span class="sxs-lookup"><span data-stu-id="1a36c-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1a36c-228">通道2上接收的信号级别。</span><span class="sxs-lookup"><span data-stu-id="1a36c-228">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="1a36c-229">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="1a36c-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a36c-230"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-230"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="1a36c-231">int</span><span class="sxs-lookup"><span data-stu-id="1a36c-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1a36c-232">频道1上接收的噪音水平。</span><span class="sxs-lookup"><span data-stu-id="1a36c-232">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="1a36c-233">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="1a36c-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a36c-234"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-234"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="1a36c-235">int</span><span class="sxs-lookup"><span data-stu-id="1a36c-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1a36c-236">频道2上接收的噪音水平。</span><span class="sxs-lookup"><span data-stu-id="1a36c-236">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="1a36c-237">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="1a36c-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a36c-238"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-238"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="1a36c-239">int</span><span class="sxs-lookup"><span data-stu-id="1a36c-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1a36c-240">通道1上发送的信号级别。</span><span class="sxs-lookup"><span data-stu-id="1a36c-240">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="1a36c-241">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="1a36c-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a36c-242"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-242"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="1a36c-243">int</span><span class="sxs-lookup"><span data-stu-id="1a36c-243">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1a36c-244">通道2上发送的信号级别。</span><span class="sxs-lookup"><span data-stu-id="1a36c-244">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="1a36c-245">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="1a36c-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a36c-246"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-246"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="1a36c-247">int</span><span class="sxs-lookup"><span data-stu-id="1a36c-247">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1a36c-248">频道1上发送的噪音水平。</span><span class="sxs-lookup"><span data-stu-id="1a36c-248">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="1a36c-249">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="1a36c-249">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a36c-250"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="1a36c-250"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="1a36c-251">int</span><span class="sxs-lookup"><span data-stu-id="1a36c-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1a36c-252">频道2上发送的噪音水平。</span><span class="sxs-lookup"><span data-stu-id="1a36c-252">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="1a36c-253">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="1a36c-253">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

