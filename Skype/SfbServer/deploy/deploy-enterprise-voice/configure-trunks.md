---
title: 在 Skype for Business Server 2015 中配置中继
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 摘要： 了解如何在 Skype 为业务服务器 2015年配置中介服务器和企业语音的对等方之间中继。
ms.openlocfilehash: a2630d3e37e6ab15a0e88593549e9365ac69a3e7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-trunks-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中配置中继
 
**摘要：**了解如何在 Skype 为业务服务器 2015年配置中介服务器和企业语音的对等方之间中继。
  
作为企业语音部署的一部分，您可以配置中继间中介服务器和一个或多个以下等为企业语音客户端和设备在您的组织提供公用交换的电话网络 (PSTN) 连接：
  
- 到 Internet 电话服务提供商 (ITSP) 的 SIP 中继连接
    
- PSTN 网关
    
- 专用交换机 (PBX)
    
有关详细信息，请参阅[规划业务服务器 2015年的 Skype 在 PSTN 连接](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)。
  
Skype 的业务服务器功能，支持多个网关之间的中介服务器关联。 这些关联进行定义的主干，是中介服务器池和公用交换的电话网络 (PSTN) 网关，会话边框控制器 (SBC) 或 IP PBX 之间的逻辑关联。 使用拓扑生成器将网关与中介服务器 （即，中继） 相关联。
  
- 要分配或删除业务服务器中 Skype 干线，您必须首先定义拓扑生成器中的主干。 干线包括以下关联： 中介服务器的完全合格的域名称 (FQDN)、 中介服务器侦听端口、 FQDN，网关和网关监听端口。
    
- 若要配置多个中继，可以创建多个相同的网关和中介服务器之间的关联。 这提供了额外弹性企业语音基础结构，这是在 interoperational 方案的专用分组交换机 (PBX) 中尤其有用。 
    
定义中继，必须将其与路由关联。 要关联到工艺路线干线，定义拓扑生成器主干的简单名称。 这个简单的名称用作业务服务器控件面板，中继可以与工艺路线相关联在 Skype 的干线名称。 简单的干线名称用作业务服务器管理外壳从 Skype 的网关名称。 
  
```
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

管理员必须选择默认中继与中介服务器相关联。 从拓扑生成器中，关联的中介服务器中，用鼠标右键单击，然后单击**属性**。 中介服务器指定的默认网关。 
  

