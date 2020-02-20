---
title: Lync Server 2013： SessionDetails 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionDetails view
ms:assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721924(v=OCS.15)
ms:contentKeyID: 49733859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f7a143a0812b19a840c7eb339e80611720a08b3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143786"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a>Lync Server 2013 中的 SessionDetails 视图

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-01_

SessionDetails 视图存储有关点对点会话的信息，这应该是 VoIP-VoIP 电话呼叫、双方 IM 会话或其他类型的会话。 此视图是在 Microsoft Lync Server 2013 中引入的。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>数据类型</th>
<th>详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>会话请求的时间。 与 SessionIdSeq 结合使用来唯一地标识会话。 有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 表中的对话框表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>用于标识会话的 ID 号。 与 SessionIdTime 结合使用来唯一地标识会话。 有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>第一个 INVITE 请求的时间。此字段通常由从会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则该字段由第一个相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUri</strong></p></td>
<td><p>nvarchar （450）</p></td>
<td><p>启动会话的用户的 URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUri</strong></p></td>
<td><p>nvarchar （450）</p></td>
<td><p>加入会话的用户的 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUriType</strong></p></td>
<td><p>nvarchar （256）</p></td>
<td><p>启动会话的用户的 URI 的类型。 有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUriType</strong></p></td>
<td><p>nvarchar （256）</p></td>
<td><p>加入会话的用户的 URI 的类型。 有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromTenant</strong></p></td>
<td><p>nvarchar （450）</p></td>
<td><p>启动会话的用户的租户。 有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToTenant</strong></p></td>
<td><p>nvarchar （256）</p></td>
<td><p>加入会话的用户的租户。 有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromEndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>启动会话的用户的终结点的唯一标识符。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToEndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>加入会话的用户的终结点的唯一标识符。</p></td>
</tr>
<tr class="even">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>会话的结束时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMessageCount</strong></p></td>
<td><p>int</p></td>
<td><p>启动会话的用户发送的消息数。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMessageCount</strong></p></td>
<td><p>int</p></td>
<td><p>加入会话的用户发送的消息数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromClientVersion</strong></p></td>
<td><p>nvarchar （256）</p></td>
<td><p>启动会话的用户使用的客户端的版本。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromClientType</strong></p></td>
<td><p>int</p></td>
<td><p>启动会话的用户使用的客户端。 有关更多详细信息，请参阅<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromClientCategory</strong></p></td>
<td><p>nvarchar （64）</p></td>
<td><p>启动会话的用户使用的客户端的类别名称。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToClientVersion</strong></p></td>
<td><p>nvarchar （256）</p></td>
<td><p>加入会话的用户使用的客户端的版本。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToClientType</strong></p></td>
<td><p>int</p></td>
<td><p>加入会话的用户使用的客户端。 有关更多详细信息，请参阅<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToClientCategory</strong></p></td>
<td><p>nvarchar （64）</p></td>
<td><p>加入会话的用户使用的客户端的类别名称。</p></td>
</tr>
<tr class="odd">
<td><p><strong>TargetUri</strong></p></td>
<td><p>nvarchar （450）</p></td>
<td><p>会话的目标用户的 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>TargetUriType</strong></p></td>
<td><p>nvarchar （450）</p></td>
<td><p>会话的目标用户的 URI 的类型。 有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OnBehalfOfUri</strong></p></td>
<td><p>nvarchar （450）</p></td>
<td><p>代表启动会话的用户的 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>OnnnBehalfOfUriType</strong></p></td>
<td><p>nvarchar （256）</p></td>
<td><p>代表启动会话的用户的 URI 的类型。 有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OnBehalfOfTenant</strong></p></td>
<td><p>nvarchar （256）</p></td>
<td><p>代表启动会话的用户的租户。 有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>ReferredByUri</strong></p></td>
<td><p>nvarchar （450）</p></td>
<td><p>提交会话的用户的 URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredByUriType</strong></p></td>
<td><p>nvarchar （256）</p></td>
<td><p>提交会话的用户的 URI 的类型。 有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>ReferredByTenant</strong></p></td>
<td><p>nvarchar （256）</p></td>
<td><p>提交会话的用户的租户。 有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogId</strong></p></td>
<td><p>varchar （775）</p></td>
<td><p>SIP 对话 ID。格式为：</p>
<p>对话框; 从-标签; 到-标记</p></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>用于关联多个会话的 GUID。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>由会话取代的对话的时间。 与 ReplaceDialogIdSeq 结合起来使用，以唯一地标识由此会话取代的对话。 有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>用于标识会话的 ID 号。 与 ReplacesDialogIdTime 结合使用来唯一地标识由该会话取代的会话。 有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplacesDialogId</strong></p></td>
<td><p>varchar （775）</p></td>
<td><p>会话取代的 SIP 对话 ID。格式为：</p>
<p>对话框; 从-标签; 到-标记</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>对第一个 INVITE 消息的响应时间。此字段通常由来自会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则该字段由第一个相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>会话邀请的 SIP 响应代码。此字段通常由来自会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则该字段由第一个相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</p></td>
</tr>
<tr class="even">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td><p>从 SIP 标头捕获的诊断 ID。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ContentType</strong></p></td>
<td><p>nvarchar （256）</p></td>
<td><p>会话内容的类型。</p></td>
</tr>
<tr class="even">
<td><p><strong>前端</strong></p></td>
<td><p>nvarchar （256）</p></td>
<td><p>捕获会话数据的前端服务器的 FQDN。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar （256）</p></td>
<td><p>捕获会话数据的池的 FQDN。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromEdgeServer</strong></p></td>
<td><p>nvarchar （256）</p></td>
<td><p>启动会话的用户使用的边缘服务器的 FQDN。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToEdgeServer</strong></p></td>
<td><p>nvarchar （256）</p></td>
<td><p>启动会话的用户使用的边缘服务器的 FQDN</p></td>
</tr>
<tr class="even">
<td><p><strong>IsFromInternal</strong></p></td>
<td><p>位</p></td>
<td><p>指示启动会话的用户是否从内部网络登录。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsToInternal</strong></p></td>
<td><p>位</p></td>
<td><p>指示加入会话的用户是否从内部网络登录。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallPriority</strong></p></td>
<td><p>nvarchar （256）</p></td>
<td><p>会话的呼叫属性。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromUserFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p>指示启动会话的用户的属性。允许以下属性定义：</p>
<p>0x01 - 与桌面电话集成</p></td>
</tr>
<tr class="even">
<td><p><strong>ToUserFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p>指示启动会话的用户的属性。允许以下属性定义：</p>
<p>0x01 - 与桌面电话集成</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p>指示呼叫属性。允许以下属性定义：</p>
<p>0x01 - 重试会话</p>
<p>0x02 - 代表响应组的代理进行的呼叫</p></td>
</tr>
<tr class="even">
<td><p><strong>Location</strong></p></td>
<td><p>varchar （max）</p></td>
<td><p>紧急呼叫的位置。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

