---
title: Lync Server 2013： tblComplianceParticipant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceParticipant
ms:assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558655(v=OCS.15)
ms:contentKeyID: 48184262
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbadec18ba7054c7b58522129fca01da7d015e7e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblcomplianceparticipant-in-lync-server-2013"></a>Lync Server 2013 中的 tblComplianceParticipant

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-12_

tblComplianceParticipant 包含每个通道和每台服务器的当前参与者。

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
<td><p>channelUri</p></td>
<td><p>nvarchar (255)，不为 null</p></td>
<td><p>通道统一资源标识符 (URI)。</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>int，不为 null</p></td>
<td><p>参与者的主体 ID（与 tblPrincipal.prinID 表对应）。</p></td>
</tr>
<tr class="odd">
<td><p>joinedAt</p></td>
<td><p>bigint，不为 null</p></td>
<td><p>加入事件的时间戳。</p></td>
</tr>
<tr class="even">
<td><p>partedAt</p></td>
<td><p>bigint</p></td>
<td><p>如果仍加入参与者，则为 null。如果不为 null，则为通道离开事件的时间戳。</p>
<p>当所有转换器处理该事件时，将最终删除这些项。</p></td>
</tr>
<tr class="odd">
<td><p>userUri</p></td>
<td><p>nvarchar(255)，不为 null</p></td>
<td><p>用户 URI。</p></td>
</tr>
<tr class="even">
<td><p>serverID</p></td>
<td><p>int</p></td>
<td><p>服务器标识（如 tblServerIdentity.serverID 表中所示）。</p></td>
</tr>
<tr class="odd">
<td><p>sessionId</p></td>
<td><p>bigint</p></td>
<td><p>服务器会话。它是每次聊天服务启动时生成的随机数字。它用于区分会话以便标识孤立参与者。</p></td>
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
<td><p>&lt;channelUri、userId、joinedAt&gt;</p></td>
<td><p>主键。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

