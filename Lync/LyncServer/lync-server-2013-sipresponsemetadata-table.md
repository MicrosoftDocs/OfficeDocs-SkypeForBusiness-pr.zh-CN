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
ms.openlocfilehash: 1fcd6cb462bd64f6fdcdbae93cfb733de0639898
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731912"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sipresponsemetadata-table-in-lync-server-2013"></a>Lync Server 2013 中的 SIPResponseMetaData 表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-28_

SIPResponseMetaDataTable 包含 SIP 响应代码列表以及每个代码的分类和定义。 系统会生成这些代码，以响应影响 SIP 设备和 SIP 通信会话的事件;例如，在 SIP 设备发出请求时，将生成响应代码403，但服务器拒绝接受该请求。

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
<td><p>Primary</p></td>
<td><p>表示 SIP 响应代码的数值。</p></td>
</tr>
<tr class="even">
<td><p><strong>种类</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>响应代码的常规分类。 分类包括：</p>
<ul>
<li><p>1-信息答复</p></li>
<li><p>2–成功的答复</p></li>
<li><p>3-重定向响应</p></li>
<li><p>4-客户端故障响应</p></li>
<li><p>5--服务器故障响应</p></li>
<li><p>6-全球故障回复</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>说明</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>SIP 响应代码的说明。 例如，响应代码181具有以下说明：</p>
<p>正在转发呼叫</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

