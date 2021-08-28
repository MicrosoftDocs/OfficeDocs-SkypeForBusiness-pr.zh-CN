---
title: Active Directory 域服务Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
description: Active Directory 域服务用作 Windows Server 2003、Windows Server 2008、Windows Server 2012 和 Windows Server 2012 R2 网络的目录服务。 Active Directory 域服务还可用作构建Skype for Business Server基础结构的基础。 本节旨在介绍用户Skype for Business Server Active Directory 域服务为 IM、Web 会议、媒体和语音创建可信赖的环境。 有关为 Active Directory 域服务准备环境的详细信息，请参阅部署文档中Skype for Business Server安装域服务。 有关 Active Directory 域服务在 Windows Server 网络中的角色的详细信息，请参阅正在使用的操作系统版本相应的文档。
ms.openlocfilehash: 4af4e4b4dd7a64dd133d36a55ca1c334a12fe97e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604651"
---
# <a name="active-directory-domain-services-for-skype-for-business-server"></a>Active Directory 域服务Skype for Business Server
 
Active Directory 域服务用作 Windows Server 2003、Windows Server 2008、Windows Server 2012 和 Windows Server 2012 R2 网络的目录服务。 Active Directory 域服务还可用作构建Skype for Business Server基础结构的基础。 本节旨在介绍用户Skype for Business Server Active Directory 域服务为 IM、Web 会议、媒体和语音创建可信赖的环境。 有关为 Active Directory 域服务准备环境的详细信息，请参阅部署[文档中Skype for Business Server](../../deploy/install/install.md)安装域服务。 有关 Active Directory 域服务在 Windows Server 网络中的角色的详细信息，请参阅正在使用的操作系统版本相应的文档。
  
Skype for Business Server Active Directory 域服务存储：
  
- 林中所有运行Skype for Business Server服务器都需要的全局设置。
    
- 标识林中所有运行服务器角色Skype for Business Server的服务信息。
    
- 一些用户设置。
    
## <a name="active-directory-infrastructure"></a>Active Directory 基础结构

Active Directory 的基础结构要求包括以下各项：
  
- 域控制器的操作系统要求
    
- 域和林的功能级别要求
    
- 全局编录域要求
    
