---
title: Lync Server 2013：ConferenceSessionDetails 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceSessionDetails table
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412741(v=OCS.15)
ms:contentKeyID: 48184925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61da586f3ecaf215b3bb636a80141ba8aaa19f18
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a>Lync Server 2013 中的 ConferenceSessionDetails 表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-28_

每个记录表示一个会议会话，该会话可以是与焦点的会话，也可以是与特定的会议服务器的会话。


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
<td><p>从中</p></td>
<td><p>主、外部</p></td>
<td><p>会话请求的时间;与<strong>SessionIdSeq</strong>结合使用以唯一标识会议会话。 有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主、外部</p></td>
<td><p>标识会话的 ID 号。 与<strong>SessionIdTime</strong>结合使用以唯一标识会议会话。 有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。 *</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>与此会话相关的焦点会议 URI。 有关详细信息，请参阅<a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表</a>。 此 URI 是基于焦点的会议 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>标识符</p></td>
<td></td>
<td><p>区分定期会议的实例的标识符。 每个定期会议实例具有相同的 ConferenceURI，但具有不同的 ConfInstance 值。</p>
<p>此字段是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>与此会话相关的会议服务器会议 URI。 有关详细信息，请参阅<a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表</a>。 此 URI 是基于会议服务器的会议 URI。 对于聚焦会议会话，此列将为 null。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>会议会话中一个用户的 ID。 有关详细信息，请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 "用户" 表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>标识符</p></td>
<td></td>
<td><p>标识终结点实例的 GUID。 例如，如果一个用户使用同一帐户登录到不同的计算机，则每台计算机都将具有不同的终结点 ID。</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfId</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>指明呼叫者代表的用户的 ID。 有关详细信息，请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 "用户" 表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredById</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>按呼叫者引用的用户的 ID。 有关详细信息，请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 "用户" 表。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>会议用户使用的客户端版本。 有关详细信息，请参阅<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConfClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>会议服务器使用的客户端版本。 有关详细信息，请参阅<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>外表</p></td>
<td><p>标识由当前会话替换的对话框的 ID 号。 有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>标识会话的 ID 号。 与<strong>ReplacesDialogIdTime</strong>结合使用以唯一标识此会话替换的会话。 有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsStartedByConfServer</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>指示会议服务器是否已启动会话。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsEndedByConfServer</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>指示会议服务器是否已结束会话。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>用户是否从内部登录。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>会话初始协议（SIP）响应代码到会话邀请。 此字段通常由会话中的初始邀请消息所生成的数据填充。 如果没有邀请消息，则该字段将填充第一个相关 SIP 邮件的日期和时间（再见、取消、消息或信息）。</p></td>
</tr>
<tr class="even">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>从 SIP 标题捕获的诊断 ID。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>用于此会话的前端服务器的 ID。 有关详细信息，请参阅<a href="lync-server-2013-servers-table.md">Lync Server 2013 中</a>的 "服务器" 表。</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>捕获会话的池的 ID。 有关详细信息，请参阅<a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 pool 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>通话所使用的中介服务器。 有关详细信息，请参阅<a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>GatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>呼叫使用的网关。 有关详细信息，请参阅<a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的网关表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>通话所使用的边缘服务器。 有关详细信息，请参阅<a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>会话中使用的内容类型。 有关详细信息，请参阅<a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 中的 ContentTypes 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>第一次邀请请求的时间。 此字段通常由会话中的初始邀请消息所生成的数据填充。 如果没有邀请消息，则该字段将填充第一个相关 SIP 邮件的日期和时间（再见、取消、消息或信息）。</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>第一次 SIP 响应的时间。 此字段通常由会话中的初始邀请消息所生成的数据填充。 如果没有邀请消息，则该字段将填充第一个相关 SIP 邮件的日期和时间（再见、取消、消息或信息）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionEndTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>会话结束的时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>外表</p></td>
<td><p><a href="lync-server-2013-uritypes-table.md">在 Lync Server 2013 中的 UriTypes 表中</a>包含 MCU URI 类型值。 此字段用于提高查询性能。</p>
<p>此字段是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserFlag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>指示用户属性的位集。 列出了以下属性定义：</p>
<ul>
<li><p>与桌面电话集成-1</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>指示通话属性的位集。 列出了以下属性定义：</p>
<ul>
<li><p>重试会话-1</p></li>
</ul></td>
</tr>
</tbody>
</table>


\*对于大多数会话，SessionIdSeq 将具有值1。 如果多个会话的开始时间完全相同，则一个会话的 SessionIdSeq 将为1，而另一个会话将为2，依此类推。

</div>

<span> </span>

</div>

</div>

</div>

