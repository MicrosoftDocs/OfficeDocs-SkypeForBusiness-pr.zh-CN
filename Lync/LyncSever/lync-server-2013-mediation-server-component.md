---
title: Lync Server 2013：中介服务器组件
TOCTitle: 中介服务器组件
ms:assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398399(v=OCS.15)
ms:contentKeyID: 49312958
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的中介服务器组件

 

_**上一次修改主题：** 2012-09-21_

如果部署 企业语音工作负荷，则必须部署 Lync Server 2013中介服务器。本节描述了基本功能、依赖关系、基本拓扑和规划指南。

中介服务器转换内部 Lync Server 2013企业语音基础结构与公用电话交换网 PSTN (PSTN) 网关或会话初始协议 (SIP) 中继之间的信号以及某些配置中的媒体。在 Lync Server 2013 这一端， 中介服务器侦听单个相互 TLS (MTLS) 传输地址。在网关这一端，中介服务器侦听与拓扑文档中定义的中继关联的所有相关侦听端口。所有合格网关必须支持 TLS，但也可以启用 TCP。不支持 TLS 的网关将支持 TCP。

如果您的环境中还有现有公用交换机 (PBX)， 中介服务器将处理 企业语音用户与 PBX 之间的呼叫。如果您的 PBX 是 IP-PBX，则可以在 PBX 和 中介服务器之间建立直接 SIP 连接。如果您的 PBX 是时分多路复用 (TDM) PBX，则还必须在 中介服务器和 PBX 之间部署 PSTN 网关。

中介服务器默认与 前端服务器并置。为提高性能， 中介服务器还可以部署在独立的池中，或者如果部署 SIP 中继，则强烈建议部署在独立的池中。

如果部署与支持媒体旁路和 DNS 负载平衡的合格 PSTN 网关的直接 SIP 连接，则不必使用独立的 中介服务器池，因为合格网关可以对中介服务器池进行 DNS 负载平衡，并且可以接收来自池中任何 中介服务器的流量。

只要满意任一以下条件，我们还建议您在部署 IP-PBX 之后在 前端池上并置 中介服务器，或者连接到 Internet 电话服务提供商的会话边界控制器 (SBC)：

  - IP-PBX 或 SBC 已配置为接收来自池中的任何 中介服务器的通信，并且可将通信统一路由到池中的所有 中介服务器。

  - IP-PBX 不支持媒体旁路，但承载 中介服务器的 前端池可为不适用媒体旁路的呼叫处理语音代码转换。

您可以使用 Microsoft Lync Server 2013 规划工具来评估要并置 中介服务器的 前端池是否能够处理负载。如果您的环境不能满足这些要求，则必须部署独立的 中介服务器池。

中介服务器的主要功能如下所示：

  - 在 Lync Server 这一端加密和解密 SRTP。

  - 将 TCP 上的 SIP（针对不支持 TLS 的网关）转换为相互 TLS 上的 SIP

  - 转换 Lync Server 与 中介服务器的对等网关之间的媒体流

  - 将网络外部的客户端连接到内部 ICE 组件，使媒体可以遍历 NAT 和防火墙

  - 充当网关不支持的呼叫流（例如，来自 企业语音客户端上的远程工作者的呼叫）的中介

  - 在包含 SIP 中继的部署中，配合 SIP 中继服务提供商提供 PSTN 支持，从而不再需要 PSTN 网关

下图显示了 中介服务器在与基本 PSTN 网关和 企业语音基础结构进行通信时所使用的信号和媒体协议。

**中介服务器使用的信号和媒体协议**

![中介服务器协议图](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "中介服务器协议图")

> [!NOTE]  
> 如果在 PSTN 网关与 中介服务器之间的网络上使用 TCP 或 RTP/RTCP（而非 SRTP 或 SRTCP），建议采取一些措施以帮助确保网络的安全和隐私。



## 本节内容

  - [Lync Server 2013 中的 M:N 中继](lync-server-2013-m-n-trunk.md)

  - [Lync Server 2013 中的呼叫允许控制和中介服务器](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [Lync Server 2013 中的增强型 9-1-1 (E9-1-1) 和中介服务器](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [Lync Server 2013 中的媒体绕过和中介服务器](lync-server-2013-media-bypass-and-mediation-server.md)

  - [Lync Server 2013 中中介服务器的组件和拓扑](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [Lync Server 2013 中介服务器部署准则](lync-server-2013-deployment-guidelines-for-mediation-server.md)

