---
title: Lync Server 2013：用户表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User table
ms:assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398505(v=OCS.15)
ms:contentKeyID: 48184437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98a34028ebec126c8d5fc5ec838a22180ccb0fa7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007641"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-table-in-lync-server-2013"></a>Lync Server 2013 中的用户表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-02_

User 表是一个支持表，用于存储已参与数据库中记录的会话的各种用户的列表。该表中的每条记录表示一个用户。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>列</strong></th>
<th><strong>数据类型</strong></th>
<th><strong>键/索引</strong></th>
<th><strong>Details</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>UserKey</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>用于标识此用户的唯一编号。</p></td>
</tr>
<tr class="even">
<td><p><strong>URI</strong></p></td>
<td><p>nvarchar （450）</p></td>
<td><p>独特</p></td>
<td><p>URI 字符串。</p></td>
</tr>
<tr class="odd">
<td><p><strong>URIType</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>1 是未知 URI 类型。</p>
<p>2 是用户 URI。</p>
<p>4 是会议 URI。</p>
<p>8 是电话 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>TenantKey</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>用户的租户，被 Tenant 表引用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LastPoorCallTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>用户具有较差音频呼叫时的最新时间戳。</p></td>
</tr>
<tr class="even">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>仅供内部使用。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

