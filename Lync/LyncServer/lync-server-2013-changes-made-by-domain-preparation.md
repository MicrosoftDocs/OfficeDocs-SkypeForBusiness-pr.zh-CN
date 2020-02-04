---
title: Lync Server 2013：由域准备进行的更改
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
ms.openlocfilehash: cbdd1fa1fbb5bd7a396e17f478326a9e4dd700f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730102"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a>Lync Server 2013 中的域准备进行的更改

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2010-10-18_

下表列出了域准备在域根上创建的访问控制条目（Ace）。 除非另有说明，否则将继承所有 Ace。

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a>添加到域根的 Ace

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
<th>棒</th>
<th>RTCUniversal-UserReadOnly</th>
<th>RTCUniversal-ServerReadOnly</th>
<th>RTCUniversal-UserAdmins</th>
<th>RTCHSUniversal-服务</th>
<th>已验证-用户</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>读取容器（不是继承的）</p></td>
<td><p><strong>是的</strong></p></td>
<td><p><strong>是</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>阅读用户 PropertySet 用户帐户-限制</p></td>
<td><p><strong>是</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>阅读用户 PropertySet 个人信息</p></td>
<td><p><strong>是</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>阅读用户 PropertySet 常规信息</p></td>
<td><p><strong>是</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>读取用户 PropertySet 公共信息</p></td>
<td><p><strong>是</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>Read User PropertySet RTCUserSearchProperty-Set</p></td>
<td><p><strong>是</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p><strong>是</strong></p></td>
</tr>
<tr class="odd">
<td><p>阅读用户 PropertySet RTCPropertySet</p></td>
<td><p><strong>是</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>编写用户属性代理-地址</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p><strong>是</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>编写用户 PropertySet RTCUserSearchProperty-Set</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p><strong>是</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>编写用户 PropertySet RTCPropertySet</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p><strong>是</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>读取 PropertySet DS-复制-对所有 Active Directory 对象的获取更改</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p><strong>是</strong></p></td>
<td><p>否</p></td>
</tr>
</tbody>
</table>


下表列出了域准备在三个内置容器中创建的 Ace：用户、计算机和域控制器。 除非另有说明，否则将继承所有 Ace。

### <a name="aces-added-to-built-in-containers"></a>添加到内置容器的 Ace

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>棒</th>
<th>RTCUniversal-UserReadOnly</th>
<th>RTCUniversal-ServerReadOnly</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>读取容器（不是继承的）</p></td>
<td><p><strong>是的</strong></p></td>
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

