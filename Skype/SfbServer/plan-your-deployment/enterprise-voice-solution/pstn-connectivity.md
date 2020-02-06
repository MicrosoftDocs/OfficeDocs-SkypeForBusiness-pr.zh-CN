---
title: Skype for Business 服务器中的 PSTN 连接组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: 了解 Skype for Business 服务器中的企业语音 SIP 中继和 PSTN 网关。
ms.openlocfilehash: 443f5425beeed5b032968837ac56ce3a26468cdc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802532"
---
# <a name="pstn-connectivity-components-in-skype-for-business-server"></a>Skype for Business 服务器中的 PSTN 连接组件
 
了解 Skype for Business 服务器中的企业语音 SIP 中继和 PSTN 网关。
  
企业级 VoIP 解决方案必须以始终如一的服务质量 (QoS) 提供来往于公用电话交换网 (PSTN) 的呼叫。 此外，用户在发起和接收呼叫时应不必了解底层技术。 从用户的角度来看，企业语音基础结构与 PSTN 之间的通话似乎就像是另一个 SIP 会话。
  
对于 PSTN 连接，既可以部署 SIP 中继，也可以部署 PSTN 网关（使用 PBX，也称为直接 SIP 链接；或不使用 PBX）。
  
## <a name="sip-trunking"></a>SIP 中继

作为使用 PSTN 网关的替代方法，你可以使用 SIP 中继将企业语音解决方案连接到 PSTN。 SIP 中继可以实现以下方案：
  
- 企业防火墙内外的企业用户可以拨打由符合 E.164 标准的号码指定的本地或长途电话，该电话将作为相应服务提供商的一项服务终止于 PSTN 上。
    
- 通过拨打与企业防火墙内外的企业用户关联的外线直拨分机 (DID) 号码，任何 PSTN 订阅者都可以与该企业用户取得联系。
    
使用此部署解决方案需要 SIP 中继服务提供商。 
  
## <a name="pstn-gateways"></a>PSTN 网关

PSTN 网关是在企业语音基础结构和 PSTN 或 PBX 之间转换信号和媒体的第三方设备。 PSTN 网关与中介服务器配合使用，向企业语音客户端提供 PSTN 或 PBX 呼叫。 中介服务器还将来自企业语音客户端的呼叫提供给 PSTN 网关，以便路由到 PSTN 或 PBX。 有关与 Microsoft 协作以提供与 Skype for Business 服务器配合使用的设备的合作伙伴列表，请参阅[Microsoft 统一通信合作伙伴网站](https://go.microsoft.com/fwlink/p/?linkId=202836)。 
  
## <a name="private-branch-exchanges"></a>专用交换机

 如果您有一个使用专用分支交换（PBX）的语音基础结构，则可以将 PBX 与企业语音配合使用。
  
支持的企业语音 PBX 集成方案如下所示：
  
- 使用中介服务器支持媒体旁路的 IP PBX。
    
- 要求使用单独的 PSTN 网关的 IP-PBX。
    
- 时分多路复用 (TDM) PBX，使用单独的 PSTN 网关。
    
> [!NOTE]
> 媒体旁路将不会与每个 PSTN 网关、IP-PBX 和 SBC 进行交互操作。 Microsoft 与认证合作伙伴一起对一组 PSTN 网关和 SBC 进行了测试，另外也对 Cisco IP-PBX 进行了一些测试。 只有在统一通信中列出的产品和版本才支持媒体旁路[打开互操作性计划-Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406)。 
  
有关提供企业语音解决方案的合作伙伴的详细信息，请参阅[Microsoft 统一通信合作伙伴网站](https://go.microsoft.com/fwlink/p/?linkId=202836)。
  
有关提供企业语音硬件解决方案（包括 PSTN 网关）的合作伙伴的详细信息，请参阅[Microsoft 统一通信合作伙伴网站](https://go.microsoft.com/fwlink/p/?linkId=202836)。
  

