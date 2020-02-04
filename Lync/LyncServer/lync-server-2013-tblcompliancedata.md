---
title: Lync Server 2013：tblComplianceData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceData
ms:assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558606(v=OCS.15)
ms:contentKeyID: 48183308
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48516f307a084d30fde06a03548119e0ada34d6a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731502"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancedata-in-lync-server-2013"></a>Lync Server 2013 中的 tblComplianceData

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-12_

tblComplianceData 包含尚未由合规性适配器处理的合规性事件。

### <a name="columns"></a>多

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
<td><p>cmplEventID</p></td>
<td><p>bigint，not null</p></td>
<td><p>事件 ID。</p></td>
</tr>
<tr class="even">
<td><p>entryDate</p></td>
<td><p>smalldatetime，not null</p></td>
<td><p>插入时间（对于 cmplType = 9，将来可能会是很远），因为在该情况下，条目只是占位符。</p></td>
</tr>
<tr class="odd">
<td><p>cmplType</p></td>
<td><p>int，not null</p></td>
<td><p>合规性事件的类型：</p>
<ul>
<li><p>1：聊天</p></li>
<li><p>2： Backchat</p></li>
<li><p>3：文件下载</p></li>
<li><p>4：文件上载</p></li>
<li><p>9：临时文件传输</p></li>
<li><p>10：删除聊天（带替换）</p></li>
<li><p>11：聊天清除</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>cmplTime</p></td>
<td><p>bigint，not null</p></td>
<td><p>事件的时间戳。</p></td>
</tr>
<tr class="odd">
<td><p>cmplChannelUri</p></td>
<td><p>nvarchar （255），not null</p></td>
<td><p>通道统一资源标识符（URI）。</p></td>
</tr>
<tr class="even">
<td><p>cmplChatID</p></td>
<td><p>bigint</p></td>
<td><p>聊天 ID （对应于 tblChat 表）。</p></td>
</tr>
<tr class="odd">
<td><p>cmplUserID</p></td>
<td><p>int，not null</p></td>
<td><p>海报的主体 ID （对应于 tblPrincipal 表）。</p></td>
</tr>
<tr class="even">
<td><p>cmplUserUri</p></td>
<td><p>nvarchar （255），not null</p></td>
<td><p>用户 URI。</p></td>
</tr>
<tr class="odd">
<td><p>cmplMessage</p></td>
<td><p>nvarchar （max）</p></td>
<td><p>邮件（编码取决于 cmplType）。</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>关键字

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
<td><p>cmplEventID</p></td>
<td><p>主键。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

