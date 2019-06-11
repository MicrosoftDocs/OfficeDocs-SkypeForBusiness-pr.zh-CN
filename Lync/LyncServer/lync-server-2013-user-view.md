---
title: 'Lync Server 2013: 用户视图'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User view
ms:assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688100(v=OCS.15)
ms:contentKeyID: 49733699
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21c22bdfbf758545418a821edaba5d8aaf447b87
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845481"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-view-in-lync-server-2013"></a>Lync Server 2013 中的用户视图

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-01_

"用户" 视图存储与在数据库中具有记录的通话或会话中参与的用户的相关信息。 此视图已在 Microsoft Lync Server 2013 中引入。


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
<td><p>UserId</p></td>
<td><p>int</p></td>
<td><p>标识此用户的唯一号码。</p></td>
</tr>
<tr class="even">
<td><p>UserUri</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>用户的 Uri。</p></td>
</tr>
<tr class="odd">
<td><p>TenantKey</p></td>
<td><p>标识符</p></td>
<td><p>用户的租户。 有关详细信息, 请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</p></td>
</tr>
<tr class="even">
<td><p>UriType</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>用户 URI 的类型。 有关详细信息, 请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

