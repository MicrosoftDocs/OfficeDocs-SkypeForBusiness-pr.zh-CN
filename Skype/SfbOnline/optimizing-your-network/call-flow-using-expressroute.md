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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: 本文旨在介绍 Skype for Business Online 和 ExpressRoute 的核心呼叫流原理，并提供详细呼叫流示例来帮助你正确理解和规划呼叫流。
ms.openlocfilehash: 2406badc671fec8ede36039ebf230115a5920e97
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23861074"
---
# <a name="call-flow-using-expressroute"></a>使用 ExpressRoute 的呼叫流

本文旨在介绍 Skype for Business Online 和 ExpressRoute 的核心呼叫流原理，并提供详细呼叫流示例来帮助你正确理解和规划呼叫流。

如果您部署 Skype 业务 Online 作为 Office 365、 业务服务器混合的 Skype 或商务云连接器版的 Skype 的一部分，您将需要，以便了解业务客户端和服务器 Skype 和呼叫流之间的通信您可以有效地规划、 部署、 操作、 和解决业务在线服务您 Skype。

## <a name="call-flow-overview"></a>呼叫流概述

本文档介绍的网络段，可以执行数据，这些呼叫流和可帮助您了解哪些流量将保持本地网络与通过 Internet 或通过 ExpressRoute 将出差的流量进行比较。了解哪些通信使用 ExpressRoute 将有助于您评估贵公司使用 ExpressRoute，以及帮助您了解 ExpressRoute 部署指南，以验证并排查部署，一旦决定将接收的好处若要使用 ExpressRoute。

本文介绍的呼叫流受你可以控制的一系列因素的影响，包括防火墙规则、NAT 配置、代理和路由器配置。本文假设你使用的是推荐设置。这些推荐设置在以下文档中进行了说明：

