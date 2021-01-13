---
title: Skype for Business Server 的参考拓扑
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
description: Skype for Business Server 的参考拓扑，包括适用于大型、中型和小型组织的图表和决策。
ms.openlocfilehash: 958f6630faf295a16aebe7513ee9e5c98daeeaa5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831732"
---
# <a name="reference-topologies-for-skype-for-business-server"></a>Skype for Business Server 的参考拓扑

Skype for Business Server 的参考拓扑，包括适用于大型、中型和小型组织的图表和决策。

适合你的最佳 Skype for Business Server 拓扑取决于组织的规模、要部署的工作负荷，以及你的高可用性与投资成本的偏好。

本节概述了三个示例参考拓扑，包括每个拓扑中许多决策背后的原因。

## <a name="reference-topology-for-a-small-organization"></a>小型组织的参考拓扑

小型组织的参考拓扑显示了如何部署强大的高可用性解决方案，只需部署三台运行 Skype for Business Server 的服务器。

**小型组织的参考拓扑**

![部署三台服务器的参考拓扑图](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology1.jpg)

- **已部署的 Standard Edition Servers 对** 此组织的中央站点有 4，000 个用户。 他们部署了两台 Standard Edition 服务器，将它们配对在一起以实现高可用性和灾难恢复。 每台服务器包含 2，000 个用户，但有关所有用户的信息在两台服务器之间同步。 如果出现故障，管理员可以对由另一台服务器提供服务的这些用户进行故障转移，并尽量减少用户中断。 有关 Skype for Business Server 中的高可用性和灾难恢复功能详细信息，请参阅 Plan [for high availability and disaster recovery in Skype for Business Server.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)

- **建议部署边缘服务器。** 尽管对于内部 IM、状态和会议，部署边缘服务器不是必需的，但我们建议进行部署，即使是小型的部署。 通过部署边缘服务器为当前位于组织防火墙之外的用户提供服务，可以最大限度地提高 Skype for Business Server 的投资。 优势包括：

  - 组织自己的用户可以使用 Skype for Business Server 功能（如果他们在家工作或外出）。

  - 您的用户可以邀请外部用户参加会议。

  - 如果你有同样使用 Skype for Business Server 的合作伙伴、供应商或客户组织，你可以与该组织建立联盟关系。 然后，Skype for Business Server 部署将识别来自该联盟组织的用户，从而更好地进行协作。

  - 您的用户可以与某些公共 IM 服务的用户交换即时消息。

- **分支站点生存能力。** 此组织正在运行 Skype for Business Server 企业语音的试点计划。 一些用户将 Skype for Business Server 用作其唯一的语音解决方案。 其中一企业语音试点用户位于分支站点。 分支站点没有到中央站点 (WAN) 可靠的广域网，因此将在那里部署 Survivable Branch Appliance。 部署此配置后，如果 WAN 链路关闭，分支站点中的用户仍可发出和接收呼叫 (同时在组织内部进行呼叫和 PSTN 呼叫) ，具有语音邮件功能，并与双方即时消息 (IM) 进行通信。 此外，在 WAN 链接不可用时，也可以对用户进行身份验证。 有关详细信息，请参阅[Plan for 企业语音 Resiliency in Skype for Business Server。](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md)

- **Exchange UM 部署。** 此参考拓扑包括 Exchange 统一消息 (UM) Server，该服务器Microsoft Exchange Server运行 Skype for Business Server。

- **Office Web Apps 服务器。** 我们建议在每个使用 Web 会议的组织内部署一个 Office Web Apps 服务器或 Office Web Apps 服务器场。 Office Web Apps Server 使 PowerPoint 幻灯片可以在 Web 会议中呈现。

## <a name="reference-topology-for-a-medium-organization"></a>中型组织的参考拓扑

具有高可用性和单个数据中心的参考拓扑是为具有一个中央站点的中小型组织设计的。 下图中的具体拓扑适用于具有 20，000 个用户的组织。

**中型组织的参考拓扑**

![单个数据中心图的参考拓扑](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology2.jpg)

