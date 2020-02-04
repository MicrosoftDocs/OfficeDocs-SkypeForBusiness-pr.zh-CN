---
title: Lync Server 2013：tblPrincipalMeta
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMeta
ms:assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615009(v=OCS.15)
ms:contentKeyID: 48184648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 848f4dc19ddf64c53c2dd30ae6ca4c8036b67c79
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764092"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmeta-in-lync-server-2013"></a>Lync Server 2013 中的 tblPrincipalMeta

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-12_

tblPrincipalMeta 包含必须从 Active Directory 域服务刷新的主体。

### <a name="columns"></a>多

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
<td><p>prinID</p></td>
<td><p>int，not null</p></td>
<td><p>主体 ID。</p></td>
</tr>
<tr class="even">
<td><p>prinAffiliationsDirty</p></td>
<td><p>位，not null</p></td>
<td><p>如果必须刷新主体隶属关系，则为 True。</p></td>
</tr>
<tr class="odd">
<td><p>prinAttributesDirty</p></td>
<td><p>位，not null</p></td>
<td><p>如果必须刷新主体属性，则为 True。</p></td>
</tr>
<tr class="even">
<td><p>prinDeleted</p></td>
<td><p>位，not null</p></td>
<td><p>如果主体已被删除，则为 True。</p></td>
</tr>
<tr class="odd">
<td><p>tryCount</p></td>
<td><p>int</p></td>
<td><p>尝试从目前为止发生的 AD DS 刷新主体的次数。</p></td>
</tr>
<tr class="even">
<td><p>lastTry</p></td>
<td><p>datetime</p></td>
<td><p>从最新尝试刷新主体的时间戳。 如果尚未尝试刷新，则可以为 null。</p></td>
</tr>
<tr class="odd">
<td><p>nextTry</p></td>
<td><p>datetime</p></td>
<td><p>下一次计划刷新的时间戳。 如果尚未安排进一步刷新，则可以为 null。</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>标示

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
<td><p>prinID</p></td>
<td><p>主键。</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>TblPrincipal 表中的 lookup 的外键。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

