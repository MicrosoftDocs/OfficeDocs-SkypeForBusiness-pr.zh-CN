---
title: 在云连接器版本中规划媒体旁路
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
description: 阅读本主题，以了解使用云连接器版本 2.0 版和更高版本实现媒体旁路的规划注意事项。 有关部署媒体绕过的信息，请参阅在云连接器版本中部署媒体旁路。
ms.openlocfilehash: 67598cbe31dac074bf360ba6fe1462544fe12c5b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814490"
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a>在云连接器版本中规划媒体旁路
 
阅读本主题，以了解使用云连接器版本 2.0 版和更高版本实现媒体旁路的规划注意事项。 有关部署媒体绕过的信息，请参阅[在云连接器版本中部署媒体旁路](deploy-media-bypass-in-cloud-connector.md)。
  
媒体绕过允许客户将媒体直接发送到公共交换式电话网络（PSTN）下一跃点（即网关或会话边界控制器（SBC）），并从媒体路径中删除云连接器版本组件。
  
媒体旁路功能可通过减少延迟、可能的数据包丢失和潜在的故障点数来提高语音质量。 消除绕过通话的媒体处理可减少云连接线上的负载，从而实现更高的并发通话次数，并且可以提高可伸缩性。 
  
 从媒体处理任务中释放云连接器可能会减少基础结构所需的云连接器装置的数量，因此应尽可能启用 "媒体绕过"。
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a>媒体旁路对媒体和信号路径的影响

在具有和没有媒体旁路时，虽然发送信号都会采用相同的路径，但媒体流会有所不同。下图显示了具有和没有媒体旁路功能的拓扑中的媒体和信号路径。 
  
例如，在以下拓扑（不使用媒体旁路）中，Skype for Business 客户端将 PSTN 呼叫置于外部号码，SIP 信号转到 Office 365，然后 Office 365 将根据最终用户的语音指示信号流量设置. 对于云连接器用户，语音策略将通知流量定向到云连接器边缘服务器，然后通过云连接器中介服务器将信号流量路由到 PSTN 会话边界控制器（SBC）或网关。 媒体从 Skype for Business 客户端流向云连接器中介服务器，然后指向 SBC 或网关，如下图所示：
  
**没有媒体旁路功能的媒体和信号路径**

![没有媒体旁路功能的信号](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
来自 PSTN 的拨入通话将以相反方向使用相同的信号路径。 对于内部用户，媒体仍将在 Skype for Business 客户端和云连接器中介服务器以及 SBC 或网关之间最终流动。
  
在下一个拓扑中，它可以使用媒体旁路-信号采用相同的路径，但媒体直接在 Skype for Business 客户端和 SBC 或网关之间流动，如下图所示：
  
**具有媒体旁路功能的媒体和信号路径**

![有媒体旁路功能的信号](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a>多站点方案和媒体旁路

当您希望使用单个云连接器设备向多个站点提供电话服务时，媒体绕过功能也很有用。 由于云连接器无法基于源或目标号码路由呼叫，因此大多数企业都在云连接器背后部署 SBC 或网关以做出路由决策。 在此方案中，媒体旁路使客户端与中心 SBC 或网关之间不再存在跃点，如下图所示：
  
**多站点应用**

![云连接器多站点示例](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. SIP 流量从苏黎世用户流入到 Office 365。
    
2. 然后，流量将按用户语音路由策略中指定的阿姆斯特丹路由到云连接器装置。
    
3. 阿姆斯特丹中的云连接器装置将 SIP 流量发送到位于阿姆斯特丹的中央网关。
    
4. 在阿姆斯特丹中，"中央网关" 建立适当的路由决策，然后将流量发送到苏黎世中的 SBC 或网关，而媒体直接在 Skype for Business 客户端和 SBC 或网关之间以阿姆斯特丹的形式流动。
    
   此方法允许为每一个云连接器部署提供更多用户，其中云连接器是集中式的。 即使从媒体路径中消除了云连接器，在集中式多站点方案媒体中，仍可能会根据需要将 WAN 传递两次，以流过集中的 SBC 或网关。
  
如果客户端在公司网络外部放置出站呼叫，则媒体流量将通过苏黎世和阿姆斯特丹之间的云连接器和 WAN 链接的边缘和中介服务器流动，如下图所示：
  
![云连接器多站点示例 2](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a>支持使用媒体旁路的客户端

第一次发布媒体旁路时，唯一支持的客户是 Office 365 专业增强版的 Skype for business 2016 Windows 客户端，版本16.0.7870.2020 或更高版本。 客户可以使用任意频道：当前、延期或首次发布延期频道。 
  
> [!NOTE]
> 如果你将客户端 VPN 解决方案与 Skype for Business 客户端结合使用，则只有 VPN 拆分隧道配置支持媒体旁路。 
  
有关发布频道的详细信息，请参阅[Office 365 专业增强版更新频道概述](https://support.office.com/en-us/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US)。
  
有关不同通道中的客户端的当前发行版本，请参阅[Office 365 专业增强版更新的发布信息](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)。 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a>使用媒体旁路功能时的云连接器容量注意事项

无需媒体绕过-根据硬件的不同，云连接器设备可以从50同时处理到500的同时通话，这需要媒体通过中介服务器旅行。 有关详细信息，请参阅[规划 Skype for Business 云连接器版本](https://technet.microsoft.com/en-us/library/mt605227.aspx)。 
  
启用媒体旁路功能时，受支持版本的内部客户端不使用中介服务器，因此内部客户端数会显著增加。 
  
如上文所述，外部客户端或不支持的客户端将使用云连接线边缘和面向媒体的中介服务器。 计算网站中应放置多少个云连接器设备时，必须考虑来自外部用户和不受支持的客户端上的用户的流量。
  
## <a name="cloud-connector-supports-always-bypass-mode"></a>云连接器支持“始终旁路”模式

云连接器仅支持始终绕过模式。 在本地环境中，有两个选项：“始终旁路”和“使用站点和区域信息”。
  
“始终旁路”意味着将对以内部客户端作为源或目标点的所有 PSTN 通话尝试媒体旁路功能。为确定客户端是内部客户端还是外部客户端，将使用中介服务器虚拟机上的网站。如果客户端可以访问该站点，则认为它是内部客户端，并将使用媒体旁路功能。如果客户端无法访问该站点（例如，客户端在家庭网络上），则不使用媒体旁路功能。 
  
“始终旁路”要求用户与 PSTN 站点内的 PSTN 网关之间的连接畅通无阻。 
  
有关详细信息，请参阅[规划 Skype for Business 云连接器版本](https://technet.microsoft.com/en-us/library/mt605227.aspx)。 
  
例如，在下图中，欧洲用户必须与三个讲座的边框控制器（SBCs）保持很好的联系，因为我们的西部用户必须与西雅图的两个 SBCs 保持很好的联系。 连接顺畅意味着它们与 SBC 或网关位于相同的网络站点中，或使用具有合适带宽的 WAN 链路。
  
![云连接器容量](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> 如果位于苏黎世的用户访问西雅图办公室，并且要使用内部网络在来访用户与欧洲网关之间发送媒体流量（而不是通过 Internet），则必须确保西雅图办公室与欧洲 SBC 或网关所在的阿姆斯特丹办公室之间连接顺畅。 
  
## <a name="codecs-used-in-media-bypass"></a>媒体旁路中使用的编解码器

启用媒体旁路功能后，客户端与 SBC 或网关之间的媒体流量将使用 G.711 编解码器。 
  
## <a name="see-also"></a>另请参阅

[在云连接器版本中部署媒体旁路](deploy-media-bypass-in-cloud-connector.md)
