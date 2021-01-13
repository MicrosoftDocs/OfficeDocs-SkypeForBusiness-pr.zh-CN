---
title: 在 Skype for Business Server 中部署呼叫允许控制
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 呼叫允许控制 (CAC) 是一种解决方案，可确定是否可以基于可用带宽建立实时会话，以帮助防止出现塞塞的网络上用户的差音频/视频质量。
ms.openlocfilehash: af08afe02b1dc138aa38ded654d567aed6a09247
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836882"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a>在 Skype for Business Server 中部署呼叫允许控制
 
呼叫允许控制 (CAC) 是一种解决方案，可确定是否可以基于可用带宽建立实时会话，以帮助防止出现塞塞的网络上用户的差音频/视频质量。 有关详细信息，请参阅规划 [Skype for Business Server 中的呼叫允许控制](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)。
  
### <a name="to-deploy-call-admission-control"></a>部署呼叫允许控制

1.  收集企业网络拓扑的所有所需信息，如示例所述：收集 Skype for Business Server 中呼叫 [允许控制的要求](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)。
    
2. 如果尚未定义，则必须定义网络区域与站点，并将子网与网络站点关联。 有关详细信息，请参阅在 Skype for Business 中部署网络区域 [、站点和子网](deploy-network.md)。
    
3. 创建带宽策略配置文件，如 [Skype for Business Server 中的"创建带宽策略配置文件"中详述](create-bandwidth-policy-profiles.md)
    
4. 创建网络区域链接，如 Skype for Business Server 中的"创建网络 [区域链接"中详述](create-network-region-links.md)。
    
5. 创建网络区域间路由，如 Skype for Business Server 中的"创建网络 [区域间路由"中详述](create-network-interregional-routes.md)。
    
6. 创建网络站点间策略，如 Skype for Business Server 中的"创建 [网络站点间策略"中详述](create-network-intersite-policies.md)。
    
7. 启用呼叫允许控制，如 Skype for Business Server 中的"启用呼叫 [允许控制"中详述](enable-call-admission-control.md)。
    
8. 检查一些最终设置，以确保一切设置正确。 有关详细信息，请参阅呼叫 [允许控制部署：Skype for Business Server 的最终清单](final-checklist.md)。
    

