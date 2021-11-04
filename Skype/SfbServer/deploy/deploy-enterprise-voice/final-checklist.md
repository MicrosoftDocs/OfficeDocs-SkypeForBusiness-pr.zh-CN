---
title: 呼叫允许控制部署最终检查表Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: 在 CAC 中部署呼叫允许控制 (CAC) 的最终Skype for Business Server 企业语音。
ms.openlocfilehash: 11bf5a69b273f1311399090cc893bee1f4732443
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759074"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a>呼叫允许控制部署：呼叫允许控制Skype for Business Server
 
在 CAC 中部署呼叫允许控制 (CAC) 的最终Skype for Business Server 企业语音。 
  
使用以下检查表验证您是否已完成在 CAC 部署中部署呼叫允许控制 (配置) 。
  
- 如果已部署一台或多台边缘服务器，则必须将每个外部接口 IP 地址添加到网络配置设置中的子网列表，其中位掩码为 32。还应该将此子网（IP 地址）与在其中部署 A/V 边缘服务的地理位置的网络站点 ID 关联。
    
    > [!NOTE]
    > 边缘服务器不需要实现 CAC。 
  
- 确保启用 CAC，如启用呼叫允许控制中的[Skype for Business Server。](enable-call-admission-control.md)
    
- 确保已在所有中央站点启用 CAC。 这可以通过拓扑生成器完成。 如果在发布时生成警告，  *请不要忽略*  它。
    
- 确保已在网络配置设置中配置在企业网络中管理的所有子网。 还必须将每个子网与一个网络站点关联，如在部署网络区域、站点和子网中的[Skype for Business。](deploy-network.md)
    
- 确保已在网络配置设置中配置所有前端服务器、Survivable Branch Appliance (SBA)、音频/视频会议服务器（如果位于单独的池中）和中介服务器的子网或 IP 地址。
    

