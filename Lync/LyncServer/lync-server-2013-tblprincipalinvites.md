---
title: Lync Server 2013：tblPrincipalInvites
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalInvites
ms:assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558650(v=OCS.15)
ms:contentKeyID: 48184141
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1081dbec8575eac0cc2aca7fc434b5801668f447
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalinvites-in-lync-server-2013"></a>Lync Server 2013 中的 tblPrincipalInvites

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-06-25_

tblPrincipalInvites 包含所有已预配用户的带有自动邀请的所有节点的邀请。

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
<td><p>prinID</p></td>
<td><p>int, not null</p></td>
<td><p>主体 ID。</p></td>
</tr>
<tr class="even">
<td><p>invID</p></td>
<td><p>int, not null</p></td>
<td><p>从 tblLastInviteId 表生成的唯一序列号 (每个主体 ID)。</p></td>
</tr>
<tr class="odd">
<td><p>a</p></td>
<td><p>int, not null</p></td>
<td><p>节点 ID (仅聊天室)。</p></td>
</tr>
<tr class="even">
<td><p>createdOn</p></td>
<td><p>datetime, not null</p></td>
<td><p>创建时间。</p></td>
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
<td><p>&lt;prinID、&gt;</p></td>
<td><p>主键。</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>TblPrincipal 表中的 lookup 的外键。</p></td>
</tr>
<tr class="odd">
<td><p>a</p></td>
<td><p>带有 tblNode 表中的 lookup 的外键。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

