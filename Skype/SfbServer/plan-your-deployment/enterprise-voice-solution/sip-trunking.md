---
title: Skype for Business Server 2015 中的 SIP 中继
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
description: 了解有关在 Skype 的 SIP 中继的业务 Server 企业语音
ms.openlocfilehash: 39300bfd518729cf99e41accfc64412bbcf4afb4
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="sip-trunking-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 SIP 中继
 
了解有关在 Skype 的 SIP 中继的业务 Server 企业语音
  
会话初始协议 (SIP) 用于启动和管理基本电话服务和其他实时通信服务（例如即时消息、会议、状态检测和多媒体）的 IP 语音 (VoIP) 通信会话。 此部分提供用于实现 SIP 中继，一种扩展到的本地网络边界以外的 SIP 连接的规划信息。
  
## <a name="what-is-sip-trunking"></a>什么是 SIP 中继？

SIP 中继是一种 IP 连接，在您的组织与防火墙以外的 Internet 电话服务提供商 (ITSP) 之间建立 SIP 通信链路。 通常，SIP 中继用于连接到 ITSP 的组织的中央站点。 在某些情况中，您也可以选择使用 SIP 中继将分支站点连接到 ITSP。
  
部署 SIP 中继可以 big 步简化您的组织的电信和准备实时通信的最新增强功能。 SIP 中继的主要优势之一是您可以整合贵组织的连接到公用电话交换网 (PSTN) 在中央站点，而不是其前置任务，时间部门多路复用 (TDM) 中继，这通常需要从每个分支站点的单独中继。
  
### <a name="cost-savings"></a>节省成本

可以大大节省与 SIP 中继有关的成本：
  
- 通过 SIP 中继拨打长途电话通常可以大幅降低成本。
    
- 可以节省可管理性成本并降低部署的复杂性。
    
- 如果可以以极低的成本将 SIP 中继直接连接到 ITSP，则可以消除基本速率接口 (BRI) 和主速率接口 (PRI) 的费用。在 TDM 中继中，服务提供商按分钟对呼叫计费。SIP 中继的成本可能基于带宽使用，能够以更小、更经济的增量购买带宽。（实际成本取决于选择的 ITSP 的服务模型。）
    
#### <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a>SIP 中继与承载 PSTN 网关或 IP-PBX

由于 SIP 中继直接连接到服务提供商，因此可以消除 PSTN 网关及其管理成本和复杂性。使用 SIP 中继可以减少维护和管理工作，从而大幅节省成本。 
  
### <a name="expanded-voip-services"></a>扩展的 VoIP 服务

语音功能通常是部署 SIP 中继的主要动机，但是语音支持只是第一步。 与 SIP 中继，您可以扩展的 VoIP 功能，并启用 Skype 业务服务器提供丰富的服务。 例如：
  
- 业务服务器未运行 Skype 的设备的增强的状态检测可以更好地与移动电话，您可以查看用户移动电话通话时启用集成。
    
- E9-1-1 紧急呼叫，应答 911 呼叫，以确定从他/她的电话号码的呼叫者的位置的机构。
    
> [!NOTE]
> 与 ITSP 联系以获取他们支持并且可以为贵组织启用的服务列表。 
  
### <a name="sip-trunks-vs-direct-sip-connections"></a>SIP 中继与直接 SIP 连接

术语中继源自电路交换技术。 它指的是连接电话交换设备的专用物理线路。 其前置任务，时分多路复用 (TDM) 中继，如 SIP 中继的两个单独的 SIP 网络之间的连接 — Business Server enterprise Skype 和 ITSP。 SIP 中继是可以通过任何支持的 SIP 中继连接类型建立的虚拟连接，这一点与电路交换中继不同。
  
而直接 SIP 连接指的是不能跨越本地网络边界的 SIP 连接（也就是说，它们连接到内部网络内的公用电话交换网 (PSTN) 网关或专用交换机 (PBX)）。 有关如何使用直接 SIP 连接使用 Skype 业务服务器的详细信息，请参阅[中的业务服务器 2015 Skype 的直接 SIP 连接](direct-sip.md)。 
  
## <a name="how-do-i-implement-sip-trunking"></a>如何实施 SIP 中继？

若要实现 SIP 中继，您必须路由通过中介服务器，充当业务 Server 客户端的 Skype 的服务提供商和必要媒体，必要时之间的通信会话代理服务器的连接。
  
每台中介服务器具有一个内部网络接口和外部网络接口。 内部接口连接到前端服务器。 因为它通常用于连接到公用电话交换网 (pstn) 网关或 IP PBX 的中介服务器的外部接口通常称为网关接口。 若要实现 SIP 中继，则中介服务器的外部接口连接到 ITSP 的外部边缘组件。 ITSP 的外部边缘组件可以是会话边界控制器 (SBC)、路由器或网关。
  
