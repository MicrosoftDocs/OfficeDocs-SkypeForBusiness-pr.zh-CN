---
title: Skype for Business Server 中的中介服务器组件
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
description: 了解 Skype for Business Server 中的中介服务器，包括其支持的拓扑及其与 M：N 中继、媒体旁路和呼叫允许控制的关系。
ms.openlocfilehash: ef95e03bb9cc604b50e0e417f8358f6d922a7819
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101348"
---
# <a name="mediation-server-component-in-skype-for-business-server"></a>Skype for Business Server 中的中介服务器组件
 
了解 Skype for Business Server 中的中介服务器，包括其支持的拓扑及其与 M：N 中继、媒体旁路和呼叫允许控制的关系。
  
若要部署企业语音，必须部署一个或多个中介服务器。 
  
中介服务器转换内部 企业语音 基础结构与公用电话交换网 (PSTN) 网关或会话初始协议 (SIP) 中继之间的信号。 在某些部署中，它还在这些点之间转换媒体本身。
  
在 Skype for Business Server 端，中介服务器侦听单个相互 TLS (MTLS) 地址。 在网关端，中介服务器侦听与中继关联的所有关联的侦听端口。 所有合格网关必须支持 TLS，但也可以启用 TCP。 不支持 TLS 的网关将支持 TCP。
  
如果环境中还有现有的公用交换机 (PBX) ，中介服务器将处理 企业语音 用户与 PBX 之间的呼叫。 如果您的 PBX 是 IP-PBX，您可以在 PBX 和中介服务器之间创建直接 SIP 连接。 如果您的 PBX 是 TDM 的时分多路 (PBX) ，则还必须在中介服务器和 PBX 之间部署 PSTN 网关。
  
默认情况下，中介服务器与前端服务器并排。 中介服务器还可以部署在独立池中。
  
## <a name="what-mediation-server-does"></a>中介服务器执行哪些操作

中介服务器的主要功能如下：
  
- 加密和解密 Skype for Business Server 端上的 SRTP。 
    
- 将不支持 TLS (TCP 上的 SIP 转换) 通过相互 TLS 转换为 SIP。
    
- 转换 Skype for Business Server 与中介服务器的对等网关之间的媒体流。
    
- 将网络外部的客户端连接到内部 ICE 组件，使媒体可以遍历 NAT 和防火墙。
    
- 充当网关不支持的呼叫流的中介，例如来自远程工作者的呼叫企业语音 clien.t
    
- 在包含 SIP 中继的部署中，与 SIP 中继服务提供商合作以提供 PSTN 支持，这样就无需 PSTN 网关。
    
下图显示了中介服务器在与基本 PSTN 网关和基础结构通信时所使用的信号和媒体企业语音协议。
  
**中介服务器使用的信号和媒体协议**

![中介服务器协议图](../../media/c3d39ba0-e323-4a58-8f07-4e80d3278af2.jpg)
  
> [!NOTE]
> 如果在 PSTN 网关和中介服务器之间的网络上使用 TCP 或 RTP/RTCP (而不是 SRTP 或 SRTCP) ，我们建议您采取措施来帮助确保网络的安全性和隐私性。 
  
## <a name="mn-trunk"></a>M:N 中继

Skype for Business Server 支持灵活定义中继以便进行呼叫路由。 中继是中介服务器和侦听端口号之间的逻辑关联，具有网关和侦听端口号。 这意味着有几个方面：中介服务器可以有多个中继到同一网关;中介服务器可以有多个到不同网关的中继;相反，网关可以有多个到不同中介服务器的中继。
  
使用拓扑生成器将网关添加到 Skype for Business 拓扑时，仍必须创建根中继。 给定中介服务器可以处理的网关数取决于服务器在高峰忙碌时段的处理能力。 如果在满足 Skype for Business Server 最低硬件要求的硬件上部署中介服务器（如 Server [requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)中所述，则独立的中介服务器可以处理大约 1000 个呼叫。 中介服务器执行代码转换，但仍为多个网关路由呼叫，即使这些网关不支持媒体旁路。
  
定义呼叫路由时，指定与该路由关联的中继，但不指定与该路由关联的中介服务器。 而是使用拓扑生成器将中继与中介服务器关联。 换句话说，路由确定用于呼叫的中继，随后会向与该中继关联的中介服务器发送该呼叫的信号。
  
中介服务器可以部署为池;此池可以与前端池并排，也可以部署为独立池。 当中介服务器与前端池并并时，池大小可能最多为 12 (注册器池大小限制) 。 综合起来，这些功能提高了中介服务器的可靠性和部署灵活性，但它们需要以下类似功能：
  
