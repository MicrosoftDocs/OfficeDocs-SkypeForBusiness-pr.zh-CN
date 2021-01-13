---
title: Skype for Business Server 中的 MN 中继
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
ms.assetid: dc4c5d66-297c-48a5-91b9-b9b8ce44a6e0
description: Skype for Business Server 企业语音支持中介服务器与 PSTN 网关、会话边界控制器和 IP-PBX 等组件之间的 M：N 中继。
ms.openlocfilehash: 9e51eb1a19904f45abdcab47af719a3ac14867bf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825482"
---
# <a name="mn-trunk-in-skype-for-business-server"></a>Skype for Business Server 中的 M：N 中继
 
Skype for Business Server 企业语音支持中介服务器与 PSTN 网关、会话边界控制器和 IP-PBX 等组件之间的 M：N 中继。
  
Skype for Business Server 支持在定义中继时更灵活地定义用于以前版本中的呼叫路由目的。 中继是中介服务器与侦听端口号与网关和侦听端口号之间的逻辑关联。 这意味着有几个方面：中介服务器可以有多个中继到同一网关;中介服务器可以有多个到不同网关的中继;相反，网关可以有多个中继到不同的中介服务器。
  
每当使用拓扑生成器向拓扑中添加网关时，仍必须创建根中继。 给定中介服务器可以处理的网关数取决于服务器在高峰忙碌时段的处理能力。 如果在超过 Skype for Business Server 最低硬件要求的硬件上部署中介服务器，如 Skype [for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)的服务器要求中所述，则独立中介服务器可以处理的活动非旁路呼叫的估计数量约为 1000 个呼叫。 在满足这些规范的硬件上部署时，中介服务器应执行代码转换，但仍为多个网关路由呼叫，即使网关不支持媒体旁路。
  
定义呼叫路由时，指定与该路由关联的中继，但不指定与该路由关联的中介服务器。 相反，使用拓扑生成器将中继与中介服务器关联。 换句话说，路由确定用于呼叫的中继，随后会向与该中继关联的中介服务器发送该呼叫的信号。
  
中介服务器可以部署为池;此池可以与前端池并排，也可以部署为独立池。 当中介服务器与前端池并排时，池大小最多为 12 (注册器池大小限制) 。 综合起来，这些新功能提高了中介服务器的可靠性和部署灵活性，但它们需要以下对等实体中的关联功能：
  
- **PSTN 网关。** Skype for Business Server 限定网关必须实现 DNS 负载平衡，这使合格的公用电话交换网 (PSTN) 网关能够充当一个中介服务器池的负载平衡器，从而在池中对呼叫进行负载平衡。
    
- **会话边界控制器。** 对于 SIP 中继，对等实体是 Internet 电话服务提供商 (SBC) 会话边界控制器。 在从中介服务器池到 SBC 的方向中，SBC 可以接收来自池中任何中介服务器的连接。 在从 SBC 到池的方向中，可以将流量发送到池中的任何中介服务器。 实现此目的的一个方法是通过 DNS 负载平衡（如果服务提供商和 SBC 支持）。 另一种选择是向服务提供商提供池中所有中介服务器的 IP 地址，服务提供商将在其 SBC 中将这些地址预配为每个中介服务器的单独 SIP 中继。 然后，服务提供商将处理其自己的服务器的负载平衡。 并非所有服务提供商或 SDC 都支持这些功能。 此外，服务提供商可能会为此功能收取额外的费用。 通常，每个到 SBC 的 SIP 中继都产生每月费用。
    
- **IP-PBX。** 在从中介服务器池到 IP-PBX SIP 终止的方向中，IP-PBX 可以接收来自池中任何中介服务器的连接。 在从 IP-PBX 到池的方向中，可以将流量发送到池中的任何中介服务器。 由于大多数IP-PBXs不支持 DNS 负载平衡，因此我们建议将各个直接 SIP 连接从 IP-PBX 定义到池中的每个中介服务器。 然后，IP-PBX 通过通过中继组分配流量来处理自己的负载平衡。 假定前提是中继组在 IP-PBX 上具有一组一致的路由规则。 特定 IP-PBX 是否支持此中继组概念及其如何与 IP-PBX 自己的冗余和群集体系结构相交，然后才能决定中介服务器群集是否可以与 IP-PBX 正确交互。
    
中介服务器池必须具有与之交互的对等网关的统一视图。 这意味着，池的所有成员都从配置存储访问对等网关的相同定义，并同样有可能针对传出呼叫与其进行交互。 因此，无法对池进行分段，以便某些中介服务器仅与传出呼叫的某些网关对等方进行通信。 如果需要这种分段，则必须使用单独的中介服务器池。 例如，如果不存在本主题前面详述的 PSTN 网关、SIP 中继或 IP-PBXs 与池交互的关联功能，则就是这种情况。
  
特定的 PSTN 网关、IP-PBX 或 SIP 中继对等方可以路由到多个中介服务器或中继。 中介服务器的特定池可以控制的网关数取决于使用媒体旁路的呼叫数。 如果大量呼叫使用媒体旁路，则池中的中介服务器可以处理更多的呼叫，因为只需要信号层处理。 
  

