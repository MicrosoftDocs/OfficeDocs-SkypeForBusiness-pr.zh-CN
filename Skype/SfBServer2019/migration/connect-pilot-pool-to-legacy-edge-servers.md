---
title: 将试点池连接到旧的边缘服务器
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 在部署 Skype for Business Server 2019 后，您需要为站点配置联盟路由。 为了使用旧安装所使用的联盟路由，必须将 Skype for Business Server 2019 配置为使用此路由。
ms.openlocfilehash: a5f5da34300d993f59d4de5e2eb0b47cc58eff0e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58607459"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>将试点池连接到旧的边缘服务器

在部署 Skype for Business Server 2019 后，您需要为站点配置联盟路由。 为了使用旧安装所使用的联盟路由，必须将 Skype for Business Server 2019 配置为使用此路由。 
  
若要使 Skype for Business Server 2019 站点能够使用旧版部署的控制器和边缘服务器，请使用拓扑生成器关联旧边缘池。
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>使用拓扑生成器关联旧边缘池

1. 打开拓扑生成器。 
    
2. 选择网站，它位于"网站"节点 **Skype for Business Server** 下方。 
    
3. 在“操作”菜单上，单击“编辑属性”。
    
4. 在左侧窗格中，选择“联盟路由”。
    
5. 在 **"站点联盟路由分配"** 下，选择" **启用 SIP** 联盟"，然后选择旧控制器或旧边缘服务器（如果未列出控制器）。
  
6. 单击“确定”关闭“编辑属性”页。 
    
7. 在拓扑生成器的"Skype for Business Server 2019"节点下，导航到 **Standard Edition 服务器** 或 Enterprise Edition **前端池**，右键单击该池，然后单击"编辑属性 **"。**
    
8. 在“关联”下，选中“关联边缘池(用于媒体组件)”旁边的复选框。 
    
9. 从列表中选择旧的边缘服务器。 
  
10. 单击“确定”关闭“编辑属性”页。 
    
11. 在 **拓扑生成器中**，选择最顶层节点，Skype for Business Server。 
    
12. 从“操作”菜单中，单击“发布拓扑”，然后单击“下一步”。
    
13. “发布向导”完成时，单击“完成”。
    

