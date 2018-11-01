---
title: Lync Server 2013 中的 Grant-CsSetupPermission 所做的更改
TOCTitle: Lync Server 2013 中的 Grant-CsSetupPermission 所做的更改
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205250(v=OCS.15)
ms:contentKeyID: 49314181
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 Grant-CsSetupPermission 所做的更改

 

_**上一次修改主题：** 2015-03-09_

若要委派安装，可向特定 Active Directory 组织单位 (OU) 的 RTCUniversalServerAdmins 通用组授予权限，使该 OU 中的 RTCUniversalServerAdmins 组的成员能够在不是 Domain Admins 组成员的情况下在指定域中安装 Lync Server 2013。

**Grant-CsSetupPermission** cmdlet 向 OU 授予 RTCUniversalServerAdmins 组权限，如下表中所述：

### 向 OU 中的对象授予的权限

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

