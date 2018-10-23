---
title: Lync Server 2013：VoipDetails 表
TOCTitle: VoipDetails 表
ms:assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398566(v=OCS.15)
ms:contentKeyID: 49313269
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 VoipDetails 表

 

_**上一次修改主题：** 2015-03-09_

每条记录均表示一个其中至少有一个用户是 VoIP 用户的双方呼叫。


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
<td><p>会话请求的时间。与 <strong>SessionIdSeq</strong> 结合使用来唯一地标识会话。有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的 Dialogs 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>用于标识会话的 ID 号。与 <strong>SessionIdTime</strong> 结合使用来唯一地标识会话。有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的 Dialogs 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromNumberId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫者的 <strong>PhoneId</strong> 。有关详细信息，请参阅 <a href="lync-server-2013-phones-table.md">Lync Server 2013 中的 Phones 表</a>。如果不为 null，并且 <strong>FromGatewayId</strong> 也为不为 null，则呼叫者是 PSTN 用户。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConnectedNumberId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫接收者的 <strong>PhoneId</strong> 。有关详细信息，请参阅 <a href="lync-server-2013-phones-table.md">Lync Server 2013 中的 Phones 表</a>。如果不为 null，并且 <strong>ToGatewayId</strong> 也为不为 null，则呼叫接收者是 PSTN 用户。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫的源中介服务器。有关详细信息，请参阅 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫的目标中介服务器。有关详细信息，请参阅 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromGatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫的源网关。有关详细信息，请参阅 <a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的 Gateways 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToGatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫的目标网关。有关详细信息，请参阅 <a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的 Gateways 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedbyURIId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>断开呼叫的用户的 URI（如果用户具有 URI）。有关详细信息，请参阅 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedbyPhoneId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>断开呼叫的电话的 ID。有关详细信息，请参阅 <a href="lync-server-2013-phones-table.md">Lync Server 2013 中的 Phones 表</a>。</p></td>
</tr>
</tbody>
</table>

