---
title: Lync Server 2013 中的关键安全功能
TOCTitle: Lync Server 2013 中的关键安全功能
ms:assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn342829(v=OCS.15)
ms:contentKeyID: 56271201
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的关键安全功能

 

_**上一次修改主题：** 2016-12-08_

Lync Server 2013 包含许多安全功能，包括服务器到服务器身份验证、基于角色的访问控制和配置数据的集中存储。

本文将高度概括性地介绍 Lync Server 2013 安全。

## Lync Server 2013 中的关键安全功能

安全是一个非常广泛的主题。安全遍及 Lync Server 2013 的每一项功能以及构成 Lync 生态系统的数据库、服务和硬件。本文特别概括介绍了 Lync Server 2013 中专门针对安全性而设计的一些功能。

## 规划和设计工具

Lync Server 2013 提供了两种工具来促进规划和设计并减少错误配置 Lync Server 组件的几率。

  - **拓扑规划工具**自动化大量拓扑设计过程。您可以将结果从规划工具导出到拓扑生成器中，拓扑生成器是安装运行 Lync Server 2013 的每个服务器时所必需的工具。

  - **拓扑生成器**将所有配置信息存储在中央管理存储中。

有关这些工具的详细信息，请参阅 [规划 Lync Server 2013](lync-server-2013-planning.md)。

## 中央管理存储

在 Lync Server 2013 中，有关服务器和服务的配置数据是中央管理存储的一部分。中央管理存储为定义、设置、维护、管理、描述和运行 Lync Server 部署所需的数据提供了可靠的图式化存储。它还对数据进行验证，以确保配置的一致性。对此配置数据的所有更改都在中央管理存储进行，这样可以消除“不同步”问题。

数据的只读副本将复制到拓扑中的所有服务器，包括边缘服务器和 Survivable Branch Appliance。复制过程由默认情况下使用 Network service 帐户运行的服务进行管理，从而将权限缩减为计算机上的简单用户所拥有的权限。

## 服务器到服务器身份验证.

在 Lync Server 2013 中，可以使用 Open Authorization (OAuth) 协议在服务器之间配置身份验证。例如，您可以配置 Lync Server 2013 以向运行 Exchange Server 2013 的服务器进行身份验证。使用 OAuth 协议，Lync 服务器和 Exchange 服务器可以相互信任。这提供以无缝方式集成产品的能力。有关详细信息，请参阅[在 Lync Server 2013 中管理服务器到服务器身份验证 (Oauth) 和合作伙伴应用程序](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

## 基于 Windows PowerShell 的管理和基于 Web 的管理界面

Lync Server 2013 提供一种基于 Windows PowerShell 命令行界面构建的强大管理界面。其中包含用于管理安全性的 cmdlet，并且默认情况下会启用 Windows PowerShell 安全功能，以防止用户轻易或无意中运行脚本。这意味着软件默认设置为自动帮助实现最大安全性并减少攻击事件。有关 Lync Server 2013 中的 Windows PowerShell 管理支持的详细信息，请参阅 [Lync Server 命令行管理程序](lync-server-2013-lync-server-management-shell.md)。

## 基于角色的访问控制 (RBAC)

Microsoft Lync Server 2013 提供基于角色的访问控制 (RBAC)，使您能够在保持高标准安全性的同时委派管理任务。可以使用 RBAC 来遵守“最小特权”原则，按照该原则，用户只能获得其工作所需的管理权限。Lync Server 2013 引入了创建新角色和修改现有角色的功能。有关详细信息，请参阅[在 Lync Server 2013 中规划基于角色的访问控制](lync-server-2013-planning-for-role-based-access-control.md)。

## 网络地址转换 (NAT)

Lync Server 2013 不支持在边缘服务器的内部接口上使用网络地址转换 (NAT)，但支持将访问边缘服务、Web 会议边缘服务和 A/V 边缘服务的外部接口置于路由器或防火墙之后，该路由器或防火墙对单一合并和扩展的合并边缘服务器拓扑执行网络地址转换 (NAT)。硬件负载平衡器后面的多台边缘服务器不能使用 NAT。如果多台边缘服务器在其外部接口上使用 NAT，将需要域名系统 (DNS) 负载平衡。反之，使用 DNS 负载平衡让您可以减少边缘服务器池中每台边缘服务器的公共 IP 地址的数量。有关详细信息，请参阅[在 Lync Server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)。

> [!NOTE]  
> 如果与具有 Microsoft Office Communications Server 2007 部署的企业建立联盟并且需要在您的企业和联盟企业之间使用音频/视频，则端口要求将采用部署的早期版本的边缘服务器上的那些要求。例如，早期版本所需的端口范围必须为两个企业打开，直到联盟伙伴将其边缘服务器升级到 Lync Server 2013。此时，可以根据新配置检查并减少端口要求。



## 边缘服务器的简化证书

部署向导可以自动填充使用者名称 (SN) 和使用者替代名称 (SAN)，从而减少包含不必要的和可能不安全的条目的可能性。

## 可信赖计算安全开发生命周期 (SDL)

Lync Server 2013 是依照 Microsoft 可信赖计算安全开发周期 (SDL) 设计和开发的，如以下网站中所述：<http://go.microsoft.com/fwlink/?linkid=68761>。

  - **设计方面的可信赖性**   创建更安全的统一通信系统的第一步是设计威胁模型，并按每项功能的设计要求对其进行测试。此外，Microsoft 超出设计行为执行测试，以查找因预期产品行为引起的安全漏洞。编码过程和做法中植入了多项与安全相关的改进。生成时工具会在将代码签入到最终产品之前检测缓冲区溢出和其他潜在安全威胁。当然，在设计上不可能做到能够防范所有未知安全威胁。任何系统都无法保证绝对的安全。不过，由于产品开发从一开始就遵循安全设计原则，因此 Lync Server 2013 采用了行业标准安全技术作为其架构的基础部分。

  - **默认的可信赖性**   默认情况下，Lync Server 2013 中的网络通信经过加密。 由于所有服务器都使用证书和 Kerberos 身份验证、TLS、安全实时传输协议 (SRTP) 以及其他行业标准加密技术（包括 128 位高级加密标准 (AES) 加密），几乎可以保护网络上的所有 Lync Server 数据。此外，基于角色的访问控制还可以部署运行 Lync Server 2013 的服务器，以便每个服务器角色只运行适当的服务，且只拥有与适于该服务器角色的那些服务相关的权限。

  - **部署方面的可信赖性**   所有 Lync Server 2013 文档都包括最佳做法和建议，可帮助您确定和配置您的部署的最佳安全级别并评估激活非默认选项的安全风险。

