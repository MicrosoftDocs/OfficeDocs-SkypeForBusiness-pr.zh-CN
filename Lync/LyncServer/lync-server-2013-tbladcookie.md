---
title: Lync Server 2013：tblADCookie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558610(v=OCS.15)
ms:contentKeyID: 48183366
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2eef65e18de609f7e10fed4aaad9283612778070
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845735"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladcookie-in-lync-server-2013"></a>Lync Server 2013 中的 tblADCookie

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-06-25_

tblADCookie 包含当前的轻型目录访问协议 (LDAP) 同步 cookie。

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
<td><p>prinGuid</p></td>
<td><p>GUID, not null</p></td>
<td><p>正在监视的域的主体 GUID。</p></td>
</tr>
<tr class="even">
<td><p>prinDCHost</p></td>
<td><p>nvarchar (255)</p></td>
<td><p>用于 Active Directory 域服务同步的当前域控制器的完全限定的域名 (FQDN)。有信息值。</p></td>
</tr>
<tr class="odd">
<td><p>adcContent</p></td>
<td><p>图像 (二进制)</p></td>
<td><p>Active Directory 同步 cookie。</p></td>
</tr>
<tr class="even">
<td><p>lastUpdated</p></td>
<td><p>datetime</p></td>
<td><p>带有行更新时间的时间戳。</p></td>
</tr>
<tr class="odd">
<td><p>lockedUntil</p></td>
<td><p>datetime</p></td>
<td><p>对行进行更改锁定的时间。 这是一种软件互操作机制的一部分, 可确保每次只有一个聊天服务执行 Active Directory 同步。</p></td>
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
<td><p>prinGuid</p></td>
<td><p>主键。</p></td>
</tr>
<tr class="even">
<td><p>prinGuid</p></td>
<td><p>PrinGuid 表中的 lookup 的外键。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

