---
title: Lync Server 2013：FileTransfers 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FileTransfers table
ms:assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398353(v=OCS.15)
ms:contentKeyID: 48184118
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71e53e59e3ed1391adebff8b7c4046ef3c23aa21
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-table-in-lync-server-2013"></a>Lync Server 2013 中的 FileTransfers 表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-28_

每条记录表示一个文件传输会话。


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
<td><p>主、外部</p></td>
<td><p>会话请求的时间。 与<strong>SessionIdSeq</strong>结合使用以唯一标识会话。 有关详细信息, 请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主、外部</p></td>
<td><p>标识会话的 ID 号。 与<strong>SessionIdTime</strong>结合使用以唯一标识会话。 有关详细信息, 请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>文件名</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>文件的名称。</p></td>
</tr>
<tr class="even">
<td><p><strong>FileIdentity</strong></p></td>
<td><p>标识符</p></td>
<td></td>
<td><p>唯一标识符, 用于区分涉及相同文件名的文件传输。</p></td>
</tr>
<tr class="odd">
<td><p><strong>票证</strong></p></td>
<td><p>nvarchar</p></td>
<td><p>Primary</p></td>
<td><p>用于标识要与此邮件关联的每个后续消息。</p></td>
</tr>
<tr class="even">
<td><p><strong>容纳</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>可以为 TRUE 或 NULL。 如果为 TRUE, 则 "拒绝" 和 "取消" 将为 NULL。</p></td>
</tr>
<tr class="odd">
<td><p><strong>&</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>可以为 TRUE 或 NULL。 如果为 TRUE, 则 "接受" 和 "取消" 将为 NULL。</p></td>
</tr>
<tr class="even">
<td><p><strong>取消</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>可以为 TRUE 或 NULL。 如果为 TRUE, 则 "接受" 和 "拒绝" 将为 NULL。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

