---
title: 'Lync Server 2013: FileTransfers 视图'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FileTransfers view
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49733848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4228bbe42f2e7bcf88b26f9147e514f09c106ac3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a>Lync Server 2013 中的 FileTransfers 视图

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-01_

FileTransfer 视图存储有关对等文件传输会话的信息。 此视图已在 Microsoft Lync Server 2013 中引入。

<div>


> [!NOTE]  
> FileTransfers 视图包含<A href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 的 SessionDetails 视图</A>中的所有列以及下面列出的列。



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
<td><p>nvarchar(256)</p></td>
<td><p>已传输的文件的名称。</p></td>
</tr>
<tr class="even">
<td><p><strong>票证</strong></p></td>
<td><p>nvarchar</p></td>
<td><p>用于标识要与此邮件关联的每个后续消息。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FileIdentity</strong></p></td>
<td><p>标识符</p></td>
<td><p>唯一标识符, 用于区分涉及相同文件名的文件传输。</p></td>
</tr>
<tr class="even">
<td><p><strong>容纳</strong></p></td>
<td><p>bit</p></td>
<td><p>可以为 TRUE 或 NULL。 如果为 TRUE, 则 "拒绝" 和 "取消" 将为 NULL。</p></td>
</tr>
<tr class="odd">
<td><p><strong>&</strong></p></td>
<td><p>bit</p></td>
<td><p>可以为 TRUE 或 NULL。 如果为 TRUE, 则 "接受" 和 "取消" 将为 NULL。</p></td>
</tr>
<tr class="even">
<td><p><strong>取消</strong></p></td>
<td><p>bit</p></td>
<td><p>可以为 TRUE 或 NULL。 如果为 TRUE, 则 "接受" 和 "拒绝" 将为 NULL。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

