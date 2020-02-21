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

# <a name="audiosignal-table-in-lync-server-2013"></a>Lync Server 2013 中的 AudioSignal 表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-11-12_

每个记录表示一个终结点的音频信号指标。 通常情况下，每个呼叫都有两个记录，一个用于呼叫者，另一个用于被叫方。


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
<td><p><strong>SendSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>表示模拟后增益控制音频信号级别。 此指标的单位为 dBmo。 为获得可接受的质量，至少应为 30 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>请参阅 SendSignalLevel。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>表示模拟后增益控制音频噪音级别。 此指标的单位为 dBmo。 为获得可接受的质量，它应小于 35 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>请参阅 SendNoiseLevel。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoReturn</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>回显返回丢失增强指标。 此指标的单位为 dB。 值越低表示回显越少。 A/V 会议服务器或 IP 电话不报告此指标。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSpeakerGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>扬声器呈现的每5分钟平均故障。 为了获得较高的质量，这应小于每五分钟一次。 不是由 A/V 会议服务器、中介服务器或 IP 电话报告。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioMicGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>麦克风捕获每5分钟的平均故障。 若要获得较高的质量，这应小于每5分钟一次。 不是由 A/V 会议服务器、中介服务器或 IP 电话报告。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampDriftRateMic</strong></p></td>
<td><p>小数（9，2）</p></td>
<td><p> </p></td>
<td><p>麦克风设备时钟相对于 CPU 时钟的速度偏移速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampDriftRateSpk</strong></p></td>
<td><p>小数（9，2）</p></td>
<td><p> </p></td>
<td><p>扬声器设备时钟相对于 CPU 时钟的速度偏移速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampErrorMicMs</strong></p></td>
<td><p>小数（9，2）</p></td>
<td><p> </p></td>
<td><p>扬声器设备时钟相对于 CPU 时钟的速度偏移速率。</p>
<p>呼叫的最后20秒内的麦克风捕获流的平均时间戳错误（以毫秒为单位）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampErrorSpkMs</strong></p></td>
<td><p>小数（9，2）</p></td>
<td><p> </p></td>
<td><p>平均扬声器在呼叫的最后20秒内呈现流时间戳错误（以毫秒为单位）。</p></td>
</tr>
<tr class="even">
<td><p><strong>VsEntryCauses</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>Voice switch 是一个半双工模式，具有更低的中断能力。 语音切换条目的原因：</p>
<p>ENTER_VS_BADTS 0x01</p>
<p>ENTER_VS_ECHO 0x02</p>
<p>ENTER_VS_FORCEORCONVERGENCE 0x04</p>
<p>ENTER_VS_DNLP 0x08</p>
<p>原因可能是这些独立原因的组合。 仅可通过 regkey 为测试目的启用 ENTER_VS_FORCEORCONVERGENCE。</p>
<p>此列的数据类型在 Microsoft Lync Server 2013 中已更改。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoEventCauses</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>Echo 事件的原因：</p>
<p>ECHO_EVENT_BAD_TIMESTAMP 0x01</p>
<p>ECHO_EVENT_POSTAEC_ECHO 0x02</p>
<p>ECHO_EVENT_ANLP 0x04</p>
<p>ECHO_EVENT_DNLP 0x08</p>
<p>ECHO_EVENT_MIC_CLIPPING 0x10</p>
<p>ECHO_EVENT_BAD_STATE 0x20</p>
<p>原因可能是这些独立原因的组合。</p></td>
</tr>
<tr class="even">
<td><p><strong>EchoPercentMicIn</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td><p> </p></td>
<td><p>在麦克风捕获流中检测到回显的时间的百分比。 通常情况下，耳机或话机的值较低，对于扬声器电话或独立扬声器，值较高。 对于支持板载音频回声取消的设备，高值表示回显泄漏。 对于其他设备，不应使用此指标来评估设备质量。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoPercentSend</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td></td>
<td><p>在发送的流中检测到回显的时间的百分比。 发送流中的高回显百分比指示回声泄漏。</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAGCSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>从网关在中介服务器上接收到的信号级别;这仅适用于中介服务器。 此指标的单位为 dBoV。 为了获得良好的质量，可接受范围应为 [-30 至-18] dBoV。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RxAGCNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>从网关在中介服务器上接收到的信号级别。 这仅适用于中介服务器。 此指标的单位为 dBoV。 为了获得良好的质量，可接受的范围应小于-50 dBoV。</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAvgAGCGain</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>中介服务器端的自动增益控制（AGC）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>InitialSignalLevelRMS</strong></p></td>
<td><p>点数</p></td>
<td><p> </p></td>
<td><p>呼叫的前30秒内传入信号的根平均平方（RMS）。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通道1上接收的信号级别。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通道2上接收的信号级别。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>频道1上接收的噪音水平。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>频道2上接收的噪音水平。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通道1上发送的信号级别。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通道2上发送的信号级别。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>频道1上发送的噪音水平。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>频道2上发送的噪音水平。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

