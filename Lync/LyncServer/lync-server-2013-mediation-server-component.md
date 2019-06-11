---
title: 'Lync Server 2013: 中介服务器组件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mediation Server component
ms:assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398399(v=OCS.15)
ms:contentKeyID: 48184239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1f3476f8b4e99b2abccb67f1d75446a126df03d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mediation-server-component-in-lync-server-2013"></a>Lync Server 2013 中的中介服务器组件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-21_

如果你部署了企业语音工作负荷, 则必须部署 Lync Server 2013、中介服务器。 本部分介绍基本功能、依赖关系、基本拓扑和规划指南。

中介服务器转换信号, 在某些配置中, 你的内部 Lync Server 2013、企业语音基础结构和公共交换电话网络 (PSTN) 网关或会话初始协议 (SIP) 干线之间的媒体。 在 Lync Server 2013 端, 中介服务器侦听单个相互 TLS (MTLS) 传输地址。 在网关端, 中介服务器侦听与拓扑文档中定义的中继相关联的所有关联的侦听端口。 所有合格网关必须支持 TLS，但也可以启用 TCP。 不支持 TLS 的网关将支持 TCP。

如果你的环境中还有现有的公共分支 Exchange (PBX), 则中介服务器处理企业语音用户和 PBX 之间的通话。 如果你的 PBX 是 IP PBX, 则可以在 PBX 和中介服务器之间创建直接 SIP 连接。 如果你的 PBX 是时间段多路传输 (TDM) PBX, 则还必须在中介服务器和 PBX 之间部署 PSTN 网关。

默认情况下, 中介服务器与前端服务器 collocated。 由于性能原因, 中介服务器也可以部署在独立的池中, 或者, 如果你部署 SIP 中继, 强烈建议使用独立池。

如果你将直接 SIP 连接部署到支持媒体绕过和 DNS 负载平衡的合格 PSTN 网关, 则不需要独立的中介服务器池。 不需要独立的中介服务器池, 因为合格的网关能够将 DNS 负载平衡到中介服务器池, 并且它们可以接收来自池中的任何中介服务器的流量。

我们还建议你在部署 IP-Pbx 或连接到 Internet 电话服务器提供商的会话边界控制器 (SBC) 时, 在前端池中 collocate 中介服务器, 前提是满足以下任何条件:

  - 将 IP PBX 或 SBC 配置为接收来自池中的任何中介服务器的流量, 并且可以将流量统一路由到池中的所有中介服务器。

  - IP-PBX 不支持媒体绕过, 但托管中介服务器的前端池可以处理语音转换, 以便不应用绕过媒体的呼叫。

你可以使用 Microsoft Lync Server 2013、计划工具评估你想要 collocate 中介服务器的前端池是否可以处理负载。 如果你的环境无法满足这些要求, 则必须部署独立的中介服务器池。

中介服务器的主要功能如下所示:

  - 在 Lync Server 端对 SRTP 进行加密和解密

  - 通过 TCP (对于不支持 TLS 的网关) 将 SIP 转换为通过相互 TLS 的 SIP

  - 在 Lync 服务器和中介服务器的网关对等之间转换媒体流

  - 将网络外部的客户端连接到内部 ICE 组件, 从而支持 NAT 和防火墙的媒体遍历

  - 充当网关不支持的呼叫流的媒介, 例如来自企业语音客户端的远程工作人员的呼叫

  - 在包含 SIP 中继的部署中, 使用 SIP 中继服务提供商提供 PSTN 支持, 从而无需 PSTN 网关

下图显示了在与基本 PSTN 网关和企业语音基础结构通信时, 中介服务器使用的信号和媒体协议。

**中介服务器使用的信号和媒体协议**

![中介服务器协议图](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "中介服务器协议图")

<div>


> [!NOTE]  
> 如果在 PSTN 网关和中介服务器之间的网络上使用 TCP 或 RTP/RTCP (而不是 SRTP 或 SRTCP), 我们建议你采取措施来帮助确保网络的安全和隐私。



</div>

<div>

## <a name="in-this-section"></a>本节内容

  - [Lync Server 2013 中的 M:N 主干](lync-server-2013-m-n-trunk.md)

  - [Lync Server 2013 中的呼叫允许控制和中介服务器](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [Lync Server 2013 中的增强型 9-1-1 (E9-1-1) 和中介服务器](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [Lync Server 2013 中的媒体绕过和中介服务器](lync-server-2013-media-bypass-and-mediation-server.md)

  - [Lync Server 2013 中中介服务器的组件和拓扑](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [Lync Server 2013 中的中介服务器部署指南](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