有关中介服务器的详细信息，请参阅[中的业务服务器 2015 Skype 的中介服务器组件](mediation-server.md)。 
  
### <a name="centralized-vs-distributed-sip-trunking"></a>集中 SIP 中继和分布式 SIP 中继

集中的 SIP 中继路由所有 VoIP 流量，包括分支站点流量，通过在中央站点。 集中的部署模型简单、 经济高效，并且通常是推荐用于实现业务服务器的 SIP 中继与 Skype 的方法。
  
分布式的 SIP 中继是您在其中实现在一个或多个分支站点的本地 SIP 中继的部署模型。 VoIP 流量是然后从分支站点直接路由到的服务提供商而不经由中央站点。
  
仅在出现以下情况时才需要使用分布式 SIP 中继： 
  
- 分支站点需要 survivable 电话连接 （例如，如果 WAN 不可用）。 应为每个分支站点; 分析这一要求分支的一些可能需要冗余和故障转移，而其他用户可能不。
    
- 恢复能力，则需要两个中央站点之间。 您需要确保 SIP 中继终止每个中央站点上。 例如，如果您具有都柏林和 Tukwila 中央站点，并同时使用只有一个站点 SIP 中继，如果中继不可用，其他站点的用户无法进行 PSTN 呼叫。
    
- 分支站点和中央站点是在不同的国家/地区。 出于兼容性和合法性考虑，每个国家/地区至少需要一个 SIP 中继。 例如，在欧盟，如果某个国家/地区的通信没有本地终止于中央点，则无法离开该国家/地区。
    
根据地理位置的网站和在企业内预计多少通信您可能不希望路由所有用户通过管理中心的 SIP 中继，或您可以选择将一些用户通过 SIP 中继都路由其分支站点。 为分析您的需求，请回答以下问题：
  
- （即，多少用户启用企业语音） 每个站点有多大？ 
    
- 每个站点中哪个外线直拨分机 (DID) 号码收到的电话呼叫最多？ 
    
确定部署集中 SIP 中继还是分布式 SIP 中继之前需要进行成本效益分析。 某些情况下，虽然并不是必需的，但选择分布式部署模型可能会比较有益。 在完全集中部署中，通过 WAN 链接路由所有分支站点流量。 如果您不想支付 WAN 链路所需的带宽费用，则可能需要使用分布式 SIP 中继。 例如，您可能想要将在分支站点使用联盟 Standard Edition server 部署到中心网站，或要部署 Survivable Branch Appliance 或 Survivable Branch Server 的小型网关。
  
> [!NOTE]
> 有关分布式 SIP 中继的详细信息，请参阅[中的业务服务器 2015 Skype 的分支站点 SIP 中继](branch-site.md)。 
  
### <a name="supported-sip-trunking-connection-types"></a>支持的 SIP 中继连接类型

Skype 业务服务器的 SIP 中继支持以下连接类型：
  
- 多协议标签交换 (MPLS) 是一种专用网络，用于定向数据并将其从一个网络节点传送到下一个网络节点。 MPLS 网络中的带宽为共享其他订阅者，并且每个数据包分配一个订阅者的数据分开其他人的标签。 这种连接类型无需使用虚拟专用网 (VPN)。 潜在的缺点是过多的 IP 流量会干扰 VoIP 操作，除非为 VoIP 流量指定优先级。
    
- 没有其他流量的专用连接（例如，租用的光纤连接或 T1 线路）通常是最安全可靠的连接类型。此连接类型提供最大的呼叫传送容量，但通常也是最昂贵的。无需使用 VPN。专用连接适用于具有大量呼叫或严格的安全和可用性要求的组织。
    
- Internet 是成本最低的连接类型，但也是最不可靠的。 Internet 连接的唯一 Skype 业务服务器 SIP 中继连接类型所需 VPN。
    
#### <a name="selecting-a-connection-type"></a>选择连接类型

最适用于企业的 SIP 中继连接类型取决于企业的需求和预算。
  
- 对于大中型企业，MPLS 网络通常是最佳选择。它能提供必需的带宽，且费率比专用网络更低。
    
- 大型企业可能需要专用的光纤、T1、T3 或更高连接（在欧盟为 E1、E3 或更高）。
    
- 对于小型企业或使用较低的呼叫量的分支站点，通过 Internet 的 SIP 中继可能是最佳选择。 建议大中型站点不要使用此连接类型。
    
### <a name="bandwidth-requirements"></a>带宽要求

