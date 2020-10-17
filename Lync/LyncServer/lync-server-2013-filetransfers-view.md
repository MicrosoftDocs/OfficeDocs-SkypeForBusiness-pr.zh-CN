---
title: Lync Server 2013： FileTransfers 视图
description: Lync Server 2013： FileTransfers 视图。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers view
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49733848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd2b084274a4d5daa093f2269617214f703ac03e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552618"
---
# <a name="filetransfers-view-in-lync-server-2013"></a>Lync Server 2013 中的 FileTransfers 视图

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-01_

FileTransfer 视图存储有关对等文件传输会话的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。

<div>


> [!NOTE]  
> FileTransfers 视图包含在 <A href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 的 SessionDetails 视图</A> 中的所有列，此外还列出了下面列出的列。



</div>


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
<td><p><strong>FileName</strong></p></td>
<td><p>nvarchar (256) </p></td>
<td><p>文件传输的名称。</p></td>
</tr>
<tr class="even">
<td><p><strong>Cookie</strong></p></td>
<td><p>nvarchar (128) </p></td>
<td><p>用于标识与此关联时的每条后续消息。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FileIdentity</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>涉及相同文件名的文件传输之间标识的唯一标识符。</p></td>
</tr>
<tr class="even">
<td><p><strong>Accept</strong></p></td>
<td><p>位</p></td>
<td><p>可以是 TRUE 或 NULL。如果是 TRUE，则拒绝和取消将为 NULL。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Reject</strong></p></td>
<td><p>位</p></td>
<td><p>可以是 TRUE 或 NULL。如果是 TRUE，则接受和取消将为 NULL。</p></td>
</tr>
<tr class="even">
<td><p><strong>Cancel</strong></p></td>
<td><p>位</p></td>
<td><p>可以是 TRUE 或 NULL。如果是 TRUE，则接受和拒绝将为 NULL。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

