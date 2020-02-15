---
title: 规划 Skype for Business 的网络要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
description: 摘要：在实施 Skype for Business Server 之前，请查看下面的网络组件注意事项。
ms.openlocfilehash: 709da2ddd60b5b6ee69c22264c159d5d94ab91e3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42025793"
---
# <a name="plan-network-requirements-for-skype-for-business"></a>规划 Skype for Business 的网络要求

**摘要：** 在实施 Skype for Business Server 之前，请查看下面的网络组件注意事项。

有关这些主题中的信息[，请参阅白皮书网络规划、监视和疑难解答（Lync Server](https://www.microsoft.com/download/details.aspx?id=39084)具有其他详细信息和深度）。 虽然内容显式引用 Lync 2010 和 Lync 2013，但 Skype for business Server 的注意事项保持不变。

同样，如果您的网络涉及 wi-fi 和有线访问，则[通过 Wi-fi 提供 Lync 2013 实时通信](https://www.microsoft.com/download/details.aspx?id=36494)的白皮书是良好的参考，同样适用于 Skype For business Server。

<!-- Deprecated tools
Network performance and needs are directly linked to the traffic load placed on them. When planning your network and server implementations we recommend making use of the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md), the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md), and the [Skype for Business Server 2015 Stress and Performance Tool](../../management-tools/stress-and-performance-tool/stress-and-performance-tool.md).    -->

## <a name="server-hardware"></a>服务器硬件
<a name="S_hard"> </a>

Skype for Business Server 拓扑中每台服务器的网络适配器都必须支持至少1千兆位/秒（Gbps）。 通常情况下，应使用低延迟和高带宽局域网（LAN）连接 Skype for Business Server 拓扑中的所有服务器角色。 LAN 的大小取决于拓扑大小：

- 在标准版拓扑中，服务器应位于支持 1 Gbps 以太网或等效项的网络中。

- 在企业版拓扑中，大多数服务器应位于支持超过 1 Gbps 的网络中，尤其是在支持音频/视频（A/V）会议和应用程序共享时。

对于公用电话交换网 (PSTN) 集成，可以使用 T1/E1 线路或 SIP 中继进行集成。

## <a name="audiovideo-network-requirements"></a>音频/视频网络要求
<a name="AV_req"> </a>

Skype for Business Server 部署中的音频/视频（A/V）的网络要求包括以下各项：

