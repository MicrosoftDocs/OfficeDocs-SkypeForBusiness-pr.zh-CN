---
title: Skype 业务服务器的参考拓扑
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
description: Skype 业务服务器，包括图和决定大型、 中型和小型组织的参考拓扑。
ms.openlocfilehash: 284fd37a6f9d65bae5e5e90695db851e66af6cfc
ms.sourcegitcommit: 247747ec19c0f5c1d45fea7e5ac5318e4d5127ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/02/2018
ms.locfileid: "21710832"
---
# <a name="reference-topologies-for-skype-for-business-server"></a>Skype 业务服务器的参考拓扑
 
Skype 业务服务器，包括图和决定大型、 中型和小型组织的参考拓扑。
  
为您的企业服务器拓扑的最佳 Skype 取决于组织的大小、 要部署的工作负荷和相应的投资成本的高可用性的首选项。 
  
本节概述了三种示例参考拓扑，包括促成每种拓扑的多种决策背后的推论。
  
## <a name="reference-topology-for-a-small-organization"></a>小型组织的参考拓扑

小型组织的参考拓扑显示了如何可以通过部署运行 Business Server Skype 只有三个服务器部署一个稳固、 高度可用的解决方案。
  
**小型组织的参考拓扑**

![用于部署三台服务器的参考拓扑图示](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology1.jpg)
  
