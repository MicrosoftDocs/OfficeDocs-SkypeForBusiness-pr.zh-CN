---
title: 适用于 Skype for business 服务器的 Active Directory 域服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
description: Active Directory 域服务充当 Windows Server 2003、Windows Server 2008、Windows Server 2012 和 Windows Server 2012 R2 网络的目录服务。 Active Directory 域服务还充当建立 Skype for business 服务器安全基础结构的基础。 本部分的目的是介绍 Skype for business 服务器如何使用 Active Directory 域服务为 IM、Web 会议、媒体和语音创建可信环境。 有关为 Active Directory 域服务准备环境的详细信息，请参阅在部署文档中安装 Skype for Business 服务器。 有关 Windows Server 网络中 Active Directory 域服务的角色的详细信息，请参阅你正在使用的操作系统版本的文档。
ms.openlocfilehash: ec3a09e2203b6f862d87403818b43ab6daae33ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815710"
---
# <a name="active-directory-domain-services-for-skype-for-business-server"></a>适用于 Skype for business 服务器的 Active Directory 域服务
 
Active Directory 域服务充当 Windows Server 2003、Windows Server 2008、Windows Server 2012 和 Windows Server 2012 R2 网络的目录服务。 Active Directory 域服务还充当建立 Skype for business 服务器安全基础结构的基础。 本部分的目的是介绍 Skype for business 服务器如何使用 Active Directory 域服务为 IM、Web 会议、媒体和语音创建可信环境。 有关为 Active Directory 域服务准备环境的详细信息，请参阅在部署文档中[安装 Skype For Business 服务器](../../deploy/install/install.md)。 有关 Windows Server 网络中 Active Directory 域服务的角色的详细信息，请参阅你正在使用的操作系统版本的文档。
  
Skype for business 服务器使用 Active Directory 域服务存储：
  
- 在目录林中运行 Skype for Business 服务器的所有服务器都需要的全局设置。
    
- 标识林中运行 Skype for Business 服务器的所有服务器的角色的服务信息。
    
- 一些用户设置。
    
## <a name="active-directory-infrastructure"></a>Active Directory 基础结构

Active Directory 的基础结构要求包括以下内容：
  
- 域控制器的操作系统要求
    
- 域和林的功能级别要求
    
- 全局编录域要求
    
