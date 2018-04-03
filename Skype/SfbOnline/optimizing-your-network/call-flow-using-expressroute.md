---
title: 使用 ExpressRoute 的呼叫流
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 413acb29-ad83-4393-9402-51d88e7561ab
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
ms.openlocfilehash: 220a23a5a43b281790422c39908e7a0ea32c03b4
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2018
---
# <a name="call-flow-using-expressroute"></a>使用 ExpressRoute 的呼叫流

本文旨在介绍 Skype for Business Online 和 ExpressRoute 的核心呼叫流原理，并提供详细呼叫流示例来帮助你正确理解和规划呼叫流。
  
如果要将 Skype for Business Online 部署为 Office 365、Skype for Business Server Hybrid 或 Skype for Business Cloud Connector Edition 的组成部分，则需要了解 Skype for Business 客户端和服务器之间的通信以及呼叫流，这样才能有效地对 Skype for Business Online 服务进行规划、部署、运行和故障排除。 
  
## <a name="call-flow-overview"></a>呼叫流概述

本文介绍可以为这些呼叫流传输数据的网络分段，并帮助你了解与通过 Internet 或 ExpressRoute 传输的流量相比，哪种流量是在本地网络传输的。了解哪种流量使用 ExpressRoute 可帮助你评估公司使用 ExpressRoute 得到的益处，还可帮助你了解 ExpressRoute 部署指南，以便在决定使用 ExpressRoute 后，对部署进行验证和故障排除。
  
本文介绍的呼叫流受你可以控制的一系列因素的影响，包括防火墙规则、NAT 配置、代理和路由器配置。本文假设你使用的是推荐设置。这些推荐设置在以下文档中进行了说明：
  
