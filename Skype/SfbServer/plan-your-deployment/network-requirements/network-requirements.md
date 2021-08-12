---
title: 规划网络网络Skype for Business
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
ms.assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
description: 摘要：实施前，请查看下面的网络组件Skype for Business Server。
ms.openlocfilehash: dc2e56c1c918a9ebdaf8a40bfcdb6530fae283b6b2733b4def890c6b26630c29
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54323004"
---
# <a name="plan-network-requirements-for-skype-for-business"></a>规划网络网络Skype for Business

**摘要：** 在实施网络组件之前，请查看下面的网络Skype for Business Server。

这些主题中的信息也在白皮书 Lync [Server](https://www.microsoft.com/download/details.aspx?id=39084) 的网络规划、监控和疑难解答中进行了讨论，并提供了其他详细信息和深度。 虽然内容明确引用了 Lync 2010 和 Lync 2013，但Skype for Business Server保持不变。

同样，如果网络涉及 WLAN 和有线访问，白皮书[Delivering Lync 2013 Real-Time Communications over Wi-Fi](https://www.microsoft.com/download/details.aspx?id=36494)是一个很好的参考，同样适用于 Skype for Business Server。

<!-- Deprecated tools
Network performance and needs are directly linked to the traffic load placed on them. When planning your network and server implementations we recommend making use of the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md), the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md), and the [Skype for Business Server 2015 Stress and Performance Tool](../../management-tools/stress-and-performance-tool/stress-and-performance-tool.md).    -->

## <a name="server-hardware"></a>服务器硬件
<a name="S_hard"> </a>

拓扑中每台服务器的网络适配器Skype for Business Server每秒至少支持 1 GB (Gbps) 。 通常，应该使用低延迟和高带宽的局域网Skype for Business Server LAN (内部的所有服务器角色) 。 LAN 的大小取决于拓扑的大小：

- 在Standard Edition拓扑中，服务器应位于支持 1 Gbps 以太网或等效以太网的网络中。

- 在Enterprise Edition拓扑中，大多数服务器应位于支持大于 1 Gbps 的网络中，尤其是在支持音频/视频 (A/V) 会议和应用程序共享时。

对于公用电话交换网 (PSTN) 集成，可以使用 T1/E1 线路或 SIP 中继进行集成。

## <a name="audiovideo-network-requirements"></a>音频/视频网络要求
<a name="AV_req"> </a>

Skype for Business Server部署中的音频/视频 (A/V) 网络要求包括：