实现所要求的带宽量取决于呼叫容量（必须能够支持的并发呼叫数）。需考虑到带宽可用性，以便能够充分利用购买的峰值容量。使用以下公式计算 SIP 中继峰值带宽的要求：
  
SIP 中继峰值带宽 = 最大并发呼叫数 x（64 kbps + 标头大小）
  
> [!NOTE]
> 标头最大大小为 20 字节。 
  
### <a name="codec-support"></a>编解码器支持

Skype 业务服务器仅支持以下编解码器：
  
- G.711 a-law（主要在北美以外的国家/地区使用）
    
- G.711 μ-law（在北美使用）
    
### <a name="internet-telephony-service-provider"></a>Internet 电话服务提供商

SIP 中继连接的服务提供商端的实现方式因 ITSP 而异。 有关部署信息，请与服务提供商联系。 有关认证的 SIP 中继服务提供商的列表，请参阅[Microsoft 统一通信开放互操作性计划网站](https://go.microsoft.com/fwlink/p/?LinkId=287029)。
  
有关 Microsoft 认证的 SIP 中继提供商的详细信息，请与 Microsoft 代表联系。
  
> [!IMPORTANT]
> 您必须使用 Microsoft 认证的服务提供商，才能确保 ITSP 支持遍历 SIP 中继的所有功能（例如，设置和管理会话以及支持所有扩展 VoIP 服务）。Microsoft 技术支持没有扩展到使用非认证提供商的配置。如果当前使用的是未认证 SIP 中继的 Internet 服务提供商，您可以选择继续使用该提供商作为您的 ISP，同时使用 Microsoft 认证的 SIP 中继提供商。 
  
### <a name="topologies-and-components-for-sip-trunking"></a>用于 SIP 中继的拓扑和组件

下图描绘业务服务器中 Skype 的 SIP 中继拓扑。
  
**SIP 中继拓扑**

![SIP 中继拓扑](../../media/669fb55d-7c81-4e21-9421-fabc43d6e064.jpg)
  
如图所示，企业网络与公用电话交换网 (PSTN) 服务提供商之间的连接使用 IP 虚拟专用网络 (VPN)。这个专用网络旨在提供 IP 连接、增强安全性和（可选的）获取服务质量 (QoS) 保证。由于 VPN 的特性，您无需为 SIP 信号流量使用传输层安全性 (TLS)，也无需为媒体流量使用安全实时传输协议 (SRTP)。因此，企业与服务提供商之间的连接由用于 SIP 的普通 TCP 连接以及用于通过 IP VPN 进行隧道传输的媒体的普通实时传输协议 (RTP)（通过 UDP）构成。确保 VPN 路由器之间的所有防火墙打开端口以允许 VPN 路由器进行通信，并且 VPN 路由器外部边缘上的 IP 地址公共可路由。
  
> [!IMPORTANT]
> 请与服务提供商联系，以确定是否提供包括故障转移在内的高可用性支持。 如果提供，则需要确定设置过程。 例如，您需要在每个中介服务器上，配置只有一个 IP 地址和一个 SIP 中继或是否需要在每台中介服务器上配置多个 SIP 中继？ > 如果您有多个中央站点，还可以询问服务提供商是否有能力启用与另一个中央站点的连接。 
  
> [!NOTE]
> SIP 中继，我们强烈建议您部署独立的中介服务器。 有关详细信息，请参阅部署文档中的[Deploying Mediation Servers and Defining Peers](http://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx) 。
  
### <a name="securing-the-mediation-server-for-sip-trunking"></a>为 SIP 中继保护中介服务器的安全

为安全起见，应为两个 VPN 路由器之间的每个连接设置一个虚拟 LAN (VLAN)。设置 VLAN 的实际过程因路由器制造商而异。请与路由器供应商联系以获取详细信息。
  
建议您遵循下列准则：
  
- 设置 up 虚拟 LAN (VLAN) 之间中介服务器和 VPN 路由器外围网络 （也称为 DMZ、 非军事区和屏蔽子网） 中。
    
- 不允许将广播数据包或多播数据包从路由器传输到 VLAN。
    
- 阻止所有将流量从路由器到 anywhere 路由的路由规则但中介服务器。
    
如果使用 VPN 服务器，建议您遵循下列准则：
  
- 设置 VPN 服务器和中介服务器之间的 VLAN。
    
- 不允许将广播数据包或多播数据包从 VPN 服务器传输到 VLAN。
    
- 阻止所有将 VPN 服务器流量路由到任何位置的路由规则但中介服务器。
    
- 使用基本路由封装 (GRE) 加密 VPN 上的数据。
    
## <a name="see-also"></a>另请参阅

#### 

[中的业务服务器 2015 Skype 的分支站点 SIP 中继](branch-site.md)

