---
title: Lync Server 2013：VoipDetails 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VoipDetails table
ms:assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398566(v=OCS.15)
ms:contentKeyID: 48184522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f13087202b15cf9b25f0c32741c396c48f628908
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-table-in-lync-server-2013"></a>Lync Server 2013 中的 VoipDetails 表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-28_

每条记录表示至少有一位用户是 VoIP 用户的 1 2 方呼叫。


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
<td><p>Primary</p></td>
<td><p>会话请求的时间。 与<strong>SessionIdSeq</strong>结合使用以唯一标识会话。 有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>标识会话的 ID 号。 与<strong>SessionIdTime</strong>结合使用以唯一标识会话。 有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromNumberId</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>呼叫方的<strong>PhoneId</strong> 。 有关详细信息，请参阅<a href="lync-server-2013-phones-table.md">Lync Server 2013 中</a>的 "电话" 表。 如果 not NULL 且<strong>FromGatewayId</strong>不为 null，则呼叫方是 PSTN 用户。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConnectedNumberId</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>呼叫接收器的<strong>PhoneId</strong> 。 有关详细信息，请参阅<a href="lync-server-2013-phones-table.md">Lync Server 2013 中</a>的 "电话" 表。 如果 not NULL 且<strong>ToGatewayId</strong>不为 null，则呼叫接收器是 PSTN 用户。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>呼叫来自的中介服务器。 有关详细信息，请参阅<a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>将调用的中介服务器将转到。 有关详细信息，请参阅<a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromGatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>呼叫的网关来自。 有关详细信息，请参阅<a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的网关表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToGatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>呼叫将转网网关。 有关详细信息，请参阅<a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的网关表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedbyURIId</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>断开呼叫的用户的 URI （如果用户具有 URI）。 有关详细信息，请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 "用户" 表。</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedbyPhoneId</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>断开通话的电话的 ID 已断开与电话的连接。 有关详细信息，请参阅<a href="lync-server-2013-phones-table.md">Lync Server 2013 中</a>的 "电话" 表。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

