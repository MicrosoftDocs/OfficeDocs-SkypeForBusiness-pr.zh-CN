---
title: Lync Server 2013：tblChat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblChat
ms:assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615031(v=OCS.15)
ms:contentKeyID: 48185203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 620dcb49580f8d19a8f262c22b1005e3cefeac4e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845734"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblchat-in-lync-server-2013"></a>Lync Server 2013 中的 tblChat

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-12_

tblChat 包含所有聊天消息。

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
<td><p>channelId</p></td>
<td><p>int, not null</p></td>
<td><p>节点 ID。</p></td>
</tr>
<tr class="even">
<td><p>chatId</p></td>
<td><p>bigint, not null</p></td>
<td><p>定义由 tblLastChatId 表生成的聊天室顺序的唯一序列号 (每个节点 ID)。</p></td>
</tr>
<tr class="odd">
<td><p>chatDate</p></td>
<td><p>bigint, not null</p></td>
<td><p>聊天消息的时间戳。</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>int, not null</p></td>
<td><p>海报的主体 ID。</p></td>
</tr>
<tr class="odd">
<td><p>isAlert</p></td>
<td><p>位, not null</p></td>
<td><p>如果邮件是警告消息, 则为 True。 如果不是, 则为 False。</p></td>
</tr>
<tr class="even">
<td><p>内容</p></td>
<td><p>nvarchar (max), not null</p></td>
<td><p>聊天内容 (纯文本版本)。 内容通常为纯文本, 但有以下例外:</p>
<ul>
<li><p>文件表示为 ma-filelink: links。</p></li>
<li><p>链接表示为 HTML 元素 (尽管无法将内容类型视为 HTML)。</p></li>
<li><p>情景编码为 "[情景] ..."-类似格式。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>rtf</p></td>
<td><p>varchar (max)</p></td>
<td><p>聊天内容 (RTF 版本)。 如果客户端不提供, 则可能为 Null。</p></td>
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
<td><p>&lt;channelID, chatD&gt;</p></td>
<td><p>主键。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

