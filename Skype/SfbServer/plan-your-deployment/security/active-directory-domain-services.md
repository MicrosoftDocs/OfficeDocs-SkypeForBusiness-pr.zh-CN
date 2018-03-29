---
title: Skype for Business Server 2015 的 Active Directory 域服务
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 4/6/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
description: Active Directory 域服务的 Windows Server 2003 和 Windows Server 2008，Windows Server 2012，和 Windows Server 2012 R2 网络目录服务的作用。 Active Directory 域服务还作为在其构建 Skype 业务服务器 2015年安全基础结构的基础。 本节的目的是为了说明如何业务服务器 2015年的 Skype 使用 Active Directory 域服务的即时消息、 Web 会议、 媒体和语音创建可信赖的环境。 有关为 Active Directory 域服务准备您的环境的详细信息，请参阅安装 Skype 的业务服务器 2015年部署文档中。 Active Directory 域服务在 Windows 服务器网络中的作用的详细信息，请参阅您正在使用的操作系统版本的文档。
ms.openlocfilehash: eb4a2d5a070f7840733dd20da859d2dede38750a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="active-directory-domain-services-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 的 Active Directory 域服务
 
Active Directory 域服务的 Windows Server 2003 和 Windows Server 2008，Windows Server 2012，和 Windows Server 2012 R2 网络目录服务的作用。 Active Directory 域服务还作为在其构建 Skype 业务服务器 2015年安全基础结构的基础。 本节的目的是为了说明如何业务服务器 2015年的 Skype 使用 Active Directory 域服务的即时消息、 Web 会议、 媒体和语音创建可信赖的环境。 有关为 Active Directory 域服务准备您的环境的详细信息，请参阅部署文档[的业务服务器 2015年安装 Skype](../../deploy/install/install.md) 。 Active Directory 域服务在 Windows 服务器网络中的作用的详细信息，请参阅您正在使用的操作系统版本的文档。
  
商业服务器 2015年的 Skype 使用 Active Directory 域服务来存储：
  
- 需要运行 Skype 业务服务器 2015 树林中的所有服务器的全局设置。
    
- 服务标识运行 Skype 业务服务器 2015 树林中的所有服务器角色的信息。
    
- 一些用户设置。
    
## <a name="active-directory-infrastructure"></a>活动目录基础结构

基础架构要求： 活动目录如下所示：
  
- 域控制器的操作系统要求
    
- 域和林的功能级别要求
    
- 全局编录域要求
    
有关详细信息，请参阅部署文档中的[业务服务器 2015年的 Skype 的环保要求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)。
  
## <a name="universal-groups"></a>通用组

此目录林的准备，在业务服务器 2015年的 Skype 创建 Active Directory 域服务有权访问和管理全局设置和服务中的各种通用组。 这些通用组包括：
  
- **管理组**。 这些组定义为业务服务器网络 Skype 基本管理员角色。 在目录林的准备，这些管理员组被添加到 Skype 业务服务器基础结构组。
    
- **服务组**。 这些组是访问业务服务器 Skype 所提供的各种服务所需的服务帐户。
    
- **基础结构组**。 这些组提供了特定区域的 Skype 业务服务器基础结构的访问权。 这些基础结构组将用作管理组的组件，不应修改这些基础结构组或直接向其中添加用户。 在林的准备过程中，会将特定的服务组和管理组添加到适当的基础结构组。
    
在 AD 准备 Skype 业务服务器，以及添加到基础结构部门的服务和管理组时创建特定通用组的详细信息，请参阅[由林准备在 Skype 业务所做的更改服务器](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)部署文档中。
  
> [!NOTE]
> Skype 的业务服务器 2015 Windows Server 2012，以及 Windows Server 2003 的域控制器的操作系统支持通用组。 通用组的成员可包括域树或林中的任何域中的其他组和帐户，并且可将域树或林中的任何域中的权限分配给这些成员。 通用组的支持，加上管理员委派，简化了业务服务器部署 Skype 的管理。 例如，不必将一个域添加到另一个域，管理员即可同时管理这两个域。 
  
## <a name="role-based-access-control"></a>基于角色的访问控制

除创建通用服务组和管理组以及将服务组和管理组添加到适当的通用组之外，林准备还创建基于角色的访问控制 (RBAC) 组。 林准备过程所创建的特定的 RBAC 组的详细信息，请参阅部署文档中[林准备在 Skype 业务服务器中进行更改](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)。 关于 RBAC 组的详细信息，请参阅[有关业务服务器 2015年的 Skype 的基于角色的访问控制 (RBAC)](role-based-access-control-rbac.md)。
  
## <a name="access-control-entries-aces-and-inheritance"></a>访问控制项 (ACE) 与继承

