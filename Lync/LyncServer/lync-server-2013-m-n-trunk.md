---
title: 'Lync Server 2013: M:N 主干'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: M:N trunk
ms:assetid: dc4c5d66-297c-48a5-91b9-b9b8ce44a6e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398971(v=OCS.15)
ms:contentKeyID: 48185592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a99a76c2291b8ffcfcb1c68367ab6a999211c24f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829916"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mn-trunk-in-lync-server-2013"></a>Lync Server 2013 中的 M:N 主干

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-01_

Lync Server 2013 支持从以前的版本进行呼叫路由的主干定义中更大的灵活性。 主干是中介服务器和侦听端口号与网关和侦听端口号之间的逻辑关联。 这意味着: 中介服务器可以有多个中继到同一网关;中介服务器可以有多个中继到不同的网关;与网关相反, 网关可以有多个中继到不同的中介服务器。

在使用拓扑生成器将网关添加到 Lync 拓扑时, 仍需要创建根主干。 给定中介服务器可以处理的网关数取决于高峰时段内服务器的处理能力。 如果你在硬件上部署超过 Lync Server 2013 最低硬件要求的中介服务器, 如支持文档中的[Lync server 2013 支持的硬件](lync-server-2013-supported-hardware.md)中所述, 然后是对活动非绕过次数的估计值呼叫独立中介服务器的处理时间大约是1000。 在满足这些规范的硬件上部署时, 中介服务器应执行转换, 但仍可以为多个网关路由呼叫, 即使网关不支持媒体旁路也是如此。

定义呼叫路线时, 指定与该路线关联的中继, 但不指定与该路由关联的中介服务器。 而是使用拓扑生成器将中继与中介服务器相关联。 换句话说, 路由确定用于呼叫的主干, 随后, 与该主干相关联的中介服务器将发送该呼叫的信号。

中介服务器可以作为池进行部署;此池可以与前端池 collocated, 也可以作为独立的池进行部署。 当使用前端池的中介服务器 collocated 时, 池大小最多为 12 (注册池大小的限制)。 总之, 这些新功能提高了中介服务器的可靠性和部署灵活性, 但它们需要在以下对等实体中具有关联的功能:

  - **PSTN 网关。** Lync Server 2013 合格的网关必须实现 DNS 负载平衡, 这使限定的公共交换电话网络 (PSTN) 网关能够充当一个中介服务器池的负载平衡器, 从而在池中对呼叫进行负载平衡。

  - **会话边界控制器。** 对于 SIP 中继，对等实体是 Internet 电话服务提供商的会话边界控制器 (SBC)。 从中介服务器池到 SBC 的方向, SBC 可以从池中的任何中介服务器接收连接。 在从 SBC 到池中的方向上, 流量可以发送到池中的任何中介服务器。 实现此功能的一个方法是通过 DNS 负载平衡（如果服务提供商和 SBC 支持）。 另一种方法是为服务提供商提供池中所有中介服务器的 IP 地址, 并且服务提供商将其 SBC 中的这些地址设置为每个中介服务器的单独 SIP 干线。 然后，服务提供商将处理自己的服务器的负载平衡。 并非所有服务提供商或 SBC 都可以支持这些功能。 此外，服务提供商可能会对此功能收取额外费用。 通常，每个到 SBC 的 SIP 中继按月收费。

  - **IP-PBX。** 从中介服务器池到 IP PBX SIP 终止方向, IP PBX 可以从池中的任何中介服务器接收连接。 在从 IP PBX 到池中的方向上, 流量可以发送到池中的任何中介服务器。 由于大多数 IP Pbx 不支持 DNS 负载平衡, 因此我们建议将单个直接 SIP 连接从 IP PBX 定义到池中的每个中介服务器。 然后，IP-PBX 将通过向中继组分发流量处理自己的负载平衡。 假定中继组在 IP-PBX 中具有一组一致的路由规则。 无论特定的 IP PBX 是否支持此中继组概念, 以及它与 IP PBX 自身的冗余和群集体系结构的交集, 都需要先确定它们, 然后才能确定中介服务器群集是否可以正确地与 IP PBX 交互。

中介服务器池必须具有与其交互的对等网关的统一视图。 这意味着池中的所有成员都能从配置存储访问对等网关的同一定义，并且都可能针对传出呼叫与其进行交互。 因此, 无法划分池, 因此某些中介服务器仅与特定网关对等的传出呼叫进行通信。 如果需要此类分段, 则必须使用单独的中介服务器池。 例如，如果与池进行交互的 PSTN 网关、SIP 中继或 IP-PBX 中的相关功能（如本主题中前面所述）不存在，则此情况适用。

特定 PSTN 网关、IP PBX 或 SIP 中继对等可以路由到多个中介服务器或中继。 特定中介服务器池可以控制的网关数取决于使用媒体绕过的调用数量。 如果大量呼叫使用媒体绕过, 则池中的中介服务器可以处理更多调用, 因为只有信号层处理是必需的。

</div>

<span> </span>

</div>

</div>

</div>

