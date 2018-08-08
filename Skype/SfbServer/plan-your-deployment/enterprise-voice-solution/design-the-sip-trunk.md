---
title: SIP 中继的设计 E9-1-1 在 Skype 业务服务器
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
description: 规划业务 Server 企业语音的 Skype 中使用 SIP 中继提供商，E9-1-1 部署 SIP 中继拓扑。
ms.openlocfilehash: 8a0264bc66be97a80b9ef1d14a020f438a8a89f5
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20974663"
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server"></a>SIP 中继的设计 E9-1-1 在 Skype 业务服务器
 
规划业务 Server 企业语音的 Skype 中使用 SIP 中继提供商，E9-1-1 部署 SIP 中继拓扑。
  
Skype 业务服务器使用 SIP 中继连接到 E9-1-1 服务提供商的紧急呼叫。 您可以为一个中央站点、多个中央站点或每个分支站点的 E9-1-1 设置紧急服务 SIP 中继。 但是，如果呼叫者的站点和站点之间承载的 WAN 链路紧急服务 SIP 中继是不可用，则在断开连接的站点的用户发出的呼叫将需要在将将呼叫路由到的用户的语音策略中的特殊的电话用法记录通过本地公用电话交换网 (pstn) 网关 ECRC。 如果呼叫允许控制并发呼叫限制有效，则会出现相同情况。
  
有两种方法在 Skype 业务服务器环境中实现 SIP 中继：
  
- 使用多宿主使用其对外公共路由接口与通信 SIP 中继提供商的中介服务器。
    
- 使用本地会话边界控制器 (SBC) 提供安全的分界点中介服务器之间的 SIP 中继提供商服务。
    
如果您选择后一种方法，请确保您选择的 SBC 品牌和型号已经过认证并且支持将状态信息数据格式位置对象 (PIDF-LO) 位置数据作为其 SIP INVITE 一部分传递。 否则，呼叫将在缺少位置信息的情况下到达紧急服务的服务提供商。 有关认证 SBCs 详细信息，请参阅["基础结构限定针对 Microsoft Lync"](https://go.microsoft.com/fwlink/p/?LinkId=248425)和["电话基础结构的 Skype 的业务"](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)。 
  
E9-1-1 的服务提供商会向您提供对 SBC 对的访问权，以实现冗余。 您需要决定几个有关中介服务器拓扑结构和呼叫路由配置。 您是否平等看待两个 SBC 并对它们之间的呼叫使用循环路由，或者您是否以其中一个 SBC 为主，而另一个为辅？
  
有关业务服务器部署中 Skype 的 SIP 中继的详细信息，请参阅[Skype 业务服务器中的 SIP 中继](sip-trunking.md)。 下列问题将帮助您确定如何部署 E9-1-1 的 SIP 中继。
  
 **应该通过专门租用的 Internet 连接还是共享的 Internet 连接部署 SIP 中继？**
  
> 紧急呼叫必须始终保持连接状态，这一点很重要。专用线路将提供不会被网络中其他流量抢占的连接以及实现服务质量 (QoS) 的功能。请记住，如果通过公共 Internet 连接到紧急服务的服务提供商，并且需要确保紧急呼叫的保密性，则需要 IPSec 加密。 
    
 **是您 E9-1-1 部署是否设计用于容灾？**
  
> 由于这是紧急解决方案，因此复原很重要。 部署您主要和辅助中介服务器和 SIP 中继灾难容错位置。 最好将主中介服务器支持，用户最接近部署和路由故障转移呼叫通过辅助中介服务器 （位于不同地理位置）。 
    
 **是否应该为每个分支机构部署单独的 SIP 中继？**
  
> Skype 业务服务器提供用于处理，包括为分支机构中的语音恢复能力的多个策略： 具有可恢复的数据网络、 部署在每个分支中，SIP 中继或推送呼叫到本地网关在中断期间。 有关详细信息，请参阅[Skype 业务服务器中的 SIP 中继](sip-trunking.md)。
    
 **是否已启用呼叫允许控制 (CAC)？**
  
> Skype 业务服务器句柄紧急呼叫任何不同于普通的呼叫。 因此，带宽管理或呼叫允许控制 (CAC) 将对 E9-1-1 配置产生负面影响。 如果已启用 CAC，并且路由紧急呼叫的链接上的流量超过配置的限制，那么将阻止紧急呼叫或将其路由至本地 PSTN 网关。 如本主题前面所述，此类呼叫不包含位置数据，必须手动将其路由到 ECRC。
    

