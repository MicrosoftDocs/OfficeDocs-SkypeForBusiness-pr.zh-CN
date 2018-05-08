---
title: Skype for Business Server 2015 中的 PSTN 连接组件
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: 了解有关 SIP 中继和 PSTN 网关的 Skype 中的企业语音的企业服务器。
ms.openlocfilehash: 4f346209b483a3d469beba233bd22ee39e45745a
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="pstn-connectivity-components-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 PSTN 连接组件
 
了解有关 SIP 中继和 PSTN 网关的 Skype 中的企业语音的企业服务器。
  
企业级 VoIP 解决方案必须以始终如一的服务质量 (QoS) 提供来往于公用电话交换网 (PSTN) 的呼叫。 此外，用户在发起和接收呼叫时应不必了解底层技术。 从用户的角度来看，企业语音基础结构与 PSTN 之间的呼叫应该就像是另一个 SIP 会话。
  
对于 PSTN 连接，既可以部署 SIP 中继，也可以部署 PSTN 网关（使用 PBX，也称为直接 SIP 链接；或不使用 PBX）。
  
## <a name="sip-trunking"></a>SIP 中继

为使用 PSTN 网关的替代方法，您可以连接到 PSTN 的企业语音解决方案，使用 SIP 中继。 SIP 中继可以实现以下方案：
  
- 企业防火墙内外的企业用户可以拨打由符合 E.164 标准的号码指定的本地或长途电话，该电话将作为相应服务提供商的一项服务终止于 PSTN 上。
    
- 通过拨打与企业防火墙内外的企业用户关联的外线直拨分机 (DID) 号码，任何 PSTN 订阅者都可以与该企业用户取得联系。
    
使用此部署解决方案需要 SIP 中继服务提供商。 
  
## <a name="pstn-gateways"></a>PSTN 网关

PSTN 网关是转换信号的第三方设备和企业语音基础结构与 PSTN 或 PBX 之间的媒体。 PSTN 网关与中介服务器演示 PSTN 或 PBX 的企业语音客户端调用工作。 中介服务器还提供来自企业语音客户端到 PSTN 网关的路由到 PSTN 或 PBX 的呼叫。 与 Microsoft 合作提供对业务服务器使用 Skype 的设备的合作伙伴列表，请参阅[Microsoft 统一通信合作伙伴网站](https://go.microsoft.com/fwlink/p/?linkId=202836)。 
  
## <a name="private-branch-exchanges"></a>专用交换机

 如果您具有现有的语音基础结构使用专用交换机 (PBX)，您可以使用企业语音的 PBX。
  
支持的企业语音-PBX 集成方案如下所示：
  
- 绕过支持媒体的 IP-PBX，具有中介服务器。
    
- 要求使用单独的 PSTN 网关的 IP-PBX。
    
- 时分多路复用 (TDM) PBX，使用单独的 PSTN 网关。
    
> [!NOTE]
> 媒体旁路将不会与每个 PSTN 网关、IP-PBX 和 SBC 进行交互操作。 Microsoft 与认证合作伙伴一起对一组 PSTN 网关和 SBC 进行了测试，另外也对 Cisco IP-PBX 进行了一些测试。 仅与产品支持媒体绕过和版本列在[统一通信开放互操作性计划的 Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406)。 
  
有关提供企业语音解决方案的合作伙伴的详细信息，请参阅[Microsoft 统一通信合作伙伴网站](https://go.microsoft.com/fwlink/p/?linkId=202836)。
  
有关提供企业语音硬件解决方案，包括 PSTN 网关的合作伙伴的详细信息，请参阅[Microsoft 统一通信合作伙伴网站](https://go.microsoft.com/fwlink/p/?linkId=202836)。
  

