---
title: Lync Server 2013：UserSite 表
TOCTitle: UserSite 表
ms:assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398256(v=OCS.15)
ms:contentKeyID: 49312171
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 UserSite 表

 

_**上一次修改主题：** 2015-03-09_

UserSite 表是一个支持表。每条记录代表一个在网络配置设置中定义的用户站点。


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
<td><p><strong>UserSiteKey</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>标识用户站点的唯一编号。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserSiteName</strong></p></td>
<td><p>nvarchar (128)</p></td>
<td><p>唯一</p></td>
<td><p>用户站点的名称。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RegionKey</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>引用自 <a href="lync-server-2013-region-table.md">Lync Server 2013 中的 Region 表</a>。</p></td>
</tr>
</tbody>
</table>

