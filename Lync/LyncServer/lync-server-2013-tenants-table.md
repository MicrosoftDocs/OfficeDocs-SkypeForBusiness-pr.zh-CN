---
title: Lync Server 2013：Tenants 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Tenants table
ms:assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412950(v=OCS.15)
ms:contentKeyID: 48185309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7da863aa2b713f874aba00f5a4f481f45fb79b3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tenants-table-in-lync-server-2013"></a>Lync Server 2013 中的 Tenants 表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-28_

租户表是一个支持表, 用于存储各种租户的列表。 表中的每条记录表示一个租户。

<div>


> [!NOTE]  
> 在本地部署中, CDR 使用内部版本租户 ID 指示不同的身份验证类型, 例如公共 IM 连接、联合和匿名。



</div>


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
<td><p><strong>TenantId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>标识此租户 ID 的唯一编号。</p></td>
</tr>
<tr class="even">
<td><p><strong>TenantKey</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>允许的值:</p>
<ul>
<li><p>00000000-0000-0000-0000-000000000000-企业版</p></li>
<li><p>00000000-0000-0000-0000-000000000001-联合</p></li>
<li><p>00000000-0000-0000-0000-000000000002-匿名</p></li>
<li><p>00000000-0000-0000-0000-000000000003-公共 IM 连接</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

