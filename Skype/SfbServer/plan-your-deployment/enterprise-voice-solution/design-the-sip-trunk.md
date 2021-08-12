---
title: 在 Skype for Business Server 中为 E9-1-1 设计 SIP 中继
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 为使用 SIP 中继提供商的 E9-1-1 部署规划 SIP 中继Skype for Business Server 企业语音。
ms.openlocfilehash: 5e669f8fc3149ac362e265a8e850e145f95c72567be99946fe0e37c0faa82130
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54283054"
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server"></a>在 Skype for Business Server 中为 E9-1-1 设计 SIP 中继
 
为使用 SIP 中继提供商的 E9-1-1 部署规划 SIP 中继Skype for Business Server 企业语音。
  
Skype for Business Server SIP 中继将紧急呼叫连接到 E9-1-1 服务提供商。 您可以为一个中央站点、多个中央站点或每个分支站点的 E9-1-1 设置紧急服务 SIP 中继。 但是，如果呼叫者的站点与承载紧急服务 SIP 中继的站点之间的 WAN 链路不可用，则断开的站点上的用户所拨打的呼叫将需要用户的语音策略中的特殊电话用法记录，该呼叫通过本地公用电话交换网 (PSTN) 网关将呼叫路由到 ECRC。 如果呼叫允许控制并发呼叫限制有效，则会出现相同情况。
  
有两种方法在安全环境中实现 SIP Skype for Business Server：
  
- 使用多主机中介服务器，这些服务器使用其面向外部的公共路由接口与 SIP 中继提供商进行通信。
    
- 使用 SBC (内部部署会话边界控制器) 中介服务器和 SIP 中继提供商的服务之间提供安全的分发点。
    
如果您选择后一种方法，请确保您选择的 SBC 品牌和型号已经过认证并且支持将状态信息数据格式位置对象 (PIDF-LO) 位置数据作为其 SIP INVITE 一部分传递。 否则，呼叫将在缺少位置信息的情况下到达紧急服务的服务提供商。 有关认证的 SDC 的详细信息，请参阅["适用于 Microsoft Lync](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)的基础结构"和"适用于 Skype for Business[的电话基础结构"。](../../../SfbPartnerCertification/certification/infra-gateways.md) 
  
E9-1-1 的服务提供商会向您提供对 SBC 对的访问权，以实现冗余。 您需要做出有关中介服务器拓扑和呼叫路由配置的多个决策。 您是否平等看待两个 SBC 并对它们之间的呼叫使用循环路由，或者您是否以其中一个 SBC 为主，而另一个为辅？
  
有关在服务器中部署 SIP 中继Skype for Business Server，请参阅 sip [trunking in Skype for Business Server](sip-trunking.md)。 下列问题将帮助您确定如何部署 E9-1-1 的 SIP 中继。
  
 **应该通过专门租用的 Internet 连接还是共享的 Internet 连接部署 SIP 中继？**
  
> 紧急呼叫必须始终保持连接状态，这一点很重要。专用线路将提供不会被网络中其他流量抢占的连接以及实现服务质量 (QoS) 的功能。请记住，如果通过公共 Internet 连接到紧急服务的服务提供商，并且需要确保紧急呼叫的保密性，则需要 IPSec 加密。 
    
 **E9-1-1 部署是否设计用于容限？**
  
> 由于这是紧急解决方案，因此复原很重要。 在容容位置部署主中介服务器和辅助中介服务器以及 SIP 中继。 建议将主要中介服务器部署在距离其支持的用户最近的位置，并通过位于不同地理位置的辅助中介服务器 (路由故障转移) 。 
    
 **是否应该为每个分支机构部署单独的 SIP 中继？**
  
> Skype for Business Server 提供了多个策略来处理分支机构中的语音恢复能力，包括：拥有可恢复的数据网络、在每个分支部署 SIP 中继或在中断期间将呼叫推送到本地网关。 有关详细信息，请参阅 sip [trunking in Skype for Business Server](sip-trunking.md)。
    
 **是否已启用呼叫允许控制 (CAC)？**
  
> Skype for Business Server处理紧急呼叫的方式与普通呼叫不同。 因此，带宽管理或呼叫允许控制 (CAC) 将对 E9-1-1 配置产生负面影响。 如果已启用 CAC，并且路由紧急呼叫的链接上的流量超过配置的限制，那么将阻止紧急呼叫或将其路由至本地 PSTN 网关。 如本主题前面所述，此类呼叫不包含位置数据，必须手动将其路由到 ECRC。
