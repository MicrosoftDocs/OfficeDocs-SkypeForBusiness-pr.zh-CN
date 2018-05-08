---
title: 在 Skype for Business Server 2015 中部署呼叫允许控制
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: 呼叫允许控制 (CAC) 是一种解决方案，它基于可用带宽确定是否可以建立实时会话，从而有助于防止在拥堵网络上为用户提供的音频/视频质量欠佳。 有关详细信息，请参阅 Plan for Skype 中的呼叫允许控制的业务服务器 2015年。
ms.openlocfilehash: 471bc7abe8a79f2ef4b4cc322450dbc7c639129f
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="deploy-call-admission-control-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中部署呼叫允许控制
 
呼叫允许控制 (CAC) 是一种解决方案，它基于可用带宽确定是否可以建立实时会话，从而有助于防止在拥堵网络上为用户提供的音频/视频质量欠佳。 有关详细信息，请参阅[规划中的业务服务器 2015 Skype 的呼叫允许控制](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)。
  
### <a name="to-deploy-call-admission-control"></a>部署呼叫允许控制

1.  收集有关您企业的网络拓扑，所需的信息的所有中所述[示例： 收集业务服务器 2015 Skype 中的呼叫允许控制的要求](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)。
    
2. 如果还未这样做，就必须定义网络区域和站点，然后将子网与网络站点关联。 有关详细信息，请参阅[Deploy 网络区域、 网站和业务 2015年的 Skype 中的子网](deploy-network.md)。
    
3. 创建带宽策略配置文件，按[创建带宽策略配置文件中的业务服务器 2015 Skype](create-bandwidth-policy-profiles.md)中所述
    
4. 创建网络区域链接，按[创建网络区域链接中的业务服务器 2015 Skype](create-network-region-links.md)中所述。
    
5. 创建网络区域间路由，按[创建网络中的业务服务器 2015 Skype 的 interregional 路由](create-network-interregional-routes.md)中所述。
    
6. 创建网络站点间策略，按[创建网络站点间策略中的业务服务器 2015 Skype](create-network-intersite-policies.md)中所述。
    
7. 启用呼叫允许控制，如[启用呼叫允许控制业务服务器 2015年的 Skype 中](enable-call-admission-control.md)所述。
    
8. 检查几项最终设置，确保一切设置正确。 有关详细信息，请参阅[呼叫允许控制部署： 最终清单业务服务器 2015年的 Skype](final-checklist.md)。
    

