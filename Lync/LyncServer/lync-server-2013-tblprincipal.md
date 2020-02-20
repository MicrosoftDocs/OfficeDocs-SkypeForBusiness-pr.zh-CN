---
title: Lync Server 2013： tblPrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipal
ms:assetid: 79a24502-b4ce-41f0-8979-8caddf535338
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558667(v=OCS.15)
ms:contentKeyID: 48184571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4894cc1e27ce2692f0afee57fafd0025cbafebc8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipal-in-lync-server-2013"></a>Lync Server 2013 中的 tblPrincipal

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-12_

tblPrincipal 包含所有主体，其中包括用户、文件夹和组。

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
<td><p>prinID</p></td>
<td><p>int，不为 null</p></td>
<td><p>主体 ID。</p></td>
</tr>
<tr class="even">
<td><p>prinGuid</p></td>
<td><p>GUID，不为 null</p></td>
<td><p>主体 GUID。 它被广泛用作备用主键，因为它的含义与 Active Directory 域服务空间中的含义相同。 （缓存主体的 GUID 等于相应的 Active Directory 对象 GUID。）</p></td>
</tr>
<tr class="odd">
<td><p>prinUri</p></td>
<td><p>nvarchar (256)，不为 null</p></td>
<td><p>主体 URI。SIP 方案用于用户，ma-grp 用于几乎其他的一切对象。</p></td>
</tr>
<tr class="even">
<td><p>prinName</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>公用名。仅供用户类型使用。</p></td>
</tr>
<tr class="odd">
<td><p>prinDisplayName</p></td>
<td><p>Nvarchar (256)</p></td>
<td><p>显示名称。仅供用户类型使用。</p></td>
</tr>
<tr class="even">
<td><p>prinCompanyName</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>公司名称。仅供用户类型使用。</p></td>
</tr>
<tr class="odd">
<td><p>prinEmail</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>电子邮件。仅供用户类型使用。</p></td>
</tr>
<tr class="even">
<td><p>prinADPath</p></td>
<td><p>nvarchar (384)</p></td>
<td><p>主体是其缓存版本的 Active Directory 对象的域名。对于非 Active Directory 对象的类型（例如系统用户），可以为 Null。</p></td>
</tr>
<tr class="odd">
<td><p>prinADUserPrincipalName</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>用户的用户主体名称 (UPN)。仅供常规用户类型使用。</p></td>
</tr>
<tr class="even">
<td><p>prinDisabled</p></td>
<td><p>smallint，不为 null</p></td>
<td><ul>
<li><p>0：主体处于活动状态。</p></li>
<li><p>1：禁用主体，因为用户的 SIP 功能被禁用。</p></li>
<li><p>2：删除主体，因为关联的 AD 对象已被删除。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>prinTypeID</p></td>
<td><p>smallint，不为 null</p></td>
<td><p>主体类型（来自 tblPrincipalType 表）。</p></td>
</tr>
<tr class="even">
<td><p>prinPoolID</p></td>
<td><p>Int</p></td>
<td><p>主体的 Lync 池分配。</p></td>
</tr>
<tr class="odd">
<td><p>prinPolicyID</p></td>
<td><p>Int</p></td>
<td><p>如果存在标记类型策略，则为用户的持久聊天服务器策略值。</p></td>
</tr>
<tr class="even">
<td><p>prinAddedBy</p></td>
<td><p>int</p></td>
<td><p>创建者的主体 ID。</p></td>
</tr>
<tr class="odd">
<td><p>prinAddedOn</p></td>
<td><p>bigint，不为 null</p></td>
<td><p>创建时间的时间戳。</p></td>
</tr>
<tr class="even">
<td><p>prinUpdatedBy</p></td>
<td><p>int</p></td>
<td><p>上次更新它的主体的 ID。</p></td>
</tr>
<tr class="odd">
<td><p>prinUpdatedOn</p></td>
<td><p>bigint，不为 null</p></td>
<td><p>上次更新的时间戳。</p></td>
</tr>
<tr class="even">
<td><p>prinVerifiedOn</p></td>
<td><p>datetime，不为 null</p></td>
<td><p>主体上次进行 Active Directory 同步刷新的日期和时间。</p></td>
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
<td><p>prinID</p></td>
<td><p>主键。</p></td>
</tr>
<tr class="even">
<td><p>prinTypeID</p></td>
<td><p>其查找包含在 tblPrincipalType.ptypeID 表中的外键。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

