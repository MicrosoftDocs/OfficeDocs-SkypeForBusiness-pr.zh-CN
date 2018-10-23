---
title: Lync Server 2013：tblAdminLock
TOCTitle: tblAdminLock
ms:assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg558665(v=OCS.15)
ms:contentKeyID: 49313311
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 tblAdminLock

 

_**上一次修改主题：** 2015-03-09_

tblAdminLock 包含运行一些管理员命令所需的管理员锁。

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
<td><p>lockExpiresTime</p></td>
<td><p>datetime，不为 null</p></td>
<td><p>锁到期日期和时间。所有者可以定期延长该值。</p></td>
</tr>
<tr class="even">
<td><p>lockServerID</p></td>
<td><p>int，不为 null</p></td>
<td><p>拥有锁的服务器的 ID。</p></td>
</tr>
<tr class="odd">
<td><p>lockActorID</p></td>
<td><p>int，不为 null</p></td>
<td><p>拥有锁的主体的 ID。</p></td>
</tr>
</tbody>
</table>

