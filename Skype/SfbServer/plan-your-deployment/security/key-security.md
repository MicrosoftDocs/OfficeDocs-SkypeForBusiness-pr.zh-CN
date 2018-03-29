---
title: Skype for Business Server 2015 中的关键安全功能
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/17/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
description: Skype 的业务服务器 2015年包括几种安全功能，包括服务器到服务器的身份验证、 基于角色的访问控制和配置数据的集中的存储。
ms.openlocfilehash: 629444f4490022bb9f37f5c67f72f393345ec1a9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="key-security-features-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的关键安全功能
 
Skype 的业务服务器 2015年包括几种安全功能，包括服务器到服务器的身份验证、 基于角色的访问控制和配置数据的集中的存储。 
  
本文提供了 Skype 业务服务器 2015年安全的高级别概述。 
  
## <a name="key-security-features-in-skype-for-business-server-2015"></a>在 Skype 业务服务器 2015年的主要安全功能

安全是一个非常广泛的主题。 安全到达通过 Skype 的每一项功能为业务服务器 2015年以及数据库、 服务和硬件构成的业务服务器生态系统 Skype。 本文概述了 Skype 的功能的一些的业务服务器 2015年特别适用于安全。
  
### <a name="planning-and-design-tools"></a>规划和设计工具

商业服务器 2015年的 Skype 提供两种工具，以便在规划和设计，并减少误配置 Skype 业务服务器组件。 
  
- **拓扑结构规划工具**自动执行大部分的拓扑设计过程。 可以将结果从规划工具导出到拓扑生成器，则安装运行 Skype 业务服务器 2015年每台服务器所需的工具。
    
- **拓扑生成器**在中央管理存储中存储所有配置信息。
    
有关这些工具的详细信息，请参阅[Skype 业务服务器 2015年管理工具](../../management-tools/management-tools.md)和[规划您的业务服务器 2015年部署 Skype](../../plan-your-deployment/plan-your-deployment.md)。
  
### <a name="central-management-store"></a>中央管理存储

业务服务器 2015年的 Skype，在配置服务器和服务有关的数据是属于中央管理存储。 中央管理存储提供了可靠、 架构化的定义、 建立、 维护、 管理、 描述和操作业务服务器部署 Skype 所需的数据存储。 它还会验证数据，以确保配置的一致性。 在中央管理存储，消除"不同步"问题发生与此配置数据的所有更改。 
  
数据的只读副本将复制到拓扑中的所有服务器，包括边缘服务器和 Survivable Branch Appliance。复制过程由默认情况下在网络服务上下文下运行的服务进行管理，从而将权限缩减为计算机上的简单用户所拥有的权限。 
  
### <a name="server-to-server-authentication"></a>服务器到服务器身份验证

在业务服务器 2015年的 Skype，可以通过打开授权 (OAuth) 协议的服务器之间配置身份验证。 例如，可以配置运行 Microsoft Exchange Server 2016年服务器进行身份验证的业务服务器 2015年的 Skype。 使用 OAuth 协议，Skype 业务服务器和 Microsoft Exchange Server 可以信任彼此。 这样做可实现无缝集成产品。 有关详细信息，请参阅[管理服务器的身份验证 (OAuth) 和业务服务器 2015年的 Skype 的合作伙伴应用程序](../../manage/authentication/server-to-server-and-partner-applications.md)。
  
### <a name="windows-powershell-based-management-and-web-based-management-interface"></a>基于 Windows PowerShell 的管理和基于 Web 的管理界面

业务服务器 2015年的 Skype 提供了功能强大的管理界面，基于 Windows PowerShell 命令行界面。 其中包含用于管理安全性的 cmdlet，并且默认情况下会启用 Windows PowerShell 安全功能，以防止用户轻易或无意中运行脚本。 这意味着软件默认设置为自动帮助实现最大安全性并减少攻击事件。 在 Skype 业务服务器 2015年的 Windows PowerShell 管理支持的详细信息，请参阅[业务服务器 2015年管理外壳的 Skype](../../manage/management-shell.md)。 
  
