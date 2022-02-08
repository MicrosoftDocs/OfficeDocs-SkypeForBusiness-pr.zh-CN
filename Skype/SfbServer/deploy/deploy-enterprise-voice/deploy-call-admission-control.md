---
title: 部署呼叫允许控制Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: 呼叫允许控制 (CAC) 是一种解决方案，可确定是否可以基于可用带宽建立实时会话，以帮助防止出现塞塞的网络上用户的音频/视频质量差。
ms.openlocfilehash: 395d40caaf9db491bffad0723cab0142238bd32a
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385300"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a>部署呼叫允许控制Skype for Business Server
 
呼叫允许控制 (CAC) 是一种解决方案，可确定是否可以基于可用带宽建立实时会话，以帮助防止出现塞塞的网络上用户的音频/视频质量差。 有关详细信息，请参阅 Plan [for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)。
  
### <a name="to-deploy-call-admission-control"></a>部署呼叫允许控制

1.  收集企业网络拓扑的所有必需信息，如示例：收集呼叫允许控制在 Skype for Business Server [中Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)。
    
2. 如果尚未定义，则必须定义网络区域与站点，并将子网与网络站点关联。 有关详细信息，请参阅部署网络[区域、站点和](deploy-network.md) Skype for Business。
    
3. 创建带宽策略配置文件，如在 Skype for Business Server [](create-bandwidth-policy-profiles.md)
    
4. 创建网络区域链接，如在 Skype for Business Server [创建网络区域链接中Skype for Business Server](create-network-region-links.md)。
    
5. 创建网络区域间路由，如在 Skype for Business Server [创建网络区域间路由中Skype for Business Server](create-network-interregional-routes.md)。
    
6. 创建网络站点间策略，如在 Skype for Business Server [创建网络站点间策略中Skype for Business Server](create-network-intersite-policies.md)。
    
7. 启用呼叫允许控制，如启用[呼叫允许](enable-call-admission-control.md)控制中的Skype for Business Server。
    
8. 检查一些最终设置，以确保一切设置正确。 有关详细信息，请参阅呼叫[允许控制部署：Skype for Business Server](final-checklist.md)。
    

