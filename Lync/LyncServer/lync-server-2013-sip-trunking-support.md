---
title: Lync Server 2013 SIP 中继支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SIP trunking support
ms:assetid: e3042831-e8d8-4ea2-baa2-1a697401ffa0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399005(v=OCS.15)
ms:contentKeyID: 48185714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2bdcf814a62bed4954c77be76bef32e1b6807ba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845862"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-support-in-lync-server-2013"></a>Lync Server 2013 中的 SIP 中继支持

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-03_

如果你计划将企业语音与 SIP 中继配合使用, 则必须部署中介服务器并确保其他基础结构和组件满足适合你的部署模型的支持要求。 有关确定是否要实现 SIP 中继的详细信息, 请参阅规划文档中[Lync Server 2013 中的 SIP 中继概述](lync-server-2013-overview-of-sip-trunking.md)。

你可以使用 Microsoft 统一通信开放式互操作性计划进行企业电话结构, 以查找合格的公共交换电话网络 (PSTN) 网关、IP-Pbx 和 SIP 中继服务, 包括合格的 IP 电话服务提供商。 有关详细信息, 请参阅 Microsoft 统一通信打开互操作性[http://go.microsoft.com/fwlink/p/?LinkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309)计划网站。

<div>

## <a name="mediation-server-support"></a>中介服务器支持

若要实现 SIP 中继, 必须通过中介服务器路由连接, 该服务器充当 Lync Server 2013 客户端和服务提供商之间的通信会话的代理。 中介服务器对来自客户端和服务器的媒体流量进行解码, 并在将其发送给服务提供商之前对其进行重新编码。 需要重新编码, 因为 SIP 中继不支持某些使用的编解码器, 例如用于防火墙遍历的实时音频 (RTA) 或交互式连接建立 (ICE) 协议协商。

每个中介服务器可以有两个网络适配器, 这两个适配器提供内部和外部网络接口。 外部接口通常称为网关接口, 因为它通常用于连接到 PSTN 网关或 IP PBX。 若要实现 SIP 主干, 请在服务提供商将外部接口连接到会话边界控制器 (SBC)。

</div>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a>集中 SIP 中继和分布式 SIP 中继

*集中*SIP 中继通过 Internet 协议 (VoIP) 通信 (包括分支站点流量) 路由您的数据中心中的所有语音。 集中部署模型简单、经济高效, 并且通常是在 Lync Server 2013 中实现 SIP 中继的首选方法。

根据你的企业中的使用模式, 你可能不希望通过集中 SIP 主干路由所有用户。 为分析您的需求，请回答以下问题：

  - 每个网站有多大？ 有多少用户？

  - 每个站点上的多条直接拨号 (已有) 号码可以获得最多的电话通话？

*分布式*SIP 中继是一种部署模型, 您可以在其中实现一个或多个分支站点上的本地 SIP 主干。 然后, VoIP 流量将从分支站点直接路由到其服务提供商, 而无需浏览您的数据中心。

仅在出现以下情况时才需要使用分布式 SIP 中继：

  - 分支站点需要 survivable 电话连接 (例如, WAN 停机)。 如果分支确实需要冗余和故障转移, 服务提供商将会收取更多费用, 并且配置将需要更长时间。 应针对每个分支站点对此进行分析。 某些分支可能需要冗余和故障转移, 而其他分支可能不需要。

  - 分支站点和数据中心位于不同的国家/地区。 出于兼容性和合法性考虑，每个国家/地区至少需要一个 SIP 中继。

确定是部署集中式 SIP 中继还是分布式 SIP 中继需要成本效益分析。 在某些情况下, 选择分布式部署模式可能会有好处, 即使不是必需的。 在完全集中的部署中, 所有分支站点流量均通过 WAN 链接进行路由。 如果您不想支付 WAN 链路所需的带宽费用，则可能需要使用分布式 SIP 中继。

<div>


> [!NOTE]  
> 有关为什么以及如何使用分布式 SIP 中继的详细信息, 请参阅规划文档中<A href="lync-server-2013-branch-site-sip-trunking.md">Lync Server 2013 中的分支站点 SIP 中继</A>。



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a>支持的 SIP 中继连接类型

Lync Server 2013 支持 SIP 中继的以下连接类型:

  - 多协议标签交换 (MPLS) 是一种专用网络，用于定向数据并将其从一个网络节点传送到下一个网络节点。 MPLS 网络中的带宽可与其他订阅者共享，并为每个数据包分配一个标签以便区别每个订阅者的数据。 此连接类型不需要 VPN。 潜在的缺点是过多的 IP 流量会干扰 VoIP 操作，除非为 VoIP 流量指定优先级。

  - 没有其他通信流的专用连接通常是最可靠且安全的连接类型 (例如, 租用光纤连接或 T1 线路)。 此连接类型提供了最高的通话能力, 但通常费用最高。 无需使用 VPN。 专用连接适用于具有大量呼叫或严格的安全和可用性要求的组织。

  - 公共 Internet 是最便宜的连接类型, 但也是最不可靠的, 并且具有最低的通话存储容量。 如果您的 Internet 电话服务提供商 (ITSP) 支持传输层安全 (TLS) 和安全实时传输协议 (SRTP) 以加密信号和媒体流量, 则您的 Internet 电话服务提供商 () 可以帮助保护此 SIP 中继连接类型。 如果无法通过 Internet 配置 SIP 中继连接以使用 TLS 和 SRTP, 我们强烈建议你使用 VPN 隧道提供更安全的连接。 请联系你的 ITSP 以确定它是否提供对 TLS 的支持 SRTP。

<div>

## <a name="selecting-a-connection-type"></a>选择连接类型

最适用于企业的 SIP 中继连接类型取决于企业的需求和预算。

  - 对于中等规模或更大的企业, MPLS 网络通常提供最大价值。 它能提供必需的带宽，且费率比专用网络更低。

  - 大型企业可能需要专用光纤或 T1 连接。

  - 对于呼叫量较少的小型企业版或分支站点, 通过互联网进行 SIP 中继可能是最佳选择。 但是, 不建议将此连接类型用于中等大小或更大的网站。

</div>

</div>

<div>

## <a name="codec-support"></a>编解码器支持

服务提供程序代理必须支持以下编解码器:

  - G.711 a-law（主要在北美以外的国家/地区使用）

  - G.711 μ-law（在北美使用）

</div>

</div>

<span> </span>

</div>

</div>

</div>

