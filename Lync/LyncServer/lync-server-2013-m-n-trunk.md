---
title: Lync Server 2013： M:N 中继
description: Lync Server 2013： M:N 中继。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: M:N trunk
ms:assetid: dc4c5d66-297c-48a5-91b9-b9b8ce44a6e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398971(v=OCS.15)
ms:contentKeyID: 48185592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e0bcee237128046985b5313a47872ad83bf6513
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542558"
---
# <a name="mn-trunk-in-lync-server-2013"></a>Lync Server 2013 中的 M:N 中继

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-01_

在以前的版本中，Lync Server 2013 支持用于呼叫路由的中继定义的更大灵活性。 中继是中介服务器和侦听端口号与网关和侦听端口号之间的逻辑关联。 这意味着有以下几种情况：中介服务器可以有多个中继到同一个网关;中介服务器可以有多个中继到不同的网关;与之相反，网关可以有多个中继到不同的中介服务器。

使用拓扑生成器向 Lync 拓扑添加网关时，仍需要创建根中继。 给定中介服务器可以处理的网关数取决于服务器在高峰忙时段处理的容量。 如果在硬件上部署超过 Lync Server 2013 最低硬件要求的中介服务器（如可支持性文档中的 [Lync server 2013 支持的硬件](lync-server-2013-supported-hardware.md) 中所述），则对独立中介服务器可以处理的活动非绕过次数的估计值约为1000个呼叫。 当在符合这些规范的硬件上部署时，中介服务器应执行转码，但仍可以路由多个网关的呼叫，即使网关不支持媒体旁路。

在定义呼叫路由时，请指定与该路由关联的中继，但不指定与该路由关联的中介服务器。 相反，您可以使用拓扑生成器将中继与中介服务器相关联。 换句话说，路由决定了用于呼叫的中继，随后与该中继关联的中介服务器将发送该呼叫的信号。

中介服务器可以部署为池;可以使用前端池并置此池，也可以将其作为独立池进行部署。 当中介服务器与前端池并置时，池大小最多可以为 12 (注册器池大小) 的限制。 总之，这些新功能提高了中介服务器的可靠性和部署灵活性，但它们需要在以下对等实体中具有关联功能：

  - **PSTN 网关。** Lync Server 2013 合格的网关必须实现 DNS 负载平衡，从而使合格的公用电话交换电话网络 (PSTN) 网关充当一个中介服务器池的负载平衡器，从而在池中对呼叫进行负载平衡。

  - **会话边界控制器。** 对于 SIP 中继，对等实体是 Internet 电话服务提供商 (SBC) 的会话边界控制器。 从中介服务器池到 SBC 的方向，SBC 可以接收来自池中任何中介服务器的连接。 在从 SBC 到池的方向上，可以将流量发送到池中的任何中介服务器。 实现这一点的一种方法是通过 DNS 负载平衡（如果服务提供商和 SBC 支持）。 另一种方法是为服务提供商提供池中所有中介服务器的 IP 地址，并且服务提供程序将其 SBC 中的这些地址设置为每个中介服务器的单独 SIP 中继。 然后，服务提供商将处理其自己的服务器的负载平衡。 并非所有服务提供商或 SBCs 都可以支持这些功能。 此外，服务提供商可能会对此功能收取额外费用。 通常情况下，每个针对 SBC 的 SIP 中继都会产生月费。

  - **IP-PBX。** 从中介服务器池到 ip-pbx SIP 终止方向，ip-pbx 可以从池中的任何中介服务器接收连接。 在从 ip-pbx 到池的方向上，可以将流量发送到池中的任何中介服务器。 由于大多数 IP-PBXs 不支持 DNS 负载平衡，因此我们建议将单个直接 SIP 连接从 IP-PBX 定义为池中的每个中介服务器。 然后，IP-PBX 将通过在中继组中分布流量来处理自己的负载平衡。 假定中继组在 ip-pbx 中具有一组一致的路由规则。 在确定中介服务器群集是否可以正确地与 ip-pbx 进行交互之前，特定的 ip-pbx 是否支持此中继组概念以及它与 IP-PBX 自己的冗余和群集体系结构的相交之处需要确定。

中介服务器池必须具有与其交互的对等网关的统一视图。 这意味着，池的所有成员都从配置存储访问相同的对等网关的定义，并且可能会与传出呼叫进行交互。 因此，无法对池进行分段，以便某些中介服务器仅与特定的网关对等方通信以进行传出呼叫。 如果需要此类分段，则必须使用单独的中介服务器池。 例如，如果 PSTN 网关、SIP 中继或 IP-PBXs 中的相关功能与池交互（如本主题前面所述）不存在，则会出现这种情况。

特定 PSTN 网关、ip-pbx 或 SIP 中继对等方可以路由到多个中介服务器或中继。 特定中介服务器池可以控制的网关数取决于使用媒体旁路的呼叫数。 如果大量呼叫使用媒体旁路，则池中的中介服务器可以处理更多的呼叫，因为只有信号层处理是必要的。

</div>

<span> </span>

</div>

</div>

</div>

