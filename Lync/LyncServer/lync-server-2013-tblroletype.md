---
title: Lync Server 2013： tblRoleType
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
ms.openlocfilehash: 721932aa2929930b3da742355a46c5e2066c5c83
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195125"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblroletype-in-lync-server-2013"></a>Lync Server 2013 中的 tblRoleType

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-06-25_

tblRoleType 是一个静态查找表，其中包含角色类型及其关联的权限集。

### <a name="columns"></a>Columns

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
<td><p>int，不为 null</p></td>
<td><p>角色类型 ID。</p></td>
</tr>
<tr class="even">
<td><p>rtypeDesc</p></td>
<td><p>nvarchar (256)，不为 null</p></td>
<td><p>角色类型描述。可用角色有四种：</p>
<ul>
<li><p>成员：聊天室成员</p></li>
<li><p>管理员：聊天室管理员</p></li>
<li><p>有发布权的人：大会堂聊天室的演讲者</p></li>
<li><p>创建者：可以创建聊天室</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>rtypeAllowedPermSet</p></td>
<td><p>bigint，不为 null</p></td>
<td><p>角色的权限集。使用的位为：</p>
<ul>
<li><p>2：在角色可以管理节点时为 True。</p></li>
<li><p>4：在角色可以创建子节点时为 True。</p></li>
<li><p>7：在角色可以加入聊天室（或某类别的子聊天室）时为 True。</p></li>
<li><p>8：在角色可以在聊天室中（或某类别的子聊天室中）聊天时为 True。</p></li>
<li><p>10：在角色即使不加入聊天室也可读取聊天历史记录时为 True。</p></li>
<li><p>11：在角色可以看到聊天室时为 True。（该值可通过作用域和可见性等因素进一步优化。）</p></li>
<li><p>12：在角色可以在大会堂聊天室中聊天时为 True。</p></li>
<li><p>13：在角色查看节点后可以绕过可见性规则时为 True。</p></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="key"></a>键

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