- **对 Standard Edition 服务器部署**此组织中其中央站点上有 4,000 用户。 它们已部署两台 Standard Edition 服务器和配对它们在一起以实现高可用性和灾难恢复。 两个服务器之间同步每个服务器总部 2,000 个用户，但所有用户的信息。 如果一个不可用，管理员可以故障转移由其他服务器，对用户造成干扰至少具有这些用户。 有关高可用性和灾难恢复功能 Skype 中的业务服务器的详细信息，请参阅[规划高可用性和灾难恢复 Skype 业务服务器中](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
    
- **建议部署边缘服务器。** 尽管对于内部 IM、状态和会议来说，部署边缘服务器并非必需，但即便对于小型部署，我们也推荐采用边缘服务器。 您可以通过部署边缘服务器提供服务向贵组织的防火墙外的当前用户最大化 Business Server 投资您 Skype。 其优点包括：
    
  - 在家工作或在旅途中时，组织的用户可以业务服务器功能使用 Skype。
    
  - 您的用户可以邀请外部用户参加会议。
    
  - 如果您有合作伙伴、 供应商或业务服务器还使用 Skype 的客户组织，您可以窗体与该组织的联合的关系。 对于业务服务器部署您 Skype 将然后识别从组织的联合用户导致更好的协作。
    
  - 您的用户可以与一些公共 IM 服务的用户交换即时消息。
    
- **分支站点生存能力。** 此组织业务服务器正在运行的企业语音功能的 Skype 试用计划。 一些用户使用 Skype 业务服务器作为其唯一语音解决方案。 某些这些企业语音部分试验用户位于分支站点上。 分支站点没有可靠的广域网 (WAN) 链接到中心网站，因此 Survivable Branch Appliance 部署存在。 这样一来，如果 WAN 链路出现故障，分支站点上的用户仍然可以发出和接收呼叫（组织内的呼叫和 PSTN 呼叫），继续使用语音邮件功能，并使用双方即时消息 (IM) 进行通信。 当 WAN 链路不可用时，仍然能够对用户进行身份验证。 有关详细信息，请参阅[规划企业语音恢复能力 Skype 业务服务器中](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md)。
    
- **Exchange UM 部署。** 此参考拓扑包括 Exchange 统一消息 (UM) 服务器，它运行 Microsoft Exchange Server，不 Skype 业务服务器。
    
- **Office Web Apps 服务器。** 我们建议在每个使用 Web 会议的组织内部署一个 Office Web Apps 服务器或 Office Web Apps 服务器场。利用 Office Web Apps 服务器，可以在 Web 会议中演示 PowerPoint 幻灯片。
    
## <a name="reference-topology-for-a-medium-organization"></a>中型组织的参考拓扑

具有高可用性和单个数据中心的参考拓扑是为具有一个中央站点的中小型组织设计的。下图中的具体拓扑用于拥有 20,000 个用户的组织。 
  
**中型组织的参考拓扑**

![用于单个数据中心的参考拓扑图示](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology2.jpg)
  
- **通过添加更多前端服务器来容纳更多用户。** 此图中的具体拓扑包含三台前端服务器，可支持 20,000 个用户。 如果具有一个中央站点和更多用户，则只需将更多前端服务器添加到池中。 每个池最多可支持 80,000 个用户，可包含 12 台前端服务器。
    
    但是，单站点拓扑可以通过向该站点添加另一个前端池来支持更多的用户。 
    
- **可以添加灾难恢复。** 为此组织，其 Skype 业务 Server 服务的高可用性所需的功能，但不进行灾难恢复。 前端服务器它们已部署的池提供高可用性。
    
    如果需要添加灾难恢复功能，可以考虑建立另一个数据中心并添加另一个前端池，同时将其当前数据中心内的前端池配对。之后，如果发生影响其主池的灾难，则管理员可以将用户故障转移到备份池。
    
- **后端服务器镜像**基本用户功能提供详细的高可用性，组织已经部署了为每个前端池的后端服务器镜像的对。
    
- **监控服务器数据库选项。** 此组织已部署监控以确保列出企业语音呼叫的质量和 A / V 会议。 在每个前端服务器上部署监控，并且监控数据库将与后端服务器并置。 我们还支持监控数据库在其中位于单独的服务器上的拓扑。
    
- **边缘服务器高可用性**在此示例组织中使用 20,000 名用户，只需一台边缘服务器将足够性能。 但是，他们已部署部署以提供高可用性的两个边缘服务器的池。
    
- **分支站点部署选项。** 在这种拓扑结构中的组织具有作为其语音解决方案部署企业语音。 分支站点 1 没有弹性广域网 (WAN) 链接到中心网站，以便它具有 Survivable Branch Appliance 部署以维护业务 Server 功能的许多 Skype 的 WAN 链路到中心网站的情况下不可用。 但是，分支站点 2 具有可恢复 WAN 链路，因此只需一个公用电话交换网 (PSTN) 网关。 该处部署的 PSTN 网关支持媒体旁路，因此分支站点 2 上不需要中介服务器。 有关详细信息，请参阅[规划企业语音恢复能力 Skype 业务服务器中](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md)。
    
- **DNS 负载平衡。** 前端池和边缘服务器池已经部署了用于 SIP 流量的 DNS 负载平衡。 这样就无需为边缘服务器部署硬件负载平衡器，并可以显著减少为其他池设置和维护硬件负载平衡器的工作量，因为只有 HTTP 流量需要使用硬件负载平衡器。 有关详细信息，请参阅 (.../../ plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing)。
    
- **Exchange UM 部署。** 此参考拓扑包括 Exchange 统一消息 (UM) 服务器，它运行 Microsoft Exchange Server，不 Skype 业务服务器。
    
- **Office Web Apps 服务器。** 我们建议在每个使用 Web 会议的组织内部署一个 Office Web Apps 服务器或 Office Web Apps 服务器场。利用 Office Web Apps 服务器，可以在 Web 会议中演示 PowerPoint 幻灯片。
    
- **可以添加控制器。** 如果此组织希望增强安全性以抵御拒绝服务攻击，也可以部署控制器池。 控制器是不承载用户帐户，或提供状态或会议服务的业务服务器 Skype 中的一个单独、 可选的服务器角色。 它可以作为边缘服务器将发往内部服务器的入站的 SIP 流量路由到内部下一个跃点服务器。 控制器对入站的请求预先进行身份验证，并将其重定向到用户的主池或服务器。 控制器进行的预先身份验证允许放弃来自部署中未知的用户帐户的请求。 Director 有助于阻止恶意流量，如拒绝服务 (DoS) 攻击的前端服务器。 如果网络状态不淹没无效的外部流量，在此类攻击中，流量结束控制器。
    
- **System Center Operations Manager，建议使用。** 我们建议您监视您 Skype 业务服务器部署，以帮助确保最终用户的服务可用性的运行状况。 您可以对 for Business 内可作为免费下载 microsoft Skype 使用 System Center Operations Manager 管理包。 使用 Skype for Business 管理包，您可在问题出现时主动获取实时警报、运行综合事务测试端到端的 Skype for Business 功能以及获取服务可用性的报告等。 这有助于您在最终用户遇到部署相关问题之前主动响应这些问题。
    
## <a name="reference-topology-for-a-large-organization"></a>大型组织的参考拓扑

具有多个数据中心的大型组织的参考拓扑支持适用于具有多个中央站点的各种规模的组织。下图中的具体拓扑适用于具有 50,000 个用户的组织，其中 20,000 个用户位于中央站点 A，20,000 个用户位于中央站点 B，总共 10,000 个用户位于中央站点 C 和分支站点。该图中显示的拓扑类型可满足具有任意数量用户的组织。
  
除了提供的前端服务器池的高可用性，这种拓扑添加灾难恢复支持。 在中央站点 A 和 B 的前端池了一起。 如果其中一个池不可用，则管理员可将受影响用户的服务转移到位于不受影响的站点上的配对池中。
  
此拓扑分为多幅图显示，首先是概述，然后是中央站点的详细视图。
  
**有多个数据中心的大型组织的参考拓扑概述**

![用于多个数据中心的参考拓扑](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-1-new.jpg)
  
**大型组织的参考拓扑：中央站点 A 的详细视图**

![拓扑 3-2](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-2.jpg)
  
**大型组织的参考拓扑：中央站点 B 的详细视图**

![拓扑 3-3](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-3.jpg)
  
**大型组织的参考拓扑：中央站点 C 的详细视图**

![拓扑 3-4](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-4.jpg)
  
- **前端池配对启用灾难恢复。** 在站点和站点 B 的前端池都与每个其他，以提供灾难恢复支持配对。 如果一个站点的池失败，管理员可以故障转移到其他站点，最少的用户服务中断成对的前端池的用户从该网站。 两个前端池中的每一个池均具有 6 台服务器，这在故障转移时足够容纳两个池中的所有 40,000 个用户。 有关详细信息，请参阅[规划高可用性和灾难恢复 Skype 业务服务器中](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。 
    
- **后端服务器镜像**基本用户功能提供详细的高可用性，组织已经部署了为每个前端池的后端服务器镜像的对。 这是可选的拓扑，您可以选择部署单一的后端服务器而。 也支持 SQL 群集和 AlwaysOn 可用性组。 有关详细信息，请参阅[Skype 业务服务器后端服务器高可用性](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)。
    
- **在分支站点上使用 Standard Edition 服务器。** 此组织考虑站点 C 作为分支站点，因为该站点上只有 600 个员工。 但是，该站点上的用户之间有许多 A/V 会议。 如果它已部署在 Skype Business Server 分支站点，请与中央站点已前端服务器部署，将跨广域网 (WAN) 运行这些会议媒体。 若要避免此潜在的带宽负载，它们已安装在此站点将承载这些会议的 Standard Edition server 的一对。 和因为安装 Standard Edition server，Skype 定义的业务服务器将其视为中央站点，并在拓扑生成器和规划工具中处理此类。
    
    只有一个 Standard Edition server 会足够性能在这里，但是组织已部署了两台和配对它们在一起以在一台服务器出现故障的情况下提供高可用性。
    
    尽管站点 C 被视为中央站点，但不需要在其上部署边缘服务器。在本例中，站点 C 将使用站点 A 上部署的边缘服务器。
    
- **监控和存档**此组织已部署监控和存档。 在部署监控或存档时，它将在每个前端服务器上运行。 这些功能的数据库可以与后端数据库，并置，或位于一台服务器上。 此组织已将这些数据库位于 server 独立于后端服务器，在中央站点 b。此处的数据库接收来自所有网站在前端服务器的监控和存档数据。
    
- **分支站点部署选项。** 此组织实际上具有 50 个以上的分支站点，但明细图中仅显示了其中的两个分支站点。 分支站点 1 没有可恢复的 WAN 链接到中心网站，以便他们具有 Survivable Branch Appliance 部署提供的电话服务的 WAN 链路到中心网站的情况下不可用。 而分支站点 2 具有可恢复的 WAN 链路，因此只需一个公用电话交换网 (PSTN) 网关。 这些站点上部署的 PSTN 网关支持媒体旁路功能，因此分支站点 2 上不需要中介服务器。 有关确定要在分支站点上安装的详细信息，请参阅[Plan for Business Server 的 Skype 中的企业语音恢复能力](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md)。
    
- **SIP 中继和中介服务器。** 请注意，在中央站点 B 上，中介服务器没有与前端服务器并置。 这是因为对于使用 SIP 中继的站点，建议使用独立的中介服务器。 在其他多数实例中，建议将中介服务器与前端服务器并置。 有关中介服务器拓扑的详细信息，请参阅规划文档中的[Components and Topologies for Mediation Server](http://technet.microsoft.com/library/71397168-36c3-4d21-b8ef-db6a751634ee.aspx) 。
    
- **已部署持久聊天。** 此组织部署了启用持久聊天所需的服务器。 它已部署多台持久聊天前端服务器以在处理池中用户数量的负载的同时提供高可用性。 它还部署了持久聊天的合规性，并且将持久聊天存储和持久聊天合规性存储放置在各台服务器上。 这些存储可进行并置，甚至可与后端服务器并置，但此组织选择将其分隔开以提供更好的性能。

    > [!NOTE] 
    > 持久聊天中的业务服务器 2015 Skype 可用但业务服务器 2019年不再支持在 Skype。 中团队提供了相同的功能。 有关详细信息，请参阅[从企业对 Microsoft 团队的 Skype 旅程](/microsoftteams/journey-skypeforbusiness-teams)。 如果您需要使用持久聊天，您的选择是也迁移要求给团队，此功能的用户或继续对业务服务器 2015年使用 Skype。 
    
- **DNS 负载平衡。** 前端池和边缘服务器池使用 DNS 负载平衡。 这就无需为边缘服务器内部接口部署硬件负载平衡器，并可以显著减少为其他池设置和维护硬件负载平衡器必须花费的时间，因为只有 HTTP 流量需要使用硬件负载平衡器。 有关详细信息，请参阅 (.../../ plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing)。
    
- **Exchange UM 部署。** Skype 业务服务器处理这两个本地部署的 Exchange 统一消息 (UM) 和托管 Exchange UM。 中央站点 A 包括 Exchange 统一消息 (UM) 服务器，它运行 Microsoft Exchange Server，不 Skype 业务服务器。 前端池上运行 Skype 业务服务器的 Exchange UM 功能。
    
    中央站点 B 使用托管 Exchange，因此也承载 Exchange UM 服务器功能。 
    
    有关 Exchange UM 的详细信息，请参阅规划文档中的[On-premises Exchange Unified Messaging Integration](http://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx)和[Hosted Exchange Unified Messaging Integration](http://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx) 。
    
- **Office Web Apps 服务器。** 我们建议在每个使用 Web 会议的组织内部署一个 Office Web Apps 服务器或 Office Web Apps 服务器场。 您无法部署在一个网站提供所有网站流量单个 Office Web Apps Server 服务器场或将其部署在每个站点。 利用 Office Web Apps 服务器，可以在 Web 会议中演示 PowerPoint 幻灯片。 
    
- **可添加控制器。** 如果此组织希望提高安全性以更好地抵御拒绝服务攻击，还可部署一个控制器池。 控制器是不承载用户帐户，或提供状态或会议服务的业务服务器 Skype 中的一个单独、 可选的服务器角色。 它可以作为边缘服务器将发往内部服务器的入站的 SIP 流量路由到内部下一个跃点服务器。 控制器对入站的请求预先进行身份验证，并将其重定向到用户的主池或服务器。 控制器进行的预先身份验证允许放弃来自部署中未知的用户帐户的请求。 Director 有助于阻止恶意流量，如拒绝服务 (DoS) 攻击的前端服务器。 如果网络状态不淹没无效的外部流量，在此类攻击中，流量结束控制器。
    
- **System Center Operations Manager，建议使用。** 我们建议您监视您 Skype 业务服务器部署，以帮助确保最终用户的服务可用性的运行状况。 您可以对 for Business 内可作为免费下载 microsoft Skype 使用 System Center Operations Manager 管理包。 使用 Skype for Business 管理包，您可在问题出现时主动获取实时警报、运行综合事务测试端到端的 Skype for Business 功能以及获取服务可用性的报告等。 这有助于您在最终用户遇到部署相关问题之前主动响应这些问题。
    

