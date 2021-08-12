---
title: 部署呼叫允许控制Skype for Business Server
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
description: 呼叫允许控制 (CAC) 是一种解决方案，可确定是否可以基于可用带宽建立实时会话，以帮助防止出现塞塞的网络上用户的音频/视频质量差。
ms.openlocfilehash: eaba53e7c4c908024b3427970c103a3bcc8885036ca3e1dbc657e6c0d78e5d8e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307813"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a>部署呼叫允许控制Skype for Business Server
 
呼叫允许控制 (CAC) 是一种解决方案，可确定是否可以基于可用带宽建立实时会话，以帮助防止出现塞塞的网络上用户的音频/视频质量差。 有关详细信息，请参阅 Plan [for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)。
  
### <a name="to-deploy-call-admission-control"></a>部署呼叫允许控制

1.  收集企业网络拓扑的所有必需信息，如示例：在 Skype for Business Server 中收集呼叫允许[控制要求中所述](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)。
    
2. 如果尚未定义，则必须定义网络区域与站点，并将子网与网络站点关联。 有关详细信息，请参阅在部署[中部署网络区域、站点和Skype for Business。](deploy-network.md)
    
3. 创建带宽策略配置文件，如在[](create-bandwidth-policy-profiles.md)Skype for Business Server
    
4. 创建网络区域链接，如在 Skype for Business Server[创建网络区域链接中Skype for Business Server。](create-network-region-links.md)
    
5. 创建网络区域间路由，如在 Skype for Business Server[创建网络区域间路由中Skype for Business Server。](create-network-interregional-routes.md)
    
6. 创建网络站点间策略，如在 Skype for Business Server[创建网络站点间策略中Skype for Business Server。](create-network-intersite-policies.md)
    
7. 启用呼叫允许控制，如启用呼叫[允许](enable-call-admission-control.md)控制中的Skype for Business Server。
    
8. 检查一些最终设置，以确保一切设置正确。 有关详细信息，请参阅 Call [admission control deployment： final checklist for Skype for Business Server](final-checklist.md)。
    

