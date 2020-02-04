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

# <a name="audiosignal-table-in-lync-server-2013"></a>Lync Server 2013 中的 AudioSignal 表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-11-12_

每条记录表示一个终结点的音频信号指标。 通常，每个通话都有两条记录，一个用于呼叫方，另一个用于被呼叫方。


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
<td><p><strong>SendSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>表示模拟后增益控制音频信号级别。 此指标的单位为 dBmo。 为获得可接受的质量，它至少应为 30 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。</p></td>
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
<td><p>表示模拟后增益控制音频噪声级别。 此指标的单位为 dBmo。 为获得可接受的质量，它应小于 35 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。</p></td>
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
<td><p>回音返回损失增强指标。 此指标的单位为 dB。 较低的值表示较少的回声。 A/V 会议服务器或 IP 电话不报告此指标。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSpeakerGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>扬声器呈现每五分钟的平均故障。 为了获得良好的质量，这应该小于每五分钟一次。 不由 A/V 式会议服务器、中介服务器或 IP 电话报告。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioMicGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>麦克风捕获每五分钟的平均故障。 为了获得良好的质量，这应该小于每五分钟一次。 不由 A/V 式会议服务器、中介服务器或 IP 电话报告。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampDriftRateMic</strong></p></td>
<td><p>十进制（9，2）</p></td>
<td><p> </p></td>
<td><p>麦克风设备时钟相对于 CPU 时钟的偏移速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampDriftRateSpk</strong></p></td>
<td><p>十进制（9，2）</p></td>
<td><p> </p></td>
<td><p>扬声器设备时钟相对于 CPU 时钟的偏移速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampErrorMicMs</strong></p></td>
<td><p>十进制（9，2）</p></td>
<td><p> </p></td>
<td><p>扬声器设备时钟相对于 CPU 时钟的偏移速率。</p>
<p>在呼叫的最后20秒内，麦克风捕获流时间戳的平均时间戳错误（以毫秒为单位）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampErrorSpkMs</strong></p></td>
<td><p>十进制（9，2）</p></td>
<td><p> </p></td>
<td><p>在呼叫的最后20秒内，演讲者渲染流的时间戳错误（以毫秒为单位）。</p></td>
</tr>
<tr class="even">
<td><p><strong>VsEntryCauses</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>语音开关是一种具有更低中断能力的半双工模式。 语音切换条目的原因：</p>
<p>ENTER_VS_BADTS 0x01</p>
<p>ENTER_VS_ECHO 0x02</p>
<p>ENTER_VS_FORCEORCONVERGENCE 0x04</p>
<p>ENTER_VS_DNLP 0x08</p>
<p>原因可能是这些个别原因的组合。 只有注册用途的 regkey 才能启用 ENTER_VS_FORCEORCONVERGENCE。</p>
<p>在 Microsoft Lync Server 2013 中，此列的数据类型已更改。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoEventCauses</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>回声事件的原因：</p>
<p>ECHO_EVENT_BAD_TIMESTAMP 0x01</p>
<p>ECHO_EVENT_POSTAEC_ECHO 0x02</p>
<p>ECHO_EVENT_ANLP 0x04</p>
<p>ECHO_EVENT_DNLP 0x08</p>
<p>ECHO_EVENT_MIC_CLIPPING 0x10</p>
<p>ECHO_EVENT_BAD_STATE 0x20</p>
<p>原因可能是这些个别原因的组合。</p></td>
</tr>
<tr class="even">
<td><p><strong>EchoPercentMicIn</strong></p></td>
<td><p>十进制（5，2）</p></td>
<td><p> </p></td>
<td><p>在麦克风捕获流量中检测回声时的时间百分比。通常，对于耳机或话筒，值较低，而对于扬声器电话或独立扬声器，值较高。对于支持板载声学回声消除的设备，高值表示回声泄漏。对于其他设备，不应使用此指标评估设备质量。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoPercentSend</strong></p></td>
<td><p>十进制（5，2）</p></td>
<td></td>
<td><p>在发送流中检测到回显的时间百分比。 发送流中的高回显百分比表示回声泄漏。</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAGCSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>从网关在中介服务器上收到信号级别;这仅适用于中介服务器。 此指标的单位为 dBoV。 为了获得良好的质量，可接受的范围应为 [-30 至-18] dBoV。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RxAGCNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>从网关在中介服务器上接收信号级别。 这仅适用于中介服务器。 此指标的单位为 dBoV。 为了获得优质，可接受范围应小于-50 dBoV。</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAvgAGCGain</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>中介服务器端的自动增益控制（AGC）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>InitialSignalLevelRMS</strong></p></td>
<td><p>float</p></td>
<td><p> </p></td>
<td><p>呼叫的前30秒内的传入信号的根平均值（RMS）。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>频道1上接收的信号级别。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>频道2上接收的信号级别。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>频道1上接收的噪音级别。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>频道2上接收的噪音级别。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>频道1上发送的信号级别。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>频道2上发送的信号级别。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>频道1上发送的噪音级别。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>频道2上发送的噪音级别。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

