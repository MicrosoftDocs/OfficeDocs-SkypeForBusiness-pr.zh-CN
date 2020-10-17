---
title: Lync Server 2013 针对具有多个数据中心的大型组织的参考拓扑
description: Lync Server 2013 针对具有多个数据中心的大型组织的参考拓扑。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for large organizations with multiple data centers
ms:assetid: 9a6aeae6-629b-49e6-9804-7ef369d7c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398797(v=OCS.15)
ms:contentKeyID: 48184887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfb88bd59e4bc27aefbdc94fdf53f094a09998f4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567598"
---
# <a name="reference-topology-for-lync-server-2013-in-large-organizations-with-multiple-data-centers"></a>具有多个数据中心的大型组织中 Lync Server 2013 的参考拓扑

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-22_

具有多个数据中心的大型组织的参考拓扑支持适用于具有多个中央站点的各种规模的组织。下图中的具体拓扑适用于具有 50,000 个用户的组织，其中 20,000 个用户位于中央站点 A，20,000 个用户位于中央站点 B，总共 10,000 个用户位于中央站点 C 和分支站点。该图中显示的拓扑类型可满足具有任意数量用户的组织。

除了前端服务器池提供的高可用性之外，此拓扑还添加了灾难恢复支持。 中央站点 A 和 B 上的前端池配对在一起。 如果其中一个池不可用，则管理员可将受影响用户的服务转移到位于不受影响的站点上的配对池中。

此拓扑分为多幅图显示，首先是概述，然后是中央站点的详细视图。

**具有多个数据中心的大型组织的参考拓扑概述**

![多个数据中心的参考拓扑](images/Gg398797.471e1ce9-be11-44b9-9f4a-59e0551b7b30(OCS.15).jpg "多个数据中心的参考拓扑")

**大型组织的参考拓扑：中央站点 A 的详细视图**

![dab33f19-e77b-42da-9047-858fb9851264](images/Gg398797.dab33f19-e77b-42da-9047-858fb9851264(OCS.15).jpg "dab33f19-e77b-42da-9047-858fb9851264")

**大型组织的参考拓扑：中央站点 B 的详细视图**

![5ccaf1d4-bd53-4cb7-96fe-723147334e7f](images/Gg398797.5ccaf1d4-bd53-4cb7-96fe-723147334e7f(OCS.15).jpg "5ccaf1d4-bd53-4cb7-96fe-723147334e7f")

**大型组织的参考拓扑：中央站点 C 的详细视图**

