---
title: Lync Server 2013：林准备所做的更改
description: Lync Server 2013：林准备所做的更改。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by forest preparation
ms:assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425791(v=OCS.15)
ms:contentKeyID: 48183734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c9bc40539c285e03610b2fc97166842473997fb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543648"
---
# <a name="changes-made-by-forest-preparation-in-lync-server-2013"></a>Lync Server 2013 中的林准备所做的更改

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-30_

本节介绍林准备步骤所创建的全局设置和对象以及通用服务组和通用管理组。

<div>

## <a name="active-directory-global-settings-and-objects"></a>Active Directory 全局设置和对象

如果将全局设置存储在 "配置" 容器中 (与所有新的 Lync Server 2013 部署) 的情况相同，则林准备将使用现有服务容器，并在配置服务对象下添加 **RTC 服务** 对象 \\ 。 在 RTC 服务对象下，林准备添加一个 msRTCSIP-GlobalContainer 类型的**Global Settings**对象。 全局设置对象包含适用于 Lync Server 部署的所有设置。 如果将全局设置存储在系统容器中，林准备将使用根域系统容器下的 Microsoft 容器和系统 Microsoft 对象下的 RTC 服务对象 \\ 。

林准备还为从中运行此过程的根域添加一个新的 **msRTCSIP-Domain** 对象。

</div>

<div>

## <a name="active-directory-universal-service-and-administration-groups"></a>Active Directory 通用服务组和通用管理组

林准备根据所指定的域创建通用组，并为这些组添加访问控制项 (ACE)。此步骤将在指定域的用户容器中创建通用组。

通用组允许管理员访问并管理全局设置和服务。林准备将添加以下类型的通用组：

  - **管理组**    这些组定义 Lync Server 网络的管理员角色。

  - **基础结构组**    这些组提供访问 Lync Server 基础结构的特定区域的权限。 它们用作管理组的组件。 您不应修改这些组或直接向其中添加用户。

  - **服务组**    这些组是访问各种 Lync Server 服务所需的服务帐户。

下表介绍的是管理组。

### <a name="administrative-groups-created-during-forest-preparation"></a>在林准备期间创建的管理组

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>管理组</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>允许成员管理服务器和池设置，包括所有服务器角色、全局设置和用户。</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>允许成员管理用户设置，以及在不同的服务器或池之间移动用户。</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalReadOnlyAdmins</p></td>
<td><p>允许成员读取服务器、池和用户设置。</p></td>
</tr>
</tbody>
</table>


下表介绍的是基础结构组。

### <a name="infrastructure-groups-created-during-forest-preparation"></a>在林准备期间创建的基础结构组

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>基础结构组</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalGlobalWriteGroup</p></td>
<td><p>为 Lync Server 授予对全局设置对象的写入权限。</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalGlobalReadOnlyGroup</p></td>
<td><p>为 Lync Server 授予对全局设置对象的只读访问权限。</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>授予对 Lync Server 用户设置的只读访问权限。</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>授予对 Lync Server 设置的只读访问权限。 此组没有对池级别设置的访问权限，只有对单个服务器专用设置的访问权限。</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalSBATechnicians</p></td>
<td><p>授予对 Lync Server 配置的只读访问权限，并将其放在安装过程中 survivable 分支设备的本地 Administrators 组中。</p></td>
</tr>
</tbody>
</table>


下表介绍的是服务组。

### <a name="service-groups-created-during-forest-preparation"></a>林准备期间创建的服务组

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>服务组</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>包括用于运行前端服务器和 Standard Edition 服务器的服务帐户。 此组允许服务器对 Lync Server 全局设置和 Active Directory 用户对象的读/写访问权限。</p></td>
</tr>
<tr class="even">
<td><p>RTCComponentUniversalServices</p></td>
<td><p>包括用于运行 A/V 会议服务器、Web 服务、中介服务器、存档服务器和监视服务器的服务帐户。</p></td>
</tr>
<tr class="odd">
<td><p>RTCProxyUniversalServices</p></td>
<td><p>包括用于运行 Lync Server 边缘服务器的服务帐户。</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalConfigReplicator</p></td>
<td><p>包括可以参与 Lync Server 中央管理存储复制的服务器。</p></td>
</tr>
<tr class="odd">
<td><p>RTCSBAUniversalServices</p></td>
<td><p>授予对 Lync Server 设置的只读访问权限，但允许安装 survivable 分支服务器和 survivable 分支设备部署的配置。</p></td>
</tr>
</tbody>
</table>


