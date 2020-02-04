---
title: Lync Server 2013： ConferenceMessageCount 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceMessageCount view
ms:assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688129(v=OCS.15)
ms:contentKeyID: 49733727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73944e1561b88301b740fcb52cf301645154c6e7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-view-in-lync-server-2013"></a>Lync Server 2013 中的 ConferenceMessageCount 视图

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-01_

ConferenceMessageCount 视图存储有关用户向会议发送的邮件数的信息。 此视图已在 Microsoft Lync Server 2013 中引入。

<div>


> [!NOTE]  
> ConferenceMessageCount 视图包含<A href="lync-server-2013-conferencesessiondetails-view.md">Lync Server 2013 的 ConferenceSessionDetails 视图</A>中的所有列以及下面列出的列。



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>数据类型</th>
<th>详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar （450）</p></td>
<td><p>发送邮件的用户的 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>发送邮件的用户的 URI 类型。 有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant</strong></p></td>
<td><p>标识符</p></td>
<td><p>发送消息的用户的租户。 有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserMessageCount</strong></p></td>
<td><p>smallint</p></td>
<td><p>在会议会话期间用户发送的消息数。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

