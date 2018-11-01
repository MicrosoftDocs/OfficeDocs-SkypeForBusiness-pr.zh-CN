---
title: Lync Server 2013：SIP 中继部署清单
TOCTitle: SIP 中继部署清单
ms:assetid: 94f4f03e-19d5-4198-92be-e4076dbb959a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398755(v=OCS.15)
ms:contentKeyID: 49313641
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 的 SIP 中继部署清单

 

_**上一次修改主题：** 2012-09-21_

在部署 SIP 中继之前，您和您的服务提供商必须交换有关各自 SIP 中继终结点的一些基本连接信息。

获取将连接到的每个 ITSP 网关的以下信息：

  - IP 地址

  - 完全限定域名 (FQDN)

> [!NOTE]  
> 服务提供商可能会要求您连接到多个 ITSP 网关。在这种情况下，必须配置每个 ITSP 网关与池中每个 中介服务器之间的连接。



您提供给服务提供商的信息取决于您的 SIP 中继连接类型：

  - 对于多协议标签交换 (MPLS) 或专用网络连接，向 ITSP 提供外围网络（也称为 Perimeter network、外围安全区域和屏蔽子网）中路由器的公共可路由的 IP 地址。请确认 ITSP 的网关或会话边界控制器 (SBC) 可以访问该地址。此外，向 ITSP 提供 中介服务器的 FQDN。

  - 对于虚拟专用网络 (VPN) 连接，向 ITSP 提供 VPN 服务器的 IP 地址。

## 证书注意事项

要确定是否需要 SIP 中继的证书，请向 ITSP 咨询协议支持：

1.  如果 ITSP 仅支持传输控制协议 (TCP)，则不需要证书。

2.  如果 ITSP 支持传输层安全性 (TLS)，则 ITSP 必须为您提供证书。

> [!NOTE]  
> SIP 可与实时传输协议 (RTP) 或安全实时传输协议 (SRTP) 结合使用，这些协议用于管理 IP 语音 (VoIP) 呼叫中的实际语音数据。



## 部署过程

要实现 Lync Server 端的 SIP 中继连接，请执行以下步骤：

1.  使用 Lync Server  拓扑生成器创建并配置 SIP 域拓扑。有关详细信息，请参阅部署文档中的 [在 Lync Server 2013 拓扑生成器中定义和配置拓扑](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)。

2.  使用 Lync Server 控制面板配置新 SIP 域的语音路由。有关详细信息，请参阅部署文档中的 [在 Lync Server 2013 中配置中继](lync-server-2013-configuring-trunks.md)。

3.  使用 **Test-CsPstnOutboundCall** cmdlet 测试连接。有关详细信息，请参阅 Lync Server 命令行管理程序文档或 Lync Server 命令行管理程序帮助。

