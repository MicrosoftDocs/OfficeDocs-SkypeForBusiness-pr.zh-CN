---
title: Lync Server 2013：tblRoleType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblRoleType
ms:assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558623(v=OCS.15)
ms:contentKeyID: 48183577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba6b5041453b0965fafc12ada2be62ec42316f89
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblroletype-in-lync-server-2013"></a>Lync Server 2013 中的 tblRoleType

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-06-25_

tblRoleType 是一个具有角色类型及其关联权限集的静态查找表。

### <a name="columns"></a>多

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>类型</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>rtypeID</p></td>
<td><p>int，not null</p></td>
<td><p>角色类型 ID。</p></td>
</tr>
<tr class="even">
<td><p>rtypeDesc</p></td>
<td><p>nvarchar （256），not null</p></td>
<td><p>角色类型说明。 有四个可用的角色：</p>
<ul>
<li><p>成员：聊天室成员</p></li>
<li><p>管理器：聊天室管理器</p></li>
<li><p>浊音：演示者使用 auditorium 聊天室</p></li>
<li><p>创建者：可以创建聊天室</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>rtypeAllowedPermSet</p></td>
<td><p>bigint，not null</p></td>
<td><p>角色的权限集。 所用位为：</p>
<ul>
<li><p>2：如果角色可以管理节点，则为 True。</p></li>
<li><p>4：如果角色可以创建子节点，则为 True。</p></li>
<li><p>7：如果角色可以加入聊天室（或类别的子聊天室），则为 True。</p></li>
<li><p>8：如果角色可以在聊天室中（或在子类别的子聊天室中）聊天，则为 True。</p></li>
<li><p>10：如果角色可以读取聊天历史记录（即使未加入聊天室），则为 True。</p></li>
<li><p>11：如果角色可以查看聊天室，则为 True。 （这将通过范围和可见性等因素进一步改进。）</p></li>
<li><p>12：如果角色可以在 auditorium 聊天室中聊天，则为 True。</p></li>
<li><p>13：如果角色在查看节点时可以绕过可见性规则，则为 True。</p></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="key"></a>关键字

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>rtypeID</p></td>
<td><p>主键。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

