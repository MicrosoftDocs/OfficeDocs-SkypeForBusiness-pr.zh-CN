---
title: Skype for Business Server 2015 中的 SIP 中继
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
description: 了解有关在 Skype 的 SIP 中继业务服务器企业语音
ms.openlocfilehash: 434e013e2ee7d0d6736b39546ba7921aa15cdee3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="sip-trunking-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 SIP 中继
 
了解有关在 Skype 的 SIP 中继业务服务器企业语音
  
会话初始协议 (SIP) 用于启动和管理基本电话服务和其他实时通信服务（例如即时消息、会议、状态检测和多媒体）的 IP 语音 (VoIP) 通信会话。 本节提供用于实现 SIP 中继，一个类型的 SIP 连接超出本地网络的边界的计划信息。
  
## <a name="what-is-sip-trunking"></a>什么是 SIP 中继？

SIP 中继是一种 IP 连接，在您的组织与防火墙以外的 Internet 电话服务提供商 (ITSP) 之间建立 SIP 通信链路。 通常情况下，SIP 中继用于连接到 ITSP 的组织的中心站点。 在某些情况中，您也可以选择使用 SIP 中继将分支站点连接到 ITSP。
  
部署 SIP 中继可以简化您的组织的电信和实时通信的最新增强功能正在准备向方向迈出一大步。 SIP 中继的主要优点之一是您可以整合您的组织连接到中心站点，而不是它的前置任务，时间分多路复用技术 (TDM) 中继、 公用交换的电话网络 (PSTN) 的一般需要从每个分支站点单独干线。
  
### <a name="cost-savings"></a>节省成本

可以大大节省与 SIP 中继有关的成本：
  
- 通过 SIP 中继拨打长途电话通常可以大幅降低成本。
    
- 可以节省可管理性成本并降低部署的复杂性。
    
- 如果可以以极低的成本将 SIP 中继直接连接到 ITSP，则可以消除基本速率接口 (BRI) 和主速率接口 (PRI) 的费用。在 TDM 中继中，服务提供商按分钟对呼叫计费。SIP 中继的成本可能基于带宽使用，能够以更小、更经济的增量购买带宽。（实际成本取决于选择的 ITSP 的服务模型。）
    
#### <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a>SIP 中继与承载 PSTN 网关或 IP-PBX

由于 SIP 中继直接连接到服务提供商，因此可以消除 PSTN 网关及其管理成本和复杂性。使用 SIP 中继可以减少维护和管理工作，从而大幅节省成本。 
  
### <a name="expanded-voip-services"></a>扩展的 VoIP 服务

语音功能通常是部署 SIP 中继的主要动机，但是语音支持只是第一步。 通过 SIP 中继、 可以扩展 VoIP 功能并启用 Skype 业务服务器，以提供更丰富的服务。 例如：
  
- 增强的状态显示为业务服务器未运行 Skype 的设备检测可以提供更好的集成，与移动电话，使得您可以查看当用户在移动电话上。
    
- E9-1-1 紧急电话使机构人员应答呼叫 911，以确定他或她的电话号码呼叫者的位置。
    
> [!NOTE]
> 与 ITSP 联系以获取他们支持并且可以为贵组织启用的服务列表。 
  
### <a name="sip-trunks-vs-direct-sip-connections"></a>SIP 中继与直接 SIP 连接

术语干线由电路交换技术。 它指的是连接电话交换设备的专用物理线路。 像其父辈处理器，时间分割多路技术 (TDM) 中继 SIP 中继是两个单独的 SIP 网络之间的连接 — — 业务服务器的企业 Skype 和 ITSP。 SIP 中继是可以通过任何支持的 SIP 中继连接类型建立的虚拟连接，这一点与电路交换中继不同。
  
而直接 SIP 连接指的是不能跨越本地网络边界的 SIP 连接（也就是说，它们连接到内部网络内的公用电话交换网 (PSTN) 网关或专用交换机 (PBX)）。 有关如何使用 SIP 连接直接与 Skype 业务服务器的详细信息，请参阅[在 Skype 的业务服务器 2015年直接 SIP 连接](direct-sip.md)。 
  
## <a name="how-do-i-implement-sip-trunking"></a>如何实施 SIP 中继？

若要实现 SIP 中继，必须将路由通过中介服务器，该通信会话之间 Skype 业务服务器客户端和服务提供商和 transcodes 媒体，在必要时充当代理服务器的连接。
  
每个中介服务器的内部网络接口和外部网络接口。 内部接口连接到前端服务器。 因为它通常用于连接到公共交换的电话网络 (PSTN) 网关或 IP PBX 的中介服务器的外部接口通常称为网关接口。 若要实现 SIP 中继，则连接到 ITSP 的外部边缘部分中介服务器的外部接口。 ITSP 的外部边缘组件可以是会话边界控制器 (SBC)、路由器或网关。
  
