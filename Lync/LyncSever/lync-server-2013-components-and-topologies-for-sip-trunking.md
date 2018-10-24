---
title: Lync Server 2013：用于 SIP 中继的组件和拓扑
TOCTitle: 用于 SIP 中继的组件和拓扑
ms:assetid: 8ed9a9d0-517e-4f36-a131-22cdafa257fa
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398720(v=OCS.15)
ms:contentKeyID: 49313566
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中用于 SIP 中继的组件和拓扑

 

_**上一次修改主题：** 2012-09-21_

下图说明了 Lync Server 中的 SIP 中继拓扑。

**SIP 中继拓扑**

![SIP 中继拓扑](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "SIP 中继拓扑")

如图所示，企业网络与公用电话交换网 (PSTN) 服务提供商之间的连接使用 IP 虚拟专用网络 (VPN)。这个专用网络旨在提供 IP 连接、增强安全性和（可选的）获取服务质量 (QoS) 保证。由于 VPN 的特性，您无需为 SIP 信号流量使用传输层安全性 (TLS)，也无需为媒体流量使用安全实时传输协议 (SRTP)。因此，企业与服务提供商之间的连接由用于 SIP 的普通 TCP 连接以及用于通过 IP VPN 进行隧道传输的媒体的普通实时传输协议 (RTP)（通过 UDP）构成。确保 VPN 路由器之间的所有防火墙打开端口以允许 VPN 路由器进行通信，并且 VPN 路由器外部边缘上的 IP 地址公共可路由。

> [!IMPORTANT]  
> 请与服务提供商联系，以确定是否提供包括故障转移在内的高可用性支持。如果提供，则需要确定设置过程。例如，是否需要在每台 中介服务器上只配置一个 IP 地址和一个 SIP 中继，或者，是否需要在每台 中介服务器上配置多个 SIP 中继？<br />
如果您具有多个 中央站点，还可以询问服务提供商是否有能力启用与另一个 中央站点的连接。


> [!NOTE]  
> 对于 SIP 中继，强烈建议您部署独立的 中介服务器。有关详细信息，请参阅部署文档中的 <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">在 Lync Server 2013 中部署中介服务器和定义对等方</a>。



## 为 SIP 中继保护中介服务器的安全

为安全起见，应为两个 VPN 路由器之间的每个连接设置一个虚拟 LAN (VLAN)。设置 VLAN 的实际过程因路由器制造商而异。请与路由器供应商联系以获取详细信息。

建议您遵循下列准则：

  - 在外围网络（也称为 DMZ、外围安全区域和屏蔽子网）中设置 中介服务器和 VPN 路由器间的虚拟 LAN (VLAN)。

  - 不允许将广播数据包或多播数据包从路由器传输到 VLAN。

  - 阻止所有将流量从路由器路由到除 中介服务器之外的任何位置的路由规则。

如果使用 VPN 服务器，建议您遵循下列准则：

  - 设置 VPN 服务器和 中介服务器之间的 VLAN。

  - 不允许将广播数据包或多播数据包从 VPN 服务器传输到 VLAN。

  - 阻止所有将 VPN 服务器流量路由到除 中介服务器之外的任何位置的路由规则。

  - 使用基本路由封装 (GRE) 加密 VPN 上的数据。

