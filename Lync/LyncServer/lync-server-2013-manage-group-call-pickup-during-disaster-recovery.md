---
title: 在灾难恢复期间管理组内呼叫应答
TOCTitle: 在灾难恢复期间管理组内呼叫应答
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ945618(v=OCS.15)
ms:contentKeyID: 52060994
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在灾难恢复期间管理组内呼叫应答

 

_**上一次修改主题：** 2015-03-09_

当前端池因意外事件变得不可用时，服务被故障转移至备份池。在至备份池的故障转移期间，用户将重定向至备份池，并将处于恢复能力模式。在恢复能力模式下，用户无法接听其他用户的呼叫也无法让其他用户接听他们的呼叫。当故障转移完成时，用户可以再次像往常一样使用组内呼叫应答。

在故障回复到主池期间，用户将重定向至主池，并再次处于恢复能力模式。组内呼叫应答功能将不可用，直到用户退出恢复能力模式。

本节讨论灾难恢复期间组内呼叫应答的一些注意事项，并介绍用户体验。

## 灾难恢复期间组内呼叫应答的注意事项

灾难恢复期间，作为故障转移过程的一部分重定向至备份池的用户将使用在备份池中运行的呼叫寄存应用程序呼叫应答组号码。因此，在灾难恢复期间支持组内呼叫应答需要在主池和备份池中部署并启用呼叫寄存应用程序。

故障转移至备份池的过程完成后，必须将呼叫寄存通道表中的组内呼叫应答号码范围重定向至备份池。当故障回复至主池的过程完成后，必须将号码范围重定向回主池。若要重定向组内呼叫应答范围，请使用 **Set-CsCallParkOrbit** cmdlet。

如果您部署具有不同完全限定域名 (FQDN) 的新池来替换主池，则需要将与主池关联的所有组内呼叫应答号码范围重新分配到新池的 FQDN。若要将号码范围重新分配到新池，您可以使用 **Set-CsCallParkOrbit** cmdlet。有关 **Set-CsCallParkOrbit** cmdlet 的详细信息，请参阅 [Set-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCallParkOrbit)。

## 池故障期间的组内呼叫应答体验

下表总结了整个灾难恢复阶段中的组内呼叫应答体验。

### 灾难恢复期间的用户体验

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>呼叫状态</th>
<th>故障转移至备份池</th>
<th>故障回复至主池</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>新呼叫</p></td>
<td><p><strong>故障转移过程期间：</strong></p>
<ul>
<li><p>组内呼叫应答不可用于恢复能力模式下的用户</p></li>
</ul>
<p><strong>故障转移完成后：</strong></p>
<ul>
<li><p>组内呼叫应答在用户退出恢复能力模式时可用，并且组内呼叫应答号码范围重定向至备份池</p></li>
</ul></td>
<td><p><strong>故障回复过程期间：</strong></p>
<ul>
<li><p>组内呼叫应答不可用于恢复能力模式下的用户</p></li>
</ul>
<p><strong>故障回复完成后：</strong></p>
<ul>
<li><p>组内呼叫应答在用户退出恢复能力模式时可用，并且组内呼叫应答号码范围重定向回主池</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>呼叫处于组内呼叫应答队列中</p></td>
<td><p><strong>故障转移过程期间：</strong></p>
<ul>
<li><p>无法通过组内呼叫应答来接听处于队列中的呼叫。</p></li>
</ul>
<p><strong>故障转移完成后：</strong></p>
<ul>
<li><p>无呼叫处于此状态</p></li>
</ul></td>
<td><p><strong>故障回复过程期间：</strong></p>
<ul>
<li><p>无法通过组内呼叫应答来接听处于队列中的呼叫。</p></li>
</ul>
<p><strong>故障回复完成后：</strong></p>
<ul>
<li><p>无法通过组内呼叫应答来接听处于队列中的呼叫。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>已建立的呼叫</p></td>
<td><p><strong>故障转移过程期间：</strong></p>
<ul>
<li><p>呼叫保持连接状态</p></li>
</ul>
<p><strong>故障转移完成后：</strong></p>
<ul>
<li><p>呼叫保持连接状态</p></li>
</ul></td>
<td><p><strong>故障回复过程期间：</strong></p>
<ul>
<li><p>呼叫保持连接状态</p></li>
</ul>
<p><strong>故障回复完成后：</strong></p>
<ul>
<li><p>呼叫保持连接状态</p></li>
</ul></td>
</tr>
</tbody>
</table>

