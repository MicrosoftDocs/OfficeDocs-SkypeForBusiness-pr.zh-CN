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
ms.custom: Strat_SB_Hybrid
ms.assetid: e69ac58c-e8fe-40bc-a4c8-f0a0190fbaa7
description: 阅读本主题，以了解使用云连接器版本 2.0 版和更高版本实现媒体旁路的规划注意事项。 有关部署媒体信息回避，请参阅部署媒体绕过云连接器版中。
ms.openlocfilehash: bf659b7ea7b872a09e8c8ce2358c04cde2ba11d7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a>在云连接器版本中规划媒体旁路
 
阅读本主题，以了解使用云连接器版本 2.0 版和更高版本实现媒体旁路的规划注意事项。 有关部署媒体信息绕过，请参阅[部署媒体绕过云连接器版中](deploy-media-bypass-in-cloud-connector.md)。
  
媒体回避允许客户端直接与公共交换电话网络 (PSTN) 的下一跃点发送媒体 — — 网关或会话边框控制器 (SBC) — — 并消除通过媒体路径中的云连接器版组件。
  
媒体旁路功能可通过减少延迟、可能的数据包丢失和潜在的故障点数来提高语音质量。 消除了媒体的跳过电话处理减少了云接头，从而使更多的并发呼叫，负载，并可提高可伸缩性。 
  
 释放云连接器从媒体处理任务可能会降低的基础结构需要，云接口装置的数量，因此您应该启用媒体回避任何可能的时候。
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a>媒体旁路对媒体和信号路径的影响

在具有和没有媒体旁路时，虽然发送信号都会采用相同的路径，但媒体流会有所不同。下图显示了具有和没有媒体旁路功能的拓扑中的媒体和信号路径。 
  
例如，在下列拓扑 — — 不使用媒体的旁路 — Skype 业务客户端发出 PSTN 呼叫到外部号码、 SIP 信号转到 Office 365 和 Office 365 然后将根据最终用户的声音信号流策略。 对于云连接器用户，语音策略指导信号流云接头边缘服务器，该服务器然后将信号传输的通信路由到 PSTN 会话边框控制器 (SBC) 或通过云连接器中介服务器的网关。 媒体从排 Skype 业务客户端云连接器中介服务器，然后为 SBC 或网关，如下面的关系图中所示：
  
**媒体和无介质的信号传输路径绕过**

