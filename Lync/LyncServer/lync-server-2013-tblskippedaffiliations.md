---
title: Lync Server 2013： tblSkippedAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblSkippedAffiliations
ms:assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558611(v=OCS.15)
ms:contentKeyID: 48183373
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d21dbda8b649588e691d285c62ff865e9f001308
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141918"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblskippedaffiliations-in-lync-server-2013"></a>Lync Server 2013 中的 tblSkippedAffiliations

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-12_

tblSkippedAffiliations 包含无法读取的隶属关系（通常是由于 Active Directory 域服务访问错误而引起的）。

### <a name="columns"></a>Columns

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>类型</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prinID</p></td>
<td><p>int，不为 null</p></td>
<td><p>主体 ID。</p></td>
</tr>
<tr class="even">
<td><p>affDescription</p></td>
<td><p>nvarchar (256)，不为 null</p></td>
<td><p>标识隶属项的字符串。</p>
<p>格式为： guid： {0} uri： {1} &gt; id：{2}</p></td>
</tr>
<tr class="odd">
<td><p>updatedBy</p></td>
<td><p>int，不为 null</p></td>
<td><p>更新此行的主体的 ID。该值始终为 1（系统用户），因为 Active Directory 同步是这些条目的唯一来源。</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>Keys

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;prinID, affDescription&gt;</p></td>
<td><p>主键。</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>其查找包含在 tblPrincipal.prinID 表中的外键。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

