---
title: MonitoredUserSiteLink 表
TOCTitle: MonitoredUserSiteLink 表
ms:assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398233(v=OCS.15)
ms:contentKeyID: 49312115
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# MonitoredUserSiteLink 表

 

_**上一次修改主题：** 2015-03-09_

MonitoredUserSiteLink 表是一个支持表。每条记录代表两个用户站点之间的一个链接。


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
<th><strong>详细信息</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>UserSite1Key</strong></p></td>
<td><p>int</p></td>
<td><p>主、外</p></td>
<td><p>引用自 <a href="lync-server-2013-usersite-table.md">Lync Server 2013 中的 UserSite 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserSite2Key</strong></p></td>
<td><p>int</p></td>
<td><p>主、外</p></td>
<td><p>引用自 <a href="lync-server-2013-usersite-table.md">Lync Server 2013 中的 UserSite 表</a>。</p></td>
</tr>
</tbody>
</table>

