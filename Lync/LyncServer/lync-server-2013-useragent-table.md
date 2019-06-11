---
title: Lync Server 2013：UserAgent 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserAgent table
ms:assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398939(v=OCS.15)
ms:contentKeyID: 48185582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09bb2e3a71f81014bcb08952c03b59c93ac6a62f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845478"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragent-table-in-lync-server-2013"></a>Lync Server 2013 中的 UserAgent 表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-05-25_

UserAgent 表是一个支持表, 用于存储参与数据库中记录的会话的各种用户代理的列表。 表中的每条记录表示一个用户代理


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
<td><p><strong>UserAgentKey</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>标识此用户代理的唯一号码。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserAgent</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>唯一</p></td>
<td><p>用户代理字符串。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UAType</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>1是中介服务器。</p>
<p>2是 A/V 会议服务器。</p>
<p>4是 Lync。</p>
<p>8是 IP 电话。</p>
<p>16是 Live Meeting 控制台。</p>
<p>32是部署验证工具 (DVT)。</p>
<p>64是 Macintosh 计算机上的 Lync。</p>
<p>128是 Office 通信服务器 2007 R2 助理。</p>
<p>256是会议公告服务。</p>
<p>512是会议自动助理。</p>
<p>1024是响应组应用程序。</p>
<p>2048不在语音控制范围内。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