- 如果要使用 DNS 负载平衡部署单个边缘服务器或边缘池，则可以将_外部_防火墙配置为执行网络地址转换（NAT）。 无法将_内部_防火墙配置为执行 NAT。 有关详细信息，请参阅[端口和防火墙规划](../edge-server-deployments/edge-environmental-requirements.md#port-and-firewall-planning)。

    > [!IMPORTANT]
    > 如果您有一个边缘池且正在使用硬件负载平衡器，则必须在边缘服务器上使用公用 IP 地址，并且不能将 NAT 用于支持 NAT 的设备（例如，防火墙装置或 LAN 交换机）中的服务器或池。 有关详细信息，请参阅[在 Skype For Business Server 中的边缘服务器方案](../edge-server-deployments/scenarios.md)。

- 如果您的组织使用了服务质量 (QoS) 基础结构，则媒体子系统应设计为在此现有基础结构中工作。

- 如果使用 Internet 协议安全性 (IPsec)，建议在用于 A/V 流量的端口范围内禁用 IPsec。 有关详细信息，请参阅[IPsec 异常](#ipsec-exceptions)。

若要提供最佳媒体质量，请执行以下操作：

- 设置网络链接以支持每个音频流的每秒 65 kbps 的吞吐量和每个视频流的 500 Kbps （如果已启用），在高峰使用时段。 双向音频或视频会话使用两个流，因此简单的音频/电话连接将需要130Kbps 来覆盖每个流。 同样，视频将使用 1000 Kbps 的总速度来传输上行和下游连接。

- 若要处理流量中的意外峰值和时间增加的使用率，Skype for Business Server 媒体终结点可适应不同的网络条件，并支持在仍保持可接受质量的情况下三倍的音频和视频吞吐量。 请勿假定此适应性将屏蔽网络预配时的问题。 在预配网络中，Skype for Business Server 媒体终结点的功能可以动态处理不同的网络条件（例如，临时数据包丢失）。

- 对于配置开销非常高且困难的网络链接，您可能必须考虑为较低的流量进行设置。 在这种情况下，让 Skype for Business Server 媒体终结点的弹性能够吸收流量量和峰值流量水平之间的差异，以降低语音质量的成本为代价。 此外，还会降低余地，否则会在流量中吸收突然的峰值。

- 对于在短期内无法正确设置的链接（例如，使用非常差的 WAN 链接的网站），请考虑为某些用户禁用视频。

- 设置网络以保证在峰值负载下的最大端到端延迟（延迟）为150毫秒（毫秒）。 延迟是 Skype for Business Server media 组件无法降低的网络障碍，查找和消除薄弱点非常重要。

- 对于运行防病毒软件的服务器，请在例外列表中包括运行 Skype for Business Server 的所有服务器，以提供最佳性能和音频质量。

## <a name="ipsec-exceptions"></a>IPsec 例外

对于已经部署了 Internet 协议安全性 (IPsec)（请参阅 IETF RFC 4301-4309）的企业网络，必须在用于传送音频、视频和全景视频的端口范围内禁用 IPsec。提出此建议的动机是需要避免由于 IPsec 协商而在分配媒体端口时产生任何延迟。

下表介绍了建议采用的 IPsec 例外设置。

**建议采用的 IPsec 例外**

|规则名称 |源 IP |目标 IP |协议 |源端口 |目标端口 |身份验证要求 |
|:--- |:--- |:--- |:--- |:---|:---|:--- |
|A/V 边缘服务器内部入站|任意  |A/V 边缘服务器内部|UDP 和 TCP|任意 |任意 |不进行身份验证|
|A/V 边缘服务器外部入站|任意  |A/V 边缘服务器外部|UDP 和 TCP|任意 |任意 |不进行身份验证|
|A/V 边缘服务器内部出站|A/V 边缘服务器内部  |A/V 边缘服务器外部 |UDP 和 TCP|任意 |任意 |不进行身份验证|
|A/V 边缘服务器外部出站|A/V 边缘服务器外部 |任意 |UDP 和 TCP|任意 |任意 |不进行身份验证|
|中介服务器入站|任意  |中介服务器 |UDP 和 TCP|任意 |任意 |不进行身份验证|
|中介服务器出站|中介服务器  |任意|UDP 和 TCP|任意 |任意 |不进行身份验证|
|会议助理入站|任意  |运行会议助理的前端服务器 |UDP 和 TCP|任意 |任意 |不进行身份验证|
|会议助理出站|运行会议助理的前端服务器  |任意|UDP 和 TCP|任意 |任意 |不进行身份验证|
|A/V 会议入站|任意|前端服务器|UDP 和 TCP|任意 |任意 |不进行身份验证|
|A/V 会议出站|前端服务器|任意|UDP 和 TCP|任意 |任意 |不进行身份验证|
|Exchange 入站|任意|Exchange 统一消息|UDP 和 TCP|任意 |任意 |不进行身份验证|
|应用程序共享服务器入站|任意|应用程序共享服务器|UDP 和 TCP|任意 |任意 |不进行身份验证|
|应用程序共享服务器出站|应用程序共享服务器| 任意 |UDP 和 TCP|任意 |任意 |不进行身份验证|
|Exchange 出站|Exchange 统一消息|任意|UDP 和 TCP|任意 |任意 |不进行身份验证|
|客户端| 任意  |任意|UDP 和 TCP|任意 |任意 |不进行身份验证|
|         |         |         |         |         |         |         |


## <a name="conferencing-network-requirements"></a>会议网络要求
<a name="Conf_req"> </a>

从 Internet 信息服务（IIS）服务器下载会议内容所使用的带宽取决于内容的大小。 您可以选择监视实际使用情况，并相应地调整带宽规划。

## <a name="network-bandwidth-requirements-for-media-traffic"></a>媒体流量的网络带宽要求
<a name="Conf_req"> </a>

网络规划的一个重要部分是确保您的网络能够处理由 Skype for Business Server 生成的媒体流量。 本节帮助您规划媒体流量。

### <a name="media-traffic-network-usage"></a>媒体流量网络使用情况
<a name="Net_req"> </a>

媒体流量带宽使用量可能由于不同变量（如编解码器使用、分辨率和活动级别）的数量而难于计算。 带宽使用是使用的编解码器的功能和流的活动，这会因不同的方案而异。 下表列出了在 Skype for Business Server 方案中通常使用的音频编解码器。

**音频编解码器带宽**

|**音频编解码器**|**应用场景**|**音频负载比特率（KBPS）**|**仅限于带宽音频负载和 IP 标头 (Kbps)**|**带宽音频负载、IP 标头、UDP、RTP 和 SRTP (Kbps)**|**带宽音频负载、IP 标头、UDP、RTP、SRTP 和前向纠错 (Kbps)**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|RTAudio 宽带  <br/> |对等  <br/> |29.0  <br/> |45.0  <br/> |57.0  <br/> |86.0  <br/> |
|RTAudio 窄带  <br/> |对等 PSTN  <br/> |11.8  <br/> |27.8  <br/> |39.8  <br/> |51.6  <br/> |
|G. g.722  <br/> |会议  <br/> |64.0  <br/> |80.0  <br/> |95.6  <br/> |159.6  <br/> |
|G.722 立体声  <br/> |对等会议  <br/> |128.0  <br/> |144.0  <br/> |159.6  <br/> |223.6  <br/> |
|G. g.711  <br/> |PSTN、会议  <br/> |64.0  <br/> |80.0  <br/> |92.0  <br/> |156.0  <br/> |
|Siren  <br/> |会议  <br/> |16.0  <br/> |32.0  <br/> |47.6  <br/> |63.6  <br/> |
|绞宽带  <br/> |对等  <br/> |36.0  <br/> |52.0  <br/> |64.0  <br/> |100.0  <br/> |
|绞宽带  <br/> |对等  <br/> |26.0  <br/> |42.0  <br/> |54.0  <br/> |80.0  <br/> |
|绞宽带  <br/> |对等  <br/> |20.0  <br/> |36.0  <br/> |48.0  <br/> |68.0  <br/> |
|绞宽带/窄带  <br/> |对等  <br/> |13.0  <br/> |29.0  <br/> |41.0  <br/> |54.0  <br/> |

> [!NOTE]
> 来自 Skype for Business 客户端的 PSTN 呼叫通常使用 g.711 编解码器，这需要较高的带宽。 如果没有足够的带宽可用于该编解码器，则调用可能会失败，并出现类似于媒体日志中的以下错误：**必须至少启用一个编解码器，hr： c0042004**。 媒体日志（即，博客文件）是加密的，只能由 Microsoft 支持人员解码。

上表中的带宽号基于20毫秒 packetization （每秒50数据包）以及 Siren 和 g.722 编解码器包含来自会议方案的其他安全实时传输协议（SRTP）开销，并假定该流是100% 活动。 当链接上存在数据包丢失时，将动态使用转发错误纠正（FEC），以帮助维护音频流的质量。

G.722 编解码器的立体声版由基于 Lync 会议室系统的系统使用，该系统使用单个立体声麦克风或一对单声道麦克风，以允许监听器更好地区分会议室中的多个扬声器。

**视频分辨率带宽**

|**视频编解码器**|**分辨率和纵横比**|**最大视频负载比特率（Kbps）**|**最小视频负载比特率（Kbps）**|
|:-----|:-----|:-----|:-----|
|H-p  <br/> |320x180 （16:9）  <br/> 212x160 （4:3）  <br/> |250  <br/> |15   <br/> |
|H-p/RTVideo  <br/> |424x240 （16:9）  <br/> 320x240 （4:3）  <br/> |350  <br/> |100  <br/> |
|H-p  <br/> |480x270 （16:9）  <br/> 424x320 （4:3）  <br/> |450  <br/> |200  <br/> |
|H-p/RTVideo  <br/> |640x360 （16:9）  <br/> 640x480 （4:3）  <br/> |800  <br/> |300  <br/> |
|H-p  <br/> |848x480 （16:9）  <br/> |1500  <br/> |400  <br/> |
|H-p  <br/> |960x540 （16:9）  <br/> |2000  <br/> |500  <br/> |
|H-p/RTVideo  <br/> |1280x720 （16:9）  <br/> |2500  <br/> |700  <br/> |
|H-p  <br/> |1920x1080 （16:9）  <br/> |4000  <br/> |1500  <br/> |
|H-p/RTVideo  <br/> |960x144 （20:3）  <br/> |500  <br/> |15   <br/> |
|H-p  <br/> |1280x192 （20:3）  <br/> |1000  <br/> |250  <br/> |
|H-p  <br/> |1920x288 （20:3）  <br/> |2000  <br/> |500  <br/> |

视频的默认编解码器是 "H-p/MPEG-2 第10部分" 高级视频编码标准，以及可伸缩性的视频编码扩展以实现时态可伸缩性。 为了维护与旧版客户端的互操作性，RTVideo 编解码器仍用于 Skype for Business Server 和旧版客户端之间的对等呼叫。 在 Skype for business Server 和旧版客户端的会议会话中，Skype for Business Server 终结点可能会使用视频编解码器对视频进行编码，并将 bitstream bitstream 发送到 Skype for Business Server 客户端和 RTVideo to legacy客户端.

所需的带宽取决于分辨率、质量、帧速率以及图片中的运动或变化量。 对于每个解决方法，有两个相关的比特率：

- **最大有效负载比特率**这是终结点将用于以最大帧速率进行解析的比特率。 这是允许最高视频和音质的值。

- **最小有效负载比特率**这是 Skype for business Server 终结点将切换到下一个较低分辨率的比特率。 为保证特定的分辨率，可用的视频有效负载比特率不得低于该分辨率的最低比特率。 如果最大比特率不可用或不切实际，此值可帮助您了解可能的最小值。 对于某些用户来说，低比特率视频可能会提供不可接受的视频体验，因此，请谨慎使用这些最低的视频有效负载 bitrates。 请注意，对于静态、不变的视频场景，实际比特率可能暂时低于最低比特率。

Skype for Business Server 支持多种解决方案。 这将允许 Skype for Business Server 调整到不同的网络带宽和接收客户端功能。 Skype for business Server 的默认纵横比为16:9。 对于不允许在16:9 长宽比中进行捕获的网络摄像头，仍支持旧版4:3 纵横比。

视频 FEC 在使用时始终包含在视频有效负载比特率中，因此，对于 video FEC 和无视频 FEC，不存在单独的值。

终结点不会持续流出音频或视频数据包。根据不同的方案，流活动的级别也不同，这些级别指示为流发送数据包的频率。流活动取决于媒体和方案，而不依赖使用的编解码器。在对等方案中：

- 仅当用户说出时，终结点才发送音频流。

- 参与双方都会接收到音频流。

- 如果使用视频，这两个终结点都会在呼叫过程中发送和接收视频流。

- 对于静态视频场景，实际比特率可能暂时较低，因为视频编解码器将跳过视频的编码区域，而不会在上一示例中进行更改。

在会议方案中：

- 仅当用户通话时终结点才发送音频流。

- 所有参与者都会接收到音频流。

- 如果使用视频，则所有参与者最多将收到 5 个接收视频流和 1 个全景（例如，纵横比 20:3）视频流。 默认情况下，5 个接收视频流是基于当前发言人历史记录的，但用户还可手动选择要从其接收视频流的参与者。 如果启用多视频，则每个视频流的分辨率和带宽要求将会降低。

- 每个打开用户的发送视频流的参与者将发送一个或多个视频流。 Skype for Business Server 具有最长可发送五个视频流的功能，以优化所有接收客户端的视频质量。 将发送的视频流的实际数量由发送方根据 CPU 容量、可用上行链路带宽和请求特定视频流的接收客户端的数量确定。 最常见的情况是，在旧客户端加入会议的情况下发送 1 个 H.264 和 1 个 RTVideo 视频流。 另一常见方案是，发送若干 H.264 视频流（例如，使用不同视频分辨率）以适应不同的接收方请求。

除音频和视频媒体的实时传输协议 (RTP) 流量所需的带宽之外，实时传输控制协议 (RTCP) 也需要带宽。 RTCP 用于报告 RTP 流的统计信息和带外控制。 规划时，请使用下表中的带宽数值规划 RTCP 流量。 这些值代表用于 RTCP 的最大带宽，由于控件数据不同，音频和视频流的使用带宽不同

**RTCP 带宽**

|**媒体**|**RTCP 最大带宽 (Kbps)**|
|:-----|:-----|
|音频  <br/> |5   <br/> |
|视频（仅正在发送/接收的 H.264 或 RTVideo）  <br/> |10   <br/> |
|视频（正在发送/接收的 H.264 和 RTVideo）  <br/> |15   <br/> |

对于容量规划，以下两个统计信息是非常重要的：

- **不带 FEC 的最大带宽**流将使用的最大带宽。 这包括流的典型活动和在没有 FEC 的情况下使用的典型编解码器。 这是流处于100% 活动时的带宽，没有任何数据包丢失触发了 FEC 的使用。 这有助于计算必须分配多少带宽以允许在给定方案中使用编解码器。 FEC 不应是托管网络的要求。

- **使用 FEC 的最大带宽**流使用的最大带宽。 这包括流的典型活动和在 FEC 方案中使用的典型编解码器。 这是流处于100% 活动时的带宽，并且存在数据包丢失触发使用 FEC 以提高质量的情况。 这对于计算必须分配多少带宽以允许在给定方案中使用编解码器，并允许使用 FEC 在数据包丢失情况下保留质量，这一点非常有用。

下面的表中还列出了另一个带宽值，“典型带宽”****。 这是流消耗的平均带宽。 这包括流的典型活动和方案中使用的典型编解码器。 此带宽可用于接近于在特定时间（但不适用于容量规划）的媒体流量使用的带宽量，因为当活动级别大于平均值时，单个呼叫将超过此值。 下表中的典型视频流带宽基于在测量的客户数据中看到的不同视频分辨率的混合，并且较小的安装可能具有与表数据不同的实际数字。 例如，在对等会话中，大多数用户将使用默认视频呈现窗口，而某些百分比的用户可能会增加或最大化 Skype for business Server 应用程序，以允许更好的视频分辨率。

下表提供了各种方案的值。

**对等会话的音频/视频容量规划**

|**媒体**|**编解码器**|**典型流带宽 (Kbps)**|**不使用 FEC 的最大流带宽**|**使用 FEC 的最大流带宽**|
|:-----|:-----|:-----|:-----|:-----|
|音频  <br/> |RTAudio 宽带  <br/> |39.8  <br/> |62  <br/> |91  <br/> |
|音频  <br/> |RTAudio 窄带  <br/> |29.3  <br/> |44.8  <br/> |56.6  <br/> |
|音频  <br/> |绞宽带  <br/> |44.3  <br/> |69  <br/> |105  <br/> |
|呼叫 Skype for Business 服务器终结点时的主视频  <br/> |H-p  <br/> |460  <br/> |4010（用于最大分辨率 1920x1080）  <br/> |已包含  <br/> |
|呼叫 Lync 2010 或 Office Communicator 2007 R2 终结点时的主视频  <br/> |RTVideo  <br/> |460  <br/> |2510（用于最大分辨率 1280x720）  <br/> |已包含  <br/> |
|呼叫 Skype for Business 服务器终结点时的全景视频  <br/> |H-p  <br/> |190  <br/> |2010（用于最大分辨率 1920x288）  <br/> |已包含  <br/> |
|调用 Lync 2010 终结点时的全景视频  <br/> |RTVideo  <br/> |190  <br/> |510（用于最大分辨率 960x144）  <br/> |已包含  <br/> |

**会议的音频/视频容量规划**

|**媒体**|**典型的编解码器**|**典型流带宽 (Kbps)**|**不使用 FEC 的最大流带宽**|**使用 FEC 的最大流带宽**|
|:-----|:-----|:-----|:-----|:-----|
|音频  <br/> |G. g.722  <br/> |46.1  <br/> |100.6  <br/> |164.6  <br/> |
|音频  <br/> |Siren  <br/> |25.5  <br/> |52.6  <br/> |68.6  <br/> |
|主视频接收  <br/> |H-p 和 RTVideo ¹  <br/> |260  <br/> |8015  <br/> |不适用  <br/> |
|主视频发送  <br/> |H-p 和 RTVideo  <br/> |270  <br/> |8015  <br/> |不适用  <br/> |
|全景视频接收  <br/> |H-p 和 RTVideo  <br/> |190  <br/> |2010（用于最大分辨率 1920x288）  <br/> |不适用  <br/> |
|全景视频发送  <br/> |H-p 和 RTVideo  <br/> |190  <br/> |2515²  <br/> |不适用  <br/> |

1. 当 Lync 2010 客户端连接到会议时，除了发送-264 视频之外，还会发送 RT 视频。

2. 如果有多个流，它们将动态共享分配的带宽。

对于主视频，典型的流带宽是已接收的所有视频流的聚合带宽，最大流是所有发送视频流的带宽。 即使使用多个视频流，典型的视频带宽也比对等方案中的小，这是因为许多视频会议使用的内容共享会导致更小的视频窗口，因此视频分辨率较小。 支持的最大聚合视频负载带宽为 8000 Kbps，将使用的发送和接收流（例如，有两个传入1920x1080p 视频流）。 仅在实际实施中很少看到最大值。

在构建使用库视图功能的多方会议时，带宽使用率最初在参与者加入时增加，然后在降低分辨率以适应最大值时降低。

||**2个参与者**|**3参与者**|**4参与者**|**5参与者**|**6个参与者**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**收到的最大分辨率** <br/> |1920x1080  <br/> |1280x720  <br/> |640x360  <br/> |640x360 320x240  <br/> |640x360 320x240  <br/> |
|**总平均比特率** <br/> |2128  <br/> |4050  <br/> |1304  <br/> |1224  <br/> |1565  <br/> |
|**总最大比特率** <br/> |4063  <br/> |5890  <br/> |2860  <br/> |2699  <br/> |3017  <br/> |

全景视频的典型流带宽基于仅流式传输到960x144 全景视频的设备。 在使用带有1920x288 全景视频的设备时，预计会增加典型的流带宽。

**PSTN 的音频容量规划**

|**媒体**|**典型的编解码器**|**典型流带宽 (Kbps)**|**不使用 FEC 的最大流带宽**|**使用 FEC 的最大流带宽**|
|:-----|:-----|:-----|:-----|:-----|
|音频  <br/> |G.711 （其中包括会议中的 PSTN 参与者）  <br/> |64.8  <br/> |97  <br/> |161  <br/> |
|音频  <br/> |RTAudio 窄带  <br/> |30.9  <br/> |44.8  <br/> |56.6  <br/> |

这些表中的网络带宽数值仅代表单向流量，其中包括分配给每个流的 5 Kbps 的 RTCP 流量开销。

## <a name="managing-quality-of-service"></a>管理服务质量
<a name="man_QOS"> </a>

服务质量（QoS）是在某些组织中使用的网络技术，可帮助为音频和视频通信提供最佳的最终用户体验。 在带宽受到限制的网络上经常使用 QoS：如果有大量网络数据包争用相当少的可用带宽，QoS 使管理员能够向携带音频或视频数据的数据包分配更高的优先级。 通过为这些数据包提供更高的优先级，音频和视频通信可能会更快地完成，且中断更少，这与涉及文件传输、web 浏览或数据库备份等内容的网络会话有关。 这是因为用于文件传输或数据库备份的网络数据包被分配了 "最大努力" 优先级。

> [!NOTE]
> 通常情况下，QoS 仅适用于内部网络上的通信会话。 在实施 QoS 时，您需要将服务器和路由器配置为以特定方式支持数据包标记，而 Internet 或其他网络上可能不受支持。 即使在其他网络上支持服务质量，也不能保证 QoS 的配置方式与您配置该服务的方式完全相同。 如果使用的是 MPLS，则需要使用 MPLS 提供程序。

Skype for Business Server 不需要 QoS，但强烈建议这样做。 如果您在网络上遇到数据包丢失问题，则可用的解决方案是添加更多带宽或实施 QoS。 如果无法添加更多的带宽，则实施 QoS 可能是解决问题的唯一收费。

Skype for Business Server 提供对 QoS 的完全支持：这意味着已使用 QoS 的组织可以轻松地将 Skype for business Server 集成到其现有的网络基础结构中。 若要执行此操作，您必须执行以下步骤：

- [为不基于 Windows 的设备在 Skype For Business Server 中启用 QoS](../../manage/network-management/qos/enabling-qos-for-devices-that-are-not-based-on-windows.md)。 默认情况下，会针对运行其他操作系统的计算机和其他设备（如 iPhone）禁用 QoS。 虽然您可以使用 Skype for Business Server 为设备启用和禁用服务质量，但通常无法使用该产品修改这些设备使用的 DSCP 代码。

- [为您的会议、应用程序和中介服务器配置端口范围和服务质量策略](../../manage/network-management/qos/configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)。 您必须为不同的数据包类型（如音频和视频）保留一组唯一的端口。 通过使用 Skype for Business Server，您不能通过将属性值设置为 True 或 False 来启用或禁用 QoS。 相反，您可以通过配置端口范围，然后创建和应用组策略来启用 QoS。 如果你后来决定不使用 QoS，可以通过删除相应的组策略对象来 "禁用" QoS。

- [为边缘服务器配置端口范围和服务质量策略](../../manage/network-management/qos/configuring-port-ranges-for-your-edge-servers.md)。 虽然不需要，但是可以将您的边缘服务器配置为与其他服务器使用相同的端口范围。 仅为边缘服务器的内部端配置 QoS 策略。 这是因为 QoS 专为用于内部网络而不是在 Internet 上使用。

- [为 Skype For Business Server 中的客户端配置端口范围和服务质量策略](../../manage/network-management/qos/configuring-port-ranges-for-your-skype-clients.md)。 这些端口范围仅适用于客户端计算机，并且通常与在您的服务器上配置的端口范围不同。 请注意，Skype for Business Server 不支持 Windows 10 之外的 Windows 操作系统的 QoS。


> [!NOTE]
> 如果你使用的是 Windows Server 2012 或 Windows Server 2012 R2，你可能会对可用于在该平台上管理 QoS 的新的一组 Windows PowerShell cmdlet 感兴趣。 有关详细信息，请参阅[Windows PowerShell 中的网络 QoS cmdlet](https://go.microsoft.com/fwlink/p/?LinkId=285379)。

还将在白皮书[网络规划、监视和故障排除](https://www.microsoft.com/download/details.aspx?id=39084)中对 QoS 服务器进行详细介绍，同时提供其他详细信息和深度。 虽然内容显式引用 Lync 2010 和 Lync 2013，但 Skype for business Server 的注意事项保持不变。

## <a name="see-also"></a>另请参阅
<a name="man_QOS"> </a>

[在 Skype for Business 中规划 IPv6](ipv6.md)

[Skype for business 的负载平衡要求](load-balancing.md)

[Skype for Business Server 的 DNS 要求](dns.md)