### <a name="role-based-access-control-rbac"></a>基于角色的访问控制 (RBAC)

商业服务器 2015年的 Skype 提供基于角色的访问控制 (RBAC)，使您能够同时保持高标准的安全委派管理任务。 可以使用 RBAC 来遵守“最小特权”原则，按照该原则，用户只能获得其工作所需的管理权限。 创建新的角色的能力以及修改现有角色的能力提供了业务服务器 2015年的 Skype。 
  
## <a name="network-address-translation-nat"></a>网络地址转换 (NAT)

Skype 业务服务器 2015年的边缘服务器的内部接口上不支持的网络地址转换 (NAT) 使用，但它支持访问边缘服务、 Web 会议边缘服务和一个外部接口放 / V 边缘路由器或防火墙执行网络地址转换 (NAT) 单和缩放后的服务合并边缘服务器拓扑。 硬件负载平衡器后的多台边缘服务器不能使用 NAT。 如果多台边缘服务器在其外部接口上使用 NAT，将需要域名系统 (DNS) 负载平衡。 反之，使用 DNS 负载平衡让你可以减少边缘服务器池中每台边缘服务器的公共 IP 地址的数量。 有关详细信息，请参阅[在业务服务器 2015年的 Skype 的边缘服务器方案](../../plan-your-deployment/edge-server-deployments/scenarios.md)。
  
> [!NOTE]
> 如果你与拥有 Microsoft Office Communications Server 2007 部署的企业联盟，且需要在你的企业与联盟企业之间使用音频/视频，则端口要求就是对已部署的边缘服务器的早期版本的端口要求。 例如，端口范围所需的那些旧联盟的伙伴会将其边缘服务器升级到 Skype 的业务服务器 2015年之前版本必须打开这两个企业。 此时，可以根据新配置检查并减少端口要求。 
  
## <a name="simplified-certificates-for-edge-servers"></a>边缘服务器的简化证书

部署向导可以自动填充使用者名称 (SN) 和使用者替代名称 (SAN)，从而减少包含不必要的和可能不安全的条目的可能性。
  
## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>可信赖计算安全开发周期 (SDL)

Skype 业务服务器 2015年的设计和开发符合[Microsoft 可信赖计算安全开发生命周期](https://go.microsoft.com/fwlink/p/?linkid=68761)(SDL)。
  
- **可靠的设计**创建更安全的统一的通信系统中的第一步是设计的威胁模型和测试每个功能按设计。 Microsoft 会对超出设计范围的行为进行测试，以便查找由于非预期产品行为引起的安全漏洞。 编码过程和做法中植入了多项与安全相关的改进。 生成时工具会在将代码签入到最终产品之前检测缓冲区溢出和其他潜在安全威胁。 当然，在设计上不可能做到能够防范所有未知安全威胁。 任何系统都无法保证绝对的安全。 但是，因为产品开发采纳安全设计原则，从一开始，Skype 的业务服务器 2015年采用行业标准安全技术作为其体系结构的基本组成部分。
    
- **默认情况下可信赖**默认情况下，业务服务器 2015年在 Skype 的网络通信进行加密。 所有服务器都使用证书和 Kerberos 身份验证，因为 TLS、 安全实时传输协议 (SRTP) 和其他业界标准的加密技术，包括 128 位高级加密标准 (AES) 加密，几乎所有的 Skype在网络上保护业务服务器数据。 此外，基于角色的访问控制就可以部署服务器，以便每个服务器角色运行仅服务，并已与这些服务，适用于服务器角色相关的权限运行 Skype 业务服务器 2015年。
    
- **可靠的部署**所有 Skype 业务服务器 2015年文档都包括最佳做法和建议，以帮助您确定并配置您的部署的最佳安全级别和评估激活非默认选项的安全风险。
    

