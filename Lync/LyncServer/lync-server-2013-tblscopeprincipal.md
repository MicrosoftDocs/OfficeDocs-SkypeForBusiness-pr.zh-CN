---
title: Lync Server 2013： tblScopePrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558639(v=OCS.15)
ms:contentKeyID: 48184009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8263369e9224c4a3aeb20bbb664392fbe3ba7c6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536279"
---
# <a name="tblscopeprincipal-in-lync-server-2013"></a>Lync Server 2013 中的 tblScopePrincipal

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-12_

tblScopePrincipal 包含分配至节点的作用域。

### <a name="columns"></a>列数

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
<td><p>scopeNodeID</p></td>
<td><p>int，不为 null</p></td>
<td><p>作用域适用的节点 ID。</p></td>
</tr>
<tr class="even">
<td><p>scopePrinID</p></td>
<td><p>int，不为 null</p></td>
<td><p>主体 ID。</p></td>
</tr>
<tr class="odd">
<td><p>scopeIsDenied</p></td>
<td><p>bit，不为 null</p></td>
<td><p>如果作用域的类型为 Deny，则为 True；如果作用域的类型为 Allow，则为 False。</p></td>
</tr>
<tr class="even">
<td><p>scopeUpdatedBy</p></td>
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
<td><p>&lt;scopeNodeID, scopePrinID&gt;</p></td>
<td><p>主键。</p></td>
</tr>
<tr class="even">
<td><p>scopeNodeID</p></td>
<td><p>其查找包含在 tblNode.nodeID 表中的外键。</p></td>
</tr>
<tr class="odd">
<td><p>scopePrinID</p></td>
<td><p>其查找包含在 tblPrincipal.prinID 表中的外键。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

