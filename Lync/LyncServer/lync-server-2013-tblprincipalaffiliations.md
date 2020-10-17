---
title: Lync Server 2013： tblPrincipalAffiliations
description: Lync Server 2013： tblPrincipalAffiliations。
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
ms.openlocfilehash: 01c373147a58300e64f22e60e989a777c59b2653
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547478"
---
# <a name="tblprincipalaffiliations-in-lync-server-2013"></a>Lync Server 2013 中的 tblPrincipalAffiliations

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-12_

tblPrincipalAffiliations 包含描述位置中的成员身份的主体隶属关系，包括 Active directory 域服务安全组，在 Active Directory 容器中的域中。

### <a name="columns"></a>列数

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
<td><p>int，不为 null</p></td>
<td><p>附属主体的 ID。</p></td>
</tr>
<tr class="even">
<td><p>affiliationID</p></td>
<td><p>int，不为 null</p></td>
<td><p>表示附属关系的主体的 ID。每个主体（系统用户类型除外）还具有自附属关系。</p></td>
</tr>
<tr class="odd">
<td><p>index</p></td>
<td><p>int，不为 null</p></td>
<td><p>索引. 自隶属关系的值是-1，对于其他隶属关系，它会从每个 &lt; principalID、affiliationId 存储桶内的1依次增加 &gt; 。</p></td>
</tr>
<tr class="even">
<td><p>updatedBy</p></td>
<td><p>int，不为 null</p></td>
<td><p>进行最新更新的主体。这通常为 1，表示 Active Directory 同步。</p></td>
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
<th>列数</th>
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
<td><p>其查找包含在 tblPrincipal.prinID 表中的外键。</p></td>
</tr>
<tr class="odd">
<td><p>affiliationID</p></td>
<td><p>其查找包含在 tblPrincipal.prinID 表中的外键。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

