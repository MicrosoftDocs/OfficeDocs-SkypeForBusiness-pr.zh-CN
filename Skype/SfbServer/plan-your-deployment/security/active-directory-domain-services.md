---
title: 业务服务器 Skype 的的 active Directory 域服务
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
description: Active Directory 域服务作为 Windows Server 2003、 Windows Server 2008、 Windows Server 2012 和 Windows Server 2012 R2 网络的目录服务。 Active Directory 域服务还可用作在其中生成业务服务器安全基础结构 Skype。 本节旨在介绍 Skype 业务 server 如何使用 Active Directory 域服务为 IM、 Web 会议、 媒体和语音创建可信的环境。 有关您的环境准备 Active Directory 域服务的详细信息，请参阅安装 Skype for Business Server 部署文档。 有关 Windows Server 网络中的 Active Directory 域服务角色的详细信息，请参阅您使用的操作系统版本的文档。
ms.openlocfilehash: 1664f3b354078c79429b20e7654b363ce9fccb7f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213659"
---
# <a name="active-directory-domain-services-for-skype-for-business-server"></a>业务服务器 Skype 的的 active Directory 域服务
 
Active Directory 域服务作为 Windows Server 2003、 Windows Server 2008、 Windows Server 2012 和 Windows Server 2012 R2 网络的目录服务。 Active Directory 域服务还可用作在其中生成业务服务器安全基础结构 Skype。 本节旨在介绍 Skype 业务 server 如何使用 Active Directory 域服务为 IM、 Web 会议、 媒体和语音创建可信的环境。 有关 Active Directory 域服务准备您的环境详细信息，请参阅部署文档中的[业务服务器安装 Skype](../../deploy/install/install.md) 。 有关 Windows Server 网络中的 Active Directory 域服务角色的详细信息，请参阅您使用的操作系统版本的文档。
  
Skype 业务服务器使用 Active Directory 域服务来存储：
  
- 运行 Skype 业务服务器林中的所有服务器都需要的全局设置。
    
- 标识林中的业务服务器运行 Skype 的所有服务器角色的服务信息。
    
- 一些用户设置。
    
## <a name="active-directory-infrastructure"></a>Active Directory 基础结构

Active directory 基础结构要求包括：
  
- 域控制器的操作系统要求
    
- 域和林的功能级别要求
    
- 全局编录域要求
    
