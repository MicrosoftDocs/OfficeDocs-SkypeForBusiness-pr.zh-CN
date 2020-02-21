---
title: Lync Server 2013：会议表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference table
ms:assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425762(v=OCS.15)
ms:contentKeyID: 48183700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf7b6627f6976001bdb1440db9aa40c33d89cfc7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204436"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-table-in-lync-server-2013"></a>Lync Server 2013 中的会议表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-02_

会议表是一个支持表。每条记录代表一个会议或点对点会话。


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
<td><p><strong>ConferenceKey</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>标识该会议记录的唯一编号。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfURI</strong></p></td>
<td><p>nvarchar （450）</p></td>
<td><p>unique</p></td>
<td><p>如果是会议，则是会议 URI；如果是点对点会话，则是 DialogID。</p></td>
</tr>
<tr class="odd">
<td><p><strong>校验和</strong></p></td>
<td><p>int</p></td>
<td><p>index</p></td>
<td><p>会议 URI 的校验和。该项仅供内部使用。</p></td>
</tr>
<tr class="even">
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

