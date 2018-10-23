---
title: Lync Server 2013：规划呼叫允许控制
TOCTitle: 规划呼叫允许控制 (CAC)
ms:assetid: ca367138-adf5-4119-bc40-5ddf335ed22f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398842(v=OCS.15)
ms:contentKeyID: 49314233
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中规划呼叫允许控制

 

_**上一次修改主题：** 2012-09-21_

对于基于 IP 的统一通信 (UC) 应用程序，例如电话、视频和应用程序共享，通常不会将企业网络的可用带宽视为 LAN 环境内的限制因素。但是，在相互连接站点的 WAN 链路中，可以限制网络带宽。当过多网络流量通过 WAN 链路时，将使用当前的诸如队列、缓冲和数据包丢弃等机制解决拥塞问题。额外的流量通常会延迟，直到网络拥塞问题得以缓解，或者必要时会丢弃流量。对于这些情况下的传统数据流量，接收客户端可以恢复。对于实时流量（如统一通信），则不能采用这种方式解决网络拥塞问题，因为统一通信流量对延迟和数据包丢失非常敏感。WAN 上的拥塞会导致用户的用户体验质量 (QoE) 降低。对于发生拥塞时的实时流量，最好拒绝呼叫，而不是提供质量欠佳的连接。

呼叫允许控制 (CAC) 可确定是否有足够的网络带宽来建立质量可接受的实时会话。在 Lync Server 2013 中，CAC 仅控制音频和视频的实时流量，但不会影响数据流量。如果默认 WAN 路径不具备所需的带宽，则 CAC 可尝试通过 Internet 路径或公用电话交换网 (PSTN) 路由呼叫。CAC 仅在 Lync Server 中可用。

本节介绍了呼叫允许控制功能，并解释了如何规划 CAC。

> [!NOTE]  
> Lync Server 有三项高级 企业语音功能：呼叫允许控制、紧急服务 (E9-1-1) 和媒体旁路。有关这三项功能共同的规划信息的概述，请参阅 <a href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Lync Server 2013 中高级企业语音功能的网络设置</a>。



## 本部分内容

  - [Lync Server 2013 中的呼叫允许控制概述](lync-server-2013-overview-of-call-admission-control.md)

  - [在 Lync Server 2013 中定义呼叫允许控制要求](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [示例：在 Lync Server 2013 中收集呼叫允许控制要求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [Lync Server 2013 中 CAC 的组件和拓扑](lync-server-2013-components-and-topologies-for-cac.md)

  - [Lync Server 2013 中呼叫允许控制的最佳做法](lync-server-2013-best-practices-for-call-admission-control.md)

  - [Lync Server 2013 中呼叫允许控制的部署清单](lync-server-2013-deployment-checklist-for-call-admission-control.md)

