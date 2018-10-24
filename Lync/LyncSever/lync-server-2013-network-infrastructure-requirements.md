---
title: Lync Server 2013 中的网络基础结构要求
TOCTitle: Lync Server 2013 中的网络基础结构要求
ms:assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425841(v=OCS.15)
ms:contentKeyID: 49312475
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的网络基础结构要求

 

_**上一次修改主题：** 2014-08-28_

Lync Server 2013 拓扑中每台服务器的网络适配器卡都必须至少支持 1 千兆位每秒 (Gbps)。通常，应该使用低延迟和高带宽的局域网 (LAN) 来连接 Lync Server 拓扑中的所有服务器角色。LAN 的大小取决于拓扑的大小：

  - 在 标准版 拓扑中，服务器应位于支持 1 Gbps 以太网或等效技术的网络中。

  - 在前端池拓扑中，大多数服务器应位于支持 1 Gbps 以上速率的网络中，尤其是在支持音频/视频 (A/V) 会议和应用程序共享时。

对于公用电话交换网 (PSTN) 集成，可以使用 T1/E1 线路或 SIP 中继进行集成。

## 音频/视频网络要求

Lync Server 部署中的音频/视频 (A/V) 网络要求包括以下内容：

  - 如果使用 DNS 负载平衡部署单个边缘服务器或边缘池，则可以配置外部防火墙作为 NAT。不能配置内部防火墙作为 NAT。有关这些要求的详细信息，请参阅规划文档中的[确定 Lync Server 2013 的外部 A/V 防火墙和端口要求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)。
    
    > [!IMPORTANT]
    > 如果具有边缘池并且正在使用硬件负载平衡器，则必须在每个边缘服务器上使用公用 IP 地址，并且不能对服务器或 NAT 设备上的池使用 NAT（例如，防火墙或其他将产生 NAT 入站或出站流量的基础架构设备）。有关详细信息，请参阅“规划外部用户访问”文档中的<a href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Lync Server 2013 中的端口摘要 - 使用硬件负载平衡器的扩展的合并边缘</a>。


  - 如果您的组织使用了服务质量 (QoS) 基础结构，则媒体子系统应设计为在此现有基础结构中工作。

  - 如果使用 Internet 协议安全性 (IPsec)，建议在用于 A/V 流量的端口范围内禁用 IPsec。有关详细信息，请参阅规划文档中的 [Lync Server 2013 中的 IPsec 例外](lync-server-2013-ipsec-exceptions.md)。

要确保最佳媒体质量，请执行以下操作：

  - 设置网络链接，使之在高峰使用时段支持每个音频流 65 千位每秒 (Kbps) 和每个视频流（如果启用）500 Kbps 的吞吐量。一个双向音频或视频会话由两个流构成。

  - 为了应对高于这一级别的意外流量峰值以及随时间增长的使用量，Lync Server 媒体终结点可以适应不断变化的网络条件，支持三倍于音频和视频吞吐量（请参阅上一段落）的负载，同时仍能保持可接受的质量。但是，不要认为这种适应性能支持未充分设置的网络。在未充分设置的网络中，Lync Server 媒体终结点动态处理不断变化的网络条件（例如临时大量数据包丢失）的能力有所下降。

  - 如果网络链路的设置成本很高，而且难于操作，可能就需要考虑设置较低的流量。在这种情况下，可以使 Lync Server 媒体终结点的弹性吸收流量与高峰流量级别之间的差异，代价是语音质量有所下降。此外，可用于吸收流量中的突发峰值的空间也会减少。

  - 对于短期内无法正确配置的链路（例如 WAN 链路很差的站点），考虑对某些用户禁用视频。

  - 配置网络，确保在高峰负载下的最大端到端延迟为 150 毫秒 (ms)。延迟是网络的损耗现象，Lync Server 媒体组件对此无能为力，因此找到并消除这些薄弱点是非常重要的。

  - 对于运行防病毒软件的服务器，为了提供最佳性能和音频质量，必须包括例外列表中所有运行 Lync Server 的服务器。

## 会议网络要求

用于从 Internet Information Services (IIS) 服务器下载会议内容的带宽取决于上载内容的大小。

