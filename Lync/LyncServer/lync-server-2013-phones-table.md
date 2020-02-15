---
title: Lync Server 2013：电话表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Phones table
ms:assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425923(v=OCS.15)
ms:contentKeyID: 48183996
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53c3a67381a101bd9aecc4872d4e08b4fb8daea3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phones-table-in-lync-server-2013"></a>Lync Server 2013 中的电话表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-08-20_

电话表是支持表格。 表中的每条记录存储在包含数据库中的记录的 VoIP 呼叫中涉及的一个电话号码的相关信息。


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
<td><p><strong>PhoneId</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>标识此电话的唯一号码。</p></td>
</tr>
<tr class="even">
<td><p><strong>PhoneUri</strong></p></td>
<td><p>nvarchar （450）</p></td>
<td><p> </p></td>
<td><p>电话号码。</p></td>
</tr>
<tr class="odd">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>dateTime</p></td>
<td></td>
<td><p>时间戳（仅供内部使用）。</p>
<p>此字段是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