- **通过添加更多前端服务器来容纳更多用户。** 此图中的具体拓扑具有三台前端服务器，可为 20，000 个用户提供支持。 如果您有一个中央站点和更多用户，则只需向池中添加更多前端服务器。 每个池的最大用户数为 80，000，其中 12 台前端服务器。

    但是，单站点拓扑可以通过向该站点添加另一个前端池来支持更多的用户。

- **可以添加灾难恢复。** 对于此组织，其 Skype for Business Server 服务的高可用性是必需的功能，但灾难恢复不是。 它们部署的前端服务器池可提供高可用性。

    如果他们希望添加灾难恢复功能，可以考虑建立另一个数据中心，并添加另一个前端池，并将其与当前数据中心中的前端池配对。 然后，如果发生影响其主池的灾难，则管理员可以将用户故障转移到备份池。

- **后端服务器已镜像** 为了为基本用户功能提供高可用性，组织已针对每个前端池部署了一对镜像的后端服务器。

- **监控服务器数据库选项。** 此组织部署了监控以确保企业语音和 A/V 会议的质量。 监控部署在前端服务器上，监控数据库与后端服务器并排。 我们还支持监控数据库位于单独服务器的拓扑。

- **边缘服务器高可用性** 在拥有 20，000 个用户的示例组织中，只需一台边缘服务器即可提高性能。 但是，它们部署了一个部署有两台边缘服务器的池，以提供高可用性。

- **分支站点部署选项。** 此拓扑中的组织已将企业语音部署为其语音解决方案。 分支站点 1 没有到中央站点的可恢复广域网 (WAN) 链接，因此它部署了 Survivable Branch Appliance 以维护许多 Skype for Business Server 功能，以防指向中央站点的 WAN 链路关闭。 但是，分支站点 2 具有可恢复 WAN 链接，因此只需一个公用电话交换网 (PSTN) 网关。 该处部署的 PSTN 网关支持媒体绕过，因此分支站点 2 上不需要中介服务器。 有关详细信息，请参阅[Plan for 企业语音 Resiliency in Skype for Business Server。](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md)

- **DNS 负载平衡。** 前端池和边缘服务器池已部署 SIP 流量的 DNS 负载平衡。 这样就无需为边缘服务器部署硬件负载平衡器，并可以显著减少为其他池设置和维护硬件负载平衡器的工作量，因为只有 HTTP 流量需要使用硬件负载平衡器。 有关详细信息，请参阅 [DNS 负载平衡](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing)。

- **Exchange UM 部署。** 此参考拓扑包括 Exchange 统一消息 (UM) Server，该服务器Microsoft Exchange Server运行 Skype for Business Server。

- **Office Web Apps 服务器。** 我们建议在每个使用 Web 会议的组织内部署一个 Office Web Apps 服务器或 Office Web Apps 服务器场。 利用 Office Web Apps 服务器，可以在 Web 会议中演示 Powerpoint 幻灯片。

- **可添加控制器。** 如果此组织希望帮助提高安全性以抵御拒绝服务攻击，它还可以部署控制器池。 控制器是 Skype for Business Server 中单独的可选服务器角色，不驻留用户帐户，也不提供状态或会议服务。 它充当内部下一个跃点服务器，边缘服务器将发往内部服务器的入站 SIP 流量路由到该服务器。 控制器会预先验证入站请求，并重定向到用户主池或服务器。 控制器进行的预先身份验证允许放弃来自部署中未知的用户帐户的请求。 控制器可帮助前端服务器隔离恶意流量，例如拒绝服务 (DoS) 攻击。 如果网络受到此类攻击中无效外部流量的淹没，则流量将终止于控制器。

- **建议使用 System Center Operations Manager。** 我们建议您监视 Skype for Business Server 部署的运行状况，以帮助确保最终用户的服务可用性。 可以使用可从 Microsoft 免费下载的适用于 Skype for Business 的 System Center Operations Manager 管理包。 借助 Skype for Business 管理包，你可以主动获取问题发生时实时警报、运行综合事务以测试端到端 Skype for Business 功能、获取服务可用性报告等。 这有助于您在最终用户遇到部署相关问题之前主动响应这些问题。

