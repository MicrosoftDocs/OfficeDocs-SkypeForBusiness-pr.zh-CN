---
title: 将试点池连接到旧 Edge Server
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 部署 Skype for Business Server 2019 后，需要为您的网站配置联盟路由。 若要使用旧版安装所使用的联盟路由，Skype for Business Server 2019 必须配置为使用此路由。
ms.openlocfilehash: 8243ebbf9540587dedd8e4ae3a51e22f9a315728
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753922"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>将试点池连接到旧 Edge Server

部署 Skype for Business Server 2019 后，需要为您的网站配置联盟路由。 若要使用旧版安装所使用的联盟路由，Skype for Business Server 2019 必须配置为使用此路由。 
  
若要启用 Skype for Business Server 2019 网站以使用旧版部署的控制器和边缘服务器，请使用拓扑生成器来关联旧版边缘池。
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>使用拓扑生成器关联旧边缘池

1. 打开拓扑生成器。 
    
2. 选择您的网站，它位于**Skype For Business Server**节点正下方。 
    
3. 在“操作”**** 菜单上，单击“编辑属性”****。
    
4. 在左侧窗格中，选择“联盟路由”****。
    
5. 在 "**站点联盟路由分配**" 下，选择 "**启用 SIP 联盟**"，然后选择旧版控制器或旧版边缘服务器（如果未列出控制器）。
  
6. 单击“确定”**** 关闭“编辑属性”**** 页。 
    
7. 在拓扑生成器中，在 Skype for Business Server 2019 节点下，导航到**Standard edition server**或**Enterprise Edition 前端池**，右键单击该池，然后单击 "**编辑属性**"。
    
8. 在“关联”**** 下，选中“关联边缘池(用于媒体组件)”**** 旁边的复选框。 
    
9. 从列表中选择旧的边缘服务器。 
  
10. 单击“确定”**** 关闭“编辑属性”**** 页。 
    
11. 在**拓扑生成器**中，选择最顶层节点（ **Skype for business Server**）。
    
12. 从“操作”**** 菜单中，单击“发布拓扑”****，然后单击“下一步”****。
    
13. “发布向导”**** 完成时，单击“完成”****。
    