- [设置 Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

- [Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

- [ExpressRoute 概述 （英文)](https://docs.microsoft.com/azure/expressroute/expressroute-introduction)

- [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/)

安装和配置您尚未遵循以上的文档中找到的安装步骤可以比我们此处介绍的不同呼叫流。 此外，您可能会发现自己与配置问题，如非对称和非最佳网络路由或非最佳传输协议。 非对称路由的重要考虑事项，只要就涉及 ExpressRoute，因为 ExpressRoute 引入到 Office 365，创建使用一个方向 Internet 的路由和使用的另一个路由的可能性的第二个路径在其他方向 ExpressRoute。 如果流量经过有状态防火墙，这可能会导致流量在返回方向被拦截。

## <a name="network-segments-and-traffic-types"></a>网络分段和流量类型

### <a name="network-segments"></a>网络分段

在介绍呼叫流之前，我们需要对某些术语进行定义，以帮助你了解 Skype for Business Online 中使用的网络分段和媒体类型。

下呼叫流图显示四个不同的网络段，其中每个由具有不同的不同组织 （内部网络、 网络服务提供商，及其 Internet 对等合作伙伴和 Microsoft）性能特征。有关网络性能目标的指南，请参阅[媒体质量和 Skype 业务 online 中的网络连接性能](media-quality-and-network-connectivity-performance.md)。

以下是我们将要讨论的各个网络分段。

![Call Flow Network Segments.](../images/25689bf2-4753-4bea-b8d7-88dc8b6d2e2a.png)

 **您的网络**这是控制并管理总体网络一部分的网络段。这包括所有中您的办公室连接是否有线或无线，连接到 Internet 提供商或合作伙伴 ExpressRoute 办公楼到本地数据中心之间。

通常情况下，您的网络边缘具有一个或多个 DMZ 防火墙和/或代理服务器，其强制实施组织的安全策略和的仅允许您设置并配置某些网络流量。 由于管理此网络，您可以直接控制您的网络的性能，强烈建议您完成网络评估，以验证同时网站网络中以及从您的网络到 Skype for Business 内的性能联机。 若要了解性能要求，请参阅 [Skype for Business Online 中的媒体质量和网络连接性能](media-quality-and-network-connectivity-performance.md)。

 **Internet**这是您要连接到 Skype 业务 online 从外部网络和 ExpressRoute 未配置时用于所有连接的用户将都使用的整个网络一部分的网络段。以便无法确定性能和路由路径，并这将对整个呼叫流和质量影响最大，不是由您或 Microsoft 托管 Internet 和所有其连接。

 **ExpressRoute** 该网络分段是你的整个网络的一部分，可以提供与 Microsoft 网络的专用连接。 所有取决于网络速度和性能，如业务联机实时通信的 Skype 的工作负荷，这是您的网络连接到 Microsoft 网络 （Office 365 数据中心） 的建议的选项。 ExpressRoute 连接所做您的网络和 Microsoft 网络使用[ExpressRoute 连接提供程序](https://azure.microsoft.com/documentation/articles/expressroute-locations/)之间提供 99.9%正常运行时间和支持的服务质量 (QoS) 可以提高性能的私钥和托管网络网络拥塞的时段的实时媒体。

 **Microsoft 网络** 该网络分段是你的整个网络的一部分，它支持 Office 365 服务。 它包括用于 Office 365 的 Online 服务器之间的所有通信。 这可能包括遍历 Microsoft 网络中枢和传输地理区域之间的流量。

### <a name="types-of-traffic"></a>流量类型

网络流量的 Skype 业务 online 分为两大类，显示为单独的路径中的呼叫流：

 **实时媒体**是封装在 RTP （实时传输协议） 的数据，并支持音频、 视频、 应用程序共享和文件传输工作负荷。一般情况下，媒体流量高度是延迟敏感的因此想要执行的最直接路径可能，此通信和因为使用 TCP 作为传输层协议使用 UDP 引入了更高的延迟。

 **信号**是客户端和服务器，或用于控制活动 （例如，当发起呼叫），其他客户端之间传送 Im 通信链接。 大多数信令流量使用 SIP 协议，但有些客户端使用基于 HTTP 的 REST 接口。 若要使简单，我们正考虑在这种类型的流量通过 HTTP 和 HTTPS 或 TLS 连接可能出差各种信号。 该流量对延迟不太敏感，但如果端点之间的延迟超过数秒钟，它可能会导致服务故障或呼叫超时，了解这一点非常重要。

有关该流量的目标，请参阅适用于所有 Office 365 服务的 [Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)。 每个 URL 会指示此部分流量是否可能通过用于 Office 365 的 ExpressRoute。 有关显示 ExpressRoute 启用时，Internet 仍使用的一些流量的图表，请参阅[Office 365 的 Azure ExpressRoute](https://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd)。 若要了解列为通过 ExpressRoute 正在可路由的偶数 Url 还可路由通过 Internet 至关重要。 这意味着，在某些情况下，确定是否使用的 Internet 或 ExpressRoute 取决于客户端的位置和代理服务器和防火墙的配置。 还有一点了解由于并不是所有 Url 都与 Office 365 还可以使用 ExpressRoute，即使您从 ExpressRoute 合作伙伴购买 ExpressRoute，都需要 Internet 连接。

仅可通过 Internet 发送的流量包括公共 Internet 依赖项，如证书吊销列表 (Crl)、 DNS 查找和名称解析，Url 共享 Office 365 服务，如用于 Office 365 管理中心中和一些非-实时通信功能的 Skype 业务 online，如遥测和联合身份验证的互操作性与 Skype 使用者视为以及媒体流入的 Skype 会议广播。 如果需要帮助你作出决定，请参阅[使用适用于 Office 365 的 ExpressRoute 进行路由](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)，了解规划网络路由时需要考虑的其他因素。

## <a name="principles-for-call-flows-with-skype-for-business"></a>Skype for Business 呼叫流的原理

深入了解特定呼叫流场景之前，有六个一般原则可帮助你了解 Skype for Business 呼叫流。

1. 业务会议 Skype 位于会议组织者所在的同一区域中。 如果会议组织者为 Online 用户，则会议托管在 Office 365 云中，而如果会议组织者为本地用户，则会议托管在本地数据中心。

2. 媒体流量从客户端发送到承载会议始终转到的服务器承载会议。这可能是您管理数据中心内的内部部署服务器或联机服务器内 Office 365 云。但是，边缘服务器始终使用的媒体流的联机会议。

3. 点对点呼叫的媒体流量采用最直接的可用路由。首选路由是直接连接远程对等机（客户端）的路由，但如果该路由因防火墙阻止流量或类似原因而不可用，则会利用一个或多个边缘服务器对流量进行中继。

4. 信令流量总是传输到用户所在地的服务器（Online 服务器或本地服务器）。如果无法直接连接前端服务器，则会使用一个边缘服务器。

5. 用户加入在 Online 中托管的会议时，总是会使用一个边缘服务器（或者在受客户端防火墙配置限制时使用两个边缘服务器）。

6. 用户加入在本地托管的会议时，如果从包含本地部署的同一个网络的内部进行连接，则通常不使用边缘服务器，但如果从你的网络的外部进行连接，则会使用一个或两个边缘服务器。

若要了解选择的媒体路径的详细信息，请参阅 [ICE - 边缘媒体连接](https://aka.ms/AVEdge)。 尽管此视频有关 Lync Server 2013，但的原则和协议仍适用于 for Business 的 Skype。

## <a name="skype-for-business-call-flows-with-expressroute"></a>使用 ExpressRoute 的 Skype for Business 呼叫流

既然您的业务呼叫流的 Skype 有四个不同的网络段和一些通用指导原则的了解，您可以使用的信息可帮助您了解业务通信的 Skype 区域将遍历 ExpressRoute网络段。

如果一个端点位于你的网络内，另一个端点位于 Office 365 数据中心，则网络流量通常会通过 ExpressRoute 连接传输。这些网络流量包括客户端和服务器之间的信令流量、会议呼叫期间使用的媒体流量或使用在线边缘服务器的点对点呼叫。

如果两个端点可以跨 Internet 直接通信，或它们位于你的网络内部，则流量不会通过 ExpressRoute 连接传输。 这将包括对等呼叫、 从内部部署，发往 Internet 的流量或任何 Internet 和 Office 365 边缘服务器之间的通信的媒体。 该场景的一个示例是用户从酒店加入 Online 会议。

## <a name="basic-skype-for-business-call-flow"></a>Skype for Business 基本呼叫流

为帮助你运用上文所述的有关 Skype for Business 呼叫流的一般原理，本文在下一节中列出了几个参考示意图。它并没有列出所有可能的呼叫流，只是为了帮助你运用上述原理。另外，示意图中所选择的场景涵盖了常见部署类型，包括 Online、Hybrid、Cloud Connector 以及 Skype 会议广播这个特殊用例。

> [!NOTE]
> Skype 用于业务通信的子集不路由通过 ExpressRoute，并将始终采用 Internet 路径。请参阅[Office 365 Url 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)以确定可能会受到影响的 Url。

### <a name="peer-to-peer-call-for-office-365-users-from-within-customer-network"></a>从客户的网络内的 Office 365 用户的对等呼叫
<a name="bk_Figure2"> </a>

对于点对点呼叫，媒体流量总是采用最直接的路径传输到目标。但是，信令流量会传输到 Online 用户托管地的 Office 365 数据中心。由于两个用户位于同一个 WAN，并且客户端可以畅通无阻地直接通信，因此媒体会直接在用户之间流动。两个用户的信令流量会通过 ExpressRoute 连接传输到每个组织的数据中心。下图说明了此场景中的呼叫流。

 **点对点呼叫流**

![Call Flow with Peer to Peer call.](../images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)

### <a name="online-user-on-your-network-joining-a-conference-that-is-hosted-online"></a>你的网络中的 Online 用户加入托管在 Online 的会议
<a name="bk_Figure3"> </a>

在对等的示例中，媒体流量始终所需的最直接路由至其目标。 但是，对于联机会议，目标是在 Office 365 云中。 这意味着，从你的网络内部加入会议的所有用户的媒体流量，将通过 ExpressRoute 连接传输，而信令流量将传输到 Office 365 云。 下图显示媒体和信号区域将遍历网络，内部用户的 ExpressRoute 连接，并直接将遍历的用户的连接到 Internet 从外部网络，如咖啡从 Internet店或酒店。

请记住，由会议组织者而非参与者定义会议的位置。这意味着，如果会议已安排的本地客户，媒体流量不会将流经到 Office 365 云 ExpressRoute，但会改为通过 Internet 到本地数据中心的会议组织者。

Online 会议的媒体流量的传输目标是 Office 365 云内部的数据中心，但该数据中心可能与加入会议的用户位于不同的地理区域。这可能会在以下两种情况下出现：

- 如果会议组织者同与会者或参与者来自不同的公司，并且组织者所在的组织位于不同的地理位置或国家/地区。

- 如果加入会议的用户的所在地与公司组织所在的国家/地区不同，例如公司为跨国公司或加入会议的用户正在出差。

有关此方案中使用 ExpressRoute 好消息是，使用 ExpressRoute premium 加载项，按照 ExpressRoute 路径的数据将自动跨传递无论会议组织者的地理区域的 Microsoft 的中枢组织的数据中心。

 **Online 用户加入 Online 会议时的呼叫流**

![Call flow for an online hosted conference call.](../images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)

### <a name="joining-a-conference-hosted-by-on-premises-user-in-hybrid-deployment"></a>加入由 Hybrid 部署中的本地用户托管的会议
<a name="bk_Figure3"> </a>

请记住，支持托管的会议的会议服务器由会议组织者所在。在此方案中，为所有用户加入会议安排的混合部署中的内部部署用户的媒体将流至本地数据中心。将通过 Office 365 云，其组织建立信号联机驻留的用户，媒体将尝试直接连接时。在此方案中，因为您的网络内从进行连接这两个用户直接媒体连接是可能的因此 ExpressRoute 仅用于信号联机托管用户的流量。如果从 Internet 连接的联机驻留的用户，媒体可以遍历 ExpressRoute，如果联机边缘服务器用于连接。

 **Hybrid 用户托管的会议的呼叫流**

![Call flow hosted onprem.](../images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)

### <a name="on-premises-edge-server-with-office-365-hosted-conferences"></a>使用本地边缘服务器和 Office 365 托管会议
<a name="bk_Figure5"> </a>

如果混合用户联接 Online 托管会议，我们知道的信号和媒体将发往 Office 365 云，因为该用户加入从 Internet，通常直接的 internet 路径将执行。但是，在某些情况下，例如，由于防火墙限制直接的 Internet 路径不可用。在这种情况下，内部部署边缘服务器可以中继的媒体流量，这将导致的媒体流量遍历到 Office 365 云 ExpressRoute 电路之前返回到您的本地网络。

 **本地用户使用本地边缘服务器加入 Online 会议呼叫**

![Call flow for a conference call going through an edge server.](../images/0178c170-5837-430d-84f1-582784bfef55.png)

### <a name="pstn-call-using-skype-for-business-cloud-connector-edition"></a>使用 Skype for Business Cloud Connector Edition 的 PSTN 呼叫
<a name="bk_Figure6"> </a>

使用 [Skype for Business Online Cloud Connector Edition](https://aka.ms/CloudConnectorInstaller) 时，可通过将本地资源（例如 SIP Trunk、PSTN 网关）或最少硬件设备与 Skype for Business 集成来提供 PSTN 连接。 与云连接器 Edition，用户驻留联机和充当普通 Online 用户，他们不涉及调用计划时。 PSTN 场景的信令会通过 ExpressRoute 连接（如可用）在客户端和云之间传输，而媒体流量会始终在 WAN 内传输。 在这种情况下，信令会在 Office 365 云处改变方向，并在 Cloud Connector 处终止。

 **通过 Office 365 和云连接器中的电话系统的 PSTN 呼叫**

![Call flow for a PSTN call using Cloud PBX Cloud Connector.](../images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)

### <a name="skype-meeting-broadcast-with-users-joining-from-customer-network"></a>用户从客户网络加入时的 Skype 会议广播
<a name="bk_Figure6"> </a>

Skype 会议广播是一种特殊用例，它由一个两部分会议组成，其中每部分都具有不同的网络传输特性。 第一部分，并从网络性能的角度来看，最重要的一个内部会议。 这是会议的包含连接到 Office 365 云中的会议服务器的一个或多个客户端终结点的实时部分。 使用此部分传输的数据是会议的完全一样示例上方，与 Office 365 用户加入联机会议。

Skype 会议广播的独特之处在于会议分发给大量使用广播流式传输服务的会议与会者。 流服务，此广播路由通过 ExpressRoute，但是改为使用内容交付网络 (CDN) 服务的可选支持 Internet。 非常有用识别的广播流是单向的媒体流因为与会者侦听，但不讨论和支持缓冲，使其对网络性能问题，如延迟、 数据包丢失和抖动得敏感。 而不被优化的这些问题的广播的流量，优化的带宽用量因为可能没有数量非常大的与会者接收流式的媒体。

 **用户从客户网络加入时的 Skype 会议广播**

![Call flow for Skype Meeting Broadcast.](../images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)

## <a name="call-flow-patterns-by-deployment-type"></a>根据部署类型分类的呼叫流模式

与公共呼叫流示例上面，并了解控制通信模式的一般原则下, 表提供了部署和使用方案的大型组合的通信模式的摘要。 这些表没有列出所有可能的呼叫流组合，但可以帮助你进一步了解呼叫流的一般原理。

数据传输和列为正在本地组织;它不会保留客户网络、 Internet 或 ExpressRoute。 下面列出的模式基于的最常见的网络设置，如防火墙、 联盟和 Internet，并且假定多方或联盟流中所涉及的所有组织都拥有 ExpressRoute。 在实践中，使用不同的设置可能会导致流量模式不同于下列流量模式。

### <a name="call-flows-for-skype-for-business-online"></a>Skype for Business Online 呼叫流

Skype 的业务在线的使用方案涉及位于联机，并可能从内部网络或 Internet 调用的用户。内部部署服务器不属于以上情况下，以便所有会议或 PSTN 相关的媒体将都流向 Office 365 云和边缘服务器还将在云中 Online 用户。

 **Skype for Business Online 呼叫流汇总**

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**使用场景** <br/> |**端点** <br/> |**信令路径** <br/> |**媒体路径** <br/> |**示例流** <br/> |**说明** <br/> |
|点对点呼叫  <br/> |两个客户端，均位于你的网络中。  <br/> |ExpressRoute  <br/> |本地  <br/> |[从客户的网络内的 Office 365 用户的对等呼叫](call-flow-using-expressroute.md#bk_Figure2) <br/> ||
|点对点呼叫  <br/> |两个客户端上 （内部） 网络和 Internet （外部） 上的其他客户端。  <br/> |内部用户：ExpressRoute  <br/> 外部用户：Internet  <br/> |内部用户：ExpressRoute  <br/> 外部用户：Internet 到 Office 365 边缘服务器。  <br/> |[从客户的网络内的 Office 365 用户的对等呼叫](call-flow-using-expressroute.md#bk_Figure2) <br/> |假定该防火墙阻止客户端，需要联机边缘服务器之间直接连接。到 Online 边缘服务器的内部用户流量遵循类似的电话会议的会议服务器的路径。  <br/> |
|点对点呼叫联盟组织中的用户  <br/> |两个客户端，一个位于你的网络（内部），另一个位于联盟组织网络（联盟）中的 Online 用户。  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[你的网络中的 Online 用户加入托管在 Online 的会议](call-flow-using-expressroute.md#bk_Figure3) <br/> |假设防火墙拦截了客户端之间的直接连接，这时需要使用在线边缘服务器。从内部用户到在线边缘服务器的流量采用的路径与到会议呼叫的会议服务器的流量采用的路径相似。  <br/> |
|客户网络中的用户加入会议呼叫  <br/> |客户端位于你的网络，会议服务器位于 Office 365 云中。  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[你的网络中的 Online 用户加入托管在 Online 的会议](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|在 Internet 加入由用户的电话会议  <br/> |客户端是 Office 365 云 Internet 和会议服务器上。  <br/> |Internet  <br/> |Internet  <br/> |[你的网络中的 Online 用户加入托管在 Online 的会议](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|加入其他公司的本地服务器托管的会议  <br/> |客户端位于你的网络，会议服务器位于第三方数据中心中。  <br/> |Internet  <br/> |Internet  <br/> |不适用  <br/> |由于托管会议的会议服务器位于另一个客户的本地网络中，因此数据不会通过 Microsoft 云进行传输。  <br/> |
|PSTN 呼叫  <br/> |客户网络和 Office 365 云中的电话系统服务器中的客户端  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[你的网络中的 Online 用户加入托管在 Online 的会议](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|PSTN 呼叫  <br/> |Office 365 云 Internet 和电话系统的服务器上的客户端  <br/> |Internet  <br/> |Internet  <br/> |不适用  <br/> |媒体和信号将流到 Office 365 数据中心。由于客户端终结点是在 Internet 上，因此所有数据将都流至 Microsoft 数据中心在 internet （即使联机边缘服务器所需的连接）。  <br/> |

> [!NOTE]
> ExpressRoute 将在位于企业网络的联机边缘服务器，用户的媒体路径中使用，但如果使用另一个客户的内部部署的边缘服务器不使用。

### <a name="call-flows-for-skype-for-business-hybrid"></a>Skype for Business Hybrid 呼叫流

Skype for Business 部署包含至少一部分本地托管用户时，将适用 Hybrid 呼叫流。 本节中的呼叫流包括两个内部会议和对等或 PSTN 呼叫与至少一个内部部署托管用户。

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**使用场景** <br/> |**端点** <br/> |**信令路径** <br/> |**媒体路径** <br/> |**示例流** <br/> |**说明** <br/> |
|点对点呼叫  <br/> |两个客户端，一个位于客户网络，另一个在本地托管  <br/> |本地  <br/> |本地  <br/> |[从客户的网络内的 Office 365 用户的对等呼叫](call-flow-using-expressroute.md#bk_Figure2) <br/> |由于用户为本地托管用户，因此信令将从本地传输到本地数据中心，而不是 Office 365 云。  <br/> |
|点对点呼叫  <br/> |两个客户端，均从客户网络进行连接。一个为 Online 托管，另一个为本地托管。  <br/> |Online 用户：ExpressRoute  <br/> 本地用户：本地  <br/> |本地  <br/> |[从客户的网络内的 Office 365 用户的对等呼叫](call-flow-using-expressroute.md#bk_Figure2) <br/> |只有 Online 托管用户将信令流量发送到 Office 365 云。  <br/> |
|点对点呼叫联盟组织中的用户  <br/> |两个客户端，一个位于客户网络（内部）中的本地用户，另一个位于联盟公司的网络（联盟）中的 Online 用户。  <br/> |内部用户：本地  <br/> 联盟用户：ExpressRoute  <br/> |Internet 或 ExpressRoute（取决于使用 Online 还是本地边缘服务器）  <br/> |[联机用户加入的会议的网络上承载的联机](call-flow-using-expressroute.md#bk_Figure3)和 （用于媒体流量）[与 Office 365 的内部部署边缘服务器承载会议](call-flow-using-expressroute.md#bk_Figure5)的一部分。 <br/> |假定防火墙阻止客户端，需要联机边缘服务器之间直接连接。ICE 协商将提供 （通过联机用户） 的联机和 （通过内部部署用户） 的内部部署边缘服务器的连接。  <br/> |
|客户网络中的用户加入会议呼叫（Online 用户安排的会议）  <br/> |本地用户位于你的网络，会议服务器位于 Office 365 云中。  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[你的网络中的 Online 用户加入托管在 Online 的会议](call-flow-using-expressroute.md#bk_Figure3) <br/> |电话会议服务器资源由会议组织者定义。 在本例中，会议由 Online 用户安排，因此资源位于 Office 365 云中。  <br/> |
|PSTN 呼叫  <br/> |本地用户位于你的网络和本地 Skype for Business 数据中心中。  <br/> |本地  <br/> |本地  <br/> |[使用 Skype for Business Cloud Connector Edition 的 PSTN 呼叫](call-flow-using-expressroute.md#bk_Figure6) <br/> |除用户为本地托管外，与使用 Cloud Connector Edition 的场景类似，因此信令一直在你的网络中。  <br/> |

### <a name="call-flows-for-skype-for-business-with-cloud-connector"></a>使用 Skype for Business 和 Cloud Connector 时的呼叫流

连接到 Cloud Connector Edition 的用户全部为 Online 托管用户。这意味着会议将为 Online 会议，并且信令遵循与 Online 用户场景相同的模式。对于 PSTN 呼叫以外的场景，呼叫流与上述 Skype for Business Online 呼叫流完全相同。

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**使用场景** <br/> |**端点** <br/> |**信令路径** <br/> |**媒体路径** <br/> |**示例流** <br/> |**说明** <br/> |
|PSTN 呼叫  <br/> |你的网络中的 Online 用户使用 Cloud Connector Edition。  <br/> |本地  <br/> |本地  <br/> |[使用 Skype for Business Cloud Connector Edition 的 PSTN 呼叫](call-flow-using-expressroute.md#bk_Figure6) <br/> ||
|PSTN 呼叫  <br/> |Internet 中的 Online 用户使用 Cloud Connector Edition。  <br/> |Internet  <br/> |Internet  <br/> |[与 Office 365 的内部部署边缘服务器承载会议](call-flow-using-expressroute.md#bk_Figure5)和[PSTN 呼叫使用商务云连接器版的 Skype](call-flow-using-expressroute.md#bk_Figure6)的组合。  <br/> |Internet 用户通过 Cloud Connector 中包含的边缘服务器进行连接，而 Cloud Connector 将连接到 PSTN 网络。  <br/> |

## <a name="related-topics"></a>相关主题

[ExpressRoute 文档](https://go.microsoft.com/fwlink/?LinkId=690285)


