---
title: Lync Server 2013：tblPrincipalAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalAffiliations
ms:assetid: 45fd8484-5837-44d2-85bb-45c83546607c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558642(v=OCS.15)
ms:contentKeyID: 48183993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3976b98fddc96ad08f3de4413bf8f38ec3525496
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalaffiliations-in-lync-server-2013"></a>Lync Server 2013 中的 tblPrincipalAffiliations

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-12_

tblPrincipalAffiliations 包含描述位置中的成员身份的主体成员，包括 Active directory 域服务安全组，位于 Active Directory 容器中的域中。

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
<td><p>principalID</p></td>
<td><p>int，not null</p></td>
<td><p>关联主体的 ID。</p></td>
</tr>
<tr class="even">
<td><p>affiliationID</p></td>
<td><p>int，not null</p></td>
<td><p>表示隶属关系的承担者的 ID。 每个主体（除系统用户类型外）还具有自我隶属关系。</p></td>
</tr>
<tr class="odd">
<td><p>食指</p></td>
<td><p>int，not null</p></td>
<td><p>食指. 自隶属关系的值是-1，对于其他隶属关系，在每个&lt;PrincipalID、affiliationId&gt;存储桶中，它将按从1开始递增。</p></td>
</tr>
<tr class="even">
<td><p>updatedBy</p></td>
<td><p>int，not null</p></td>
<td><p>已进行最新更新的主体。 这通常是1，这意味着 Active Directory 同步。</p></td>
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
<th>多</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;principalID、index、affiliationID&gt;</p></td>
<td><p>主键。</p></td>
</tr>
<tr class="even">
<td><p>principalID</p></td>
<td><p>TblPrincipal 表中的 lookup 的外键。</p></td>
</tr>
<tr class="odd">
<td><p>affiliationID</p></td>
<td><p>TblPrincipal 表中的 lookup 的外键。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

