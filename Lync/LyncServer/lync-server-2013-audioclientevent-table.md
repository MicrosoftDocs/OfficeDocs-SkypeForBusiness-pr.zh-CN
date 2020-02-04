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

# <a name="audioclientevent-table-in-lync-server-2013"></a>Lync Server 2013 中的 AudioClientEvent 表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-17_

每条记录都包含音频呼叫中一个终结点的客户端事件。 通常，一个通话有两个记录，一个用于呼叫方，另一个用于被呼叫方。


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
<th><strong>详细信息</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>bit</p></td>
<td><p>Primary</p></td>
<td><p>0：被调用方的数据</p>
<p>1：调用方的数据</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkSendQualityEventRatio</strong></p></td>
<td><p>十进制（5，2）</p></td>
<td><p> </p></td>
<td><p>会话百分比为 "坏" 状态引发 NetworkSendQuality 事件的百分比。</p>
<p>"抖动" 或 "数据包丢失" 方面的网络质量非常严重，影响音频的质量。</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkReceiveQualityEventRatio</strong></p></td>
<td><p>十进制（5，2）</p></td>
<td><p> </p></td>
<td><p>会话百分比为 "坏" 状态引发 ReceiveSendQuality 事件的百分比。</p>
<p>"抖动" 或 "数据包丢失" 方面的网络质量非常严重，影响了接收音频的质量。</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkDelayEventRatio</strong></p></td>
<td><p>十进制（5，2）</p></td>
<td><p> </p></td>
<td><p>会话百分比延迟事件针对 "错误" 状态引发。 网络延迟非常严重，并通过阻止交互式通信影响体验</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkBandwidthLowEventRatio</strong></p></td>
<td><p>十进制（5，2）</p></td>
<td><p> </p></td>
<td><p>会话百分比为 "坏" 状态引发 LowBandwidth 事件的百分比。 可用带宽不足以获得可接受的语音体验。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUInsufficientEventRatio</strong></p></td>
<td><p>十进制（5，2）</p></td>
<td><p> </p></td>
<td><p>会话百分比为 "坏" 状态引发的 CPU 事件不足。 没有足够的 CPU 周期用于处理当前形式和正在使用的应用程序。 这将导致音频通道出现扭曲。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHalfDuplexAECEventRatio</strong></p></td>
<td><p>十进制（5，2）</p></td>
<td><p> </p></td>
<td><p>会话百分比为 "坏" 状态引发 DeviceHalfDuplexAEC 事件的百分比。 为了防止回声，系统已输入半双工。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderNotFunctioningEventRatio</strong></p></td>
<td><p>十进制（5，2）</p></td>
<td><p> </p></td>
<td><p>会话百分比为 "坏" 状态引发 DeviceRenderNotFunctioning 事件的百分比。 当前用于会话的渲染设备不能正常工作。 这可能会导致单向音频问题。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceCaptureNotFunctioningEventRatio</strong></p></td>
<td><p>十进制（5，2）</p></td>
<td><p> </p></td>
<td><p>会话百分比为 "坏" 状态引发 DeviceCaptureNotFunctioning 事件的百分比。 当前用于会话的捕获设备不能正常工作。 这可能会导致单向音频问题。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceGlitchesEventRatio</strong></p></td>
<td><p>十进制（5，2）</p></td>
<td><p> </p></td>
<td><p>会话百分比为 "坏" 状态引发 DeviceGlitches 事件的百分比。 呈现导致扭曲的音频有严重的难题。 这些故障可能由驱动程序问题、延期过程调用（DPC）风暴（驱动程序）和高 CPU 使用率导致。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceLowSNREventRatio</strong></p></td>
<td><p>十进制（5，2）</p></td>
<td><p> </p></td>
<td><p>会话百分比为 "坏" 状态引发 DeviceLowSNR 事件的百分比。 捕获质量非常差，很大噪音，或者用户距离麦克风太远。 这将导致扭曲。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceLowSpeechLevelEventRatio</strong></p></td>
<td><p>十进制（5，2）</p></td>
<td><p> </p></td>
<td><p>会话百分比为 "坏" 状态引发 DeviceLowSpeechLevel 事件的百分比。 用户的语音级别太低，系统无法再进一步增加。 这可能会导致扭曲或视为单向音频。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceClippingEventRatio</strong></p></td>
<td><p>十进制（5，2）</p></td>
<td><p> </p></td>
<td><p>会话百分比为 "坏" 状态引发 DeviceClipping 事件的百分比。</p>
<p>近距离的语音剪辑时，麦克风的最大声音将因剪辑而被听到。 避免接近结束的麦克风剪辑非常重要。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceEchoEventRatio</strong></p></td>
<td><p>十进制（5，2）</p></td>
<td><p> </p></td>
<td><p>会话百分比为 "坏" 状态引发 DeviceEchoEvent 事件的百分比。 设备或安装程序导致回声超出了系统进行补偿的能力。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceNearEndToEchoRatioEventRatio</strong></p></td>
<td><p>十进制（5，2）</p></td>
<td><p> </p></td>
<td><p>会话百分比为 "坏" 状态引发 DeviceNearEndToEchoRatio 事件的百分比。 与正在捕获的回显相比，用户的语音太低，这会影响用户体验，因为它限制了中断用户的难易程度。 缩小扬声器音量，将麦克风移近讲话者。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceMultipleEndpointsEventCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>会话期间的次数 DeviceMultipleEndpoints 事件针对 "错误" 状态引发。 检测到同一会话中有多个音频终结点，并且系统通过减少呈现音量进行了补偿。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHowlingEventCount</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>会话期间的次数 DeviceHowlingEvent 事件针对 "错误" 状态引发。 检测到音频反馈循环（由多个终结点共享音频路径引起）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderZeroVolumeEventRatio</strong></p></td>
<td><p>十进制（5，2）</p></td>
<td></td>
<td><p>触发 DeviceRenderZeroVolume 事件以处于 "错误" 状态的会话百分比。 呈现设备已设置为零卷。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceRenderMuteEventRatio</strong></p></td>
<td><p>十进制（5，2）</p></td>
<td></td>
<td><p>触发 DeviceRenderMute 事件以处于 "错误" 状态的会话百分比。 呈现设备已静音。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

