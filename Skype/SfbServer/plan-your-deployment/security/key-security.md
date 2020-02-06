---
title: Skype for Business 服务器中的主要安全功能
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
ms.assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
description: Skype for Business 服务器包括多项安全功能，包括服务器到服务器身份验证、基于角色的访问控制和配置数据的集中存储。
ms.openlocfilehash: ac1891194d231c4d494ba4014e4abd8bd7f1185b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815650"
---
# <a name="key-security-features-in-skype-for-business-server"></a>Skype for Business 服务器中的主要安全功能
 
Skype for Business 服务器包括多项安全功能，包括服务器到服务器身份验证、基于角色的访问控制和配置数据的集中存储。 
  
本文提供 Skype for business 服务器安全的高级概述。 
  
## <a name="key-security-features-in-skype-for-business-server"></a>Skype for Business 服务器中的主要安全功能

安全是一个非常广泛的主题。 安全性达到 Skype for business 服务器的每个功能，以及组成 Skype for business Server 生态系统的数据库、服务和硬件。 本文概述了 Skype for Business 服务器中的某些功能，尤其是针对安全设计的。
  
### <a name="planning-and-design-tools"></a>规划和设计工具

Skype for Business 服务器提供了两种工具来促进规划和设计，并减少错误配置 Skype for Business 服务器组件的几率。 
  
- **拓扑规划工具**会自动执行大部分拓扑设计过程。 你可以将计划工具中的结果导出到拓扑生成器，这是安装运行 Skype for Business Server 的每台服务器所需的工具。
    
- **拓扑生成器**在中央管理存储中存储所有配置信息。
    
有关这些工具的详细信息，请参阅[Skype for Business 服务器管理工具](../../management-tools/management-tools.md)。
  
### <a name="central-management-store"></a>中央管理存储

在 Skype for Business 服务器中，有关服务器和服务的配置数据是中央管理存储的一部分。 中央管理存储为定义、设置、维护、管理、描述和操作 Skype for Business 服务器部署所需的数据提供可靠的 schematized 存储。 它还会验证数据，以确保配置的一致性。 对此配置数据所做的所有更改都将在中央管理存储中发生，从而消除了 "不同步" 问题。 
  
数据的只读副本将复制到拓扑中的所有服务器，包括边缘服务器和 Survivable Branch Appliance。复制过程由默认情况下在网络服务上下文下运行的服务进行管理，从而将权限缩减为计算机上的简单用户所拥有的权限。 
  
### <a name="server-to-server-authentication"></a>服务器到服务器身份验证

在 Skype for Business 服务器中，可以使用开放授权（OAuth）协议在服务器之间配置身份验证。 例如，您可以将 Skype for business 服务器配置为与运行 Microsoft Exchange Server 2016 的服务器进行身份验证。 通过使用 OAuth 协议，Skype for business 服务器和 Microsoft Exchange Server 可以相互信任。 这样做可实现无缝集成产品。 有关详细信息，请参阅[在 Skype For Business 服务器中管理服务器到服务器身份验证（OAuth）和合作伙伴应用程序](../../manage/authentication/server-to-server-and-partner-applications.md)。
  
### <a name="windows-powershell-based-management-and-web-based-management-interface"></a>基于 Windows PowerShell 的管理和基于 Web 的管理界面

Skype for business 服务器提供了一个功能强大的管理界面，该界面是基于 Windows PowerShell 命令行界面构建的。 其中包含用于管理安全性的 cmdlet，并且默认情况下会启用 Windows PowerShell 安全功能，以防止用户轻易或无意中运行脚本。 这意味着软件默认设置为自动帮助实现最大安全性并减少攻击事件。 有关 Skype for Business Server 中的 Windows PowerShell 管理支持的详细信息，请参阅 Skype for business [Server 命令行管理程序](../../manage/management-shell.md)。 
  
### <a name="role-based-access-control-rbac"></a>基于角色的访问控制 (RBAC)

Skype for Business 服务器提供基于角色的访问控制（RBAC），使你能够委派管理任务，同时保持高标准的安全。 可以使用 RBAC 来遵守“最小特权”原则，按照该原则，用户只能获得其工作所需的管理权限。 Skype for business 服务器提供了创建新角色的功能，还提供了修改现有角色的功能。 
  
## <a name="network-address-translation-nat"></a>网络地址转换 (NAT)

Skype for Business 服务器不支持在边缘服务器的内部接口上使用网络地址转换（NAT），但它支持将访问边缘服务的外部接口、Web 会议边缘服务和 A/V 边缘服务置于为单个和缩放的合并边缘服务器拓扑执行网络地址转换（NAT）的路由器或防火墙后面。 硬件负载平衡器后的多台边缘服务器不能使用 NAT。 如果多台边缘服务器在其外部接口上使用 NAT，将需要域名系统 (DNS) 负载平衡。 反之，使用 DNS 负载平衡让你可以减少边缘服务器池中每台边缘服务器的公共 IP 地址的数量。 有关详细信息，请参阅[Skype For Business 服务器中的边缘服务器方案](../../plan-your-deployment/edge-server-deployments/scenarios.md)。
  
> [!NOTE]
> 如果你与拥有 Microsoft Office Communications Server 2007 部署的企业联盟，且需要在你的企业与联盟企业之间使用音频/视频，则端口要求就是对已部署的边缘服务器的早期版本的端口要求。 例如，必须为两个企业打开这些旧版本所需的端口范围，直到联盟伙伴将其边缘服务器升级到 Skype for business 服务器。 此时，可以根据新配置检查并减少端口要求。 
  
## <a name="simplified-certificates-for-edge-servers"></a>边缘服务器的简化证书

部署向导可以自动填充使用者名称 (SN) 和使用者替代名称 (SAN)，从而减少包含不必要的和可能不安全的条目的可能性。
  
## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>可信赖计算安全开发周期 (SDL)

Skype for business 服务器的设计和开发符合[Microsoft 高可信计算安全开发生命周期](https://go.microsoft.com/fwlink/p/?linkid=68761)（SDL）。
  
- **由设计信任**创建更安全的统一通信系统的第一步是设计威胁模型并测试每个功能的设计方式。 Microsoft 会对超出设计范围的行为进行测试，以便查找由于非预期产品行为引起的安全漏洞。 编码过程和做法中植入了多项与安全相关的改进。 生成时工具会在将代码签入到最终产品之前检测缓冲区溢出和其他潜在安全威胁。 当然，在设计上不可能做到能够防范所有未知安全威胁。 任何系统都无法保证绝对的安全。 但是，由于产品开发采纳了来自开始的安全设计原则，因此 Skype for business 服务器将业界标准安全技术合并为其体系结构的基础部分。
    
- **默认为可信**默认情况下，Skype for Business 服务器中的网络通信已加密。 由于所有服务器使用证书和 Kerberos 身份验证、TLS、安全实时传输协议（SRTP）和其他业界标准的加密技术（包括128位高级加密标准（AES）加密），因此几乎所有 Skype 都适用于业务服务器数据在网络上受到保护。 此外，基于角色的访问控制使你可以部署运行 Skype for Business Server 的服务器，以便每个服务器角色仅运行服务，并且仅具有与这些服务相关的权限，这些服务适用于服务器角色。
    
- **受部署信任**所有 Skype for Business 服务器文档均包含最佳做法和建议，可帮助你确定和配置你的部署的最佳安全级别，并评估激活非默认选项的安全风险。
    

