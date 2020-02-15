---
title: Lync Server 2013：池故障期间的呼叫寄存体验
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park experience during pool failure
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205383(v=OCS.15)
ms:contentKeyID: 48185831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a89acc193f70ba5047a2f1c6362b957d182afdb5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044314"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a>池故障期间 Lync Server 2013 中的呼叫寄存体验

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-10_

当前端池因计划外事件而不可用时，将断开已暂停但尚未检索的呼叫。 在至备份池的故障转移期间，用户将重定向至备份池，并将处于恢复能力模式。 在恢复能力模式下，用户无法寄存呼叫，但可保持呼叫并转接呼叫。 故障转移完成后，可再次正常寄存并取回呼叫。 在故障回复期间，用户在脱离恢复能力模式之前，无法寄存呼叫。

在灾难恢复过程中，作为故障转移过程的一部分被重定向到备份池的用户将使用在备份池中部署的呼叫寄存应用程序。 因此，重定向到备份池的用户将使用为备份池中的呼叫寄存应用程序配置的呼叫寄存设置。

下表总结了灾难恢复阶段的呼叫寄存体验。

### <a name="user-experience-during-disaster-recovery"></a>灾难恢复期间的用户体验

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


</div>

<span> </span>

</div>

</div>

</div>

