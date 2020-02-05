---
title: 在 Skype for Business 服务器中部署呼叫许可控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: 呼叫允许控制 (CAC) 是一种解决方案，它基于可用带宽确定是否可以建立实时会话，从而有助于防止在拥堵网络上为用户提供的音频/视频质量欠佳。
ms.openlocfilehash: 2e41d5a26e99c482041fb29e204f777a6c1a7cd7
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767665"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a>在 Skype for Business 服务器中部署呼叫许可控制
 
呼叫允许控制 (CAC) 是一种解决方案，它基于可用带宽确定是否可以建立实时会话，从而有助于防止在拥堵网络上为用户提供的音频/视频质量欠佳。 有关详细信息，请参阅[在 Skype For Business 服务器中计划呼叫许可控制](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)。
  
### <a name="to-deploy-call-admission-control"></a>部署呼叫允许控制

1.  为您的企业网络拓扑收集所有所需的信息，如示例所述[：在 Skype For Business 服务器中收集呼叫许可控制的要求](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)。
    
2. 如果还未这样做，就必须定义网络区域和站点，然后将子网与网络站点关联。 有关详细信息，请参阅[在 Skype For business 中部署网络区域、网站和子网](deploy-network.md)。
    
3. 创建带宽策略配置文件，详细信息请见在[Skype For Business Server 中创建带宽策略配置文件中](create-bandwidth-policy-profiles.md)的详细信息
    
4. 创建网络区域链接，详细信息请见在[Skype For Business 服务器中创建网络区域链接](create-network-region-links.md)中的详细信息。
    
5. 创建网络区域内路由，详细信息请见在[Skype For Business 服务器中创建网络 interregional 路由](create-network-interregional-routes.md)中的详细信息。
    
6. 创建网络站点间策略，详细信息请见在[Skype For Business 服务器中创建网络站点间策略](create-network-intersite-policies.md)。
    
7. 启用呼叫许可控制，如在[Skype For Business 服务器的 "启用呼叫许可控制](enable-call-admission-control.md)" 中详细介绍。
    
8. 检查几项最终设置，确保一切设置正确。 有关详细信息，请参阅[呼叫许可控制部署： Skype for Business 服务器的最终清单](final-checklist.md)。
    

