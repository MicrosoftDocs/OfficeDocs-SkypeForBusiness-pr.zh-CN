---
title: Lync Server 2013： AppSharingMetricsThreshold 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppSharingMetricsThreshold table
ms:assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205018(v=OCS.15)
ms:contentKeyID: 48184556
ms.date: 12/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e247f83b00d226024f9fc671f2d744f1ee7fdf0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738422"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a>Lync Server 2013 中的 AppSharingMetricsThreshold 表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2015-12-08_

AppSharingMetricsThreshold 表包含与应用程序共享一起使用的体验质量指标的最佳值和可接受值。 这些阈值用于确定应用程序共享体验是否应归类为较差。

此表是在 Microsoft Lync Server 2013 中引入的。


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
<td><p><strong>CallType</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>所发出通话的类型。</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimitOptimal</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>应用程序共享的最佳带宽限制。 默认值为1000000。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthLimitAcceptable</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>应用程序共享的可接受带宽限制。 默认值为500000。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentTotalOptimal</strong></p></td>
<td><p>十进制（5，2）</p></td>
<td></td>
<td><p>用于对应用程序共享质量进行分类的 "损坏" 图块的最佳百分比费率。 此值表示来自共享者的未到达查看者的内容百分比。 当共享者丢弃来自图形源或 ASMCU 磁贴的磁贴时，可能会放弃内容（或损坏）。 默认值为11%。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentTotalAcceptable</strong></p></td>
<td><p>十进制（5，2）</p></td>
<td></td>
<td><p>用于对应用程序共享质量进行分类的 "损坏" 图块的 cceptable 百分比费率。 此值表示来自共享者的未到达查看者的内容百分比。 当共享者丢弃来自图形源或 ASMCU 磁贴的磁贴时，可能会放弃内容（或损坏）。 默认值为36%。</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalOptimal</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Microsoft Lync Server 2013 中不使用此列。</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrivalAcceptable</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Microsoft Lync Server 2013 中不使用此列。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDensityOptimal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Microsoft Lync Server 2013 中不使用此列。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensityAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Microsoft Lync Server 2013 中不使用此列。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Microsoft Lync Server 2013 中不使用此列。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Microsoft Lync Server 2013 中不使用此列。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverageOptimal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>应用程序共享中涉及的两个媒体终结点之间的相对单向延迟的最佳值。 这是单跃点延迟度量。 默认值为1.0 秒。</p>
<p>在 Microsoft Lync Server 2013 中引入了该列。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayAverageAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>应用程序共享中涉及的两个媒体终结点之间的相对单向延迟的最佳值。 这是单跃点延迟度量。 默认值为1.75 秒。</p>
<p>在 Microsoft Lync Server 2013 中引入了该列。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyAverageOptimal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>在查看会话期间作为会议服务器中的平均 RDP 磁贴处理延迟的最佳值。 滞后时间是在服务器上编码起始帧时的时间差（共享者或 MCU 取决于方案），并且在查看器上对同一开始帧进行解码。</p>
<p>高平均值反映了查看体验中的延迟较长。 过载的会议服务器可能会遇到更长的平均延迟。 默认值为200ms。</p>
<p>在 Microsoft Lync Server 2013 中引入了该列。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyAverageAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>在查看会话期间作为会议服务器中的平均 RDP 磁贴处理延迟的可接受值。 滞后时间是在服务器上编码起始帧时的时间差（共享者或 MCU 取决于方案），并且在查看器上对同一开始帧进行解码。</p>
<p>高平均值反映了查看体验中的延迟较长。 过载的会议服务器可能会遇到更长的平均延迟。 默认值为200ms。</p>
<p>在 Microsoft Lync Server 2013 中引入了该列。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

