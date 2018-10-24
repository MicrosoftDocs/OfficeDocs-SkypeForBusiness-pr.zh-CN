---
title: Lync Server 2013：AudioClientEvent 表
TOCTitle: AudioClientEvent 表
ms:assetid: fef73d8f-7261-4e5b-9769-82435b007979
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413086(v=OCS.15)
ms:contentKeyID: 49314847
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 AudioClientEvent 表

 

_**上一次修改主题：** 2015-03-09_

每条记录包含音频呼叫中的一个终结点的客户端事件。通常情况下，一个呼叫有两条记录，一条用于呼叫者，一条用于被叫方。


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
<td><p>主</p></td>
<td><p>引用自 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>引用自 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主</p></td>
<td><p>引用自 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>bit</p></td>
<td><p>主</p></td>
<td><p>0：被叫方的数据</p>
<p>1：呼叫者的数据</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkSendQualityEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>对“错误”状态引发 NetworkSendQuality 事件的会话百分比。</p>
<p>抖动或数据包丢失十分严重，且影响要发送的音频的质量的网络质量。</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkReceiveQualityEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>对“错误”状态引发 ReceiveSendQuality 事件的会话百分比。</p>
<p>抖动或数据包丢失十分严重，且影响要接收的音频的质量的网络质量。</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkDelayEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>对“错误”状态引发 Delay 事件的会话百分比。网络延迟十分严重，并且阻止交互式通信，从而影响体验</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkBandwidthLowEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>对“错误”状态引发 LowBandwidth 事件的会话百分比。对于可接受的语音体验，可用带宽不足。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUInsufficientEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>对“错误”状态引发 CPU 不足事件的会话百分比。CPU 周期不足以处理当前使用的形式和应用程序。这将导致音频信道失真。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHalfDuplexAECEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>对“错误”状态引发 DeviceHalfDuplexAEC 事件的会话百分比。为了防止回声，系统已进入半双工模式。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderNotFunctioningEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>对“错误”状态引发 DeviceRenderNotFunctioning 事件的会话百分比。会话当前使用的呈现设备运行不正常。这可能导致单向音频问题。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceCaptureNotFunctioningEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>对“错误”状态引发 DeviceCaptureNotFunctioning 事件的会话百分比。会话当前使用的捕获设备运行不正常。这可能导致单向音频问题。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceGlitchesEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>对“错误”状态引发 DeviceGlitches 事件的会话百分比。导致失真的音频呈现中存在严重故障。这些故障可能由驱动程序问题、延迟过程调用 (DPC) 风暴（驱动程序）和高 CPU 使用率造成。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceLowSNREventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>对“错误”状态引发 DeviceLowSNR 事件的会话百分比。捕获质量非常差，非常吵或者用户在离麦克风过远的位置讲话。这将导致失真。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceLowSpeechLevelEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>对“错误”状态引发 DeviceLowSpeechLevel 事件的会话百分比。用户的语音级别非常慢，并且系统无法再增加它。这可能导致失真或被视为单向音频。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceClippingEventRatio</strong></p></td>
<td><p>Decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>对“错误”状态引发 DeviceClipping 事件的会话百分比。</p>
<p>当近端语音擦击麦克风时，远端会由于擦击而听到失真。应避免近端麦克风擦击，这一点十分重要。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceEchoEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>对“错误”状态引发 DeviceEchoEvent 事件的会话百分比。设备或设置导致的回声超出系统修复的能力范围。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceNearEndToEchoRatioEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>对“错误”状态引发 DeviceNearEndToEchoRatio 事件的会话百分比。与已捕获回声相比，用户的语音过低，这会影响用户体验，因为它限制了中断用户的轻松程度。降低扬声器音量，将麦克风移到离讲话者较近的位置。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceMultipleEndpointsEventCount</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>会话期间对“错误”状态引发 DeviceMultipleEndpoints 事件的次数。在同一会话中检测到多个音频终结点，并且系统已通过降低呈现音量来修复。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHowlingEventCount</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>会话中对“错误”状态引发 DeviceHowlingEvent 事件的次数。检测到音频反馈循环（由共享音频路径的多个终结点引起）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderZeroVolumeEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p></p></td>
<td><p>对“错误”状态引发 DeviceRenderZeroVolume 事件的会话百分比。将呈现设备设置为零音量。</p>
<p>此列是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceRenderMuteEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p></p></td>
<td><p>对“错误”状态引发 DeviceRenderMute 事件的会话百分比。将呈现设备设置为静音。</p>
<p>此列是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
</tbody>
</table>

