---
title: "使用 ExpressRoute 的呼叫流"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 413acb29-ad83-4393-9402-51d88e7561ab
description: "本文旨在介绍 Skype for Business Online 和 ExpressRoute 的核心呼叫流原理，并提供详细呼叫流示例来帮助你正确理解和规划呼叫流。"
---

# 使用 ExpressRoute 的呼叫流

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明](413acb29-ad83-4393-9402-51d88e7561ab.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/413acb29-ad83-4393-9402-51d88e7561ab) 中查找本文的英文版本以便参考。
  
本文旨在介绍 Skype for Business Online 和 ExpressRoute 的核心呼叫流原理，并提供详细呼叫流示例来帮助你正确理解和规划呼叫流。
  
如果您部署 Skype for Business Online 作为 Office 365、 Skype for Business Server 混合或 Skype for Business 云连接线版本的一部分，您将需要因此了解 Skype for Business 客户端和服务器和呼叫流之间的通信有效地可以规划、 部署、 操作和解决您的 Skype for Business Online 服务。
  
## 呼叫流概述

本文介绍可以执行的数据排列这些呼叫，并可帮助您了解哪种通信的段将保留本地网络相比将旅行通过适用 ExpressRoute 或通过 Internet 流量网络。了解哪种通信使用适用 ExpressRoute 将帮助您评估贵公司使用适用 ExpressRoute，以及帮助您了解适用 ExpressRoute 部署指南来验证和解决您的部署一旦决定将收到的好处若要使用适用 ExpressRoute。
  
本文介绍的呼叫流受你可以控制的一系列因素的影响，包括防火墙规则、NAT 配置、代理和路由器配置。本文假设你使用的是推荐设置。这些推荐设置在以下文档中进行了说明：
  
