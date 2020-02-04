---
title: Lync Server 2013：AudioClientEvent 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioClientEvent table
ms:assetid: fef73d8f-7261-4e5b-9769-82435b007979
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413086(v=OCS.15)
ms:contentKeyID: 48185967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44d5146b334af83618ca2dd6261a18e72708f4f5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722622"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audioclientevent-table-in-lync-server-2013"></a><span data-ttu-id="4f2ab-102">Lync Server 2013 中的 AudioClientEvent 表</span><span class="sxs-lookup"><span data-stu-id="4f2ab-102">AudioClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f2ab-103">_**主题上次修改时间：** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="4f2ab-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="4f2ab-104">每条记录都包含音频呼叫中一个终结点的客户端事件。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-104">Each record contains a client event for one endpoint in an audio call.</span></span> <span data-ttu-id="4f2ab-105">通常，一个通话有两个记录，一个用于呼叫方，另一个用于被呼叫方。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f2ab-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="4f2ab-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="4f2ab-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="4f2ab-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="4f2ab-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="4f2ab-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="4f2ab-109"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="4f2ab-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f2ab-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="4f2ab-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4f2ab-111">datetime</span><span class="sxs-lookup"><span data-stu-id="4f2ab-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="4f2ab-112">Primary</span><span class="sxs-lookup"><span data-stu-id="4f2ab-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="4f2ab-113">从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f2ab-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4f2ab-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4f2ab-115">int</span><span class="sxs-lookup"><span data-stu-id="4f2ab-115">int</span></span></p></td>
<td><p><span data-ttu-id="4f2ab-116">Primary</span><span class="sxs-lookup"><span data-stu-id="4f2ab-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="4f2ab-117">从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f2ab-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="4f2ab-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="4f2ab-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="4f2ab-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4f2ab-120">Primary</span><span class="sxs-lookup"><span data-stu-id="4f2ab-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="4f2ab-121">从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f2ab-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="4f2ab-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="4f2ab-123">bit</span><span class="sxs-lookup"><span data-stu-id="4f2ab-123">bit</span></span></p></td>
<td><p><span data-ttu-id="4f2ab-124">Primary</span><span class="sxs-lookup"><span data-stu-id="4f2ab-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="4f2ab-125">0：被调用方的数据</span><span class="sxs-lookup"><span data-stu-id="4f2ab-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="4f2ab-126">1：调用方的数据</span><span class="sxs-lookup"><span data-stu-id="4f2ab-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f2ab-127"><strong>NetworkSendQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="4f2ab-127"><strong>NetworkSendQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="4f2ab-128">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="4f2ab-128">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f2ab-129">会话百分比为 "坏" 状态引发 NetworkSendQuality 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-129">Percentage of session the NetworkSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="4f2ab-130">"抖动" 或 "数据包丢失" 方面的网络质量非常严重，影响音频的质量。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-130">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f2ab-131"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="4f2ab-131"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="4f2ab-132">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="4f2ab-132">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f2ab-133">会话百分比为 "坏" 状态引发 ReceiveSendQuality 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-133">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="4f2ab-134">"抖动" 或 "数据包丢失" 方面的网络质量非常严重，影响了接收音频的质量。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-134">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f2ab-135"><strong>NetworkDelayEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="4f2ab-135"><strong>NetworkDelayEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="4f2ab-136">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="4f2ab-136">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f2ab-137">会话百分比延迟事件针对 "错误" 状态引发。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-137">Percentage of session the Delay event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="4f2ab-138">网络延迟非常严重，并通过阻止交互式通信影响体验</span><span class="sxs-lookup"><span data-stu-id="4f2ab-138">Network latency is severe and impacting the experience by preventing interactive communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f2ab-139"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="4f2ab-139"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="4f2ab-140">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="4f2ab-140">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f2ab-141">会话百分比为 "坏" 状态引发 LowBandwidth 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-141">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="4f2ab-142">可用带宽不足以获得可接受的语音体验。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-142">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f2ab-143"><strong>CPUInsufficientEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="4f2ab-143"><strong>CPUInsufficientEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="4f2ab-144">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="4f2ab-144">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f2ab-145">会话百分比为 "坏" 状态引发的 CPU 事件不足。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-145">Percentage of session the insufficient CPU event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="4f2ab-146">没有足够的 CPU 周期用于处理当前形式和正在使用的应用程序。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-146">There are insufficient CPU cycles for processing with the current modalities and applications in use.</span></span> <span data-ttu-id="4f2ab-147">这将导致音频通道出现扭曲。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-147">This causes distortions with the audio channel.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f2ab-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="4f2ab-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="4f2ab-149">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="4f2ab-149">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f2ab-150">会话百分比为 "坏" 状态引发 DeviceHalfDuplexAEC 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-150">Percentage of session the DeviceHalfDuplexAEC event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="4f2ab-151">为了防止回声，系统已输入半双工。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-151">In order to prevent echo, the system has enter half duplex.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f2ab-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="4f2ab-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="4f2ab-153">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="4f2ab-153">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f2ab-154">会话百分比为 "坏" 状态引发 DeviceRenderNotFunctioning 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-154">Percentage of session the DeviceRenderNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="4f2ab-155">当前用于会话的渲染设备不能正常工作。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-155">The render device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="4f2ab-156">这可能会导致单向音频问题。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-156">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f2ab-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="4f2ab-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="4f2ab-158">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="4f2ab-158">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f2ab-159">会话百分比为 "坏" 状态引发 DeviceCaptureNotFunctioning 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-159">Percentage of session the DeviceCaptureNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="4f2ab-160">当前用于会话的捕获设备不能正常工作。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-160">The capture device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="4f2ab-161">这可能会导致单向音频问题。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-161">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f2ab-162"><strong>DeviceGlitchesEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="4f2ab-162"><strong>DeviceGlitchesEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="4f2ab-163">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="4f2ab-163">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f2ab-164">会话百分比为 "坏" 状态引发 DeviceGlitches 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-164">Percentage of session the DeviceGlitches event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="4f2ab-165">呈现导致扭曲的音频有严重的难题。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-165">There are severe glitches in the rendering of audio which is causing distortions.</span></span> <span data-ttu-id="4f2ab-166">这些故障可能由驱动程序问题、延期过程调用（DPC）风暴（驱动程序）和高 CPU 使用率导致。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-166">These glitches can be caused by driver issues, deferred procedure calls (DPC) storm (drivers), and high CPU usage.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f2ab-167"><strong>DeviceLowSNREventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="4f2ab-167"><strong>DeviceLowSNREventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="4f2ab-168">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="4f2ab-168">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f2ab-169">会话百分比为 "坏" 状态引发 DeviceLowSNR 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-169">Percentage of session the DeviceLowSNR event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="4f2ab-170">捕获质量非常差，很大噪音，或者用户距离麦克风太远。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-170">The capture quality is very poor, either very noisy or user is talking too far away from the microphone.</span></span> <span data-ttu-id="4f2ab-171">这将导致扭曲。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-171">This will cause distortions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f2ab-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="4f2ab-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="4f2ab-173">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="4f2ab-173">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f2ab-174">会话百分比为 "坏" 状态引发 DeviceLowSpeechLevel 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-174">Percentage of session the DeviceLowSpeechLevel event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="4f2ab-175">用户的语音级别太低，系统无法再进一步增加。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-175">User‘s speech level is too low and the system cannot increase it any further.</span></span> <span data-ttu-id="4f2ab-176">这可能会导致扭曲或视为单向音频。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-176">This can either cause distortions or perceived as one-way audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f2ab-177"><strong>DeviceClippingEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="4f2ab-177"><strong>DeviceClippingEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="4f2ab-178">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="4f2ab-178">Decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f2ab-179">会话百分比为 "坏" 状态引发 DeviceClipping 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-179">Percentage of session the DeviceClipping event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="4f2ab-180">近距离的语音剪辑时，麦克风的最大声音将因剪辑而被听到。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-180">When near-end speech clips the microphone, far-end hears distortion due to clipping.</span></span> <span data-ttu-id="4f2ab-181">避免接近结束的麦克风剪辑非常重要。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-181">It is important to avoid near-end microphone clipping.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f2ab-182"><strong>DeviceEchoEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="4f2ab-182"><strong>DeviceEchoEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="4f2ab-183">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="4f2ab-183">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f2ab-184">会话百分比为 "坏" 状态引发 DeviceEchoEvent 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-184">Percentage of session the DeviceEchoEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="4f2ab-185">设备或安装程序导致回声超出了系统进行补偿的能力。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-185">Device or setup is causing echo beyond the ability of the system to compensate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f2ab-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="4f2ab-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="4f2ab-187">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="4f2ab-187">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f2ab-188">会话百分比为 "坏" 状态引发 DeviceNearEndToEchoRatio 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-188">Percentage of session the DeviceNearEndToEchoRatio event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="4f2ab-189">与正在捕获的回显相比，用户的语音太低，这会影响用户体验，因为它限制了中断用户的难易程度。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-189">The user’s speech is too low compared to the echo being captured which impacts the users experience because it limits how easy it is to interrupt a user.</span></span> <span data-ttu-id="4f2ab-190">缩小扬声器音量，将麦克风移近讲话者。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-190">Reduce speaker volume, move the microphone closer to the talker.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f2ab-191"><strong>DeviceMultipleEndpointsEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="4f2ab-191"><strong>DeviceMultipleEndpointsEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="4f2ab-192">int</span><span class="sxs-lookup"><span data-stu-id="4f2ab-192">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f2ab-193">会话期间的次数 DeviceMultipleEndpoints 事件针对 "错误" 状态引发。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-193">Number of times during session the DeviceMultipleEndpoints event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="4f2ab-194">检测到同一会话中有多个音频终结点，并且系统通过减少呈现音量进行了补偿。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-194">Multiple audio endpoints in the same session detected and the system has compensated by reducing render volume.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f2ab-195"><strong>DeviceHowlingEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="4f2ab-195"><strong>DeviceHowlingEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="4f2ab-196">int</span><span class="sxs-lookup"><span data-stu-id="4f2ab-196">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f2ab-197">会话期间的次数 DeviceHowlingEvent 事件针对 "错误" 状态引发。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-197">Number of times during session the DeviceHowlingEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="4f2ab-198">检测到音频反馈循环（由多个终结点共享音频路径引起）。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-198">Audio feedback loop detected (caused by multiple endpoints sharing audio path).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f2ab-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="4f2ab-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="4f2ab-200">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="4f2ab-200">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f2ab-201">触发 DeviceRenderZeroVolume 事件以处于 "错误" 状态的会话百分比。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-201">Percentage of session the DeviceRenderZeroVolume event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="4f2ab-202">呈现设备已设置为零卷。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-202">The render device was set to zero volume.</span></span></p>
<p><span data-ttu-id="4f2ab-203">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-203">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f2ab-204"><strong>DeviceRenderMuteEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="4f2ab-204"><strong>DeviceRenderMuteEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="4f2ab-205">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="4f2ab-205">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f2ab-206">触发 DeviceRenderMute 事件以处于 "错误" 状态的会话百分比。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-206">Percentage of session the DeviceRenderMute event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="4f2ab-207">呈现设备已静音。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-207">The render device was muted.</span></span></p>
<p><span data-ttu-id="4f2ab-208">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="4f2ab-208">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

