---
title: Lync Server 2013：AudioSignal 表
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
ms.openlocfilehash: 950c8457f80c69af5875064fff55c5ac7df61b24
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="44736-102">Lync Server 2013 中的 AudioSignal 表</span><span class="sxs-lookup"><span data-stu-id="44736-102">AudioSignal table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44736-103">_**主题上次修改时间：** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="44736-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="44736-104">每条记录表示一个终结点的音频信号指标。</span><span class="sxs-lookup"><span data-stu-id="44736-104">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="44736-105">通常，每个通话都有两条记录，一个用于呼叫方，另一个用于被呼叫方。</span><span class="sxs-lookup"><span data-stu-id="44736-105">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="44736-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="44736-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="44736-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="44736-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="44736-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="44736-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="44736-109"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="44736-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44736-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="44736-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="44736-111">datetime</span><span class="sxs-lookup"><span data-stu-id="44736-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="44736-112">Primary</span><span class="sxs-lookup"><span data-stu-id="44736-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="44736-113">从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="44736-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44736-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="44736-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="44736-115">int</span><span class="sxs-lookup"><span data-stu-id="44736-115">int</span></span></p></td>
<td><p><span data-ttu-id="44736-116">Primary</span><span class="sxs-lookup"><span data-stu-id="44736-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="44736-117">从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="44736-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44736-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="44736-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="44736-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="44736-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="44736-120">Primary</span><span class="sxs-lookup"><span data-stu-id="44736-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="44736-121">从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="44736-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44736-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="44736-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="44736-123">bit</span><span class="sxs-lookup"><span data-stu-id="44736-123">bit</span></span></p></td>
<td><p><span data-ttu-id="44736-124">Primary</span><span class="sxs-lookup"><span data-stu-id="44736-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="44736-125">0：被调用方的数据</span><span class="sxs-lookup"><span data-stu-id="44736-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="44736-126">1：调用方的数据</span><span class="sxs-lookup"><span data-stu-id="44736-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44736-127"><strong>SendSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="44736-127"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="44736-128">int</span><span class="sxs-lookup"><span data-stu-id="44736-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="44736-129">表示模拟后增益控制音频信号级别。</span><span class="sxs-lookup"><span data-stu-id="44736-129">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="44736-130">此指标的单位为 dBmo。</span><span class="sxs-lookup"><span data-stu-id="44736-130">The unit for this metric is dBmo.</span></span> <span data-ttu-id="44736-131">为获得可接受的质量，它至少应为 30 dBmo。</span><span class="sxs-lookup"><span data-stu-id="44736-131">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="44736-132">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="44736-132">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44736-133"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="44736-133"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="44736-134">int</span><span class="sxs-lookup"><span data-stu-id="44736-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="44736-135">请参阅 SendSignalLevel。</span><span class="sxs-lookup"><span data-stu-id="44736-135">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44736-136"><strong>SendNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="44736-136"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="44736-137">int</span><span class="sxs-lookup"><span data-stu-id="44736-137">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="44736-138">表示模拟后增益控制音频噪声级别。</span><span class="sxs-lookup"><span data-stu-id="44736-138">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="44736-139">此指标的单位为 dBmo。</span><span class="sxs-lookup"><span data-stu-id="44736-139">The unit for this metric is dBmo.</span></span> <span data-ttu-id="44736-140">为获得可接受的质量，它应小于 35 dBmo。</span><span class="sxs-lookup"><span data-stu-id="44736-140">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="44736-141">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="44736-141">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44736-142"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="44736-142"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="44736-143">int</span><span class="sxs-lookup"><span data-stu-id="44736-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="44736-144">请参阅 SendNoiseLevel。</span><span class="sxs-lookup"><span data-stu-id="44736-144">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44736-145"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="44736-145"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="44736-146">int</span><span class="sxs-lookup"><span data-stu-id="44736-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="44736-147">回音返回损失增强指标。</span><span class="sxs-lookup"><span data-stu-id="44736-147">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="44736-148">此指标的单位为 dB。</span><span class="sxs-lookup"><span data-stu-id="44736-148">The unit for this metric is dB.</span></span> <span data-ttu-id="44736-149">较低的值表示较少的回声。</span><span class="sxs-lookup"><span data-stu-id="44736-149">Lower values represent less echo.</span></span> <span data-ttu-id="44736-150">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="44736-150">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44736-151"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="44736-151"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="44736-152">int</span><span class="sxs-lookup"><span data-stu-id="44736-152">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="44736-153">扬声器呈现每五分钟的平均故障。</span><span class="sxs-lookup"><span data-stu-id="44736-153">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="44736-154">为了获得良好的质量，这应该小于每五分钟一次。</span><span class="sxs-lookup"><span data-stu-id="44736-154">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="44736-155">不由 A/V 式会议服务器、中介服务器或 IP 电话报告。</span><span class="sxs-lookup"><span data-stu-id="44736-155">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44736-156"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="44736-156"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="44736-157">int</span><span class="sxs-lookup"><span data-stu-id="44736-157">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="44736-158">麦克风捕获每五分钟的平均故障。</span><span class="sxs-lookup"><span data-stu-id="44736-158">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="44736-159">为了获得良好的质量，这应该小于每五分钟一次。</span><span class="sxs-lookup"><span data-stu-id="44736-159">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="44736-160">不由 A/V 式会议服务器、中介服务器或 IP 电话报告。</span><span class="sxs-lookup"><span data-stu-id="44736-160">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44736-161"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="44736-161"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="44736-162">十进制（9，2）</span><span class="sxs-lookup"><span data-stu-id="44736-162">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="44736-163">麦克风设备时钟相对于 CPU 时钟的偏移速率。</span><span class="sxs-lookup"><span data-stu-id="44736-163">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44736-164"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="44736-164"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="44736-165">十进制（9，2）</span><span class="sxs-lookup"><span data-stu-id="44736-165">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="44736-166">扬声器设备时钟相对于 CPU 时钟的偏移速率。</span><span class="sxs-lookup"><span data-stu-id="44736-166">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44736-167"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="44736-167"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="44736-168">十进制（9，2）</span><span class="sxs-lookup"><span data-stu-id="44736-168">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="44736-169">扬声器设备时钟相对于 CPU 时钟的偏移速率。</span><span class="sxs-lookup"><span data-stu-id="44736-169">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="44736-170">在呼叫的最后20秒内，麦克风捕获流时间戳的平均时间戳错误（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="44736-170">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44736-171"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="44736-171"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="44736-172">十进制（9，2）</span><span class="sxs-lookup"><span data-stu-id="44736-172">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="44736-173">在呼叫的最后20秒内，演讲者渲染流的时间戳错误（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="44736-173">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44736-174"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="44736-174"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="44736-175">smallint</span><span class="sxs-lookup"><span data-stu-id="44736-175">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="44736-176">语音开关是一种具有更低中断能力的半双工模式。</span><span class="sxs-lookup"><span data-stu-id="44736-176">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="44736-177">语音切换条目的原因：</span><span class="sxs-lookup"><span data-stu-id="44736-177">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="44736-178">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="44736-178">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="44736-179">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="44736-179">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="44736-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="44736-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="44736-181">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="44736-181">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="44736-182">原因可能是这些个别原因的组合。</span><span class="sxs-lookup"><span data-stu-id="44736-182">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="44736-183">只有注册用途的 regkey 才能启用 ENTER_VS_FORCEORCONVERGENCE。</span><span class="sxs-lookup"><span data-stu-id="44736-183">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="44736-184">在 Microsoft Lync Server 2013 中，此列的数据类型已更改。</span><span class="sxs-lookup"><span data-stu-id="44736-184">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44736-185"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="44736-185"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="44736-186">tinyint</span><span class="sxs-lookup"><span data-stu-id="44736-186">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="44736-187">回声事件的原因：</span><span class="sxs-lookup"><span data-stu-id="44736-187">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="44736-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="44736-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="44736-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="44736-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="44736-190">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="44736-190">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="44736-191">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="44736-191">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="44736-192">ECHO_EVENT_MIC_CLIPPING 0x10</span><span class="sxs-lookup"><span data-stu-id="44736-192">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="44736-193">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="44736-193">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="44736-194">原因可能是这些个别原因的组合。</span><span class="sxs-lookup"><span data-stu-id="44736-194">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44736-195"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="44736-195"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="44736-196">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="44736-196">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="44736-p109">在麦克风捕获流量中检测回声时的时间百分比。通常，对于耳机或话筒，值较低，而对于扬声器电话或独立扬声器，值较高。对于支持板载声学回声消除的设备，高值表示回声泄漏。对于其他设备，不应使用此指标评估设备质量。</span><span class="sxs-lookup"><span data-stu-id="44736-p109">Percentage of time when echo was detected in the microphone capture stream. Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers. For devices that support on-board acoustic echo cancellation, high values indicate echo leak. For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44736-201"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="44736-201"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="44736-202">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="44736-202">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="44736-203">在发送流中检测到回显的时间百分比。</span><span class="sxs-lookup"><span data-stu-id="44736-203">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="44736-204">发送流中的高回显百分比表示回声泄漏。</span><span class="sxs-lookup"><span data-stu-id="44736-204">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44736-205"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="44736-205"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="44736-206">int</span><span class="sxs-lookup"><span data-stu-id="44736-206">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="44736-207">从网关在中介服务器上收到信号级别;这仅适用于中介服务器。</span><span class="sxs-lookup"><span data-stu-id="44736-207">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="44736-208">此指标的单位为 dBoV。</span><span class="sxs-lookup"><span data-stu-id="44736-208">The unit of this metric is dBoV.</span></span> <span data-ttu-id="44736-209">为了获得良好的质量，可接受的范围应为 [-30 至-18] dBoV。</span><span class="sxs-lookup"><span data-stu-id="44736-209">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44736-210"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="44736-210"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="44736-211">int</span><span class="sxs-lookup"><span data-stu-id="44736-211">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="44736-212">从网关在中介服务器上接收信号级别。</span><span class="sxs-lookup"><span data-stu-id="44736-212">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="44736-213">这仅适用于中介服务器。</span><span class="sxs-lookup"><span data-stu-id="44736-213">This applies only to the Mediation Server.</span></span> <span data-ttu-id="44736-214">此指标的单位为 dBoV。</span><span class="sxs-lookup"><span data-stu-id="44736-214">The unit of this metric is dBoV.</span></span> <span data-ttu-id="44736-215">为了获得优质，可接受范围应小于-50 dBoV。</span><span class="sxs-lookup"><span data-stu-id="44736-215">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44736-216"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="44736-216"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="44736-217">int</span><span class="sxs-lookup"><span data-stu-id="44736-217">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="44736-218">中介服务器端的自动增益控制（AGC）。</span><span class="sxs-lookup"><span data-stu-id="44736-218">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44736-219"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="44736-219"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="44736-220">float</span><span class="sxs-lookup"><span data-stu-id="44736-220">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="44736-221">呼叫的前30秒内的传入信号的根平均值（RMS）。</span><span class="sxs-lookup"><span data-stu-id="44736-221">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44736-222"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="44736-222"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="44736-223">int</span><span class="sxs-lookup"><span data-stu-id="44736-223">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="44736-224">频道1上接收的信号级别。</span><span class="sxs-lookup"><span data-stu-id="44736-224">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="44736-225">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="44736-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44736-226"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="44736-226"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="44736-227">int</span><span class="sxs-lookup"><span data-stu-id="44736-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="44736-228">频道2上接收的信号级别。</span><span class="sxs-lookup"><span data-stu-id="44736-228">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="44736-229">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="44736-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44736-230"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="44736-230"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="44736-231">int</span><span class="sxs-lookup"><span data-stu-id="44736-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="44736-232">频道1上接收的噪音级别。</span><span class="sxs-lookup"><span data-stu-id="44736-232">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="44736-233">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="44736-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44736-234"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="44736-234"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="44736-235">int</span><span class="sxs-lookup"><span data-stu-id="44736-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="44736-236">频道2上接收的噪音级别。</span><span class="sxs-lookup"><span data-stu-id="44736-236">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="44736-237">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="44736-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44736-238"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="44736-238"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="44736-239">int</span><span class="sxs-lookup"><span data-stu-id="44736-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="44736-240">频道1上发送的信号级别。</span><span class="sxs-lookup"><span data-stu-id="44736-240">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="44736-241">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="44736-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44736-242"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="44736-242"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="44736-243">int</span><span class="sxs-lookup"><span data-stu-id="44736-243">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="44736-244">频道2上发送的信号级别。</span><span class="sxs-lookup"><span data-stu-id="44736-244">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="44736-245">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="44736-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44736-246"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="44736-246"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="44736-247">int</span><span class="sxs-lookup"><span data-stu-id="44736-247">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="44736-248">频道1上发送的噪音级别。</span><span class="sxs-lookup"><span data-stu-id="44736-248">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="44736-249">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="44736-249">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44736-250"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="44736-250"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="44736-251">int</span><span class="sxs-lookup"><span data-stu-id="44736-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="44736-252">频道2上发送的噪音级别。</span><span class="sxs-lookup"><span data-stu-id="44736-252">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="44736-253">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="44736-253">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

