---
title: Skype 业务服务器中的重大安全功能
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
description: Skype 业务服务器包括几个安全功能，包括服务器到服务器身份验证、 基于角色的访问控制和集中的存储的配置数据。
ms.openlocfilehash: 5a0a82800be8158b6d54e4e01e7609d3e6b3714d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894278"
---
# <a name="key-security-features-in-skype-for-business-server"></a>Skype 业务服务器中的重大安全功能
 
Skype 业务服务器包括几个安全功能，包括服务器到服务器身份验证、 基于角色的访问控制和集中的存储的配置数据。 
  
本文提供了 Skype 业务 Server security 的高层次概述。 
  
## <a name="key-security-features-in-skype-for-business-server"></a>Skype 业务服务器中的重大安全功能

安全是一个非常广泛的主题。 安全达到跨 Skype 每个功能的业务服务器以及数据库、 服务和业务服务器生态系统的 Skype 构成的硬件。 本文列出了一些 Skype 中的功能的业务服务器尤其要指出的针对安全设计。
  
### <a name="planning-and-design-tools"></a>规划和设计工具

Skype 业务服务器提供了两个工具以加快规划和设计并减少设施 Business Server 组件配置 Skype 的机会。 
  
- **拓扑规划工具**自动执行何种拓扑设计过程。 可以将从规划工具的结果导出到拓扑生成器，是安装业务服务器运行 Skype 每台服务器所需的工具。
    
- **拓扑生成器**在中央管理存储中存储所有配置信息。
    
有关这些工具的详细信息，请参阅[Business Server 管理工具的 Skype](../../management-tools/management-tools.md)。
  
### <a name="central-management-store"></a>中央管理存储

在业务服务器 Skype，有关服务器和服务的配置数据是中央管理存储的一部分。 中央管理存储提供定义、 设置、 维护、 管理、 描述和运行 Business Server 部署 Skype 所需的数据稳固、 架构化存储。 它还会验证数据，以确保配置的一致性。 对此配置数据的所有更改都发生在中央管理存储中，消除"同步 out"问题。 
  
数据的只读副本将复制到拓扑中的所有服务器，包括边缘服务器和 Survivable Branch Appliance。复制过程由默认情况下在网络服务上下文下运行的服务进行管理，从而将权限缩减为计算机上的简单用户所拥有的权限。 
  
### <a name="server-to-server-authentication"></a>服务器到服务器身份验证

Skype 业务服务器，可以使用的 Open Authorization (OAuth) 协议的服务器之间配置身份验证。 例如，您可以配置 Skype 业务服务器正在运行 Microsoft Exchange Server 2016 服务器进行身份验证。 使用 OAuth 协议，业务 Server 和 Microsoft Exchange Server Skype 可以相互信任。 这样做可实现无缝集成产品。 有关详细信息，请参阅[管理服务器到服务器身份验证 (OAuth) 和 Skype 业务服务器中的合作伙伴应用程序](../../manage/authentication/server-to-server-and-partner-applications.md)。
  
### <a name="windows-powershell-based-management-and-web-based-management-interface"></a>基于 Windows PowerShell 的管理和基于 Web 的管理界面

Skype 业务服务器提供强大的管理界面，基于 Windows PowerShell 命令行界面。 其中包含用于管理安全性的 cmdlet，并且默认情况下会启用 Windows PowerShell 安全功能，以防止用户轻易或无意中运行脚本。 这意味着软件默认设置为自动帮助实现最大安全性并减少攻击事件。 有关 Windows PowerShell 管理支持在 Skype 业务服务器的详细信息，请参阅[Business Server Management Shell 的 Skype](../../manage/management-shell.md)。 
  
### <a name="role-based-access-control-rbac"></a>基于角色的访问控制 (RBAC)

Skype 业务服务器提供了基于角色的访问控制 (RBAC)，以使您能够保持高标准安全性的同时委派管理任务。 可以使用 RBAC 来遵守“最小特权”原则，按照该原则，用户只能获得其工作所需的管理权限。 Skype 业务服务器提供的功能，以创建新角色以及能够修改现有角色。 
  
## <a name="network-address-translation-nat"></a>网络地址转换 (NAT)

Skype 业务服务器不支持边缘服务器的内部接口上使用网络地址转换 (NAT)，但它支持发出的外部接口访问边缘服务、 Web 会议边缘服务和 A / V 边缘服务后面路由器或防火墙执行网络地址转换 (NAT) 的单个和扩展的合并边缘服务器拓扑。 硬件负载平衡器后的多台边缘服务器不能使用 NAT。 如果多台边缘服务器在其外部接口上使用 NAT，将需要域名系统 (DNS) 负载平衡。 反之，使用 DNS 负载平衡让你可以减少边缘服务器池中每台边缘服务器的公共 IP 地址的数量。 有关详细信息，请参阅[Skype 业务服务器中的边缘服务器方案](../../plan-your-deployment/edge-server-deployments/scenarios.md)。
  
> [!NOTE]
> 如果你与拥有 Microsoft Office Communications Server 2007 部署的企业联盟，且需要在你的企业与联盟企业之间使用音频/视频，则端口要求就是对已部署的边缘服务器的早期版本的端口要求。 例如，端口范围所需的那些较旧版本必须打开这两个企业，直到联盟的伙伴升级到 Skype 业务服务器的边缘服务器。 此时，可以根据新配置检查并减少端口要求。 
  
## <a name="simplified-certificates-for-edge-servers"></a>边缘服务器的简化证书

部署向导可以自动填充使用者名称 (SN) 和使用者替代名称 (SAN)，从而减少包含不必要的和可能不安全的条目的可能性。
  
## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>可信赖计算安全开发周期 (SDL)

Skype 业务服务器是设计和开发的符合[Microsoft 可信赖计算安全开发生命周期](https://go.microsoft.com/fwlink/p/?linkid=68761)(SDL)。
  
- **设计的可信赖性**创建更安全的统一的通信系统的第一步是设计威胁模型和按设计测试每个功能。 Microsoft 会对超出设计范围的行为进行测试，以便查找由于非预期产品行为引起的安全漏洞。 编码过程和做法中植入了多项与安全相关的改进。 生成时工具会在将代码签入到最终产品之前检测缓冲区溢出和其他潜在安全威胁。 当然，在设计上不可能做到能够防范所有未知安全威胁。 任何系统都无法保证绝对的安全。 但是，由于产品开发采纳从开始安全设计原则，业务服务器 Skype 包含行业标准安全技术作为基本及其体系结构的一部分。
    
- **默认的可信赖性**默认情况下，Skype 中的业务服务器的网络通信进行加密。 TLS、 安全实时传输协议 (SRTP) 和其他行业标准的加密技术，因为所有服务器都使用证书和 Kerberos 身份验证，包括 128 位高级加密标准 (AES) 加密，几乎所有的 Skype业务 Server 数据保护网络上。 此外，基于角色的访问控制使部署，以使每个服务器角色运行仅服务，并具有仅与这些服务，适用于服务器角色的权限运行 Skype 业务服务器的服务器。
    
- **部署的可信赖性**最佳实践和建议，以帮助您确定和配置您的部署的最佳安全级别，并评估安全风险的激活非默认选项，包括所有 Skype for Business Server 文档。
    

