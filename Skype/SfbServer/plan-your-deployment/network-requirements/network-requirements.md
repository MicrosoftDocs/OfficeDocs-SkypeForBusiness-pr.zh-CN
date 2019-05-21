---
title: Plan network requirements for Skype for Business
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
ms.assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
description: '摘要: 在实施 Skype for Business 服务器之前, 请查看下面的网络组件注意事项。'
ms.openlocfilehash: 56e8b00a4b662d19fd928b439ae8fafb7bcbdb3d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297034"
---
# <a name="plan-network-requirements-for-skype-for-business"></a>Plan network requirements for Skype for Business

**摘要:** 在实施 Skype for Business 服务器之前, 请查看下面的网络组件注意事项。

这些主题中的信息还将在包含其他详细信息和深度[的 Lync Server 的白皮书网络规划、监视和疑难解答](https://www.microsoft.com/en-us/download/details.aspx?id=39084)中进行讨论。 虽然内容显式引用 Lync 2010 和 Lync 2013, 但 Skype for business 服务器的注意事项保持不变。

同样, 如果你的网络涉及 wi-fi 和有线访问, 则[通过 Wi-fi 提供 Lync 2013 实时通信](https://www.microsoft.com/en-us/download/details.aspx?id=36494)的白皮书是一个很好的参考, 同样适用于 Skype For business 服务器。

<!-- Deprecated tools
Network performance and needs are directly linked to the traffic load placed on them. When planning your network and server implementations we recommend making use of the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md), the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md), and the [Skype for Business Server 2015 Stress and Performance Tool](../../management-tools/stress-and-performance-tool/stress-and-performance-tool.md).    -->

## <a name="server-hardware"></a>服务器硬件
<a name="S_hard"> </a>

Skype for Business 服务器拓扑中每台服务器的网络适配器必须支持至少1千兆位/秒 (Gbps)。 通常, 你应使用低延迟和高带宽局域网 (LAN) 连接 Skype for Business 服务器拓扑中的所有服务器角色。 LAN 的大小取决于拓扑的大小：

- 在标准版拓扑中, 服务器应位于支持 1 Gbps 以太网或等效的网络中。

- 在企业版拓扑中, 大多数服务器应位于支持超过 1 Gbps 的网络中, 尤其是在支持音频/视频 (A/V) 会议和应用程序共享时。

对于公用电话交换网 (PSTN) 集成，可以使用 T1/E1 线路或 SIP 中继进行集成。

## <a name="audiovideo-network-requirements"></a>音频/视频网络要求
<a name="AV_req"> </a>

Skype for business Server 部署中音频/视频 (A/V) 的网络要求如下所示:

- 如果使用 DNS 负载平衡部署单个边缘服务器或边缘池, 则可以将_外部_防火墙配置为执行网络地址转换 (NAT)。 您无法配置_internal_防火墙以执行 NAT。 有关详细信息, 请参阅[端口和防火墙规划](../edge-server-deployments/edge-environmental-requirements.md#port-and-firewall-planning)。

    > [!IMPORTANT]
    > 如果你有一个 Edge 池, 并且正在使用硬件负载平衡器, 则必须在 Edge 服务器上使用公共 IP 地址, 并且不能在支持 NAT 的设备 (例如, 防火墙装置或 LAN 交换机) 上使用 NAT。 有关详细信息, 请参阅[Skype For Business 服务器中的边缘服务器方案](../edge-server-deployments/scenarios.md)。

- 如果您的组织使用了服务质量 (QoS) 基础结构，则媒体子系统应设计为在此现有基础结构中工作。

- 如果使用 Internet 协议安全性 (IPsec)，建议在用于 A/V 流量的端口范围内禁用 IPsec。 有关详细信息, 请参阅[IPsec 例外](#ipsec-exceptions)。

要提供最佳媒体质量，请执行以下操作：

- 设置网络链接，使之在高峰使用时段支持每个音频流 65 千位每秒 (Kbps) 和每个视频流（如果启用）500 Kbps 的吞吐量。 双向音频或视频会话使用两个流，因此简单的音频/电话连接需要 130Kbps 才能覆盖每个流。 同样, 视频还使用 1000 Kbps 的总速率来传输上游和下游连接。

- 为了处理流量中的意外峰值和延长使用时间, Skype for Business 服务器媒体终结点可以适应不同的网络条件, 并支持三倍于音频和视频的吞吐量, 同时仍保持可接受的质量。 不要认为这种适应性能够掩盖未充分设置的网络中的问题。 在预配网络中, Skype for business 服务器媒体终结点的功能可动态处理不同的网络条件 (例如, 临时数据包丢失)。

- 如果网络链路的设置成本很高，而且难于操作，可能就需要考虑设置较低的流量。 在这种情况下, 让 Skype for Business 服务器媒体终结点的 elasticity 能够吸收流量音量和峰值流量级别之间的差异, 降低语音质量的成本。 此外，可用于吸收流量中的突发峰值的空间也会减少。

- 对于短期内无法正确设置的链路（例如 WAN 链路很差的站点），考虑对某些用户禁用视频。

- 配置网络，确保在高峰负载下的最大端到端延迟为 150 毫秒 (ms)。 延迟是指 Skype for business 服务器媒体组件无法减少的网络有障碍, 查找和消除这些薄弱点非常重要。

- 对于运行防病毒软件的服务器, 请在例外列表中包括运行 Skype for Business 服务器的所有服务器, 以提供最佳性能和音频质量。

## <a name="ipsec-exceptions"></a>IPsec 例外

对于 Internet 协议安全 (IPsec) (请参阅 IETF RFC 4301-4309) 已部署的企业网络, 必须在用于传送音频、视频和全景视频的端口范围内禁用 IPsec。 提出此建议的动机是需要避免由于 IPsec 协商而在分配媒体端口时产生任何延迟。

下表介绍了建议采用的 IPsec 例外设置。

**建议采用的 IPsec 例外**

|规则名称 |源 IP |目标 IP |协议 |源端口 |目标端口 |身份验证要求 |
|:--- |:--- |:--- |:--- |:---|:---|:--- |
|A/V 边缘服务器内部入站|任意  |A/V 边缘服务器内部|UDP 和 TCP|任何 |任何 |不进行身份验证|
|A/V 边缘服务器外部入站|任意  |A/V 边缘服务器外部|UDP 和 TCP|任何 |任何 |不进行身份验证|
|A/V 边缘服务器内部出站|A/V 边缘服务器内部  |A/V 边缘服务器外部 |UDP 和 TCP|任何 |任何 |不进行身份验证|
|A/V 边缘服务器外部出站|A/V 边缘服务器外部 |任意 |UDP 和 TCP|任何 |任何 |不进行身份验证|
|中介服务器入站|任意  |中介服务器 |UDP 和 TCP|任何 |任何 |不进行身份验证|
|中介服务器出站|中介服务器  |任意|UDP 和 TCP|任何 |任何 |不进行身份验证|
|会议助理入站|任意  |运行会议助理的前端服务器 |UDP 和 TCP|任何 |任何 |不进行身份验证|
|会议助理出站|运行会议助理的前端服务器  |任意|UDP 和 TCP|任何 |任何 |不进行身份验证|
|A/V 会议入站|任意|前端服务器|UDP 和 TCP|任何 |任何 |不进行身份验证|
|A/V 会议出站|前端服务器|任意|UDP 和 TCP|任何 |任何 |不进行身份验证|
|Exchange 入站|任意|Exchange 统一消息|UDP 和 TCP|任何 |任何 |不进行身份验证|
|应用程序共享服务器入站|任意|应用程序共享服务器|UDP 和 TCP|任何 |任何 |不进行身份验证|
|应用程序共享服务器出站|应用程序共享服务器| 任意 |UDP 和 TCP|任何 |任何 |不进行身份验证|
|Exchange 出站|Exchange 统一消息|任意|UDP 和 TCP|任何 |任何 |不进行身份验证|
|客户端| 任意  |任何|UDP 和 TCP|任何 |任何 |不进行身份验证|
|         |         |         |         |         |         |         |


## <a name="conferencing-network-requirements"></a>会议网络要求
<a name="Conf_req"> </a>

从 Internet 信息服务 (IIS) 服务器下载会议内容所用的带宽取决于内容的大小。 您可以选择监控实际使用情况并对带宽计划作出相应的调整。

## <a name="network-bandwidth-requirements-for-media-traffic"></a>媒体流量的网络带宽要求
<a name="Conf_req"> </a>

网络规划的一个重要部分是确保你的网络能够处理由 Skype for Business 服务器生成的媒体流量。 本节帮助您规划媒体流量。

### <a name="media-traffic-network-usage"></a>媒体流量网络使用情况
<a name="Net_req"> </a>

媒体流量带宽使用量可能由于不同变量（如编解码器使用、分辨率和活动级别）的数量而难于计算。 带宽使用量是使用的编解码器和流活动的一种功能，这两者在不同的方案中各不相同。 下表列出了 Skype for Business Server 方案中通常使用的音频编解码器。

**音频编解码器带宽**

|**音频编解码器**|**应用场景**|**音频负载比特率 (KBPS)**|**仅限于带宽音频负载和 IP 标头 (Kbps)**|**带宽音频负载、IP 标头、UDP、RTP 和 SRTP (Kbps)**|**带宽音频负载、IP 标头、UDP、RTP、SRTP 和前向纠错 (Kbps)**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|RTAudio 宽带  <br/> |对等  <br/> |29.0  <br/> |45.0  <br/> |57.0  <br/> |86.0  <br/> |
|RTAudio 窄带  <br/> |对等 PSTN  <br/> |11.8  <br/> |27.8  <br/> |39.8  <br/> |51.6  <br/> |
|G.722  <br/> |会议  <br/> |64.0  <br/> |80.0  <br/> |95.6  <br/> |159.6  <br/> |
|G.722 立体声  <br/> |对等会议  <br/> |128.0  <br/> |144.0  <br/> |159.6  <br/> |223.6  <br/> |
|G.711  <br/> |PSTN，会议  <br/> |64.0  <br/> |80.0  <br/> |92.0  <br/> |156.0  <br/> |
|Siren  <br/> |会议  <br/> |16.0  <br/> |32.0  <br/> |47.6  <br/> |63.6  <br/> |
|SILK 宽带  <br/> |对等  <br/> |36.0  <br/> |52.0  <br/> |64.0  <br/> |100.0  <br/> |
|SILK 宽带  <br/> |对等  <br/> |26.0  <br/> |42.0  <br/> |54.0  <br/> |80.0  <br/> |
|SILK 宽带  <br/> |对等  <br/> |20.0  <br/> |36.0  <br/> |48.0  <br/> |68.0  <br/> |
|绞宽带/narrowband  <br/> |对等  <br/> |13.0  <br/> |29.0  <br/> |41.0  <br/> |54.0  <br/> |

> [!NOTE]
> 来自 Skype for Business 客户端的 PSTN 呼叫通常使用711编解码器, 这需要高带宽。 如果该编解码器的带宽不足, 则呼叫可能会失败, 并显示类似于媒体日志中的以下错误:**必须至少启用一个编解码器, hr: c0042004**。 媒体日志 (如博客文件) 已加密, 并且只能由 Microsoft 支持人员解码。

上表中的带宽数值基于 Siren 和 G.722 编解码器的 20 毫秒数据分包（每秒 50 个数据包），其中包含其他安全实时传输协议 (SRTP) 开销（在会议方案中），并假定流是 100% 活动的。如果链接上出现数据包丢失，则会以动态方式使用前向纠错 (FEC) 以帮助维护音频流的质量。

G.722 编解码器的立体声版本由基于 Lync Room System 的系统使用，Lync Room System 使用一个立体声麦克风或一对单声道麦克风以允许收听者更好地辨别会议室中的多个讲话人。

**视频分辨率带宽**

|**视频编解码器**|**分辨率和纵横比**|**最大视频负载比特率 (Kbps)**|**最小视频负载比特率 (Kbps)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |320x180 (16:9)  <br/> 212x160 (4:3)  <br/> |250  <br/> |岁  <br/> |
|H.264/RTVideo  <br/> |424x240 (16:9)  <br/> 320x240 (4:3)  <br/> |350  <br/> |100  <br/> |
|H.264  <br/> |480x270 (16:9)  <br/> 424x320 (4:3)  <br/> |450  <br/> |200  <br/> |
|H.264/RTVideo  <br/> |640x360 (16:9)  <br/> 640x480 (4:3)  <br/> |800  <br/> |300  <br/> |
|H.264  <br/> |848x480 (16:9)  <br/> |1500  <br/> |400  <br/> |
|H.264  <br/> |960x540 (16:9)  <br/> |2000  <br/> |500  <br/> |
|H.264/RTVideo  <br/> |1280x720 (16:9)  <br/> |2500  <br/> |700  <br/> |
|H.264  <br/> |1920x1080 (16:9)  <br/> |4000  <br/> |1500  <br/> |
|H.264/RTVideo  <br/> |960x144 (20:3)  <br/> |500  <br/> |岁  <br/> |
|H.264  <br/> |1280x192 (20:3)  <br/> |1000  <br/> |250  <br/> |
|H.264  <br/> |1920x288 (20:3)  <br/> |2000  <br/> |500  <br/> |

视频的默认编解码器为 H.264/MPEG-4 Part 10 高级视频编码标准及其可扩展的用于临时可扩展性的视频编码扩展。 为保持与旧客户端的互操作, RTVideo 编解码器仍用于 Skype for Business 服务器与旧客户端之间的对等调用。 在 Skype for business 服务器和旧式客户端的会议会话中, Skype for business 服务器终结点可能会使用视频编解码器对视频进行编码, 并向 Skype for business 服务器客户端和 RTVideo bitstream 发送 bitstream 到旧版台.

所需的带宽取决于分辨率、质量、帧速率和图像中的运动或变化量。每种分辨率都有两个相关的比特率：

- **最大负载比特率**这是终结点将在最大帧速率下用于解析的比特率。 此值可实现最高的视频和音频质量。

- **最小负载比特率**这是 Skype for Business 服务器终结点将切换到下一个较低分辨率的比特率。 为了保证特定分辨率，可用的视频负载比特率不得低于该分辨率的此最低比特率。 利用此值，您可以了解在最大比特率不可用或不切实际时可能实现的最低值。 对于部分用户，此低比特率视频体验可能被视为无法接受的视频体验，因此在考虑使用这些最低视频负载比特率时应十分谨慎。 请注意，对于静态无变化的视频场景，实际比特率可能会暂时低于此最小比特率。

Skype for Business 服务器支持许多分辨率。 这允许 Skype for Business 服务器调整到不同的网络带宽和接收客户端功能。 Skype for Business Server 的默认纵横比为16:9。 对于不允许在16:9 纵横比中捕获的网络摄像头, 仍支持旧版4:3 纵横比。

使用视频负载比特率时，其中始终包含视频 FEC，因此，无论使用或不使用视频 FEC，值都相同。

终结点不会持续流出音频或视频数据包。根据不同的方案，流活动的级别也不同，这些级别指示为流发送数据包的频率。流活动取决于媒体和方案，而不依赖使用的编解码器。在对等方案中：

- 仅当用户通话时终结点才发送音频流。

- 参与双方都会接收到音频流。

- 如果使用视频，则双方终结点都会在呼叫过程中发送和接收视频流。

- 对于静态视频场景，实际比特率可能会暂时变得很低，因为视频编解码器将跳过编码视频区域的步骤，从前一示例起不作任何更改。

在会议方案中：

- 仅当用户通话时终结点才发送音频流。

- 所有参与者都会接收到音频流。

- 如果使用视频，则所有参与者最多将收到 5 个接收视频流和 1 个全景（例如，纵横比 20:3）视频流。 默认情况下，5 个接收视频流是基于当前发言人历史记录的，但用户还可手动选择要从其接收视频流的参与者。 如果启用多视频，则每个视频流的分辨率和带宽要求将更低。

- 每个打开用户发送视频流的参与者都将发送一个或多个视频流。 Skype for Business 服务器可以发送多达五个视频流, 以优化所有接收客户端的视频质量。 将发送的视频流的实际数量由发送方根据 CPU 容量、可用上行链路带宽和请求特定视频流的接收客户端的数量确定。 最常见的情况是，在旧客户端加入会议的情况下发送 1 个 H.264 和 1 个 RTVideo 视频流。 另一常见方案是，发送若干 H.264 视频流（例如，使用不同视频分辨率）以适应不同的接收方请求。

除音频和视频媒体的实时传输协议 (RTP) 流量所需的带宽之外，实时传输控制协议 (RTCP) 也需要带宽。RTCP 用于报告 RTP 流的统计信息和带外控制。规划时，请使用下表中的带宽数值规划 RTCP 流量。这些值代表用于 RTCP 的最大带宽，并且因控制数据不同，音频流和视频流的这些值也有所不同。

**RTCP 带宽**

|**Media**|**RTCP 最大带宽 (Kbps)**|
|:-----|:-----|
|音频  <br/> |5  <br/> |
|视频（仅正在发送/接收的 H.264 或 RTVideo）  <br/> |10  <br/> |
|视频（正在发送/接收的 H.264 和 RTVideo）  <br/> |岁  <br/> |

出于容量规划的目的，以下两项统计数据十分重要：

- **不带 FEC 的最大带宽**流将占用的最大带宽。 这包括流的典型活动和在没有 FEC 的情况下使用的典型编解码器。 这是当流处于 100% 活动且没有数据包丢失触发 FEC 使用时的带宽。 这在计算必须分配多少带宽以允许在给定方案中使用编解码器时非常有用。 FEC 不应是托管网络的要求。

- **FEC 的最大带宽**流使用的最大带宽。 这包括流的典型活动和在 FEC 方案中使用的典型编解码器。 这是流达到 100% 活动时的带宽, 有数据包丢失触发使用 FEC 以提高质量。 这对于计算必须分配多少带宽以允许在给定方案中使用编解码器, 并允许使用 FEC 在数据包丢失情况下保留质量, 这一点非常有用。

下表中还列出了另一个带宽值，**典型带宽**。 这是流使用的平均带宽。 这包括方案中的典型流活动和使用的典型编解码器。 此带宽可用于估计在给定时间媒体流量使用的带宽量，但不应用于容量规划，因为活动级别高于平均水平时，个别呼叫会超过该值。 下表中的典型视频流带宽基于在测得的客户数据中观察到的不同视频分辨率的组合，较小的安装具备的实际数量可能与表中数据不同。 例如, 在对等会话中, 大多数用户将使用默认视频呈现窗口, 而某些部分的用户会增加或最大化 Skype for Business 服务器应用程序, 以获得更佳的视频分辨率。

下表提供了适用于不同方案的值。

**对等会话的音频/视频容量规划**

|**Media**|**编解码器**|**典型流带宽 (Kbps)**|**不使用 FEC 的最大流带宽**|**使用 FEC 的最大流带宽**|
|:-----|:-----|:-----|:-----|:-----|
|音频  <br/> |RTAudio 宽带  <br/> |39.8  <br/> |62  <br/> |91  <br/> |
|音频  <br/> |RTAudio 窄带  <br/> |29.3  <br/> |44.8  <br/> |56.6  <br/> |
|音频  <br/> |SILK 宽带  <br/> |44.3  <br/> |69  <br/> |105  <br/> |
|呼叫 Skype for Business 服务器终结点时的主视频  <br/> |H.264  <br/> |460  <br/> |4010（用于最大分辨率 1920x1080）  <br/> |已包含  <br/> |
|呼叫 Lync 2010 或 Office Communicator 2007 R2 终结点时的主视频  <br/> |RTVideo  <br/> |460  <br/> |2510（用于最大分辨率 1280x720）  <br/> |已包含  <br/> |
|呼叫 Skype for business 服务器终结点时的全景视频  <br/> |H.264  <br/> |190  <br/> |2010（用于最大分辨率 1920x288）  <br/> |已包含  <br/> |
|呼叫 Lync 2010 终结点时的全景视频  <br/> |RTVideo  <br/> |190  <br/> |510（用于最大分辨率 960x144）  <br/> |已包含  <br/> |

**会议的音频/视频容量规划**

|**Media**|**典型的编解码器**|**典型流带宽 (Kbps)**|**不使用 FEC 的最大流带宽**|**使用 FEC 的最大流带宽**|
|:-----|:-----|:-----|:-----|:-----|
|音频  <br/> |G.722  <br/> |46.1  <br/> |100.6  <br/> |164.6  <br/> |
|音频  <br/> |Siren  <br/> |25.5  <br/> |52.6  <br/> |68.6  <br/> |
|主视频接收  <br/> |H.264 和 RTVideo¹  <br/> |260  <br/> |8015  <br/> |不适用  <br/> |
|主视频发送  <br/> |H.264 和 RTVideo  <br/> |270  <br/> |8015  <br/> |不适用  <br/> |
|全景视频接收  <br/> |H.264 和 RTVideo  <br/> |190  <br/> |2010（用于最大分辨率 1920x288）  <br/> |不适用  <br/> |
|全景视频发送  <br/> |H.264 和 RTVideo  <br/> |190  <br/> |2515 ²  <br/> |不适用  <br/> |

1. 当 Lync 2010 客户端连接到会议时, 除 H-p 外, 还会发送 RT 视频。

2. 如果有多个流, 它们将动态共享分配的带宽。

对于主视频，典型流带宽是用于所有收到的视频流的聚合带宽，最大流是用于所有发送视频流的带宽。即使对于多个视频流，典型视频带宽也小于对等方案，因为很多视频会议使用了内容共享，这会导致视频窗口小很多，从而使视频分辨率更低。例如，如果存在两个传入 1920x1080p 视频流，则将使用的发送和接收流二者支持的最大聚合视频负载带宽为 8000 Kbps。在实际实施中，很少看到最大值。

当构建使用库视图功能的多方会议时, 在参与者加入时带宽利用率最初会增加, 然后随着分辨率的下降而降低, 以适应最大限制。

||**2 个参与者**|**3 个参与者**|**4 个参与者**|**5 个参与者**|**6 个参与者**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**接收的最大分辨率** <br/> |1920x1080  <br/> |1280x720  <br/> |640x360  <br/> |640x360 320x240  <br/> |640x360 320x240  <br/> |
|**总平均比特率** <br/> |2128  <br/> |4050  <br/> |1304  <br/> |1224  <br/> |1565  <br/> |
|**总最大比特率** <br/> |4063  <br/> |5890  <br/> |2860  <br/> |2699  <br/> |3017  <br/> |

全景视频的典型流带宽基于仅可传输最高为 960x144 的全景视频的设备。在使用具备 1920x288 全景视频的设备时，预计典型流带宽会提升。

**PSTN 的音频容量规划**

|**Media**|**典型的编解码器**|**典型流带宽 (Kbps)**|**不使用 FEC 的最大流带宽**|**使用 FEC 的最大流带宽**|
|:-----|:-----|:-----|:-----|:-----|
|音频  <br/> |G. 711 (这包括会议中的 PSTN 参与者)  <br/> |64.8  <br/> |97  <br/> |161  <br/> |
|音频  <br/> |RTAudio 窄带  <br/> |30.9  <br/> |44.8  <br/> |56.6  <br/> |

这些表中的网络带宽数值仅代表单向流量，其中包括分配给每个流的 5 Kbps 的 RTCP 流量开销。

## <a name="managing-quality-of-service"></a>管理服务质量
<a name="man_QOS"> </a>

服务质量 (QoS) 是某些组织中所使用的一种网络技术，目的是有助于针对音频和视频通信提供最佳的最终用户体验。QoS 最常用于带宽有限的网络上：其中大量的网络数据包争用相对数量较小的可用带宽。QoS 允许管理员为承载音频或视频数据的数据包分配较高的优先级。通过为这些数据包提供较高的优先级，与涉及诸如文件传输、Web 浏览或数据库备份等内容的网络会话相比，音频和视频通信可能会以更快的速度完成，并且发生更少的中断。这是因为针对用于文件传输或数据库备份的网络数据包分配了“最佳效果”优先级。

> [!NOTE]
> 一般而言，QoS 仅适用于内部网络上的通信会话。 在实施 QoS 时，您将服务器和路由器配置为支持数据包标记，但 Internet 或其他网络上可能不支持您所使用的特定方式。 即使在其他网络上支持质量服务, 也不能保证 QoS 的配置方式与配置服务完全相同。 如果您使用 MPLS，则需要与您的 MPLS 提供商合作。

Skype for Business 服务器不需要 QoS, 但强烈建议这样做。 如果你在网络上遇到数据包丢失问题, 则你的可用解决方案是增加更多带宽或实现 QoS。 如果无法增加带宽，则实施 QoS 可能是您解决该问题的唯一办法。

Skype for Business 服务器提供全面的 QoS 支持: 这意味着已使用 QoS 的组织可以轻松地将 Skype for business 服务器集成到其现有网络基础结构中。 为执行此操作，您必须执行以下步骤：

- [在不基于 Windows 的设备的 Skype For Business 服务器中启用 QoS](../../manage/network-management/qos/enabling-qos-for-devices-that-are-not-based-on-windows.md)。 默认情况下，会针对运行其他操作系统的计算机和其他设备（如 iPhone）禁用 QoS。 尽管可以使用 Skype for Business 服务器启用和禁用设备的服务质量, 但通常无法使用该产品修改这些设备使用的 DSCP 代码。

- [为你的会议、应用程序和中介服务器配置端口范围和服务质量策略](../../manage/network-management/qos/configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)。 您必须为不同的数据包类型（如音频和视频）保留一组唯一的端口。 通过使用 Skype for Business 服务器, 您不能通过将属性值设置为 True 或 False 来启用或禁用 QoS。 而是可以通过配置端口范围，然后创建并应用组策略，来启用 QoS。 如果稍后决定不使用 QoS, 则可以通过删除相应的组策略对象来 "禁用" QoS。

- [为 Edge 服务器配置端口范围和服务质量策略](../../manage/network-management/qos/configuring-port-ranges-for-your-edge-servers.md)。 虽然不需要，但是可以将您的边缘服务器配置为与其他服务器使用相同的端口范围。 仅为边缘服务器的内部端配置 QoS 策略。 原因是 QoS 设计用于内部网络而不是 Internet 上。

- [为 Skype For Business Server 中的客户端配置端口范围和服务质量策略](../../manage/network-management/qos/configuring-port-ranges-for-your-skype-clients.md)。 这些端口范围仅适用于客户端计算机，并且通常与在您的服务器上配置的端口范围有所不同。 请注意, Skype for Business 服务器不支持 windows 10 之外的 Windows 操作系统的 QoS。


> [!NOTE]
> 如果你使用的是 Windows Server 2012 或 Windows Server 2012 R2, 你可能会对可用于管理该平台上的 QoS 的新的一组 Windows PowerShell cmdlet 感兴趣。 有关详细信息, 请参阅[Windows PowerShell 中的网络 QoS cmdlet](https://go.microsoft.com/fwlink/p/?LinkId=285379)。

有关 QoS 的详细信息,[请参阅网络规划、监视和疑难解答](https://www.microsoft.com/en-us/download/details.aspx?id=39084)以及与其他详细信息和深度有关的 Lync 服务器疑难解答。 虽然内容显式引用 Lync 2010 和 Lync 2013, 但 Skype for business 服务器的注意事项保持不变。

## <a name="see-also"></a>另请参阅
<a name="man_QOS"> </a>

[规划 Skype for Business 中的 IPv6](ipv6.md)

[Skype for Business 的负载平衡要求](load-balancing.md)

[Skype for business 服务器的 DNS 要求](dns.md)
