---
title: Lync Server 2013： Server 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server table
ms:assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398801(v=OCS.15)
ms:contentKeyID: 48184890
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d95ca6af9a3e762a39142fcaf754d810050d83d3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200768"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-table-in-lync-server-2013"></a>Lync Server 2013 中的服务器表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-02_

Server 表是一个支持表。每个记录表示一台服务器。


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
<th><strong>Details</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ServerKey</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>标识服务器的唯一编号。</p></td>
</tr>
<tr class="even">
<td><p><strong>FQDNOrIP</strong></p></td>
<td><p>nvarchar （256）</p></td>
<td><p>index</p></td>
<td><p>MAC 地址字符串。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerType</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>1：中介服务器</p>
<p>2：A/V 会议服务器 16394：A/V 边缘服务 32769：网关</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolName</strong></p></td>
<td><p>nvarchar （512）</p></td>
<td></td>
<td><p>服务器所属的池。仅适用于 A/V 会议服务器。</p></td>
</tr>
<tr class="odd">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>仅供内部使用。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

