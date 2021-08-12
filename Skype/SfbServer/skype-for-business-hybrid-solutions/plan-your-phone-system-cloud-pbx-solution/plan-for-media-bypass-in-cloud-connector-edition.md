---
title: 云连接器版本中的媒体旁路规划
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e69ac58c-e8fe-40bc-a4c8-f0a0190fbaa7
description: 阅读本主题，查看使用云连接器版本 2.0 版和更高版本实现媒体旁路的规划注意事项。 有关部署媒体旁路的信息，请参阅在云连接器版本中部署媒体旁路。
ms.openlocfilehash: 622bb6cbc4acf5987d28a2c4823bdfd0e495445cba84ed01762423c8e65de576
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54339888"
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a>云连接器版本中的媒体旁路规划
 
阅读本主题，查看使用云连接器版本 2.0 版和更高版本实现媒体旁路的规划注意事项。 有关部署媒体旁路的信息，请参阅 [在云连接器版本中部署媒体旁路](deploy-media-bypass-in-cloud-connector.md)。
  
媒体旁路允许客户端将媒体直接发送到公用电话交换网 (PSTN) 下一个跃点（网关或会话边界控制器 (SBC) ）并消除媒体路径中的云连接器版本组件。
  
媒体旁路功能可以通过降低延迟、丢失数据包的可能性以及潜在的故障点数来提高语音质量。 消除旁路呼叫的媒体处理可以减少云连接器上的负载，从而增加并发呼叫数，并可以改进可伸缩性。 
  
 从媒体处理任务中释放云连接器可能会减少基础结构所需的云连接器设备的数量，因此应尽可能启用媒体旁路。
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a>媒体旁路如何影响媒体和信号路径

虽然信号采用相同路径（带或不带媒体旁路功能）时，媒体流将有所不同。 下图显示了具有和没有媒体旁路的拓扑中的媒体和信号路径。 
  
例如，在下列拓扑（没有使用媒体旁路）中，Skype for Business 客户端向外部号码发出 PSTN 呼叫，SIP 信号将转到 Microsoft 365 或 Office 365，根据最终用户语音策略将信号流量引导到该拓扑。 对于云连接器用户，语音策略将信号通信路由到云连接器边缘服务器，然后该服务器通过云连接器中介服务器将信号通信路由到 PSTN 会话边界控制器 (SBC) 或网关。 媒体从 Skype for Business 客户端流到云连接器中介服务器，然后流到 SBC 或网关，如下图所示：
  
**没有媒体旁路的媒体和信号路径**

