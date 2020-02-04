---
title: Lync Server 2013： ErrorCategory 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorCategory table
ms:assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204675(v=OCS.15)
ms:contentKeyID: 48183425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5da1da6f54fa9099cc455040a71fb11c4fe070e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorcategory-table-in-lync-server-2013"></a>Lync Server 2013 中的 ErrorCategory 表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-08-20_

ErrorCategory 表包含每个 Microsoft Lync Server 2013 诊断分类的友好名称。 默认情况下，Lync Server 2013 使用以下分类：

  - 0--成功

  - 1--预期故障

  - 2-意外故障

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
<td><p><strong>CategoryId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>分类的唯一标识符。</p></td>
</tr>
<tr class="even">
<td><p><strong>名称</strong> - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>分配给分类的值和友好名称。 允许的值包括：</p>
<ul>
<li><p>0--成功</p></li>
<li><p>1--预期故障</p></li>
<li><p>2-意外故障</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

