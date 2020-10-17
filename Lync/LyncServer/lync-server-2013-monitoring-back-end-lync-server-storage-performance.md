---
title: Lync Server 2013：监视后端 Lync Server 存储性能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring back end Lync Server 2013 storage performance
ms:assetid: 71627c70-1953-4ac2-afbe-f3ad85be0f44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720917(v=OCS.15)
ms:contentKeyID: 63969619
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aad04524df22c9d299b4a871b580330052d2aa5b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531949"
---
# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a>监视后端 Lync Server 2013 存储性能

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-05-02_

Lync Server 2013 后端数据库是 Lync Server 2013 部署的一个非常重要的部分。 我们建议持续监视数据库和相应的事务日志，以帮助确保 Lync Server 2013 后端能够以最佳方式执行。

下表列出了应监视的性能计数器，以了解有关存储性能的信息。 当系统处于其正常) 负载时，必须首先确定这些计数器的比较基准值 (，以了解系统压力时的性能变化。

### <a name="performance-counters-to-be-monitored"></a>要监视的性能计数器

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>性能计数器</th>
<th>基准阈值</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>每秒事务数 (RTC) </p></td>
<td></td>
</tr>
<tr class="even">
<td><p>每秒事务数 (rtcdyn) </p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>每秒事务数 (tempdb) </p></td>
<td></td>
</tr>
<tr class="even">
<td><p> (RTC) 的日志刷新数/秒</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>日志刷新次数/秒 (rtcdyn) </p></td>
<td></td>
</tr>
<tr class="even">
<td><p>日志刷新次数/秒 (tempdb) </p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>磁盘传输/秒 (读写) RTC db</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>磁盘传输/秒-RTC 日志</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>磁盘传输数/秒-rtcdyn db</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>磁盘传输数/秒-rtcdyn 日志</p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

