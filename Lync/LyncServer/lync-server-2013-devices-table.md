---
title: Lync Server 2013：Devices 表
TOCTitle: Devices 表
ms:assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398351(v=OCS.15)
ms:contentKeyID: 49312857
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 Devices 表

 

_**上一次修改主题：** 2015-03-09_

Devices 表是一个支持表。每条记录存储有关一个设备（桌面电话）的信息。


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
<td><p><strong>DeviceId</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>用于标识此硬件版本的唯一编号。</p></td>
</tr>
<tr class="even">
<td><p><strong>ManufacturerId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>此设备的制造商。有关详细信息，请参阅 <a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 中的 Manufacturers 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>HardwareVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>此设备的硬件版本。有关详细信息，请参阅 <a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 中的 HardwareVersions 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>MacAddress</strong></p></td>
<td><p>bigint</p></td>
<td><p></p></td>
<td><p>MAC 地址</p></td>
</tr>
</tbody>
</table>

