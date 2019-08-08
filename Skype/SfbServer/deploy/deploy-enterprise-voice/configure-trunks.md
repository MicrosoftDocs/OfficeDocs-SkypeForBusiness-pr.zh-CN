---
title: 在 Skype for Business 服务器中配置中继
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: '摘要: 了解如何在 Skype for Business 服务器中配置用于企业语音的中介服务器和对等之间的主干。'
ms.openlocfilehash: 714c712816709e8f2211e752f87d20c8d2067c7b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233655"
---
# <a name="configure-trunks-in-skype-for-business-server"></a>在 Skype for Business 服务器中配置中继
 
**摘要:** 了解如何在 Skype for Business 服务器中配置用于企业语音的中介服务器和对等之间的主干。
  
作为企业语音部署的一部分, 您可以在中介服务器和一个或多个以下对等方之间配置主干, 以便为企业语音客户端和组织中的设备提供公共交换电话网络 (PSTN) 连接:
  
- 到 Internet 电话服务提供商 (ITSP) 的 SIP 中继连接
    
- PSTN 网关
    
- 专用交换机 (PBX)
    
有关更多详细信息, 请参阅[在 Skype For Business 服务器中规划 PSTN 连接](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)。
  
Skype for Business 服务器功能支持网关和中介服务器之间的多个关联。 这些关联通过定义主干 (这是中介服务器池和公共交换电话网络 (PSTN) 网关、会话边界控制器 (SBC) 或 ip-pbx) 之间的逻辑关联来进行。 使用拓扑生成器将网关与中介服务器相关联 (即中继)。
  
- 若要在 Skype for Business 服务器中分配或删除主干, 必须首先在拓扑生成器中定义一个主干。 主干包含以下关联: 中介服务器完全限定的域名 (FQDN)、中介服务器侦听端口、网关 FQDN 和网关侦听端口。
    
- 若要配置多个中继, 可以在同一网关和中介服务器之间创建多个关联。 这将为企业语音基础结构提供额外的复原, 这在专用分支 exchange (PBX) interoperational 方案中尤其有用。 
    
定义中继，必须将其与路由关联。 若要将主干关联到路由, 请为拓扑生成器中的主干定义一个简单名称。 此简单名称用作 Skype for Business Server 控制面板中的主干名称, 其中中继可以与路线相关联。 简单主干名称用作 Skype for Business Server Management Shell 中的网关名称。 
  
```
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

管理员必须选择与中介服务器关联的默认中继。 从拓扑生成器中, 右键单击关联的中介服务器, 然后单击 "**属性**"。 指定中介服务器的默认网关。 
  

