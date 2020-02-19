---
title: Lync Server 2013：会议表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences table
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412964(v=OCS.15)
ms:contentKeyID: 48185340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8cbb42d078ccba029ae0cf55c7b1ced803aa94f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferences-table-in-lync-server-2013"></a>Lync Server 2013 中的 "会议" 表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-28_

此表中的每条记录都包含有关一个会议的呼叫详细信息。


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主</p></td>
<td><p>由 CDR 代理捕获会议请求的时间。 仅用作用于唯一标识会议实例的主键。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>用于标识会话的 ID 号。 与<strong>SessionIdTime</strong>结合使用，以唯一标识会议实例。 *</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>会议 URI。 有关详细信息，请参阅<a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p> </p></td>
<td><p>对定期会议有用;每个定期会议实例都具有相同的<strong>ConferenceUri</strong>，但将具有不同的<strong>ConfInstance</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceStartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>会议开始时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceEndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>会议开始时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>标识在其中捕获会议的池的 ID 号。 有关详细信息，请参阅<a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 pool 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>OrganizerId</strong></p></td>
<td><p>Int</p></td>
<td><p>对外</p></td>
<td><p>标识此会议的组织者 URI 的 ID 号。 有关详细信息，请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Flag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>包含会议属性的位掩码。 可能的值是：</p>
<ul>
<li><p>0X01</p></li>
<li><p>合成</p></li>
<li><p>事务</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>处理</strong></p></td>
<td><p>位</p></td>
<td></td>
<td><p>监视服务使用的内部字段。</p>
<p>此字段是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
</tbody>
</table>


\*对于大多数会话，SessionIdSeq 的值将为1。 如果两个会话完全启动，则一个会话的 SessionIdSeq 将为1，而另一个会话将为2，依此类推。

</div>

<span> </span>

</div>

</div>

</div>

