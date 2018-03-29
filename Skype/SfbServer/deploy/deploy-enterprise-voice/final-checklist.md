---
title: 调用的业务服务器 2015 Skype 许可控制部署最终核对清单
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: 为部署业务服务器企业语音调用许可控制 (CAC) 在 Skype 的最后清单。
ms.openlocfilehash: 9971d59f0b9c3c2c1f9bfd5e8176122715b19d20
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 的呼叫允许控制部署：最终检查表
 
为部署业务服务器企业语音调用许可控制 (CAC) 在 Skype 的最后清单。 
  
使用以下检查表验证是否已完成部署呼叫允许控制 (CAC) 的所有必要配置任务。
  
- 如果部署一个或多个边缘服务器，则每个外部接口的 IP 地址必须添加到的子网列表中的网络配置设置，使用位掩码为 32。 还应该将此子网（IP 地址）与在其中部署 A/V 边缘服务的地理位置的网络站点 ID 关联。
    
    > [!NOTE]
    > 边缘服务器不需要实现 CAC。 
  
- 请确保启用 CAC，以指定在[启用呼叫许可控制下的业务服务器 2015年的 Skype](enable-call-admission-control.md)。
    
- 确保已在所有中央站点启用 CAC。 这可以通过拓扑生成器。 如果在发布时，将生成警告，*不能*忽略它。
    
- 确保已在网络配置设置中配置在企业网络中管理的所有子网。 也是必不可少的每个子网有关联到网络站点，[部署网络区域、 站点和子网业务 2015年的 Skype 在](deploy-network.md)中所述。
    
- 确保已在网络配置设置中配置所有前端服务器、Survivable Branch Appliance (SBA)、音频/视频会议服务器（如果位于单独的池中）和中介服务器的子网或 IP 地址。
    

