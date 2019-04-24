---
title: Skype 中为 Business Server 的林准备所做的更改
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: 本节介绍的全局设置和对象以及通用服务组和管理组林准备步骤创建的。
ms.openlocfilehash: 27b8e183f4c76c7c5db71af1422ba9185206632a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213422"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a>Skype 中为 Business Server 的林准备所做的更改

本节介绍的全局设置和对象以及通用服务组和管理组林准备步骤创建的。

## <a name="active-directory-global-settings-and-objects"></a>Active Directory 全局设置和对象

如果 （如 Business Server 部署的所有新 Skype 的是这种情况） 在配置容器中存储全局设置，林准备使用现有的服务容器，并将添加下配置 \ **RTC 服务**对象对象。 在 RTC 服务对象下，林准备添加一个 Msrtcsip-globalcontainer 类型的**全局设置**对象。 全局设置对象容纳适用于业务服务器部署 Skype 的所有设置。 如果在系统容器中存储全局设置，林准备使用根域系统容器下的 Microsoft 容器和 System\Microsoft 对象下的 RTC 服务对象。

林准备还添加新的**Msrtcsip-domain**对象在其中运行此过程的根域。

## <a name="active-directory-universal-service-and-administration-groups"></a>Active Directory 通用服务和通用管理组

林准备创建基于指定的域的通用组，并将这些组的访问控制项 (Ace)。 此步骤所指定的域的用户容器中创建通用组。

通用组允许管理员访问和管理全局设置和服务。 林准备添加以下类型的通用组：

- **管理组**这些组为 Business Server 网络 Skype 定义管理员角色。

- **基础结构组**这些组将提供的特定区域的企业服务器基础结构 Skype 的访问权。 他们将作为管理组的组件。 不应修改这些组，或直接向其中添加用户。

- **服务组**这些组是访问业务 Server 服务的各种 Skype 所需的服务帐户。

下表介绍的是管理组。

**林准备期间创建的管理组**

|**管理组**|**说明**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> |允许成员管理服务器和池设置，包括所有服务器角色、 全局设置和用户。  <br/> |
|RTCUniversalUserAdmins  <br/> |允许成员管理用户设置并将用户从一个服务器或池移到另一个。  <br/> |
|RTCUniversalReadOnlyAdmins  <br/> |允许成员读取服务器、 池和用户设置。  <br/> |

下表介绍的是基础结构组。

**林准备期间创建的基础结构组**

|**基础结构组**|**说明**|
|:-----|:-----|
|RTCUniversalGlobalWriteGroup  <br/> |授予对业务服务器 Skype 的全局设置对象的写访问权限。  <br/> |
|RTCUniversalGlobalReadOnlyGroup  <br/> |授予对 Skype 的全局设置对象的只读访问权限的业务服务器。  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |授予对 Skype 的只读访问权限的企业服务器用户设置。  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |授予对 Skype 的只读访问权限的业务服务器设置。 此组没有对池级别设置，仅对特定于单个服务器设置的访问。  <br/> |
|RTCUniversalSBATechnicians  <br/> |授予对 Skype 的只读访问权限的业务服务器配置和安装过程中被放在 survivable branch appliance 的 Local Administrators 组中。  <br/> |

下表介绍的是服务组。

**林准备期间创建的服务组**

|**服务组**|**说明**|
|:-----|:-----|
|RTCHSUniversalServices  <br/> |包括用于运行前端服务器和 Standard Edition server 的服务帐户。 此组允许 Skype 服务器读/写访问业务 Server 全局设置和 Active Directory 用户对象。  <br/> |
|RTCComponentUniversalServices  <br/> |包括服务帐户用于运行 A / V 会议服务器、 Web 服务、 中介服务器、 存档服务器和监控服务器。  <br/> |
|RTCProxyUniversalServices  <br/> |包括用于运行 Skype 业务 Server 边缘服务器的服务帐户。  <br/> |
|RTCUniversalConfigReplicator  <br/> |业务 Server 中央管理存储复制 Skype 包括可参与的服务器。  <br/> |
|RTCSBAUniversalServices  <br/> |授予对 Skype 的只读访问权限的业务服务器设置，但允许配置 survivable branch server 和 survivable branch appliance 部署的安装。  <br/> |

然后，林准备，如下所示将服务和管理组添加到适当的基础结构组：

- RTCUniversalServerAdmins 添加到 RTCUniversalGlobalReadOnlyGroup、 RTCUniversalGlobalWriteGroup、 RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 中。

- RTCUniversalUserAdmins 被添加为 RTCUniversalGlobalReadOnlyGroup、 RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 的成员。

- RTCHSUniversalServices、 RTCComponentUniversalServices 和 RTCUniversalReadOnlyAdmins 添加为 RTCUniversalGlobalReadOnlyGroup、 RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 的成员。

林准备还创建以下基于角色的访问控制 (RBAC) 组：

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

有关 RBAC 角色以及允许每个任务的详细信息，请参阅规划文档中的[基于角色的访问控制](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx)。

林准备创建专用和公共 Ace。 它在 for Business Server 使用的 Skype 的全局设置容器创建专用 Ace。 此容器只能由 Skype 用于业务服务器，并位于在配置容器或根域，具体取决于您在其中存储全局设置中的系统容器中。 下表列出了林准备所创建的公共 Ace。

**林准备创建的公共 Ace**


| **ACE**                                                                 | **RTCUniversalGlobalReadOnlyGroup** |
|:------------------------------------------------------------------------|:------------------------------------|
| 读取根域系统容器 （非继承）**\\**\* <br/>        | X  <br/>                            |
| 读取配置的 DisplaySpecifiers 容器 （非继承）  <br/> | X  <br/>                            |

> [!NOTE]
> <strong>\\</strong>* 不继承的 Ace 不会授予对这些容器下的子对象的访问。 继承的 Ace 将授予对这些容器下的子对象的访问。

在配置容器下配置命名上下文中，林准备将执行以下任务：

- 添加条目 **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** **RTC 属性**页下 adminContextMenu 和 adminPropertyPages 属性的语言显示说明符用户、 联系人和 Inetorgperson (例如，CN =User-display，CN = 409，CN = DisplaySpecifiers)。

- 添加在适用于 User 和 Contact 类的**扩展权限**下，键入**controlAccessRight**的**RTCPropertySet**对象。

- 添加在适用于用户、 联系人、 OU 和 DomainDNS 类的**扩展权限**下，键入**controlAccessRight**的**RTCUserSearchPropertySet**对象。

- 添加的每个语言组织单位 (OU) 显示说明符的**extraColumns**属性下**Msrtcsip-primaryuseraddress** (例如，CN = Organizationalunit-display，CN = 409，CN = DisplaySpecifiers)，并将复制的值默认显示的**extraColumns**属性 (例如，CN = Default-display，CN = 409，CN = DisplaySpecifiers)。

- 添加**Msrtcsip-primaryuseraddress**、 **Msrtcsip-primaryhomeserver**和**Msrtcsip-userenabled**筛选属性的每种语言的**attributeDisplayNames**属性下显示用户、 联系人、 说明符和 InetOrgPerson 对象 (例如，英文： CN = User-display，CN = 409，CN = DisplaySpecifiers)。


