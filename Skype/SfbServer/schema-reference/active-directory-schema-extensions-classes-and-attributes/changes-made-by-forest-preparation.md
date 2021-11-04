---
title: 林中林准备的更改Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: 本节介绍林准备步骤所创建的全局设置和对象以及通用服务组和通用管理组。
ms.openlocfilehash: 3da4c97a5dab0b7738f01201f9c0cc5b4e34a782
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745868"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a>林中林准备的更改Skype for Business Server

本节介绍林准备步骤所创建的全局设置和对象以及通用服务组和通用管理组。

## <a name="active-directory-global-settings-and-objects"></a>Active Directory 全局设置和对象

如果在配置容器中存储全局设置 (则所有新的 Skype for Business Server 部署) 都会使用现有的服务容器，并将 **RTC 服务** 对象添加到 Configuration\Services 对象下。 在 RTC 服务对象下，林准备添加一个 msRTCSIP-GlobalContainer 类型的 **Global Settings** 对象。 全局设置对象包含应用于部署Skype for Business Server设置。 如果在系统容器中存储全局设置，则林准备会使用根域系统容器下的一个 Microsoft 容器，以及系统\Microsoft 对象下的一个 RTC 服务对象。

林准备还为从中运行此过程的根域添加一个新的 **msRTCSIP-Domain** 对象。

## <a name="active-directory-universal-service-and-administration-groups"></a>Active Directory 通用服务组和通用管理组

林准备根据所指定的域创建通用组，并为这些组添加访问控制项 (ACE)。此步骤将在指定域的用户容器中创建通用组。

通用组允许管理员访问并管理全局设置和服务。林准备将添加以下类型的通用组：

- **管理组** 这些组定义网络管理员Skype for Business Server角色。

- **基础结构组** 这些组提供访问基础结构的特定区域Skype for Business Server权限。 它们用作管理组的组件。 您不应修改这些组或直接向其中添加用户。

- **服务组** 这些组是访问各种服务所需的服务Skype for Business Server帐户。

下表介绍的是管理组。

**在林准备期间创建的管理组**

|**管理组**|**说明**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> |允许成员管理服务器和池设置，包括所有服务器角色、全局设置和用户。  <br/> |
|RTCUniversalUserAdmins  <br/> |允许成员管理用户设置，以及在不同的服务器或池之间移动用户。  <br/> |
|RTCUniversalReadOnlyAdmins  <br/> |允许成员读取服务器、池和用户设置。  <br/> |

下表介绍的是基础结构组。

**在林准备期间创建的基础结构组**

|**基础结构组**|**说明**|
|:-----|:-----|
|RTCUniversalGlobalWriteGroup  <br/> |授予对全局设置对象的写入权限，Skype for Business Server。  <br/> |
|RTCUniversalGlobalReadOnlyGroup  <br/> |授予对全局设置对象的只读访问权限，Skype for Business Server。  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |授予对用户设置的只读Skype for Business Server访问权限。  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |授予对这些设置的只读Skype for Business Server权限。 此组没有对池级别设置的访问权限，只有对单个服务器专用设置的访问权限。  <br/> |
|RTCUniversalSBATechnicians  <br/> |授予对配置Skype for Business Server只读访问权限，在安装期间管理员组位于 survivable Branch 设备的本地服务器中。  <br/> |

下表介绍的是服务组。

**林准备期间创建的服务组**

|**服务组**|**说明**|
|:-----|:-----|
|RTCHSUniversalServices  <br/> |包括用于运行前端服务器和前端服务器Standard Edition帐户。 此组允许服务器对全局设置Skype for Business Server Active Directory 用户对象进行读/写访问。  <br/> |
|RTCComponentUniversalServices  <br/> |包括用于运行 A/V 会议服务器、Web 服务、中介服务器、存档服务器和监控服务器的服务帐户。  <br/> |
|RTCProxyUniversalServices  <br/> |包括用于在边缘服务器上运行Skype for Business Server帐户。  <br/> |
|RTCUniversalConfigReplicator  <br/> |包括可以参与中央管理Skype for Business Server复制的服务器。  <br/> |
|RTCSBAUniversalServices  <br/> |授予对服务器设置Skype for Business Server访问权限，但允许配置 Survivable Branch Server 和 Survivable Branch Appliance 部署。  <br/> |

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

有关 RBAC 角色以及允许每个角色执行的任务的详细信息，请参阅规划文档中的[Role-Based Access Control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control)。

林准备同时创建专用和公共 ACE。 它将在全局设置容器上创建专用 AES，Skype for Business Server。 此容器仅由 Skype for Business Server，并且位于根域的"配置"容器或"系统"容器中，具体取决于存储全局设置的位置。 下表中列出了林准备所创建的公共 ACE。

**林准备所创建的公共 ACE**


| **ACE**                                                                 | **RTCUniversalGlobalReadOnlyGroup** |
|:------------------------------------------------------------------------|:------------------------------------|
| 读取根域系统容器 (继承) **\\**\* <br/>        | X  <br/>                            |
| 读取 Configuration 的 DisplaySpecifiers 容器 (继承)   <br/> | X  <br/>                            |

> [!NOTE]
> <strong>\\</strong>*未继承的 AES 不会授予访问这些容器下的子对象的权限。 继承的 AES 授予访问这些容器下的子对象的权限。

在配置容器上的配置命名上下文中，林准备将执行以下任务：

- 在用户、联系人和 InetOrgPerson 的语言显示说明符（例如 CN=user-Display,CN=409,CN=DisplaySpecifiers）的 adminContextMenu 和 adminPropertyPages 属性下，为“**RTC property**”页添加一个 **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** 条目。

- 在 **Extended-Rights** 下添加一个适用于 User 和 Contact 类的 **controlAccessRight** 类型的 **RTCPropertySet** 对象。

- 在 **Extended-Rights** 下添加一个适用于 User、Contact、OU 和 DomainDNS 类的 **controlAccessRight** 类型的 **RTCUserSearchPropertySet** 对象。

- 在每个语言组织单位 (OU) 显示说明符（例如，CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers）的 **extraColumns** 属性下添加 **msRTCSIP-PrimaryUserAddress**，并复制默认显示（例如，CN=default-Display, CN=409,CN=DisplaySpecifiers）的 **extraColumns** 属性值。

- 在 User、Contact 和 InetOrgPerson 对象的每个语言显示说明符（例如，英文为 CN=user-Display,CN=409,CN=DisplaySpecifiers）的 **attributeDisplayNames** 属性下，添加 **msRTCSIP-PrimaryUserAddress**、**msRTCSIP-PrimaryHomeServer** 和 **msRTCSIP-UserEnabled** 筛选属性。