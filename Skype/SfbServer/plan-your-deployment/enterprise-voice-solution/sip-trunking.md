---
title: Skype for Business 服务器中的 SIP 中继
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
description: 了解 Skype for Business 服务器中的 SIP 中继企业版语音
ms.openlocfilehash: 10d47b6a235ee45e68415db2ff9253fffe1e2697
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297370"
---
# <a name="sip-trunking-in-skype-for-business-server"></a>Skype for Business 服务器中的 SIP 中继

了解 Skype for Business 服务器中的 SIP 中继企业版语音

会话初始协议 (SIP) 用于启动和管理基本电话服务和其他实时通信服务（例如即时消息、会议、状态检测和多媒体）的 IP 语音 (VoIP) 通信会话。 本节提供实现 SIP 中继（一种 SIP 连接，可以扩展到本地网络以外）的规划信息。

## <a name="what-is-sip-trunking"></a>什么是 SIP 中继？

SIP 中继是一种 IP 连接，在您的组织与防火墙以外的 Internet 电话服务提供商 (ITSP) 之间建立 SIP 通信链路。 通常, SIP 主干用于将组织的中心网站连接到 ITSP。 在某些情况中，您也可以选择使用 SIP 中继将分支站点连接到 ITSP。

部署 SIP 中继可能是简化组织的电信以及准备最新的实时通信增强的一个重大步骤。 SIP 中继的主要优势之一是, 你可以将组织的连接合并到中心站点上的公共交换电话网络 (PSTN), 而不是其前置任务、时间段复用 (TDM) 中继, 这通常是需要来自每个分支站点的单独主干。

### <a name="cost-savings"></a>节省成本

可以大大节省与 SIP 中继有关的成本：

- 通过 SIP 中继拨打长途电话通常可以大幅降低成本。

- 可以节省可管理性成本并降低部署的复杂性。

- 如果可以以极低的成本将 SIP 中继直接连接到 ITSP，则可以消除基本速率接口 (BRI) 和主速率接口 (PRI) 的费用。在 TDM 中继中，服务提供商按分钟对呼叫计费。SIP 中继的成本可能基于带宽使用，能够以更小、更经济的增量购买带宽。（实际成本取决于选择的 ITSP 的服务模型。）

#### <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a>SIP 中继与承载 PSTN 网关或 IP-PBX

由于 SIP 中继直接连接到服务提供商，因此可以消除 PSTN 网关及其管理成本和复杂性。使用 SIP 中继可以减少维护和管理工作，从而大幅节省成本。

### <a name="expanded-voip-services"></a>扩展的 VoIP 服务

语音功能通常是部署 SIP 中继的主要动机，但是语音支持只是第一步。 使用 SIP 中继, 您可以扩展 VoIP 功能并启用 Skype for Business 服务器以提供一组更丰富的服务。 例如：

- 未运行 Skype for Business Server 的设备的增强状态检测功能可提供与移动电话的更好集成, 让你能够查看用户何时使用手机呼叫。

- E9-1 个紧急电话使拨打911呼叫的机构能够确定呼叫者在其电话号码中的位置。

> [!NOTE]
> 与 ITSP 联系以获取他们支持并且可以为贵组织启用的服务列表。

### <a name="sip-trunks-vs-direct-sip-connections"></a>SIP 中继与直接 SIP 连接

术语中继源自电路交换技术。 它指的是连接电话交换设备的专用物理线路。 与它们的前置任务、时间段复用 (TDM) 中继、SIP 中继是两个独立 SIP 网络 (Skype for business 服务器企业版和 ITSP) 之间的连接。 SIP 中继是可以通过任何支持的 SIP 中继连接类型建立的虚拟连接，这一点与电路交换中继不同。

而直接 SIP 连接指的是不能跨越本地网络边界的 SIP 连接（也就是说，它们连接到内部网络内的公用电话交换网 (PSTN) 网关或专用交换机 (PBX)）。 有关如何与 Skype for business 服务器配合使用直接 SIP 连接的详细信息, 请参阅[在 skype For Business 服务器中直接进行 sip 连接](direct-sip.md)。

## <a name="how-do-i-implement-sip-trunking"></a>如何实施 SIP 中继？

若要实现 SIP 中继, 必须通过中介服务器路由连接, 该服务器充当 Skype for Business 服务器客户端和服务提供商和 transcodes 媒体 (如有必要) 之间的通信会话的代理。

