---
title: Lync Server 2013：Endpoint 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Endpoint table
ms:assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398327(v=OCS.15)
ms:contentKeyID: 48184098
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11da225da1a8120f5de7ac21b3beb318326601f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="endpoint-table-in-lync-server-2013"></a>Lync Server 2013 中的 Endpoint 表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-02_

终结点表是一个支持表，用于存储参与数据库中记录的会话的终结点的相关信息。 表中的每条记录表示一个终结点。


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
<td><p>Primary</p></td>
<td><p>标识此终结点的唯一号码。</p></td>
</tr>
<tr class="even">
<td><p><strong>名称</strong> - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>唯一</p></td>
<td><p>终结点名称。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OS</strong></p></td>
<td><p>nvarchar</p></td>
<td><p> </p></td>
<td><p>终结点的操作系统（OS）。</p></td>
</tr>
<tr class="even">
<td><p><strong>CPUName</strong></p></td>
<td><p>nvarchar</p></td>
<td></td>
<td><p>终结点的 CPU 名称。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUNumberOfCores</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>终结点的 CPU 内核数。</p></td>
</tr>
<tr class="even">
<td><p><strong>CPUProcessorSpeed</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>终结点的 CPU 处理器速度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VirtualizationFlag</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>指示系统是否在虚拟化环境中运行的位标志：</p>
<ul>
<li><p>0x0000 –无</p></li>
<li><p>0x0001-HyperV</p></li>
<li><p>0x0002-VMWare</p></li>
<li><p>0x0004-虚拟电脑</p></li>
<li><p>0x0008-Xen 电脑</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

