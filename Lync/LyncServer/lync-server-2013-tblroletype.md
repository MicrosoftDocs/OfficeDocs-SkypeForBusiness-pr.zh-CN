---
title: Lync Server 2013：tblRoleType
TOCTitle: tblRoleType
ms:assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg558623(v=OCS.15)
ms:contentKeyID: 49312205
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 tblRoleType

 

_**上一次修改主题：** 2015-03-09_

tblRoleType 是一个静态查找表，其中包含角色类型及其关联的权限集。

### 列

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


### 按键

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

