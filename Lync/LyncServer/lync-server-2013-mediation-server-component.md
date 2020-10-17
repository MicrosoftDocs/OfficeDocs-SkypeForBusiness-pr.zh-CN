---
title: Lync Server 2013：中介服务器组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mediation Server component
ms:assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398399(v=OCS.15)
ms:contentKeyID: 48184239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8ddc21554ce57601f61e4b37d1988ca3e4dad65
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513749"
---
# <a name="mediation-server-component-in-lync-server-2013"></a>Lync Server 2013 中的中介服务器组件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-21_

如果部署企业语音工作负载，则必须部署 Lync Server 2013 （中介服务器）。 本节描述了基本功能、依赖关系、基本拓扑和规划指南。

中介服务器转换信号，在某些配置中，内部 Lync Server 2013、企业语音基础结构和公共交换电话网络之间的媒体 (PSTN) 网关或会话初始协议 (SIP) 中继。 在 Lync Server 2013 端，中介服务器侦听单个相互 TLS (MTLS) 传输地址。 在网关这一端，中介服务器侦听与拓扑文档中定义的中继关联的所有相关侦听端口。 所有合格网关必须支持 TLS，但也可以启用 TCP。 不支持 TLS 的网关将支持 TCP。

如果你的环境中还有现有的公共分支 Exchange (PBX) ，中介服务器将处理企业语音用户和 PBX 之间的呼叫。 如果你的 PBX 是 ip-pbx，则可以在 PBX 和中介服务器之间创建直接 SIP 连接。 如果你的 PBX 是时间分段多路传输 (TDM) PBX，则还必须在中介服务器和 PBX 之间部署 PSTN 网关。

默认情况下，中介服务器与前端服务器并置。 由于性能原因，中介服务器也可以部署在独立的池中，如果您部署 SIP 中继，则强烈建议使用独立池。

如果将直接 SIP 连接部署到支持媒体旁路和 DNS 负载平衡的合格 PSTN 网关，则不需要独立的中介服务器池。 若要将直接 SIP 连接部署到支持媒体旁路和 DNS 负载平衡的合格的 PSTN 网关，则不需要独立的中介服务器池，因为合格的网关能够将 DNS 负载平衡到中介服务器池，并且可以从池中的任何中介服务器接收通信。

如果已部署 IP-PBX 或连接到互联网电话服务供应商的会话边界控制器 (SBC)，只要满足以下其中一个条件，我们还建议您将中介服务器并置在前端池上：

  - IP-PBX 或 SBC 已配置为接收来自池中的任何中介服务器的通信，并且可将通信统一路由到池中的所有中介服务器。

  - Ip-pbx 不支持媒体旁路，但承载中介服务器的前端池可以处理对不应用媒体旁路的呼叫的语音转码。

您可以使用 Microsoft Lync Server 2013、规划工具来评估您要并置中介服务器的前端池是否可以处理负载。 如果您的环境不能满足这些要求，则必须部署独立的中介服务器池。

中介服务器的主要功能如下所示：

  - 在 Lync Server 端对 SRTP 进行加密和解密

  - 将 TCP 上的 SIP（针对不支持 TLS 的网关）转换为相互 TLS 上的 SIP

  - 在 Lync Server 和中介服务器的网关对等之间转换媒体流

  - 将网络外部的客户端连接到内部 ICE 组件，使媒体可以遍历 NAT 和防火墙

  - 充当网关不支持的呼叫流媒介，例如来自企业语音客户端的远程工作人员的呼叫

  - 在包含 SIP 中继的部署中，配合 SIP 中继服务提供商提供 PSTN 支持，从而不再需要 PSTN 网关

下图显示了在与基本 PSTN 网关和企业语音基础结构通信时，中介服务器使用的信号和媒体协议。

**中介服务器使用的信号和媒体协议**

![中介服务器协议图](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "中介服务器协议图")

<div>


> [!NOTE]  
> 如果您在网络中使用 TCP 或 RTP/RTCP (而不是 SRTP 或 SRTCP) 在 PSTN 网关和中介服务器之间，我们建议采取措施来帮助确保网络的安全和隐私。



</div>

<div>

## <a name="in-this-section"></a>本部分内容

  - [Lync Server 2013 中的 M:N 中继](lync-server-2013-m-n-trunk.md)

  - [Lync Server 2013 中的呼叫允许控制和中介服务器](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [Lync Server 2013 中的增强型 9-1-1 (E9-1-1) 和中介服务器](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [Lync Server 2013 中的媒体旁路和中介服务器](lync-server-2013-media-bypass-and-mediation-server.md)

  - [Lync Server 2013 中的中介服务器的组件和拓扑](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [Lync Server 2013 中的中介服务器的部署指南](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

