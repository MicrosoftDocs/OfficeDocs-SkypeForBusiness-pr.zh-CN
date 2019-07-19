---
title: 使用 ExpressRoute 的呼叫流
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.topic: article
ms.assetid: 413acb29-ad83-4393-9402-51d88e7561ab
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: 本文旨在介绍 Skype for Business Online 和 ExpressRoute 的核心呼叫流原理，并提供详细呼叫流示例来帮助你正确理解和规划呼叫流。
ms.openlocfilehash: 59198cf24445ba486b193436b4374fea6698f146
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792627"
---
# <a name="call-flow-using-expressroute"></a>使用 ExpressRoute 的呼叫流

本文旨在介绍 Skype for Business Online 和 ExpressRoute 的核心呼叫流原理，并提供详细呼叫流示例来帮助你正确理解和规划呼叫流。

如果你要部署 Skype for business Online 作为 Office 365、Skype for business Server 混合版或 Skype for business 云连接器版的一部分, 你需要了解 Skype for Business 客户端和服务器与呼叫流之间的通信, 以便您可以有效地计划、部署、操作和解决 Skype for Business Online 服务。

## <a name="call-flow-overview"></a>呼叫流概述

本文档介绍了可以携带这些通话流的数据的网段, 并帮助你了解与通过 Internet 或 ExpressRoute 传输的流量相比, 哪些流量将在网络上保持本地。了解使用 ExpressRoute 的流量将帮助你评估贵公司使用 ExpressRoute 接收的好处, 并帮助你了解 ExpressRoute 部署指南, 以便在你确定后验证和解决你的部署使用 ExpressRoute。

本文介绍的呼叫流受你可以控制的一系列因素的影响，包括防火墙规则、NAT 配置、代理和路由器配置。本文假设你使用的是推荐设置。这些推荐设置在以下文档中进行了说明：

