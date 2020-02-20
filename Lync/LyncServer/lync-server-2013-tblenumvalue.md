---
title: Lync Server 2013： tblEnumValue
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblEnumValue
ms:assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615025(v=OCS.15)
ms:contentKeyID: 48185040
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 984dd5f161b31c40de914f363c0722657d3194ed
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142098"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a>Lync Server 2013 中的 tblEnumValue

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-06-28_

tblEnumValue 表是一个硬编码表，包含节点表使用的属性的“可见性”值和“行为”值。

### <a name="columns"></a>Columns

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>类型</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>valueID</p></td>
<td><p>smallint，不为 null</p></td>
<td><p>值的 ID。</p></td>
</tr>
<tr class="even">
<td><p>attributeID</p></td>
<td><p>smallint，不为 null</p></td>
<td><p>属性的 ID。</p></td>
</tr>
<tr class="odd">
<td><p>attributeValue</p></td>
<td><p>nvarchar  (256)，不为 null</p></td>
<td><p>值名称。</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>Keys

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>valueID</p></td>
<td><p>主键。</p></td>
</tr>
<tr class="even">
<td><p>attributeID</p></td>
<td><p>其查找包含在 tblEnumAttribute.attributeID 表中的外键。</p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a>表值

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>valueID</th>
<th>attributeID</th>
<th>attributeValue</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>双面</p></td>
<td><p>1</p></td>
<td><p>private</p></td>
</tr>
<tr class="even">
<td><p>第三章</p></td>
<td><p>1</p></td>
<td><p>范围</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>双面</p></td>
<td><p>通用</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>双面</p></td>
<td><p>大会堂</p></td>
</tr>
<tr class="odd">
<td><p>6 </p></td>
<td><p>1</p></td>
<td><p>open</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的 tblNode](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

