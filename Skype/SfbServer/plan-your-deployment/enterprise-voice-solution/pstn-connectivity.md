---
title: PSTN 连接组件Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: 了解 sip 中继和 PSTN 网关，企业语音中Skype for Business Server。
ms.openlocfilehash: 8aa3914eac1a716380b69971b0c576186dbfac17
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620968"
---
# <a name="pstn-connectivity-components-in-skype-for-business-server"></a>PSTN 连接组件Skype for Business Server
 
了解 sip 中继和 PSTN 网关，企业语音中Skype for Business Server。
  
企业级 VoIP 解决方案必须以始终如一的服务质量 (QoS) 提供来往于公用电话交换网 (PSTN) 的呼叫。此外，用户在发起和接收呼叫时应不必了解底层技术。从用户的角度来看，企业语音基础结构与 PSTN 之间的呼叫应该就像是另一个 SIP 会话。
  
对于 PSTN 连接，可以使用 PBX 部署 SIP 中继或 PSTN (（也称为直接 SIP 链接）或部署 PBX) 。
  
## <a name="sip-trunking"></a>SIP 中继

作为使用 PSTN 网关的替代方案，可以使用 SIP 中继将企业语音解决方案连接到 PSTN。SIP 中继可以实现以下方案：
  
- 企业防火墙内外的企业用户可以拨打由符合 E.164 标准的号码指定的本地或长途电话，该电话将作为相应服务提供商的一项服务终止于 PSTN 上。
    
- 通过拨打与企业防火墙内外的企业用户关联的外线直拨分机 (DID) 号码，任何 PSTN 订阅者都可以与该企业用户取得联系。
    
使用此部署解决方案需要 SIP 中继服务提供商。 
  
## <a name="pstn-gateways"></a>PSTN 网关

PSTN 网关是在企业语音基础结构与 PSTN 或 PBX 之间转换信号和媒体的第三方设备。 PSTN 网关与中介服务器配合工作，以向企业语音客户端提交 PSTN 或 PBX 呼叫。 中介服务器还将来自企业语音客户端的呼叫提交到 PSTN 网关，以便路由到 PSTN 或 PBX。 有关与 Microsoft 合作以提供与 Skype for Business Server 合作的设备的合作伙伴列表，请参阅 Microsoft 统一[通信合作伙伴网站](https://go.microsoft.com/fwlink/p/?linkId=202836)。 
  
## <a name="private-branch-exchanges"></a>专用交换机

 如果您现有的语音基础结构使用专用交换机或 PBX (，) PBX 与 企业语音。
  
支持的企业语音-PBX 集成方案包括：
  
- 支持媒体绕过的 IP-PBX，具有中介服务器。
    
- 要求使用单独的 PSTN 网关的 IP-PBX。
    
- 时分多路复用 (TDM) PBX，使用单独的 PSTN 网关。
    
> [!NOTE]
> 媒体绕过将不会与每个 PSTN 网关、IP-PBX 和 SBC 进行交互操作。 Microsoft 已经与认证合作伙伴一起测试了一组 PSTN 网关和 SDC，并且已经使用 Cisco IP-PBX 进行了一些测试。 只有统一通信开放式互操作性计划 - Lync Server 中列出的产品和版本才支持 [媒体旁路](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)。 
  
有关提供解决方案企业语音的详细信息，请参阅[Microsoft 统一通信合作伙伴网站](https://go.microsoft.com/fwlink/p/?linkId=202836)。
  
有关提供 PSTN 企业语音解决方案（包括 PSTN 网关）的合作伙伴的详细信息，请参阅[Microsoft 统一通信合作伙伴网站](https://go.microsoft.com/fwlink/p/?linkId=202836)。
