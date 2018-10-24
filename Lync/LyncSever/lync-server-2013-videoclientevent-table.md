---
title: Lync Server 2013：VideoClientEvent 表
TOCTitle: VideoClientEvent 表
ms:assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg399039(v=OCS.15)
ms:contentKeyID: 49314592
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 VideoClientEvent 表

 

_**上一次修改主题：** 2015-03-09_

每条记录包含视频呼叫中的一个终结点的客户端事件。通常情况下，一个呼叫有两条记录，一条用于呼叫者，一条用于被叫方。


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
<td><p><strong>NetworkBandwidthLowEventRatio</strong></p></td>
<td><p></p></td>
<td><p> </p></td>
<td><p>对“错误”状态引发 LowBandwidth 事件的会话百分比。对于可接受的语音体验，可用带宽不足。</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkReceiveQualityEventRatio</strong></p></td>
<td><p></p></td>
<td><p> </p></td>
<td><p>对“错误”状态引发 ReceiveSendQuality 事件的会话百分比。</p>
<p>网络质量的抖动或数据包丢失非常严重，影响收到的音频的质量。</p></td>
</tr>
</tbody>
</table>

