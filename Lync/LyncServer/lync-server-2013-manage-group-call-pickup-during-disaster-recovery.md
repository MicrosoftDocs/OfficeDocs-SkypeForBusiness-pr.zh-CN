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
ms.openlocfilehash: 45ebe93ebc1711f49d4578a2a5d908104ca2a411
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733372"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a>在 Lync Server 2013 中的灾难恢复期间管理组呼叫装货

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-01-30_

当前端池因计划外事件而变为不可用时，服务将故障转移到备份池。 在故障转移到备份池的过程中，用户将被重定向到备份池并处于复原模式。 在弹性模式下，用户无法获取其他用户的通话或让其他用户能够接听呼叫。 故障转移完成后，用户可以再次使用群组呼叫分拣。

在回切到主池期间，用户将被重定向到主池，并再次进入恢复模式。 只有在用户退出恢复模式后，组呼叫分拣功能才可用。

本部分讨论了在灾难恢复过程中进行组呼叫拾取的一些注意事项，还介绍了用户体验。

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a>灾难恢复期间组呼叫装货的注意事项

在灾难恢复过程中，已被重定向到备份池的用户作为故障转移过程的一部分，使用在备份池中为呼叫装货组编号运行的调用寄存应用程序。 因此，在灾难恢复过程中对组呼叫拾取的支持要求在主池和备份池中部署和启用呼叫驻留应用程序。

在备份池完成故障转移过程后，必须将 "呼叫驻留" 轨道表中的组呼叫装货号码范围重定向到备份池。 在故障恢复过程完成后，必须将数字范围重定向到主池。 若要重定向组呼叫的装货范围，请使用**CsCallParkOrbit** cmdlet。

如果你部署具有不同完全限定的域名（FQDN）的新池来替换主池，你需要将与主池关联的所有组呼叫装货号码范围重新分配给新池的 FQDN。 若要将号码范围重新分配给新池，你可以使用**CsCallParkOrbit** cmdlet。 有关**CsCallParkOrbit** cmdlet 的详细信息，请参阅[set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)。

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a>池故障期间的组呼叫装货体验

下表总结了组通过灾难恢复阶段的装货体验。

### <a name="user-experience-during-disaster-recovery"></a>灾难恢复期间的用户体验

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>通话状态</th>
<th>故障转移到备份池</th>
<th>回切到主池</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>新通话</p></td>
<td><p><strong>在故障转移过程中：</strong></p>
<ul>
<li><p>用户在复原模式下无法使用组呼叫装货</p></li>
</ul>
<p><strong>故障切换完成后：</strong></p>
<ul>
<li><p>当用户退出弹性和组呼叫装货号码范围被重定向到备份池时，可以使用组呼叫装货</p></li>
</ul></td>
<td><p><strong>在故障回复过程中：</strong></p>
<ul>
<li><p>用户在复原模式下无法使用组呼叫装货</p></li>
</ul>
<p><strong>故障回复完成后：</strong></p>
<ul>
<li><p>当用户退出弹性和组呼叫时，组呼叫的装货号码范围将被重定向到主池</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>组呼叫装货队列中的呼叫</p></td>
<td><p><strong>在故障转移过程中：</strong></p>
<ul>
<li><p>无法通过组呼叫提货应答队列中的通话。</p></li>
</ul>
<p><strong>故障切换完成后：</strong></p>
<ul>
<li><p>此状态下没有通话</p></li>
</ul></td>
<td><p><strong>在故障回复过程中：</strong></p>
<ul>
<li><p>无法通过组呼叫提货应答队列中的通话。</p></li>
</ul>
<p><strong>故障回复完成后：</strong></p>
<ul>
<li><p>无法通过组呼叫提货应答队列中的通话。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>已建立通话</p></td>
<td><p><strong>在故障转移过程中：</strong></p>
<ul>
<li><p>通话保持连接</p></li>
</ul>
<p><strong>故障切换完成后：</strong></p>
<ul>
<li><p>通话保持连接</p></li>
</ul></td>
<td><p><strong>在故障回复过程中：</strong></p>
<ul>
<li><p>通话保持连接</p></li>
</ul>
<p><strong>故障回复完成后：</strong></p>
<ul>
<li><p>通话保持连接</p></li>
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