## <a name="reference-topology-for-a-large-organization"></a>大型组织的参考拓扑

具有多个数据中心的大型组织的参考拓扑支持适用于具有多个中央站点的各种规模的组织。下图中的具体拓扑适用于具有 50,000 个用户的组织，其中 20,000 个用户位于中央站点 A，20,000 个用户位于中央站点 B，总共 10,000 个用户位于中央站点 C 和分支站点。该图中显示的拓扑类型可满足具有任意数量用户的组织。

除了前端服务器池提供的高可用性之外，此拓扑还增加了灾难恢复支持。 中央站点 A 和 B 的前端池配对在一起。 如果其中一个池不可用，则管理员可将受影响用户的服务转移到位于不受影响的站点上的配对池中。

此拓扑分为多幅图显示，首先是概述，然后是中央站点的详细视图。

**具有多个数据中心的大型组织的参考拓扑概述**

![多个数据中心的引用拓扑](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-1-new.jpg)

**大型组织的参考拓扑：中央站点 A 的详细视图**

![拓扑 3-2](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-2.jpg)

**大型组织的参考拓扑：中央站点 B 的详细视图**

![拓扑 3-3](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-3.jpg)

**大型组织的参考拓扑：中央站点 C 的详细视图**

![拓扑 3-4](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-4.jpg)

- **配对前端池以启用灾难恢复。** 站点 A 和站点 B 的前端池相互配对，以提供灾难恢复支持。 如果一个站点上的池出现故障，管理员可以将用户从该站点故障转移到另一个站点上的配对前端池，同时为用户减少服务中断。 两个前端池中的每一个池均具有 6 台服务器，这在故障转移时足够容纳两个池中的所有 40,000 个用户。 有关详细信息，请参阅[Plan for high availability and disaster recovery in Skype for Business Server.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)

- **后端服务器已镜像** 为了为基本用户功能提供高可用性，组织已针对每个前端池部署了一对镜像的后端服务器。 这是可选拓扑，您可以选择部署单个后端服务器。 SQL群集和 AlwaysOn 可用性组也受支持。 有关详细信息，请参阅 [Skype for Business Server 中的后端服务器高可用性](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)。

- **在分支站点使用 Standard Edition Server。** 此组织考虑站点 C 作为分支站点，因为该站点上只有 600 个员工。 但是，该站点上的用户之间有许多 A/V 会议。 如果在 Skype for Business Server 中将其部署为分支站点，则这些会议的媒体将在广域网 (WAN) 与部署了前端服务器的中央站点之间运行。 为了避免这种潜在的带宽负载，他们在此站点上安装了一对 Standard Edition 服务器，该服务器将承载这些会议。 由于 Standard Edition Server 已安装在那里，因此根据定义，Skype for Business Server 会认为它是一个中央站点，并且它在拓扑生成器和规划工具中也被视为中央站点。

    此处只需一台 Standard Edition Server 就足以提高性能，但组织已部署两台并将它们配对在一起，以在一台服务器关闭时提供高可用性。

    尽管站点 C 被视为中央站点，但不需要在其上部署边缘服务器。在本例中，站点 C 将使用站点 A 上部署的边缘服务器。

- **监控和存档** 此组织已部署监控和存档。 部署监控或存档时，监控或存档将运行在前端服务器上。 这些功能的数据库可以与后端数据库并并，也可以位于单独的服务器上。 此组织将这些数据库放在中央站点 B 中与后端服务器分开的服务器上。此处的数据库接收来自所有站点中的前端服务器的监控和存档数据。

- **分支站点部署选项。** 此组织实际上拥有 50 多个分支站点，详细图中只显示了其中两个分支站点。 分支站点 1 没有到中央站点的可恢复 WAN 链路，因此它们部署了 Survivable Branch 设备以提供电话服务，以防指向中央站点的 WAN 链路关闭。 但是，分支站点 2 具有可恢复的 WAN 链路，因此它只需要一个公用电话交换网 (PSTN) 网关。 该处部署的 PSTN 网关支持媒体绕过，因此分支站点 2 上不需要中介服务器。 有关决定在分支站点安装的内容的详细信息，请参阅 Plan [for 企业语音 resiliency in Skype for Business Server.](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md)