![没有媒体旁路功能的信号](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
来自 PSTN 的拨入通话将以相反方向使用相同的信号路径。 对于内部用户，媒体将最终仍 Skype 业务客户端和云连接器中介服务器然后 SBC 或网关之间流动。
  
在下一步的拓扑结构 — — 采用媒体的旁路 — 信号传输采用相同的路径，但媒体流业务客户端与 SBC 或网关，Skype 之间直接下图中所示：
  
**媒体和媒体信号传输路径绕过**

![有媒体旁路功能的信号](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a>多站点方案和媒体旁路

当您希望提供电话服务，到多个站点使用单个云接头装置时，则也可以回避媒体。 因为云连接器无法路由调用基于源或目标数字，大多数企业部署 SBC 或网关后面云连接器做出路由决策。 在此方案中，媒体旁路使客户端与中心 SBC 或网关之间不再存在跃点，如下图所示：
  
**多站点的应用程序**

![云连接器多站点示例](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. SIP 通信流向中苏黎世的用户从 Office 365。
    
2. 通信然后传送到云接头装置在阿姆斯特丹作为用户语音路由策略中指定。
    
3. 在阿姆斯特丹云接头装置向阿姆斯特丹的中央网关发送 SIP 通信。
    
4. 在阿姆斯特丹的中央网关制定适当的路由决策，然后将通信发送到 SBC 或网关在苏黎世，在企业客户端和 SBC 或网关在阿姆斯特丹 Skype 之间直接的媒体流时。
    
 此方法允许为每一个云连接器部署更多的用户服务集中云连接器的位置。 即使从介质路径消除了云连接器，在集中式多站点方案媒体可能仍然通过 WAN 倍所需流动集中的 SBC 或网关。
  
如果客户端是公司网络外部的出站呼叫，介质流量的流动通过云连接器和 WAN 链接，苏黎世和阿姆斯特丹，之间的边缘、 中介服务器下面的关系图中所示：
  
![云连接器多站点示例 2](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a>支持使用媒体旁路的客户端

绕过媒体的第一个版本中，唯一受支持的客户端是业务 2016年的 Windows 客户端的 Office 365 ProPlus，16.0.7870.2020 版本一部分的 Skype 或更高版本。 客户可以使用任意频道：当前、延期或首次发布延期频道。 
  
> [!NOTE]
> 如果你将客户端 VPN 解决方案与 Skype for Business 客户端结合使用，则只有 VPN 拆分隧道配置支持媒体旁路。 
  
有关发行渠道的详细信息，请参阅[概述 Office 365 ProPlus 更新通道](https://support.office.com/en-us/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US)。
  
不同的渠道中的客户端的当前发行版，请参阅[Office 365 更新通道版本的客户端](https://technet.microsoft.com/en-us/office/mt465751.aspx)。 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a>使用媒体旁路功能时的云连接器容量注意事项

没有媒体绕过 — — 这取决于硬件 — — 云接头装置到 500 个呼叫要求媒体要经过中介服务器可以处理从 50。 有关详细信息，请参阅[规划业务云连接器版 Skype](https://technet.microsoft.com/en-us/library/mt605227.aspx)。 
  
启用媒体旁路功能时，受支持版本的内部客户端不使用中介服务器，因此内部客户端数会显著增加。 
  
如上文所述，外部客户端或不受支持的客户端将媒体使用的云接头边缘和中介服务器。 在计算多少云接头装置应放置在一个站点时，必须考虑来自外部的用户和不受支持的客户端上的用户的通信。
  
## <a name="cloud-connector-supports-always-bypass-mode"></a>云连接器支持“始终旁路”模式

云连接器支持仅始终旁路模式。 在本地环境中，有两个选项：“始终旁路”和“使用站点和区域信息”。
  
“始终旁路”意味着将对以内部客户端作为源或目标点的所有 PSTN 通话尝试媒体旁路功能。为确定客户端是内部客户端还是外部客户端，将使用中介服务器虚拟机上的网站。如果客户端可以访问该站点，则认为它是内部客户端，并将使用媒体旁路功能。如果客户端无法访问该站点（例如，客户端在家庭网络上），则不使用媒体旁路功能。 
  
“始终旁路”要求用户与 PSTN 站点内的 PSTN 网关之间的连接畅通无阻。 
  
有关详细信息，请参阅[规划业务云连接器版 Skype](https://technet.microsoft.com/en-us/library/mt605227.aspx)。 
  
例如，在下图中，欧洲用户必须很好地连接到阿姆斯特丹三个会话边框控制器 (SBCs) 虽然美国西用户必须很好地连接到两个 SBCs 在西雅图。 连接顺畅意味着它们与 SBC 或网关位于相同的网络站点中，或使用具有合适带宽的 WAN 链路。
  
![云连接器容量](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> 如果位于苏黎世的用户访问西雅图办公室，并且要使用内部网络在来访用户与欧洲网关之间发送媒体流量（而不是通过 Internet），则必须确保西雅图办公室与欧洲 SBC 或网关所在的阿姆斯特丹办公室之间连接顺畅。 
  
## <a name="codecs-used-in-media-bypass"></a>媒体旁路中使用的编解码器

启用媒体旁路功能后，客户端与 SBC 或网关之间的媒体流量将使用 G.711 编解码器。 
  
## <a name="see-also"></a>另请参阅

#### 

[部署云连接器版中的媒体回避](deploy-media-bypass-in-cloud-connector.md)