中介服务器的详细信息，请参阅[中业务服务器 2015年的 Skype 的中介服务器组件](mediation-server.md)。 
  
### <a name="centralized-vs-distributed-sip-trunking"></a>集中 SIP 中继和分布式 SIP 中继

集中式的 SIP 中继路由所有的 VoIP 通信，包括通过中央网站分支站点通信。 集中的部署模型简单、 经济高效、 而且通常推荐用于实现业务服务器的 SIP 中继与 Skype 的方法。
  
分布式的 SIP 中继是在哪个实现在一个或多个分支站点的本地 SIP 中继的部署模型。 VoIP 流量是然后从分支站点直接路由到服务提供商而不需要通过中心站点。
  
仅在出现以下情况时才需要使用分布式 SIP 中继： 
  
- 分支站点要求高存活力的电话连接 （例如，如果 WAN 出现故障）。 这一要求应分析对于每个分支站点;一些分支可能需要冗余和故障切换，而其他人可能不会。
    
- 可恢复性是两个中心站点之间所必需的。 您需要确保在每个中心站点，终止 SIP 中继。 例如，如果您有都柏林和 Tukwila 的中心站点，并且都使用一个站点的 SIP 中继主干断开时，该站点的用户无法进行 PSTN 呼叫。
    
- 分支站点和中心站点位于不同的国家/地区。 出于兼容性和合法性考虑，每个国家/地区至少需要一个 SIP 中继。 例如，在欧盟，如果某个国家/地区的通信没有本地终止于中央点，则无法离开该国家/地区。
    
这取决于站点和您的企业内预计多少通信量可能不希望所有用户通过中央 SIP 中继都路由或您可能会选择一些用户通过 SIP 中继都路由及其分支地点的地理位置。 为分析您的需求，请回答以下问题：
  
- 每个站点 （即，用户数为企业语音启用） 有多大？ 
    
- 每个站点中哪个外线直拨分机 (DID) 号码收到的电话呼叫最多？ 
    
确定部署集中 SIP 中继还是分布式 SIP 中继之前需要进行成本效益分析。 某些情况下，虽然并不是必需的，但选择分布式部署模型可能会比较有益。 在完全集中式的部署中，所有的分支站点通信路由通过 WAN 链接。 如果您不想支付 WAN 链路所需的带宽费用，则可能需要使用分布式 SIP 中继。 例如，您可能想要将标准版服务器在与联盟分支站点部署到中心站点，或者您可能想要部署高存活力的分支装置或与小网关自动恢复分支服务器。
  
> [!NOTE]
> 分布式的 SIP 中继的详细信息，请参见[分支站点中的业务服务器 2015 Skype 的 SIP 中继](branch-site.md)。 
  
### <a name="supported-sip-trunking-connection-types"></a>支持的 SIP 中继连接类型

Skype 业务服务器的 SIP 中继支持下列连接类型：
  
- 多协议标签交换 (MPLS) 是一种专用网络，用于定向数据并将其从一个网络节点传送到下一个网络节点。 在 MPLS 网络中的带宽共享与其它订阅服务器，以及每个数据包分配一个标签，以将一个订阅服务器上的数据与其他人区分开来。 这种连接类型无需使用虚拟专用网 (VPN)。 潜在的缺点是过多的 IP 流量会干扰 VoIP 操作，除非为 VoIP 流量指定优先级。
    
- 没有其他流量的专用连接（例如，租用的光纤连接或 T1 线路）通常是最安全可靠的连接类型。此连接类型提供最大的呼叫传送容量，但通常也是最昂贵的。无需使用 VPN。专用连接适用于具有大量呼叫或严格的安全和可用性要求的组织。
    
- Internet 是成本最低的连接类型，但也是最不可靠的。 互联网连接是唯一 Skype 业务服务器的 SIP 中继连接类型需要 VPN。
    
#### <a name="selecting-a-connection-type"></a>选择连接类型

最适用于企业的 SIP 中继连接类型取决于企业的需求和预算。
  
- 对于大中型企业，MPLS 网络通常是最佳选择。它能提供必需的带宽，且费率比专用网络更低。
    
- 大型企业可能需要专用的光纤、T1、T3 或更高连接（在欧盟为 E1、E3 或更高）。
    
- 对于小型企业或具有低的话务量的分支站点，通过互联网的 SIP 中继可能是最佳的选择。 建议大中型站点不要使用此连接类型。
    
### <a name="bandwidth-requirements"></a>带宽要求

