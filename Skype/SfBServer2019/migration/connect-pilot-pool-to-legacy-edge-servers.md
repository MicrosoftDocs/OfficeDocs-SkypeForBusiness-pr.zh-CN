---
title: 将试点池连接到旧 Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 部署 Skype for Business Server 2019 后, 您需要为您的站点配置联盟路由。 为了使用旧版安装使用的联盟路由, 必须将 Skype for Business Server 2019 配置为使用此路由。
ms.openlocfilehash: 7a5a65e1488d5a119e3d11affbbaa9995a06626e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239222"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>将试点池连接到旧 Edge Server

部署 Skype for Business Server 2019 后, 您需要为您的站点配置联盟路由。 为了使用旧版安装使用的联盟路由, 必须将 Skype for Business Server 2019 配置为使用此路由。 
  
若要启用 Skype for Business Server 2019 网站使用旧版部署的 Director 和 Edge 服务器, 请使用拓扑生成器关联旧版 Edge 池。
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>使用拓扑生成器关联旧式边缘池

1. 打开拓扑生成器。 
    
2. 选择您的网站, 它位于**Skype For Business 服务器**节点正下方。 
    
3. 在 "**操作**" 菜单上, 单击 "**编辑属性**"。
    
4. 在左窗格中, 选择 "**联盟路由**"。
    
5. 在 "**站点联合路由分配**" 下, 选择 "**启用 SIP 联盟**", 然后选择旧式控制器, 如果未列出 Director, 则选择旧版边缘服务器。
  
6. 单击 **"确定"** 以关闭 "**编辑属性**" 页面。 
    
7. 在拓扑生成器中, 在 Skype for Business Server 2019 节点下, 导航到**标准版服务器**或**企业版前端池**, 右键单击该池, 然后单击 "**编辑属性**"。
    
8. 在 "**关联**" 下, 选中 "**关联边缘池" (对于媒体组件)** 旁边的复选框。 
    
9. 从列表中, 选择旧式边缘服务器。 
  
10. 单击 **"确定"** 以关闭 "**编辑属性**" 页面。 
    
11. 在**拓扑生成器**中, 选择最上面的节点 " **Skype For**business" 服务器。
    
12. 从 "**操作**" 菜单中, 单击 "**发布拓扑**", 然后单击 "**下一步**"。
    
13. **发布向导**完成后, 单击 "**完成**"。
    

