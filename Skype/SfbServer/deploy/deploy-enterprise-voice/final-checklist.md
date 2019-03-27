---
title: 呼叫允许控制最终的部署清单 Skype 业务服务器
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
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: 业务 Server 企业语音部署呼叫允许控制 (CAC) Skype 中的最后一个清单。
ms.openlocfilehash: d0d61bcf6c6f0ab509eafa2b968bbb45c00b2a50
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878457"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a>呼叫允许控制部署： Skype 业务服务器的最终清单
 
业务 Server 企业语音部署呼叫允许控制 (CAC) Skype 中的最后一个清单。 
  
使用以下检查表验证是否已完成部署呼叫允许控制 (CAC) 的所有必要配置任务。
  
- 如果部署了一个或多个边缘服务器，每个外部接口 IP 地址必须为添加到子网列表中的网络配置设置，32 位掩码。 还应该将此子网（IP 地址）与在其中部署 A/V 边缘服务的地理位置的网络站点 ID 关联。
    
    > [!NOTE]
    > 边缘服务器无需实现 CAC。 
  
- 请确保已启用 CAC，为中指定的[Skype 业务服务器中的启用呼叫允许控制](enable-call-admission-control.md)。
    
- 确保已在所有中央站点启用 CAC。 这可以通过在拓扑生成器。 如果您发布时生成一条警告，则*不*忽略它。
    
- 确保已在网络配置设置中配置在企业网络中管理的所有子网。 也是必需的每个子网将关联到网络站点，如[部署网络区域、 站点和 Skype for Business 中的子网](deploy-network.md)中所述。
    
- 确保已在网络配置设置中配置所有前端服务器、Survivable Branch Appliance (SBA)、音频/视频会议服务器（如果位于单独的池中）和中介服务器的子网或 IP 地址。
    