- **PSTN 网关。** Skype for Business Server 合格网关必须实现 DNS 负载平衡，这使合格的公用电话交换网 (PSTN) 网关可以充当中介服务器池的负载平衡器，从而在池中对呼叫进行负载平衡。
    
- **会话边界控制器。** 对于 SIP 中继，对等实体是 Internet 电话服务提供商 (SBC) 会话边界控制器。 在从中介服务器池到 SBC 的方向中，SBC 可以从该池中的任何中介服务器接收连接。 在从 SBC 到池的方向中，可以将流量发送到池中的任何中介服务器。 实现此目的的一个方法是通过 DNS 负载平衡（如果服务提供商和 SBC 支持）。 另一种选择是向服务提供商提供池中所有中介服务器的 IP 地址，服务提供商会在每个中介服务器的 SBC 中将 IP 地址作为单独的 SIP 中继进行设置。 然后，服务提供商将处理其自己的服务器的负载平衡。 并非所有服务提供商或 SDC 都支持这些功能。 此外，服务提供商可能需要为此功能收取额外的费用。 通常，每个到 SBC 的 SIP 中继都产生每月费用。
    
- **IP-PBX。** 在从中介服务器池到 IP-PBX SIP 终止的方向中，IP-PBX 可以接收来自池中任何中介服务器的连接。 在从 IP-PBX 到池的方向中，可以将流量发送到池中的任何中介服务器。 由于大多数IP-PBXs都不支持 DNS 负载平衡，因此建议将单个直接 SIP 连接从 IP-PBX 定义到池中的每个中介服务器。 然后，IP-PBX 会通过通过中继组分布流量来处理自己的负载平衡。 假定中继组在 IP-PBX 上具有一组一致的路由规则。 特定 IP-PBX 是否支持此中继组概念及其如何与 IP-PBX 自己的冗余和群集体系结构相交，需要先确定，然后才能决定中介服务器群集能否与 IP-PBX 正确交互。
    
中介服务器池必须具有与之交互的对等网关的统一视图。 这意味着，池的所有成员都从配置存储访问对等网关的相同定义，并同样有可能与对等网关进行交互进行传出呼叫。 因此，无法对池进行分段，以便某些中介服务器仅与某些网关对等方进行通信进行传出呼叫。 如果需要这种分段，则必须使用单独的中介服务器池。 例如，如果 PSTN 网关、SIP 中继或 IP-PBXs 中不存在本主题前面详述的与池交互的关联功能，则就是这种情况。
  
特定的 PSTN 网关、IP-PBX 或 SIP 中继对等方可以路由到多个中介服务器或中继。 特定中介服务器池可以控制的网关数取决于使用媒体旁路的呼叫数。 如果大量呼叫使用媒体旁路，则池中的中介服务器可以处理更多的呼叫，因为只需处理信号层。 
  
## <a name="call-admission-control-and-mediation-server"></a>呼叫允许控制和中介服务器

呼叫允许控制 (CAC) ，根据可用带宽管理实时会话建立，以帮助防止出现占用网络的用户的用户体验质量差 (QoE) 。 为了支持这一点，中介服务器负责对 Skype for Business Server 端和网关端上的两次交互进行带宽管理。 在呼叫允许控制中，呼叫的端接实体处理带宽预留。 中介服务器 (PSTN 网关、IP-PBX、SBC) 的对等网关不支持 Skype for Business Server 呼叫允许控制。 因此，中介服务器必须代表其对等网关处理带宽交互。 如果可能，中介服务器将提前预留带宽。 如果不可能（例如，如果网关端的最终媒体终结点位置对于发往对等网关的传出呼叫是未知的），则会在发出呼叫时预留带宽。 此行为可能导致带宽订阅过度，但这是防止错误响铃的唯一方法。
  
媒体旁路和带宽预留相互排斥。 如果对呼叫使用媒体旁路，则不针对该呼叫执行呼叫允许控制。 此处假定前提是此次呼叫不涉及具有限定带宽的链接。 如果呼叫允许控制用于涉及中介服务器的特定呼叫，则该呼叫不能使用媒体旁路。
  
有关媒体旁路或呼叫允许控制的详细信息，请参阅 Plan [for media bypass in Skype for Business](media-bypass.md)或 Plan for call admission control in Skype for Business [Server。](call-admission-control.md)
  
## <a name="enhanced-9-1-1-e9-1-1-and-mediation-server"></a>增强型 9-1-1 (E9-1-1) 和中介服务器

