---
title: Lync Server 2013： tblEnumAttribute
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblEnumAttribute
ms:assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558617(v=OCS.15)
ms:contentKeyID: 48183523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbb970d217ff24396fa72c76ba4b88c3d38be6eb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142108"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblenumattribute-in-lync-server-2013"></a>Lync Server 2013 中的 tblEnumAttribute

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-12_

tblEnumAttribute 是一个硬编码表，包含用于节点表的 Visibility 和 Behavior 属性。

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
<td><p>attributeID</p></td>
<td><p>smallint，不为 null</p></td>
<td><p>属性的 ID。</p></td>
</tr>
<tr class="even">
<td><p>attributeName</p></td>
<td><p>nvarchar (256)，不为 null</p></td>
<td><p>属性的名称。</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>键

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
<td><p>attributeID</p></td>
<td><p>主键。</p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a>表值

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>attributeID</th>
<th>attributeName</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>深入.</p></td>
</tr>
<tr class="even">
<td><p>双面</p></td>
<td><p>性能.</p></td>
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

