---
title: 在部署媒体Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
description: 部署媒体旁路Skype for Business Server 企业语音。 包括先决条件和部署过程清单。
ms.openlocfilehash: c5699d1116faa6bc3b8ae0178ec617bcf06c1ef4
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834690"
---
# <a name="deploy-media-bypass-in-skype-for-business-server"></a>在部署媒体Skype for Business Server
 
部署媒体旁路Skype for Business Server 企业语音。 包括先决条件和部署过程清单。
  
本主题假定你已发布并配置了至少一台或多台中介服务器以及至少一个对等网关以提供 PSTN 连接。 有关这些任务的更多详细信息，请参阅 Skype for Business Server[](deploy-a-mediation-server.md)中的在拓扑生成器中部署中介服务器和在拓扑生成器中定义[Skype for Business Server。](define-a-gateway.md)
  
 如果您连接到的对等方是 SIP 中继提供商的 SBC，请确保该提供商是合格的提供商，并且该提供商支持媒体旁路。 例如，很多 SIP 中继提供商仅允许其 SBC 接收来自中介服务器的流量。 如果这样，则不得为出现故障的中继启用绕过。 同时，只有您的组织向 SIP 中继提供商显示其内部网络 IP 地址后，您才能启用媒体绕过。
  
> [!NOTE]
> 媒体绕过将不会与每个 PSTN 网关、IP-PBX 和 SBC 进行交互操作。 Microsoft 已经与认证合作伙伴一起测试了一组 PSTN 网关和 SDC，并且已经使用 Cisco IP-PBX 进行了一些测试。 只有统一通信开放式互操作性计划 - Lync Server 中列出的产品和版本才支持 [媒体旁路](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)。 
  
如果您已选择配置呼叫允许控制 (CAC)（企业语音的另一种高级功能），请注意，呼叫允许控制所执行的带宽保留不会应用于已应用媒体绕过的任何呼叫。首先验证是否应用了媒体绕过，如果已经应用，则不会对该呼叫使用呼叫允许控制；仅当媒体绕过检查失败时，才会检查呼叫允许控制。因此，对于路由至 PSTN 的任何特定呼叫，这两种功能是相互排斥的。这是符合逻辑的，因为媒体绕过假设呼叫中的媒体终结点间不存在带宽约束；无法在带宽受限的链接上执行媒体绕过。因此，会将以下情形之一应用于 PSTN 呼叫：a) 媒体绕过中介服务器，呼叫允许控制不为呼叫保留带宽；或者，b) 呼叫允许控制将带宽保留应用于呼叫，媒体由呼叫中涉及的中介服务器处理。
  
除了为与对等方关联的各个中继连接启用媒体绕过功能外，还必须在全局范围内启用媒体绕过功能。 全局媒体旁路设置可以指定始终尝试对 PSTN 的呼叫进行媒体旁路，或者通过使用子网到网络站点和网络区域的映射来使用媒体旁路—类似于呼叫允许控制（另一个高级语音功能）所完成的操作。 当同时启用媒体旁路和呼叫允许控制时，当确定是否使用媒体旁路时，将自动使用为呼叫允许控制指定的网络区域、网络站点和子网信息。 这意味着您无法指定启用呼叫允许控制时始终尝试媒体旁路呼叫 PSTN。
  
> [!NOTE]
> 使用这些步骤配置媒体绕过时，假定客户端和中介服务器对等方（例如，SIP 中继提供商的 PSTN 网关、IP-PBX 或 SBC）之间的连接工作正常。 如果链接上有任何带宽限制，则媒体绕过无法应用于呼叫。 媒体绕过将不会与每个 PSTN 网关、IP-PBX 和 SBC 进行交互操作。 Microsoft 已经与认证合作伙伴一起测试了一组 PSTN 网关和 SDC，并且已经使用 Cisco IP-PBX 进行了一些测试。 只有统一通信开放式互操作性计划 - Lync Server 中列出的产品和版本才支持 [媒体旁路](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)。 
  
## <a name="deployment-process-for-media-bypass"></a>媒体旁路的部署过程

下表概述了媒体旁路部署过程。 
  
|**阶段**|**步骤**|**Roles**|**部署文档**|
|:-----|:-----|:-----|:-----|
|配置用于媒体旁路的中继  <br/> |如果尚未配置，请为媒体旁路配置一个或多个中继。  <br/> | RTCUniversalServerAdmins 组的成员，或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成员 <br/> |[在客户端中配置具有媒体旁路Skype for Business Server](configure-trunk-with-media-bypass.md) <br/> |
|全局配置媒体旁路  <br/> |为 PSTN 的所有呼叫或基于网络站点和网络区域的某些呼叫配置媒体旁路。  <br/> | RTCUniversalServerAdmins 组的成员，或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成员 <br/> |[配置媒体旁路Skype for Business Server以始终绕过中介服务器](bypass-the-mediation-server.md) <br/> [将媒体旁路全局设置配置为Skype for Business Server站点和地区信息](use-site-and-region-information.md) <br/> |
|如有必要，将子网与网络站点关联  <br/> |如果将媒体旁路配置为使用站点和地区信息，则必须将部署的子网与网络站点和 (如果尚未针对其他语音功能进行关联)   <br/> | RTCUniversalServerAdmins 组的成员，或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成员 <br/> |[将子网与网络站点关联](deploy-network.md#BKMK_AssociateSubnets) <br/> |