每个中介服务器都有一个内部网络接口和一个外部网络接口。 内部接口连接到前端服务器。 外部接口通常称为网关接口, 因为它传统上用于将中介服务器连接到公共交换电话网络 (PSTN) 网关或 IP PBX。 若要实现 SIP 主干, 请将中介服务器的外部接口连接到 ITSP 的外部边缘组件。 ITSP 的外部边缘组件可以是会话边界控制器 (SBC)、路由器或网关。

有关中介服务器的详细信息, 请参阅[Skype For Business 服务器中的中介服务器组件](mediation-server.md)。

### <a name="centralized-vs-distributed-sip-trunking"></a>集中 SIP 中继和分布式 SIP 中继

集中 SIP 中继通过您的中心站点路由所有 VoIP 通信, 包括分支站点流量。 集中部署模型简单、经济高效, 并且通常是使用 Skype for Business 服务器实现 SIP 中继的推荐方法。

分布式 SIP 中继是一种部署模型, 您可以在其中实现一个或多个分支站点上的本地 SIP 中继。 然后, VoIP 流量将从分支站点直接路由到服务提供商, 而无需通过中心站点。

仅在出现以下情况时才需要使用分布式 SIP 中继：

- 分支站点需要 survivable 电话连接 (例如, WAN 停机)。 应针对每个分支站点分析此要求;某些分支可能需要冗余和故障转移, 而其他分支可能不需要。

- 在两个中心站点之间需要弹性。 您需要确保 SIP 主干在每个中心站点终止。 例如, 如果您有都柏林和 Tukwila 中心网站, 并且两者都仅使用一个网站的 SIP 主干, 则如果主干中断, 则其他网站的用户将无法进行 PSTN 呼叫。

- 分支站点和中央站点位于不同的国家/地区。 出于兼容性和合法性考虑，每个国家/地区至少需要一个 SIP 中继。 例如，在欧盟，如果某个国家/地区的通信没有本地终止于中央点，则无法离开该国家/地区。

根据网站的地理位置和你的企业中预期的预期流量, 你可能不希望通过中心 SIP 主干路由所有用户, 或者你可以选择通过 SIP 主干在其分支站点路由某些用户。 为分析您的需求，请回答以下问题：

- 每个网站有多大 (即为企业语音启用的用户数)？

- 每个站点中哪个外线直拨分机 (DID) 号码收到的电话呼叫最多？

确定部署集中 SIP 中继还是分布式 SIP 中继之前需要进行成本效益分析。 某些情况下，虽然并不是必需的，但选择分布式部署模型可能会比较有益。 在完全集中的部署中, 所有分支站点流量均通过 WAN 链接进行路由。 如果您不想支付 WAN 链路所需的带宽费用，则可能需要使用分布式 SIP 中继。 例如, 你可能希望在具有中心网站的联合的分支站点上部署标准版服务器, 或者你可能希望使用小型网关部署 Survivable 分支设备或 Survivable 分支服务器。

> [!NOTE]
> 有关分布式 SIP 中继的详细信息, 请参阅[Skype For Business 服务器中的分支站点 SIP 中继](branch-site.md)。

### <a name="supported-sip-trunking-connection-types"></a>支持的 SIP 中继连接类型

Skype for Business 服务器支持 SIP 中继的以下连接类型:

- 多协议标签交换 (MPLS) 是一种专用网络，用于定向数据并将其从一个网络节点传送到下一个网络节点。 MPLS 网络中的带宽与其他订阅者共享, 并且为每个数据包分配了一个标签, 用于将一个订阅者的数据与另一个订阅者的数据区分开。 这种连接类型无需使用虚拟专用网 (VPN)。 潜在的缺点是过多的 IP 流量会干扰 VoIP 操作，除非为 VoIP 流量指定优先级。

- 没有其他流量的专用连接（例如，租用的光纤连接或 T1 线路）通常是最安全可靠的连接类型。此连接类型提供最大的呼叫传送容量，但通常也是最昂贵的。无需使用 VPN。专用连接适用于具有大量呼叫或严格的安全和可用性要求的组织。

- Internet 是成本最低的连接类型，但也是最不可靠的。 Internet 连接是唯一需要 VPN 的 Skype for business 服务器 SIP 中继连接类型。

#### <a name="selecting-a-connection-type"></a>选择连接类型

最适用于企业的 SIP 中继连接类型取决于企业的需求和预算。

- 对于大中型企业，MPLS 网络通常是最佳选择。它能提供必需的带宽，且费率比专用网络更低。

- 大型企业可能需要专用的光纤、T1、T3 或更高连接（在欧盟为 E1、E3 或更高）。

- 对于呼叫量较少的小型企业版或分支站点, 通过互联网进行 SIP 中继可能是最佳选择。 建议大中型站点不要使用此连接类型。

### <a name="bandwidth-requirements"></a>带宽要求