林准备同时创建专用和公共 ACE，并为其创建的通用组添加 ACE。 它在全局设置容器用于通过 Skype 业务服务器上创建特定专用 Ace。 该容器用于业务服务器只能通过 Skype 和位于配置容器或根域，这取决于您在那里存储全局设置中的系统容器中。
  
域准备步骤将向通用组添加必要的访问控制项 (ACE)，这些访问控制项将授予承载和管理域中用户的权限。域准备过程将在域根和以下三个内置容器中创建 ACE：“用户”、“计算机”和“域控制器”。
  
[林准备在 Skype 业务服务器中进行更改](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)和[更改由 Skype 业务服务器在域准备](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-domain-preparation.md)有关公共 Ace 的详细信息创建，并准备林和域准备添加，请参见部署文档。
  
组织通常锁定 Active Directory 域服务 (AD DS)，以帮助降低安全风险。 但是，锁定的 Active Directory 环境可以限制业务服务器 2015年的 Skype 所要求的权限。 这可以包括从容器和 OU 中删除 ACE 以及在“用户”、“联系人”、“InetOrgPerson”或“计算机”对象上禁用权限继承。 在锁定状态下活动目录环境权限必须手动设置容器和要求他们的 Ou。
  
## <a name="server-information"></a>服务器信息

在激活期间，Skype 的业务服务器 2015年将服务器信息发布到 Active Directory 域服务在以下三个位置：
  
- 服务连接点 (SCP) 对应于物理计算机安装 Skype 业务服务器 2015年的每个活动目录计算机对象上。
    
- 在 **msRTCSIP-Pools** 类的容器中创建的服务器对象。
    
- 拓扑生成器中指定受信任的服务器。
    
## <a name="service-connection-points"></a>服务连接点

每个业务服务器 2015年对象在 Active Directory 域服务 Skype 的 SCP 称为 RTC 服务，又包含多个属性，标识每一台计算机，并指定它所提供的服务。 更重要的是 SCP 特性包括*serviceDNSName* 、 *serviceDNSNameType* 、 *serviceClassname*和*serviceBindingInformation* 。 第三方资产管理应用程序可以通过针对上述 SCP 属性和其他 SCP 属性进行查询来检索部署中的服务器信息。
  
## <a name="active-directory-server-objects"></a>Active Directory 服务器对象

每个 Skype 业务服务器 2015年服务器角色都有相应活动目录对象的属性定义该角色提供的服务。 此外，标准版服务器激活时，或当创建企业版池，Skype 的业务服务器 2015 **msRTCSIP 池**容器中创建一个新的**msRTCSIP 池**对象。 **MsRTCSIP 池**类指定的池，池中的前端和后端组件之间的关联以及完全限定的域名 (FQDN)。 （标准版服务器被视为其前端和后端都搭配一台计算机的逻辑池。）
  
## <a name="trusted-servers"></a>受信任的服务器

在业务服务器 2015年的 Skype，受信任的服务器都是运行拓扑生成器并发布拓扑时指定的。 发布的拓扑（包括所有服务器信息）存储在中央管理存储中。 只有中央管理存储中定义的服务器是受信任的。 在业务服务器 2015年的 Skype，受信任的服务器是一个满足以下条件：
  
- 服务器的 FQDN 出现在存储在中央管理存储中的拓扑中。
    
- 服务器提供了来自受信任的 CA 的有效证书。 有关详细信息，请参阅[有关业务服务器 2015年的 Skype 的环境要求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)。
    
如果未满足上述任一条件，则该服务器将不会受到信任，并且与该服务器的连接将被拒绝。 这种双要求防止恶意服务器尝试接管一个有效的服务器的 FQDN 的可能，如果不可能，攻击。
  
此外，要使 Microsoft Office 通信服务器 2007 R2 和 Microsoft Office 通信服务器 2007年部署与 Skype 业务服务器 2015年服务器进行通信，Skype 的业务服务器 2015年创建容器在林准备用于保存的以前的版本中为受信任的服务器列表。 下表介绍为了与早期部署兼容而创建的容器。
  
**与以前版本的兼容性为受信任服务器列表和他们的 Active Directory 容器**

|**受信任的服务器列表**|**活动目录容器**|
|:-----|:-----|
|Standard Edition Server 和企业版池前端服务器  <br/> |RTC 服务/全局设置  <br/> |
|会议服务器  <br/> |RTC 服务/受信任的 MCU  <br/> |
|Web 组件服务器  <br/> |RTC 服务/TrustedWebComponentsServers  <br/> |
|中介服务器和 Communicator Web Access 服务器、应用程序服务器、QoE 注册器、A/V 会议服务（也称作第三方 SIP 服务器）  <br/> |RTC 服务/受信任的服务  <br/> |
|代理服务器  <br/> |Skype 的业务服务器 2015年对代理服务器不支持向后兼容性  <br/> |
   

