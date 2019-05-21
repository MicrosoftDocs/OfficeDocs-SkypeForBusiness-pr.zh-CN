---
title: 验证旧环境
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 在共存状态中部署 Skype for Business Server 2019 之前, 你需要验证是否已配置并启动旧式服务。 在部署 Skype for business Server 2019 试验池之前, 请务必确定旧版环境中存在的关键服务和功能。 在使用旧版 XMPP 部署部署 Microsoft Skype for Business Server 2019 XMPP 之前, 你需要验证旧的 XMPP 服务是否已配置并启动, 并确定旧版 XMPP 配置是哪个联盟伙伴证明.
ms.openlocfilehash: 9495c68085f3fc3495d4c2ced05be8b20039eb4e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280658"
---
# <a name="verify-the-legacy-environment"></a>验证旧环境

在共存状态中部署 Skype for Business Server 2019 之前, 你需要验证是否已配置并启动旧式服务。 在部署 Skype for business Server 2019 试验池之前, 请务必确定旧环境中存在的关键服务和功能。 在使用旧版 XMPP 部署在共存状态中部署 Microsoft Skype for Business Server 2019 XMPP 之前, 你需要验证是否已配置并启动旧版 XMPP 服务, 并确定旧 XMPP 的联盟合作伙伴配置支持。 验证旧部署需要执行以下操作:
  
- 验证是否已启动旧式服务
    
- 查看拓扑和用户
    
- 验证联盟和边缘服务器设置
    
- 验证 XMPP 服务和联盟合作伙伴
    
## <a name="verify-that-legacy-services-are-started"></a>验证是否已启动旧式服务

1. 从旧前端服务器, 导航到 "管理 Tools\Services" 小程序。
    
2. 验证以下服务是否在前端服务器上运行:
    
     ![前端服务器上运行的服务列表](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a>查看 Skype for Business Server 控制面板中的旧版拓扑

1. 使用具有 RTCUniversalServerAdmins 组成员身份或 CsAdministrator 或 CsUserAdministrator 管理角色成员身份的帐户登录到前端服务器。
    
2. 打开 "Skype for Business 服务器" 控制面板。
    
3. 选择 "**拓扑**"。 验证是否列出了旧版部署中的各种服务器。
    
     !["控制面板拓扑" 页面](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a>在 Skype for Business Server "控制面板" 中查看旧版用户

1. 打开 "Skype for Business 服务器" 控制面板。
    
2. 选择 "**用户**", 然后单击 "**查找**"。
    
3. 验证 "**注册机构池**" 列是否指向列出的每个用户的旧版池。 
    
     !["控制面板", 其中列出了用户](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a>验证旧版边缘和联盟设置

1. 启动拓扑生成器。
    
2. **从现有部署中选择 "下载拓扑**"。
    
3. 选择文件名, 然后使用默认的 tbxml 文件类型保存拓扑。
    
4. 展开 "旧版安装" 节点以显示部署中的各种服务器角色。
    
5. 选择 "网站" 节点并验证是否设置了 "**网站联合" 路由分配**值。 
    
     ![拓扑生成器、站点联合身份验证路线](../media/migration_lyncserver_w14_federation.jpg)
  
6. 选择标准版服务器或企业版前端池。 确定是否已针对 "**关联**" 下的媒体配置了边缘池。 
    
     ![拓扑生成器, 显示服务器和池](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. 选择 "边缘" 池并确定下一个跃点池是否在**下一个跃点选择**下配置。
    
     ![拓扑生成器, 下一跃点选择](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a>验证旧版 XMPP 联盟合作伙伴配置

1. 从旧的 XMPP 服务器中, 导航到 "管理 Tools\Services" 小程序。
    
2. 验证是否已启动 Office 通信服务器 XMPP 网关服务。 
    
     ![Office 通信服务器 XMPP 网关服务](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

