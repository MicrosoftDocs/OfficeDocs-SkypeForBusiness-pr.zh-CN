---
title: Lync Server 2013： tblPrincipalRole
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalRole
ms:assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615039(v=OCS.15)
ms:contentKeyID: 48185597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4da9525e81856989c5d5046e43b2277ca6a8b2a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalrole-in-lync-server-2013"></a>Lync Server 2013 中的 tblPrincipalRole

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-12_

tblPrincipalRole 包含分配给节点的显式角色。

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
<td><p>prinRoleNodeID</p></td>
<td><p>int，不为 null</p></td>
<td><p>该角色应用于的节点 ID。</p></td>
</tr>
<tr class="even">
<td><p>prinRolePrinID</p></td>
<td><p>int，不为 null</p></td>
<td><p>主体 ID。</p></td>
</tr>
<tr class="odd">
<td><p>prinRoleTypeID</p></td>
<td><p>int，不为 null</p></td>
<td><p>角色类型 ID （从 tblRoleType）。</p></td>
</tr>
<tr class="even">
<td><p>prinRoleUpdatedBy</p></td>
<td><p>int, 不为 null</p></td>
<td><p>上次更新此项的主体的 ID。</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>Keys

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
<td><p>&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</p></td>
<td><p>主键。</p></td>
</tr>
<tr class="even">
<td><p>prinRoleNodeID</p></td>
<td><p>其查找包含在 tblNode.nodeID 表中的外键。</p></td>
</tr>
<tr class="odd">
<td><p>prinRolePrinID</p></td>
<td><p>其查找包含在 tblPrincipal.prinID 表中的外键。</p></td>
</tr>
<tr class="even">
<td><p>prinRoleTypeID</p></td>
<td><p>包含 tblRoleType 表中的 lookup 的外键。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

