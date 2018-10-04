---
title: 在云连接器版本中规划媒体旁路
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e69ac58c-e8fe-40bc-a4c8-f0a0190fbaa7
description: 阅读本主题，以了解使用云连接器版本 2.0 版和更高版本实现媒体旁路的规划注意事项。 有关部署媒体绕过，请参阅 Deploy 媒体绕过云连接器版本中。
ms.openlocfilehash: a3cfaea8d963efa4f7774b8b589fcd0ecc61d3bc
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370999"
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a>在云连接器版本中规划媒体旁路
 
阅读本主题，以了解使用云连接器版本 2.0 版和更高版本实现媒体旁路的规划注意事项。 有关部署媒体绕过，请参阅[Deploy 媒体绕过在云连接器 Edition](deploy-media-bypass-in-cloud-connector.md)。
  
媒体绕过允许客户端媒体直接发送到下一个跃点公共公用电话交换网 (PSTN) — 网关或会话边界控制器 (SBC) — 并消除通过的媒体路径中的云连接器 Edition 组件。
  
媒体旁路功能可通过减少延迟、可能的数据包丢失和潜在的故障点数来提高语音质量。 消除了媒体绕过呼叫处理减少了云连接器，从而使并发呼叫数越大上的负载，并可以提高可伸缩性。 
  
 从媒体处理任务释放云连接器可能会降低的基础结构要求，云连接器装置的数量，因此您应启用媒体绕过尽可能。
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a>媒体旁路对媒体和信号路径的影响

在具有和没有媒体旁路时，虽然发送信号都会采用相同的路径，但媒体流会有所不同。下图显示了具有和没有媒体旁路功能的拓扑中的媒体和信号路径。 
  
例如，在以下拓扑 — 不采用媒体的旁路 — Skype 业务客户端发起 PSTN 呼叫外部号码的 SIP 信号转到 Office 365 和 Office 365 便会根据最终用户语音信号流量策略。 云连接器用户语音策略将定向到云连接器边缘服务器，然后将信号流量路由到 PSTN 会话边界控制器 (SBC) 或通过云连接器中介服务器的网关的信号流量。 媒体从流动业务客户端 Skype 云连接器中介服务器，然后写入的 SBC 或网关，如下图中所示：
  
**没有媒体旁路功能的媒体和信号路径**

