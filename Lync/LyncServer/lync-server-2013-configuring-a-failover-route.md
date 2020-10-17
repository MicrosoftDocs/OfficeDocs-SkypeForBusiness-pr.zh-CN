---
title: Lync Server 2013：配置故障转移路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a failover route
ms:assetid: 76e48df4-3b78-4fb7-b1f7-c1e604b81bad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398581(v=OCS.15)
ms:contentKeyID: 48184542
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0a3a0d3b2eb2d505ff345af66ae8ccbcc551ee8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520059"
---
# <a name="configuring-a-failover-route-in-lync-server-2013"></a>在 Lync Server 2013 中配置故障转移路由

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-21_

以下示例显示在 Dallas-GW1 因维护而关闭或因其他原因不可用时，管理员如何定义故障转移路由以供使用。下面的表显示了所需的配置更改。

### <a name="table-1-user-policy"></a>表 1. 用户策略

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>用户策略</th>
<th>电话用法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Default Calling Policy</p></td>
<td><p>本地</p>
<p>名</p></td>
</tr>
<tr class="even">
<td><p>Redmond Local Policy</p></td>
<td><p>RedmondLocal</p></td>
</tr>
<tr class="odd">
<td><p>Dallas Calling Policy</p></td>
<td><p>DallasUsers</p>
<p>名</p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a>表 2. 路由

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>路由名称</th>
<th>号码模式</th>
<th>电话用法</th>
<th>干线</th>
<th>网关</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Redmond Local Route</p></td>
<td><p>^\+1 (425 | 206 | 253) # A2\d {7}) $</p></td>
<td><p>本地</p>
<p>RedmondLocal</p></td>
<td><p>Trunk1</p>
<p>Trunk2</p></td>
<td><p>Red-GW1</p>
<p>Red-GW2</p></td>
</tr>
<tr class="even">
<td><p>Dallas Local Route</p></td>
<td><p>^\+1 (972 | 214 | 469) # A2\d {7}) $</p></td>
<td><p>本地</p></td>
<td><p>Trunk3</p></td>
<td><p>达拉斯-GW1</p></td>
</tr>
<tr class="odd">
<td><p>Universal Route</p></td>
<td><p>^\+ ( \d * ) $</p></td>
<td><p>名</p></td>
<td><p>Trunk1</p>
<p>Trunk2</p>
<p>Trunk3</p></td>
<td><p>Red-GW1</p>
<p>Red-GW2</p>
<p>达拉斯-GW1</p></td>
</tr>
<tr class="even">
<td><p>Dallas Users Route</p></td>
<td><p>^\+ ( \d * ) $</p></td>
<td><p>DallasUsers</p></td>
<td><p>Trunk3</p></td>
<td><p>达拉斯-GW1</p></td>
</tr>
</tbody>
</table>


在表 1 中，名为 GlobalPSTNHopoff 的电话用法添加到 Dallas Calling Policy 中的 DallasUsers 电话用法的后面。这样，当 DallasUsers 电话用法的路由不可用时，具有 Dallas Calling Policy 的呼叫就可以使用针对 GlobalPSTNHopoff 电话用法配置的路由。

</div>

<span> </span>

</div>

</div>

</div>

