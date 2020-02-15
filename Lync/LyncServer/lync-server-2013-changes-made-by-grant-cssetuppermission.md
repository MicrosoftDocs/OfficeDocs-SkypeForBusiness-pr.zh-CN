---
title: Lync Server 2013：由 Grant-CsSetupPermission 所做的更改
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
ms.openlocfilehash: 23547ebc7faf594ee3ea72ef7d0c094846ac94b3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043914"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a>Lync Server 2013 中的 CsSetupPermission 所做的更改

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-06-20_

若要委派安装程序，可以为特定 Active Directory 组织单位（OU）授予对 RTCUniversalServerAdmins 通用组的权限，从而启用该 OU 中 RTCUniversalServerAdmins 组的成员，以在指定的中安装 Lync Server 2013。不是 Domain Admins 组的成员的域。

**Grant-CsSetupPermission** cmdlet 向 OU 授予 RTCUniversalServerAdmins 组权限，如下表中所述：

### <a name="permissions-granted-to-objects-in-the-ou"></a>向 OU 中的对象授予的权限

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
<li><p>读取 servicePrincipalName</p></li>
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
<li><p>创建子级</p></li>
<li><p>删除子级</p></li>
<li><p>列出内容</p></li>
<li><p>写入属性</p></li>
<li><p>读取属性</p></li>
<li><p>删除树</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>后代 msRTCSIP-Server 对象</p></td>
<td><p>特殊访问：</p>
<ul>
<li><p>写入属性</p></li>
<li><p>读取属性</p></li>
<li><p>删除树</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>后代 msRTCSIP-WebComponents 对象</p></td>
<td><p>特殊访问：</p>
<ul>
<li><p>写入属性</p></li>
<li><p>读取属性</p></li>
<li><p>删除树</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>后代 msRTCSIP-MCU 对象</p></td>
<td><p>特殊访问：</p>
<ul>
<li><p>写入属性</p></li>
<li><p>读取属性</p></li>
<li><p>删除树</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>后代 msRTCSIP-MediationServer 对象</p></td>
<td><p>特殊访问：</p>
<ul>
<li><p>写入属性</p></li>
<li><p>读取属性</p></li>
<li><p>删除树</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>后代 msRTCSIP-ApplicationServer 对象</p></td>
<td><p>特殊访问：</p>
<ul>
<li><p>写入属性</p></li>
<li><p>读取属性</p></li>
<li><p>删除树</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>后代 msRTCSIP-ConnectionPoint 对象</p></td>
<td><p>特殊访问：</p>
<ul>
<li><p>写入属性</p></li>
<li><p>读取属性</p></li>
<li><p>删除树</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>后代计算机对象</p></td>
<td><p>对 serviceConnectionPoint 的特殊访问：</p>
<ul>
<li><p>创建子对象</p></li>
<li><p>删除子对象</p></li>
<li><p>删除树</p></li>
</ul>
<p>对公共信息的特殊访问：</p>
<ul>
<li><p>读取属性</p></li>
</ul>
<p>对 DNS 主机名的特殊访问：</p>
<ul>
<li><p>读取属性</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

