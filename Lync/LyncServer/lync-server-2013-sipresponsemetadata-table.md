---
title: Lync Server 2013： SIPResponseMetaData 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIPResponseMetaData table
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205294(v=OCS.15)
ms:contentKeyID: 48185510
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 164c6e1541869a2976f283443f2fae9246f28007
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038854"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sipresponsemetadata-table-in-lync-server-2013"></a>Lync Server 2013 中的 SIPResponseMetaData 表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-28_

SIPResponseMetaDataTable 包含 SIP 响应代码的列表以及每种代码的分类和定义。在响应影响 SIP 设备和 SIP 通信会话的事件时生成这些代码；例如，当某个 SIP 设备发出请求，但服务器拒绝服从该请求时，将生成响应代码 403。

此表是在 Microsoft Lync Server 2013 中引入的。


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
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>表示 SIP 响应代码的数字值。</p></td>
</tr>
<tr class="even">
<td><p><strong>类</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>响应代码的常规分类。分类包括：</p>
<ul>
<li><p>1 – 信息响应</p></li>
<li><p>2 – 成功响应</p></li>
<li><p>3 – 重定向响应</p></li>
<li><p>4 – 客户端失败响应</p></li>
<li><p>5--服务器故障响应</p></li>
<li><p>6 – 全局失败响应</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>说明</strong></p></td>
<td><p>nvarchar （256）</p></td>
<td></td>
<td><p>SIP 响应代码的说明。例如，响应代码 181 的说明如下：</p>
<p>Call Is Being Forwarded</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

