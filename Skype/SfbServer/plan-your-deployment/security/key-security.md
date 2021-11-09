---
title: 安全与安全Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
description: Skype for Business Server包括多个安全功能，包括服务器到服务器身份验证、基于角色的访问控制以及配置数据的集中存储。
ms.openlocfilehash: c70d997dc29166b05376bbd6c1bcd7886d1c176b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60848385"
---
# <a name="key-security-features-in-skype-for-business-server"></a>安全与安全Skype for Business Server
 
Skype for Business Server包括多个安全功能，包括服务器到服务器身份验证、基于角色的访问控制以及配置数据的集中存储。 
  
本文提供有关安全Skype for Business Server概述。 
  
## <a name="key-security-features-in-skype-for-business-server"></a>Skype for Business Server

安全性是一个非常广泛的主题。 安全将跨越每个Skype for Business Server功能以及数据库、服务和硬件，这些组件是一个Skype for Business Server系统。 本文概述了本文中专为Skype for Business Server设计的功能。
  
### <a name="planning-and-design-tools"></a>规划和设计工具

Skype for Business Server提供了两种工具，以方便规划和设计并减少错误配置组件Skype for Business Server的可能性。 
  
- **拓扑规划工具** 可自动执行大部分拓扑设计过程。 您可以将规划工具中的结果导出到拓扑生成器，拓扑生成器是安装每台运行拓扑Skype for Business Server。
    
- **拓扑生成器** 将所有配置信息存储在中央管理存储中。
    
有关这些工具的详细信息，请参阅Skype for Business Server[管理工具。](../../management-tools/management-tools.md)
  
### <a name="central-management-store"></a>中央管理存储

在Skype for Business Server中，有关服务器和服务的配置数据是中央管理存储的一部分。 中央管理存储为定义、设置、维护、管理、描述和运行部署部署所需的数据提供可靠的Skype for Business Server存储。 它还会验证数据，以确保配置的一致性。 对此配置数据进行的所有更改都发生在中央管理存储中，消除了"不同步"问题。 
  
数据的只读副本将复制到拓扑中的所有服务器，包括边缘服务器。 复制过程由默认情况下使用 Network service 帐户运行的服务进行管理，从而将权限缩减为计算机上的简单用户所拥有的权限。 
  
### <a name="server-to-server-authentication"></a>服务器到服务器身份验证

在Skype for Business Server中，可以使用 Open Authorization (OAuth 协议在服务器) 身份验证。 例如，您可以将 Skype for Business Server配置为向运行 2016 Microsoft Exchange Server的服务器进行身份验证。 通过使用 OAuth 协议，Skype for Business Server和Microsoft Exchange Server相互信任。 这提供了以无缝方式集成产品的能力。 有关详细信息，请参阅管理 OAuth (中的服务器到[服务器) 和合作伙伴](../../manage/authentication/server-to-server-and-partner-applications.md)Skype for Business Server。
  
### <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Windows PowerShell基于管理和基于 Web 的管理界面

Skype for Business Server提供了一个基于命令行界面构建Windows PowerShell功能强大的管理界面。 其中包含用于管理安全性的 cmdlet，并且默认情况下会启用 Windows PowerShell 安全功能，以防止用户轻易或无意中运行脚本。 这意味着软件默认设置为自动帮助实现最大安全性并减少攻击事件。 有关在命令行Windows PowerShell管理Skype for Business Server的详细信息，请参阅Skype for Business Server[命令行管理程序。](../../manage/management-shell.md) 
  
### <a name="role-based-access-control-rbac"></a>基于角色的访问控制 (RBAC)

Skype for Business Server RBAC (基于角色的访问控制) ，使您能够在保持高安全标准的同时委派管理任务。 可以使用 RBAC 来遵守“最小特权”原则，按照该原则，用户只能获得其工作所需的管理权限。 Skype for Business Server能够创建新角色，还可以修改现有角色。 
  
## <a name="network-address-translation-nat"></a>NAT 网络地址 (转换) 

Skype for Business Server 不支持在边缘服务器的内部接口上使用网络地址转换 (NAT) ，但它支持将访问边缘服务、Web 会议边缘服务和 A/V 边缘服务的外部接口置于路由器或防火墙之后，该路由器或防火墙对单一和扩展的合并边缘服务器拓扑执行网络地址转换 (NAT) 。 硬件负载平衡器后面的多台边缘服务器无法使用 NAT。 如果多个边缘服务器在外部接口上使用 NAT，则域名系统 (DNS) 负载平衡是必需的。 反过来，使用 DNS 负载平衡可以减少边缘服务器池中每个边缘服务器的公用 IP 地址数。 有关详细信息，请参阅 Edge [Server scenarios in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/scenarios.md)。
  
> [!NOTE]
> 如果您与具有 Microsoft Office Communications Server 2007 部署的企业联盟，并且需要在企业与联盟企业之间使用音频/视频，则端口要求将为部署的较旧版本的边缘服务器的端口要求。 例如，必须为这两个企业打开这些旧版本所需的端口范围，直到联盟伙伴升级其边缘服务器以Skype for Business Server。 此时，可以根据新配置检查并减少端口要求。 
  
## <a name="simplified-certificates-for-edge-servers"></a>边缘服务器的简化证书

部署向导可以自动在 SN (中填充主题名称) 主题替代名称 (SN) ，从而减少包括不必要的和可能不安全的条目的可能性。
  
## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>SDL (可信赖计算安全) 

Skype for Business Server符合 SDL ([Microsoft 可信任计算安全](/previous-versions/ms995349(v=msdn.10))开发生命周期) 。
  
- **设计上可信赖** 创建更安全的统一通信系统的第一步是设计威胁模型并测试其设计时的每个功能。 此外，Microsoft 在设计行为之外执行测试，以查找意外产品行为造成的安全漏洞。 编码过程和做法中植入了多项与安全相关的改进。 生成时工具会在将代码签入到最终产品之前检测缓冲区溢出和其他潜在安全威胁。 当然，在设计上不可能做到能够防范所有未知安全威胁。 任何系统都无法保证绝对的安全。 但是，由于产品开发从一开始就遵循安全设计原则，Skype for Business Server将行业标准安全技术纳入其体系结构的基础部分。
    
- **默认情况下可信赖** 默认情况下，加密Skype for Business Server通信。 由于所有服务器都使用证书和 Kerberos 身份验证、TLS、安全 Real-Time 传输协议 (SRTP) 以及其他行业标准加密技术（包括 128 位高级加密标准 (AES) 加密）因此，几乎所有 Skype for Business Server 数据都受网络保护。 此外，利用基于角色的访问控制，可以部署运行 Skype for Business Server 的服务器，以便每个服务器角色仅运行这些服务，并且仅具有与适用于服务器角色的这些服务相关的权限。
    
- **部署可信赖性** 所有Skype for Business Server文档都包括最佳做法和建议，以帮助您确定和配置部署的最佳安全级别，并评估激活非默认选项的安全风险。
