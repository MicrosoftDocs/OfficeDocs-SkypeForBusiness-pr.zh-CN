---
title: Lync Server 2013： Grant-CsOUPermission 所做的更改
description: Lync Server 2013： CsOUPermission 所做的更改。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsOUPermission
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205310(v=OCS.15)
ms:contentKeyID: 48185564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10d3db0e9dde380628690bc016e2b4bd2ec85b54
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543608"
---
# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a>Lync Server 2013 中 Grant-CsOUPermission 所做的更改

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-06-20_

若要委派 Lync Server 2013 管理，可以将权限添加到指定的组织单位 (Ou 中) 以便由林准备创建的 RTC 通用组的成员可以访问 Ou，而无需成为 Domain Admins 组的成员。

**Grant-CsOuPermission** cmdlet 向指定 OU 中的对象授予权限，如下表所示。

<div>

## <a name="granting-permission-for-user-objects"></a>为用户对象授予权限

在对 OU 上的用户对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。

### <a name="permissions-granted-for-user-objects"></a>为用户对象授予的权限

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Group</th>
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


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a>为计算机对象授予权限

在对 OU 上的计算机对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。

### <a name="permissions-granted-for-computer-objects"></a>为计算机对象授予的权限

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Group</th>
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


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a>为联系人或 AppContact 对象授予权限

在对 OU 上的联系人或 AppContact 对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a>为联系人对象或 AppContact 对象授予的权限

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Group</th>
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


</div>

<div>

## <a name="granting-permission-for-device-objects"></a>为设备对象授予权限

在对 OU 上的设备对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。

### <a name="permissions-granted-for-device-objects"></a>为设备对象授予的权限

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Group</th>
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
<td><p>Contact</p></td>
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


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a>为 InetOrgPerson 对象授予权限

在对 OU 上的 InetOrgPerson 对象运行 **Grant-CsOuPermission** cmdlet 时，会为组授予如下表所示的权限。

### <a name="permissions-granted-for-inetorgperson-objects"></a>为 InetOrgPerson 对象授予的权限

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Group</th>
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


</div>

</div>

<span> </span>

</div>

</div>

</div>

