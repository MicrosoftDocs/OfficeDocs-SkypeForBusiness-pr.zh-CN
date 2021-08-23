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
f1.keywords:
- NOCSH
ms.custom:
- Optimization
description: 本文旨在介绍 Skype for Business Online 和 ExpressRoute 的核心呼叫流原理，并提供详细呼叫流示例来帮助你正确理解和规划呼叫流。
ms.openlocfilehash: 35936e1e33f2914345aa5443ca745dc2c5260ad7
ms.sourcegitcommit: 9fcd9a7ae78e04cef90415c2a0f30a98fbf8270f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2021
ms.locfileid: "58407201"
---
# <a name="call-flow-using-expressroute"></a>使用 ExpressRoute 的呼叫流

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

本文旨在介绍 Skype for Business Online 和 ExpressRoute 的核心呼叫流原理，并提供详细呼叫流示例来帮助你正确理解和规划呼叫流。

如果要将 Skype for Business Online 部署为 Microsoft 365、Office 365、Skype for Business Server 混合或 Skype for Business 云连接器版本 的一部分，则需要了解 Skype for Business 客户端与服务器之间的通信以及呼叫流，以便有效地规划、部署、操作和排查 Skype for Business Online 服务问题。

## <a name="call-flow-overview"></a>呼叫流概述

本文档介绍可以承载这些呼叫流的数据的网段，并帮助你了解与通过 Internet 或 ExpressRoute 传输的流量相比，哪些流量将保留在网络本地。 了解哪种流量使用 ExpressRoute 可帮助你评估公司使用 ExpressRoute 得到的益处，还可帮助你了解 ExpressRoute 部署指南，以便在决定使用 ExpressRoute 后，对部署进行验证和故障排除。

本文介绍的呼叫流受你可以控制的一系列因素的影响，包括防火墙规则、NAT 配置、代理和路由器配置。本文假设你使用的是推荐设置。这些推荐设置在以下文档中进行了说明：

