---
title: Skype for Business Server 中的林准备所做的更改
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: 本部分介绍全局设置和对象，以及由林准备步骤创建的通用服务和管理组。
ms.openlocfilehash: 26917915d89aff721e74f094eb8ad5bb72db3cf6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815530"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a>Skype for Business Server 中的林准备所做的更改

本部分介绍全局设置和对象，以及由林准备步骤创建的通用服务和管理组。

## <a name="active-directory-global-settings-and-objects"></a>Active Directory 全局设置和对象

如果在配置容器中存储全局设置（对于所有新的 Skype for business 服务器部署而言），林准备将使用现有服务容器，并在 Configuration\Services 对象下添加**RTC 服务**对象。 在 RTC 服务对象下，林准备添加了类型 msRTCSIP-GlobalContainer 的**全局设置**对象。 全局设置对象包含适用于 Skype for Business 服务器部署的所有设置。 如果在系统容器中存储全局设置，林准备将使用根域系统容器下的 Microsoft 容器和 System\Microsoft 对象下的 RTC 服务对象。

林准备还会为运行该过程的根域添加一个新的**MsRTCSIP 域**对象。

## <a name="active-directory-universal-service-and-administration-groups"></a>Active Directory 通用服务和管理组

林准备基于你指定的域创建通用组，并为这些组添加访问控制条目（Ace）。 此步骤将在你指定的域的用户容器中创建通用组。

通用组允许管理员访问和管理全局设置和服务。 林准备添加了以下类型的通用组：

- **管理组**这些组定义 Skype for business 服务器网络的管理员角色。

- **基础结构组**这些组提供访问 Skype for Business 服务器基础结构的特定区域的权限。 它们充当管理组的组件。 不应修改这些组或直接将用户添加到其中。

- **服务组**这些组是访问各种 Skype for Business 服务器服务所需的服务帐户。

下表介绍了管理组。

**在林准备期间创建的管理组**

|**管理组**|**说明**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> |允许成员管理服务器和池设置，包括所有服务器角色、全局设置和用户。  <br/> |
|RTCUniversalUserAdmins  <br/> |允许成员管理用户设置并将用户从一个服务器或池移动到另一个服务器或池。  <br/> |
|RTCUniversalReadOnlyAdmins  <br/> |允许成员读取服务器、池和用户设置。  <br/> |

下表介绍了基础结构组。

**在林准备期间创建的基础结构组**

|**基础结构组**|**说明**|
|:-----|:-----|
|RTCUniversalGlobalWriteGroup  <br/> |向 Skype for Business 服务器的全局设置对象授予写入访问权限。  <br/> |
|RTCUniversalGlobalReadOnlyGroup  <br/> |向 Skype for Business Server 的全局设置对象授予只读访问权限。  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |授予对 Skype for Business 服务器用户设置的只读访问权限。  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |授予对 Skype for Business 服务器设置的只读访问权限。 此组无权访问池级别设置，只能访问特定于单个服务器的设置。  <br/> |
|RTCUniversalSBATechnicians  <br/> |授予对 Skype for Business 服务器配置的只读访问权限，并将其放在安装期间 survivable 分支装置的本地管理员组中。  <br/> |

下表介绍了服务组。

**在林准备期间创建的服务组**

|**服务组**|**说明**|
|:-----|:-----|
|RTCHSUniversalServices  <br/> |包括用于运行前端服务器和标准版服务器的服务帐户。 此组允许服务器对 Skype for Business 服务器全局设置和 Active Directory 用户对象进行读/写访问。  <br/> |
|RTCComponentUniversalServices  <br/> |包括用于运行 A/V 会议服务器、Web 服务、中介服务器、存档服务器和监视服务器的服务帐户。  <br/> |
|RTCProxyUniversalServices  <br/> |包括用于运行 Skype for Business Server Edge 服务器的服务帐户。  <br/> |
|RTCUniversalConfigReplicator  <br/> |包括可参与 Skype for Business Server 中央管理存储复制的服务器。  <br/> |
|RTCSBAUniversalServices  <br/> |授予对 Skype for Business 服务器设置的只读访问权限，但允许配置 survivable 分支服务器和 survivable 分支装置部署。  <br/> |

林准备然后将服务和管理组添加到相应的基础结构组，如下所示：

- RTCUniversalServerAdmins 已添加到 RTCUniversalGlobalReadOnlyGroup、RTCUniversalGlobalWriteGroup、RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup。

- RTCUniversalUserAdmins 将添加为 RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 的成员。

- RTCHSUniversalServices、RTCComponentUniversalServices 和 RTCUniversalReadOnlyAdmins 将添加为 RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 的成员。

林准备还会创建以下基于角色的访问控制（RBAC）组：

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

有关 RBAC 角色和每个角色允许执行的任务的详细信息，请参阅规划文档中的[基于角色的访问控制](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx)。

林准备创建 private 和 public Ace。 它在由 Skype for Business 服务器使用的全局设置容器上创建专用 Ace。 此容器仅由 Skype for Business 服务器使用，并且位于配置容器或根域的系统容器中，具体取决于全局设置的存储位置。 下表列出了林准备创建的公共 Ace。

**由林准备创建的公共 Ace**


| **棒**                                                                 | **RTCUniversalGlobalReadOnlyGroup** |
|:------------------------------------------------------------------------|:------------------------------------|
| 读取根域系统容器（不是继承的）**\\**\* <br/>        | X  <br/>                            |
| 读取配置的 DisplaySpecifiers 容器（而不是继承的容器）  <br/> | X  <br/>                            |

> [!NOTE]
> <strong>\\</strong>* 未继承的 Ace 不会向这些容器下的子对象授予访问权限。 继承的 Ace 授予对这些容器下的子对象的访问权限。

在配置容器的配置命名上下文下，林准备执行以下任务：

- 为用户、联系人和 InetOrgPersons 的语言显示说明符的 adminContextMenu 和 adminPropertyPages 属性（例如，CN = 用户显示，CN = 409，cn = DisplaySpecifiers）下的**RTC 属性**页添加一个条目 **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** 。

- 在应用于用户和联系人类的**扩展权限**下，添加类型**controlAccessRight**的**RTCPropertySet**对象。

- 在适用于用户、联系人、OU 和 DomainDNS 类的**扩展权限**下，添加类型**controlAccessRight**的**RTCUserSearchPropertySet**对象。

- 在每个语言组织单位（OU）显示说明符（例如，CN = organizationalUnit-Display，CN = 409，CN = DisplaySpecifiers）的**extraColumns**属性下添加**msRTCSIP-PrimaryUserAddress** ，并复制默认显示的**extraColumns**属性的值（例如，CN = default-display、cn = 409）。

- 为用户、联系人和 MsRTCSIP 对象（例如英语： CN = 用户显示，CN = 409，cn = UserEnabled）添加每个语言显示说明符的**attributeDisplayNames**属性下的**msRTCSIP**、 **msRTCSIP-PrimaryHomeServer**和**InetOrgPerson** DisplaySpecifiers 筛选属性。