- [设置 Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
    
- [Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
    
- [适用于 Office 365 的 Azure ExpressRoute](https://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd)
    
- [Azure ExpressRoute](https://azure.microsoft.com/en-us/services/expressroute/)
    
设置和配置尚未遵循上面的文档中找到的设置步骤可以比我们此处介绍的不同呼叫流。此外，您可能会发现自己配置问题，例如对称和非最佳网络路由或非最佳传输协议。对称路由是重要的考虑因素时涉及适用 ExpressRoute，因为适用 ExpressRoute 引入到 Office 365，请使用一个方向 Internet 传送和使用另一个路由可能导致的第二个路径在其他方向适用 ExpressRoute。这可能会导致如果它遍历状态防火墙被阻止的寄信人方向的流量。
  
## 网络分段和流量类型

### 网络分段

在介绍呼叫流之前，我们需要对某些术语进行定义，以帮助你了解 Skype for Business Online 中使用的网络分段和媒体类型。
  
呼叫工艺流程图下面显示四种不同的网络段，其中每个由具有不同的不同组织 （内部网络、 网络服务提供商，以及其 Internet 对等合作伙伴和 Microsoft）性能特征。有关网络性能目标的准则，请参阅[Skype for Business Online 中的媒体质量和网络连接性能](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md)。
  
以下是我们将要讨论的各个网络分段。
  
![Call Flow Network Segments.](../images/25689bf2-4753-4bea-b8d7-88dc8b6d2e2a.png)
  
 **您的网络** 这是网段整体网络中控制和管理的一部分。这其中包括您的所有连接您的办公室内是否有线或无线，之间办公楼到本地数据中心，并且您连接到 Internet 提供商或适用 ExpressRoute 合作伙伴。
  
通常情况下，您的网络的边缘具有一个或多个 DMZ 防火墙和/或代理服务器，其中强制实施您所在组织的安全策略和，只允许您设置并配置某些网络流量。由于管理此网络，您可以直接控制您的网络的性能，强烈建议您完成网络评估验证同时内网站从您的网络 Skype for Business 中您的网络和性能联机。若要查看的性能要求，请参阅[Skype for Business Online 中的媒体质量和网络连接性能](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md)。
  
 **Internet** 这是您将使用的用户连接到 Skype for Business Online 从外部网络，以及时适用 ExpressRoute 没有配置用于所有连接的整体网络的一部分的网络段。Internet 和所有其连接不管理由您或 Microsoft，所以性能和路由路径不能确定，而这将拥有整体呼叫流和质量的最大的影响。
  
 **适用 ExpressRoute** 这是您可以让您与 Microsoft 网络的专用连接的整体网络的一部分的网络段。所有的工作负荷依赖于网络速度和性能，例如 Skype for Business Online 实时通信，这是您的网络连接到 Microsoft 网络 （Office 365 数据中心） 的推荐的选项。适用 ExpressRoute 连接之间进行您的网络和 Microsoft 网络使用[适用 ExpressRoute 连接提供程序](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/)为私有和托管网络，提供 99.9%的运行时间和支持服务质量 (QoS)可提高性能期间网络拥挤实时媒体。
  
 **Microsoft 网络** 这是属于您支持 Office 365 服务的总体网络的网络段。这其中包括所有 Office 365 联机服务器之间的通信。这可能包括遍历 Microsoft 网络主干和地理区域之间传输的流量。
  
### 流量类型

Skype for Business Online 的网络流量分为两大类，显示为单独的路径，在呼叫流：
  
 **实时媒体** 封装 RTP （实时传输协议） 内的数据，并且支持音频、 视频、 应用程序共享和文件传输工作负载。一般情况下，媒体流量是高度敏感，延迟，因此想以使最直接的路径，此通信和 UDP 用作传输层协议因为使用 TCP 引入了较高延迟。
  
 **信号** 是客户端和服务器，或用于控制活动 （例如，在启动呼叫时），其他客户端之间提供即时消息通信链接。大多数信号流使用 SIP 协议，某些客户端使用基于 HTTP 的其余部分接口也是如此。若要更加简单，我们正在考虑可能在这种类型的流量旅行通过 HTTP 和 HTTPS 或 TLS 连接各种信号。请务必了解这种通信重要性低得多敏感的延迟，但可能会导致服务中断或呼叫超时，如果终结点之间的延迟超过几秒钟。
  
为此通信目标[Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)中找到所有 Office 365 服务。对于每个 URL，则表明是否的流量部分可能会为 Office 365 遍历适用 ExpressRoute。 显示启用适用 ExpressRoute 时，Internet 仍使用某些通信的图表，请参阅[适用于 Office 365 的 Azure ExpressRoute](https://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd)。请务必理解，甚至被列为可路由适用 ExpressRoute 上方的 Url 是也可路由通过 Internet。这意味着，在某些情况下，确定是否使用 Internet 或适用 ExpressRoute 取决于客户端的位置和配置代理服务器和防火墙。还有一点了解由于并非所有 Url 都与 Office 365 还可以使用适用 ExpressRoute，即使您购买适用 ExpressRoute 从适用 ExpressRoute 合作伙伴，则需要 Internet 连接。
  
仅通过 Internet 发送的流量包括公共 Internet 相关性，例如证书吊销列表 (Crl)、 DNS 查找和名称解析，Url 共享 Office 365 服务，如 Office 365 管理中心中和的一些非实时的通信功能的 Skype for Business Online，如遥测和联合身份验证的互操作性与 Skype 消费者作为以及用于 Skype 会议直播传输的媒体。为了帮助您做出决策，请参阅[使用适用于 Office 365 的 ExpressRoute 进行路由](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)多个注意事项计划您的网络路由时。
  
## Skype for Business 呼叫流的原理

我们了解详细信息之前的特定呼叫流方案，有六个常规原则，帮助您了解 Skype for Business 呼叫流。
  
1. Skype for Business 会议托管会议组织者所在的同一区域中。这是在 Office 365 云如果组织者的联机用户或本地数据中心中，如果会议组织者是本地用户。
    
2. 从客户端发送到托管会议始终媒体流量转到服务器托管会议的位置。这可能是您管理数据中心内的内部部署服务器或 Office 365 云内的联机服务器。 但是，边缘服务器始终用于为联机会议的媒体流。
    
3. 点对点呼叫的媒体流量采用最直接的可用路由。首选路由是直接连接远程对等机（客户端）的路由，但如果该路由因防火墙阻止流量或类似原因而不可用，则会利用一个或多个边缘服务器对流量进行中继。
    
4. 信令流量总是传输到用户所在地的服务器（Online 服务器或本地服务器）。如果无法直接连接前端服务器，则会使用一个边缘服务器。
    
5. 用户加入在 Online 中托管的会议时，总是会使用一个边缘服务器（或者在受客户端防火墙配置限制时使用两个边缘服务器）。
    
6. 用户加入在本地托管的会议时，如果从包含本地部署的同一个网络的内部进行连接，则通常不使用边缘服务器，但如果从你的网络的外部进行连接，则会使用一个或两个边缘服务器。
    
若要了解有关在选择的媒体路径的详细信息的详细信息，请参阅[冰-边缘的媒体连接](https://aka.ms/AVEdge)。虽然此视频是有关 Lync Server 2013，原则和协议仍然适用于 Skype for Business。
  
## 使用 ExpressRoute 的 Skype for Business 呼叫流

既然您已为 Skype for Business 呼叫流了解四种不同的网段和一些常规指导原则，您可以使用信息以帮助您了解哪些 Skype for Business 的流量将遍历适用 ExpressRoute网络段。
  
如果一个端点位于你的网络内，另一个端点位于 Office 365 数据中心，则网络流量通常会通过 ExpressRoute 连接传输。这些网络流量包括客户端和服务器之间的信令流量、会议呼叫期间使用的媒体流量或使用在线边缘服务器的点对点呼叫。
  
如果两个终结点可以直接通过 internet 通信或都是在您的网络，流量不会遍历适用 ExpressRoute 连接。这将包括对等呼叫、 从本地部署中，发往 Internet 流量或任何 Internet 和 Office 365 边缘服务器之间的通信的媒体。此示例将用户加入旅馆从一个联机会议。
  
## Skype for Business 基本呼叫流

为帮助你运用上文所述的有关 Skype for Business 呼叫流的一般原理，本文在下一节中列出了几个参考示意图。它并没有列出所有可能的呼叫流，只是为了帮助你运用上述原理。另外，示意图中所选择的场景涵盖了常见部署类型，包括 Online、Hybrid、Cloud Connector 以及 Skype 会议广播这个特殊用例。
  
> [!NOTE]
> 使用 Skype for Business 的通信的子集适用 ExpressRoute，在未可路由并始终将 Internet 路径。请参阅[Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)以确定 Url 可能会受到影响。 
  
### 从客户网络中的 Office 365 用户的对等呼叫
<a name="bk_Figure2"> </a>

对于点对点呼叫，媒体流量总是采用最直接的路径传输到目标。但是，信令流量会传输到 Online 用户托管地的 Office 365 数据中心。由于两个用户位于同一个 WAN，并且客户端可以畅通无阻地直接通信，因此媒体会直接在用户之间流动。两个用户的信令流量会通过 ExpressRoute 连接传输到每个组织的数据中心。下图说明了此场景中的呼叫流。
  
 **点对点呼叫流**
  
![Call Flow with Peer to Peer call.](../images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)
  
### 你的网络中的 Online 用户加入托管在 Online 的会议
<a name="bk_Figure3"> </a>

在对等的示例中，媒体流量始终接受最直接路由到其目标。但是，对于一个联机会议目标是在 Office 365 云。这意味着媒体加入会议从您的网络中的所有用户的流量将遍历适用 ExpressRoute 连接，并且信号流传输到 Office 365 云。下图显示媒体和信号将遍历适用 ExpressRoute 连接为您的网络中的用户，并将直接遍历 Internet 连接到 Internet 从外部网络，例如从 coffee 的用户购买或旅馆。
  
请记住，会议组织者，而非按参与者定义会议的位置。这意味着如果会议已通过本地客户排定日程，媒体流量不到 Office 365 云排列在适用 ExpressRoute，但会改为通过 Internet 到本地数据中心的会议组织者。
  
Online 会议的媒体流量的传输目标是 Office 365 云内部的数据中心，但该数据中心可能与加入会议的用户位于不同的地理区域。这可能会在以下两种情况下出现：
  
- 如果会议组织者同与会者或参与者来自不同的公司，并且组织者所在的组织位于不同的地理位置或国家/地区。
    
- 如果加入会议的用户的所在地与公司组织所在的国家/地区不同，例如公司为跨国公司或加入会议的用户正在出差。
    
好消息中包含有关使用适用 ExpressRoute 这种情况是，带适用 ExpressRoute 高级加载项，按照适用 ExpressRoute 路径的数据将自动跨传递 Microsoft 的主干网，而不考虑会议组织者的地理区域组织的数据中心。
  
 **Online 用户加入 Online 会议时的呼叫流**
  
![Call flow for an online hosted conference call.](../images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)
  
### 加入由 Hybrid 部署中的本地用户托管的会议
<a name="bk_Figure3"> </a>

请记住支持托管的会议的会议服务器由会议组织者所在。在此方案中，为所有用户加入会议计划通过本地用户混合部署中的媒体将流向本地数据中心。 将通过在 Office 365 云，其组织建立信号 Online 迁移用户，同时媒体将尝试直接连接。在此方案中，因为这两个用户从连接您的网络中直接媒体连接是可行的因此适用 ExpressRoute 仅用于信号 Online 迁移用户的通信。如果联机迁移的用户从 Internet 连接时，媒体无法遍历适用 ExpressRoute，如果 Online Edge 服务器用于连接。
  
 **Hybrid 用户托管的会议的呼叫流**
  
![Call flow hosted onprem.](../images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)
  
### 使用本地边缘服务器和 Office 365 托管会议
<a name="bk_Figure5"> </a>

混合用户联接联机承载会议，我们就知道信号和媒体将被发送到 Office 365 云，，因为该用户从 Internet 加入，通常直接 internet 将采用路径。但是，在某些情况下，如由于防火墙限制直接的 Internet 路径不可用。在此例中，本地边缘服务器可以中继媒体通信，这会导致媒体通信到 Office 365 云遍历适用 ExpressRoute 电路之前返回到您的本地网络。
  
 **本地用户使用本地边缘服务器加入 Online 会议呼叫**
  
![Call flow for a conference call going through an edge server.](../images/0178c170-5837-430d-84f1-582784bfef55.png)
  
### 使用 Skype for Business Cloud Connector Edition 的 PSTN 呼叫
<a name="bk_Figure6"> </a>

使用[Skype for Business Online 云连接线版本](https://aka.ms/CloudConnectorInstaller)提供 PSTN 连接使用本地资源，如 SIP trunk 或 PSTN 网关，或使用最少的硬件设备与 Skype for Business 集成。使用云连接线版本，用户联机托管和它们不涉及调用计划时作为普通联机用户。 PSTN 方案信号将穿越客户端和云之间如果可用，适用 ExpressRoute 连接和媒体流量停留在您 WAN。 在此例中，信号使用 Office 365 云，并会终止于云连接线。
  
 **通过在 Office 365 和云连接线电话系统的 PSTN 呼叫**
  
![Call flow for a PSTN call using Cloud PBX Cloud Connector.](../images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)
  
### 用户从客户网络加入时的 Skype 会议广播
<a name="bk_Figure6"> </a>

Skype 会议直播是一种特殊使用由两部分会议使用不同的网络传输配置文件时遇到的每个部分组成的大小写。第一部分，并从网络性能的角度来看，最重要的一个是内部会议。这是实时会议包含一个或多个客户端端点连接到 Office 365 云中的会议服务器部分。 使用会议的这一部分传输数据是一样的上方，与 Office 365 用户加入联机会议的示例。
  
Skype 会议直播的独特之处在于，会议分发给大量使用流服务广播会议与会者。此广播流服务，可路由通过适用 ExpressRoute，但改为使用内容传递网络 (CDN) 服务的可选支持 Internet。 很有帮助意识到广播流式处理是单向媒体流因为与会者侦听，但不沟通和支持缓冲，因此对网络性能问题，例如延迟、 数据包丢失和抖动重要性低得多敏感。而不被优化这些问题的广播的通信，它是针对带宽使用优化，因为可能有大量的与会者接收流式的媒体。
  
 **用户从客户网络加入时的 Skype 会议广播**
  
![Call flow for Skype Meeting Broadcast.](../images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)
  
## 根据部署类型分类的呼叫流模式

与公共呼叫流示例上述情况，并了解控件流量模式的一般原则下, 表提供的部署和使用方案大型组合的通信模式的摘要。这些表不捕获的呼叫流所有可能的组合，但可以帮助您进一步了解呼叫流的一般原则。
  
数据传输和列出的本地组织;它不会将客户网络、 Internet 或适用 ExpressRoute。下面列出的模式基于的最常见的网络设置，如防火墙、 联盟和 Internet，并且假定多方或联合流中涉及的所有组织都拥有适用 ExpressRoute。在练习中，让不同设置可能会导致比下面列出了不同的通信模式。
  
### Skype for Business Online 呼叫流

Skype for Business Online 的使用方案涉及托管联机，并可能从您的内部网络或 Internet 调用的用户。内部部署服务器不属于以下情况下，以便所有会议或 PSTN 相关的媒体将都流向 Office 365 云和联机边缘服务器还将在云中的用户。
  
 **Skype for Business Online 呼叫流汇总**
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**使用场景** <br/> |**端点** <br/> |**信令路径** <br/> |**媒体路径** <br/> |**示例流** <br/> |**说明** <br/> |
|点对点呼叫  <br/> |两个客户端，均位于你的网络中。  <br/> |ExpressRoute  <br/> |本地  <br/> |[从客户网络中的 Office 365 用户的对等呼叫](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure2) <br/> ||
|点对点呼叫  <br/> |两个客户端，在您的网络 （内部） 的另一个 （外部） 在 Internet 上的其他客户端。  <br/> |内部用户：ExpressRoute  <br/> 外部用户：Internet  <br/> |内部用户：ExpressRoute  <br/> 外部用户：Internet 到 Office 365 边缘服务器。  <br/> |[从客户网络中的 Office 365 用户的对等呼叫](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure2) <br/> |假定该防火墙阻止客户端，需要 Online Edge 服务器之间的直接连接。从内部用户到 Online Edge 服务器通信遵循类似路径与会议服务器电话会议邀请。  <br/> |
|点对点呼叫联盟组织中的用户  <br/> |两个客户端，一个位于你的网络（内部），另一个位于联盟组织网络（联盟）中的 Online 用户。  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[你的网络中的 Online 用户加入托管在 Online 的会议](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) <br/> |假设防火墙拦截了客户端之间的直接连接，这时需要使用在线边缘服务器。从内部用户到在线边缘服务器的流量采用的路径与到会议呼叫的会议服务器的流量采用的路径相似。  <br/> |
|客户网络中的用户加入会议呼叫  <br/> |客户端位于你的网络，会议服务器位于 Office 365 云中。  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[你的网络中的 Online 用户加入托管在 Online 的会议](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) <br/> ||
|在 Internet 中加入由用户的电话会议  <br/> |客户端是在 Office 365 云 Internet 和会议的服务器上。  <br/> |Internet  <br/> |Internet  <br/> |[你的网络中的 Online 用户加入托管在 Online 的会议](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) <br/> ||
|加入其他公司的本地服务器托管的会议  <br/> |客户端位于你的网络，会议服务器位于第三方数据中心中。  <br/> |Internet  <br/> |Internet  <br/> |不适用  <br/> |由于托管会议的会议服务器位于另一个客户的本地网络中，因此数据不会通过 Microsoft 云进行传输。  <br/> |
|PSTN 呼叫  <br/> |在客户网络并在 Office 365 云的电话系统服务器中的客户端  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[你的网络中的 Online 用户加入托管在 Online 的会议](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) <br/> ||
|PSTN 呼叫  <br/> |在 Office 365 云的 Internet 和电话系统服务器上的客户端  <br/> |Internet  <br/> |Internet  <br/> |不适用  <br/> |媒体和信号将流向 Office 365 数据中心。由于 Internet 上的客户端终结点，所有数据将都流至 Microsoft 数据中心跨 Internet （即使 Online Edge 服务器需要连接）。  <br/> |
   
> [!NOTE]
> 适用 ExpressRoute 将在位于联机边缘服务器上，向公司网络上的用户的媒体路径中使用，但如果使用另一个客户本地部署边缘服务器不会使用。 
  
### Skype for Business Hybrid 呼叫流

混合呼叫流应用时必须包含至少某些用户的迁移的内部部署的业务部署 Skype。本部分中的呼叫流包括两个本地会议，然后对等或 PSTN 呼叫与至少一个本地迁移用户。
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**使用场景** <br/> |**端点** <br/> |**信令路径** <br/> |**媒体路径** <br/> |**示例流** <br/> |**说明** <br/> |
|点对点呼叫  <br/> |两个客户端，一个位于客户网络，另一个在本地托管  <br/> |本地  <br/> |本地  <br/> |[从客户网络中的 Office 365 用户的对等呼叫](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure2) <br/> |由于用户为本地托管用户，因此信令将从本地传输到本地数据中心，而不是 Office 365 云。  <br/> |
|点对点呼叫  <br/> |两个客户端，均从客户网络进行连接。一个为 Online 托管，另一个为本地托管。  <br/> |Online 用户：ExpressRoute  <br/> 本地用户：本地  <br/> |本地  <br/> |[从客户网络中的 Office 365 用户的对等呼叫](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure2) <br/> |只有 Online 托管用户将信令流量发送到 Office 365 云。  <br/> |
|点对点呼叫联盟组织中的用户  <br/> |两个客户端，一个位于客户网络（内部）中的本地用户，另一个位于联盟公司的网络（联盟）中的 Online 用户。  <br/> |内部用户：本地  <br/> 联盟用户：ExpressRoute  <br/> |Internet 或 ExpressRoute（取决于使用 Online 还是本地边缘服务器）  <br/> |[你的网络中的 Online 用户加入托管在 Online 的会议](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3)和[使用本地边缘服务器和 Office 365 托管会议](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure5)（适用于媒体流量）部分。  <br/> |假定防火墙阻止客户端，要求 Online Edge 服务器之间的直接连接。 冰协商将提供联机 （通过联机用户） 和 （通过本地用户） 的本地边缘服务器的连接。  <br/> |
|客户网络中的用户加入会议呼叫（Online 用户安排的会议）  <br/> |本地用户位于你的网络，会议服务器位于 Office 365 云中。  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[你的网络中的 Online 用户加入托管在 Online 的会议](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) <br/> |会议组织者定义电话会议的服务器资源。在此例中，其计划通过联机用户，以便资源位于 Office 365 云。  <br/> |
|PSTN 呼叫  <br/> |本地用户位于你的网络和本地 Skype for Business 数据中心中。  <br/> |本地  <br/> |本地  <br/> |[使用 Skype for Business Cloud Connector Edition 的 PSTN 呼叫](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure6) <br/> |除用户为本地托管外，与使用 Cloud Connector Edition 的场景类似，因此信令一直在你的网络中。  <br/> |
   
### 使用 Skype for Business 和 Cloud Connector 时的呼叫流

连接到 Cloud Connector Edition 的用户全部为 Online 托管用户。这意味着会议将为 Online 会议，并且信令遵循与 Online 用户场景相同的模式。对于 PSTN 呼叫以外的场景，呼叫流与上述 Skype for Business Online 呼叫流完全相同。
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**使用场景** <br/> |**端点** <br/> |**信令路径** <br/> |**媒体路径** <br/> |**示例流** <br/> |**说明** <br/> |
|PSTN 呼叫  <br/> |你的网络中的 Online 用户使用 Cloud Connector Edition。  <br/> |本地  <br/> |本地  <br/> |[使用 Skype for Business Cloud Connector Edition 的 PSTN 呼叫](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure6) <br/> ||
|PSTN 呼叫  <br/> |Internet 中的 Online 用户使用 Cloud Connector Edition。  <br/> |Internet  <br/> |Internet  <br/> |[使用本地边缘服务器和 Office 365 托管会议](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure5)和[使用 Skype for Business Cloud Connector Edition 的 PSTN 呼叫](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure6)的组合。  <br/> |Internet 用户通过 Cloud Connector 中包含的边缘服务器进行连接，而 Cloud Connector 将连接到 PSTN 网络。  <br/> |
   
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