- [设置 Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

- [Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

- [ExpressRoute 概述](/azure/expressroute/expressroute-introduction)

- [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/)

未遵循上述文档中的设置步骤的设置和配置可能具有不同的调用流，而此处介绍的调用流可能不同。 此外，你可能会发现自己存在非对称和非最佳网络路由或非最佳传输协议等配置问题。 每当涉及到 ExpressRoute 时，非对称路由都是一个重要的考虑因素，因为 ExpressRoute 会引入到 Office 365 的第二个路径，因此，在一个方向使用 Internet 的路由，以及在另一个方向使用 ExpressRoute 的另一个路由。 如果流量遍历有状态防火墙，则可能会导致流量在返回方向被阻止。

## <a name="network-segments-and-traffic-types"></a>网段和流量类型

### <a name="network-segments"></a>网段

在解释呼叫流之前，我们需要定义一些术语，以帮助你了解在 Skype for Business Online 中使用的网络分段和Skype for Business类型。

下面的呼叫流图显示了四个不同的网段，每个网段由不同的组织管理 (包括内部网络、网络服务提供商及其 Internet 对等合作伙伴以及具有不同的性能特征的 Microsoft) 。 有关网络性能目标的准则，请参阅 Skype for Business Online 中的媒体质量和[网络连接性能](media-quality-and-network-connectivity-performance.md)。

下面可以看到我们将讨论的每个网段。

![调用Flow段。](../images/25689bf2-4753-4bea-b8d7-88dc8b6d2e2a.png)

 **你的网络** 这是网络段，它是你控制和管理的总体网络的一部分。 这包括办公室内的所有连接（无论是有线连接还是无线连接、办公大楼之间、到本地数据中心的连接）以及与 Internet 提供商或 ExpressRoute 合作伙伴的连接。

通常，网络边缘具有一个或多个带防火墙和/或代理服务器的外围网络，这些外围网络强制实施组织的安全策略，并且仅允许已设置和配置的某些网络流量。 由于您管理此网络，因此您可以直接控制网络的性能，强烈建议完成网络评估，以验证网络站点内部的性能以及从网络到 Skype for Business Online 的性能。 若要了解性能要求，请参阅 Skype for Business Online 中的媒体[质量和网络连接性能](media-quality-and-network-connectivity-performance.md)。

 **Internet** 这是整个网络的一部分网络段，供从网络外部连接到 Skype for Business Online 的用户使用，在未配置 ExpressRoute 时用于所有连接。 Internet 及其所有连接不由你或 Microsoft 管理，因此无法确定性能和路由路径，这对总体呼叫流和质量的影响最大。

 **ExpressRoute** 这是整个网络的一部分网络段，可让你与 Microsoft 网络建立专用连接。 对于依赖于网络速度和性能的所有工作负荷（例如 Skype for Business Online 实时通信）来说，建议使用此选项将网络连接到 Microsoft 网络 (Microsoft 365 或 Office 365 数据中心) 。 ExpressRoute 连接在网络和 Microsoft 网络之间使用 [ExpressRoute](/azure/expressroute/expressroute-locations) 连接提供商提供专用和托管网络，其运行时间为 99.9%，并支持服务质量 (QoS) ，可在网络拥塞期间提高实时媒体的性能。

 **Microsoft 网络** 这是一个网络段，它属于整个网络，支持Microsoft 365 Office 365服务。 这包括联机服务器之间的所有通信，Microsoft 365或Office 365。 这可能包括遍历 Microsoft 网络主干和在地理区域之间传输的流量。

### <a name="types-of-traffic"></a>流量类型

Skype for Business Online 的网络流量分为两大类，在调用流中显示为单独的路径：

 **实时媒体是** RTP 中封装的数据 (实时传输协议) 支持音频、视频、应用程序共享和文件传输工作负荷。 通常，媒体流量对延迟高度敏感，因此，你可能希望此流量采用尽可能最直接的路径，并使用 UDP 作为传输层协议，因为使用 TCP 会引入更高的延迟。

 **信令** 是客户端与服务器或其他客户端之间的通信链接，用于控制活动 (例如，在调用发起时) 传递 VM。 大多数信令流量使用 SIP 协议，尽管某些客户端使用基于 HTTP 的 REST 接口。 为简单明了，我们正在考虑在此类流量中通过 HTTP 和 HTTPS 或 TLS 连接传输的各种信号。 必须了解，此流量对延迟不太敏感，但如果终结点之间的延迟超过几秒，则可能会导致服务中断或调用超时。

此流量的目标位于所有Office 365或服务Microsoft 365 [IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)地址Office 365范围。 对于每个 URL，它指示该部分流量是否可以遍历 ExpressRoute Microsoft 365或Office 365。 有关显示启用 ExpressRoute 时，Internet 仍用于某些流量的图表，请参阅 Azure [ExpressRoute for Office 365。](https://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd) 必须知道，即使列为通过 ExpressRoute 可路由的 URL 也可通过 Internet 进行路由。 这意味着，在某些情况下，决定是使用 Internet 还是 ExpressRoute 取决于客户端的位置以及代理服务器和防火墙的配置。 还必须了解，由于并非所有与 Microsoft 365 或 Office 365 关联的 URL 都能使用 ExpressRoute，因此即使从 ExpressRoute 合作伙伴购买 ExpressRoute，也还需要建立 Internet 连接。

只能通过 Internet 发送的流量包括常见的 Internet 依赖项，例如证书吊销列表 (CTL) 、DNS 查找和名称解析、共享 Microsoft 365 或 Office 365 服务（例如 Microsoft 365 管理中心）的 URL，以及 Skype for Business Online 的一些非实时通信功能，例如用于与 Skype 使用者互操作性的遥测和联合，以及针对 Skype 会议 Broadcast 流式传输的媒体。 若要帮助做出决策，请参阅[使用 ExpressRoute](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)进行Office 365，了解规划网络路由时需要考虑的更多注意事项。

## <a name="principles-for-call-flows-with-skype-for-business"></a>使用 Skype for Business 的呼叫流原则

在了解特定调用流方案的详细信息之前，有六个一般性原则可帮助你了解特定呼叫流的Skype for Business。

1. Skype for Business会议托管在会议组织者的同一区域。 如果组织者是联机用户，则位于云中;如果会议组织者是本地用户，则位于本地数据中心。

2. 从客户端发送到托管会议的媒体流量始终会发送到托管会议的服务器。 这可能是你管理的数据中心内的本地服务器，或者是云中的联机服务器。 但是，Edge 服务器始终用于联机会议的媒体流。

3. 点对点呼叫的媒体流量使用最直接的可用路由。 首选路由直接路由到远程对等 (客户端) ，但如果该路由因防火墙阻止流量或类似情况而不可用，则一个或多个边缘服务器将中继流量。

4. 信令流量始终会转到用户所位于的服务器（联机或本地）。 如果前端服务器无法直接连接到，则使用 Edge 服务器。

5. 由于客户端防火墙配置 (，加入联机托管会议的用户始终会使用一 (两个边缘) 。

6. 如果从包含本地部署的同一网络进行连接，则加入本地托管会议的用户通常不使用 Edge 服务器，并且从网络外部连接时将使用一个或两个边缘服务器。

若要了解有关所选媒体路径的详细信息，请参阅 [ICE - 边缘媒体连接](https://aka.ms/AVEdge)。 尽管此视频与 Lync Server 2013 有关，但原理和协议仍适用于Skype for Business。

## <a name="skype-for-business-call-flows-with-expressroute"></a>Skype for Business ExpressRoute 调用流

了解四个不同的网段和 Skype for Business 呼叫流的一些一般指导原则后，可以使用该信息来帮助了解哪些 Skype for Business 流量将遍历 ExpressRoute 网络段。

一般情况下，如果一个终结点位于网络中，另一个终结点位于数据中心或数据中心，则网络流量Microsoft 365 expressRoute Office 365。 这包括客户端和服务器之间的信令流量、电话会议期间使用的媒体流量或使用 Online Edge 服务器的点对点呼叫。

如果两个终结点能够直接通过 Internet 通信或位于网络内部，则流量不会遍历 ExpressRoute 连接。 这包括点对点呼叫的媒体、从 Internet 发往本地部署的流量，或者 Internet 与 Microsoft 365 或 Office 365 服务器之间的任何流量。 例如，用户从酒店加入联机会议。

## <a name="basic-skype-for-business-call-flow"></a>基本Skype for Business调用流

为了帮助你应用与上述调用流Skype for Business一般主体，本文的下一部分包含多个图表供参考。 这不是所有可能的调用流的详尽列表，但旨在帮助你应用上面详述的原则。 此外，图中的方案已选择涵盖常见部署类型，包括联机、混合、云连接器，在一种特殊情况下，Skype 会议广播。

> [!NOTE]
> 用户使用的一Skype for Business不可通过 ExpressRoute 路由，并且始终采用 Internet 路径。 请参阅Office 365 URL 和[IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)，确定可能受影响的 URL。

### <a name="peer-to-peer-call-for-microsoft-365-or-office-365-user-from-within-customer-network"></a>从客户网络内部Microsoft 365或Office 365用户的对等呼叫
<a name="bk_Figure2"> </a>

对于对等调用，媒体流量始终采用最直接的路由到其目标。 但是，信令流量将Microsoft 365或Office 365 Online 用户托管的数据中心。 由于两个用户位于同一 WAN 上，并且没有任何内容阻止客户端直接通信，因此媒体直接在两者之间流动。 为两个用户发送流量信号会遍历 ExpressRoute 连接，该连接目标为每个组织的数据中心。 若要在此方案中显示呼叫流，请参阅此部分。

 **对等呼叫流**

![使用Flow对等调用调用呼叫。](../images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)

### <a name="online-user-on-your-network-joining-a-conference-that-is-hosted-online"></a>你的网络上加入在线托管会议的在线用户
<a name="bk_Figure3"> </a>

在对等示例中，媒体流量始终采用最直接的路由到达其目标。 但是，对于联机会议，目标位于云中。 这意味着，从网络内部加入会议的所有用户的媒体流量将遍历 ExpressRoute 连接，并且信令流量将到达云。 下图显示媒体和信令都将遍历网络中用户的 ExpressRoute 连接，并且对于从网络外部（如咖啡店或酒店）连接到 Internet 的用户，将直接遍历 Internet。

请记住，会议的位置由会议组织者而不是参与者定义。 这意味着，如果会议由本地客户安排，则媒体流量不会通过 ExpressRoute 流向云，而是通过 Internet 遍历到会议组织者本地数据中心。

Online 会议的媒体目标将是 Microsoft 365 或 Office 365 云中的数据中心，但数据中心可能位于与加入会议的用户不同的地理区域。 这可以通过两种方式之一发生：

- 如果会议组织者来自与与会者或参与者不同的公司，并且组织者的组织托管在不同的地理位置或国家/地区。

- 如果用户从与公司组织所在的国家/地区不同的国家/地区加入，原因可能是公司是跨国公司，或者用户正在出差。

在此方案中使用 ExpressRoute 的好消息是，使用 ExpressRoute 高级版外接程序时，无论会议组织的数据中心的组织者的地理区域如何，ExpressRoute 路径后的数据都会自动通过 Microsoft 主干传递。

 **具有联机会议呼叫流的联机用户**

![联机托管电话会议的呼叫流。](../images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)

### <a name="joining-a-conference-hosted-by-on-premises-user-in-hybrid-deployment"></a>在混合部署中加入由本地用户托管的会议
<a name="bk_Figure3"> </a>

请记住，支持托管会议的会议服务器由会议组织者的托管位置决定。 在此方案中，加入由混合部署中的本地用户安排的会议的所有用户的媒体将流向本地数据中心。 将通过其组织在云中为 Online 托管用户建立信号，而媒体将尝试直接连接。 在此方案中，由于两个用户都从网络内部进行连接，因此可以建立直接媒体连接，因此 ExpressRoute 仅用于向在线用户发送流量信号。 如果 Online 家庭用户从 Internet 进行连接，则媒体可以遍历 ExpressRoute（如果使用联机边缘服务器进行连接）。

 **由混合用户呼叫流托管的会议**

![托管于 onprem 的调用流。](../images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)

### <a name="on-premises-edge-server-with-microsoft-365-or-office-365-hosted-conferences"></a>本地边缘服务器，Microsoft 365 Office 365会议
<a name="bk_Figure5"> </a>

当混合用户加入联机托管会议时，我们知道信令和媒体将目的地为 Microsoft 365 或 Office 365 云，并且由于用户正在从 Internet 加入，因此通常会采用直接 Internet 路径。 但是，在某些情况下，例如由于防火墙限制，直接 Internet 路径不可用。 在这种情况下，本地边缘服务器可以中继媒体流量，这会导致媒体流量在将 ExpressRoute 线路遍历到云之前返回到本地网络。

 **使用本地边缘服务器加入联机电话会议本地用户**

![通过边缘服务器进行电话会议的呼叫流。](../images/0178c170-5837-430d-84f1-582784bfef55.png)

### <a name="pstn-call-using-skype-for-business-cloud-connector-edition"></a>使用 PSTN 呼叫Skype for Business 云连接器版本
<a name="bk_Figure6"> </a>

使用[Skype for Business Online Cloud Connector Edition](https://aka.ms/CloudConnectorInstaller)提供 PSTN 连接，使用本地资源（例如 SIP 中继或 PSTN 网关）或者使用最少的硬件设备与 Skype for Business。 使用 Cloud Connector Edition 时，用户是托管在 Online 上的，在不涉及呼叫计划时充当普通 Online 用户。 PSTN 方案的信号将跨 ExpressRoute 连接在客户端和云之间传输（如果可用，并且媒体流量保留在 WAN 内）。 在这种情况下，信令在云中Microsoft 365或Office 365，在云连接器处终止。

 **通过云连接器或云电话系统Microsoft 365 Office 365 PSTN 呼叫**

![使用云 PBX 云连接器进行 PSTN 呼叫的呼叫流。](../images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)

### <a name="skype-meeting-broadcast-with-users-joining-from-customer-network"></a>Skype 会议使用从客户网络加入的用户进行广播
<a name="bk_Figure6"> </a>

Skype 会议广播是一种特殊用例，包括由两部分组成的会议，每个部分具有不同的网络传输配置文件。 从网络性能的角度来看，第一部分（也是最重要的部分）是内部会议。 这是会议实时部分，包括连接到云中会议服务器的一个或多个客户端终结点。 使用此部分会议传输的数据与上述示例完全相同，用户正在加入联机会议。

广播Skype 会议的独特之处是会议使用广播流式处理服务分发给大量与会者。 此广播流式处理服务无法通过 ExpressRoute 进行路由，而是使用具有可选支持的 Internet 内容分发网络 (CDN) 服务。 它有助于识别广播流是单向媒体流，因为与会者会侦听，但不说话并支持缓冲，因此对网络性能问题（如延迟、数据包丢失和抖动）不太敏感。 它针对带宽利用率进行了优化，而不是针对这些问题优化广播流量，因为可能有很多与会者接收流式传输的媒体。

 **Skype 会议从客户网络与用户一起广播**

![直播的Skype 会议流。](../images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)

## <a name="call-flow-patterns-by-deployment-type"></a>按部署类型表示的调用流模式

通过上面的常见调用流示例，以及控制流量模式的一般原则，下表汇总了大型部署和使用方案组合的流量模式。 这些表不会捕获所有可能的呼叫流组合，但可以帮助你进一步了解呼叫流的一般原理。

数据将传输并列为组织本地数据;它不会离开客户网络、Internet 或 ExpressRoute。 下面列出的模式基于最常见的网络设置（例如防火墙、联合身份验证和 Internet）并假设参与多方或联合流的所有组织都有 ExpressRoute。 在实践中，使用不同的设置可能会导致流量模式不同于下面列出的流量模式。

### <a name="call-flows-for-skype-for-business-online"></a>Skype for Business Online 的呼叫流

Skype for Business联机使用方案涉及在线家庭用户，并且可能正在从内部网络或 Internet 进行呼叫。 本地服务器不是这些方案的一部分，因此所有与会议或 PSTN 相关的媒体都将流向云，Online 用户边缘服务器也将在云中。

 **Skype for Business Online 的呼叫流摘要**


|**使用方案** <br/> |**终结点** <br/> |**信令路径** <br/> |**媒体路径** <br/> |**示例流** <br/> |**注释** <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|
|点对点呼叫  <br/> |两个客户端，两个都位于网络中。  <br/> |ExpressRoute  <br/> |local  <br/> |[从客户网络内部Microsoft 365或Office 365用户的对等呼叫](call-flow-using-expressroute.md#bk_Figure2) <br/> ||
|点对点呼叫  <br/> |两个客户端（一个位于 (内部) ，另一个客户端位于 Internet 上的 (外部) 。  <br/> |内部用户：ExpressRoute  <br/> 外部用户：Internet  <br/> |内部用户：ExpressRoute  <br/> 外部用户：通过 Internet Microsoft 365或Office 365边缘服务器。  <br/> |[从客户网络内部Microsoft 365或Office 365用户的对等呼叫](call-flow-using-expressroute.md#bk_Figure2) <br/> |假设防火墙阻止需要联机边缘服务器的客户端之间的直接连接。 从内部用户到 Online Edge 服务器的流量遵循的路径与会议呼叫的会议服务器的路径类似。  <br/> |
|对联盟组织中用户的对等调用  <br/> |两个客户端位于 (内部) ，联机用户位于联合组织的网络中， (联合) 。  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[你的网络上加入在线托管会议的在线用户](call-flow-using-expressroute.md#bk_Figure3) <br/> |假设防火墙阻止客户端之间的直接连接，需要联机边缘服务器。 从内部用户到 Online Edge 服务器的流量遵循的路径与用于电话会议的会议服务器的路径类似。  <br/> |
|在客户网络中按用户加入电话会议  <br/> |网络客户端和云中的会议服务器。  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[你的网络上加入在线托管会议的在线用户](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|在 Internet 中按用户加入电话会议  <br/> |客户端位于 Internet 上，会议服务器位于云中。  <br/> |Internet  <br/> |Internet  <br/> |[你的网络上加入在线托管会议的在线用户](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|加入由另一家公司的内场服务器托管的会议  <br/> |第三方数据中心的网络和会议服务器上的客户端。  <br/> |Internet  <br/> |Internet  <br/> |不适用  <br/> |由于托管会议的会议服务器位于其他客户的本地网络上，因此不会通过 Microsoft 云传递任何数据。  <br/> |
|PSTN 呼叫  <br/> |客户网络中客户端电话系统云中的服务器  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[你的网络上加入在线托管会议的在线用户](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|PSTN 呼叫  <br/> |Internet 上的客户端电话系统云中的服务器  <br/> |Internet  <br/> |Internet  <br/> |不适用  <br/> |媒体和信号将流向Microsoft 365或Office 365数据中心。 由于客户端终结点位于 Internet 上，因此所有数据都将通过 Internet 流式传输至 Microsoft 数据中心 (即使需要一个 Online Edge 服务器才能进行连接) 。  <br/> |

> [!NOTE]
> ExpressRoute 将在媒体路径（从位于企业网络的用户到联机边缘服务器）上使用，但如果使用了其他客户的本地部署的边缘服务器，则不使用 ExpressRoute。

### <a name="call-flows-for-skype-for-business-hybrid"></a>调用流的Skype for Business 混合

当具有至少包含一些本地Skype for Business部署时，混合调用流适用。 本部分中的呼叫流包括本地会议以及具有至少一个本地本地用户对等呼叫或 PSTN 呼叫。



|**使用方案** <br/> |**终结点** <br/> |**信令路径** <br/> |**媒体路径** <br/> |**示例流** <br/> |**注释** <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|
|点对点呼叫  <br/> |两个客户端，同时位于客户网络和本地  <br/> |Local  <br/> |local  <br/> |[从客户网络内部Microsoft 365或Office 365用户的对等呼叫](call-flow-using-expressroute.md#bk_Figure2) <br/> |由于用户位于本地，因此信令流会本地流向本地数据中心，而不是云。  <br/> |
|点对点呼叫  <br/> |两个客户端，两个客户端都从客户网络进行连接。 一个为联机主页，另一个位于本地。  <br/> |联机用户：ExpressRoute  <br/> 本地用户：本地  <br/> |local  <br/> |[从客户网络内部Microsoft 365或Office 365用户的对等呼叫](call-flow-using-expressroute.md#bk_Figure2) <br/> |只有 Online 托管用户向云发送信号流量。  <br/> |
|对联盟组织中用户的对等调用  <br/> |两个客户端（客户网络 (本地用户) 联合公司网络本地用户 (联合) 。  <br/> |内部用户：本地  <br/> 联合用户：ExpressRoute  <br/> |Internet 或 ExpressRoute (取决于是联机服务器还是本地边缘服务器)   <br/> |你的[网络上在线](call-flow-using-expressroute.md#bk_Figure3)用户加入联机托管的会议以及本地边缘服务器的一部分，使用[Microsoft 365](call-flow-using-expressroute.md#bk_Figure5)或 Office 365 托管的会议 (媒体流量) 。 <br/> |假设防火墙阻止客户端之间的直接连接，需要联机边缘服务器。 ICE 协商将提供联机 (联机用户) 本地边缘服务器 (本地边缘服务器) 连接。  <br/> |
|在由 Online 用户组安排 (中按用户加入电话会议)   <br/> |网络和云中的会议服务器中的本地用户。  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[你的网络上加入在线托管会议的在线用户](call-flow-using-expressroute.md#bk_Figure3) <br/> |会议呼叫的服务器资源由会议组织者定义。 在这种情况下，它是由 Online 用户计划的，因此资源在云中。  <br/> |
|PSTN 呼叫  <br/> |网络本地用户，本地用户Skype for Business数据中心。  <br/> |Local  <br/> |Local  <br/> |[使用 PSTN 呼叫Skype for Business 云连接器版本](call-flow-using-expressroute.md#bk_Figure6) <br/> |与使用 Cloud Connector Edition 的方案类似，但该用户位于本地，因此信号保留在网络中。  <br/> |

### <a name="call-flows-for-skype-for-business-with-cloud-connector"></a>使用云连接器Skype for Business调用流

将连接到 Cloud Connector Edition 的用户全部托管在 Online 中。 这意味着会议将联机，并且信令遵循与 Online 用户相同的模式。 对于 PSTN 呼叫外的其他情况，呼叫流将完全如上文所述，适用于 Skype for Business Online。



|**使用方案** <br/> |**终结点** <br/> |**信令路径** <br/> |**媒体路径** <br/> |**示例流** <br/> |**注释** <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|
|PSTN 呼叫  <br/> |使用 Cloud Connector Edition 在网络中联机用户。  <br/> |local  <br/> |local  <br/> |[使用 PSTN 呼叫Skype for Business 云连接器版本](call-flow-using-expressroute.md#bk_Figure6) <br/> ||
|PSTN 呼叫  <br/> |使用 Internet 的联机用户使用 Cloud Connector Edition。  <br/> |Internet  <br/> |Internet  <br/> |本地[Edge 服务器与](call-flow-using-expressroute.md#bk_Figure5)Microsoft 365 或 Office 365 会议的组合，以及使用 Skype for Business 云连接器版本[的 PSTN 呼叫](call-flow-using-expressroute.md#bk_Figure6)。  <br/> |Internet 用户通过云连接器中包含的边缘服务器进行连接，云连接器将连接到 PSTN 网络。  <br/> |

## <a name="related-topics"></a>相关主题

[ExpressRoute 文档](/azure/expressroute/)