然后，林准备将服务组和管理组添加到适当的基础结构组，具体如下：

  - 将 RTCUniversalServerAdmins 添加到 RTCUniversalGlobalReadOnlyGroup、RTCUniversalGlobalWriteGroup、RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 中。

  - RTCUniversalUserAdmins 被添加为 RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 的成员。

  - RTCHSUniversalServices、RTCComponentUniversalServices 和 RTCUniversalReadOnlyAdmins 添加为 RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 的成员。

林准备还创建了以下基于角色的访问控制 (RBAC) 组：

  - CSAdministrator

  - CSArchivingAdministrator

  - CSHelpDesk

  - CSLocationAdministrator

  - CSResponseGroupAdministrator

  - CSServerAdministrator

  - CSUserAdministrator

  - CSViewOnlyAdministrator

  - CSVoiceAdministrator

  - CsPersistentChatAdministator

  - CsResponseGroupManager

有关 RBAC 角色和每个角色允许执行的任务的详细信息，请参阅规划文档中的在 [Lync Server 2013 中规划基于角色的访问控制](lync-server-2013-planning-for-role-based-access-control.md) 。

林准备同时创建专用和公共 ACE。 它在 Lync Server 使用的全局设置容器上创建专用 Ace。 此容器仅由 Lync Server 使用，并位于配置容器或根域中的系统容器中，具体取决于存储全局设置的位置。 下表中列出了林准备所创建的公共 ACE。

### <a name="public-aces-created-by-forest-preparation"></a>林准备所创建的公共 ACE

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>RTCUniversalGlobalReadOnlyGroup</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>读取根域系统容器（非继承）<strong>*</strong></p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>读取配置的 DisplaySpecifiers 容器（非继承）</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <STRONG>*</STRONG>未继承的 Ace 不会向这些容器下的子对象授予访问权限。 继承的 Ace 授予对这些容器下的子对象的访问权限。



</div>

在配置容器上的配置命名上下文中，林准备将执行以下任务：

  - 在用户、联系人和 InetOrgPerson 的语言显示说明符（例如 CN=user-Display,CN=409,CN=DisplaySpecifiers）的 adminContextMenu 和 adminPropertyPages 属性下，为“**RTC property**”页添加一个 **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** 条目。

  - 在 **Extended-Rights** 下添加一个适用于 User 和 Contact 类的 **controlAccessRight** 类型的 **RTCPropertySet** 对象。

  - 在 **Extended-Rights** 下添加一个适用于 User、Contact、OU 和 DomainDNS 类的 **controlAccessRight** 类型的 **RTCUserSearchPropertySet** 对象。

  - 在每个语言组织单位 (OU) 显示说明符（例如，CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers）的 **extraColumns** 属性下添加 **msRTCSIP-PrimaryUserAddress**，并复制默认显示（例如，CN=default-Display, CN=409,CN=DisplaySpecifiers）的 **extraColumns** 属性值。

  - 在 User、Contact 和 InetOrgPerson 对象的每个语言显示说明符（例如，英文为 CN=user-Display,CN=409,CN=DisplaySpecifiers）的 **attributeDisplayNames** 属性下，添加 **msRTCSIP-PrimaryUserAddress**、**msRTCSIP-PrimaryHomeServer** 和 **msRTCSIP-UserEnabled** 筛选属性。

</div>

</div>

<span> </span>

</div>

</div>

</div>

