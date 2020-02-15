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
description: 阅读本主题，了解使用云连接器版本2.0 和更高版本实现媒体旁路的规划注意事项。 有关部署媒体旁路的信息，请参阅在云连接器版本中部署媒体旁路。
ms.openlocfilehash: 47b8d9e5d0b69b95c48f89591d75d53591b7426c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010305"
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a>在云连接器版本中规划媒体旁路
 
阅读本主题，了解使用云连接器版本2.0 和更高版本实现媒体旁路的规划注意事项。 有关部署媒体旁路的信息，请参阅[在云连接器版本中部署媒体旁路](deploy-media-bypass-in-cloud-connector.md)。
  
媒体旁路允许客户端直接向公用电话交换网（PSTN）的下一个跃点（网关或会话边界控制器（SBC））发送媒体，并从媒体路径中消除云连接器版本组件。
  
媒体旁路可以通过减少延迟、数据包丢失的可能性和潜在的故障点数来提高语音质量。 取消绕过呼叫的媒体处理降低云连接器上的负载，从而实现更高的并发呼叫数，并提高可伸缩性。 
  
 从媒体处理任务中释放云连接器可能会减少基础结构所需的云连接器设备的数量，因此应尽可能启用媒体旁路。
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a>媒体旁路如何影响媒体和信号路径

信号在使用或没有媒体旁路的情况下采用相同的路径，而媒体流将有所不同。 下图显示了具有和没有媒体旁路功能的拓扑中的媒体和信号路径。 
  
例如，在以下拓扑（不采用媒体旁路）中，Skype for Business 客户端将 PSTN 呼叫放入外部号码，SIP 信号转到 Office 365，然后 Office 365 将根据最终用户的语音指示信号流量。政策. 对于云连接器用户，语音策略将信号流量定向到云连接器边缘服务器，然后通过云连接器中介服务器将信号流量路由到 PSTN 会话边界控制器（SBC）或网关。 媒体从 Skype for Business 客户端流向云连接器中介服务器，然后传递到 SBC 或网关，如下图所示：
  
**没有媒体旁路功能的媒体和信号路径**

![没有媒体旁路的信号](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
来自 PSTN 的入站呼叫按相反方向使用相同的信号路径。 对于内部用户，媒体仍将在 Skype for Business 客户端和云连接器中介服务器之间流动，然后在 SBC 或网关之间流动。
  
在下一个拓扑中（它使用媒体旁路），信号传输采用相同的路径，但媒体直接在 Skype for Business 客户端与 SBC 或网关之间流动，如下图所示：
  
**媒体和信号路径与媒体旁路**

![使用媒体旁路发出信号](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a>多站点方案和媒体旁路

当您想要使用单个云连接器设备向多个站点提供电话服务时，媒体旁路也很有用。 由于云连接器无法根据源号码或目标号码路由呼叫，因此大多数企业都部署了 SBC 或 gateway 背后的云连接器以做出路由决策。 此方案中的媒体旁路消除了客户端与中心 SBC 或网关之间的跃点，如下图所示：
  
**多站点应用程序**

![云连接器多站点示例](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. SIP 流量从位于苏黎世的用户流向 Office 365。
    
2. 然后，流量将路由到位于阿姆斯特丹中的云连接器设备，如用户语音路由策略中所指定。
    
3. 阿姆斯特丹中的云连接器设备将 SIP 流量发送到位于阿姆斯特丹的中心网关。
    
4. 位于阿姆斯特丹的中心网关建立适当的路由决策，然后将流量发送到苏黎世中的 SBC 或网关，而媒体直接在位于阿姆斯特丹的 Skype for Business 客户端和 SBC 或网关之间流动。
    
   此方法允许在每个云连接器部署中为多个用户提供服务，云连接器集中在一起。 尽管从媒体路径中消除了云连接器，但在集中式多站点方案中，媒体仍可能会在需要时通过集中的 SBC 或网关遍历 WAN 两次。
  
如果客户端不在公司网络外部，则发出出站呼叫，媒体流量通过 "云连接器" 的边缘服务器和 "中介服务器" 和 "苏黎世" 和 "阿姆斯特丹" 之间的 WAN 链接流动，如下图所示：
  
![云连接器多站点示例2](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a>媒体旁路支持的客户端

在首次发布媒体旁路的情况下，唯一受支持的客户端是 Office 365 专业增强版16.0.7870.2020 或更高版本中的 Skype for Business 2016 Windows 客户端。 客户可以使用任何频道： Current、延期或 First Release 延期。 
  
> [!NOTE]
> 如果将客户端 VPN 解决方案与 Skype for Business 客户端结合使用，则仅支持使用 VPN 拆分隧道配置的媒体旁路。 
  
有关发布频道的详细信息，请参阅[Office 365 的更新频道概述专业增强版](https://support.office.com/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US)。
  
有关不同通道中的客户端的当前发布版本，请参阅[release information For Office 365 专业增强版](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)中的更新。 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a>媒体旁路的云连接器容量注意事项

如果没有媒体旁路功能（具体取决于硬件），云连接器设备可以处理从50到500的同时呼叫，需要媒体通过中介服务器传输。 有关详细信息，请参阅[Plan For Skype For Business Cloud Connector Edition](https://technet.microsoft.com/library/mt605227.aspx)。 
  
启用媒体旁路后，受支持的版本中的内部客户端不使用中介服务器，因此内部客户端的数量可能会显著增加。 
  
如上文所述，外部客户端或不受支持的客户端将使用云连接器边缘和中介服务器进行媒体。 在计算站点中应放入多少个云连接器设备时，必须考虑来自外部用户的流量和不受支持的客户端上的用户。
  
## <a name="cloud-connector-supports-always-bypass-mode"></a>云连接器支持始终绕过模式

云连接器仅支持始终绕过模式。 在本地环境中，有两个选项：总是绕过和使用网站和区域信息。
  
Always 旁路意味着将对内部客户端作为源或目标点的所有 PSTN 呼叫尝试媒体旁路。 若要确定客户端是内部客户端还是外部客户端，请使用中介服务器虚拟机上的网站。 如果客户端可以访问该站点，则认为它是内部的，并使用媒体旁路。 如果客户端无法访问该站点（例如，客户端在家庭网络上），则不使用媒体旁路。 
  
总是绕过 PSTN 站点中的用户和 PSTN 网关之间的无障碍连接。 
  
有关详细信息，请参阅[Plan For Skype For Business Cloud Connector Edition](https://technet.microsoft.com/library/mt605227.aspx)。 
  
例如，在下图中，欧洲用户必须连接到位于阿姆斯特丹的三个会话边界控制器（SBCs），而我们的西部用户必须与西雅图的两个 SBCs 连接良好。 "连接良好" 意味着它们位于 SBCs 或网关所在的网络站点中，或者位于具有合适带宽的 WAN 链路上。
  
![云连接器容量](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> 如果苏黎世的用户向西雅图办事处传播，并且您想要使用内部网络在欧洲的旅行用户和网关之间传递媒体流量（而不是通过 Internet），则必须确保西雅图办事处和阿姆斯特丹office，其中欧洲的 SBCs 或网关已正确连接。 
  
## <a name="codecs-used-in-media-bypass"></a>媒体旁路中使用的编解码器

启用媒体旁路后，客户端与 SBC 或网关之间的媒体流量使用 g.711 编解码器。 
  
## <a name="see-also"></a>另请参阅

[在云连接器版本中部署媒体旁路](deploy-media-bypass-in-cloud-connector.md)
