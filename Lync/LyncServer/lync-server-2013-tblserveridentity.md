---
title: Lync Server 2013：tblServerIdentity
TOCTitle: tblServerIdentity
ms:assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg558648(v=OCS.15)
ms:contentKeyID: 49312865
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 tblServerIdentity

 

_**上一次修改主题：** 2015-03-09_

tblServerIdentity 包含 持久聊天服务器池中的活动聊天服务器。

### 列

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
<td><p>serverID</p></td>
<td><p>int，不为 null</p></td>
<td><p>服务器 ID。对应于 中央管理存储中的实例 ID。</p></td>
</tr>
<tr class="even">
<td><p>serverAddress</p></td>
<td><p>nvarchar (256)，不为 null</p></td>
<td><p>使用 Windows Communication Foundation 地址的服务器地址。</p></td>
</tr>
<tr class="odd">
<td><p>serverLastPingTime</p></td>
<td><p>datetime</p></td>
<td><p>通道服务器更新此行以表明服务器正在运行的最新时间。</p></td>
</tr>
</tbody>
</table>


### 按键

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
<td><p>serverID</p></td>
<td><p>主键。</p></td>
</tr>
</tbody>
</table>

