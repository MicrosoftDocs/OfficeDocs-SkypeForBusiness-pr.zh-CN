---
title: 为业务服务器部署中 Skype 的媒体绕过
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
description: 为业务 Server 企业语音部署中 Skype 的媒体绕过。 包括先决条件和部署过程清单。
ms.openlocfilehash: 307c3ff66adf042a984c544a722517d2709154d0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223104"
---
# <a name="deploy-media-bypass-in-skype-for-business-server"></a>为业务服务器部署中 Skype 的媒体绕过
 
为业务 Server 企业语音部署中 Skype 的媒体绕过。 包括先决条件和部署过程清单。
  
本主题假定您已发布和配置至少一个或多个中介服务器和对等至少一个网关，以提供 PSTN 连接。 这些任务的详细信息，请参阅[部署中介服务器在拓扑生成器中在 Skype 业务服务器](deploy-a-mediation-server.md)和[定义拓扑生成器中的业务服务器 Skype 的网关](define-a-gateway.md)。
  
 如果您连接到的对等方是 SIP 中继提供商的 SBC，请确保该提供商是合格的提供商，且支持媒体旁路。例如，很多 SIP 中继提供商仅允许其 SBC 接收来自中介服务器的流量。如果这样，则不得为出现故障的中继启用旁路。同时，只有您的组织向 SIP 中继提供商显示其内部网络 IP 地址后，您才能启用媒体旁路。
  
> [!NOTE]
> 媒体旁路将不会与每个 PSTN 网关、IP-PBX 和 SBC 进行交互操作。 Microsoft 与认证合作伙伴一起对一组 PSTN 网关和 SBC 进行了测试，另外也对 Cisco IP-PBX 进行了一些测试。 仅与产品支持媒体绕过和版本上列出[统一通信开放互操作性计划的 Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406)。 
  
如果您已选择配置呼叫允许控制 (CAC)（企业语音的另一种高级功能），请注意，呼叫允许控制所执行的带宽保留不会应用于已应用媒体旁路的任何呼叫。首先验证是否应用了媒体旁路，如果已经应用，则不会对该呼叫使用呼叫允许控制；仅当媒体旁路检查失败时，才会检查呼叫允许控制。因此，对于路由至 PSTN 的任何特定呼叫，这两种功能是相互排斥的。这是符合逻辑的，因为媒体旁路假设呼叫中的媒体终结点间不存在带宽约束；无法在带宽受限的链接上执行媒体旁路。因此，会将以下情形之一应用于 PSTN 呼叫：a) 媒体绕过中介服务器，呼叫允许控制不为呼叫保留带宽；或者，b) 呼叫允许控制将带宽保留应用于呼叫，媒体由呼叫中涉及的中介服务器处理。
  
除了为与对等方关联的各个中继连接启用媒体旁路功能外，还必须在全局范围内启用媒体旁路功能。全局媒体旁路设置可以指定始终为对 PSTN 的呼叫尝试媒体旁路，或者指定通过将子网映射到网络站点和网络区域来使用媒体旁路，这与呼叫允许控制（另一高级语音功能）所执行的操作类似。同时启用媒体旁路和呼叫允许控制后，在确定是否使用媒体旁路时，会自动使用为呼叫允许控制指定的网络区域、网络站点和子网信息。这意味着，启用呼叫允许控制后无法指定始终为对 PSTN 的呼叫尝试媒体旁路。
  
> [!NOTE]
> 使用这些步骤配置媒体旁路时，假定客户端和中介服务器对等方（例如，SIP 中继提供商的 PSTN 网关、IP-PBX 或 SBC）之间的连接工作正常。 如果链接上有任何带宽限制，则媒体旁路无法应用于呼叫。 媒体旁路将不会与每个 PSTN 网关、IP-PBX 和 SBC 进行交互操作。 Microsoft 与认证合作伙伴一起对一组 PSTN 网关和 SBC 进行了测试，另外也对 Cisco IP-PBX 进行了一些测试。 仅与产品支持媒体绕过和版本上列出[统一通信开放互操作性计划的 Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406)。 
  
## <a name="deployment-process-for-media-bypass"></a>媒体旁路的部署过程

下表概述了媒体旁路部署过程。 
  
|**阶段**|**步骤**|**Roles**|**部署文档**|
|:-----|:-----|:-----|:-----|
|配置用于媒体旁路的中继  <br/> |如果还未配置，请配置一个或多个用于媒体旁路的中继。  <br/> | 以 RTCUniversalServerAdmins 组或 CsVoiceAdministrator、 CsServerAdministrator 或 CsAdministrator 角色的成员的成员 <br/> |[为业务 Server 使用 Skype 中的媒体旁路配置中继](configure-trunk-with-media-bypass.md) <br/> |
|全局配置媒体旁路  <br/> |为发给 PSTN 的所有呼叫，或者基于网络站点和网络区域的特定呼叫配置媒体旁路。  <br/> | 以 RTCUniversalServerAdmins 组或 CsVoiceAdministrator、 CsServerAdministrator 或 CsAdministrator 角色的成员的成员 <br/> |[Skype 业务服务器以始终绕过中介服务器中配置媒体绕过](bypass-the-mediation-server.md) <br/> [在 Business Server 以使用站点和区域信息的 Skype 中配置媒体绕过全局设置](use-site-and-region-information.md) <br/> |
|如有必要，将子网与网络站点关联  <br/> |如果配置媒体旁路来使用站点和区域信息，那就必须将部署的子网与网络站点和区域关联（如果还未对另一个语音功能进行这样的配置）。  <br/> | 以 RTCUniversalServerAdmins 组或 CsVoiceAdministrator、 CsServerAdministrator 或 CsAdministrator 角色的成员的成员 <br/> |[Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) <br/> |
   

