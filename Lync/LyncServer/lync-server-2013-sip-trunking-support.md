---
title: Lync Server 2013 SIP 中继支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking support
ms:assetid: e3042831-e8d8-4ea2-baa2-1a697401ffa0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399005(v=OCS.15)
ms:contentKeyID: 48185714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fd2bd6d66b8b4f040e654f2412f86027071f9ac
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-support-in-lync-server-2013"></a>Lync Server 2013 中的 SIP 中继支持

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-03_

如果计划将企业语音与 SIP 中继结合使用，则必须部署中介服务器，并确保其他基础结构和组件满足部署模型的相应支持要求。 有关确定是否实现 SIP 中继的详细信息，请参阅规划文档中的[Lync Server 2013 中的 SIP 中继概述](lync-server-2013-overview-of-sip-trunking.md)。

您可以使用 Microsoft 统一通信开放式互操作性计划进行企业电话基础结构，以查找限定的公共交换电话网络（PSTN）网关、IP Pbx 和 SIP 中继服务，包括符合条件的 IP 电话服务提供商。 有关详细信息，请参阅 Microsoft 统一通信开放式互操作性[http://go.microsoft.com/fwlink/p/?LinkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309)计划网站，网址为。

<div>

## <a name="mediation-server-support"></a>中介服务器支持

若要实现 SIP 中继，必须通过中介服务器路由连接，该服务器充当 Lync Server 2013 客户端和服务提供商之间的通信会话的代理。 中介服务器对来自客户端和服务器的媒体流量进行解码，并在将其发送到服务提供程序之前对其进行重新编码。 重新编码是必需的，因为 SIP 中继不支持用于防火墙遍历的一些编解码器，如实时音频（RTA）或交互连接建立（ICE）协议协商。

每个中介服务器都可以有两个网络适配器，它们提供了内部和外部网络接口。 外部接口通常称为网关接口，因为传统情况下它用于连接到 PSTN 网关或 ip-pbx。 若要实现 SIP 中继，请将外部接口连接到服务提供商的会话边界控制器（SBC）。

</div>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a>集中 SIP 中继和分布式 SIP 中继

*集中*SIP 中继通过数据中心路由所有 Internet 协议（VoIP）通信，包括分支站点流量。 集中部署模型简单、经济高效，通常是使用 Lync Server 2013 实现 SIP 中继的首选方法。

根据企业中的使用模式，您可能不希望通过集中 SIP 中继路由所有用户。 为分析您的需求，请回答以下问题：

  - 每个站点有多大？ 有多少用户？

  - 每个站点上的哪些直接向内拨号（已）号码可以获得最多的电话呼叫？

*分布式*SIP 中继是一种部署模型，可在其中实现一个或多个分支站点的本地 SIP 中继。 然后，将 VoIP 流量从分支站点直接路由到其服务提供商，而无需遍历您的数据中心。

仅在出现以下情况时才需要使用分布式 SIP 中继：

  - 分支站点需要 survivable 电话连接（例如，如果 WAN 故障）。 如果分支确实需要冗余和故障转移，则服务提供商将会花费更多费用，配置将需要更长时间。 应针对每个分支站点对此进行分析。 某些分支可能需要冗余和故障转移，而其他分支可能不需要。

  - 分支站点和数据中心位于不同的国家/地区。 出于兼容性和合法性考虑，每个国家/地区至少需要一个 SIP 中继。

决定是部署集中式 SIP 中继还是分布式 SIP 中继需要进行成本效益分析。 在某些情况下，选择分布式部署模式可能会有好处，即使不是必需的也是如此。 在完全集中的部署中，所有分支站点流量都通过 WAN 链路进行路由。 如果您不想支付 WAN 链路所需的带宽费用，则可能需要使用分布式 SIP 中继。

<div>


> [!NOTE]  
> 有关您可能使用分布式 SIP 中继的原因和方式的详细信息，请参阅规划文档中的<A href="lync-server-2013-branch-site-sip-trunking.md">Lync Server 2013 中的分支站点 SIP 中继</A>。



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a>支持的 SIP 中继连接类型

Lync Server 2013 支持 SIP 中继的以下连接类型：

  - 多协议标签交换 (MPLS) 是一种专用网络，用于定向数据并将其从一个网络节点传送到下一个网络节点。 MPLS 网络中的带宽可与其他订阅者共享，并为每个数据包分配一个标签以便区别每个订阅者的数据。 此连接类型不需要 VPN。 潜在的缺点是过多的 IP 流量会干扰 VoIP 操作，除非为 VoIP 流量指定优先级。

  - 没有其他通信的专用连接通常是最可靠和安全的连接类型（例如，租用光纤连接或 T1 线路）。 此连接类型提供了最高的呼叫存储容量，但通常成本最高。 无需使用 VPN。 专用连接适用于具有大量呼叫或严格的安全和可用性要求的组织。

  - 公用 Internet 是开销最低的连接类型，但也是最不可靠的，并且具有最低的呼叫存储容量。 如果 Internet 电话服务提供商（ITSP）支持传输层安全性（TLS）和安全实时传输协议（SRTP）来加密信号和媒体流量，则您的 Internet 电话服务提供商（）可以帮助保护这种 SIP 中继连接类型。 如果无法通过 Internet 配置 SIP 中继连接以使用 TLS 和 SRTP，强烈建议您使用 VPN 隧道提供更安全的连接。 请联系你的 ITSP 以确定它是否提供对 TLS 的 SRTP 支持。

<div>

## <a name="selecting-a-connection-type"></a>选择连接类型

最适用于企业的 SIP 中继连接类型取决于企业的需求和预算。

  - 对于中等规模或更大的企业，MPLS 网络通常可提供最大价值。 它能提供必需的带宽，且费率比专用网络更低。

  - 大型企业可能需要专用光纤或 T1 连接。

  - 对于呼叫量较低的小型企业或分支站点，通过 Internet 的 SIP 中继可能是最佳选择。 但是，不建议将此连接类型用于中等规模或更大的网站。

</div>

</div>

<div>

## <a name="codec-support"></a>编解码器支持

服务提供程序代理必须支持以下编解码器：

  - G.711 a-law（主要在北美以外的国家/地区使用）

  - G.711 µ-law（在北美使用）

</div>

</div>

<span> </span>

</div>

</div>

</div>