![无媒体旁路功能的信号](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
来自 PSTN 的入站呼叫在相反方向使用相同的信号路径。 对于内部用户，媒体最终仍将在 Skype for Business 客户端与云连接器中介服务器之间流动，然后流至 SBC 或网关。
  
在采用媒体旁路的下一个拓扑中，信号采用相同的路径，但媒体直接在 Skype for Business 客户端和 SBC 或网关之间流动，如下图所示：
  
**具有媒体旁路的媒体和信号路径**

![带媒体旁路的信号](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a>多站点方案和媒体旁路

当你希望使用单个云连接器设备向多个站点提供电话服务时，媒体旁路也很有用。 由于云连接器无法基于源或目标号码路由呼叫，因此大多数企业在云连接器后面部署 SBC 或网关以做出路由决策。 此方案中的媒体旁路消除了客户端与中央 SBC 或网关之间的跃点，如下图所示：
  
**多站点应用程序**

![云连接器多站点示例](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. SIP 流量从苏黎世的用户流向Microsoft 365 Office 365。
    
2. 然后，流量将路由到位于阿姆斯特丹的云连接器设备，如用户语音路由策略中指定。
    
3. 位于阿姆斯特丹的云连接器设备将 SIP 流量发送到阿姆斯特丹的中央网关。
    
4. 阿姆斯特丹的中央网关做出相应的路由决策，然后将流量发送到位于阿姆斯特丹的 SBC 或网关，而媒体直接在 Skype for Business 客户端与位于阿姆斯特丹的 SBC 或网关之间流动。
    
   此方法允许每个云连接器部署（其中云连接器集中）为更多用户服务。 即使从媒体路径中消除云连接器，在集中的多站点方案中，媒体仍可能会按需要遍历 WAN 两次，以通过集中式 SBC 或网关。
  
如果客户端位于发出出站呼叫的企业网络外部，则媒体流量通过云连接器的边缘服务器和中介服务器以及位于阿姆斯特丹与阿姆斯特丹之间的 WAN 链路流动，如下图所示：
  
![云连接器多站点示例 2](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a>支持媒体旁路的客户端

对于第一个版本的媒体旁路，唯一受支持的客户端是 Skype for Business 2016 Windows 客户端，它是 Microsoft 365 企业应用版 版本 16.0.7870.2020 或更高的一部分。 客户可以使用任何频道：Current、Deferred 或 First Release Deferred。 
  
> [!NOTE]
> 如果结合使用客户端 VPN 解决方案和 Skype for Business，则只有 VPN 拆分隧道配置才支持媒体旁路。 
  
有关发布频道的信息，请参阅更新频道概述[Microsoft 365 企业应用版。](https://support.office.com/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US)
  
有关不同渠道中客户端的当前版本，请参阅发布更新信息以[Microsoft 365 企业应用版。](/officeupdates/release-notes-office365-proplus) 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a>媒体旁路的云连接器容量注意事项

没有媒体旁路功能（具体取决于硬件）云连接器设备可以处理 50 到 500 个同时呼叫，这些呼叫需要媒体通过中介服务器。 有关详细信息，请参阅规划[Skype for Business 云连接器版本。](./plan-skype-for-business-cloud-connector-edition.md) 
  
启用媒体旁路后，受支持版本上的内部客户端不使用中介服务器，因此内部客户端的数量会显著增加。 
  
如上所述，外部客户端或不受支持的客户端将云连接器边缘和中介服务器用于媒体。 在计算站点中应放置多少云连接器设备时，必须考虑来自外部用户的流量和不受支持客户端上的用户的流量。
  
## <a name="cloud-connector-supports-always-bypass-mode"></a>云连接器支持"始终绕过"模式

云连接器仅支持"始终绕过"模式。 在本地环境中，有两个选项："始终绕过"和"使用站点和地区信息"。
  
始终绕过意味着将尝试媒体旁路以将内部客户端作为源或目标点的所有 PSTN 呼叫。 若要确定客户端是内部客户端还是外部客户端，需使用中介服务器虚拟机上的网站。 如果客户端可以到达该站点，则被视为内部站点，并且使用媒体旁路。 如果客户端无法访问站点 (例如，客户端位于家庭) ，则不能使用媒体旁路。 
  
始终绕过需要在用户和 PSTN 站点内的 PSTN 网关之间建立无结构连接。 
  
有关详细信息，请参阅规划[Skype for Business 云连接器版本。](./plan-skype-for-business-cloud-connector-edition.md) 
  
例如，在下图中，欧洲用户必须很好地连接到位于阿姆斯特丹的三个会话边界控制器 (SDC) ，而美国西部的用户必须很好地连接到西雅图的两个 SDC。 连接良好意味着它们位于与 SDC 或网关相同的网络站点中，或者位于具有适当带宽的 WAN 链路上。
  
![云连接器容量](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> 如果来自阿姆斯特丹的用户出差到西雅图办事处，并且你想要使用内部网络在出差的用户和位于欧洲 (的网关之间传递媒体流量，而不是通过 Internet) ，则必须确保西雅图办事处和欧洲 SDC 或网关所在的阿姆斯特丹办事处符合连接条件。 
  
## <a name="codecs-used-in-media-bypass"></a>媒体旁路中使用的编解码器

启用媒体旁路后，客户端与 SBC 或网关之间的媒体流量将使用 G.711 编解码器。 
  
## <a name="see-also"></a>另请参阅

[在云连接器版本中部署媒体旁路](deploy-media-bypass-in-cloud-connector.md)