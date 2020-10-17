---
title: Lync Server 2013：关键安全功能
description: Lync Server 2013：关键安全功能。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Key security features in Lync Server 2013
ms:assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342829(v=OCS.15)
ms:contentKeyID: 56107266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 689cf2ac54eacd24bb4d31b451836edcf676521b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557608"
---
# <a name="key-security-features-in-lync-server-2013"></a>Lync Server 2013 中的关键安全功能

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-07-18_

Lync Server 2013 包括几种安全功能，包括服务器到服务器身份验证、基于角色的访问控制和配置数据的集中存储。

本文提供了 Lync Server 2013 安全性的高级别概述。

<div>

## <a name="key-security-features-in-lync-server-2013"></a>Lync Server 2013 中的关键安全功能

安全性是一个非常广泛的主题。 在 Lync Server 2013 的每个功能以及组成 Lync 生态系统的数据库、服务和硬件之间，安全性会更好地到达。 本文概述了 Lync Server 2013 中的某些功能，尤其是出于安全目的而设计的。

<div>

## <a name="planning-and-design-tools"></a>规划和设计工具

Lync Server 2013 提供了两种工具，可促进规划和设计以及降低 kerberos Lync Server 组件的机率。

  - **拓扑规划工具** 自动化了大部分拓扑设计过程。 您可以将规划工具中的结果导出到拓扑生成器，这是安装运行 Lync Server 2013 的每台服务器所需的工具。

  - **拓扑生成器** 将所有配置信息存储在中央管理存储中。

有关这些工具的详细信息，请参阅 [规划 Lync Server 2013](lync-server-2013-planning.md)。

</div>

<div>

## <a name="central-management-store"></a>中央管理存储

在 Lync Server 2013 中，有关服务器和服务的配置数据是中央管理存储的一部分。 中央管理存储为定义、设置、维护、管理、描述和操作 Lync Server 部署所需的数据提供了一个强健的架构化存储。 它还会验证数据，以确保配置的一致性。 对此配置数据所做的所有更改都将发生在中央管理存储中，从而消除了 "不同步" 问题。

数据的只读副本将复制到拓扑中的所有服务器，包括边缘服务器。 复制过程由默认情况下使用 Network service 帐户运行的服务进行管理，从而将权限缩减为计算机上的简单用户所拥有的权限。

</div>

<div>

## <a name="server-to-server-authentication"></a>服务器到服务器身份验证

在 Lync Server 2013 中，可以使用开放授权 (OAuth) 协议在服务器之间配置身份验证。 例如，可以将 Lync Server 2013 配置为使用运行 Exchange Server 2013 的服务器进行身份验证。 通过使用 OAuth 协议，Lync server 和 Exchange 服务器可以相互信任。 这提供了以无缝方式集成产品的功能。 有关详细信息，请参阅 [在 Lync server 2013 中管理服务器到服务器身份验证 (OAuth) 和合作伙伴应用程序](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

</div>

<div>

## <a name="windows-powershell-based-management-and-web-based-management-interface"></a>基于 Windows PowerShell 的管理和基于 Web 的管理界面

Lync Server 2013 提供了在 Windows PowerShell 命令行接口上构建的功能强大的管理界面。 其中包含用于管理安全性的 cmdlet，并且默认情况下会启用 Windows PowerShell 安全功能，以防止用户轻易或无意中运行脚本。 这意味着软件默认设置为自动帮助实现最大安全性并减少攻击事件。 有关 Lync Server 2013 中的 Windows PowerShell 管理支持的详细信息，请参阅 [Lync server 2013 命令行管理](lync-server-2013-lync-server-management-shell.md)程序。

</div>

<div>

## <a name="role-based-access-control-rbac"></a>基于角色的访问控制 (RBAC)

Microsoft Lync Server 2013 提供了基于角色的访问控制 (RBAC) ，使您能够在保持高标准安全性的同时委派管理任务。 可以使用 RBAC 来遵守“最小特权”原则，按照该原则，用户只能获得其工作所需的管理权限。 Lync Server 2013 引入了创建新角色以及修改现有角色的功能。 有关详细信息，请参阅 [Lync Server 2013 中的规划基于角色的访问控制](lync-server-2013-planning-for-role-based-access-control.md)。

</div>

</div>

<div>

## <a name="network-address-translation-nat"></a>网络地址转换 (NAT) 

Lync Server 2013 不支持在边缘服务器的内部接口上使用网络地址转换 (NAT) ，但它支持将访问边缘服务、Web 会议边缘服务和 A/V 边缘服务的外部接口放置在为单个合并和扩展的合并边缘服务器拓扑执行网络地址转换 (NAT) 的路由器或防火墙后面。 硬件负载平衡器后面的多台边缘服务器不能使用 NAT。 如果多台边缘服务器在其外部接口上使用 NAT，则需要域名系统 (DNS) 负载平衡。 反过来，使用 DNS 负载平衡可以减少边缘服务器池中每个边缘服务器的公用 IP 地址的数量。 有关详细信息，请参阅[在 Lync Server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)。

<div>


> [!NOTE]  
> 如果与具有 Microsoft Office 通信服务器2007部署的企业联合，并且需要在企业和联合企业之间使用音频/视频，则端口要求将是部署的较旧版本的边缘服务器的要求。 例如，必须为这两个企业打开这些早期版本所需的端口范围，直到联合合作伙伴将其边缘服务器升级到 Lync Server 2013。 此时，可以根据新配置检查并减少端口要求。



</div>

</div>

<div>

## <a name="simplified-certificates-for-edge-servers"></a>简化了边缘服务器的证书

部署向导可以自动填充主题名称 (SNs) 和使用者可选名称 (SANs) ，从而降低了包含不必要的和可能不安全的条目的可能性。

</div>

<div>

## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>SDL) 的可信赖计算安全开发生命周期 (

Lync Server 2013 的设计和开发符合 Microsoft 可信赖计算安全开发生命周期 (SDL) ，如中所述 <https://go.microsoft.com/fwlink/?linkid=68761> 。

  - 可**信赖的设计**    创建更安全的统一通信系统的第一步是设计威胁模型，并在设计每个功能时对其进行测试。 此外，Microsoft 还会在设计的行为之外执行测试，以查找因意外产品行为而产生的安全漏洞。 编码过程和做法中植入了多项与安全相关的改进。 生成时工具会在将代码签入到最终产品之前检测缓冲区溢出和其他潜在安全威胁。 当然，在设计上不可能做到能够防范所有未知安全威胁。 任何系统都无法保证绝对的安全。 但是，由于产品开发采用了开始时的安全设计原则，因此 Lync Server 2013 将业界标准安全技术并入为其体系结构的基本部分。

  - **默认情况下可信**    默认情况下，Lync Server 2013 中的网络通信是加密的。 由于所有服务器都使用证书和 Kerberos 身份验证、TLS、安全 Real-Time 传输协议 (SRTP) 和其他行业标准加密技术（包括128位高级加密标准 (AES) 加密），几乎所有 Lync Server 数据在网络上都受到保护。 此外，基于角色的访问控制可以部署运行 Lync Server 2013 的服务器，以便每个服务器角色仅运行服务，并且仅拥有与这些服务相关的权限，这些服务适用于服务器角色。

  - **受部署信任**    所有 Lync Server 2013 文档都包括最佳实践和建议，可帮助您确定和配置针对部署的最佳安全级别，并评估激活非默认选项的安全风险。

</div>

</div>

<span> </span>

</div>

</div>

</div>

