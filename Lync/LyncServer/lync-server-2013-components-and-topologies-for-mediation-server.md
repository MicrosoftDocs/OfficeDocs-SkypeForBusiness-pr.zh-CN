---
title: Lync Server 2013：中介服务器的组件和拓扑
description: Lync Server 2013：中介服务器的组件和拓扑。
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
ms.openlocfilehash: befd244508db9c98d565a76301e150da98708522
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576848"
---
# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a>Lync Server 2013 中的中介服务器的组件和拓扑

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-21_

本主题介绍了中介服务器依赖的组件以及可在其中部署中介服务器的拓扑

<div>

## <a name="dependencies"></a>相关性

中介服务器具有以下依存关系：

  - **注册.** 必填。 注册器是中介服务器与 Lync Server 2013 网络的交互中的信号的下一个跃点。 请注意，除了安装在仅包含中介服务器的独立池之外，中介服务器还可以与注册器一起并置在前端服务器上。 注册器与 Survivable 分支设备上的中介服务器和 PSTN 网关并置。

  - **监控服务器。** 可选，但强烈建议。 监控服务器允许中介服务器记录与其媒体会话相关的质量指标。

  - **边缘服务器。** 外部用户支持的必需项。 通过边缘服务器，中介服务器可以与位于 NAT 或防火墙后面的用户进行交互。

</div>

<div>

## <a name="topologies"></a>拓扑

Lync Server 2013 （中介服务器）默认情况下并置具有 Standard Edition Server、前端池或 Survivable 分支设备上的注册器实例。 前端池中的所有中介服务器都必须进行相同的配置。

在性能问题的情况下，最好在专用独立池中部署一个或多个中介服务器。 或者，如果您正在部署 SIP 中继，我们建议您部署独立的中介服务器池。

如果将直接 SIP 连接部署到支持媒体旁路和 DNS 负载平衡的合格 PSTN 网关，则不需要独立的中介服务器池。 若要将直接 SIP 连接部署到支持媒体旁路和 DNS 负载平衡的合格的 PSTN 网关，则不需要独立的中介服务器池，因为合格的网关能够将 DNS 负载平衡到中介服务器池，并且可以从池中的任何中介服务器接收通信。

如果已部署 IP-PBX 或连接到互联网电话服务供应商的会话边界控制器 (SBC)，只要满足以下其中一个条件，我们还建议您将中介服务器并置在前端池上：

  - IP-PBX 或 SBC 已配置为接收来自池中的任何中介服务器的通信，并且可将通信统一路由到池中的所有中介服务器。

  - Ip-pbx 不支持媒体旁路，但承载中介服务器的前端池可以处理对不应用媒体旁路的呼叫的语音转码。

您可以使用 Microsoft Lync Server 2013、规划工具来评估您要并置中介服务器的前端池是否可以处理负载。 如果您的环境不能满足这些要求，则必须部署独立的中介服务器池。

有关要部署的拓扑的详细信息，请参阅 [Lync server 2013 中的中介服务器部署指南](lync-server-2013-deployment-guidelines-for-mediation-server.md)。

下图显示了由通过 WAN 链路连接的两个站点组成的简单拓扑。 中介服务器与在站点1的前端池上的注册器并置。 站点1上的中介服务器控制站点1和站点2上的网关的 PSTN 网关。 在此拓扑中，已在全局范围内启用媒体旁路以使用站点和区域信息，并且到每个 PSTN 网关（GW1 和 GW2）的中继都已启用旁路。

**通过 WAN 链路与站点 1 的中介服务器和站点 2 的 PSTN 网关相连接的站点示例**

![具有中介服务器 WAN 网关的语音拓扑](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "具有中介服务器 WAN 网关的语音拓扑")

下图显示了一个简单的拓扑，其中中介服务器与在站点1上的注册器在前端池上并置，并具有站点1与 IP PBX 的直接 SIP 连接。 在此图中，中介服务器还控制站点2的 PSTN 网关。 假定 Lync 用户同时存在于站点1和2。 此外，还假定在发送到由 ip-pbx 控制的媒体终结点之前，必须由源自 Lync 终结点的所有媒体遍历的 ip-pbx 的媒体处理器。 在此拓扑中，已在全局范围内启用媒体旁路以使用站点和区域信息，并且到 PBX 和 PSTN 网关的中继已启用媒体旁路。

**通过 WAN 链路与站点 1 的中介服务器和站点 2 的 PBX 相连接的站点的示例**

![语音拓扑中介服务器 WAN PBX](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "语音拓扑中介服务器 WAN PBX")

有关规划 PBX 拓扑的详细信息，请参阅 lync server [2013 中的中介服务器部署指南](lync-server-2013-deployment-guidelines-for-mediation-server.md) 和 [lync server 2013 中的直接 SIP 部署选项](lync-server-2013-direct-sip-deployment-options.md)。

本主题中的最后一个图显示了中介服务器连接到 Internet 电话服务提供商的 SBC 的拓扑。 有关 SIP 中继拓扑的详细信息，请参阅 [Lync Server 2013 中的 SIP 中继](lync-server-2013-sip-trunking.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

