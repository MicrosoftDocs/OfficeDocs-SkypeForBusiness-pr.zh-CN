---
title: Lync Server 2013：SIP 中继
TOCTitle: SIP 中继
ms:assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398619(v=OCS.15)
ms:contentKeyID: 49313355
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 SIP 中继

 

_**上一次修改主题：** 2012-08-13_

会话初始协议 (SIP) 用于启动和管理基本电话服务和其他实时通信服务（例如即时消息、会议、状态检测和多媒体）的 IP 语音 (VoIP) 通信会话。本节提供实现 *SIP 中继* （一种 SIP 连接，可以扩展到本地网络以外）的规划信息。

## 什么是 SIP 中继？

SIP 中继是一种 IP 连接，在您的组织与防火墙以外的 Internet 电话服务提供商 (ITSP) 之间建立 SIP 通信链路。通常情况下，SIP 中继用于将组织的中央站点连接到 ITSP。在某些情况中，您也可以选择使用 SIP 中继将分支站点连接到 ITSP。

## SIP 中继与直接 SIP 连接

术语*中继*源自电路交换技术。它指的是连接电话交换设备的专用物理线路。与前置时分多路复用 (TDM) 中继类似，SIP 中继是两个单独的 SIP 网络（即 Lync Server 2013 企业和 ITSP）之间的连接。SIP 中继是可以通过任何支持的 SIP 中继连接类型建立的虚拟连接，这一点与电路交换中继不同。有关支持的连接类型的详细信息，请参阅[如何在 Lync Server 2013 中实施 SIP 中继？](lync-server-2013-how-do-i-implement-sip-trunking.md)。

而直接 SIP 连接指的是不能跨越本地网络边界的 SIP 连接（也就是说，它们连接到内部网络内的公用电话交换网 (PSTN) 网关或专用交换机 (PBX)）。有关如何将直接 SIP 连接与 Lync Server 2013 结合使用的详细信息，请参阅 [Lync Server 2013 中的直接 SIP 连接](lync-server-2013-direct-sip-connections.md)。

## 本节内容

  - [Lync Server 2013 中的 SIP 中继概述](lync-server-2013-overview-of-sip-trunking.md)

  - [如何在 Lync Server 2013 中实施 SIP 中继？](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [Lync Server 2013 中用于 SIP 中继的组件和拓扑](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [Lync Server 2013 中的分支站点 SIP 中继](lync-server-2013-branch-site-sip-trunking.md)

  - [Lync Server 2013 的 SIP 中继部署清单](lync-server-2013-sip-trunk-deployment-checklist.md)

