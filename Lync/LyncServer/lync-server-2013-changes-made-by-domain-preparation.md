---
title: Lync Server 2013：域准备所做的更改
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by domain preparation
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48184845
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b1eea02c41acf748674cdd7976028a51fdb367e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529499"
---
# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a>Lync Server 2013 中的域准备所做的更改

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2010-10-18_

下表列出域准备在域根上创建的访问控制项 (ACE)。除非另行说明，否则所有 ACE 都是继承的。

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a>添加到域根的 ACE

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>RTCUniversal-UserReadOnly-组</th>
<th>RTCUniversal-ServerReadOnly-组</th>
<th>RTCUniversal-UserAdmins</th>
<th>RTCHSUniversal-Services</th>
<th>Authenticated-Users</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>读取容器（非继承）</p></td>
<td><p><strong>是</strong></p></td>
<td><p><strong>是</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>读取用户属性集 User-Account-Restrictions</p></td>
<td><p><strong>是</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>读取用户属性集 Personal-Information</p></td>
<td><p><strong>是</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>读取用户属性集 General-Information</p></td>
<td><p><strong>是</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>读取用户属性集 Public-Information</p></td>
<td><p><strong>是</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>读取用户属性集 RTCUserSearchProperty-Set</p></td>
<td><p><strong>是</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p><strong>是</strong></p></td>
</tr>
<tr class="odd">
<td><p>读取用户属性集 RTCPropertySet</p></td>
<td><p><strong>是</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>写入用户属性 Proxy-Addresses</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p><strong>是</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>写入用户属性集 RTCUserSearchProperty-Set</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p><strong>是</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>写入用户属性集 RTCPropertySet</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p><strong>是</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>读取所有 Active Directory 对象的属性集 DS-Replication-Get-Changes</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p><strong>是</strong></p></td>
<td><p>否</p></td>
</tr>
</tbody>
</table>


下表列出域准备在以下三个内置容器中创建的 ACE：用户、计算机和域控制器。除非另行说明，否则所有 ACE 都是继承的。

### <a name="aces-added-to-built-in-containers"></a>添加到内置容器的 ACE

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>RTCUniversal-UserReadOnly-组</th>
<th>RTCUniversal-ServerReadOnly-组</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>读取容器（非继承）</p></td>
<td><p><strong>是</strong></p></td>
<td><p><strong>是</strong></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

