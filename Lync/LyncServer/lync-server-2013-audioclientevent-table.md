---
title: Lync Server 2013： AudioClientEvent 表
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
ms.openlocfilehash: fff3c143f06fe7a71d10b65bd281be4619cb8942
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533519"
---
# <a name="audioclientevent-table-in-lync-server-2013"></a><span data-ttu-id="40565-102">Lync Server 2013 中的 AudioClientEvent 表</span><span class="sxs-lookup"><span data-stu-id="40565-102">AudioClientEvent table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40565-103">_**上次修改的主题：** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="40565-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="40565-104">每个记录都包含音频呼叫中一个终结点的客户端事件。</span><span class="sxs-lookup"><span data-stu-id="40565-104">Each record contains a client event for one endpoint in an audio call.</span></span> <span data-ttu-id="40565-105">通常情况下，一个呼叫有两个记录，一个用于呼叫者，一个用于被叫方。</span><span class="sxs-lookup"><span data-stu-id="40565-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="40565-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="40565-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="40565-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="40565-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="40565-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="40565-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="40565-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="40565-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="40565-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="40565-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="40565-111">datetime</span><span class="sxs-lookup"><span data-stu-id="40565-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="40565-112">主</span><span class="sxs-lookup"><span data-stu-id="40565-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="40565-113"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="40565-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40565-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="40565-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="40565-115">int</span><span class="sxs-lookup"><span data-stu-id="40565-115">int</span></span></p></td>
<td><p><span data-ttu-id="40565-116">主</span><span class="sxs-lookup"><span data-stu-id="40565-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="40565-117"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="40565-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40565-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="40565-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="40565-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="40565-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="40565-120">主</span><span class="sxs-lookup"><span data-stu-id="40565-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="40565-121"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="40565-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40565-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="40565-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="40565-123">位</span><span class="sxs-lookup"><span data-stu-id="40565-123">bit</span></span></p></td>
<td><p><span data-ttu-id="40565-124">主</span><span class="sxs-lookup"><span data-stu-id="40565-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="40565-125">0：被调用方的数据</span><span class="sxs-lookup"><span data-stu-id="40565-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="40565-126">1：呼叫者的数据</span><span class="sxs-lookup"><span data-stu-id="40565-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40565-127"><strong>NetworkSendQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="40565-127"><strong>NetworkSendQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="40565-128">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="40565-128">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="40565-129">会话百分比为 "错误" 状态触发了 NetworkSendQuality 事件。</span><span class="sxs-lookup"><span data-stu-id="40565-129">Percentage of session the NetworkSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="40565-130">在抖动或数据包丢失方面，网络质量非常严重，影响音频发送的质量。</span><span class="sxs-lookup"><span data-stu-id="40565-130">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40565-131"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="40565-131"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="40565-132">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="40565-132">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="40565-133">会话百分比为 "错误" 状态触发了 ReceiveSendQuality 事件。</span><span class="sxs-lookup"><span data-stu-id="40565-133">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="40565-134">在抖动或数据包丢失方面，网络质量非常严重，并会影响所接收音频的质量。</span><span class="sxs-lookup"><span data-stu-id="40565-134">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40565-135"><strong>NetworkDelayEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="40565-135"><strong>NetworkDelayEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="40565-136">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="40565-136">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="40565-137">会话百分比延迟事件因 "错误" 状态而触发。</span><span class="sxs-lookup"><span data-stu-id="40565-137">Percentage of session the Delay event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="40565-138">网络延迟非常严重，并通过防止交互通信来影响体验</span><span class="sxs-lookup"><span data-stu-id="40565-138">Network latency is severe and impacting the experience by preventing interactive communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40565-139"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="40565-139"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="40565-140">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="40565-140">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="40565-141">会话百分比为 "错误" 状态触发了 LowBandwidth 事件。</span><span class="sxs-lookup"><span data-stu-id="40565-141">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="40565-142">可用带宽不足以获得可接受的语音体验。</span><span class="sxs-lookup"><span data-stu-id="40565-142">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40565-143"><strong>CPUInsufficientEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="40565-143"><strong>CPUInsufficientEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="40565-144">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="40565-144">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="40565-145">会话百分比为 "错误" 状态触发的 CPU 空间不足的事件。</span><span class="sxs-lookup"><span data-stu-id="40565-145">Percentage of session the insufficient CPU event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="40565-146">CPU 周期不足，无法使用当前形式和正在使用的应用程序进行处理。</span><span class="sxs-lookup"><span data-stu-id="40565-146">There are insufficient CPU cycles for processing with the current modalities and applications in use.</span></span> <span data-ttu-id="40565-147">这将导致音频通道发生扭曲。</span><span class="sxs-lookup"><span data-stu-id="40565-147">This causes distortions with the audio channel.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40565-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="40565-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="40565-149">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="40565-149">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="40565-150">会话百分比为 "错误" 状态触发了 DeviceHalfDuplexAEC 事件。</span><span class="sxs-lookup"><span data-stu-id="40565-150">Percentage of session the DeviceHalfDuplexAEC event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="40565-151">为了防止回声，系统有输入半双工。</span><span class="sxs-lookup"><span data-stu-id="40565-151">In order to prevent echo, the system has enter half duplex.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40565-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="40565-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="40565-153">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="40565-153">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="40565-154">会话百分比为 "错误" 状态触发了 DeviceRenderNotFunctioning 事件。</span><span class="sxs-lookup"><span data-stu-id="40565-154">Percentage of session the DeviceRenderNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="40565-155">当前用于会话的呈现设备未正常运行。</span><span class="sxs-lookup"><span data-stu-id="40565-155">The render device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="40565-156">这可能会导致单向音频问题。</span><span class="sxs-lookup"><span data-stu-id="40565-156">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40565-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="40565-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="40565-158">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="40565-158">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="40565-159">会话百分比为 "错误" 状态触发了 DeviceCaptureNotFunctioning 事件。</span><span class="sxs-lookup"><span data-stu-id="40565-159">Percentage of session the DeviceCaptureNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="40565-160">当前用于会话的捕获设备不能正常运行。</span><span class="sxs-lookup"><span data-stu-id="40565-160">The capture device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="40565-161">这可能会导致单向音频问题。</span><span class="sxs-lookup"><span data-stu-id="40565-161">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40565-162"><strong>DeviceGlitchesEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="40565-162"><strong>DeviceGlitchesEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="40565-163">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="40565-163">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="40565-164">会话百分比为 "错误" 状态触发了 DeviceGlitches 事件。</span><span class="sxs-lookup"><span data-stu-id="40565-164">Percentage of session the DeviceGlitches event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="40565-165">呈现导致扭曲的音频会出现严重的难题。</span><span class="sxs-lookup"><span data-stu-id="40565-165">There are severe glitches in the rendering of audio which is causing distortions.</span></span> <span data-ttu-id="40565-166">这些故障可能是由驱动程序问题、延迟的过程调用 (DPC) 风暴 (驱动程序) 和高 CPU 使用率导致的。</span><span class="sxs-lookup"><span data-stu-id="40565-166">These glitches can be caused by driver issues, deferred procedure calls (DPC) storm (drivers), and high CPU usage.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40565-167"><strong>DeviceLowSNREventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="40565-167"><strong>DeviceLowSNREventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="40565-168">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="40565-168">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="40565-169">会话百分比为 "错误" 状态触发了 DeviceLowSNR 事件。</span><span class="sxs-lookup"><span data-stu-id="40565-169">Percentage of session the DeviceLowSNR event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="40565-170">捕捉质量非常差，或者是用户在远离麦克风的距离。</span><span class="sxs-lookup"><span data-stu-id="40565-170">The capture quality is very poor, either very noisy or user is talking too far away from the microphone.</span></span> <span data-ttu-id="40565-171">这将导致扭曲。</span><span class="sxs-lookup"><span data-stu-id="40565-171">This will cause distortions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40565-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="40565-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="40565-173">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="40565-173">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="40565-174">会话百分比为 "错误" 状态触发了 DeviceLowSpeechLevel 事件。</span><span class="sxs-lookup"><span data-stu-id="40565-174">Percentage of session the DeviceLowSpeechLevel event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="40565-175">用户的语音级别过低，系统无法再进一步增加。</span><span class="sxs-lookup"><span data-stu-id="40565-175">User‘s speech level is too low and the system cannot increase it any further.</span></span> <span data-ttu-id="40565-176">这可能会导致扭曲或被视为单向音频。</span><span class="sxs-lookup"><span data-stu-id="40565-176">This can either cause distortions or perceived as one-way audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40565-177"><strong>DeviceClippingEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="40565-177"><strong>DeviceClippingEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="40565-178">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="40565-178">Decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="40565-179">会话百分比为 "错误" 状态触发了 DeviceClipping 事件。</span><span class="sxs-lookup"><span data-stu-id="40565-179">Percentage of session the DeviceClipping event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="40565-180">当临近的语音剪辑麦克风时，由于剪辑而导致的远距离听不到失真。</span><span class="sxs-lookup"><span data-stu-id="40565-180">When near-end speech clips the microphone, far-end hears distortion due to clipping.</span></span> <span data-ttu-id="40565-181">一定要避免接近结束的麦克风剪辑。</span><span class="sxs-lookup"><span data-stu-id="40565-181">It is important to avoid near-end microphone clipping.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40565-182"><strong>DeviceEchoEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="40565-182"><strong>DeviceEchoEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="40565-183">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="40565-183">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="40565-184">会话百分比为 "错误" 状态触发了 DeviceEchoEvent 事件。</span><span class="sxs-lookup"><span data-stu-id="40565-184">Percentage of session the DeviceEchoEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="40565-185">设备或安装程序导致回声超出系统补偿的能力。</span><span class="sxs-lookup"><span data-stu-id="40565-185">Device or setup is causing echo beyond the ability of the system to compensate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40565-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="40565-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="40565-187">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="40565-187">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="40565-188">会话百分比为 "错误" 状态触发了 DeviceNearEndToEchoRatio 事件。</span><span class="sxs-lookup"><span data-stu-id="40565-188">Percentage of session the DeviceNearEndToEchoRatio event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="40565-189">与被捕获的回显相比，用户的语音过低，这会影响用户体验，因为它限制了中断用户的难易程度。</span><span class="sxs-lookup"><span data-stu-id="40565-189">The user’s speech is too low compared to the echo being captured which impacts the users experience because it limits how easy it is to interrupt a user.</span></span> <span data-ttu-id="40565-190">减小扬声器音量，将麦克风移近 talker。</span><span class="sxs-lookup"><span data-stu-id="40565-190">Reduce speaker volume, move the microphone closer to the talker.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40565-191"><strong>DeviceMultipleEndpointsEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="40565-191"><strong>DeviceMultipleEndpointsEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="40565-192">int</span><span class="sxs-lookup"><span data-stu-id="40565-192">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="40565-193">会话期间的次数 DeviceMultipleEndpoints 事件是针对 "错误" 状态触发的。</span><span class="sxs-lookup"><span data-stu-id="40565-193">Number of times during session the DeviceMultipleEndpoints event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="40565-194">检测到同一会话中有多个音频终结点，并且系统通过减少呈现卷来获得补偿。</span><span class="sxs-lookup"><span data-stu-id="40565-194">Multiple audio endpoints in the same session detected and the system has compensated by reducing render volume.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40565-195"><strong>DeviceHowlingEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="40565-195"><strong>DeviceHowlingEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="40565-196">int</span><span class="sxs-lookup"><span data-stu-id="40565-196">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="40565-197">会话期间的次数 DeviceHowlingEvent 事件是针对 "错误" 状态触发的。</span><span class="sxs-lookup"><span data-stu-id="40565-197">Number of times during session the DeviceHowlingEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="40565-198">检测到由多个终结点共享音频路径) 导致的音频反馈循环 (。</span><span class="sxs-lookup"><span data-stu-id="40565-198">Audio feedback loop detected (caused by multiple endpoints sharing audio path).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40565-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="40565-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="40565-200">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="40565-200">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="40565-201">会话触发的 DeviceRenderZeroVolume 事件处于 "错误" 状态的百分比。</span><span class="sxs-lookup"><span data-stu-id="40565-201">Percentage of session the DeviceRenderZeroVolume event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="40565-202">呈现设备已设置为零卷。</span><span class="sxs-lookup"><span data-stu-id="40565-202">The render device was set to zero volume.</span></span></p>
<p><span data-ttu-id="40565-203">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="40565-203">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40565-204"><strong>DeviceRenderMuteEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="40565-204"><strong>DeviceRenderMuteEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="40565-205">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="40565-205">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="40565-206">会话触发的 DeviceRenderMute 事件处于 "错误" 状态的百分比。</span><span class="sxs-lookup"><span data-stu-id="40565-206">Percentage of session the DeviceRenderMute event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="40565-207">呈现设备已静音。</span><span class="sxs-lookup"><span data-stu-id="40565-207">The render device was muted.</span></span></p>
<p><span data-ttu-id="40565-208">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="40565-208">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

