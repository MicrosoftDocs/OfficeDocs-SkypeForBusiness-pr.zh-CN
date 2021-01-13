---
title: Skype for Business Server 的呼叫允许控制部署最终清单
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
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: 在 Skype for Business Server (CAC) 部署呼叫允许控制的最终企业语音。
ms.openlocfilehash: d3a6484e35225627c8f22002823eff7fd5939694
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830832"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a>呼叫允许控制部署：Skype for Business Server 的最终清单
 
在 Skype for Business Server (CAC) 部署呼叫允许控制的最终企业语音。 
  
使用以下检查表验证您是否已完成所有必要的配置任务，以将呼叫允许控制部署到 CAC (CAC) 。
  
- 如果已部署一台或多台边缘服务器，则必须将每个外部接口 IP 地址添加到网络配置设置中的子网列表，其中位掩码为 32。还应该将此子网（IP 地址）与在其中部署 A/V 边缘服务的地理位置的网络站点 ID 关联。
    
    > [!NOTE]
    > 边缘服务器不需要实现 CAC。 
  
- 确保启用 CAC，如 Skype for Business Server 中的"启用呼叫 [允许控制"中指定](enable-call-admission-control.md)。
    
- 确保已在所有中央站点启用 CAC。 这可以通过拓扑生成器完成。 如果在发布时生成警告，  *请不要*  忽略它。
    
- 确保已在网络配置设置中配置在企业网络中管理的所有子网。 还必须将每个子网与网络站点关联，如在 Skype for Business 中部署网络区域、站点和子网 [所介绍](deploy-network.md)。
    
- 确保已在网络配置设置中配置所有前端服务器、Survivable Branch Appliance (SBA)、音频/视频会议服务器（如果位于单独的池中）和中介服务器的子网或 IP 地址。
    