有关详细信息，请参阅[Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或[Server requirements for Skype for Business Server 2019。](../../../SfBServer2019/plan/system-requirements.md)
  
## <a name="universal-groups"></a>通用组

在准备林期间，Skype for Business Server Active Directory 域服务内创建各种通用组，这些通用组有权访问和管理全局设置和服务。 这些通用组包括：
  
- **管理组**。 这些组定义网络的基本管理员Skype for Business Server角色。 在林准备过程中，这些管理员组将添加到Skype for Business Server组。
    
- **服务组**。 这些组是访问由组织提供的各种服务所需的Skype for Business Server。
    
- **基础结构组**。 这些组提供访问基础结构的特定Skype for Business Server的权限。 这些基础结构组将用作管理组的组件，不应修改这些基础结构组或直接向其中添加用户。 在林准备过程中，特定服务组和管理组将添加到相应的基础结构组中。
    
有关为 Skype for Business Server 准备 AD 时创建的特定通用组以及添加到基础结构组的服务组和管理组的详细信息，请参阅部署文档中的 changes made by [forest preparation in Skype for Business Server。](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)
  
> [!NOTE]
> Skype for Business Server支持 Windows Server 2012 中的通用组，Windows支持域控制器的 Windows Server 2003 操作系统。 通用组的成员可包括域树或林中的任何域中的其他组和帐户，并且可将域树或林中的任何域中的权限分配给这些成员。 通用组支持与管理员委派相结合，简化了对部署Skype for Business Server管理。 例如，不必将一个域添加到另一个域，管理员即可同时管理这两个域。 
  
## <a name="role-based-access-control"></a>基于角色的访问控制

除了创建通用服务组和管理组以及将服务组和管理组添加到相应的通用组之外，林准备还创建 Role-Based Access Control (RBAC) 组。 有关林准备创建的特定 RBAC 组的详细信息，请参阅部署文档中的[Skype for Business Server林准备](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)所做的更改。 有关 RBAC 组详细信息，请参阅[Role-based access control (RBAC) for Skype for Business Server。](role-based-access-control-rbac.md)
  
## <a name="access-control-entries-aces-and-inheritance"></a>访问控制项 (ACE) 与继承

林准备同时创建专用和公共 ACE，并为其创建的通用组添加 ACE。 它将在全局设置容器上创建特定私有 AES，Skype for Business Server。 此容器仅由 Skype for Business Server，并且位于根域的"配置"容器或"系统"容器中，具体取决于存储全局设置的位置。
  
域准备步骤将向通用组添加必要的访问控制项 (ACE)，这些访问控制项将授予承载和管理域中用户的权限。域准备过程将在域根和以下三个内置容器中创建 ACE：“用户”、“计算机”和“域控制器”。
  
有关林准备和域准备创建和添加的公共 AAC 的详细信息，请参阅部署文档中的 changes [made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)和 changes made by domain preparation in [Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-domain-preparation.md) in the Deployment documentation。
  
组织经常会锁定 Active Directory 域服务 (AD DS) 以帮助缓解安全风险。 但是，锁定的 Active Directory 环境可以限制用户Skype for Business Server权限。 这可以包括从容器和 OU 中删除 ACE 以及在“用户”、“联系人”、“InetOrgPerson”或“计算机”对象上禁用权限继承。 在锁定的 Active Directory 环境中，必须在需要权限的容器和 OU 上手动设置权限。
  
## <a name="server-information"></a>服务器信息

激活期间，Skype for Business Server将服务器信息发布到 Active Directory 域服务中的以下三个位置：
  
- 与安装了 SCP (物理) 对应的每个 Active Directory 计算机对象上的服务连接点Skype for Business Server连接点。
    
- 在 **msRTCSIP-Pools** 类的容器中创建的服务器对象。
    
- 拓扑生成器中指定的受信任服务器。
    
## <a name="service-connection-points"></a>服务连接点

Active Directory 域服务中的Skype for Business Server对象都有一个称为 RTC Services 的 SCP，而 SCP 又包含许多标识每台计算机并指定其提供的服务的属性。 在更重要的 SCP 属性中，有 serviceDNSName、serviceDNSNameType、serviceClassname 和 *serviceBindingInformation* 。    第三方资产管理应用程序可以通过针对上述 SCP 属性和其他 SCP 属性进行查询来检索部署中的服务器信息。
  
## <a name="active-directory-server-objects"></a>Active Directory 服务器对象

每个Skype for Business Server角色都有一个对应的 Active Directory 对象，该对象的属性定义了该角色提供的服务。 此外，当激活 Standard Edition 服务器或创建 Enterprise Edition 池时，Skype for Business Server 将在 **msRTCSIP-Pools 容器中创建新的 msRTCSIP-Pool** 对象。  **msRTCSIP-Pool** 类指定池的完全限定域名 (FQDN) ，以及池的前端组件和后端组件之间的关联。  (将Standard Edition服务器视为一个逻辑池，其前端和后端并排在单个计算机上。) 
  
## <a name="trusted-servers"></a>受信任的服务器

在Skype for Business Server中，受信任的服务器是运行拓扑生成器并发布拓扑时指定的服务器。 发布的拓扑（包括所有服务器信息）存储在中央管理存储中。 只有中央管理存储中定义的服务器是受信任的。 在Skype for Business Server中，受信任的服务器是满足以下条件的服务器：
  
- 服务器的 FQDN 出现在存储在中央管理存储中的拓扑中。
    
- 服务器提供了来自受信任的 CA 的有效证书。 有关详细信息，请参阅[Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或[System requirements for Skype for Business Server 2019。](../../../SfBServer2019/plan/system-requirements.md)
    
如果未满足上述任一条件，则该服务器将不会受到信任，并且与该服务器的连接将被拒绝。 此双重要求可防止未授权服务器尝试接管有效服务器的 FQDN（如果不太可能）受到攻击。
  
此外，为了启用 Microsoft Office Communications Server 2007 R2 和 Microsoft Office Communications Server 2007 部署与 Skype for Business Server 服务器进行通信，Skype for Business Server 在林准备期间创建容器，以便存放早期版本的受信任服务器列表。 下表介绍为了与早期部署兼容而创建的容器。
  
**与早期版本兼容的受信任的服务器列表及其 Active Directory 容器**

|**受信任的服务器列表**|**Active Directory 容器**|
|:-----|:-----|
|Standard Edition Server 和企业版池前端服务器  <br/> |RTC 服务/全局设置  <br/> |
|会议服务器  <br/> |RTC 服务/受信任的 MCU  <br/> |
|Web 组件服务器  <br/> |RTC 服务/TrustedWebComponentsServers  <br/> |
|中介服务器和 Communicator Web Access 服务器、应用程序服务器、QoE 注册器、A/V 会议服务（也称作第三方 SIP 服务器）  <br/> |RTC 服务/受信任的服务  <br/> |
|代理服务器  <br/> |Skype for Business Server不支持代理服务器的向后兼容性  <br/> |
   

## <a name="see-also"></a>另请参阅

[为 Active Directory 准备Skype for Business Server](../../deploy/install/prepare-active-directory.md)