- [设置 Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

- [Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

- [ExpressRoute 概述](https://docs.microsoft.com/azure/expressroute/expressroute-introduction)

- [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/)

未遵循上述文档中的设置步骤的设置和配置可以有不同于我们在此处介绍的通话流。 此外, 你可能会发现你有配置问题, 如非对称网络路由或非最佳传输协议。 当涉及 ExpressRoute 时, 非对称路由是一个重要考虑因素, 因为 ExpressRoute 引入了第二条指向 Office 365 的路径, 这将创建一个方向使用 Internet 的路由, 另一个路由使用其他方向上的 ExpressRoute。 如果流量经过有状态防火墙，这可能会导致流量在返回方向被拦截。

## <a name="network-segments-and-traffic-types"></a>网络段和流量类型

### <a name="network-segments"></a>网络段

在介绍呼叫流之前，我们需要对某些术语进行定义，以帮助你了解 Skype for Business Online 中使用的网络分段和媒体类型。

下面的 "调用流程" 图表显示四个不同的网络段, 其中每个网段由不同组织 (内部网络、网络服务提供商以及他们的 Internet 对等合作伙伴和 Microsoft) 管理, 其不同性能特征。有关网络性能目标的指南, 请参阅[Skype for Business Online 中的媒体质量和网络连接性能](media-quality-and-network-connectivity-performance.md)。

以下是我们将要讨论的各个网络分段。

![Call Flow Network Segments.](../images/25689bf2-4753-4bea-b8d7-88dc8b6d2e2a.png)

 **您的网络**这是您控制和管理的整个网络的一部分的网络段。这包括您的办公室内的所有连接, 无论是有线还是无线、办公大楼、本地数据中心, 还是 Internet 提供商或 ExpressRoute 合作伙伴的连接。

通常, 你的网络边缘有一个或多个具有防火墙和/或代理服务器的 DMZ, 这将强制实施你的组织的安全策略, 并且仅允许你已设置和配置的某些网络流量。 由于你管理此网络, 你可以直接控制你的网络的性能, 因此强烈建议你完成网络评估, 以验证网络中的网站和网络之间的性能, 以验证你的网络和 Skype for business 之间的性能Online. 若要了解性能要求，请参阅 [Skype for Business Online 中的媒体质量和网络连接性能](media-quality-and-network-connectivity-performance.md)。

 **互联网**这是整个网络的一部分, 它将由从您的网络外部连接到 Skype for business Online 的用户使用, 并且在未配置 ExpressRoute 时用于所有连接。Internet 及其所有连接不由你或 Microsoft 管理, 因此无法确定性能和路由路径, 这将对整体的通话流和质量产生最大影响。

 **ExpressRoute** 该网络分段是你的整个网络的一部分，可以提供与 Microsoft 网络的专用连接。 对于将你的网络连接到 Microsoft 网络 (Office 365 数据中心) 以获取所有依赖于网络速度和性能的工作负荷 (如 Skype for Business Online 实时通信), 建议使用此选项。 在你的网络与 Microsoft 网络之间建立 ExpressRoute 连接使用[expressroute 连接提供程序](https://azure.microsoft.com/documentation/articles/expressroute-locations/)提供专用和托管的网络, 使用 99.9% 的正常运行时间和支持服务质量 (QoS), 可提高性能在网络拥挤期间进行实时媒体。

 **Microsoft 网络** 该网络分段是你的整个网络的一部分，它支持 Office 365 服务。 它包括用于 Office 365 的 Online 服务器之间的所有通信。 这可能包括流经 Microsoft 网络骨干并在地理区域之间传输的流量。

### <a name="types-of-traffic"></a>流量类型

Skype for business Online 的网络流量分为两大类别, 在呼叫流程中显示为单独的路径:

 **实时媒体**是在 RTP (实时传输协议) 内封装的数据, 支持音频、视频、应用程序共享和文件传输工作负荷。通常情况下, 媒体流量是高度延迟的, 因此你希望此流量尽可能地采用最直接路径, 并且将 UDP 用作传输层协议, 因为使用 TCP 会带来更高的延迟。

 **信号**是客户端和服务器之间的通信链接, 或用于控制活动的其他客户端 (例如, 启动呼叫时) 和发送即时消息。 大多数信令流量使用 SIP 协议，但有些客户端使用基于 HTTP 的 REST 接口。 为了简化, 我们正在考虑在此类流量中通过 HTTP 和 HTTPS 或 TLS 连接传输的各种信号。 该流量对延迟不太敏感，但如果端点之间的延迟超过数秒钟，它可能会导致服务故障或呼叫超时，了解这一点非常重要。

有关该流量的目标，请参阅适用于所有 Office 365 服务的 [Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)。 每个 URL 会指示此部分流量是否可能通过用于 Office 365 的 ExpressRoute。 对于显示启用 ExpressRoute 时, Internet 仍用于某些通信流的图表, 请参阅[适用于 Office 365 的 Azure ExpressRoute](https://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd)。 请务必了解, 即使被列为通过 ExpressRoute 路由的 Url, 也可通过 Internet 进行路由。 这意味着在某些情况下, 确定是否将使用 Internet 或 ExpressRoute 取决于代理服务器和防火墙的客户端和配置的位置。 还有一点很重要, 因为并非所有与 Office 365 关联的 Url 都能够使用 ExpressRoute, 即使您是从 ExpressRoute 合作伙伴购买 ExpressRoute, 也需要 Internet 连接。

仅可通过 Internet 发送的流量包括常见的 Internet 依赖关系, 例如证书吊销列表 (Crl)、DNS 查找和名称解析、共享 Office 365 服务的 Url, 例如 Microsoft 365 管理中心的 Url 以及一些Skype for business Online 的非实时通信功能, 例如用于与 Skype 消费者进行互操作的遥测和联盟, 以及用于 Skype 会议直播流处理的媒体。 如果需要帮助你作出决定，请参阅[使用适用于 Office 365 的 ExpressRoute 进行路由](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)，了解规划网络路由时需要考虑的其他因素。

## <a name="principles-for-call-flows-with-skype-for-business"></a>Skype for Business 通话流程的原则

深入了解特定呼叫流场景之前，有六个一般原则可帮助你了解 Skype for Business 呼叫流。

1. Skype for Business 会议托管在会议组织者所在的同一地区。 如果会议组织者为 Online 用户，则会议托管在 Office 365 云中，而如果会议组织者为本地用户，则会议托管在本地数据中心。

2. 从客户端发送到托管会议的媒体流量始终转到托管会议的服务器。这可能是你管理的数据中心内的本地服务器, 也可能是 Office 365 云中的联机服务器。但是, 边缘服务器始终用于在线会议的媒体流。

3. 点对点呼叫的媒体流量采用最直接的可用路由。首选路由是直接连接远程对等机（客户端）的路由，但如果该路由因防火墙阻止流量或类似原因而不可用，则会利用一个或多个边缘服务器对流量进行中继。

4. 信令流量总是传输到用户所在地的服务器（Online 服务器或本地服务器）。如果无法直接连接前端服务器，则会使用一个边缘服务器。

5. 用户加入在 Online 中托管的会议时，总是会使用一个边缘服务器（或者在受客户端防火墙配置限制时使用两个边缘服务器）。

6. 用户加入在本地托管的会议时，如果从包含本地部署的同一个网络的内部进行连接，则通常不使用边缘服务器，但如果从你的网络的外部进行连接，则会使用一个或两个边缘服务器。

若要了解选择的媒体路径的详细信息，请参阅 [ICE - 边缘媒体连接](https://aka.ms/AVEdge)。 尽管此视频是关于 Lync Server 2013 的, 但原则和协议仍然适用于 Skype for business。

## <a name="skype-for-business-call-flows-with-expressroute"></a>具有 ExpressRoute 的 Skype for Business 呼叫流

现在, 你已了解了四个不同网段以及 Skype for business 呼叫流程的一些一般指导原则, 你可以使用该信息来帮助你了解哪些 Skype for business 流量将遍历 ExpressRoute网络段。

如果一个端点位于你的网络内，另一个端点位于 Office 365 数据中心，则网络流量通常会通过 ExpressRoute 连接传输。这些网络流量包括客户端和服务器之间的信令流量、会议呼叫期间使用的媒体流量或使用在线边缘服务器的点对点呼叫。

如果两个端点可以跨 Internet 直接通信，或它们位于你的网络内部，则流量不会通过 ExpressRoute 连接传输。 这将包括针对点对点呼叫的媒体、来自 Internet 的流量 (目标为本地部署) 或 Internet 与 Office 365 边缘服务器之间的任何流量。 该场景的一个示例是用户从酒店加入 Online 会议。

## <a name="basic-skype-for-business-call-flow"></a>基本 Skype for Business 呼叫流程

为帮助你运用上文所述的有关 Skype for Business 呼叫流的一般原理，本文在下一节中列出了几个参考示意图。它并没有列出所有可能的呼叫流，只是为了帮助你运用上述原理。另外，示意图中所选择的场景涵盖了常见部署类型，包括 Online、Hybrid、Cloud Connector 以及 Skype 会议广播这个特殊用例。

> [!NOTE]
> Skype for Business 使用的流量子集不会通过 ExpressRoute 进行路由, 并且将始终获取 Internet 路径。请参阅[Office 365 url 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)以确定可能受影响的 url。

### <a name="peer-to-peer-call-for-office-365-users-from-within-customer-network"></a>来自客户网络内的 Office 365 用户的对等呼叫
<a name="bk_Figure2"> </a>

对于点对点呼叫，媒体流量总是采用最直接的路径传输到目标。但是，信令流量会传输到 Online 用户托管地的 Office 365 数据中心。由于两个用户位于同一个 WAN，并且客户端可以畅通无阻地直接通信，因此媒体会直接在用户之间流动。两个用户的信令流量会通过 ExpressRoute 连接传输到每个组织的数据中心。下图说明了此场景中的呼叫流。

 **点对点呼叫流**

![Call Flow with Peer to Peer call.](../images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)

### <a name="online-user-on-your-network-joining-a-conference-that-is-hosted-online"></a>网络上的联机用户加入联机托管的会议
<a name="bk_Figure3"> </a>

在对等示例中, 媒体流量始终最直接到达其目标。 但是, 对于联机会议, 目标位于 Office 365 cloud 中。 这意味着从你的网络中加入会议的所有用户的媒体流量将遍历 ExpressRoute 连接, 而信号流量将传播到 Office 365 云。 下图显示了媒体和信号将遍历你的网络中的用户的 ExpressRoute 连接, 并且将直接从你的网络外部连接到 Internet 的用户 (如来自咖啡的用户) 对 Internet 进行遍历。商店或酒店。

请记住, 会议的位置由会议组织者定义, 而不是由参与者定义。这意味着, 如果会议是由本地客户安排的, 则媒体流量不会通过 ExpressRoute 流向 Office 365 云, 而是将 Internet 转到会议组织者的本地数据中心。

Online 会议的媒体流量的传输目标是 Office 365 云内部的数据中心，但该数据中心可能与加入会议的用户位于不同的地理区域。这可能会在以下两种情况下出现：

- 如果会议组织者同与会者或参与者来自不同的公司，并且组织者所在的组织位于不同的地理位置或国家/地区。

- 如果加入会议的用户的所在地与公司组织所在的国家/地区不同，例如公司为跨国公司或加入会议的用户正在出差。

有关在此方案中使用 ExpressRoute 的好消息是使用 ExpressRoute premium 加载项时, ExpressRoute 路径后面的数据将自动传递到 Microsoft 的主干中, 而不考虑会议组织者的地理区域组织的数据中心。

 **Online 用户加入 Online 会议时的呼叫流**

![Call flow for an online hosted conference call.](../images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)

### <a name="joining-a-conference-hosted-by-on-premises-user-in-hybrid-deployment"></a>在混合部署中加入由本地用户托管的会议
<a name="bk_Figure3"> </a>

请记住, 支持托管会议的会议服务器由会议组织者托管的位置决定。在此方案中, 通过混合部署中的本地用户计划加入会议的所有用户的媒体将流向本地数据中心。在线托管用户的信号将通过其组织在 Office 365 云中建立, 而媒体将尝试直接连接。在这种情况下, 由于两个用户都是从你的网络中连接, 因此可以直接使用直接媒体连接, 因此 ExpressRoute 仅用于联机托管用户的信号流量。如果联机托管用户从 Internet 连接, 则如果使用联机边缘服务器进行连接, 媒体可以遍历 ExpressRoute。

 **Hybrid 用户托管的会议的呼叫流**

![Call flow hosted onprem.](../images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)

### <a name="on-premises-edge-server-with-office-365-hosted-conferences"></a>具有 Office 365 托管会议的本地边缘服务器
<a name="bk_Figure5"> </a>

当混合用户加入联机托管会议时, 我们知道信号和媒体将为 Office 365 云的目标, 并且由于用户是从 Internet 加入, 因此通常会采取直接的 internet 路径。但是, 在某些情况下 (例如, 由于防火墙限制), 直接的 Internet 路径不可用。在这种情况下, 本地边缘服务器可以中继媒体流量, 这将导致媒体流量在将 ExpressRoute 线路遍历到 Office 365 云之前返回到您的本地网络。

 **本地用户使用本地边缘服务器加入 Online 会议呼叫**

![Call flow for a conference call going through an edge server.](../images/0178c170-5837-430d-84f1-582784bfef55.png)

### <a name="pstn-call-using-skype-for-business-cloud-connector-edition"></a>使用 Skype for Business Cloud Connector Edition 的 PSTN 呼叫
<a name="bk_Figure6"> </a>

使用 [Skype for Business Online Cloud Connector Edition](https://aka.ms/CloudConnectorInstaller) 时，可通过将本地资源（例如 SIP Trunk、PSTN 网关）或最少硬件设备与 Skype for Business 集成来提供 PSTN 连接。 借助云连接器 Edition, 用户可以联机托管, 并且当他们不参与通话计划时, 该用户可以充当正常的联机用户。 PSTN 场景的信令会通过 ExpressRoute 连接（如可用）在客户端和云之间传输，而媒体流量会始终在 WAN 内传输。 在这种情况下，信令会在 Office 365 云处改变方向，并在 Cloud Connector 处终止。

 **通过 Office 365 和云连接器中的电话系统进行 PSTN 呼叫**

![Call flow for a PSTN call using Cloud PBX Cloud Connector.](../images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)

### <a name="skype-meeting-broadcast-with-users-joining-from-customer-network"></a>通过客户网络加入的用户的 Skype 会议直播
<a name="bk_Figure6"> </a>

Skype 会议广播是一种特殊用例，它由一个两部分会议组成，其中每部分都具有不同的网络传输特性。 第一部分 (从网络性能角度来查看最重要的部分) 是内部会议。 这是会议的实时部分, 其中包含一个或多个客户端终结点连接到 Office 365 云中的会议服务器。 使用会议的此部分传输的数据与上述示例完全一样, 使用 Office 365 用户加入和联机会议。

Skype 会议直播的独特之处是, 使用广播流服务将会议分发到大量的会议与会者。 此广播流服务不会通过 ExpressRoute 进行路由, 而是将 Internet 与可选的内容交付网络 (CDN) 服务支持配合使用。 将广播流识别为单向媒体流是很有帮助的, 因为与会者会听但不讲话并支持缓冲, 因此对网络性能问题 (如延迟、数据包丢失和抖动) 的敏感程度不太敏感。 由于可能有大量与会者收到流媒体, 因此它针对带宽利用率进行优化, 而不是为这些问题优化广播流量。

 **用户从客户网络加入时的 Skype 会议广播**

![Call flow for Skype Meeting Broadcast.](../images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)

## <a name="call-flow-patterns-by-deployment-type"></a>按部署类型的呼叫流模式

通过上述通用的调用流程示例, 并了解控制流量模式的一般原则, 下表提供了部署和使用方案的大型组合的流量模式摘要。 这些表没有列出所有可能的呼叫流组合，但可以帮助你进一步了解呼叫流的一般原理。

数据将传输并列为组织的本地;它不会留下客户网络、互联网或 ExpressRoute。 下面列出的模式基于最常见的网络设置, 如防火墙、联盟和 Internet, 并且假设参与多方或联盟流的所有组织都有 ExpressRoute。 在实践中，使用不同的设置可能会导致流量模式不同于下列流量模式。

### <a name="call-flows-for-skype-for-business-online"></a>Skype for Business Online 通话流程

Skype for Business Online 使用方案涉及处于联机状态的用户, 并且可以从内部网络或 Internet 进行呼叫。本地服务器不属于这些方案, 因此所有与会议或 PSTN 相关的媒体都将流向 Office 365 云, 并且联机用户边缘服务器也将位于云中。

 **Skype for Business Online 呼叫流汇总**

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**使用场景** <br/> |**端点** <br/> |**信令路径** <br/> |**媒体路径** <br/> |**示例流** <br/> |**说明** <br/> |
|点对点呼叫  <br/> |两个客户端，均位于你的网络中。  <br/> |ExpressRoute  <br/> |本地  <br/> |[来自客户网络内的 Office 365 用户的对等呼叫](call-flow-using-expressroute.md#bk_Figure2) <br/> ||
|点对点呼叫  <br/> |两个客户端, 一个位于你的网络 (内部), 另一个在 Internet 上的客户端 (外部)。  <br/> |内部用户：ExpressRoute  <br/> 外部用户：Internet  <br/> |内部用户：ExpressRoute  <br/> 外部用户：Internet 到 Office 365 边缘服务器。  <br/> |[来自客户网络内的 Office 365 用户的对等呼叫](call-flow-using-expressroute.md#bk_Figure2) <br/> |假定防火墙阻止客户端之间的直接连接, 这需要联机边缘服务器。从内部用户到联机边缘服务器的流量遵循与会议服务器通话的类似路径。  <br/> |
|点对点呼叫联盟组织中的用户  <br/> |两个客户端，一个位于你的网络（内部），另一个位于联盟组织网络（联盟）中的 Online 用户。  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[你的网络中的 Online 用户加入托管在 Online 的会议](call-flow-using-expressroute.md#bk_Figure3) <br/> |假设防火墙拦截了客户端之间的直接连接，这时需要使用在线边缘服务器。从内部用户到在线边缘服务器的流量采用的路径与到会议呼叫的会议服务器的流量采用的路径相似。  <br/> |
|客户网络中的用户加入会议呼叫  <br/> |客户端位于你的网络，会议服务器位于 Office 365 云中。  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[你的网络中的 Online 用户加入托管在 Online 的会议](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|通过 Internet 中的用户加入会议呼叫  <br/> |客户端位于 Office 365 cloud 中的 Internet 和会议服务器上。  <br/> |Internet  <br/> |Internet  <br/> |[你的网络中的 Online 用户加入托管在 Online 的会议](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|加入其他公司的本地服务器托管的会议  <br/> |客户端位于你的网络，会议服务器位于第三方数据中心中。  <br/> |Internet  <br/> |Internet  <br/> |不适用  <br/> |由于托管会议的会议服务器位于另一个客户的本地网络中，因此数据不会通过 Microsoft 云进行传输。  <br/> |
|PSTN 呼叫  <br/> |客户网络中的客户端和 Office 365 云中的电话系统服务器  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[你的网络中的 Online 用户加入托管在 Online 的会议](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|PSTN 呼叫  <br/> |Office 365 cloud 中的 Internet 和电话系统服务器上的客户端  <br/> |Internet  <br/> |Internet  <br/> |不适用  <br/> |媒体和信号将流向 Office 365 数据中心。由于客户端终结点位于 Internet 上, 因此所有数据都将通过 Internet 流向 Microsoft 数据中心 (即使连接需要联机边缘服务器)。  <br/> |

> [!NOTE]
> ExpressRoute 将在来自企业网络的用户的媒体路径上使用到联机边缘服务器, 但如果使用另一客户的本地部署的边缘服务器, 则不会使用它。

### <a name="call-flows-for-skype-for-business-hybrid"></a>Skype for business 混合的呼叫流程

Skype for Business 部署包含至少一部分本地托管用户时，将适用 Hybrid 呼叫流。 此部分中的调用流包括本地会议和对等呼叫以及至少有一个本地托管用户的对等呼叫。

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**使用场景** <br/> |**端点** <br/> |**信令路径** <br/> |**媒体路径** <br/> |**示例流** <br/> |**说明** <br/> |
|点对点呼叫  <br/> |两个客户端，一个位于客户网络，另一个在本地托管  <br/> |本地  <br/> |本地  <br/> |[来自客户网络内的 Office 365 用户的对等呼叫](call-flow-using-expressroute.md#bk_Figure2) <br/> |由于用户为本地托管用户，因此信令将从本地传输到本地数据中心，而不是 Office 365 云。  <br/> |
|点对点呼叫  <br/> |两个客户端，均从客户网络进行连接。一个为 Online 托管，另一个为本地托管。  <br/> |Online 用户：ExpressRoute  <br/> 本地用户：本地  <br/> |本地  <br/> |[来自客户网络内的 Office 365 用户的对等呼叫](call-flow-using-expressroute.md#bk_Figure2) <br/> |只有 Online 托管用户将信令流量发送到 Office 365 云。  <br/> |
|对联合组织中的用户的对等呼叫  <br/> |两个客户端，一个位于客户网络（内部）中的本地用户，另一个位于联盟公司的网络（联盟）中的 Online 用户。  <br/> |内部用户：本地  <br/> 联盟用户：ExpressRoute  <br/> |Internet 或 ExpressRoute（取决于使用 Online 还是本地边缘服务器）  <br/> |[您的网络上的联机用户加入一个](call-flow-using-expressroute.md#bk_Figure3)[通过 Office 365 托管会议](call-flow-using-expressroute.md#bk_Figure5)(适用于媒体流量) 托管的联机会议和本地边缘服务器的一部分。 <br/> |假定防火墙阻止客户端之间的直接连接, 需要联机边缘服务器。ICE 协商将为连接提供联机 (由联机用户) 和本地边缘服务器 (由本地用户)。  <br/> |
|客户网络中的用户加入会议呼叫（Online 用户安排的会议）  <br/> |本地用户位于你的网络，会议服务器位于 Office 365 云中。  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[你的网络中的 Online 用户加入托管在 Online 的会议](call-flow-using-expressroute.md#bk_Figure3) <br/> |会议呼叫的服务器资源由会议组织者定义。 在本例中，会议由 Online 用户安排，因此资源位于 Office 365 云中。  <br/> |
|PSTN 呼叫  <br/> |本地用户位于你的网络和本地 Skype for Business 数据中心中。  <br/> |本地  <br/> |本地  <br/> |[使用 Skype for Business Cloud Connector Edition 的 PSTN 呼叫](call-flow-using-expressroute.md#bk_Figure6) <br/> |除用户为本地托管外，与使用 Cloud Connector Edition 的场景类似，因此信令一直在你的网络中。  <br/> |

### <a name="call-flows-for-skype-for-business-with-cloud-connector"></a>Skype for business 与云连接器的通话流

连接到 Cloud Connector Edition 的用户全部为 Online 托管用户。这意味着会议将为 Online 会议，并且信令遵循与 Online 用户场景相同的模式。对于 PSTN 呼叫以外的场景，呼叫流与上述 Skype for Business Online 呼叫流完全相同。

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**使用场景** <br/> |**端点** <br/> |**信令路径** <br/> |**媒体路径** <br/> |**示例流** <br/> |**说明** <br/> |
|PSTN 呼叫  <br/> |你的网络中的 Online 用户使用 Cloud Connector Edition。  <br/> |本地  <br/> |本地  <br/> |[使用 Skype for Business Cloud Connector Edition 的 PSTN 呼叫](call-flow-using-expressroute.md#bk_Figure6) <br/> ||
|PSTN 呼叫  <br/> |Internet 中的 Online 用户使用 Cloud Connector Edition。  <br/> |Internet  <br/> |Internet  <br/> |[使用 Skype For Business Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6)[与 Office 365 托管会议](call-flow-using-expressroute.md#bk_Figure5)和 PSTN 呼叫结合使用的本地边缘服务器的组合。  <br/> |Internet 用户通过 Cloud Connector 中包含的边缘服务器进行连接，而 Cloud Connector 将连接到 PSTN 网络。  <br/> |

## <a name="related-topics"></a>相关主题

[ExpressRoute 文档](https://go.microsoft.com/fwlink/?LinkId=690285)


