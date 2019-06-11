---
title: 'Lync Server 2013: 通过授予 CsOUPermission 进行的更改'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by Grant-CsOUPermission
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205310(v=OCS.15)
ms:contentKeyID: 48185564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ce6b16dff48afeeec848024d763655695905008
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a>Lync Server 2013 中的 "授权-CsOUPermission" 所做的更改

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-06-20_

若要委派 Lync Server 2013 管理, 可以向指定的组织单位 (Ou) 添加权限, 以便林准备创建的 RTC 通用组的成员无需成为域管理员组的成员即可访问 Ou。

**CsOuPermission** cmdlet 按下表中指定的方式向指定 OU 中的对象授予权限。

<div>

## <a name="granting-permission-for-user-objects"></a>为用户对象授予权限

在 OU 上运行用户对象的**CsOuPermission** cmdlet 时, 将向组授予下表中所示的权限。

### <a name="permissions-granted-for-user-objects"></a>为用户对象授予的权限

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>团队</th>
<th>权限</th>
<th>适用于</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>复制目录更改</p></td>
<td><p>仅此对象</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>列表内容</p>
<p>读取所有属性</p>
<p>读取权限</p></td>
<td><p>仅此对象</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>列表内容</p>
<p>读取所有属性</p>
<p>读取权限</p></td>
<td><p>仅此对象</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>阅读 RTCUserSearchPropertySet</p>
<p>阅读 RTCUserProvisioningPropertySet</p>
<p>阅读 RTCPropertySet</p>
<p>阅读公共信息</p>
<p>阅读常规信息</p>
<p>阅读用户-帐户限制</p></td>
<td><p>子代用户对象</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>写 RTCUserSearchPropertySet</p>
<p>写 msExchUCVoiceMailSettings</p>
<p>写 RTCUserProvisioningPropertySet</p>
<p>写 RTCPropertySet</p>
<p>写 proxyAddresses</p></td>
<td><p>子代用户对象</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a>为计算机对象授予权限

在 OU 上运行计算机对象的**CsOuPermission** cmdlet 时, 将向组授予下表中所示的权限。

### <a name="permissions-granted-for-computer-objects"></a>为计算机对象授予的权限

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>团队</th>
<th>权限</th>
<th>适用于</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>复制目录更改</p></td>
<td><p>仅此对象</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>列表内容</p>
<p>读取所有属性</p>
<p>读取权限</p></td>
<td><p>仅此对象</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>列表内容</p>
<p>读取所有属性</p>
<p>读取权限</p></td>
<td><p>仅此对象</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>阅读公共信息</p>
<p>读取已验证的 DNS 主机名</p></td>
<td><p>子体计算机对象</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>阅读公共信息</p>
<p>读取已验证的 DNS 主机名</p></td>
<td><p>子体计算机对象</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a>授予联系人或 AppContact 对象的权限

当你为某个 OU 上的 Contact 对象或 AppContact 对象运行**CsOuPermission** cmdlet 时, 将向组授予下表中所示的权限。

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a>为联系人或 AppContact 对象授予的权限

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>团队</th>
<th>权限</th>
<th>适用于</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>复制目录更改</p></td>
<td><p>仅此对象</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>列表内容</p>
<p>读取所有属性</p>
<p>读取权限</p></td>
<td><p>仅此对象</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>列表内容</p>
<p>读取所有属性</p>
<p>读取权限</p></td>
<td><p>仅此对象</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>阅读 RTCUserSearchPropertySet</p>
<p>阅读 RTCUserProvisioningPropertySet</p>
<p>阅读 RTCPropertySet</p>
<p>阅读公共信息</p>
<p>阅读常规信息</p>
<p>阅读个人信息</p>
<p>阅读用户-帐户限制</p></td>
<td><p>子代联系人对象</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>写 RTCUserSearchPropertySet</p>
<p>写 otherIpPhone</p>
<p>写入 displayName</p>
<p>写入说明</p>
<p>写 telephoneNumber</p>
<p>写 msExchUCVoiceMailSettings</p>
<p>写 RTCUserProvisioningPropertySet</p>
<p>写 RTCPropertySet</p>
<p>写 proxyAddresses</p></td>
<td><p>子代联系人对象</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a>为设备对象授予权限

在 OU 上运行设备对象的**CsOuPermission** cmdlet 时, 将向组授予下表中所示的权限。

### <a name="permissions-granted-for-device-objects"></a>为设备对象授予的权限

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>团队</th>
<th>权限</th>
<th>适用于</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>复制目录更改</p></td>
<td><p>仅此对象</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>列表内容</p>
<p>读取所有属性</p>
<p>读取权限</p></td>
<td><p>仅此对象</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>列表内容</p>
<p>读取所有属性</p>
<p>读取权限</p></td>
<td><p>仅此对象</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>阅读 RTCUserSearchPropertySet</p>
<p>阅读 RTCUserProvisioningPropertySet</p>
<p>阅读 RTCPropertySet</p>
<p>阅读公共信息</p>
<p>阅读个人信息</p>
<p>阅读常规信息</p>
<p>阅读用户-帐户限制</p></td>
<td><p>子代联系人对象</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>创建子元素</p>
<p>删除子元素</p>
<p>删除树</p></td>
<td><p>联系人</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>写入 displayName</p>
<p>写入说明</p>
<p>写 telephoneNumber</p></td>
<td><p>子代用户对象</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>写 RTCUserSearchPropertySet</p>
<p>写 otherIpPhone</p>
<p>写入 displayName</p>
<p>写入说明</p>
<p>写 telephoneNumber</p>
<p>写 msExchUCVoiceMailSettings</p>
<p>写 RTCUserProvisioningPropertySet</p>
<p>写 RTCPropertySet</p>
<p>写 proxyAddresses</p></td>
<td><p>子代联系人对象</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a>为 InetOrgPerson 对象授予权限

当你针对 OU 上的 InetOrgPerson 对象运行**CsOuPermission** cmdlet 时, 将向组授予下表中所示的权限。

### <a name="permissions-granted-for-inetorgperson-objects"></a>为 InetOrgPerson 对象授予的权限

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>团队</th>
<th>权限</th>
<th>适用于</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>复制目录更改</p></td>
<td><p>仅此对象</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>列表内容</p>
<p>读取所有属性</p>
<p>读取权限</p></td>
<td><p>仅此对象</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>列表内容</p>
<p>读取所有属性</p>
<p>读取权限</p></td>
<td><p>仅此对象</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>阅读 RTCUserSearchPropertySet</p>
<p>阅读 RTCUserProvisioningPropertySet</p>
<p>阅读 RTCPropertySet</p>
<p>阅读个人信息</p>
<p>阅读公共信息</p>
<p>阅读常规信息</p>
<p>阅读用户-帐户限制</p></td>
<td><p>子代 inetOrgPerson 对象</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>写 RTCUserSearchPropertySet</p>
<p>写 RTCUserProvisioningPropertySet</p>
<p>写 RTCPropertySet</p>
<p>写 proxyAddresses</p></td>
<td><p>子代 inetOrgPerson 对象</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

