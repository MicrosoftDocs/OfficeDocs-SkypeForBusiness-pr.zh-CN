---
title: 由林准备在 Skype 业务服务器所做的更改
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: 本部分介绍的全局设置和对象，以及通用的服务和管理组创建的目录林的准备步骤。
ms.openlocfilehash: 3e37948cae33412ac028d5190c780d6bee5aeeb2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a>由林准备在 Skype 业务服务器所做的更改
 
本部分介绍的全局设置和对象，以及通用的服务和管理组创建的目录林的准备步骤。
  
## <a name="active-directory-global-settings-and-objects"></a>Active Directory 全局设置和对象

如果存储的全局设置配置容器中 （如所有新业务服务器部署 Skype 的是这种情况）、 林准备使用现有的服务容器，添加配置下的**RTC 服务**对象对象。 在 RTC 服务对象中，林准备过程添加类型 msRTCSIP GlobalContainer**全局设置**对象。 全局设置对象包含应用于业务服务器部署 Skype 的所有设置。 如果系统容器中存储的全局设置，林准备过程将使用根域系统容器下的 Microsoft 容器和 RTC 服务对象的 System\Microsoft 对象下。
  
林准备过程还将添加新的**msRTCSIP 域**对象运行该过程时的根域。
  
## <a name="active-directory-universal-service-and-administration-groups"></a>活动目录的通用服务和管理组

林准备过程创建基于您指定的域的通用组，并将这些组的访问控制项 (Ace)。 此步骤在您指定的域的用户容器中创建通用组。 
  
通用组，管理员可以访问和管理全局设置和服务。 林准备过程将添加下列类型的通用组中：
  
- **管理组**这些组定义为 Skype 业务服务器网络管理员角色。
    
- **基础结构部门**这些组提供了特定区域的 Skype 业务服务器基础结构的访问权。 它们的功能组件的管理组。 您不应修改这些组或直接向其添加用户。
    
- **服务组**这些组是访问各种 Skype 业务服务器服务所需的服务帐户。
    
下表描述了管理组。
  
**林准备过程中创建的管理组**

|**管理组**|**说明**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> |允许管理服务器和池设置，包括所有的服务器角色、 全局设置，以及用户成员。  <br/> |
|RTCUniversalUserAdmins  <br/> |允许管理用户设置并将用户从一个服务器或池移到另一个成员。  <br/> |
|RTCUniversalReadOnlyAdmins  <br/> |允许读取服务器、 池和用户设置的成员。  <br/> |
   
下表描述基础结构部门。
  
**林准备过程中创建的基础结构部门**

|**基础结构小组**|**说明**|
|:-----|:-----|
|RTCUniversalGlobalWriteGroup  <br/> |授予对 Skype 业务服务器的全局设置对象的写访问权限。  <br/> |
|RTCUniversalGlobalReadOnlyGroup  <br/> |为业务服务器的 Skype 授予全局设置对象的只读访问。  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |企业服务器用户设置的只读访问权限授予 Skype。  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |业务服务器设置为 Skype 授予只读访问权限。 此组没有访问池级设置，仅对特定于单个服务器的设置。  <br/> |
|RTCUniversalSBATechnicians  <br/> |只读访问权限授予 Skype 业务服务器配置和安装过程都放在本地管理员组的高存活力的分支装置。  <br/> |
   
下表描述了服务组。
  
**林准备过程中创建的服务组**

|**服务组**|**说明**|
|:-----|:-----|
|RTCHSUniversalServices  <br/> |包括用于运行前端服务器，标准版服务器的服务帐户。 此组允许业务服务器全局设置以及 Active Directory 用户对象对 Skype 的服务器读/写访问。  <br/> |
|RTCComponentUniversalServices  <br/> |包含服务帐户来运行 A / V 会议服务器、 Web 服务、 中介服务器、 存档的服务器和监视服务器。  <br/> |
|RTCProxyUniversalServices  <br/> |包含用于为业务服务器边缘服务器运行 Skype 的服务帐户。  <br/> |
|RTCUniversalConfigReplicator  <br/> |包括 Skype 业务服务器集中管理存储复制的服务器可以参与。  <br/> |
|RTCSBAUniversalServices  <br/> |只读访问权限授予 Skype 业务服务器设置，但允许高存活力的分支服务器和高存活力的分支装置部署的安装配置。  <br/> |
   
然后林准备过程，如下所示添加到适当的基础结构组的服务和管理组：
  
- RTCUniversalServerAdmins 被添加到 RTCUniversalGlobalReadOnlyGroup、 RTCUniversalGlobalWriteGroup、 RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup。
    
- RTCUniversalUserAdmins 将添加为 RTCUniversalGlobalReadOnlyGroup、 RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 的成员。
    
- RTCHSUniversalServices、 RTCComponentUniversalServices 和 RTCUniversalReadOnlyAdmins 作为 RTCUniversalGlobalReadOnlyGroup、 RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 的成员。
    
林准备过程还将创建以下基于角色的访问控制 (RBAC) 组：
  
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
    
RBAC 角色和允许为每个任务的详细信息，请参阅规划文档中[基于角色的访问控制](http://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx)。
  
林准备过程创建私钥和公钥的 Ace。 它在全局设置容器用于通过 Skype 业务服务器上创建专用的 Ace。 该容器用于业务服务器只能通过 Skype 和位于配置容器或根域，这取决于您在那里存储全局设置中的系统容器中。 下表中列出了公共 Ace 由林准备过程。
  
**林准备过程所创建的公用 Ace**

|**ACE**|**RTCUniversalGlobalReadOnlyGroup**|
|:-----|:-----|
|根域系统容器 （不继承所得） 中读取**\*** <br/> |X  <br/> |
|读取配置 DisplaySpecifiers 容器 （不继承）  <br/> |X  <br/> |
   
> [!NOTE]
> **\***不能继承的 Ace 不授予在这些容器的子对象的访问。 继承的 Ace 授予在这些容器的子对象的访问。 
  
在配置容器中配置命名上下文，林准备过程执行以下任务：
  
- 添加在 adminContextMenu 下的**RTC 属性**页面项**{AB255F23-2DBD-4bb6-891D-38754AC280EF}**和语言的 adminPropertyPages 属性显示为用户、 联系人和 InetOrgPersons 说明符 (例如，CN =用户显示，CN = 409，CN = DisplaySpecifiers)。
    
- 添加下**扩展权限**应用于用户和联系人类类型**controlAccessRight**的一个**RTCPropertySet**对象。
    
- 添加下**扩展权限**应用于用户、 联系人、 OU 和 DomainDNS 类的类型**controlAccessRight**的一个**RTCUserSearchPropertySet**对象。
    
- 添加在每个语言的组织单位 (OU) 显示说明符的**extraColumns**属性下的**msRTCSIP PrimaryUserAddress** (例如，CN = organizationalUnit 显示，CN = 409，CN = DisplaySpecifiers)，并将复制的值默认显示的**extraColumns**属性 (例如，CN = 默认显示，CN = 409，CN = DisplaySpecifiers)。
    
- 添加**msRTCSIP PrimaryUserAddress**， **msRTCSIP PrimaryHomeServer**， **msRTCSIP UserEnabled**筛选在每种语言的**attributeDisplayNames**属性下的属性显示为用户、 联系人、 说明符和 InetOrgPerson 对象 (例如，在英语： CN = 用户显示，CN = 409，CN = DisplaySpecifiers)。
    

