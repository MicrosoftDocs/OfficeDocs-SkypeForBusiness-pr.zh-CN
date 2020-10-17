---
title: Lync Server 2013： AudioClientEvent 表
description: Lync Server 2013： AudioClientEvent 表。
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
ms.openlocfilehash: 2200cd9567bdd10ac4ad8f5c269062c2f5614dcb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568778"
---
# <a name="audioclientevent-table-in-lync-server-2013"></a><span data-ttu-id="c0bb4-103">Lync Server 2013 中的 AudioClientEvent 表</span><span class="sxs-lookup"><span data-stu-id="c0bb4-103">AudioClientEvent table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0bb4-104">_**上次修改的主题：** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="c0bb4-104">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="c0bb4-105">每个记录都包含音频呼叫中一个终结点的客户端事件。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-105">Each record contains a client event for one endpoint in an audio call.</span></span> <span data-ttu-id="c0bb4-106">通常情况下，一个呼叫有两个记录，一个用于呼叫者，一个用于被叫方。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-106">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c0bb4-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="c0bb4-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="c0bb4-108"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="c0bb4-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="c0bb4-109"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="c0bb4-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="c0bb4-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="c0bb4-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0bb4-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="c0bb4-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bb4-112">datetime</span><span class="sxs-lookup"><span data-stu-id="c0bb4-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="c0bb4-113">主</span><span class="sxs-lookup"><span data-stu-id="c0bb4-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="c0bb4-114"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0bb4-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c0bb4-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bb4-116">int</span><span class="sxs-lookup"><span data-stu-id="c0bb4-116">int</span></span></p></td>
<td><p><span data-ttu-id="c0bb4-117">主</span><span class="sxs-lookup"><span data-stu-id="c0bb4-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="c0bb4-118"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0bb4-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="c0bb4-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bb4-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="c0bb4-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c0bb4-121">主</span><span class="sxs-lookup"><span data-stu-id="c0bb4-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="c0bb4-122"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0bb4-123"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="c0bb4-123"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bb4-124">位</span><span class="sxs-lookup"><span data-stu-id="c0bb4-124">bit</span></span></p></td>
<td><p><span data-ttu-id="c0bb4-125">主</span><span class="sxs-lookup"><span data-stu-id="c0bb4-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="c0bb4-126">0：被调用方的数据</span><span class="sxs-lookup"><span data-stu-id="c0bb4-126">0: Callee’s data</span></span></p>
<p><span data-ttu-id="c0bb4-127">1：呼叫者的数据</span><span class="sxs-lookup"><span data-stu-id="c0bb4-127">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0bb4-128"><strong>NetworkSendQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c0bb4-128"><strong>NetworkSendQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bb4-129">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="c0bb4-129">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c0bb4-130">会话百分比为 "错误" 状态触发了 NetworkSendQuality 事件。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-130">Percentage of session the NetworkSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="c0bb4-131">在抖动或数据包丢失方面，网络质量非常严重，影响音频发送的质量。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-131">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0bb4-132"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c0bb4-132"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bb4-133">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="c0bb4-133">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c0bb4-134">会话百分比为 "错误" 状态触发了 ReceiveSendQuality 事件。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-134">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="c0bb4-135">在抖动或数据包丢失方面，网络质量非常严重，并会影响所接收音频的质量。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-135">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0bb4-136"><strong>NetworkDelayEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c0bb4-136"><strong>NetworkDelayEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bb4-137">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="c0bb4-137">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c0bb4-138">会话百分比延迟事件因 "错误" 状态而触发。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-138">Percentage of session the Delay event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="c0bb4-139">网络延迟非常严重，并通过防止交互通信来影响体验</span><span class="sxs-lookup"><span data-stu-id="c0bb4-139">Network latency is severe and impacting the experience by preventing interactive communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0bb4-140"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c0bb4-140"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bb4-141">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="c0bb4-141">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c0bb4-142">会话百分比为 "错误" 状态触发了 LowBandwidth 事件。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-142">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="c0bb4-143">可用带宽不足以获得可接受的语音体验。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-143">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0bb4-144"><strong>CPUInsufficientEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c0bb4-144"><strong>CPUInsufficientEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bb4-145">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="c0bb4-145">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c0bb4-146">会话百分比为 "错误" 状态触发的 CPU 空间不足的事件。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-146">Percentage of session the insufficient CPU event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="c0bb4-147">CPU 周期不足，无法使用当前形式和正在使用的应用程序进行处理。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-147">There are insufficient CPU cycles for processing with the current modalities and applications in use.</span></span> <span data-ttu-id="c0bb4-148">这将导致音频通道发生扭曲。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-148">This causes distortions with the audio channel.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0bb4-149"><strong>DeviceHalfDuplexAECEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c0bb4-149"><strong>DeviceHalfDuplexAECEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bb4-150">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="c0bb4-150">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c0bb4-151">会话百分比为 "错误" 状态触发了 DeviceHalfDuplexAEC 事件。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-151">Percentage of session the DeviceHalfDuplexAEC event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="c0bb4-152">为了防止回声，系统有输入半双工。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-152">In order to prevent echo, the system has enter half duplex.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0bb4-153"><strong>DeviceRenderNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c0bb4-153"><strong>DeviceRenderNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bb4-154">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="c0bb4-154">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c0bb4-155">会话百分比为 "错误" 状态触发了 DeviceRenderNotFunctioning 事件。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-155">Percentage of session the DeviceRenderNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="c0bb4-156">当前用于会话的呈现设备未正常运行。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-156">The render device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="c0bb4-157">这可能会导致单向音频问题。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-157">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0bb4-158"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c0bb4-158"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bb4-159">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="c0bb4-159">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c0bb4-160">会话百分比为 "错误" 状态触发了 DeviceCaptureNotFunctioning 事件。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-160">Percentage of session the DeviceCaptureNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="c0bb4-161">当前用于会话的捕获设备不能正常运行。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-161">The capture device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="c0bb4-162">这可能会导致单向音频问题。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-162">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0bb4-163"><strong>DeviceGlitchesEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c0bb4-163"><strong>DeviceGlitchesEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bb4-164">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="c0bb4-164">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c0bb4-165">会话百分比为 "错误" 状态触发了 DeviceGlitches 事件。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-165">Percentage of session the DeviceGlitches event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="c0bb4-166">呈现导致扭曲的音频会出现严重的难题。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-166">There are severe glitches in the rendering of audio which is causing distortions.</span></span> <span data-ttu-id="c0bb4-167">这些故障可能是由驱动程序问题、延迟的过程调用 (DPC) 风暴 (驱动程序) 和高 CPU 使用率导致的。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-167">These glitches can be caused by driver issues, deferred procedure calls (DPC) storm (drivers), and high CPU usage.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0bb4-168"><strong>DeviceLowSNREventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c0bb4-168"><strong>DeviceLowSNREventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bb4-169">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="c0bb4-169">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c0bb4-170">会话百分比为 "错误" 状态触发了 DeviceLowSNR 事件。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-170">Percentage of session the DeviceLowSNR event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="c0bb4-171">捕捉质量非常差，或者是用户在远离麦克风的距离。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-171">The capture quality is very poor, either very noisy or user is talking too far away from the microphone.</span></span> <span data-ttu-id="c0bb4-172">这将导致扭曲。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-172">This will cause distortions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0bb4-173"><strong>DeviceLowSpeechLevelEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c0bb4-173"><strong>DeviceLowSpeechLevelEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bb4-174">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="c0bb4-174">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c0bb4-175">会话百分比为 "错误" 状态触发了 DeviceLowSpeechLevel 事件。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-175">Percentage of session the DeviceLowSpeechLevel event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="c0bb4-176">用户的语音级别过低，系统无法再进一步增加。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-176">User‘s speech level is too low and the system cannot increase it any further.</span></span> <span data-ttu-id="c0bb4-177">这可能会导致扭曲或被视为单向音频。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-177">This can either cause distortions or perceived as one-way audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0bb4-178"><strong>DeviceClippingEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c0bb4-178"><strong>DeviceClippingEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bb4-179">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="c0bb4-179">Decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c0bb4-180">会话百分比为 "错误" 状态触发了 DeviceClipping 事件。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-180">Percentage of session the DeviceClipping event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="c0bb4-181">当临近的语音剪辑麦克风时，由于剪辑而导致的远距离听不到失真。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-181">When near-end speech clips the microphone, far-end hears distortion due to clipping.</span></span> <span data-ttu-id="c0bb4-182">一定要避免接近结束的麦克风剪辑。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-182">It is important to avoid near-end microphone clipping.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0bb4-183"><strong>DeviceEchoEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c0bb4-183"><strong>DeviceEchoEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bb4-184">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="c0bb4-184">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c0bb4-185">会话百分比为 "错误" 状态触发了 DeviceEchoEvent 事件。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-185">Percentage of session the DeviceEchoEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="c0bb4-186">设备或安装程序导致回声超出系统补偿的能力。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-186">Device or setup is causing echo beyond the ability of the system to compensate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0bb4-187"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c0bb4-187"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bb4-188">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="c0bb4-188">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c0bb4-189">会话百分比为 "错误" 状态触发了 DeviceNearEndToEchoRatio 事件。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-189">Percentage of session the DeviceNearEndToEchoRatio event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="c0bb4-190">与被捕获的回显相比，用户的语音过低，这会影响用户体验，因为它限制了中断用户的难易程度。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-190">The user’s speech is too low compared to the echo being captured which impacts the users experience because it limits how easy it is to interrupt a user.</span></span> <span data-ttu-id="c0bb4-191">减小扬声器音量，将麦克风移近 talker。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-191">Reduce speaker volume, move the microphone closer to the talker.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0bb4-192"><strong>DeviceMultipleEndpointsEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="c0bb4-192"><strong>DeviceMultipleEndpointsEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bb4-193">int</span><span class="sxs-lookup"><span data-stu-id="c0bb4-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c0bb4-194">会话期间的次数 DeviceMultipleEndpoints 事件是针对 "错误" 状态触发的。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-194">Number of times during session the DeviceMultipleEndpoints event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="c0bb4-195">检测到同一会话中有多个音频终结点，并且系统通过减少呈现卷来获得补偿。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-195">Multiple audio endpoints in the same session detected and the system has compensated by reducing render volume.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0bb4-196"><strong>DeviceHowlingEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="c0bb4-196"><strong>DeviceHowlingEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bb4-197">int</span><span class="sxs-lookup"><span data-stu-id="c0bb4-197">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c0bb4-198">会话期间的次数 DeviceHowlingEvent 事件是针对 "错误" 状态触发的。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-198">Number of times during session the DeviceHowlingEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="c0bb4-199">检测到由多个终结点共享音频路径) 导致的音频反馈循环 (。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-199">Audio feedback loop detected (caused by multiple endpoints sharing audio path).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0bb4-200"><strong>DeviceRenderZeroVolumeEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c0bb4-200"><strong>DeviceRenderZeroVolumeEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bb4-201">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="c0bb4-201">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c0bb4-202">会话触发的 DeviceRenderZeroVolume 事件处于 "错误" 状态的百分比。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-202">Percentage of session the DeviceRenderZeroVolume event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="c0bb4-203">呈现设备已设置为零卷。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-203">The render device was set to zero volume.</span></span></p>
<p><span data-ttu-id="c0bb4-204">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-204">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0bb4-205"><strong>DeviceRenderMuteEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c0bb4-205"><strong>DeviceRenderMuteEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c0bb4-206">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="c0bb4-206">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c0bb4-207">会话触发的 DeviceRenderMute 事件处于 "错误" 状态的百分比。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-207">Percentage of session the DeviceRenderMute event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="c0bb4-208">呈现设备已静音。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-208">The render device was muted.</span></span></p>
<p><span data-ttu-id="c0bb4-209">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c0bb4-209">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

