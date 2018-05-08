---
title: 在 Skype for Business Server 2015 中配置中继
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 摘要： 了解如何在 Skype for Business Server 2015 配置中介服务器与企业语音的对等方之间的中继。
ms.openlocfilehash: 4944cac2b06d837facf0cf014fb3a4fd32343305
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="configure-trunks-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中配置中继
 
**摘要：**了解如何在 Skype for Business Server 2015 配置中介服务器与企业语音的对等方之间的中继。
  
作为企业语音部署的一部分，您可以配置中介服务器和一个或多个您的组织中的企业语音客户端和设备提供公用电话交换网 (pstn) 连接的以下的对等方之间中继：
  
- 到 Internet 电话服务提供商 (ITSP) 的 SIP 中继连接
    
- PSTN 网关
    
- 专用交换机 (PBX)
    
有关详细信息，请参阅[规划中的业务服务器 2015 Skype 的 PSTN 连接](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)。
  
业务服务器功能的 Skype 支持多个网关和中介服务器之间的关联。 通过定义是中介服务器池和公用电话交换网 (pstn) 网关，会话边界控制器 (SBC) 或 IP PBX 之间的逻辑关联 a trunk 进行这些关联。 使用拓扑生成器将网关与中介服务器 （即，中继） 相关联。
  
- 若要分配或删除业务服务器在 Skype 中继，必须首先在拓扑生成器中定义中继。 中继包含的以下关联： 中介服务器的完全限定域名 (FQDN)、 中介服务器侦听端口、 网关 FQDN，和网关侦听端口。
    
- 若要配置多个中继，可以创建多个同一个网关和中介服务器之间的关联。 这将提供企业语音基础结构，即在专用交换机 (pbx) interoperational 方案中尤其有用的其他恢复能力。 
    
定义中继，必须将其与路由关联。 若要将路由到中继相关联，请拓扑生成器中定义中继的简单名称。 此简单名称用作中继可以路由相关联的业务 Server Control Panel 中 Skype 的中继名称。 简单 trunk 名称用作业务 Server 命令行管理程序 Skype 的网关名称。 
  
```
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

管理员必须选择默认中继与中介服务器关联。 从拓扑生成器中，右键单击关联的中介服务器，然后单击**属性**。 为中介服务器指定默认网关。 
  

