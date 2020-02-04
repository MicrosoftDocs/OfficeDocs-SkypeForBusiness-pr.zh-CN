---
title: Lync Server 2013：通过授予 CsSetupPermission 进行的更改
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsSetupPermission
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205250(v=OCS.15)
ms:contentKeyID: 48185360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d82b896f1d6d1da1184bfa61d7352c9b4803a03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742352"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a>Lync Server 2013 中的 "授权-CsSetupPermission" 所做的更改

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-06-20_

若要委派设置，你可以向特定 Active Directory 组织单位（OU）的 RTCUniversalServerAdmins 通用组授予权限，从而允许该 OU 中的 RTCUniversalServerAdmins 组成员在指定的 Active Directory 中安装 Lync Server 2013不是域管理员组成员的域。

**CsSetupPermission** cmdlet 授予对 OU 的 RTCUniversalServerAdmins 组权限，如下表所示：

### <a name="permissions-granted-to-objects-in-the-ou"></a>在 OU 中授予对象的权限

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>权限适用于：</th>
<th>授予的权限为：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>特殊访问：</p>
<ul>
<li><p>阅读 servicePrincipalName</p></li>
<li><p>写入 servicePrincipalName</p></li>
<li><p>删除树</p></li>
<li><p>复制目录更改</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>后代 serviceConnectionPoint 对象</p></td>
<td><p>特殊访问：</p>
<ul>
<li><p>读取权限</p></li>
<li><p>写入权限</p></li>
<li><p>创建子元素</p></li>
<li><p>删除子元素</p></li>
<li><p>列表内容</p></li>
<li><p>Write 属性</p></li>
<li><p>Read 属性</p></li>
<li><p>删除树</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>子代 msRTCSIP-服务器对象</p></td>
<td><p>特殊访问：</p>
<ul>
<li><p>Write 属性</p></li>
<li><p>Read 属性</p></li>
<li><p>删除树</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>子代 msRTCSIP-WebComponents 对象</p></td>
<td><p>特殊访问：</p>
<ul>
<li><p>Write 属性</p></li>
<li><p>Read 属性</p></li>
<li><p>删除树</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>子体 msRTCSIP-MCU 对象</p></td>
<td><p>特殊访问：</p>
<ul>
<li><p>Write 属性</p></li>
<li><p>Read 属性</p></li>
<li><p>删除树</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>子代 msRTCSIP-MediationServer 对象</p></td>
<td><p>特殊访问：</p>
<ul>
<li><p>Write 属性</p></li>
<li><p>Read 属性</p></li>
<li><p>删除树</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>子代 msRTCSIP-ApplicationServer 对象</p></td>
<td><p>特殊访问：</p>
<ul>
<li><p>Write 属性</p></li>
<li><p>Read 属性</p></li>
<li><p>删除树</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>子代 msRTCSIP-ConnectionPoint 对象</p></td>
<td><p>特殊访问：</p>
<ul>
<li><p>Write 属性</p></li>
<li><p>Read 属性</p></li>
<li><p>删除树</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>子体计算机对象</p></td>
<td><p>用于 serviceConnectionPoint 的特殊访问：</p>
<ul>
<li><p>创建子对象</p></li>
<li><p>删除子对象</p></li>
<li><p>删除树</p></li>
</ul>
<p>公共信息的特殊访问权限：</p>
<ul>
<li><p>Read 属性</p></li>
</ul>
<p>DNS 主机名的特殊访问权限：</p>
<ul>
<li><p>Read 属性</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