![7238ca40-340c-491f-b497-ddc2665dadb6](images/Gg398797.7238ca40-340c-491f-b497-ddc2665dadb6(OCS.15).jpg "7238ca40-340c-491f-b497-ddc2665dadb6")

  - **前端池配对以启用灾难恢复。**    站点 A 和站点 B 上的前端池相互配对，以提供灾难恢复支持。 如果一个站点上的池发生故障，则管理员可以将该站点中的用户故障转移到另一个站点上的配对的前端池，同时对用户的服务中断最少。 两个前端池中的每一个池均具有 6 台服务器，这在故障转移时足够容纳两个池中的所有 40,000 个用户。 有关详细信息，请参阅 [Lync Server 2013 中的规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。

  - **对后端服务器进行镜像**    为为基本用户功能提供更高的可用性，组织已为每个前端池部署了一个镜像对后端服务器。 这是一个可选拓扑，可以选择部署一台后端服务器。

  - **在分支站点中使用 Standard Edition server。**    此组织将站点 C 视为分支站点，因为它只有600名员工。 但是，该站点上的用户之间有许多 A/V 会议。 如果它是作为分支站点在 Lync Server 中部署的，则这些会议的媒体将跨广域网络运行 (WAN) 与部署了前端服务器的中央站点。 为了避免这种潜在的带宽负载，已在此站点上安装了一对 Standard Edition 服务器，这将主持这些会议。 由于安装了 Standard Edition 服务器，因此 Lync Server 按定义将其视为一个中央站点，并在拓扑生成器和规划工具中将其视为这样的情况。
    
    在这里，仅有一个 Standard Edition 服务器的性能就足够了，但组织已部署两个并配对在一起，以在一台服务器出现故障时提供高可用性。
    
    尽管站点 C 被视为中央站点，但不需要在其上部署边缘服务器。在本例中，站点 C 将使用站点 A 上部署的边缘服务器。

  - **监控和存档**    此组织已部署监视和存档。 在部署监控或存档时，它将在每台前端服务器上运行。 这些功能的数据库可以与后端数据库并置，也可以位于单独的服务器上。 此组织已将服务器上的这些数据库与后端服务器分开，位于中央站点 B 中。此处的数据库接收来自所有站点中的前端服务器的监视和存档数据。

  - **分支站点部署选项。**    此组织实际上拥有超过50个分支站点，详细信息图中仅显示了其中三个。 分支站点1和3不具有到中央站点的弹性 WAN 链接，因此他们已部署 Survivable 分支机构以提供电话服务，以确保指向中央站点的 WAN 链接断开。 分支站点2但是有一个弹性 WAN 链路，因此只需 (PSTN) 网关的公用电话交换电话网络。 部署的 PSTN 网关支持媒体旁路，因此分支站点 B 不需要中介服务器。有关决定在分支站点上安装哪些内容的详细信息，请参阅规划文档中的在 [Lync Server 2013 中规划企业语音恢复](lync-server-2013-planning-for-enterprise-voice-resiliency.md) 。

  - **SIP 中继和中介服务器。**    请注意，在中央站点 B 上，中介服务器未与前端服务器并置。 这是因为对于使用 SIP 中继的站点，建议使用独立的中介服务器。 在其他多数实例中，建议将中介服务器与前端服务器并置。 有关中介服务器拓扑的详细信息，请参阅规划文档中的 [Lync server 2013 中的中介服务器的组件和拓扑](lync-server-2013-components-and-topologies-for-mediation-server.md) 。

  - **已部署持久聊天。**    此组织部署了启用持久聊天所必需的服务器。 它已部署多台持久聊天前端服务器以在处理池中用户数量的负载的同时提供高可用性。 它还部署了持久聊天的合规性，并且将持久聊天存储和持久聊天合规性存储放置在各台服务器上。 这些存储可进行并置，甚至可与后端服务器并置，但此组织选择将其分隔开以提供更好的性能。

  - **DNS 负载平衡。**    前端池和边缘服务器池。 这就无需为边缘服务器内部接口部署硬件负载平衡器，并可以显著减少为其他池设置和维护硬件负载平衡器必须花费的时间，因为只有 HTTP 流量需要使用硬件负载平衡器。 有关 DNS 负载平衡的详细信息，请参阅规划文档中的 [Lync Server 2013 中的 DNS 负载平衡](lync-server-2013-dns-load-balancing.md) 。

  - **EXCHANGE UM 部署。**   Lync Server 适用于 Exchange 统一消息 (UM) 和*托管*exchange UM 的*本地*部署。 中央站点 A 包含 Exchange 统一消息 (UM) 服务器，该服务器运行 Microsoft Exchange Server，而不是 Lync Server。 Lync Server 的 Exchange UM 功能在前端池上运行。
    
    中央站点 B 使用托管 Exchange，因此也承载 Exchange UM 服务器功能。
    
    有关 Exchange UM 的详细信息，请参阅规划文档中的在 lync server [2013 中规划 Exchange 统一消息集成](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) 和 [lync server 2013 中的托管 exchange 统一消息集成](lync-server-2013-hosted-exchange-unified-messaging-integration.md) 。

  - **Office Web Apps 服务器。**   我们建议在每个使用 Web 会议的组织内部署一个 Office Web Apps 服务器或 Office Web Apps 服务器场。 您可在一个站点上部署一个 Office Web Apps 服务器场，以通过所有站点提供流量，也可以在所有站点上部署该场。 利用 Office Web Apps 服务器，可以在 Web 会议中演示 Powerpoint 幻灯片。 有关详细信息，请参阅 [配置与 Office Web Apps Server 和 Lync Server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

  - 可**添加控制器。**   如果此组织希望提高抵御拒绝服务攻击的安全性，它还可以部署一个控制器池。 Director 是 Lync Server 中的一个单独的可选服务器角色，它不会家庭用户帐户，也不提供状态或会议服务。 它充当内部下一个跃点服务器，边缘服务器将入站 SIP 流量路由到内部服务器。 控制器对入站请求进行预身份验证，并将其重定向到用户的主池或服务器。 控制器进行的预先身份验证允许放弃来自部署中未知的用户帐户的请求。 控制器可帮助将前端服务器与恶意流量（如拒绝服务 (DoS) 攻击）隔离。 如果网络在此类攻击中遇到无效的外部通信，则流量将在 Director 处结束。

  - **已部署 System Center Operations Manager。**   建议您监视 Lync Server 部署的运行状况，以确保最终用户的服务可用性。 您可以使用可从 Microsoft 免费下载的 Lync 的 System Center Operations Manager 管理包监视 Lync。 使用 Lync 管理包，您可在问题出现时主动获取实时警报、运行综合事务测试端到端的 Lync 功能以及获取服务可用性的报告等。 这有助于您在最终用户遇到部署相关问题之前主动响应这些问题。
    
    此组织已在每个中央站点中部署 System Center Operations Manager 服务器。

</div>

<span> </span>

</div>

</div>

</div>

