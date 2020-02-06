---
title: 在 Skype for Business 服务器中设计 E9 的 SIP 主干-1-1
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
ms.assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
description: 为在 Skype for Business Server 企业语音中使用 SIP 中继提供商的 E9 部署计划 SIP 中继拓扑。
ms.openlocfilehash: bd310b39affbea9b4d9328c66b54712c0d388b8d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803072"
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server"></a>在 Skype for Business 服务器中设计 E9 的 SIP 主干-1-1
 
为在 Skype for Business Server 企业语音中使用 SIP 中继提供商的 E9 部署计划 SIP 中继拓扑。
  
Skype for business 服务器使用 SIP 中继将紧急电话连接到 E9 服务提供商。 您可以为一个中央站点、多个中央站点或每个分支站点的 E9-1-1 设置紧急服务 SIP 中继。 但是，如果呼叫者的站点和托管紧急服务 SIP 主干的网站之间的 WAN 链接不可用，则由用户在断开连接的站点处发出的呼叫将需要用户语音策略中的特殊电话使用记录，并将呼叫路由到通过本地公共交换电话网络（PSTN）网关 ECRC。 如果呼叫允许控制并发呼叫限制有效，则会出现相同情况。
  
可通过两种方式在 Skype for Business Server 环境中实施 SIP 主干：
  
- 使用多主中介服务器，这些服务器使用其面向外部的公共路由接口与 SIP 中继提供商通信。
    
- 使用本地会话边界控制器（SBC）在中介服务器和 SIP 中继提供商的服务之间提供安全的 demarcation 点。
    
如果您选择后一种方法，请确保您选择的 SBC 品牌和型号已经过认证并且支持将状态信息数据格式位置对象 (PIDF-LO) 位置数据作为其 SIP INVITE 一部分传递。 否则，呼叫将在缺少位置信息的情况下到达紧急服务的服务提供商。 有关认证的 SBCs 的详细信息，请参阅["适用于 Microsoft Lync 的基础结构认证"](https://go.microsoft.com/fwlink/p/?LinkId=248425)和["Skype For Business 的电话架构"](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)。 
  
E9-1-1 的服务提供商会向您提供对 SBC 对的访问权，以实现冗余。 您需要对中介服务器拓扑和呼叫路由配置进行几项决策。 您是否平等看待两个 SBC 并对它们之间的呼叫使用循环路由，或者您是否以其中一个 SBC 为主，而另一个为辅？
  
有关在 Skype for Business 服务器中部署 SIP 主干的详细信息，请参阅[skype For Business 服务器中的 sip 中继](sip-trunking.md)。 下列问题将帮助您确定如何部署 E9-1-1 的 SIP 中继。
  
 **应该通过专门租用的 Internet 连接还是共享的 Internet 连接部署 SIP 中继？**
  
> 紧急呼叫必须始终保持连接状态，这一点很重要。专用线路将提供不会被网络中其他流量抢占的连接以及实现服务质量 (QoS) 的功能。请记住，如果通过公共 Internet 连接到紧急服务的服务提供商，并且需要确保紧急呼叫的保密性，则需要 IPSec 加密。 
    
 **您的 E9 部署是否是为灾难容许而设计的？**
  
> 由于这是紧急解决方案，因此复原很重要。 在灾难容错位置部署主要和辅助中介服务器以及 SIP 中继。 最好是部署最接近其支持的用户的主中介服务器，并通过辅助中介服务器（位于不同的地理位置）路由故障转移呼叫。 
    
 **是否应该为每个分支机构部署单独的 SIP 中继？**
  
> Skype for Business 服务器提供了多个用于处理分支机构中的语音复原的策略，包括：具有弹性数据网络、在每个分支处部署 SIP 主干或在中断期间将呼叫推送到本地网关。 有关详细信息，请参阅[Skype For Business 服务器中的 SIP 中继](sip-trunking.md)。
    
 **是否已启用呼叫允许控制 (CAC)？**
  
> Skype for Business 服务器不会处理与普通通话不同的紧急呼叫。 因此，带宽管理或呼叫允许控制 (CAC) 将对 E9-1-1 配置产生负面影响。 如果已启用 CAC，并且路由紧急呼叫的链接上的流量超过配置的限制，那么将阻止紧急呼叫或将其路由至本地 PSTN 网关。 如本主题前面所述，此类呼叫不包含位置数据，必须手动将其路由到 ECRC。
    