实现所要求的带宽量取决于呼叫容量（必须能够支持的并发呼叫数）。需考虑到带宽可用性，以便能够充分利用购买的峰值容量。使用以下公式计算 SIP 中继峰值带宽的要求：

SIP 中继峰值带宽 = 最大并发呼叫数 x（64 kbps + 标头大小）

> [!NOTE]
> 标头最大大小为 20 字节。

### <a name="codec-support"></a>编解码器支持

Skype for Business 服务器仅支持以下编解码器:

- G.711 a-law（主要在北美以外的国家/地区使用）

- G.711 μ-law（在北美使用）

### <a name="internet-telephony-service-provider"></a>Internet 电话服务提供商

SIP 中继连接的服务提供商端的实现方式因 ITSP 而异。 有关部署信息，请与服务提供商联系。 有关已认证的 SIP 中继服务提供商的列表, 请参阅[Microsoft 统一通信打开互操作性计划网站](https://go.microsoft.com/fwlink/p/?LinkId=287029)。

有关 Microsoft 认证的 SIP 中继提供商的详细信息，请与 Microsoft 代表联系。

> [!IMPORTANT]
> 您必须使用 Microsoft 认证的服务提供商，才能确保 ITSP 支持遍历 SIP 中继的所有功能（例如，设置和管理会话以及支持所有扩展 VoIP 服务）。Microsoft 技术支持没有扩展到使用非认证提供商的配置。如果当前使用的是未认证 SIP 中继的 Internet 服务提供商，您可以选择继续使用该提供商作为您的 ISP，同时使用 Microsoft 认证的 SIP 中继提供商。

### <a name="topologies-and-components-for-sip-trunking"></a>用于 SIP 中继的拓扑和组件

下图描绘了 Skype for Business 服务器中的 SIP 中继拓扑。

**SIP 中继拓扑**

![SIP 中继拓扑](../../media/669fb55d-7c81-4e21-9421-fabc43d6e064.jpg)

如图所示，企业网络与公用电话交换网 (PSTN) 服务提供商之间的连接使用 IP 虚拟专用网络 (VPN)。这个专用网络旨在提供 IP 连接、增强安全性和（可选的）获取服务质量 (QoS) 保证。由于 VPN 的特性，您无需为 SIP 信号流量使用传输层安全性 (TLS)，也无需为媒体流量使用安全实时传输协议 (SRTP)。因此，企业与服务提供商之间的连接由用于 SIP 的普通 TCP 连接以及用于通过 IP VPN 进行隧道传输的媒体的普通实时传输协议 (RTP)（通过 UDP）构成。确保 VPN 路由器之间的所有防火墙打开端口以允许 VPN 路由器进行通信，并且 VPN 路由器外部边缘上的 IP 地址公共可路由。

> [!IMPORTANT]
> 请与服务提供商联系，以确定是否提供包括故障转移在内的高可用性支持。 如果提供，则需要确定设置过程。 例如, 你只需要在每个中介服务器上配置一个 IP 地址和一个 SIP 中继, 还是需要在每个中介服务器上配置多个 SIP 中继？ > 如果你有多个中心网站, 还应询问服务提供商是否有能力启用与另一个中心站点的连接。

> [!NOTE]
> 对于 SIP 中继, 强烈建议你部署独立的中介服务器。 有关详细信息，请参阅部署文档中的 [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)。

### <a name="securing-the-mediation-server-for-sip-trunking"></a>为 SIP 中继保护中介服务器的安全

为安全起见，应为两个 VPN 路由器之间的每个连接设置一个虚拟 LAN (VLAN)。设置 VLAN 的实际过程因路由器制造商而异。请与路由器供应商联系以获取详细信息。

建议您遵循下列准则：

- 在外围网络 (也称为 DMZ、隔离区和屏蔽子网) 之间的中介服务器和 VPN 路由器之间设置虚拟 LAN (VLAN)。

- 不允许将广播数据包或多播数据包从路由器传输到 VLAN。

- 阻止将流量从路由器路由到除中介服务器之外的任何位置的任何路由规则。

如果使用 VPN 服务器，建议您遵循下列准则：

- 在 VPN 服务器和中介服务器之间设置 VLAN。

- 不允许将广播数据包或多播数据包从 VPN 服务器传输到 VLAN。

- 阻止将 VPN 服务器流量路由到除中介服务器之外的任何位置的任何路由规则。

- 使用基本路由封装 (GRE) 加密 VPN 上的数据。

## <a name="see-also"></a>另请参阅

[Skype for Business 服务器中的分支站点 SIP 中继](branch-site.md)

