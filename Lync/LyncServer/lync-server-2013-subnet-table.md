---
title: Lync Server 2013：Subnet 表
TOCTitle: Subnet 表
ms:assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398582(v=OCS.15)
ms:contentKeyID: 49313299
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 Subnet 表

 

_**上一次修改主题：** 2015-03-09_

Subnet 表是一个支持表。每条记录均表示网络配置设置中定义的一个子网。


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
<td><p><strong>SubnetIP</strong></p></td>
<td><p>int</p></td>
<td><p>主、外</p></td>
<td><p>子网 IP 的整数表示形式。</p></td>
</tr>
<tr class="even">
<td><p><strong>SubnetMask</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>子网掩码。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserSiteKey</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>引用自 <a href="lync-server-2013-usersite-table.md">Lync Server 2013 中的 UserSite 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>SubnetDescription</strong></p></td>
<td><p>nvarchar (512)</p></td>
<td><p></p></td>
<td><p>子网的说明。</p></td>
</tr>
</tbody>
</table>

