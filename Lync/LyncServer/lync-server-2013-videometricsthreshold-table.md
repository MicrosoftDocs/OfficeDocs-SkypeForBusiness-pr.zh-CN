---
title: Lync Server 2013： VideoMetricsThreshold 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoMetricsThreshold table
ms:assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204778(v=OCS.15)
ms:contentKeyID: 48183736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93dc2fd539ccc24717939ccfa2ca93032fd9f25b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videometricsthreshold-table-in-lync-server-2013"></a>Lync Server 2013 中的 VideoMetricsThreshold 表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-02_

VideoMetricsThreshold 表包含用于视频通话的体验指标质量的最佳值和可接受值。


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
<td><p><strong>VideoPostFECPLROptimal</strong></p></td>
<td><p>十进制（5，2）</p></td>
<td></td>
<td><p>默认值为0.05。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoPostFECPLRAcceptable</strong></p></td>
<td><p>十进制（5，2）</p></td>
<td></td>
<td><p>默认值为0.10。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></p></td>
<td><p>十进制（5，2）</p></td>
<td></td>
<td><p>默认值为5.0。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></p></td>
<td><p>十进制（5，2）</p></td>
<td></td>
<td><p>默认值为10.0。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvFrameRateAverageOptimal</strong></p></td>
<td><p>十进制（9，4）</p></td>
<td></td>
<td><p>默认值为12.0000。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvFramerateAverageAcceptable</strong></p></td>
<td><p>十进制（9，4）</p></td>
<td></td>
<td><p>默认值为7.0000。</p></td>
</tr>
<tr class="even">
<td><p><strong>LowFrameRateCallPercentOptimal</strong></p></td>
<td><p>十进制（5，2）</p></td>
<td></td>
<td><p>默认值为5.0。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowFrameRateCallPercentAcceptable</strong></p></td>
<td><p>十进制（5，2）</p></td>
<td></td>
<td><p>默认值为 10.0/</p></td>
</tr>
<tr class="even">
<td><p><strong>LowResolutionCallPercentOptimal</strong></p></td>
<td><p>十进制（5，2）</p></td>
<td></td>
<td><p>默认值为5.0。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowResolutionCallPercentAcceptable</strong></p></td>
<td><p>十进制（5，2）</p></td>
<td></td>
<td><p>默认值为10.0。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPacketLossRateOptimal</strong></p></td>
<td><p>foat</p></td>
<td></td>
<td><p>默认值为0.05。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoPacketLossRateAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>默认值为0.10。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoFrameRateAvgOptimal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>默认值为12。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoFrameRateAvgAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>默认值为7。</p></td>
</tr>
<tr class="even">
<td><p><strong>DynamicCapabilityPercentOptimal</strong></p></td>
<td><p>十进制（5，2）</p></td>
<td></td>
<td><p>默认值为5.00。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DynamicCapabilityPercentAcceptable</strong></p></td>
<td><p>十进制（5，2）</p></td>
<td></td>
<td><p>默认值为10.00。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

