---
title: 将试点池连接到旧边缘服务器
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 部署业务服务器 2019 Skype 之后，您需要配置联盟路由，为您的网站。 若要使用正在使用旧安装的联盟的路由，必须配置的业务服务器 2019 Skype 要使用该路由。
ms.openlocfilehash: 6766034cf54fd867c9b270324cb1db8ad2d644d5
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030565"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>将试点池连接到旧边缘服务器

部署业务服务器 2019 Skype 之后，您需要配置联盟路由，为您的网站。 若要使用正在使用旧安装的联盟的路由，必须配置的业务服务器 2019 Skype 要使用该路由。 
  
若要启用业务服务器 2019年网站 Skype，以使用控制器和边缘服务器的旧部署，请使用拓扑生成器来关联旧式边缘池。
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>使用拓扑生成器关联旧式边缘池

1. 打开拓扑生成器。 
    
2. 选择您的网站，即**Skype 业务 server**节点正下方。 
    
3. 在**操作**菜单中，单击**编辑属性**。
    
4. 在左窗格中，选择**联盟路由**。
    
5. 在**站点联盟路由分配**下选择**启用 SIP 联盟**，，然后选择上旧控制器或旧的边缘服务器，如果未不列出任何控制器。
  
6. 单击**确定**以关闭**编辑属性**页。 
    
7. 在拓扑生成器，业务服务器 2019年节点 Skype 导航到**Standard Edition server**或**Enterprise Edition 前端池**，右键单击池，，然后单击**编辑属性**。
    
8. 在**关联**下选择**关联边缘池 （用于媒体组件）** 旁边的复选框。 
    
9. 从列表中，选择旧边缘服务器。 
  
10. 单击**确定**以关闭**编辑属性**页。 
    
11. 在**拓扑生成器**中，选择顶层节点， **Skype 业务服务器**。
    
12. 从**操作**菜单中，单击**发布拓扑**，，然后单击**下一步**。
    
13. **发布向导**完成后，单击**完成**。
    

