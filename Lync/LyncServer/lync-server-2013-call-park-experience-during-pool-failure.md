---
title: Lync Server 2013：池故障期间的呼叫寄存体验
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Park experience during pool failure
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205383(v=OCS.15)
ms:contentKeyID: 48185831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b175e5029749ea4e3a344aaf9f3bcc7a403c1b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a>池故障期间 Lync Server 2013 中的呼叫寄存体验

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-10_

当前端池因计划外事件而不可用时, 已暂停但尚未检索的通话将断开连接。 在故障转移到备份池的过程中, 用户将被重定向到备份池并处于复原模式。 在弹性模式下, 用户不能寄存呼叫, 但可以将呼叫置于保持状态, 并将其转移。 故障转移完成后, 可以再次按正常方式暂停和检索呼叫。 在故障回复期间, 用户不能寄存呼叫, 直到他们退出恢复模式。

在灾难恢复期间, 已作为故障转移过程的一部分被重定向到备份池的用户将使用在备份池中部署的 "呼叫驻留" 应用程序。 因此, 被重定向到备份池的用户使用为备份池中的 "呼叫驻留" 应用程序配置的 "呼叫寄存" 设置。

下表总结了灾难恢复阶段的通话寄存体验。

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
<th>通话状态</th>
<th>出现停机时</th>
<th>故障转移期间</th>
<th>故障回复期间</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>通话尚未停用</p></td>
<td><p>通话保持连接, 但无法停用。</p></td>
<td><ul>
<li><p>在故障转移期间, 当用户处于复原模式时, 无法停止呼叫, 但可以将呼叫置于保持状态并进行转移。</p></li>
<li><p>故障转移完成后, 可以停用和检索呼叫。</p></li>
</ul></td>
<td><ul>
<li><p>在故障回复期间, 当用户处于复原模式时, 无法停止呼叫, 但可以将呼叫置于保持状态并进行转移。</p></li>
<li><p>当故障回复完成时, 可以停用和检索呼叫。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>呼叫已暂停, 但尚未检索</p></td>
<td><p>通话断开。</p></td>
<td><p>通话处于此状态。</p></td>
<td><p>通话保持停用。</p></td>
</tr>
<tr class="odd">
<td><p>已检索寄存通话</p></td>
<td><p>通话保持连接。</p></td>
<td><p>通话保持连接。</p></td>
<td><p>通话保持连接。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

