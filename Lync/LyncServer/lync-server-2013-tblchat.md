---
title: Lync Server 2013： tblChat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblChat
ms:assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615031(v=OCS.15)
ms:contentKeyID: 48185203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efadf0e5e850b825f6e5f47928e615ba32b9fd33
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207228"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblchat-in-lync-server-2013"></a>Lync Server 2013 中的 tblChat

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-12_

tblChat 表包含所有聊天消息。

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
<td><p>channelId</p></td>
<td><p>int，不为 null</p></td>
<td><p>节点 ID。</p></td>
</tr>
<tr class="even">
<td><p>chatId</p></td>
<td><p>bigint，不为 null</p></td>
<td><p>由 tblLastChatId 表生成的用于确定聊天室顺序的唯一序列号（每个节点 ID 一个）。</p></td>
</tr>
<tr class="odd">
<td><p>chatDate</p></td>
<td><p>bigint，不为 null</p></td>
<td><p>聊天消息的时间戳。</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>int，不为 null</p></td>
<td><p>发布者的主要 ID。</p></td>
</tr>
<tr class="odd">
<td><p>isAlert</p></td>
<td><p>bit，不为 null</p></td>
<td><p>如果消息是警报消息，则为 True。否则为 False。</p></td>
</tr>
<tr class="even">
<td><p>content</p></td>
<td><p>nvarchar (max)，不为 null</p></td>
<td><p>聊天内容（纯文本版本）。该内容通常为纯文本，但以下情况除外：</p>
<ul>
<li><p>文件表示为 ma-filelink: 链接。</p></li>
<li><p>链接表示为 HTML 元素（但内容类型不能被视为 HTML）。</p></li>
<li><p>文章以类似“[STORY]....”的格式编码。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>rtf</p></td>
<td><p>varchar （max）</p></td>
<td><p>聊天内容（RTF 版本）。如果客户端未提供该内容，可能为 Null。</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>键

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

