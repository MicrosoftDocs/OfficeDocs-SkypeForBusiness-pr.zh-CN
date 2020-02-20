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
ms.openlocfilehash: 0f0d37de40340a66e6d87365ce40924f6c6d98f0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audioclientevent-table-in-lync-server-2013"></a>Lync Server 2013 中的 AudioClientEvent 表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-17_

每个记录都包含音频呼叫中一个终结点的客户端事件。 通常情况下，一个呼叫有两个记录，一个用于呼叫者，一个用于被叫方。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>列</strong></th>
<th><strong>数据类型</strong></th>
<th><strong>键/索引</strong></th>
<th><strong>Details</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>位</p></td>
<td><p>主</p></td>
<td><p>0：被调用方的数据</p>
<p>1：呼叫者的数据</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkSendQualityEventRatio</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td><p> </p></td>
<td><p>会话百分比为 "错误" 状态触发了 NetworkSendQuality 事件。</p>
<p>在抖动或数据包丢失方面，网络质量非常严重，影响音频发送的质量。</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkReceiveQualityEventRatio</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td><p> </p></td>
<td><p>会话百分比为 "错误" 状态触发了 ReceiveSendQuality 事件。</p>
<p>在抖动或数据包丢失方面，网络质量非常严重，并会影响所接收音频的质量。</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkDelayEventRatio</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td><p> </p></td>
<td><p>会话百分比延迟事件因 "错误" 状态而触发。 网络延迟非常严重，并通过防止交互通信来影响体验</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkBandwidthLowEventRatio</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td><p> </p></td>
<td><p>会话百分比为 "错误" 状态触发了 LowBandwidth 事件。 可用带宽不足以获得可接受的语音体验。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUInsufficientEventRatio</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td><p> </p></td>
<td><p>会话百分比为 "错误" 状态触发的 CPU 空间不足的事件。 CPU 周期不足，无法使用当前形式和正在使用的应用程序进行处理。 这将导致音频通道发生扭曲。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHalfDuplexAECEventRatio</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td><p> </p></td>
<td><p>会话百分比为 "错误" 状态触发了 DeviceHalfDuplexAEC 事件。 为了防止回声，系统有输入半双工。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderNotFunctioningEventRatio</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td><p> </p></td>
<td><p>会话百分比为 "错误" 状态触发了 DeviceRenderNotFunctioning 事件。 当前用于会话的呈现设备未正常运行。 这可能会导致单向音频问题。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceCaptureNotFunctioningEventRatio</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td><p> </p></td>
<td><p>会话百分比为 "错误" 状态触发了 DeviceCaptureNotFunctioning 事件。 当前用于会话的捕获设备不能正常运行。 这可能会导致单向音频问题。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceGlitchesEventRatio</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td><p> </p></td>
<td><p>会话百分比为 "错误" 状态触发了 DeviceGlitches 事件。 呈现导致扭曲的音频会出现严重的难题。 这些故障可能是由驱动程序问题、延迟的过程调用（DPC）风暴（驱动程序）和高 CPU 使用率导致的。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceLowSNREventRatio</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td><p> </p></td>
<td><p>会话百分比为 "错误" 状态触发了 DeviceLowSNR 事件。 捕捉质量非常差，或者是用户在远离麦克风的距离。 这将导致扭曲。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceLowSpeechLevelEventRatio</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td><p> </p></td>
<td><p>会话百分比为 "错误" 状态触发了 DeviceLowSpeechLevel 事件。 用户的语音级别过低，系统无法再进一步增加。 这可能会导致扭曲或被视为单向音频。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceClippingEventRatio</strong></p></td>
<td><p>Decimal （5，2）</p></td>
<td><p> </p></td>
<td><p>会话百分比为 "错误" 状态触发了 DeviceClipping 事件。</p>
<p>当临近的语音剪辑麦克风时，由于剪辑而导致的远距离听不到失真。 一定要避免接近结束的麦克风剪辑。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceEchoEventRatio</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td><p> </p></td>
<td><p>会话百分比为 "错误" 状态触发了 DeviceEchoEvent 事件。 设备或安装程序导致回声超出系统补偿的能力。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceNearEndToEchoRatioEventRatio</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td><p> </p></td>
<td><p>会话百分比为 "错误" 状态触发了 DeviceNearEndToEchoRatio 事件。 与被捕获的回显相比，用户的语音过低，这会影响用户体验，因为它限制了中断用户的难易程度。 减小扬声器音量，将麦克风移近 talker。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceMultipleEndpointsEventCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>会话期间的次数 DeviceMultipleEndpoints 事件是针对 "错误" 状态触发的。 检测到同一会话中有多个音频终结点，并且系统通过减少呈现卷来获得补偿。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHowlingEventCount</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>会话期间的次数 DeviceHowlingEvent 事件是针对 "错误" 状态触发的。 检测到音频反馈循环（由多个终结点共享音频路径引起）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderZeroVolumeEventRatio</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td></td>
<td><p>会话触发的 DeviceRenderZeroVolume 事件处于 "错误" 状态的百分比。 呈现设备已设置为零卷。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceRenderMuteEventRatio</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td></td>
<td><p>会话触发的 DeviceRenderMute 事件处于 "错误" 状态的百分比。 呈现设备已静音。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

