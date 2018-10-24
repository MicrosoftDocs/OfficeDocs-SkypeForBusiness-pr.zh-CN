---
title: Lync Server 2013：Endpoint 表
TOCTitle: Endpoint 表
ms:assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398327(v=OCS.15)
ms:contentKeyID: 49312823
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 Endpoint 表

 

_**上一次修改主题：** 2015-03-09_

Endpoint 表是一个支持表，用于存储有关参与数据库中所记录会话的终结点的信息。表中的每条记录都代表一个终结点。


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
<td><p><strong>EndpointKey</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>标识此终结点的唯一号码。</p></td>
</tr>
<tr class="even">
<td><p><strong>Name</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>唯一</p></td>
<td><p>终结点名称。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OS</strong></p></td>
<td><p>nvarchar (128)</p></td>
<td><p> </p></td>
<td><p>终结点的操作系统 (OS)。</p></td>
</tr>
<tr class="even">
<td><p><strong>CPUName</strong></p></td>
<td><p>nvarchar (128)</p></td>
<td><p></p></td>
<td><p>终结点的 CPU 名称。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUNumberOfCores</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>终结点的 CPU 内核数。</p></td>
</tr>
<tr class="even">
<td><p><strong>CPUProcessorSpeed</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>终结点的 CPU 处理器速度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VirtualizationFlag</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>指示系统是否在虚拟环境中运行的位标志：</p>
<ul>
<li><p>0x0000 – 无</p></li>
<li><p>0x0001 – HyperV</p></li>
<li><p>0x0002 – VMWare</p></li>
<li><p>0x0004 – 虚拟 PC</p></li>
<li><p>0x0008 – Xen PC</p></li>
</ul></td>
</tr>
</tbody>
</table>

