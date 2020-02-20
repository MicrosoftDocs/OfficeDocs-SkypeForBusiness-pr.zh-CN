---
title: Lync Server 2013：在灾难恢复过程中管理组呼叫装货
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Group Call Pickup during disaster recovery
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945618(v=OCS.15)
ms:contentKeyID: 51541455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 633ccf1c792f951d13c747c935af51569365c753
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a>在 Lync Server 2013 中管理灾难恢复期间的组呼叫装货

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-01-30_

当前端池因计划外事件而变为不可用时，服务将故障转移到备份池。 在故障转移到备份池的过程中，用户将被重定向到备份池并处于恢复模式。 在恢复模式下，用户不能选择其他用户的呼叫，也不能接听其他用户的呼叫。 故障转移完成后，用户可以像往常一样使用组呼叫应答。

在故障回复到主池期间，用户会被重定向到主池，并再次处于恢复模式。 在用户离开恢复模式之前，组呼叫应答功能将不可用。

本节讨论灾难恢复过程中组呼叫选取的一些注意事项，同时还介绍了用户体验。

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a>灾难恢复过程中组呼叫装货的注意事项

在灾难恢复过程中，作为故障转移过程的一部分被重定向到备份池的用户将使用在备份池中为呼叫应答组编号运行的呼叫寄存应用程序。 因此，在灾难恢复过程中对组呼叫选取的支持要求在主池和备份池中部署和启用呼叫寄存应用程序。

在完成对备份池的故障转移过程后，必须将呼叫寄存通道表中的组内呼叫应答号范围重定向到备份池。 在将故障回复进程完成后，必须将号码范围重定向回主池。 若要重定向组的呼叫装货范围，请使用**CsCallParkOrbit** cmdlet。

如果使用其他完全限定的域名（FQDN）部署新池以替换主池，则需要将与主池关联的所有组呼叫应答号码范围重新分配给新池的 FQDN。 若要将号码范围重新分配给新池，您可以使用**CsCallParkOrbit** cmdlet。 有关**CsCallParkOrbit** cmdlet 的详细信息，请参阅[CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)。

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a>池故障期间的组内呼叫装货体验

下表汇总了灾难恢复阶段的组呼叫装货体验。

### <a name="user-experience-during-disaster-recovery"></a>灾难恢复期间的用户体验

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>呼叫状态</th>
<th>故障转移到备份池</th>
<th>故障回复到主池</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>新呼叫</p></td>
<td><p><strong>在故障转移过程中：</strong></p>
<ul>
<li><p>用户处于恢复模式时，组呼叫应答不可用</p></li>
</ul>
<p><strong>故障转移完成后：</strong></p>
<ul>
<li><p>用户离开弹性和组呼叫应答范围被重定向到备份池时可用的组内呼叫装货</p></li>
</ul></td>
<td><p><strong>在故障回复过程中：</strong></p>
<ul>
<li><p>用户处于恢复模式时，组呼叫应答不可用</p></li>
</ul>
<p><strong>故障回复完成后：</strong></p>
<ul>
<li><p>当用户无法使用弹性和组呼叫应答号范围重定向回主池时，可以使用组内呼叫应答</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>组内呼叫应答队列中的呼叫</p></td>
<td><p><strong>在故障转移过程中：</strong></p>
<ul>
<li><p>无法通过组呼叫应答应答队列中的呼叫。</p></li>
</ul>
<p><strong>故障转移完成后：</strong></p>
<ul>
<li><p>处于此状态的呼叫</p></li>
</ul></td>
<td><p><strong>在故障回复过程中：</strong></p>
<ul>
<li><p>无法通过组呼叫应答应答队列中的呼叫。</p></li>
</ul>
<p><strong>故障回复完成后：</strong></p>
<ul>
<li><p>无法通过组呼叫应答应答队列中的呼叫。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>已建立呼叫</p></td>
<td><p><strong>在故障转移过程中：</strong></p>
<ul>
<li><p>呼叫保持连接</p></li>
</ul>
<p><strong>故障转移完成后：</strong></p>
<ul>
<li><p>呼叫保持连接</p></li>
</ul></td>
<td><p><strong>在故障回复过程中：</strong></p>
<ul>
<li><p>呼叫保持连接</p></li>
</ul>
<p><strong>故障回复完成后：</strong></p>
<ul>
<li><p>呼叫保持连接</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