实现所要求的带宽量取决于呼叫容量（必须能够支持的并发呼叫数）。需考虑到带宽可用性，以便能够充分利用购买的峰值容量。使用以下公式计算 SIP 中继峰值带宽的要求：
  
SIP 中继峰值带宽 = 最大并发呼叫数 x（64 kbps + 标头大小）
  
> [!NOTE]
> 标头最大大小为 20 字节。 
  
### <a name="codec-support"></a>编解码器支持

Skype 业务服务器的支持只有下列编码解码器：
  
- G.711 a-law（主要在北美以外的国家/地区使用）
    
- G.711 μ-law（在北美使用）
    
### <a name="internet-telephony-service-provider"></a>Internet 电话服务提供商

SIP 中继连接的服务提供商端的实现方式因 ITSP 而异。 有关部署信息，请与服务提供商联系。 经认证的 SIP 中继服务提供商的列表，请参阅[Microsoft 统一通信开放互操作性计划网站](https://go.microsoft.com/fwlink/p/?LinkId=287029)。
  
有关 Microsoft 认证的 SIP 中继提供商的详细信息，请与 Microsoft 代表联系。
  
> [!IMPORTANT]
> 您必须使用 Microsoft 认证的服务提供商，才能确保 ITSP 支持遍历 SIP 中继的所有功能（例如，设置和管理会话以及支持所有扩展 VoIP 服务）。Microsoft 技术支持没有扩展到使用非认证提供商的配置。如果当前使用的是未认证 SIP 中继的 Internet 服务提供商，您可以选择继续使用该提供商作为您的 ISP，同时使用 Microsoft 认证的 SIP 中继提供商。 
  
### <a name="topologies-and-components-for-sip-trunking"></a>用于 SIP 中继的拓扑和组件

下图描绘为业务服务器在 Skype 的 SIP 中继拓扑。
  
**SIP 中继拓扑**

![SIP 中继拓扑](../../media/669fb55d-7c81-4e21-9421-fabc43d6e064.jpg)
  
如图所示，企业网络与公用电话交换网 (PSTN) 服务提供商之间的连接使用 IP 虚拟专用网络 (VPN)。这个专用网络旨在提供 IP 连接、增强安全性和（可选的）获取服务质量 (QoS) 保证。由于 VPN 的特性，您无需为 SIP 信号流量使用传输层安全性 (TLS)，也无需为媒体流量使用安全实时传输协议 (SRTP)。因此，企业与服务提供商之间的连接由用于 SIP 的普通 TCP 连接以及用于通过 IP VPN 进行隧道传输的媒体的普通实时传输协议 (RTP)（通过 UDP）构成。确保 VPN 路由器之间的所有防火墙打开端口以允许 VPN 路由器进行通信，并且 VPN 路由器外部边缘上的 IP 地址公共可路由。
  
> [!IMPORTANT]
> 请与服务提供商联系，以确定是否提供包括故障转移在内的高可用性支持。 如果提供，则需要确定设置过程。 例如，您需要配置每个中介服务器，只有一个 IP 地址和一个 SIP 中继或您是否需要在每个中介服务器上配置多个 SIP 中继？ > 如果您有多个中心站点，还要求服务提供商是否具有启用与另一个中心站点的连接的能力。 
  
> [!NOTE]
> 为 SIP 中继，强烈建议您部署独立的中介服务器。 有关详细信息，请参阅部署文档中的[部署中介服务器和定义对等](http://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)。
  
### <a name="securing-the-mediation-server-for-sip-trunking"></a>为 SIP 中继保护中介服务器的安全

为安全起见，应为两个 VPN 路由器之间的每个连接设置一个虚拟 LAN (VLAN)。设置 VLAN 的实际过程因路由器制造商而异。请与路由器供应商联系以获取详细信息。
  
建议您遵循下列准则：
  
- 设置了虚拟 LAN (VLAN) 中介服务器和外围网络 （也称为 DMZ、 非军事区和屏蔽子网） 中的 VPN 路由器之间。
    
- 不允许将广播数据包或多播数据包从路由器传输到 VLAN。
    
- 阻止任何路由到任何地方从路由器通信的路由规则，但中介服务器。
    
如果使用 VPN 服务器，建议您遵循下列准则：
  
- 设置 VLAN 之间的 VPN 服务器和中介服务器。
    
- 不允许将广播数据包或多播数据包从 VPN 服务器传输到 VLAN。
    
- 阻止将 VPN 服务器的通信路由到任何地方的任何路由规则，但中介服务器。
    
- 使用基本路由封装 (GRE) 加密 VPN 上的数据。
    
## <a name="see-also"></a>另请参阅

#### 

[在业务服务器 2015年的 Skype 的分支站点 SIP 中继](branch-site.md)

