---
title: Lync Server 2013 网络基础结构要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network infrastructure requirements
ms:assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425841(v=OCS.15)
ms:contentKeyID: 48183804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3571dba317998af4fe19f7d2dfd1677d3691f278
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217108"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="network-infrastructure-requirements-for-lync-server-2013"></a>Lync Server 2013 的网络基础结构要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-18_

Lync Server 2013 拓扑中每台服务器的网络适配器卡必须至少支持1千兆位/秒（Gbps）。 通常情况下，应使用低延迟和高带宽局域网（LAN）连接 Lync Server 拓扑中的所有服务器角色。 LAN 的大小取决于拓扑的大小：

  - 在标准版拓扑中，服务器应位于支持 1 Gbps 以太网或等效项的网络中。

  - 在前端池拓扑中，大多数服务器应位于支持超过 1 Gbps 的网络中，尤其是在支持音频/视频（A/V）会议和应用程序共享时。

对于公用电话交换网 (PSTN) 集成，可以使用 T1/E1 线路或 SIP 中继进行集成。

<div>

## <a name="audiovideo-network-requirements"></a>音频/视频网络要求

Lync Server 部署中的音频/视频（A/V）的网络要求包括以下各项：

  - 如果要使用 DNS 负载平衡部署单个边缘服务器或边缘池，则可以将外部防火墙配置为 NAT。 不能配置内部防火墙作为 NAT。 有关这些要求的详细信息，请参阅规划文档中的[确定 Lync Server 2013 的外部 A/V 防火墙和端口要求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果你有一个边缘池，并且使用的是硬件负载平衡器，则必须在每台边缘服务器上使用公用 IP 地址，并且无法将 NAT 用于您的 NAT 设备（例如，防火墙或将 NAT inbou 的其他基础结构设备）中的池。nd 或出站通信）。 有关详细信息，请参阅规划外部用户访问文档中的在<A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Lync Server 2013 中的端口摘要-扩展的合并边缘和硬件负载平衡</A>器。

    
    </div>

  - 如果您的组织使用了服务质量 (QoS) 基础结构，则媒体子系统应设计为在此现有基础结构中工作。

  - 如果使用 Internet 协议安全性 (IPsec)，建议在用于 A/V 流量的端口范围内禁用 IPsec。 有关详细信息，请参阅规划文档中的[Lync Server 2013 中的 IPsec 例外](lync-server-2013-ipsec-exceptions.md)。

要确保最佳媒体质量，请执行以下操作：

  - 设置网络链接，使之在高峰使用时段支持每个音频流 65 千位每秒 (Kbps) 和每个视频流（如果启用）500 Kbps 的吞吐量。一个双向音频或视频会话由两个流构成。

  - 为了处理此级别以上流量中的意外峰值并随着时间的推移而提高使用率，Lync Server 媒体终结点可适应不同的网络条件，并支持加载三倍于音频和视频的吞吐量（请参阅上一段），同时仍保留可接受的质量。 但是，不要认为这种适应性能支持未充分设置的网络。 在预配网络中，Lync Server 媒体终结点能够动态处理各种网络情况（例如，暂时的数据包丢失），这种能力会降低。

  - 如果网络链路的设置成本很高，而且难于操作，可能就需要考虑设置较低的流量。 在这种情况下，让 Lync Server 媒体终结点的弹性能够吸收流量量与峰值流量水平之间的差异，以降低语音质量的成本为代价。 此外，可用于吸收流量中的突发峰值的空间也会减少。

  - 对于短期内无法正确配置的链路（例如 WAN 链路很差的站点），考虑对某些用户禁用视频。

  - 配置网络，确保在高峰负载下的最大端到端延迟为 150 毫秒 (ms)。 延迟是 Lync Server 媒体组件无法降低的网络障碍，查找和消除薄弱点很重要。

  - 对于运行防病毒软件的服务器，请在例外列表中包括运行 Lync Server 的所有服务器，以便提供最佳性能和音频质量。

</div>

<div>

## <a name="conferencing-network-requirements"></a>会议网络要求

用于从 Internet 信息服务（IIS）服务器下载会议内容的带宽取决于上载的内容的大小。

</div>

</div>

<span> </span>

</div>

</div>

</div>