有关详细信息，请参阅[环境要求的业务服务器 2015 Skype](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或[业务服务器 2019年的 Skype 的服务器要求](../../../SfBServer2019/plan/system-requirements.md)。
  
## <a name="universal-groups"></a>通用组

准备的林中，期间 Skype 业务服务器创建各种通用组有权访问和管理全局设置和服务的 Active Directory 域服务中。 这些通用组包括：
  
- **管理组**。 这些组定义 Skype Business Server 网络的基本管理员角色。 林准备期间这些管理员组的业务服务器基础结构组添加到 Skype。
    
- **服务组**。 这些组是访问 Skype 业务服务器提供的各种服务所需的服务帐户。
    
- **基础结构组**。 这些组将提供的特定区域的企业服务器基础结构 Skype 的访问权。 这些基础结构组将用作管理组的组件，不应修改这些基础结构组或直接向其中添加用户。 在林的准备过程中，会将特定的服务组和管理组添加到适当的基础结构组。
    
有关特定 AD 准备 Skype 企业服务器，以及获取添加到基础结构组服务和管理组时创建的通用组的详细信息，请参阅[中 Skype for Business 的林准备所做的更改服务器](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)部署文档中。
  
> [!NOTE]
> Skype 业务服务器中的 Windows Server 2012，以及对应的域控制器的 Windows Server 2003 操作系统支持通用组。 通用组的成员可包括域树或林中的任何域中的其他组和帐户，并且可将域树或林中的任何域中的权限分配给这些成员。 通用组支持与管理员委派组合简化了管理对于业务服务器部署 Skype。 例如，不必将一个域添加到另一个域，管理员即可同时管理这两个域。 
  
## <a name="role-based-access-control"></a>基于角色的访问控制

除创建通用服务组和管理组以及将服务组和管理组添加到适当的通用组之外，林准备还创建基于角色的访问控制 (RBAC) 组。 有关林准备所创建的特定 RBAC 组的详细信息，请参阅部署文档中的[Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)。 有关 RBAC 组的详细信息，请参阅[基于角色的访问控制 (RBAC) 的 Skype 业务服务器](role-based-access-control-rbac.md)。
  
## <a name="access-control-entries-aces-and-inheritance"></a>访问控制项 (ACE) 与继承

林准备同时创建专用和公共 ACE，并为其创建的通用组添加 ACE。 它在 for Business Server 使用的 Skype 的全局设置容器中创建特定的专用 Ace。 此容器只能由 Skype 用于业务服务器，并位于在配置容器或根域，具体取决于您在其中存储全局设置中的系统容器中。
  
域准备步骤将向通用组添加必要的访问控制项 (ACE)，这些访问控制项将授予承载和管理域中用户的权限。域准备过程将在域根和以下三个内置容器中创建 ACE：“用户”、“计算机”和“域控制器”。
  
有关的公共 Ace 的详细信息创建并添加林准备和域准备，请参阅[中的业务服务器 Skype 的林准备所做的更改](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)和中[所做的 Skype 业务服务器中的域准备更改](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-domain-preparation.md)部署文档。
  
组织经常会锁定 Active Directory 域服务 (AD DS) 来帮助缓解安全风险。 但是，锁定 Active Directory 环境会限制 Skype 业务服务器所需的权限。 这可以包括从容器和 OU 中删除 ACE 以及在“用户”、“联系人”、“InetOrgPerson”或“计算机”对象上禁用权限继承。 在锁定 Active Directory 环境下权限必须手动设置容器和 Ou 需要它们。
  
## <a name="server-information"></a>服务器信息

在激活期间，Skype 业务服务器将服务器信息发布到 Active Directory 域服务中的以下三个位置：
  
- 服务连接点 (SCP) 在其安装 Skype 业务服务器的物理计算机对应的每个 Active Directory 计算机对象上。
    
- 在 **msRTCSIP-Pools** 类的容器中创建的服务器对象。
    
- 在拓扑生成器中指定受信任的服务器。
    
## <a name="service-connection-points"></a>服务连接点

Active Directory 域服务中的 Business Server 对象的每个 Skype 具有 SCP 调用 RTC 服务，后者又包含多个属性，确定每台计算机，并指定其所提供的服务。 更重要的 SCP 属性为*serviceDNSName* 、 *serviceDNSNameType* 、 *serviceClassname*和*serviceBindingInformation* 。 第三方资产管理应用程序可以通过针对上述 SCP 属性和其他 SCP 属性进行查询来检索部署中的服务器信息。
  
## <a name="active-directory-server-objects"></a>Active Directory 服务器对象

业务 Server 服务器角色的每个 Skype 了相应的 Active Directory 对象的属性定义角色所提供的服务。 此外，在激活 Standard Edition server 或创建企业版池时，Skype 业务服务器在**Msrtcsip-pools**容器中创建新的**Msrtcsip-pool**对象。 **Msrtcsip-pool**类将指定，以及池的前端和后端组件之间的关联池的完全限定的域名 (FQDN)。 （Standard Edition server 将被视为一个逻辑池，其前端和后端都并置在一台计算机。）
  
## <a name="trusted-servers"></a>受信任的服务器

Skype 业务服务器，在受信任的服务器的指定当您运行拓扑生成器并发布拓扑。 发布的拓扑（包括所有服务器信息）存储在中央管理存储中。 只有中央管理存储中定义的服务器是受信任的。 Skype 业务服务器，在受信任的服务器是指满足以下条件：
  
- 服务器的 FQDN 出现在存储在中央管理存储中的拓扑中。
    
- 服务器提供了来自受信任的 CA 的有效证书。 有关详细信息，请参阅[环境要求的业务服务器 2015 Skype](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或[业务服务器 2019年的 Skype 的系统要求](../../../SfBServer2019/plan/system-requirements.md)。
    
如果未满足上述任一条件，则该服务器将不会受到信任，并且与该服务器的连接将被拒绝。 此双重要求可防止可能存在，如果可能，攻击恶意服务器尝试接管有效服务器的 FQDN。
  
此外，若要启用 Microsoft Office Communications Server 2007 R2 和 Microsoft Office Communications Server 2007 部署与 Skype 业务 Server 服务器进行通信，业务服务器 Skype 创建容器在林准备期间用于保存的早期版本的受信任服务器列表。 下表介绍为了与早期部署兼容而创建的容器。
  
**受信任的服务器列表和其 Active Directory 容器与早期版本兼容**

|**受信任的服务器列表**|**Active Directory 容器**|
|:-----|:-----|
|Standard Edition Server 和企业版池前端服务器  <br/> |RTC 服务/全局设置  <br/> |
|会议服务器  <br/> |RTC 服务/受信任的 MCU  <br/> |
|Web 组件服务器  <br/> |RTC 服务/TrustedWebComponentsServers  <br/> |
|中介服务器和 Communicator Web Access 服务器、应用程序服务器、QoE 注册器、A/V 会议服务（也称作第三方 SIP 服务器）  <br/> |RTC 服务/受信任的服务  <br/> |
|代理服务器  <br/> |Skype 业务服务器不支持代理服务器的向后兼容性  <br/> |
   

## <a name="see-also"></a>另请参阅

[准备 Active Directory 的 Skype 业务服务器](../../deploy/install/prepare-active-directory.md)