- [设置 Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
    
- [Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
    
- [ExpressRoute Overview](https://docs.microsoft.com/azure/expressroute/expressroute-introduction)
    
- [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/)
    
Setup and configurations that haven't followed the setup steps found in the documentation above can have different call flows than those we have documented here. Additionally, you may find yourself with configuration issues such as asymmetrical and non-optimal network routes, or non-optimal transport protocols. Asymmetrical routing is an important consideration whenever ExpressRoute is involved, because ExpressRoute introduces a second path to Office 365, which creates the possibility for a route that uses the Internet in one direction and another route that uses ExpressRoute in the other direction. 如果流量经过有状态防火墙，这可能会导致流量在返回方向被拦截。
  
## <a name="network-segments-and-traffic-types"></a>网络分段和流量类型

### <a name="network-segments"></a>网络分段

在介绍呼叫流之前，我们需要对某些术语进行定义，以帮助你了解 Skype for Business Online 中使用的网络分段和媒体类型。 
  
下面的呼叫流示意图列出了四种不同的网络分段，每种网络分段由不同的组织（你的内部网络、你的网络服务提供商及其 Internet 对等合作伙伴以及 Microsoft）进行管理并具有不同的性能特征。有关网络性能目标的指导原则，请参考 [Skype for Business Online 中的媒体质量和网络连接性能](media-quality-and-network-connectivity-performance.md)。
  
以下是我们将要讨论的各个网络分段。
  
![Call Flow Network Segments.](../images/25689bf2-4753-4bea-b8d7-88dc8b6d2e2a.png)
  
 **你的网络** 这是你控制和管理的整个网络中的一个网络分段。它包括办公室内部的有线或无线连接、办公楼之间的连接、与内部数据中心的连接以及与 Internet 提供商或 ExpressRoute 合作伙伴的连接。
  
Typically, the edge of your network has one or more DMZ with firewalls and/or proxy servers, which enforce your organization's security policies and that only allow certain network traffic that you have set up and configured. Because you manage this network, you have direct control over the performance of your network, and it is highly recommended that you complete network assessments to validate performance both within sites in your network and from your network to Skype for Business Online. 若要了解性能要求，请参阅 [Skype for Business Online 中的媒体质量和网络连接性能](media-quality-and-network-connectivity-performance.md)。
  
 **Internet** 该网络分段是你的整个网络的一部分，供从你的网络外部连接到 Skype for Business Online 的用户使用，并在未配置 ExpressRoute 时用于所有连接。Internet 及其所有连接均不受你或 Microsoft 管理，因此无法确定性能和路由路径，对总体呼叫流和质量的影响也最大。
  
 **ExpressRoute** 该网络分段是你的整个网络的一部分，可以提供与 Microsoft 网络的专用连接。 This is the recommended option for connecting your network to the Microsoft network (Office 365 datacenters) for all of the workloads that are dependent on network speed and performance, such as Skype for Business Online real-time communication. ExpressRoute connections are made between your network and the Microsoft network use [ExpressRoute connectivity providers](https://azure.microsoft.com/documentation/articles/expressroute-locations/) to provide a private and managed network, with 99.9% uptime and support for Quality of Service (QoS) that can improve performance for real-time media during periods of network congestion.
  
 **Microsoft 网络** 该网络分段是你的整个网络的一部分，它支持 Office 365 服务。 它包括用于 Office 365 的 Online 服务器之间的所有通信。 This may include traffic that traverses the Microsoft network backbone and is transmitted between geographical regions.
  
### <a name="types-of-traffic"></a>流量类型

The network traffic for Skype for Business Online falls into two broad categories, shown as separate paths in the call flow:
  
 **实时媒体** 是 RTP（实时传输协议）中封装的数据，支持音频、视频、应用程序共享以及文件传输工作负载。媒体流量通常对延迟非常敏感，因此你可能希望该流量尽量沿最直接的路径传输，并希望使用 UDP 作为传输层协议，因为使用 TCP 会增加延迟。
  
 **Signaling** is the communication link between the client and server, or other clients that are used to control activities (for example, when a call is initiated), and deliver IMs. 大多数信令流量使用 SIP 协议，但有些客户端使用基于 HTTP 的 REST 接口。 To make it simple, we are considering a variety signaling that may travel over HTTP and HTTPS or TLS connections in this type of traffic. 该流量对延迟不太敏感，但如果端点之间的延迟超过数秒钟，它可能会导致服务故障或呼叫超时，了解这一点非常重要。
  
有关该流量的目标，请参阅适用于所有 Office 365 服务的 [Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)。 每个 URL 会指示此部分流量是否可能通过用于 Office 365 的 ExpressRoute。 For diagrams that show that the Internet is still used for some traffic when ExpressRoute is enabled, please see [Azure ExpressRoute for Office 365](http://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd). It is important to understand that even URLs that are listed as being routable over ExpressRoute are also routable over the Internet. This means that in some scenarios, the determination about whether the Internet or ExpressRoute will be used depends on location of client and configuration of proxy servers and firewalls. It is also important to understand that since not all URLs associated with Office 365 are able to use ExpressRoute, an Internet connection is required even if you purchase ExpressRoute from an ExpressRoute partner. 
  
Traffic that can only be sent over the Internet includes common Internet dependencies, such as Certificate Revocation Lists (CRLs), DNS lookups and name resolution, URLs for shared Office 365 services, such as for the Office 365 admin center, and some non-real-time communication features of Skype for Business Online, such as telemetry and federation for interoperability with Skype consumer, as well media that is streamed for Skype Meeting Broadcast. 如果需要帮助你作出决定，请参阅[使用适用于 Office 365 的 ExpressRoute 进行路由](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)，了解规划网络路由时需要考虑的其他因素。
  
## <a name="principles-for-call-flows-with-skype-for-business"></a>Skype for Business 呼叫流的原理

深入了解特定呼叫流场景之前，有六个一般原则可帮助你了解 Skype for Business 呼叫流。
  
1. A Skype for Business conference is hosted in the same region where the conference organizer is homed. 如果会议组织者为 Online 用户，则会议托管在 Office 365 云中，而如果会议组织者为本地用户，则会议托管在本地数据中心。
    
2. 从客户端发送到托管会议的媒体流量总是传输到会议托管所在地的服务器。该服务器可以是你管理的数据中心中的本地服务器，也可以是 Office 365 云中的 Online 服务器。但是，对于 Online 会议，媒体流始终会使用边缘服务器。
    
3. 点对点呼叫的媒体流量采用最直接的可用路由。首选路由是直接连接远程对等机（客户端）的路由，但如果该路由因防火墙阻止流量或类似原因而不可用，则会利用一个或多个边缘服务器对流量进行中继。
    
4. 信令流量总是传输到用户所在地的服务器（Online 服务器或本地服务器）。如果无法直接连接前端服务器，则会使用一个边缘服务器。
    
5. 用户加入在 Online 中托管的会议时，总是会使用一个边缘服务器（或者在受客户端防火墙配置限制时使用两个边缘服务器）。
    
6. 用户加入在本地托管的会议时，如果从包含本地部署的同一个网络的内部进行连接，则通常不使用边缘服务器，但如果从你的网络的外部进行连接，则会使用一个或两个边缘服务器。 
    
若要了解选择的媒体路径的详细信息，请参阅 [ICE - 边缘媒体连接](https://aka.ms/AVEdge)。 Although this video is about Lync Server 2013, the principles and protocols still apply to Skype for Business.
  
## <a name="skype-for-business-call-flows-with-expressroute"></a>使用 ExpressRoute 的 Skype for Business 呼叫流

现在，您已经了解的四个不同的网段和一些一般的指导原则为 Skype 业务呼叫流，您可以使用信息以帮助您了解哪些 Skype 业务通信将遍历 ExpressRoute网络段。
  
如果一个端点位于你的网络内，另一个端点位于 Office 365 数据中心，则网络流量通常会通过 ExpressRoute 连接传输。这些网络流量包括客户端和服务器之间的信令流量、会议呼叫期间使用的媒体流量或使用在线边缘服务器的点对点呼叫。
  
如果两个端点可以跨 Internet 直接通信，或它们位于你的网络内部，则流量不会通过 ExpressRoute 连接传输。 This will include media for peer-to-peer calls, traffic from the Internet destined to an on-premises deployment, or any traffic between the Internet and Office 365 Edge Servers. 该场景的一个示例是用户从酒店加入 Online 会议。
  
## <a name="basic-skype-for-business-call-flow"></a>Skype for Business 基本呼叫流

为帮助你运用上文所述的有关 Skype for Business 呼叫流的一般原理，本文在下一节中列出了几个参考示意图。它并没有列出所有可能的呼叫流，只是为了帮助你运用上述原理。另外，示意图中所选择的场景涵盖了常见部署类型，包括 Online、Hybrid、Cloud Connector 以及 Skype 会议广播这个特殊用例。
  
> [!NOTE]
> [!注释] Skype for Business 使用的流量子集不可通过 ExpressRoute 进行路由，而是始终采用 Internet 路径。若要确定哪些 URL 会受到影响，请参阅 [Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)。
  
### <a name="peer-to-peer-call-for-office-365-users-from-within-customer-network"></a>Peer-to-peer call for Office 365 users from within customer network
<a name="bk_Figure2"> </a>

对于点对点呼叫，媒体流量总是采用最直接的路径传输到目标。但是，信令流量会传输到 Online 用户托管地的 Office 365 数据中心。由于两个用户位于同一个 WAN，并且客户端可以畅通无阻地直接通信，因此媒体会直接在用户之间流动。两个用户的信令流量会通过 ExpressRoute 连接传输到每个组织的数据中心。下图说明了此场景中的呼叫流。
  
 **点对点呼叫流**
  
![Call Flow with Peer to Peer call.](../images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)
  
### <a name="online-user-on-your-network-joining-a-conference-that-is-hosted-online"></a>你的网络中的 Online 用户加入托管在 Online 的会议
<a name="bk_Figure3"> </a>

In the peer-to-peer example, media traffic always takes the most direct route to its destination. However, for an Online conference, the destination is in the Office 365 cloud. 这意味着，从你的网络内部加入会议的所有用户的媒体流量，将通过 ExpressRoute 连接传输，而信令流量将传输到 Office 365 云。 下面的图形显示媒体和信号传输将遍历 ExpressRoute 连接您的网络内的用户，并将直接通过互联网的用户连接到您的网络之外的 Internet 如从喝杯咖啡商店或旅馆。
  
请记住，由会议组织者而非参与者定义会议的位置。这意味着如果会议已安排由内部客户，媒体通信通过 ExpressRoute，不会流到 Office 365 云但相反会给会议组织者的内部数据中心通过互联网。
  
Online 会议的媒体流量的传输目标是 Office 365 云内部的数据中心，但该数据中心可能与加入会议的用户位于不同的地理区域。这可能会在以下两种情况下出现：
  
- 如果会议组织者同与会者或参与者来自不同的公司，并且组织者所在的组织位于不同的地理位置或国家/地区。
    
- 如果加入会议的用户的所在地与公司组织所在的国家/地区不同，例如公司为跨国公司或加入会议的用户正在出差。
    
The good news about using ExpressRoute in this scenario is that with ExpressRoute premium add-on, data that follows the ExpressRoute path will pass automatically across Microsoft's backbone regardless of geographical region of the organizer of the meeting organization's datacenter.
  
 **Online 用户加入 Online 会议时的呼叫流**
  
![Call flow for an online hosted conference call.](../images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)
  
### <a name="joining-a-conference-hosted-by-on-premises-user-in-hybrid-deployment"></a>加入由 Hybrid 部署中的本地用户托管的会议
<a name="bk_Figure3"> </a>

请记住支持寄宿的会议会议服务器由会议组织者所在。在此方案中，加入会议安排由内部用户混合部署中的所有用户的媒体将流向的内部数据中心。将通过在 Office 365 云中，他们组织建立在线穴的用户信号，虽然媒体将尝试直接连接。在此方案中，因为这两个用户从连接您的网络内直接媒体连接是可行的所以 ExpressRoute 仅用于信号在线穴的用户的通信。如果联机的穴的用户从 Internet 连接，媒体可以遍历 ExpressRoute 如果在线边缘服务器用来连接。
  
 **Hybrid 用户托管的会议的呼叫流**
  
![Call flow hosted onprem.](../images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)
  
### <a name="on-premises-edge-server-with-office-365-hosted-conferences"></a>使用本地边缘服务器和 Office 365 托管会议
<a name="bk_Figure5"> </a>

混合用户连接联机主持会议，我们就知道信号和介质将被发往 Office 365 云，，因为该用户从 Internet 加入，通常直接互联网将采用路径。但是，在某些情况下，例如，由于防火墙限制，直接的 Internet 路径不可用。在这种情况下，内部部署边缘服务器可以将中继媒体通信，这将导致媒体通信到 Office 365 云遍历 ExpressRoute 电路之前返回到您的内部网络。
  
 **本地用户使用本地边缘服务器加入 Online 会议呼叫**
  
![Call flow for a conference call going through an edge server.](../images/0178c170-5837-430d-84f1-582784bfef55.png)
  
### <a name="pstn-call-using-skype-for-business-cloud-connector-edition"></a>使用 Skype for Business Cloud Connector Edition 的 PSTN 呼叫
<a name="bk_Figure6"> </a>

使用 [Skype for Business Online Cloud Connector Edition](https://aka.ms/CloudConnectorInstaller) 时，可通过将本地资源（例如 SIP Trunk、PSTN 网关）或最少硬件设备与 Skype for Business 集成来提供 PSTN 连接。 With Cloud Connector Edition, users are homed Online and act as normal Online users when they don't involve Calling Plans. PSTN 场景的信令会通过 ExpressRoute 连接（如可用）在客户端和云之间传输，而媒体流量会始终在 WAN 内传输。 在这种情况下，信令会在 Office 365 云处改变方向，并在 Cloud Connector 处终止。
  
 **在 Office 365 和云连接器电话系统通过 PSTN 呼叫**
  
![Call flow for a PSTN call using Cloud PBX Cloud Connector.](../images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)
  
### <a name="skype-meeting-broadcast-with-users-joining-from-customer-network"></a>用户从客户网络加入时的 Skype 会议广播
<a name="bk_Figure6"> </a>

Skype 会议广播是一种特殊用例，它由一个两部分会议组成，其中每部分都具有不同的网络传输特性。 The first part, and the one that is most important from a network performance point of view, is the inner meeting. 这是实时部分会议，其中包括一个或多个 Office 365 云中的会议服务器连接的客户端终结点。 Data transmitted using this portion of the meeting is exactly like the example above, with an Office 365 user joining and Online conference. 
  
Skype 会议广播的独特之处在于，会议将被分发到大量的会议与会者通过广播流服务。 流服务，此广播不路由是通过 ExpressRoute，但改为可选的内容传递网络 (CDN) 服务支持与使用互联网。 最好意识到广播流是一个单向的媒体流因为与会者听而不说和支持缓冲，使其对网络性能问题，如延迟、 数据包丢失和抖动得敏感。 而不被优化这些问题的广播的流量，它是带宽利用率的优化，因为可能是接收流式的媒体的与会者的数量非常大。
  
 **用户从客户网络加入时的 Skype 会议广播**
  
![Call flow for Skype Meeting Broadcast.](../images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)
  
## <a name="call-flow-patterns-by-deployment-type"></a>根据部署类型分类的呼叫流模式

与公共调用流示例上面，并控制通信模式的一般原则的了解，下面的表提供摘要，在部署和使用情况的大组合的通信模式。 这些表没有列出所有可能的呼叫流组合，但可以帮助你进一步了解呼叫流的一般原理。
  
数据传输和被列为本地的组织;它不能让客户网络、 Internet 或 ExpressRoute。 下面列出的模式基于最常用的网络设置，如防火墙、 联盟和互联网，并且假定多方或联合流程中涉及的所有组织都有 ExpressRoute。 在实践中，使用不同的设置可能会导致流量模式不同于下列流量模式。
  
### <a name="call-flows-for-skype-for-business-online"></a>Skype for Business Online 呼叫流

Skype 的在线业务的使用情况是指用户托管联机，并且可能会从您的内部网络或 Internet 中调用。的内部部署服务器不属于上述情形中，使所有会议或 PSTN 相关的媒体会都流动到 Office 365 云，以及边缘服务器还将在云中的在线用户。
  
 **Skype for Business Online 呼叫流汇总**
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**使用场景** <br/> |**端点** <br/> |**信令路径** <br/> |**媒体路径** <br/> |**示例流** <br/> |**说明** <br/> |
|点对点呼叫  <br/> |两个客户端，均位于你的网络中。  <br/> |ExpressRoute  <br/> |本地  <br/> |[Office 365 提供用户能够从客户网络中点到点调用](call-flow-using-expressroute.md#bk_Figure2) <br/> ||
|点对点呼叫  <br/> |两个客户端，另一个 （内部） 网络上其它客户端 Internet （外部） 上。  <br/> |内部用户：ExpressRoute  <br/> 外部用户：Internet  <br/> |内部用户：ExpressRoute  <br/> 外部用户：Internet 到 Office 365 边缘服务器。  <br/> |[Office 365 提供用户能够从客户网络中点到点调用](call-flow-using-expressroute.md#bk_Figure2) <br/> |假定该防火墙阻止客户端，需要在线边缘服务器之间的直接连接。从内部用户到在线边缘服务器通信遵循相似路径的电话会议的会议服务器。  <br/> |
|点对点呼叫联盟组织中的用户  <br/> |两个客户端，一个位于你的网络（内部），另一个位于联盟组织网络（联盟）中的 Online 用户。  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[你的网络中的 Online 用户加入托管在 Online 的会议](call-flow-using-expressroute.md#bk_Figure3) <br/> |假设防火墙拦截了客户端之间的直接连接，这时需要使用在线边缘服务器。从内部用户到在线边缘服务器的流量采用的路径与到会议呼叫的会议服务器的流量采用的路径相似。  <br/> |
|客户网络中的用户加入会议呼叫  <br/> |客户端位于你的网络，会议服务器位于 Office 365 云中。  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[你的网络中的 Online 用户加入托管在 Online 的会议](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|加入会议呼叫的用户在互联网连接  <br/> |客户端是在 Office 365 云的互联网和会议服务器上。  <br/> |Internet  <br/> |Internet  <br/> |[你的网络中的 Online 用户加入托管在 Online 的会议](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|加入其他公司的本地服务器托管的会议  <br/> |客户端位于你的网络，会议服务器位于第三方数据中心中。  <br/> |Internet  <br/> |Internet  <br/> |不适用  <br/> |由于托管会议的会议服务器位于另一个客户的本地网络中，因此数据不会通过 Microsoft 云进行传输。  <br/> |
|PSTN 呼叫  <br/> |在客户网络和电话系统在 Office 365 云中的服务器的客户端  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[你的网络中的 Online 用户加入托管在 Online 的会议](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|PSTN 呼叫  <br/> |在 Office 365 云互联网和电话系统的服务器上的客户端  <br/> |Internet  <br/> |Internet  <br/> |不适用  <br/> |媒体和信号会流到 Office 365 提供数据中心。由于客户端终结点是在 Internet 上，所有数据将都流经 Microsoft 数据中心到互联网 （即使在线边缘服务器时所需的连接）。  <br/> |
   
> [!NOTE]
> ExpressRoute 将在位于企业网络边缘联机服务器上，用户从媒体路径中使用，但如果使用另一个客户的内部部署边缘服务器不能使用。 
  
### <a name="call-flows-for-skype-for-business-hybrid"></a>Skype for Business Hybrid 呼叫流

Skype for Business 部署包含至少一部分本地托管用户时，将适用 Hybrid 呼叫流。 本节中的调用流包括两个内部会议和对等或 PSTN 与至少一个内部穴的用户调用。
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**使用场景** <br/> |**端点** <br/> |**信令路径** <br/> |**媒体路径** <br/> |**示例流** <br/> |**说明** <br/> |
|点对点呼叫  <br/> |两个客户端，一个位于客户网络，另一个在本地托管  <br/> |本地  <br/> |本地  <br/> |[Office 365 提供用户能够从客户网络中点到点调用](call-flow-using-expressroute.md#bk_Figure2) <br/> |由于用户为本地托管用户，因此信令将从本地传输到本地数据中心，而不是 Office 365 云。  <br/> |
|点对点呼叫  <br/> |两个客户端，均从客户网络进行连接。一个为 Online 托管，另一个为本地托管。  <br/> |Online 用户：ExpressRoute  <br/> 本地用户：本地  <br/> |本地  <br/> |[Office 365 提供用户能够从客户网络中点到点调用](call-flow-using-expressroute.md#bk_Figure2) <br/> |只有 Online 托管用户将信令流量发送到 Office 365 云。  <br/> |
|点对点呼叫联盟组织中的用户  <br/> |两个客户端，一个位于客户网络（内部）中的本地用户，另一个位于联盟公司的网络（联盟）中的 Online 用户。  <br/> |内部用户：本地  <br/> 联盟用户：ExpressRoute  <br/> |Internet 或 ExpressRoute（取决于使用 Online 还是本地边缘服务器）  <br/> |[参加的会议的是网络上的联机用户托管联机](call-flow-using-expressroute.md#bk_Figure3)和 （对于媒体通信）[与 Office 365 的内部部署边缘服务器主持会议](call-flow-using-expressroute.md#bk_Figure5)的组成部分。 <br/> |假定防火墙阻止要求在线边缘服务器的客户端之间的直接连接。冰协商将提供联机 （通过在线用户） 和内部边缘服务器 （通过内部用户） 进行连接。  <br/> |
|客户网络中的用户加入会议呼叫（Online 用户安排的会议）  <br/> |本地用户位于你的网络，会议服务器位于 Office 365 云中。  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[你的网络中的 Online 用户加入托管在 Online 的会议](call-flow-using-expressroute.md#bk_Figure3) <br/> |会议组织者定义会议呼叫的服务器资源。 在本例中，会议由 Online 用户安排，因此资源位于 Office 365 云中。  <br/> |
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

  
 