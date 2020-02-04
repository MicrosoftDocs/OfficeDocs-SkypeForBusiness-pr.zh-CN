---
title: Lync Server 2013：中介服务器的组件和拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Mediation Server
ms:assetid: 71397168-36c3-4d21-b8ef-db6a751634ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398537(v=OCS.15)
ms:contentKeyID: 48184487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62516645266f67b7be61154b45afd00107ec3814
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a>Lync Server 2013 中中介服务器的组件和拓扑

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-21_

本主题介绍了中介服务器依赖的组件以及可以在其中部署中介服务器的拓扑

<div>

## <a name="dependencies"></a>依赖项

中介服务器具有以下依赖关系：

  - **注册.** 必需。 注册机构是中介服务器与 Lync Server 2013 网络交互中的信号的下一跃点。 请注意，除了在包含中介服务器的独立池中安装外，还可以在前端服务器上与注册机构一起 collocated。 注册机构在 Survivable 分支装置上使用中介服务器和 PSTN 网关 collocated。

  - **监视服务器。** 可选，但强烈建议使用。 监视服务器允许中介服务器记录与其媒体会话关联的质量指标。

  - **边缘服务器。** 外部用户支持所必需。 Edge 服务器允许中介服务器与位于 NAT 或防火墙后面的用户进行交互。

</div>

<div>

## <a name="topologies"></a>朴

Lync Server 2013 （中介服务器）默认情况下 collocated 在标准版服务器、前端池或 Survivable 分支装置上使用注册机构的实例。 前端池中的所有中介服务器的配置都必须相同。

在性能有问题的情况下，最好是在专用独立池中部署一个或多个中介服务器。 或者，如果你要部署 SIP 中继，我们建议你部署独立的中介服务器池。

如果你将直接 SIP 连接部署到支持媒体绕过和 DNS 负载平衡的合格 PSTN 网关，则不需要独立的中介服务器池。 不需要独立的中介服务器池，因为合格的网关能够将 DNS 负载平衡到中介服务器池，并且它们可以接收来自池中的任何中介服务器的流量。

我们还建议你在部署 IP-Pbx 或连接到 Internet 电话服务器提供商的会话边界控制器（SBC）时，在前端池中 collocate 中介服务器，前提是满足以下任何条件：

  - 将 IP PBX 或 SBC 配置为接收来自池中的任何中介服务器的流量，并且可以将流量统一路由到池中的所有中介服务器。

  - IP-PBX 不支持媒体绕过，但托管中介服务器的前端池可以处理语音转换，以便不应用绕过媒体的呼叫。

你可以使用 Microsoft Lync Server 2013、计划工具评估你想要 collocate 中介服务器的前端池是否可以处理负载。 如果你的环境无法满足这些要求，则必须部署独立的中介服务器池。

有关要部署的拓扑的详细信息，请参阅[Lync server 2013 中的中介服务器部署指南](lync-server-2013-deployment-guidelines-for-mediation-server.md)。

下图显示了由通过 WAN 链路连接的两个站点组成的简单拓扑。 在站点1的前端池中的注册机构 collocated 的中介服务器。 站点1处的中介服务器控制站点1和站点2上的网关的 PSTN 网关。 在此拓扑中，已在全局范围内启用媒体旁路以使用站点和区域信息，并且到每个 PSTN 网关（GW1 和 GW2）的中继都已启用旁路。

**通过 WAN 链路与站点 1 的中介服务器和站点 2 的 PSTN 网关相连接的站点示例**

![带中介服务器 WAN 网关的语音拓扑](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "带中介服务器 WAN 网关的语音拓扑")

下图显示了一个简单的拓扑，其中中介服务器在站点1上与 collocated 前端池的注册机构进行了连接，并与站点1上的 IP PBX 具有直接 SIP 连接。 在此图中，中介服务器还控制站点2上的 PSTN 网关。 假设 Lync 用户同时存在于站点1和2。 此外，假设在发送到由 IP PBX 控制的媒体终结点之前，必须由所有源自 Lync 终结点的媒体遍历到 IP PBX 的媒体处理器。 在此拓扑中，已在全局范围内启用媒体旁路以使用站点和区域信息，并且到 PBX 和 PSTN 网关的中继已启用媒体旁路。

**通过 WAN 链路与站点 1 的中介服务器和站点 2 的 PBX 相连接的站点的示例**

![语音拓扑中介服务器 WAN PBX](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "语音拓扑中介服务器 WAN PBX")

有关规划 PBX 拓扑的详细信息，请参阅[lync server 2013 中的中介服务器部署指南](lync-server-2013-deployment-guidelines-for-mediation-server.md)和[lync server 2013 中的直接 SIP 部署选项](lync-server-2013-direct-sip-deployment-options.md)。

本主题中的最后一个图显示了一个拓扑，其中中介服务器连接到 Internet 电话服务提供商的 SBC。 有关 SIP 中继拓扑的详细信息，请参阅[Lync Server 2013 中的 SIP 中继](lync-server-2013-sip-trunking.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

