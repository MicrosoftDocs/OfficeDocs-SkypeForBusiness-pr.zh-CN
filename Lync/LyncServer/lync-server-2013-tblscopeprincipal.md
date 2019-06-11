---
title: Lync Server 2013：tblScopePrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558639(v=OCS.15)
ms:contentKeyID: 48184009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ece5ae542060835aefa05edb6e08b766293e2ac1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblscopeprincipal-in-lync-server-2013"></a>Lync Server 2013 中的 tblScopePrincipal

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-12_

tblScopePrincipal 包含分配给节点的作用域。

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
<td><p>scopeNodeID</p></td>
<td><p>int, not null</p></td>
<td><p>作用域所适用的节点 ID。</p></td>
</tr>
<tr class="even">
<td><p>scopePrinID</p></td>
<td><p>int, not null</p></td>
<td><p>主体 ID。</p></td>
</tr>
<tr class="odd">
<td><p>scopeIsDenied</p></td>
<td><p>位, not null</p></td>
<td><p>如果范围的类型为 "拒绝", 则为 True;如果允许, 则为 False。</p></td>
</tr>
<tr class="even">
<td><p>scopeUpdatedBy</p></td>
<td><p>int, not null</p></td>
<td><p>上次更新此条目的主体的 ID。</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>标示

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
<td><p>带有 tblNode 表中的 lookup 的外键。</p></td>
</tr>
<tr class="odd">
<td><p>scopePrinID</p></td>
<td><p>TblPrincipal 表中的 lookup 的外键。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

