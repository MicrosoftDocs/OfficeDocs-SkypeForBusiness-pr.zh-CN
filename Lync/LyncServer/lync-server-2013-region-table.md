---
title: Lync Server 2013：区域表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Region table
ms:assetid: 1751a6aa-a6e8-4f16-8eb7-ae731c2e3ee3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398235(v=OCS.15)
ms:contentKeyID: 48183518
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d48217ff0daa62a8f528829b85620e173626ca06
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536719"
---
# <a name="region-table-in-lync-server-2013"></a>Lync Server 2013 中的区域表

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2010-11-09_

区域表是一个支持表。每条记录代表网络配置设置中定义的一个国家/区域。


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
<td><p><strong>RegionKey</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>标识国家/区域的唯一编号。</p></td>
</tr>
<tr class="even">
<td><p><strong>RegionName</strong></p></td>
<td><p>nvarchar (128) </p></td>
<td><p>独特</p></td>
<td><p>国家/区域的名称。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

