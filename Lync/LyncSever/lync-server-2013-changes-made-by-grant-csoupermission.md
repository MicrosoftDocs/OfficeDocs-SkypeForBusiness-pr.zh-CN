---
title: Lync Server 2013 中的 Grant-CsOUPermission 所做的更改
TOCTitle: Lync Server 2013 中的 Grant-CsOUPermission 所做的更改
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205310(v=OCS.15)
ms:contentKeyID: 49314395
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 Grant-CsOUPermission 所做的更改

 

_**上一次修改主题：** 2015-03-09_

若要委派 Lync Server 2013 管理，可以向指定组织单位 (OU) 添加权限，以便林准备过程所创建的 RTC 通用组的成员无需成为 Domain Admins 组的成员即可访问 OU。

**Grant-CsOuPermission** cmdlet 向指定 OU 中的对象授予权限，如下表所示。

## 为用户对象授予权限

在对 OU 上的用户对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。

### 为用户对象授予的权限

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>组</th>
<th>权限</th>
<th>适用于</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>复制目录更改</p></td>
<td><p>仅限此对象</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>列出内容</p>
<p>读取所有属性</p>
<p>读取权限</p></td>
<td><p>仅限此对象</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>列出内容</p>
<p>读取所有属性</p>
<p>读取权限</p></td>
<td><p>仅限此对象</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>读取 RTCUserSearchPropertySet</p>
<p>读取 RTCUserProvisioningPropertySet</p>
<p>读取 RTCPropertySet</p>
<p>读取 Public-Information</p>
<p>读取 General-Information</p>
<p>读取 User-Account-Restrictions</p></td>
<td><p>后代用户对象</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>写入 RTCUserSearchPropertySet</p>
<p>写入 msExchUCVoiceMailSettings</p>
<p>写入 RTCUserProvisioningPropertySet</p>
<p>写入 RTCPropertySet</p>
<p>写入 proxyAddresses</p></td>
<td><p>后代用户对象</p></td>
</tr>
</tbody>
</table>


## 为计算机对象授予权限

在对 OU 上的计算机对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。

### 为计算机对象授予的权限

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>组</th>
<th>权限</th>
<th>适用于</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>复制目录更改</p></td>
<td><p>仅限此对象</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>列出内容</p>
<p>读取所有属性</p>
<p>读取权限</p></td>
<td><p>仅限此对象</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>列出内容</p>
<p>读取所有属性</p>
<p>读取权限</p></td>
<td><p>仅限此对象</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>读取 Public-Information</p>
<p>读取 Validated-DNS-Host-Name</p></td>
<td><p>后代计算机对象</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>读取 Public-Information</p>
<p>读取 Validated-DNS-Host-Name</p></td>
<td><p>后代计算机对象</p></td>
</tr>
</tbody>
</table>


## 为联系人或 AppContact 对象授予权限

在对 OU 上的联系人或 AppContact 对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。

### 为联系人对象或 AppContact 对象授予的权限

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>组</th>
<th>权限</th>
<th>适用于</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>复制目录更改</p></td>
<td><p>仅限此对象</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>列出内容</p>
<p>读取所有属性</p>
<p>读取权限</p></td>
<td><p>仅限此对象</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>列出内容</p>
<p>读取所有属性</p>
<p>读取权限</p></td>
<td><p>仅限此对象</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>读取 RTCUserSearchPropertySet</p>
<p>读取 RTCUserProvisioningPropertySet</p>
<p>读取 RTCPropertySet</p>
<p>读取 Public-Information</p>
<p>读取 General-Information</p>
<p>读取 Personal-Information</p>
<p>读取 User-Account-Restrictions</p></td>
<td><p>后代联系人对象</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>写入 RTCUserSearchPropertySet</p>
<p>写入 otherIpPhone</p>
<p>写入 displayName</p>
<p>写入 description</p>
<p>写入 telephoneNumber</p>
<p>写入 msExchUCVoiceMailSettings</p>
<p>写入 RTCUserProvisioningPropertySet</p>
<p>写入 RTCPropertySet</p>
<p>写入 proxyAddresses</p></td>
<td><p>后代联系人对象</p></td>
</tr>
</tbody>
</table>


## 为设备对象授予权限

在对 OU 上的设备对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。

### 为设备对象授予的权限

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>组</th>
<th>权限</th>
<th>适用于</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>复制目录更改</p></td>
<td><p>仅限此对象</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>列出内容</p>
<p>读取所有属性</p>
<p>读取权限</p></td>
<td><p>仅限此对象</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>列出内容</p>
<p>读取所有属性</p>
<p>读取权限</p></td>
<td><p>仅限此对象</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>读取 RTCUserSearchPropertySet</p>
<p>读取 RTCUserProvisioningPropertySet</p>
<p>读取 RTCPropertySet</p>
<p>读取 Public-Information</p>
<p>读取 Personal-Information</p>
<p>读取 General-Information</p>
<p>读取 User-Account-Restrictions</p></td>
<td><p>后代联系人对象</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>创建子级</p>
<p>删除子级</p>
<p>删除树</p></td>
<td><p>联系人</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>写入 displayName</p>
<p>写入 description</p>
<p>写入 telephoneNumber</p></td>
<td><p>后代用户对象</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>写入 RTCUserSearchPropertySet</p>
<p>写入 otherIpPhone</p>
<p>写入 displayName</p>
<p>写入 description</p>
<p>写入 telephoneNumber</p>
<p>写入 msExchUCVoiceMailSettings</p>
<p>写入 RTCUserProvisioningPropertySet</p>
<p>写入 RTCPropertySet</p>
<p>写入 proxyAddresses</p></td>
<td><p>后代联系人对象</p></td>
</tr>
</tbody>
</table>


## 为 InetOrgPerson 对象授予权限

在对 OU 上的 InetOrgPerson 对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。

### 为 InetOrgPerson 对象授予的权限

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>组</th>
<th>权限</th>
<th>适用于</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>复制目录更改</p></td>
<td><p>仅限此对象</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>列出内容</p>
<p>读取所有属性</p>
<p>读取权限</p></td>
<td><p>仅限此对象</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>列出内容</p>
<p>读取所有属性</p>
<p>读取权限</p></td>
<td><p>仅限此对象</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>读取 RTCUserSearchPropertySet</p>
<p>读取 RTCUserProvisioningPropertySet</p>
<p>读取 RTCPropertySet</p>
<p>读取 Personal-Information</p>
<p>读取 Public-Information</p>
<p>读取 General-Information</p>
<p>读取 User-Account-Restrictions</p></td>
<td><p>后代 InetOrgPerson 对象</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>写入 RTCUserSearchPropertySet</p>
<p>写入 RTCUserProvisioningPropertySet</p>
<p>写入 RTCPropertySet</p>
<p>写入 proxyAddresses</p></td>
<td><p>后代 InetOrgPerson 对象</p></td>
</tr>
</tbody>
</table>