有关详细信息，请参阅 skype for business server [2015 的环境要求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或[Skype for business Server 2019 的服务器要求](../../../SfBServer2019/plan/system-requirements.md)。
  
## <a name="universal-groups"></a>通用组

在准备林期间，Skype for Business 服务器将在具有访问和管理全局设置和服务权限的 Active Directory 域服务中创建各种通用组。 这些通用组包括：
  
- **管理组**。 这些组定义 Skype for business 服务器网络的基本管理员角色。 在林准备期间，这些管理员组将添加到 Skype for business 服务器基础结构组。
    
- **服务组**。 这些组是访问 Skype for Business Server 提供的各种服务所需的服务帐户。
    
- **基础结构组**。 这些组提供访问 Skype for Business 服务器基础结构的特定区域的权限。 这些基础结构组将用作管理组的组件，不应修改这些基础结构组或直接向其中添加用户。 在林的准备过程中，会将特定的服务组和管理组添加到适当的基础结构组。
    
有关在为 Skype for Business 服务器准备广告时创建的特定通用组以及添加到基础结构组的服务和管理组的详细信息，请参阅部署文档中[Skype For Business 服务器的林准备所做的更改](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)。
  
> [!NOTE]
> Skype for Business 服务器支持 Windows Server 2012 中的通用组以及适用于域控制器的 Windows Server 2003 操作系统。 通用组的成员可包括域树或林中的任何域中的其他组和帐户，并且可将域树或林中的任何域中的权限分配给这些成员。 通用组支持与管理员委派结合使用，简化了 Skype for business 服务器部署的管理。 例如，不必将一个域添加到另一个域，管理员即可同时管理这两个域。 
  
## <a name="role-based-access-control"></a>基于角色的访问控制

除创建通用服务组和管理组以及将服务组和管理组添加到适当的通用组之外，林准备还创建基于角色的访问控制 (RBAC) 组。 有关林准备所创建的特定 RBAC 组的详细信息，请参阅部署文档中的[Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)。 有关 RBAC 组的详细信息，请参阅[Skype for Business 服务器的基于角色的访问控制（RBAC）](role-based-access-control-rbac.md)。
  
## <a name="access-control-entries-aces-and-inheritance"></a>访问控制项 (ACE) 与继承

林准备同时创建专用和公共 ACE，并为其创建的通用组添加 ACE。 它在由 Skype for Business 服务器使用的全局设置容器上创建特定的专用 Ace。 此容器仅由 Skype for Business 服务器使用，并且位于配置容器或根域的系统容器中，具体取决于全局设置的存储位置。
  
域准备步骤将向通用组添加必要的访问控制项 (ACE)，这些访问控制项将授予承载和管理域中用户的权限。域准备过程将在域根和以下三个内置容器中创建 ACE：“用户”、“计算机”和“域控制器”。
  
有关由林准备和域准备创建和添加的公共 Ace 的详细信息，请参阅[skype for Business 服务器中的林准备](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)所做的更改和部署文档中[Skype for business 服务器的域准备](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-domain-preparation.md)所做的更改。
  
组织通常会锁定 Active Directory 域服务（AD DS）以帮助降低安全风险。 但是，锁定的活动目录环境可以限制 Skype for Business 服务器需要的权限。 这可以包括从容器和 OU 中删除 ACE 以及在“用户”、“联系人”、“InetOrgPerson”或“计算机”对象上禁用权限继承。 在锁定的活动目录环境中，必须在需要它们的容器和 Ou 上手动设置权限。
  
## <a name="server-information"></a>服务器信息

在激活期间，Skype for business 服务器将服务器信息发布到 Active Directory 域服务中的三个以下位置：
  
- 每个 Active Directory 计算机对象上的服务连接点（SCP），对应于安装了 Skype for business 服务器的物理计算机。
    
- 在 **msRTCSIP-Pools** 类的容器中创建的服务器对象。
    
- 拓扑生成器中指定的受信任服务器。
    
## <a name="service-connection-points"></a>服务连接点

Active Directory 域服务中的每个 Skype for Business 服务器对象都具有一个名为 RTC 服务的 SCP，后者又包含许多属性，这些属性标识每台计算机并指定它所提供的服务。 在更重要的 SCP 属性中， *serviceDNSName* 、 *serviceDNSNameType* 、 *serviceClassname*和*serviceBindingInformation* 。 第三方资产管理应用程序可以通过针对上述 SCP 属性和其他 SCP 属性进行查询来检索部署中的服务器信息。
  
## <a name="active-directory-server-objects"></a>Active Directory 服务器对象

每个 Skype for Business 服务器角色都具有相应的 Active Directory 对象，该对象的属性定义了该角色提供的服务。 此外，在激活标准版服务器或创建企业版池时，Skype for Business 服务器将在**msRTCSIP**容器中创建一个新的**msRTCSIP**对象。 **MsRTCSIP**类指定池的完全限定的域名（FQDN），以及池的前端和后端组件之间的关联。 （标准版服务器被视为一种逻辑池，其前端和后端在一台计算机上 collocated。）
  
## <a name="trusted-servers"></a>受信任的服务器

在 Skype for Business 服务器中，受信任的服务器是运行拓扑生成器和发布拓扑时指定的服务器。 发布的拓扑（包括所有服务器信息）存储在中央管理存储中。 只有中央管理存储中定义的服务器是受信任的。 在 Skype for Business 服务器中，受信任的服务器是符合以下条件的服务器：
  
- 服务器的 FQDN 出现在存储在中央管理存储中的拓扑中。
    
- 服务器提供了来自受信任的 CA 的有效证书。 有关详细信息，请参阅 skype for business [server 2015 的环境要求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或[Skype for business Server 2019 的系统要求](../../../SfBServer2019/plan/system-requirements.md)。
    
如果未满足上述任一条件，则该服务器将不会受到信任，并且与该服务器的连接将被拒绝。 如果不太可能，这种双重要求可以防止恶意服务器尝试接管有效服务器的 FQDN 的攻击。
  
此外，若要使 Microsoft Office 通信服务器 2007 R2 和 Microsoft Office 通信服务器2007部署与 Skype for business 服务器服务器进行通信，Skype for business 服务器在林准备期间创建容器用于保存以前版本的受信任服务器列表。 下表介绍为了与早期部署兼容而创建的容器。
  
**受信任服务器列表及其 Active Directory 容器与以前版本的兼容性**

|**受信任的服务器列表**|**Active Directory 容器**|
|:-----|:-----|
|Standard Edition Server 和企业版池前端服务器  <br/> |RTC 服务/全局设置  <br/> |
|会议服务器  <br/> |RTC 服务/受信任的 MCU  <br/> |
|Web 组件服务器  <br/> |RTC 服务/TrustedWebComponentsServers  <br/> |
|中介服务器和 Communicator Web Access 服务器、应用程序服务器、QoE 注册器、A/V 会议服务（也称作第三方 SIP 服务器）  <br/> |RTC 服务/受信任的服务  <br/> |
|代理服务器  <br/> |Skype for Business 服务器不支持代理服务器的向后兼容性  <br/> |
   

## <a name="see-also"></a>另请参阅

[为 Skype for business 服务器准备 Active Directory](../../deploy/install/prepare-active-directory.md)
