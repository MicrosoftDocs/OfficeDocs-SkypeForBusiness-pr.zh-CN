---
title: 呼叫许可控制部署 Skype for Business 服务器的最终清单
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
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: 用于在 Skype for Business Server 企业语音中部署呼叫许可控制（CAC）的最终清单。
ms.openlocfilehash: 5d5e4f6f40143bfec2a215e6bc9a54817d53da1b
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767225"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a>呼叫许可控制部署： Skype for business 服务器的最终清单
 
用于在 Skype for Business Server 企业语音中部署呼叫许可控制（CAC）的最终清单。 
  
使用以下检查表验证是否已完成部署呼叫允许控制 (CAC) 的所有必要配置任务。
  
- 如果部署了一个或多个边缘服务器，则每个外部接口 IP 地址都必须添加到网络配置设置中的子网列表中，位掩码为32。 还应该将此子网（IP 地址）与在其中部署 A/V 边缘服务的地理位置的网络站点 ID 关联。
    
    > [!NOTE]
    > 不需要边缘服务器实现 CAC。 
  
- 请确保启用了 CAC，如在[Skype For Business 服务器的 "启用呼叫许可控制](enable-call-admission-control.md)" 中所述。
    
- 确保已在所有中央站点启用 CAC。 这可以通过拓扑生成器完成。 如果发布时生成警告，请*不要*忽略它。
    
- 确保已在网络配置设置中配置在企业网络中管理的所有子网。 每个子网都必须与网络网站相关联，如在[Skype for business 中部署网络区域、网站和子网](deploy-network.md)中所述。
    
- 确保已在网络配置设置中配置所有前端服务器、Survivable Branch Appliance (SBA)、音频/视频会议服务器（如果位于单独的池中）和中介服务器的子网或 IP 地址。
    

