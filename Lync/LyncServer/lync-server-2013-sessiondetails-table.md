---
title: Lync Server 2013： SessionDetails 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionDetails table
ms:assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398589(v=OCS.15)
ms:contentKeyID: 48184559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b27721923e265bbb687b5df42b32e0fb6f25e92e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sessiondetails-table-in-lync-server-2013"></a>Lync Server 2013 中的 SessionDetails 表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-28_

每条记录表示一个点对点会话，它可以是 VoIP-VoIP 电话呼叫、双方 IM 会话或其他类型的会话。 您可以使用[Lync Server 2013 中的 media 表](lync-server-2013-media-table.md)执行表联接，以查找此会话中涉及的每个媒体的详细信息。

请注意，IsUser1IntegratedWithDeskPhone 和 IsUser2IntegratedWithDeskPhone 字段已从 Microsoft Lync Server 2013 中使用的 SessionDetails 表中删除。


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主、外</p></td>
<td><p>会话请求的时间。 与 <strong>SessionIdSeq</strong> 结合使用来唯一地标识会话。 有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主、外</p></td>
<td><p>用于标识会话的 ID 号。 与<strong>SessionIdTime</strong>结合使用以唯一标识会话。 * 有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CorrelationId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td></td>
<td><p>用于关联多个会话的 GUID。</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>对外</p></td>
<td><p>用于标识由当前会话取代的对话的 ID 号。 有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>用于标识会话的 ID 号。 与 <strong>ReplacesDialogIdTime</strong> 结合使用来唯一地标识由此会话取代的会话。 有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>User1Id</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>会话中的一个用户的 ID。 有关详细信息，请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2Id</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>会话中另一个用户的 ID。 有关详细信息，请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>User1EndpointId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td></td>
<td><p>标识会话中的第一个用户所使用的终结点的 GUID。</p>
<p>此字段是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2EndpointId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td></td>
<td><p>标识会话中的第二个用户所使用的终结点的 GUID。</p>
<p>此字段是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="even">
<td><p><strong>TargetUserId</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>SIP 请求中的原始目标用户 URI。 有关详细信息，请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionStartedById</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>启动会话的用户的 ID。 有关详细信息，请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfId</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>指示呼叫者所代表的用户的 ID。 有关详细信息，请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredById</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>引用呼叫的用户的 ID。 有关详细信息，请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>用于此会话的前端服务器的 ID。 有关详细信息，请参阅<a href="lync-server-2013-servers-table.md">Lync Server 2013 中的 Servers 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>在其中捕获会话的池的 ID。 有关详细信息，请参阅<a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 pool 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeID</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>会话中使用的内容类型。 有关详细信息，请参阅<a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 中的 ContentTypes 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>User1ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>User1 使用的客户端版本。 有关详细信息，请参阅<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>User2ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>User2 使用的客户端版本。 有关详细信息，请参阅<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>User1EdgeServerid</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>User1 使用的边缘服务器。 有关详细信息，请参阅<a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>User2EdgeServerid</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>User2 使用的边缘服务器。 有关详细信息，请参阅<a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUser1Internal</strong></p></td>
<td><p>位</p></td>
<td></td>
<td><p>User1 是否从内部登录。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUser2Internal</strong></p></td>
<td><p>位</p></td>
<td></td>
<td><p>User2 是否从内部登录。</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>第一个 INVITE 请求的时间。 此字段通常用从会话中的初始 INVITE 消息生成的数据填充。 如果没有 INVITE 消息，则此字段将用第一条相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。 此字段通常用从会话中的初始 INVITE 消息生成的数据填充。 如果没有 INVITE 消息，则此字段将用第一条相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>第一个 INVITE 消息的响应时间。 此字段通常用从会话中的初始 INVITE 消息生成的数据填充。 如果没有 INVITE 消息，则此字段将用第一条相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>会话邀请的 SIP 响应代码。此字段通常由来自会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则该字段由第一个相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</p></td>
</tr>
<tr class="even">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>从 SIP 标头捕获的诊断 ID。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallPriority</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>呼叫优先级。 有关详细信息，请参阅<a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 中的 CallPriorities 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>User1MessageCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>User1 在会话期间发送的消息数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2MessageCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>User2 在会话期间发送的消息数。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionEndTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>会话的结束时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaTypes</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>指示此会话的媒体类型的位集。下面列出了类型的定义：</p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>IM</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>FILE_TRANSFER</p></td>
<td><p>双面</p></td>
</tr>
<tr class="odd">
<td><p>REMOTE_ASSISTANCE</p></td>
<td><p>4</p></td>
</tr>
<tr class="even">
<td><p>APP_SHARING</p></td>
<td><p>8 </p></td>
</tr>
<tr class="odd">
<td><p>视频</p></td>
<td><p>16 </p></td>
</tr>
<tr class="even">
<td><p>显示</p></td>
<td><p>32</p></td>
</tr>
<tr class="odd">
<td><p>APP_INVITE</p></td>
<td><p>64</p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><strong>User1Flag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>指示 User1 属性的位集。列出了以下属性定义：</p>
<ul>
<li><p>0x01 - 与桌面电话集成</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>User2Flag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>指示 User2 属性的位集。列出了以下属性定义：</p>
<ul>
<li><p>0x01 - 与桌面电话集成</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>指示呼叫属性的位集。列出了以下属性定义：</p>
<ul>
<li><p>0x01 - 重试会话</p></li>
<li><p>0x02 - 代表响应组的代理进行的呼叫</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>处理</strong></p></td>
<td><p>位</p></td>
<td></td>
<td><p>供监控服务内部使用。</p>
<p>此字段是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
</tbody>
</table>


\*对于大多数会话，SessionIdSeq 的值将为1。 如果多个会话完全同时启动，则一个会话的 SessionIdSeq 将为 1，另一个会话的 SessionIdSeq 将为 2，依此类推。

</div>

<span> </span>

</div>

</div>

</div>