中介服务器扩展了某些功能，从而可以正确地与增强型 9-1-1 (E9-1-1) 服务提供商进行交互。 中介服务器上不需要任何特殊配置。 默认情况下，E9-1-1 交互所需的 SIP 扩展包括在中介服务器的 SIP 协议中，用于与对等网关 (PSTN 网关、IP-PBX 或 Internet 电话服务提供商的 SBC（包括 E9-1-1 服务提供商）) 
  
到 E9-1-1 服务提供商的 SIP 中继是可以在现有中介服务器池上终止，还是需要独立的中介服务器将取决于 E9-1-1 SBC 能否与中介服务器池进行交互。 有关详细信息，请参阅[M：N trunk in Skype for Business Server。](m-n-trunk.md)
  
## <a name="media-bypass-and-mediation-server"></a>媒体旁路和中介服务器

媒体旁路是 Skype for Business Server 的一项功能，它使管理员能够将呼叫路由配置为直接在用户终结点与公用电话交换网 (PSTN) 网关之间流动，而无需遍历中介服务器。 媒体旁路功能通过减少延迟、不必要的转换、可能的数据包丢失和潜在的故障点数来改进呼叫质量。 在没有中介服务器的远程站点通过具有限定带宽的一个或多个 WAN 链路连接到中央站点的情况下，媒体旁路功能通过使来自远程站点的客户端的媒体直接流动到其本地网关来降低带宽要求，而不必首先通过 WAN 链路流至中央站点上的中介服务器并流回。媒体处理的减少还补充了中介服务器控制多个网关的能力。
  
媒体旁路功能和呼叫允许控制 (CAC) 相互排斥。如果某次呼叫使用媒体旁路功能，则不会为此次呼叫执行 CAC。假定前提是此次呼叫不涉及具有限定带宽的链接。
  
## <a name="topologies-for-mediation-server"></a>中介服务器的拓扑

默认情况下，Skype for Business Server、中介服务器与 Standard Edition Server、前端池或 Survivable Branch Appliance 并并。 前端池中的所有中介服务器必须配置相同。
  
如果性能问题，最好在专用独立池中部署一台或多台中介服务器。 如果要部署 SIP 中继，我们强烈建议使用独立的池。 
  
如果将直接 SIP 连接部署到支持媒体旁路和 DNS 负载平衡的合格 PSTN 网关，则不需要独立的中介服务器池。 这是因为合格的网关能够将 DNS 负载平衡到中介服务器池，并且它们可以接收来自池中任何中介服务器的流量。
  
我们还建议您在部署 IP-PBXs 或连接到 Internet 电话服务提供商的会话边界控制器 (SBC) （只要满足以下任一条件）时，就将中介服务器并排在前端池上：
  
- IP-PBX 或 SBC 已配置为接收来自池中的任何中介服务器的通信，并且可将通信统一路由到池中的所有中介服务器。
    
- IP-PBX 不支持媒体旁路，但承载中介服务器的前端池可以处理不适用媒体旁路的呼叫的语音转码。
    
可以使用 Microsoft Lync Server 2013 规划工具评估要并并中介服务器的前端池是否可以处理负载。 如果您的环境不能满足这些要求，则必须部署独立的中介服务器池。
  
下图显示了由通过 WAN 链路连接的两个站点组成的简单拓扑。 中介服务器并位于站点 1 的前端池上。 站点 1 的中介服务器控制站点 1 的 PSTN 网关和站点 2 的网关。 在此拓扑中，已在全局范围内启用媒体旁路以使用站点和区域信息，并且到每个 PSTN 网关（GW1 和 GW2）的中继都已启用旁路。
  
**通过 WAN 链路与站点 1 的中介服务器和站点 2 的 PSTN 网关相连接的站点示例**

![具有中介服务器 WAN 网关的语音拓扑](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanGwy.jpg)
  
下图显示了一个简单的拓扑，其中中介服务器并位于站点 1 的前端池上，并且具有与站点 1 的 IP-PBX 的直接 SIP 连接。 在此图中，中介服务器还控制站点 2 的 PSTN 网关。 假设 Skype for Business 用户同时存在于站点 1 和站点 2 中。 还假定 IP-PBX 具有一个关联的媒体处理器，在发送到由 IP-PBX 控制的媒体终结点之前，来自 Skype for Business 终结点的所有媒体必须遍历该处理器。 在此拓扑中，已在全局范围内启用媒体旁路以使用站点和区域信息，并且到 PBX 和 PSTN 网关的中继已启用媒体旁路。
  
