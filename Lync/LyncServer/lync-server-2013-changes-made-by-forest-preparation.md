---
title: 'Lync Server 2013: 林准备所做的更改'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by forest preparation
ms:assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425791(v=OCS.15)
ms:contentKeyID: 48183734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef94ea82f31871cf90939aa25a130903f15ef756
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-forest-preparation-in-lync-server-2013"></a>Lync Server 2013 中的林准备所做的更改

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-30_

本部分介绍全局设置和对象, 以及由林准备步骤创建的通用服务和管理组。

<div>

## <a name="active-directory-global-settings-and-objects"></a>Active Directory 全局设置和对象

如果在配置容器中存储全局设置 (所有新的 Lync Server 2013 部署的情况), 林准备将使用现有服务容器, 并在配置\\服务下添加**RTC 服务**对象。目标. 在 RTC 服务对象下, 林准备添加了类型 msRTCSIP-GlobalContainer 的**全局设置**对象。 全局设置对象包含适用于 Lync Server 部署的所有设置。 如果在系统容器中存储全局设置, 林准备将使用根域系统容器下的 Microsoft 容器和系统\\Microsoft 对象下的 RTC 服务对象。

林准备还会为运行该过程的根域添加一个新的**MsRTCSIP 域**对象。

</div>

<div>

## <a name="active-directory-universal-service-and-administration-groups"></a>Active Directory 通用服务和管理组

林准备基于你指定的域创建通用组, 并为这些组添加访问控制条目 (Ace)。 此步骤将在你指定的域的用户容器中创建通用组。

通用组允许管理员访问和管理全局设置和服务。 林准备添加了以下类型的通用组:

  - **管理组**   这些组定义 Lync Server 网络的管理员角色。

  - **基础结构组**   这些组提供访问 Lync Server 基础结构的特定区域的权限。 它们充当管理组的组件。 不应修改这些组或直接将用户添加到其中。

  - **服务组**   这些组是访问各种 Lync Server 服务所需的服务帐户。

下表介绍了管理组。

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
<td><p>允许成员管理服务器和池设置, 包括所有服务器角色、全局设置和用户。</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>允许成员管理用户设置并将用户从一个服务器或池移动到另一个服务器或池。</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalReadOnlyAdmins</p></td>
<td><p>允许成员读取服务器、池和用户设置。</p></td>
</tr>
</tbody>
</table>


下表介绍了基础结构组。

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
<td><p>向 Lync Server 的全局设置对象授予写入访问权限。</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalGlobalReadOnlyGroup</p></td>
<td><p>授予 Lync Server 全局设置对象的只读访问权限。</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>授予对 Lync Server 用户设置的只读访问权限。</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>授予对 Lync Server 设置的只读访问权限。 此组无权访问池级别设置, 只能访问特定于单个服务器的设置。</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalSBATechnicians</p></td>
<td><p>授予对 Lync Server 配置的只读访问权限, 并将其放在安装期间 survivable 分支装置的本地管理员组中。</p></td>
</tr>
</tbody>
</table>


下表介绍了服务组。

### <a name="service-groups-created-during-forest-preparation"></a>在林准备期间创建的服务组

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
<td><p>包括用于运行前端服务器和标准版服务器的服务帐户。 此组允许服务器对 Lync Server 全局设置和 Active Directory 用户对象进行读写访问。</p></td>
</tr>
<tr class="even">
<td><p>RTCComponentUniversalServices</p></td>
<td><p>包括用于运行 A/V 会议服务器、Web 服务、中介服务器、存档服务器和监视服务器的服务帐户。</p></td>
</tr>
<tr class="odd">
<td><p>RTCProxyUniversalServices</p></td>
<td><p>包括用于运行 Lync Server Edge 服务器的服务帐户。</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalConfigReplicator</p></td>
<td><p>包括可参与 Lync Server 中央管理存储复制的服务器。</p></td>
</tr>
<tr class="odd">
<td><p>RTCSBAUniversalServices</p></td>
<td><p>授予对 Lync Server 设置的只读访问权限, 但允许配置 survivable 分支服务器和 survivable 分支装置部署。</p></td>
</tr>
</tbody>
</table>


林准备然后将服务和管理组添加到相应的基础结构组, 如下所示:

  - RTCUniversalServerAdmins 已添加到 RTCUniversalGlobalReadOnlyGroup、RTCUniversalGlobalWriteGroup、RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup。

  - RTCUniversalUserAdmins 将添加为 RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 的成员。

  - RTCHSUniversalServices、RTCComponentUniversalServices 和 RTCUniversalReadOnlyAdmins 将添加为 RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 的成员。

林准备还会创建以下基于角色的访问控制 (RBAC) 组:

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

有关 RBAC 角色和每个角色允许执行的任务的详细信息, 请参阅规划文档中的在[Lync Server 2013 中规划基于角色的访问控制](lync-server-2013-planning-for-role-based-access-control.md)。

林准备创建 private 和 public Ace。 它在 Lync Server 使用的全局设置容器上创建专用 Ace。 此容器仅由 Lync Server 使用, 并且位于配置容器或根域中的系统容器中, 具体取决于你存储全局设置的位置。 下表列出了林准备创建的公共 Ace。

### <a name="public-aces-created-by-forest-preparation"></a>由林准备创建的公共 Ace

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>棒</th>
<th>RTCUniversalGlobalReadOnlyGroup</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>读取根域系统容器 (不是继承的)<strong>*</strong></p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>读取配置的 DisplaySpecifiers 容器 (而不是继承的容器)</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <STRONG>*</STRONG>未继承的 Ace 不会向这些容器下的子对象授予访问权限。 继承的 Ace 授予对这些容器下的子对象的访问权限。



</div>

在配置容器的配置命名上下文下, 林准备执行以下任务:

  - 为用户、联系人和 InetOrgPersons 的语言显示说明符的 "adminContextMenu" 和 "adminPropertyPages" 属性下的**RTC 属性**页面添加一个条目 **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** (例如, CN =用户显示, CN = 409, CN = DisplaySpecifiers)。

  - 在应用于用户和联系人类的**扩展权限**下, 添加类型**controlAccessRight**的**RTCPropertySet**对象。

  - 在适用于用户、联系人、OU 和 DomainDNS 类的**扩展权限**下, 添加类型**controlAccessRight**的**RTCUserSearchPropertySet**对象。

  - 在每个语言组织单位 (OU) 显示说明符的**extraColumns**属性下添加**msRTCSIP-PRIMARYUSERADDRESS** (如 CN = ORGANIZATIONALUNIT-display、CN = 409、cn = DisplaySpecifiers), 并将默认显示的**extraColumns**属性 (例如, cn = Default-DISPLAY, cn = 409, Cn = DisplaySpecifiers)。

  - 在每个语言显示说明符的**msRTCSIP**属性下为用户、联系人添加**msRTCSIP PrimaryUserAddress**、 **msRTCSIP-PrimaryHomeServer**和**UserEnabled**筛选属性和 InetOrgPerson 对象 (例如, 在英语中: CN = user-Display, CN = 409, CN = DisplaySpecifiers)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

