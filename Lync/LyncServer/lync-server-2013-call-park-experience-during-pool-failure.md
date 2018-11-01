---
title: Lync Server 2013：池故障期间的呼叫寄存体验
TOCTitle: 池故障期间的呼叫寄存体验
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205383(v=OCS.15)
ms:contentKeyID: 49314761
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 池故障期间 Lync Server 2013 中的呼叫寄存体验

 

_**上一次修改主题：** 2015-03-09_

当 前端池因意外事件变得不可用时，将断开已寄存但尚未取回的呼叫。在至备份池的故障转移期间，用户将重定向至备份池，并将处于恢复能力模式。在恢复能力模式下，用户无法寄存呼叫，但可保持呼叫并转接呼叫。故障转移完成后，可再次正常寄存并取回呼叫。在故障回复期间，用户在脱离恢复能力模式之前，无法寄存呼叫。

灾难恢复期间，作为故障转移过程之一重定向至备份池的用户将使用在备份池中部署的 呼叫寄存应用程序。因此，重定向至备份池的用户将使用为备份池中的 呼叫寄存应用程序配置的呼叫寄存设置。

下表总结了整个灾难恢复阶段中的 呼叫寄存体验。

### 灾难恢复期间的用户体验

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>呼叫状态</th>
<th>中断出现时间</th>
<th>故障转移期间</th>
<th>故障回复期间</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>尚未寄存的呼叫</p></td>
<td><p>呼叫仍处于连接状态，但无法寄存。</p></td>
<td><ul>
<li><p>故障转移期间，用户处于恢复能力模式，无法寄存呼叫，但可保持呼叫并进行转接。</p></li>
<li><p>故障转移完成后，可寄存并取回呼叫。</p></li>
</ul></td>
<td><ul>
<li><p>故障回复期间，用户处于恢复能力模式，无法寄存呼叫，但可保持呼叫并进行转接。</p></li>
<li><p>故障回复完成后，可寄存并取回呼叫。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>呼叫已寄存，但尚未取回</p></td>
<td><p>将断开呼叫。</p></td>
<td><p>无呼叫处于此状态。</p></td>
<td><p>呼叫仍处于寄存状态。</p></td>
</tr>
<tr class="odd">
<td><p>已取回的寄存呼叫</p></td>
<td><p>呼叫仍处于连接状态。</p></td>
<td><p>呼叫仍处于连接状态。</p></td>
<td><p>呼叫仍处于连接状态。</p></td>
</tr>
</tbody>
</table>