**通过 WAN 链路与站点 1 的中介服务器和站点 2 的 PBX 相连接的站点的示例**

![语音拓扑中介服务器 WAN PBX](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanPbx.jpg)
  
本主题中的最后一个图显示了中介服务器连接到 Internet 电话服务提供商的 SBC 的拓扑。 
  
## <a name="planning-decisions-for-mediation-server"></a>规划中介服务器的决策

本主题介绍为中介服务器部署需要做出的计划决策，
  
### <a name="collocated-or-stand-alone-mediation-server"></a>并站中介服务器还是独立中介服务器？

默认情况下，在中央站点上的 Standard Edition Server 或前端池中的前端服务器上并置中介服务器。 可处理的公用电话交换网 (PSTN) 呼叫数，池中所需的计算机数取决于以下各项：
  
- 中介服务器池控制对等网关的数量
    
- 通过这些网关的高流量时段
    
- 媒体绕过中介服务器的呼叫所占的百分比
    
规划时，请务必考虑未针对媒体旁路配置的 PSTN 呼叫和 A/V 会议的媒体处理要求，以及处理需要支持的忙时呼叫数的信号交互所需的处理。 如果没有足够的 CPU，则必须部署独立的中介服务器池;PSTN 网关、IP-PBX 和 SDC 需要拆分为子集，这些子集由一个池中的并站中介服务器和一个或多个独立池中独立的中介服务器控制。
  
如果部署的 PSTN 网关、IP-PBX 或会话边界控制器 (SDC) 不支持与中介服务器池交互的正确功能，包括以下这些，则需要将其与由单个中介服务器组成的独立池关联：
  
- 在池 (中的中介服务器之间执行域名系统 (DNS) 负载平衡，或者将流量统一路由到池中所有中介服务器) 
    
- 接受来自池中任意中介服务器的流量
    
可以使用 Microsoft Lync Server 2013 规划工具评估将中介服务器与前端池并排是否可以处理负载。 如果您的环境不能满足这些要求，则必须部署独立的中介服务器池。
  
### <a name="central-site-and-branch-site-considerations"></a>中央站点和分支站点注意事项

 中央站点的中介服务器可用于为分支站点的 IP-PBX 或 PSTN 网关路由呼叫。 但是，如果部署 SIP 中继，则必须在每个中继终止的站点上部署一台中介服务器。 使用中央站点的中介服务器为分支站点的 IP-PBX 或 PSTN 网关路由呼叫时，不需要使用媒体绕过。 但是，如果可以启用媒体旁路，这样做将减少媒体路径延迟并提高媒体质量，因为媒体路径不再需要遵循信号路径。 媒体旁路还可以降低池上的处理负载。
  
> [!NOTE]
> 媒体绕过将不会与每个 PSTN 网关、IP-PBX 和 SBC 进行交互操作。 Microsoft 已经与认证合作伙伴一起测试了一组 PSTN 网关和 SDC，并且已经使用 Cisco IP-PBX 进行了一些测试。 只有统一通信开放式互操作性计划 - Lync Server 中列出的产品和版本才支持 [媒体旁路](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)。 
  
如果要求具有分支站点恢复能力，则必须在分支站点部署 Survivable Branch Appliance 或部署前端服务器、中介服务器和网关的组合。  (分支站点恢复能力的假设是，状态和会议在站点中无法恢复。) 有关分支站点语音规划的指导，请参阅 Plan [for 企业语音 resiliency in Skype for Business Server。](enterprise-voice-resiliency.md)
  
对于与 IP-PBX 的交互，如果 IP-PBX 无法正确支持与多个早期对话的早期媒体交互和 RFC 3960 交互，则对于从 IP-PBX 到 Skype for Business 终结点的传入呼叫，可能会截断问候语的前几个单词。 如果中央站点上的中介服务器为 IP-PBX 路由呼叫，其中路由终止于分支站点，则此问题可能更严重，因为完成信号需要更多时间。 如果遇到此行为，在分支站点部署中介服务器是减少截断前几个单词的唯一方法。
  
最后，如果中央站点具有 TDM PBX，或者 IP-PBX 仍然需要 PSTN 网关，则必须在连接中介服务器和 PBX 的呼叫路由上部署网关。
  
> [!NOTE]
> 若要提高独立中介服务器的媒体性能，您应在这些服务器上网络适配器 (RSS) 启用接收端缩放。 通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。 有关详细信息，请参阅["Windows Server 中的接收端缩放增强功能"。](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11)) 若要详细了解如何启用 RSS，请参阅网络适配器文档。 