- 如果要使用 DNS 负载平衡部署单个边缘服务器或边缘池，可以将外部防火墙配置为通过 NAT  (网络) 。 不能将内部 _防火墙配置为_ 执行 NAT。 有关详细信息，请参阅端口 [和防火墙规划](../edge-server-deployments/edge-environmental-requirements.md#port-and-firewall-planning)。

    > [!IMPORTANT]
    > 如果您有边缘池并且正在使用硬件负载平衡器，则必须在边缘服务器上使用公用 IP 地址，并且不能将 NAT 用于服务器或支持 NAT 的设备上的池 (例如防火墙设备或 LAN 交换机。 有关详细信息，请参阅中[的边缘服务器Skype for Business Server。](../edge-server-deployments/scenarios.md)

- 如果您的组织使用了服务质量 (QoS) 基础结构，则媒体子系统应设计为在此现有基础结构中工作。

- 如果使用 Internet 协议安全性 (IPsec)，建议在用于 A/V 流量的端口范围内禁用 IPsec。 有关详细信息，请参阅 [IPsec exceptions](#ipsec-exceptions)。

若要提供最佳媒体质量，请执行下列操作：

- 设置网络链接以支持高峰使用时段内每个音频流 65 千位每秒 (Kbps) 和每个视频流 500 Kbps（如果启用）的吞吐量。 双向音频或视频会话使用两个流，因此简单的音频/电话连接需要 130Kbps 才能覆盖每个流。 同样，视频总共使用 1000 Kbps 进行上游和下游连接。

- 为了应对意外的流量峰值和随时间增加的使用量，Skype for Business Server媒体终结点可以适应不断变化的网络条件，并支持音频和视频吞吐量的三倍，同时仍保持可接受的质量。 不要假定在网络预配不足时，这种适适性将掩盖问题。 在预配不足的网络中，Skype for Business Server 媒体终结点动态处理不同网络条件的能力 (例如，临时高数据包丢失) 减少。

- 对于设置成本很高且难以进行设置的网络链接，可能需要考虑为较低的流量进行设置。 在此方案中，让媒体终结点的弹性Skype for Business Server流量和高峰流量级别之间的差异，代价是语音质量下降。 此外，可用于吸收流量中的突发峰值的可用空间也会减少。

- 对于无法在短时间内正确设置的链接 (例如，使用 WAN 链接非常差) ，请考虑对某些用户禁用视频。

- 设置网络以确保最大端到端延迟 (在高峰负载) 为 150 (毫秒) 延迟。 延迟是媒体组件无法Skype for Business Server的一种网络障碍，必须查找并消除这些缺陷。

- 对于运行防病毒软件的服务器，在例外列表中Skype for Business Server运行软件的所有服务器，以提供最佳性能和音频质量。

## <a name="ipsec-exceptions"></a>IPsec 异常

对于已经部署了 Internet 协议安全性 (IPsec)（请参阅 IETF RFC 4301-4309）的企业网络，必须在用于传送音频、视频和全景视频的端口范围内禁用 IPsec。提出此建议的动机是需要避免由于 IPsec 协商而在分配媒体端口时产生任何延迟。

下表介绍了建议采用的 IPsec 例外设置。

**建议采用的 IPsec 例外**

|规则名称 |源 IP |目标 IP |协议 |源端口 |目标端口 |身份验证要求 |
|:--- |:--- |:--- |:--- |:---|:---|:--- |
|A/V 边缘服务器内部入站|任何  |A/V 边缘服务器内部|UDP 和 TCP|任何 |任何 |不进行身份验证|
|A/V 边缘服务器外部入站|任何  |A/V 边缘服务器外部|UDP 和 TCP|任何 |任何 |不进行身份验证|
|A/V 边缘服务器内部出站|A/V 边缘服务器内部  |A/V 边缘服务器外部 |UDP 和 TCP|任何 |任何 |不进行身份验证|
|A/V 边缘服务器外部出站|A/V 边缘服务器外部 |任何 |UDP 和 TCP|任何 |任何 |不进行身份验证|
|中介服务器入站|任何  |中介 (服务器)  |UDP 和 TCP|任何 |任何 |不进行身份验证|
|中介服务器出站|中介 (服务器)   |任何|UDP 和 TCP|任何 |任何 |不进行身份验证|
|会议助理入站|任何  |运行会议助理的前端服务器 |UDP 和 TCP|任何 |任何 |不进行身份验证|
|会议助理出站|运行会议助理的前端服务器  |任何|UDP 和 TCP|任何 |任何 |不进行身份验证|
|A/V 会议入站|任何|前端服务器|UDP 和 TCP|任何 |任何 |不进行身份验证|
|A/V 会议出站|前端服务器|任何|UDP 和 TCP|任何 |任何 |不进行身份验证|
|Exchange 入站|任何|Exchange 统一消息|UDP 和 TCP|任何 |任何 |不进行身份验证|
|应用程序共享服务器入站|任何|应用程序共享服务器|UDP 和 TCP|任何 |任何 |不进行身份验证|
|应用程序共享服务器出站|应用程序共享服务器| 任何 |UDP 和 TCP|任何 |任何 |不进行身份验证|
|Exchange 出站|Exchange 统一消息|任何|UDP 和 TCP|任何 |任何 |不进行身份验证|
|客户端| 任何  |任何|UDP 和 TCP|任何 |任何 |不进行身份验证|
|         |         |         |         |         |         |         |


## <a name="conferencing-network-requirements"></a>会议网络要求
<a name="Conf_req"> </a>

用于从 IIS 服务器Internet Information Services (会议) 带宽取决于内容的大小。 您可以选择监视实际使用情况并相应地调整带宽规划。

## <a name="network-bandwidth-requirements-for-media-traffic"></a>媒体流量的网络带宽要求
<a name="Conf_req"> </a>

网络规划的一个重要部分是确保你的网络可以处理由网络生成的媒体Skype for Business Server。 本节帮助您规划媒体流量。

### <a name="media-traffic-network-usage"></a>媒体流量网络使用情况
<a name="Net_req"> </a>

媒体流量带宽使用量可能由于不同变量（如编解码器使用、分辨率和活动级别）的数量而难于计算。 带宽使用量是使用的编解码器以及流活动的一个功能，因方案而异。 下表列出了通常用于各种方案Skype for Business Server编解码器。

**音频编解码器带宽**

|**音频编解码器**|**应用场景**|**音频负载比特率 (KBPS)**|**仅限于带宽音频负载和 IP 标头 (Kbps)**|**带宽音频负载、IP 标头、UDP、RTP 和 SRTP (Kbps)**|**带宽音频负载、IP 标头、UDP、RTP、SRTP 和前向纠错 (Kbps)**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|RTAudio 宽带  <br/> |对等  <br/> |29.0  <br/> |45.0  <br/> |57.0  <br/> |86.0  <br/> |
|RTAudio 窄带  <br/> |对等 PSTN  <br/> |11.8  <br/> |27.8  <br/> |39.8  <br/> |51.6  <br/> |
|G.722  <br/> |会议  <br/> |64.0  <br/> |80.0  <br/> |95.6  <br/> |159.6  <br/> |
|G.722 立体声  <br/> |对等会议  <br/> |128.0  <br/> |144.0  <br/> |159.6  <br/> |223.6  <br/> |
|G.711  <br/> |PSTN，会议  <br/> |64.0  <br/> |80.0  <br/> |92.0  <br/> |156.0  <br/> |
|Siren  <br/> |会议  <br/> |16.0  <br/> |32.0  <br/> |47.6  <br/> |63.6  <br/> |
|一个使用一个 1000 个  <br/> |对等  <br/> |36.0  <br/> |52.0  <br/> |64.0  <br/> |100.0  <br/> |
|一个使用一个 1000 个  <br/> |对等  <br/> |26.0  <br/> |42.0  <br/> |54.0  <br/> |80.0  <br/> |
|一个使用一个 1000 个  <br/> |对等  <br/> |20.0  <br/> |36.0  <br/> |48.0  <br/> |68.0  <br/> |
|一个可宽带/窄带  <br/> |对等  <br/> |13.0  <br/> |29.0  <br/> |41.0  <br/> |54.0  <br/> |

> [!NOTE]
> 来自客户端的 PSTN Skype for Business通常使用 G.711 编解码器，这需要高带宽。 如果该编解码器没有足够的带宽，则呼叫可能会失败，并出现类似于媒体日志中的以下错误：Atleast 必须启用一个编解码器 **，hr： c0042004**。 媒体日志 A0.blog 文件) 加密，并且仅能由 Microsoft 支持人员解码。

上表中的带宽数字基于 20 毫秒的分组 (每秒 50 个数据包) 对于 Siren 和 G.722 编解码器包括其他安全实时传输协议 (SRTP) 开销（来自会议方案）并假定流为 100% 活动。 当链接 (数据包丢失时，会动态使用FEC) 前向错误更正，以帮助维护音频流的质量。

G.722 编解码器立体声版本由基于 Lync 会议室系统的系统使用，该系统使用一个立体声麦克风或一对单声道麦克风，以便侦听器更好地区分会议室中的多个扬声器。

**视频分辨率带宽**

|**视频编解码器**|**分辨率和纵横比**|**最大视频负载比特率 (Kbps)**|**最小视频负载比特率 (Kbps)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |320x180 (16：9)   <br/> 212x160 (4：3)   <br/> |250  <br/> |15  <br/> |
|H.264/RTVideo  <br/> |424x240 (16：9)   <br/> 320x240 (4：3)   <br/> |350  <br/> |100  <br/> |
|H.264  <br/> |480x270 (16：9)   <br/> 424x320 (4：3)   <br/> |450  <br/> |200  <br/> |
|H.264/RTVideo  <br/> |640x360 (16：9)   <br/> 640x480 (4：3)   <br/> |800  <br/> |300  <br/> |
|H.264  <br/> |848x480 (16：9)   <br/> |1500  <br/> |400  <br/> |
|H.264  <br/> |960x540 (16：9)   <br/> |2000  <br/> |500  <br/> |
|H.264/RTVideo  <br/> |1280x720 (16：9)   <br/> |2500  <br/> |700  <br/> |
|H.264  <br/> |1920x1080 (16：9)   <br/> |4000  <br/> |1500  <br/> |
|H.264/RTVideo  <br/> |960x144 (20：3)   <br/> |500  <br/> |15  <br/> |
|H.264  <br/> |1280x192 (20：3)   <br/> |1000  <br/> |250  <br/> |
|H.264  <br/> |1920x288 (20：3)   <br/> |2000  <br/> |500  <br/> |

视频的默认编解码器是 H.264/MPEG-4 第 10 部分高级视频编码标准，以及针对临时可伸缩性的可扩展视频编码扩展。 为了维护与旧客户端的互操作性，RTVideo 编解码器仍用于客户端和旧客户端Skype for Business Server对等呼叫。 在使用 Skype for Business Server 和旧客户端的会议会话中，Skype for Business Server 终结点可能同时使用视频编解码器对视频进行编码，并将 H.264 位流发送到 Skype for Business Server 客户端，将 RTVideo 比特流发送到旧客户端。

所需的带宽取决于分辨率、质量、帧速率以及图片中的运动或更改量。 对于每个分辨率，都有两个相关的比特率：

- **最大有效负载比特率** 这是终结点在最大帧速率下用于分辨率的比特率。 这是允许最高视频和声音质量的值。

- **最小有效负载比特率** 此比特率低于此比特率，Skype for Business Server终结点将切换到下一个较低分辨率。 为保证特定分辨率，可用视频负载比特率不得低于该分辨率的最低比特率。 如果最大比特率不可用或不可用，则此值可帮助您了解可能的最低值。 对于一些用户，这种低比特率视频可能会提供不可接受的视频体验，因此请谨慎使用这些最小视频负载比特率。 请注意，对于静态、未更改的视频场景，实际比特率可能会暂时低于最低比特率。

Skype for Business Server支持许多分辨率。 这样，Skype for Business Server可以适应不同的网络带宽和接收客户端功能。 默认纵横比Skype for Business Server 16：9。 网络摄像机仍支持传统的 4：3 纵横比，它不允许以 16：9 纵横比进行捕获。

视频 FEC 在使用时始终包含在视频负载比特率中，因此对于视频 FEC 和没有视频 FEC，没有单独的值。

终结点不会持续流出音频或视频数据包。根据不同的方案，流活动的级别也不同，这些级别指示为流发送数据包的频率。流活动取决于媒体和方案，而不依赖使用的编解码器。在对等方案中：

- 终结点仅在用户说话时发送音频流。

- 参与双方都会接收到音频流。

- 如果使用视频，两个终结点将在呼叫期间发送和接收视频流。

- 对于静态视频场景，实际比特率可能暂时非常低，因为视频编解码器将跳过视频的编码区域，而不会自上一个示例起发生变化。

在会议方案中：

- 仅当用户通话时终结点才发送音频流。

- 所有参与者都会接收到音频流。

- 如果使用视频，则所有参与者最多将收到 5 个接收视频流和 1 个全景（例如，纵横比 20:3）视频流。 默认情况下，5 个接收视频流是基于当前发言人历史记录的，但用户还可手动选择要从其接收视频流的参与者。 如果启用多视频，则每个视频流的分辨率和带宽要求将更低。

- 打开用户发送视频流的每个参与者将发送一个或多个视频流。 Skype for Business Server发送最多五个视频流，以优化所有接收客户端的视频质量。 将发送的视频流的实际数量由发送方根据 CPU 容量、可用上行链路带宽和请求特定视频流的接收客户端的数量确定。 最常见的情况是，在旧客户端加入会议的情况下发送 1 个 H.264 和 1 个 RTVideo 视频流。 另一常见方案是，发送若干 H.264 视频流（例如，使用不同视频分辨率）以适应不同的接收方请求。

除音频和视频媒体的实时传输协议 (RTP) 流量所需的带宽之外，实时传输控制协议 (RTCP) 也需要带宽。 RTCP 用于报告 RTP 流的统计信息和带外控制。 规划时，请使用下表中的带宽数值规划 RTCP 流量。 这些值表示用于 RTCP 的最大带宽，并且因控制数据不同而不同用于音频和视频流

**RTCP 带宽**

|**Media**|**RTCP 最大带宽 (Kbps)**|
|:-----|:-----|
|音频  <br/> |5   <br/> |
|视频（仅正在发送/接收的 H.264 或 RTVideo）  <br/> |10   <br/> |
|视频（正在发送/接收的 H.264 和 RTVideo）  <br/> |15  <br/> |

对于容量规划，需要关注以下两个统计信息：

- **没有 FEC 的最大带宽** 流将占用的最大带宽。 这包括流的典型活动和在没有 FEC 的情况下使用的典型编解码器。 这是流处于 100% 活动状态且没有数据包丢失触发使用 FEC 的带宽。 这可用于计算为允许编解码器在给定方案中使用而必须分配的带宽量。 FEC 不应成为托管网络的要求。

- **FEC 的最大带宽** 流使用的最大带宽。 这包括流的典型活动和 FEC 方案中使用的典型编解码器。 这是当流处于 100% 活动状态且数据包丢失时触发使用 FEC 来改进质量的带宽。 这可用于计算必须分配的带宽量，以允许编解码器在给定方案中使用，并允许使用 FEC 在数据包丢失条件下保持质量。

下面的表中还列出了另一个带宽值，“典型带宽”。 这是流使用的平均带宽。 这包括流的典型活动和方案中使用的典型编解码器。 此带宽可用于估计特定时间媒体流量使用的带宽量，但不应用于容量规划，因为当活动级别大于平均值时，单个呼叫将超过此值。 下表中的典型视频流带宽基于测量的客户数据中观察到的不同视频分辨率的组合，较小的安装可能具有与表数据不同的实际数字。 例如，在对等会话中，大多数用户将使用默认视频呈现窗口，而一定百分比的用户将增加或最大化 Skype for Business Server 应用程序以允许更好的视频分辨率。

下表提供了各种方案的值。

**对等会话的音频/视频容量规划**

|**Media**|**编解码器**|**典型流带宽 (Kbps)**|**不使用 FEC 的最大流带宽**|**使用 FEC 的最大流带宽**|
|:-----|:-----|:-----|:-----|:-----|
|音频  <br/> |RTAudio 宽带  <br/> |39.8  <br/> |62  <br/> |91  <br/> |
|音频  <br/> |RTAudio 窄带  <br/> |29.3  <br/> |44.8  <br/> |56.6  <br/> |
|音频  <br/> |一个使用一个 1000 个  <br/> |44.3  <br/> |69  <br/> |105  <br/> |
|呼叫终结点时Skype for Business Server视频  <br/> |H.264  <br/> |460  <br/> |4010（用于最大分辨率 1920x1080）  <br/> |已包含  <br/> |
|调用 Lync 2010 或 Office Communicator 2007 R2 终结点时的主视频  <br/> |RTVideo  <br/> |460  <br/> |2510（用于最大分辨率 1280x720）  <br/> |已包含  <br/> |
|调用终结点时Skype for Business Server全景视频  <br/> |H.264  <br/> |190  <br/> |2010（用于最大分辨率 1920x288）  <br/> |已包含  <br/> |
|调用 Lync 2010 终结点时全景视频  <br/> |RTVideo  <br/> |190  <br/> |510（用于最大分辨率 960x144）  <br/> |已包含  <br/> |

**会议的音频/视频容量规划**

|**Media**|**典型的编解码器**|**典型流带宽 (Kbps)**|**不使用 FEC 的最大流带宽**|**使用 FEC 的最大流带宽**|
|:-----|:-----|:-----|:-----|:-----|
|音频  <br/> |G.722  <br/> |46.1  <br/> |100.6  <br/> |164.6  <br/> |
|音频  <br/> |Siren  <br/> |25.5  <br/> |52.6  <br/> |68.6  <br/> |
|主视频接收  <br/> |H.264 和 RTVideo¹  <br/> |260  <br/> |8015  <br/> |不适用  <br/> |
|主视频发送  <br/> |H.264 和 RTVideo  <br/> |270  <br/> |8015  <br/> |不适用  <br/> |
|全景视频接收  <br/> |H.264 和 RTVideo  <br/> |190  <br/> |2010（用于最大分辨率 1920x288）  <br/> |不适用  <br/> |
|全景视频发送  <br/> |H.264 和 RTVideo  <br/> |190  <br/> |2515 下午 4：00  <br/> |不适用  <br/> |

1. 当 Lync 2010 客户端连接到会议时，除了 H.264 之外，还发送 RT 视频。

2. 如果有多个流，则动态共享分配的带宽。

对于主视频，典型流带宽是所有接收的视频流的聚合带宽，最大流是所有发送视频流的带宽。 即使具有多个视频流，典型视频带宽也小于对等方案，因为许多视频会议使用的内容共享导致视频窗口更小，因此视频分辨率更小。 对于发送和接收流，支持的最大聚合视频负载带宽为 8000 Kbps，例如，如果有两个传入的 1920x1080p 视频流 (则使用) 。 在实际实现中，最大值很少看到。

构建使用库视图功能的多部分会议时，带宽利用率最初会随着参与者加入而增加，然后随着分辨率的降低而降低，以适应最大值。

||**2 个参与者**|**3 个参与者**|**4 个参与者**|**5 个参与者**|**6 个参与者**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**接收的最大分辨率** <br/> |1920x1080  <br/> |1280x720  <br/> |640x360  <br/> |640x360 320x240  <br/> |640x360 320x240  <br/> |
|**总平均比特率** <br/> |2128  <br/> |4050  <br/> |1304  <br/> |1224  <br/> |1565  <br/> |
|**Total 最大比特率** <br/> |4063  <br/> |5890  <br/> |2860  <br/> |2699  <br/> |3017  <br/> |

全景视频的典型流带宽基于仅流式传输最高为 960x144 全景视频的设备。 在使用具有 1920x288 全景视频的设备时，预期典型流带宽将增加。

**PSTN 的音频容量规划**

|**Media**|**典型的编解码器**|**典型流带宽 (Kbps)**|**不使用 FEC 的最大流带宽**|**使用 FEC 的最大流带宽**|
|:-----|:-----|:-----|:-----|:-----|
|音频  <br/> |G.711 (包括 PSTN 参与者参加)   <br/> |64.8  <br/> |97  <br/> |161  <br/> |
|音频  <br/> |RTAudio 窄带  <br/> |30.9  <br/> |44.8  <br/> |56.6  <br/> |

这些表中的网络带宽数值仅代表单向流量，其中包括分配给每个流的 5 Kbps 的 RTCP 流量开销。

## <a name="managing-quality-of-service"></a>管理服务质量
<a name="man_QOS"> </a>

QoS (服务质量) 是一种网络技术，在某些组织中用于帮助为音频和视频通信提供最佳最终用户体验。 QoS 最常用于带宽受限的网络：由于大量网络数据包与相当少的可用带宽竞争，因此利用 QoS，管理员可以为包含音频或视频数据的数据包分配更高的优先级。 通过为这些数据包提供更高的优先级，与涉及文件传输、Web 浏览或数据库备份等内容的网络会话相比，音频和视频通信完成速度更快且中断更少。 这是因为用于文件传输或数据库备份的网络数据包分配有"最佳"优先级。

> [!NOTE]
> 一般来说，QoS 仅适用于内部网络的通信会话。 实施 QoS 时，配置服务器和路由器以支持在 Internet 或其他网络上可能不受支持的特定方式的数据包标记。 即使服务质量在其他网络上受支持，也不能保证 QoS 的配置方式与配置该服务的方式完全相同。 如果你使用的是 MPLS，则需要与 MPLS 提供商合作。

Skype for Business Server QoS，但强烈建议使用 QoS。 如果网络上遇到数据包丢失问题，可用解决方案是增加更多带宽或实施 QoS。 如果无法添加更多带宽，则实施 QoS 可能是解决此问题的唯一代价。

Skype for Business Server QoS 的完全支持：这意味着已使用 QoS 的组织可以轻松Skype for Business Server集成到其现有网络基础结构中。 为此，必须按照以下步骤操作：

- [为不基于 Skype for Business Server](../../manage/network-management/qos/enabling-qos-for-devices-that-are-not-based-on-windows.md)的设备启用 QoS Windows。 默认情况下，会针对运行其他操作系统的计算机和其他设备（如 iPhone）禁用 QoS。 尽管可以使用Skype for Business Server启用和禁用设备的服务质量，但通常无法使用该产品修改这些设备使用的 DSCP 代码。

- [为会议、应用程序和](../../manage/network-management/qos/configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)中介服务器配置端口范围和服务质量策略。 您必须为不同的数据包类型（如音频和视频）保留一组唯一的端口。 通过使用Skype for Business Server不会将属性值设置为 True 或 False 来启用或禁用 QoS。 而是通过配置端口范围，然后创建和应用组策略来启用 QoS。 如果您稍后决定不使用 QoS，您可以通过删除相应的组策略对象来"禁用"QoS。

- [为边缘服务器配置端口范围和服务质量策略](../../manage/network-management/qos/configuring-port-ranges-for-your-edge-servers.md)。 虽然不需要，但是可以将您的边缘服务器配置为与其他服务器使用相同的端口范围。 仅为边缘服务器的内部端配置 QoS 策略。 这是因为 QoS 设计用于内部网络而不是 Internet。

- 在 Skype for Business Server 中为客户端配置端口[范围和服务质量Skype for Business Server。](../../manage/network-management/qos/configuring-port-ranges-for-your-skype-clients.md) 这些端口范围仅适用于客户端计算机，并且通常不同于服务器上配置的端口范围。 请注意，Skype for Business Server不支持 QoS Windows操作系统，而不支持 qoS Windows 10。


> [!NOTE]
> 如果你使用的是 Windows Server 2012 或 Windows Server 2012 R2，你可能对可用于管理该平台上的 QoS 的新 Windows PowerShell cmdlet 集感兴趣。 有关详细信息，请参阅 Network [QoS Cmdlets in Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=285379)。

在白皮书 Lync [Server](https://www.microsoft.com/download/details.aspx?id=39084) 的网络规划、监控和疑难解答中也讨论了 QoS，并提供了其他详细信息和深度。 虽然内容明确引用了 Lync 2010 和 Lync 2013，但Skype for Business Server保持不变。

## <a name="see-also"></a>另请参阅
<a name="man_QOS"> </a>

[规划 IPv6 Skype for Business](ipv6.md)

[负载平衡要求Skype for Business](load-balancing.md)

[dns requirements for Skype for Business Server](dns.md)