![没有媒体旁路功能的信号](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
来自 PSTN 的拨入通话将以相反方向使用相同的信号路径。 对于内部用户，媒体将仍最终业务客户端 Skype 云连接器中介服务器，然后 SBC 或网关之间流动。
  
下一个拓扑中 — 采用媒体的旁路 — 信号采用相同的路径，但直接之间业务客户端和 SBC 或网关，Skype 流动的媒体，如下图中所示：
  
**具有媒体旁路功能的媒体和信号路径**

![有媒体旁路功能的信号](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a>多站点方案和媒体旁路

您想要提供多个网站使用单个云连接器装置的电话服务时，则也可以媒体绕过。 云连接器无法将基于源或目标号码的呼叫路由，因为大多数企业部署的 SBC 或云连接器后面的网关做出路由决定。 在此方案中，媒体旁路使客户端与中心 SBC 或网关之间不再存在跃点，如下图所示：
  
**多站点应用**

![云连接器多站点示例](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. 从苏黎世中为用户到 Office 365 流动的 SIP 流量。
    
2. 然后，通信将路由到云连接器装置的阿姆斯特丹用户语音路由策略中指定中。
    
3. 云连接器装置的阿姆斯特丹将发送到阿姆斯特丹中的管理中心网关的 SIP 通信。
    
4. 阿姆斯特丹中的管理中心网关创建相应的路由决策，然后发送到 SBC 或中苏黎世，直接之间业务客户端和 SBC 或网关阿姆斯特丹 Skype 的媒体流时的网关的通信。
    
   此方法允许提供更多的用户，每一个云连接器部署集中进行云连接器。 尽管从媒体路径消除了云连接器，集中的多站点方案中媒体可能仍通过 WAN 两次所需通过集中 SBC 或网关的排列。
  
如果客户端位于企业网络发起出站呼叫，媒体流量的流动苏黎世和阿姆斯特丹，之间的云连接器和 WAN 链接的边缘服务器和中介服务器通过下图中所示：
  
![云连接器多站点示例 2](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a>支持使用媒体旁路的客户端

媒体绕过的第一版，仅支持的客户端是为 Office 365 ProPlus，版本 16.0.7870.2020 一部分的业务 2016 Windows Client Skype 或更高版本。 客户可以使用任意频道：当前、延期或首次发布延期频道。 
  
> [!NOTE]
> 如果你将客户端 VPN 解决方案与 Skype for Business 客户端结合使用，则只有 VPN 拆分隧道配置支持媒体旁路。 
  
有关版本通道的详细信息，请参阅[Overview of Office 365 ProPlus 的更新通道](https://support.office.com/en-us/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US)。
  
当前发行版本中舂中的客户端，请参阅[发布的更新 Office 365 ProPlus 的信息](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)。 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a>使用媒体旁路功能时的云连接器容量注意事项

无媒体旁路功能，并根据硬件 — 云连接器 appliance 可为 500 个呼叫需要媒体通过中介服务器出差的处理从 50。 有关详细信息，请参阅[规划商务云连接器版的 Skype](https://technet.microsoft.com/en-us/library/mt605227.aspx)。 
  
启用媒体旁路功能时，受支持版本的内部客户端不使用中介服务器，因此内部客户端数会显著增加。 
  
如上所述，外部客户端或不受支持的客户端将媒体使用云连接器边缘服务器和中介服务器。 在计算多少云连接器 appliance 应位于网站时，您必须考虑来自外部用户和不受支持的客户端上的用户通信。
  
## <a name="cloud-connector-supports-always-bypass-mode"></a>云连接器支持“始终旁路”模式

云连接器支持仅始终绕过模式。 在本地环境中，有两个选项：“始终旁路”和“使用站点和区域信息”。
  
“始终旁路”意味着将对以内部客户端作为源或目标点的所有 PSTN 通话尝试媒体旁路功能。为确定客户端是内部客户端还是外部客户端，将使用中介服务器虚拟机上的网站。如果客户端可以访问该站点，则认为它是内部客户端，并将使用媒体旁路功能。如果客户端无法访问该站点（例如，客户端在家庭网络上），则不使用媒体旁路功能。 
  
“始终旁路”要求用户与 PSTN 站点内的 PSTN 网关之间的连接畅通无阻。 
  
有关详细信息，请参阅[规划商务云连接器版的 Skype](https://technet.microsoft.com/en-us/library/mt605227.aspx)。 
  
例如，如下图中欧洲用户必须是很好地连接到阿姆斯特丹三个会话边界控制器 (Sbc) 时美国西用户必须是很好地连接到两个 SBCs 西雅图。 连接顺畅意味着它们与 SBC 或网关位于相同的网络站点中，或使用具有合适带宽的 WAN 链路。
  
![云连接器容量](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> 如果位于苏黎世的用户访问西雅图办公室，并且要使用内部网络在来访用户与欧洲网关之间发送媒体流量（而不是通过 Internet），则必须确保西雅图办公室与欧洲 SBC 或网关所在的阿姆斯特丹办公室之间连接顺畅。 
  
## <a name="codecs-used-in-media-bypass"></a>媒体旁路中使用的编解码器

启用媒体旁路功能后，客户端与 SBC 或网关之间的媒体流量将使用 G.711 编解码器。 
  
## <a name="see-also"></a>另请参阅

[在云连接器版本中部署媒体旁路](deploy-media-bypass-in-cloud-connector.md)