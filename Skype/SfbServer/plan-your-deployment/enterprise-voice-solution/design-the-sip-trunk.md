---
title: 在 Skype for Business Server 2015 中为 E9-1-1 设计 SIP 中继
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
description: 规划中业务服务器企业语音的 Skype 使用 SIP 中继提供商、 E9-1-1 部署您的 SIP 中继拓扑。
ms.openlocfilehash: 588cd32d4c3c7f7aacc9a42d2a2ca8791d036dea
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中为 E9-1-1 设计 SIP 中继
 
规划中业务服务器企业语音的 Skype 使用 SIP 中继提供商、 E9-1-1 部署您的 SIP 中继拓扑。
  
Skype 业务服务器使用 SIP 中继连接到 E9-1-1 的服务提供商紧急呼叫。 您可以为一个中央站点、多个中央站点或每个分支站点的 E9-1-1 设置紧急服务 SIP 中继。 但是，如果调用方的网站与网站之间承载的 WAN 链路紧急服务 SIP 中继是不可用，则调用放在断开连接的站点的用户将需要特殊的电话使用情况记录用户的语音策略中将路由到该调用通过本地公用交换的电话网络 (PSTN) 网关 ECRC。 如果呼叫允许控制并发呼叫限制有效，则会出现相同情况。
  
有两种方法可以在 Skype 业务服务器环境中实现 SIP 中继：
  
- 使用多宿主使用公开传送其面向外部的接口与通信的 SIP 中继提供的中介服务器。
    
- 使用内部会话边框控制器 (SBC) 提供商服务的中介服务器和 SIP 中继之间安全的分界点。
    
如果您选择后一种方法，请确保您选择的 SBC 品牌和型号已经过认证并且支持将状态信息数据格式位置对象 (PIDF-LO) 位置数据作为其 SIP INVITE 一部分传递。 否则，呼叫将在缺少位置信息的情况下到达紧急服务的服务提供商。 经认证的 SBCs 有关详细信息，请参阅["基础架构限定为 Microsoft Lync"](https://go.microsoft.com/fwlink/p/?LinkId=248425)和["电话基础架构的 Skype 的业务"](https://technet.microsoft.com/en-us/office/dn947483)。
  
E9-1-1 的服务提供商会向您提供对 SBC 对的访问权，以实现冗余。 您需要做出几个有关中介服务器拓扑结构和调用路由配置。 您是否平等看待两个 SBC 并对它们之间的呼叫使用循环路由，或者您是否以其中一个 SBC 为主，而另一个为辅？
  
有关部署 Skype 在 SIP 中继业务服务器的详细信息，请参阅[SIP 中继业务服务器 2015年的 Skype 中](sip-trunking.md)。 下列问题将帮助您确定如何部署 E9-1-1 的 SIP 中继。
  
 **应该通过专门租用的 Internet 连接还是共享的 Internet 连接部署 SIP 中继？**
  
> 紧急呼叫必须始终保持连接状态，这一点很重要。专用线路将提供不会被网络中其他流量抢占的连接以及实现服务质量 (QoS) 的功能。请记住，如果通过公共 Internet 连接到紧急服务的服务提供商，并且需要确保紧急呼叫的保密性，则需要 IPSec 加密。 
    
 **E9-1-1 部署专为灾难容受能力？**
  
> 由于这是紧急解决方案，因此复原很重要。 部署您主要和次要中介服务器和 SIP 中继灾难容错位置中。 最好将最接近用户的支持，主要中介服务器部署，通过辅助中介服务器 （位于不同的地理位置） 调用路由故障转移。 
    
 **是否应该为每个分支机构部署单独的 SIP 中继？**
  
> Skype 业务服务器提供几种策略，用于处理语音留存能力在分支机构，其中包括： 具有弹性数据网络、 部署在每个分支中，SIP 中继或推出电话本地网关在停机期间。 有关详细信息，请参阅[SIP 中继业务服务器 2015年的 Skype 中](sip-trunking.md)。
    
 **是否已启用呼叫允许控制 (CAC)？**
  
> Skype 业务服务器处理紧急调用任何不同于普通的电话。 因此，带宽管理或呼叫允许控制 (CAC) 将对 E9-1-1 配置产生负面影响。 如果已启用 CAC，并且路由紧急呼叫的链接上的流量超过配置的限制，那么将阻止紧急呼叫或将其路由至本地 PSTN 网关。 如本主题前面所述，此类呼叫不包含位置数据，必须手动将其路由到 ECRC。
    

