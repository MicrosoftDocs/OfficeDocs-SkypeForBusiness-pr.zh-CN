---
title: Lync Server 2013： DeRegisterType 表
description: Lync Server 2013： DeRegisterType 表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DeRegisterType table
ms:assetid: 09148118-6209-4fd7-a494-99118689a245
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398142(v=OCS.15)
ms:contentKeyID: 48183346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afad63c2abeba3e91565e07dac75d0ac6c96ca3a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555348"
---
# <a name="deregistertype-table-in-lync-server-2013"></a>Lync Server 2013 中的 DeRegisterType 表

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-28_

DeRegisterType 表是一个静态表，用于存储可能的用户注销类型（例如“客户端已启动”、“注册过期”或“客户端停止响应”）的列表。


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
<td><p><strong>DeRegisterTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>DeRegisterReason</strong></p></td>
<td><p>nvarchar (256) </p></td>
<td></td>
<td><p>允许的值：</p>
<ul>
<li><p>0 -- 未知</p></li>
<li><p>1 -- 客户端启动的取消注册</p></li>
<li><p>2 -- 注册过期</p></li>
<li><p>3 – 客户端崩溃</p></li>
<li><p>4 -- 用户属性已更改</p></li>
<li><p>5 – 首选注册器已更改</p></li>
<li><p>6 -- 旧客户端处于生存模式</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

