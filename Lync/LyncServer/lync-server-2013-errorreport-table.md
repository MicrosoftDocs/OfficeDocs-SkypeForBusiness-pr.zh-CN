---
title: Lync Server 2013： ErrorReport 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport table
ms:assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412826(v=OCS.15)
ms:contentKeyID: 48185129
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 321a975e9461e39de882d9620cdded9d2554e8ed
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533135"
---
# <a name="errorreport-table-in-lync-server-2013"></a>Lync Server 2013 中的 ErrorReport 表

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-28_

ErrorReport 表存储有关已发生的错误的信息。 每条记录代表发生一次错误。 错误由在前端服务器上运行的 CDR 代理捕获或发送自客户端。


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
<td><p><strong>ErrorTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主</p></td>
<td><p>错误发生的日期和时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>标识错误报告的 ID 号。 与 <strong>ErrorTime</strong> 结合使用，以唯一标识错误报告。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorId</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>错误类型的唯一 ID。 有关详细信息，请参阅 <a href="lync-server-2013-errordef-table.md">Lync Server 2013 中的 ErrorDef 表</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUserId</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>发出导致错误的请求的用户。 有关详细信息，请参阅 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUserId</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>导致错误的请求的目标用户。 有关详细信息，请参阅 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>与错误相关的会议 URI。 有关详细信息，请参阅 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表</a> 。 通常情况下，如果 ConferenceUriId 不为 null，则 FromUserId 或 ToUserId 将为 null。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>对外</p></td>
<td><p>与 <strong>SessionIdSeq</strong> 结合使用来唯一地标识会话。 有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>用于标识会话的 ID 号。 与 <strong>SessionIdTime</strong> 结合使用来唯一地标识会话。 有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SourceId</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>发送错误报告的服务器 (如果正在从服务器组件) 发送报告。 有关详细信息，请参阅 <a href="lync-server-2013-servers-table.md">Lync Server 2013 中的 Servers 表</a> 。</p>
<p>此字段是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="even">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>发送错误报告的服务器 (如果正在从服务器组件) 发送报告。 有关详细信息，请参阅 <a href="lync-server-2013-application-table.md">Lync Server 2013 中的应用程序表</a> 。</p>
<p>此字段是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>image</p></td>
<td><p> </p></td>
<td><p>有关错误的详细信息。</p>
<p>可以使用以下语法将此数据转换为文本格式：</p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><strong>ClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>发送错误报告的终结点的客户端版本。 有关详细信息，请参阅 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsCapturedByServer</strong></p></td>
<td><p>位</p></td>
<td></td>
<td><p>是由在前端服务器上运行的 CDR 代理捕获的或由客户端发送的错误报告。</p></td>
</tr>
<tr class="even">
<td><p><strong>Flag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>保留以供将来使用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td></td>
<td><p>关联会议中所涉及不同组件的加入时间信息的唯一标识符。</p>
<p>此字段是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>特定组件加入会议所需的时间（以毫秒为单位）。</p>
<p>此字段是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>表示生成错误报告的服务器的完全限定的域名。</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>表示生成错误报告的池的完全限定的域名。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

