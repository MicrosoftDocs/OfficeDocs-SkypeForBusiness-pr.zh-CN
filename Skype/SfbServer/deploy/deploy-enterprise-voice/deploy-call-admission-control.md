---
title: 为业务 Server 部署中 Skype 的呼叫允许控制
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: 呼叫允许控制 (CAC) 是一种解决方案，它基于可用带宽确定是否可以建立实时会话，从而有助于防止在拥堵网络上为用户提供的音频/视频质量欠佳。
ms.openlocfilehash: 52fcedaab781e9ed76222afb32b56840a3b07c1c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223139"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a>为业务 Server 部署中 Skype 的呼叫允许控制
 
呼叫允许控制 (CAC) 是一种解决方案，它基于可用带宽确定是否可以建立实时会话，从而有助于防止在拥堵网络上为用户提供的音频/视频质量欠佳。 有关详细信息，请参阅[规划中的业务服务器 Skype 的呼叫允许控制](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)。
  
### <a name="to-deploy-call-admission-control"></a>部署呼叫允许控制

1.  收集有关您企业的网络拓扑，所需的信息的所有中所述[示例： 收集呼叫允许控制 Skype 中的业务服务器的要求](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)。
    
2. 如果还未这样做，就必须定义网络区域和站点，然后将子网与网络站点关联。 有关详细信息，请参阅[Deploy 网络区域、 站点和 Skype for Business 中的子网](deploy-network.md)。
    
3. 创建带宽策略配置文件，按[创建带宽策略配置文件中的业务服务器 Skype](create-bandwidth-policy-profiles.md)中所述
    
4. 创建网络区域链接，如[创建网络区域链接 Skype 业务服务器中的](create-network-region-links.md)所述。
    
5. 创建网络区域间路由，按[创建网络中的业务服务器 Skype 的 interregional 路由](create-network-interregional-routes.md)中所述。
    
6. 创建网络站点间策略，详见[Skype 业务服务器中的创建网络站点间策略](create-network-intersite-policies.md)。
    
7. 启用呼叫允许控制，如[启用呼叫允许控制业务服务器 Skype 中的](enable-call-admission-control.md)所述。
    
8. 检查几项最终设置，确保一切设置正确。 有关详细信息，请参阅[呼叫允许控制部署： 最终清单业务服务器 Skype](final-checklist.md)。
    

