---
title: 在 Skype for Business Server 2015 中部署呼叫允许控制
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: 呼叫允许控制 (CAC) 是一种解决方案，它基于可用带宽确定是否可以建立实时会话，从而有助于防止在拥堵网络上为用户提供的音频/视频质量欠佳。 有关详细信息，请参阅计划在 Skype 呼叫许可控制业务服务器 2015年。
ms.openlocfilehash: 0302663546a099e682b5dc405625d4519fe998d9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-call-admission-control-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中部署呼叫允许控制
 
呼叫允许控制 (CAC) 是一种解决方案，它基于可用带宽确定是否可以建立实时会话，从而有助于防止在拥堵网络上为用户提供的音频/视频质量欠佳。 有关详细信息，请参阅[规划中业务服务器 2015年的 Skype 通话许可控制](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)。
  
### <a name="to-deploy-call-admission-control"></a>部署呼叫允许控制

1.  收集所有您的企业网络拓扑所需的信息，如中所述[示例： 收集业务服务器 2015年在 Skype 呼叫许可控制要求](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)。
    
2. 如果还未这样做，就必须定义网络区域和站点，然后将子网与网络站点关联。 有关详细信息，请参阅[部署网络区域、 站点和子网中为业务 2015 Skype](deploy-network.md)。
    
3. 创建策略的配置文件，如[业务服务器 2015年的 Skype 在创建带宽策略配置文件](create-bandwidth-policy-profiles.md)中所述的带宽
    
4. 创建网络区域链接，如所述[创建中业务服务器 2015年的 Skype 的网络区域链接](create-network-region-links.md)。
    
5. 创建网络间区域路由，如所述[业务服务器 2015年的 Skype 在创建 interregional 的网络路由](create-network-interregional-routes.md)。
    
6. 创建网络站点间的策略，如所述[业务服务器 2015年的 Skype 在创建站点间的网络策略](create-network-intersite-policies.md)。
    
7. 启用呼叫许可控制，如所述[业务服务器 2015年的 Skype 在启用呼叫许可控制](enable-call-admission-control.md)。
    
8. 检查几项最终设置，确保一切设置正确。 有关详细信息，请参阅[调用许可控制部署： 业务服务器 2015年的 Skype 的最终清单](final-checklist.md)。
    