- **SIP 中继和中介服务器。** 请注意，在中央站点 B 上，中介服务器没有与前端服务器并置。 这是因为对于使用 SIP 中继的站点，建议使用独立的中介服务器。 在其他多数实例中，建议将中介服务器与前端服务器并置。 有关中介服务器拓扑的详细信息，请参阅规划文档中的[Components and Topologies for Mediation Server](https://technet.microsoft.com/library/71397168-36c3-4d21-b8ef-db6a751634ee.aspx)。

- **部署了持久聊天。** 此组织部署了启用持久聊天所需的服务器。 它已部署多台持久聊天前端服务器以在处理池中用户数量的负载的同时提供高可用性。 它还部署了持久聊天的合规性，并且将持久聊天存储和持久聊天合规性存储放置在各台服务器上。 这些存储可进行并置，甚至可与后端服务器并置，但此组织选择将其分隔开以提供更好的性能。

    > [!NOTE]
    > 持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。 Teams 中也提供相同的功能。 有关详细信息，请参阅 [Microsoft Teams](/microsoftteams/upgrade-start-here)升级入门。 如果你需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。

- **DNS 负载平衡。** 前端池和边缘服务器池使用 DNS 负载平衡。 这就无需为边缘服务器内部接口部署硬件负载平衡器，并可以显著减少为其他池设置和维护硬件负载平衡器必须花费的时间，因为只有 HTTP 流量需要使用硬件负载平衡器。 有关详细信息，请参阅 (。/../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) 。

- **Exchange UM 部署。** Skype for Business Server 既适用于 Exchange 统一消息本地部署， (UM) 和托管 Exchange UM。 中央站点 A 包括 Exchange 统一 (UM) Server，该服务器在 Microsoft Exchange Server运行，而不是 Skype for Business Server。 Skype for Business Server 的 Exchange UM 功能在前端池中运行。

    中央站点 B 使用托管 Exchange，因此也承载 Exchange UM 服务器功能。

    有关 Exchange UM 的详细信息，请参阅规划文档中的 ["内部部署 Exchange](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) 统一消息集成和托管 Exchange 统一 [消息](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx) 集成"。

- **Office Web Apps 服务器。** 我们建议在每个使用 Web 会议的组织内部署一个 Office Web Apps 服务器或 Office Web Apps 服务器场。 您可在一个站点上部署一个 Office Web Apps 服务器场，以通过所有站点提供流量，也可以在所有站点上部署该场。 利用 Office Web Apps 服务器，可以在 Web 会议中演示 Powerpoint 幻灯片。

- **可添加控制器。** 如果此组织希望提高针对拒绝服务攻击的安全性，还可部署一个控制器的池。 控制器是 Skype for Business Server 中单独的可选服务器角色，不驻留用户帐户，也不提供状态或会议服务。 它充当内部下一个跃点服务器，边缘服务器将发往内部服务器的入站 SIP 流量路由到该服务器。 控制器会预先验证入站请求，并重定向到用户主池或服务器。 控制器进行的预先身份验证允许放弃来自部署中未知的用户帐户的请求。 控制器可帮助前端服务器隔离恶意流量，例如拒绝服务 (DoS) 攻击。 如果网络受到此类攻击中无效外部流量的淹没，则流量将终止于控制器。

- **建议使用 System Center Operations Manager。** 我们建议您监视 Skype for Business Server 部署的运行状况，以帮助确保最终用户的服务可用性。 可以使用可从 Microsoft 免费下载的适用于 Skype for Business 的 System Center Operations Manager 管理包。 借助 Skype for Business 管理包，你可以主动获取问题发生时实时警报、运行综合事务以测试端到端 Skype for Business 功能、获取服务可用性报告等。 这有助于您在最终用户遇到部署相关问题之前主动响应这些问题。


