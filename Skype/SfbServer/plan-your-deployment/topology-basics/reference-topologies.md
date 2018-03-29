---
title: Skype for Business Server 2015 的参考拓扑
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
description: 参考拓扑 Skype 业务服务器，包括图表和决策进行大型、 中型和小型企业。
ms.openlocfilehash: 5019e292344dfe20ee086ff6ceb86c11aeeee944
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="reference-topologies-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 的参考拓扑
 
参考拓扑 Skype 业务服务器，包括图表和决策进行大型、 中型和小型企业。
  
为您的企业服务器拓扑的最佳 Skype 取决于您所在组织的大小、 要部署的工作负荷和您的首选项而不是投资成本的高可用性。 
  
本节概述了三种示例参考拓扑，包括促成每种拓扑的多种决策背后的推论。
  
## <a name="reference-topology-for-a-small-organization"></a>小型组织的参考拓扑

小型企业参考拓扑显示通过部署业务服务器运行 Skype 的只有三个服务器，您就可以部署一个强健、 高可用的解决方案。
  
**小型企业参考拓扑**

![用于部署三台服务器的参考拓扑图示](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology1.jpg)
  
- **对的标准版服务器部署**该组织在其中心的网站有 4000 个用户。 他们已经部署了两个标准版服务器并成对出现，它们在一起以实现高可用性和灾难恢复。 两台服务器之间同步每个服务器 2000 家用户，但所有用户的信息。 如果其中一个出现故障，管理员可以通过由其他服务器，最小的中断对用户提供这些用户失败。 企业服务器高可用性和灾难恢复功能，在 Skype 的详细信息，请参阅[规划高可用性和灾难恢复业务服务器 2015年的 Skype](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
    
- **建议部署边缘服务器。** 尽管对于内部 IM、状态和会议来说，部署边缘服务器并非必需，但即便对于小型部署，我们也推荐采用边缘服务器。 通过部署边缘服务器当前在您的组织的防火墙之外的用户提供服务，可以最大化您的 Skype 业务服务器投资。 其优点包括：
    
  - 您的组织的用户可用于 Skype 业务服务器的功能，如果他们在家工作或者是掉在路上。
    
  - 您的用户可以邀请外部用户参加会议。
    
  - 如果您有合作伙伴、 供应商或客户组织，还对企业服务器使用 Skype，可以形成与该组织之间的联盟的关系。 您 Skype 业务服务器部署将然后识别用户从该联盟的组织，从而导致更好的协作。
    
  - 您的用户可以与一些公共 IM 服务的用户交换即时消息。
    
- **分支站点生存能力。** 本组织业务服务器运行 Skype 的企业语音功能的试验计划。 某些用户使用 Skype 业务服务器作为其唯一的语音解决方案。 一些这些企业语音试验用户位于分支站点。 分支站点没有可靠的广域网 (WAN) 链接到中心站点，因此高存活力的分支装置那里部署。 这样一来，如果 WAN 链路出现故障，分支站点上的用户仍然可以发出和接收呼叫（组织内的呼叫和 PSTN 呼叫），继续使用语音邮件功能，并使用双方即时消息 (IM) 进行通信。 当 WAN 链路不可用时，仍然能够对用户进行身份验证。 有关详细信息，请参阅[规划业务服务器 2015年的 Skype 企业语音恢复功能](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md)。
    
- **Exchange UM 部署。** 此参考拓扑包括 Exchange 统一消息 (UM) 服务器，它运行 Microsoft Exchange Server，不 Skype 业务服务器。
    
- **Office Web Apps 服务器。** 我们建议在每个使用 Web 会议的组织内部署一个 Office Web Apps 服务器或 Office Web Apps 服务器场。利用 Office Web Apps 服务器，可以在 Web 会议中演示 PowerPoint 幻灯片。
    
## <a name="reference-topology-for-a-medium-organization"></a>中型组织的参考拓扑

具有高可用性和单个数据中心的参考拓扑是为具有一个中央站点的中小型组织设计的。下图中的具体拓扑用于拥有 20,000 个用户的组织。 
  
**参考拓扑的中型组织**

![用于单个数据中心的参考拓扑图示](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology2.jpg)
  
- **通过添加更多前端服务器来容纳更多用户。** 此图中的具体拓扑包含三台前端服务器，可支持 20,000 个用户。 如果具有一个中央站点和更多用户，则只需将更多前端服务器添加到池中。 每个池最多可支持 80,000 个用户，可包含 12 台前端服务器。
    
    但是，单站点拓扑可以通过向该站点添加另一个前端池来支持更多的用户。 
    
- **可以添加灾难恢复。** 对于该组织来说，其 Skype 业务服务器服务的高可用性是一个必要条件，但不是灾难恢复。 前端服务器他们部署的池提供高可用性。
    
    如果需要添加灾难恢复功能，可以考虑建立另一个数据中心并添加另一个前端池，同时将其当前数据中心内的前端池配对。之后，如果发生影响其主池的灾难，则管理员可以将用户故障转移到备份池。
    
- **后端服务器进行镜像**若要提供基本的用户功能更高的可用性，组织部署镜像的对的后端服务器的每个前端池。
    
- **监控服务器数据库选项。** 此组织已部署监视以确保质量的企业语音调用和 A / V 会议。 在每个前端服务器上部署监控，并且监控数据库将与后端服务器并置。 我们还支持监控数据库在其中位于单独的服务器上的拓扑。
    
- **边缘服务器高可用性**20000 个用户使用此示例组织中，只是一个边缘服务器将需要足够的性能。 但是，他们已经部署部署可提供高可用性的两个边缘服务器的池。
    
- **分支站点部署选项。** 此拓扑结构中的组织已部署为其语音解决方案企业语音。 分支站点 1 没有弹性的广域网 (WAN) 链接到中心站点，因此它具有高存活力的分支装置部署维护许多 Skype 业务服务器功能以防到中心站点的 WAN 链路出现故障。 但是，分支站点 2 具有可恢复 WAN 链路，因此只需一个公用电话交换网 (PSTN) 网关。 该处部署的 PSTN 网关支持媒体旁路，因此分支站点 2 上不需要中介服务器。 有关详细信息，请参阅[规划业务服务器 2015年的 Skype 企业语音恢复功能](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md)。
    
- **DNS 负载平衡。** 前端池和边缘服务器池已经部署了用于 SIP 流量的 DNS 负载平衡。 这样就无需为边缘服务器部署硬件负载平衡器，并可以显著减少为其他池设置和维护硬件负载平衡器的工作量，因为只有 HTTP 流量需要使用硬件负载平衡器。 有关详细信息，请参阅 (.../../ plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing)。
    
- **Exchange UM 部署。** 此参考拓扑包括 Exchange 统一消息 (UM) 服务器，它运行 Microsoft Exchange Server，不 Skype 业务服务器。
    
- **Office Web Apps 服务器。**我们建议在每个使用 Web 会议的组织内部署一个 Office Web Apps 服务器或 Office Web Apps 服务器场。利用 Office Web Apps 服务器，可以在 Web 会议中演示 PowerPoint 幻灯片。
    
- **可以添加控制器。** 如果此组织希望增强安全性以抵御拒绝服务攻击，也可以部署控制器池。 导演是 Skype 不家庭用户帐户或提供会议存在服务业务服务器在单独的、 可选的服务器角色。 它可以作为边缘服务器将发送到内部服务器的入站的 SIP 通信路由到内部下一个跃点服务器。 Director 预先对入站的请求进行身份验证，并且将它们重定向到用户的主池或服务器。 控制器进行的预先身份验证允许放弃来自部署中未知的用户帐户的请求。 董事可以帮助隔离如拒绝服务 (DoS) 攻击的恶意通信量从前端服务器。 如果网络被淹没在此类攻击中无效的外部通信，通信结束处主任。
    
- **建议系统中心操作管理器。** 我们建议您监控您业务服务器部署有助于确保为最终用户的服务可用性的 Skype 的运行状况。 系统中心操作管理器管理包可用于 Skype 为 Microsoft 的免费下载可用的业务。 使用 Skype for Business 管理包，您可在问题出现时主动获取实时警报、运行综合事务测试端到端的 Skype for Business 功能以及获取服务可用性的报告等。 这有助于您在最终用户遇到部署相关问题之前主动响应这些问题。
    
## <a name="reference-topology-for-a-large-organization"></a>大型组织的参考拓扑

具有多个数据中心的大型组织的参考拓扑支持适用于具有多个中央站点的各种规模的组织。下图中的具体拓扑适用于具有 50,000 个用户的组织，其中 20,000 个用户位于中央站点 A，20,000 个用户位于中央站点 B，总共 10,000 个用户位于中央站点 C 和分支站点。该图中显示的拓扑类型可满足具有任意数量用户的组织。
  
除了由池的前端服务器的高可用性，此拓扑中添加灾难恢复支持。 在中央站点 A 和 B 的前端池在了一起。 如果其中一个池不可用，则管理员可将受影响用户的服务转移到位于不受影响的站点上的配对池中。
  
此拓扑分为多幅图显示，首先是概述，然后是中央站点的详细视图。
  
**中心的大型组织中具有多个数据的引用拓扑概述**

![用于多个数据中心的参考拓扑](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-1-new.jpg)
  
**对于大型组织参考拓扑： 详细视图的中心站点 A**

![拓扑 3-2](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-2.jpg)
  
**对于大型组织参考拓扑： 详细视图的中心站点 B**

![拓扑 3-3](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-3.jpg)
  
**对于大型组织参考拓扑： 详细视图的中心站点 C**

![拓扑 3-4](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-4.jpg)
  
- **前结束池启用灾难恢复配对。** 在站点 A 和站点 B 的前端池配合对方，以提供灾难恢复支持。 如果一个站点上的池出现故障，管理员可以故障转移到其它站点，最少的用户服务中断成对的前端池的用户从该站点中。 两个前端池中的每一个池均具有 6 台服务器，这在故障转移时足够容纳两个池中的所有 40,000 个用户。 有关详细信息，请参阅[规划高可用性和灾难恢复业务服务器 2015年的 Skype](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。 
    
- **后端服务器进行镜像**若要提供基本的用户功能更高的可用性，组织部署镜像的对的后端服务器的每个前端池。 这是一个可选的拓扑结构，并且您可以选择改为部署单个后端服务器。 也支持 SQL 群集和 AlwaysOn 可用性组。 有关详细信息，请参阅[在 Skype 业务服务器 2015年的后端服务器高可用性](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)。
    
- **在分支站点使用标准版服务器。** 此组织考虑站点 C 作为分支站点，因为该站点上只有 600 个员工。 但是，该站点上的用户之间有许多 A/V 会议。 如果它部署在 Skype 业务作为分支站点的服务器，这些会议的媒体将从中央站点具有前端服务器部署和运行跨广域网 (WAN)。 若要避免这种潜在的带宽负载，他们安装一对的标准版服务器在此站点上，其中将主持这些会议。 并因为安装了标准版服务器那里，Skype 业务服务器被定义为将其视为一个中央站点拓扑生成器和规划工具中处理这种情况下。
    
    只是一个标准版服务器就是足够的性能，但公司部署两个，配对在一起以提供高可用性，在一台服务器出现故障的情况下。
    
    尽管站点 C 被视为中央站点，但不需要在其上部署边缘服务器。在本例中，站点 C 将使用站点 A 上部署的边缘服务器。
    
- **监视和存档**该组织在监视和归档部署。 部署监视或存档时，它将在每个前端服务器上运行。 可以搭配与后端数据库，或位于单独的服务器上对这些功能的数据库。 该组织已将这些数据库位于服务器分开后端服务器，在中心站点 b。这里的数据库接收来自前端服务器的所有站点监视和存档数据。
    
- **分支站点部署选项。** 此组织实际上具有 50 个以上的分支站点，但明细图中仅显示了其中的两个分支站点。 分支站点 1 没有弹性的 WAN 链接到中心站点，因此它们具有高存活力的分支装置部署提供的电话服务以防到中心站点的 WAN 链路出现故障。 而分支站点 2 具有可恢复的 WAN 链路，因此只需一个公用电话交换网 (PSTN) 网关。 这些站点上部署的 PSTN 网关支持媒体旁路功能，因此分支站点 2 上不需要中介服务器。 有关决定安装在分支站点的内容的详细信息，请参阅[规划业务服务器 2015年的 Skype 企业语音恢复功能](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md)。
    
- **SIP 中继和中介服务器。** 请注意，在中央站点 B 上，中介服务器没有与前端服务器并置。 这是因为对于使用 SIP 中继的站点，建议使用独立的中介服务器。 在其他多数实例中，建议将中介服务器与前端服务器并置。 中介服务器拓扑的详细信息，请参阅规划文档中的[组件和中介服务器的拓扑结构](http://technet.microsoft.com/library/71397168-36c3-4d21-b8ef-db6a751634ee.aspx)。
    
- **已部署持久聊天。** 此组织部署了启用持久聊天所需的服务器。 它已部署多台持久聊天前端服务器以在处理池中用户数量的负载的同时提供高可用性。 它还部署了持久聊天的合规性，并且将持久聊天存储和持久聊天合规性存储放置在各台服务器上。 这些存储可进行并置，甚至可与后端服务器并置，但此组织选择将其分隔开以提供更好的性能。
    
- **DNS 负载平衡。** 前端池和边缘服务器池使用 DNS 负载平衡。 这就无需为边缘服务器内部接口部署硬件负载平衡器，并可以显著减少为其他池设置和维护硬件负载平衡器必须花费的时间，因为只有 HTTP 流量需要使用硬件负载平衡器。 有关详细信息，请参阅 (.../../ plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing)。
    
- **Exchange UM 部署。** Skype 业务服务器的 bothon 内部部署的 Exchange 统一消息 (UM) andhosted UM 交换合作。 中心站点 A 包括 Exchange 统一消息 (UM) 服务器，它运行 Microsoft Exchange Server，不 Skype 业务服务器。 在前端池上运行 Skype 业务服务器的 Exchange UM 功能。
    
    中央站点 B 使用托管 Exchange，因此也承载 Exchange UM 服务器功能。 
    
    嗯交换有关详细信息，请参阅规划文档中的[内部 Exchange 统一消息传递集成](http://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx)和[承载 Exchange 统一消息传递集成](http://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)。
    
- **Office Web Apps 服务器。** 我们建议在每个使用 Web 会议的组织内部署一个 Office Web Apps 服务器或 Office Web Apps 服务器场。 您可以部署用于通信的所有站点，从一个站点中的单个 Office Web 应用程序服务器场或将其部署在每个站点。 利用 Office Web Apps 服务器，可以在 Web 会议中演示 PowerPoint 幻灯片。 
    
- **可添加控制器。** 如果此组织希望提高安全性以更好地抵御拒绝服务攻击，还可部署一个控制器池。 导演是 Skype 不家庭用户帐户或提供会议存在服务业务服务器在单独的、 可选的服务器角色。 它可以作为边缘服务器将发送到内部服务器的入站的 SIP 通信路由到内部下一个跃点服务器。 Director 预先对入站的请求进行身份验证，并且将它们重定向到用户的主池或服务器。 控制器进行的预先身份验证允许放弃来自部署中未知的用户帐户的请求。 董事可以帮助隔离如拒绝服务 (DoS) 攻击的恶意通信量从前端服务器。 如果网络被淹没在此类攻击中无效的外部通信，通信结束处主任。
    
- **建议系统中心操作管理器。** 我们建议您监控您业务服务器部署有助于确保为最终用户的服务可用性的 Skype 的运行状况。 系统中心操作管理器管理包可用于 Skype 为 Microsoft 的免费下载可用的业务。 使用 Skype for Business 管理包，您可在问题出现时主动获取实时警报、运行综合事务测试端到端的 Skype for Business 功能以及获取服务可用性的报告等。 这有助于您在最终用户遇到部署相关问题之前主动响应这些问题。
    

