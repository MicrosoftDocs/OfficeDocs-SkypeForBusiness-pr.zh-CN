---
title: Lync Server 2013：角色表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Roles table
ms:assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399043(v=OCS.15)
ms:contentKeyID: 48185893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d3c241f685e9acc24b82acab1c7f50e1e15754b1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050814"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="roles-table-in-lync-server-2013"></a>Lync Server 2013 中的 Roles 表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-28_

角色表是一个静态表，用于存储可能的会议角色（如与者会和演示者）的列表。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>数据类型</th>
<th>键/索引</th>
<th>详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>RoleId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>角色</strong></p></td>
<td><p>nvarchar （256）</p></td>
<td></td>
<td><p>允许的值：</p>
<ul>
<li><p>0 -- 未知</p></li>
<li><p>1 -- 演示者</p></li>
<li><p>2 -- 与会者</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

