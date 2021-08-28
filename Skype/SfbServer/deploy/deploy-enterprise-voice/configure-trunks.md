---
title: 在服务器中配置Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 摘要：了解如何在中介服务器和对等方之间为企业语音配置中继Skype for Business Server。
ms.openlocfilehash: 0b3846a79d05d6b3eaea664f919dfbca61b036b7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617038"
---
# <a name="configure-trunks-in-skype-for-business-server"></a>在服务器中配置Skype for Business Server
 
**摘要：** 了解如何在中介服务器和对等方之间为企业语音配置中继Skype for Business Server。
  
作为 企业语音 部署的一部分，您可以在中介服务器与以下一个或多个对等方之间配置中继，为贵组织的 企业语音 客户端和设备提供公用电话交换网 (PSTN) 连接：
  
- 到 Internet 电话服务提供商 (ITSP) 的 SIP 中继连接
    
- PSTN 网关
    
- 专用交换机 (PBX)
    
有关详细信息，请参阅 Plan [for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)。
  
Skype for Business Server功能支持网关和中介服务器之间的多个关联。 这些关联通过定义中继来建立，中继是中介服务器池与公用电话交换网 (PSTN) 网关、会话边界控制器 (SBC) 或 IP-PBX 之间的逻辑关联。 使用拓扑生成器将网关与中介服务器 (，即中继) 。
  
- 若要在拓扑中分配Skype for Business Server，必须先在拓扑生成器中定义中继。 中继包含以下关联：中介服务器完全限定域名 (FQDN) 、中介服务器侦听端口、网关 FQDN 和网关侦听端口。
    
- 若要配置多个中继，可以在同一网关和中介服务器之间创建多个关联。 这为 pbX 基础结构提供了企业语音恢复能力，在专用交换机和 PBX (互操作) 特别有用。 
    
定义中继，必须将其与路由关联。 若要将中继与路由关联，您可以在拓扑生成器中为中继定义一个简单名称。 此简单名称在控制面板中用作中继Skype for Business Server，其中中继可以与路由关联。 简单中继名称用作命令行管理程序中的Skype for Business Server名称。 
  
```powershell
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

管理员必须选择与中介服务器关联的默认中继。 在拓扑生成器中，右键单击关联的中介服务器，然后单击"属性 **"。** 指定中介服务器的默认网关。 
  

