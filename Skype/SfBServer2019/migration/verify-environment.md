---
title: 验证旧环境
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
description: 在将 Skype for Business Server 2019 部署到共存状态之前，您需要验证是否已配置并启动旧版服务。 在部署 Skype for Business Server 2019 试点池之前，请务必确定旧环境中存在的关键服务和功能。 在使用旧版 XMPP 部署在共存状态中部署 Microsoft Skype for Business Server 2019 XMPP 之前，您需要验证是否已配置并启动旧的 XMPP 服务，并确定旧版 XMPP 配置支持的联盟伙伴。
ms.openlocfilehash: 2600cc2e6f4fac258431bcf505af10d1f8c212fe
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751674"
---
# <a name="verify-the-legacy-environment"></a>验证旧环境

在将 Skype for Business Server 2019 部署到共存状态之前，您需要验证是否已配置并启动旧版服务。 在部署 Skype for business Server 2019 试点池之前，请务必确定旧环境中存在的关键服务和功能。 在将 Microsoft Skype for Business Server 2019 XMPP 部署到旧版 XMPP 部署的共存状态之前，您需要验证是否已配置并启动旧的 XMPP 服务，并确定旧版 XMPP 配置支持的联盟伙伴。 验证您的旧部署需要执行以下操作：
  
- 验证是否已启动旧版服务
    
- 查看拓扑和用户
    
- 验证联盟和边缘服务器设置
    
- 验证 XMPP 服务和联盟伙伴
    
## <a name="verify-that-legacy-services-are-started"></a>验证是否已启动旧版服务

1. 在旧版前端服务器中，导航到 "管理" Tools\Services 小程序。
    
2. 确认以下服务正在前端服务器上运行：
    
     ![前端服务器上运行的服务的列表](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a>查看 Skype for Business Server 控制面板中的旧版拓扑

1. 使用具有 RTCUniversalServerAdmins 组成员身份或者 CsAdministrator 或 CsUserAdministrator 管理角色成员身份的帐户登录到前端服务器。
    
2. 打开 "Skype for Business Server 控制面板"。
    
3. 选择“拓扑”****。 验证是否列出了旧版部署中的各个服务器。
    
     !["控制面板拓扑" 页面](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a>查看 Skype for Business Server 控制面板中的旧版用户

1. 打开 "Skype for Business Server 控制面板"。
    
2. 选择 "**用户**"，然后单击 "**查找**"。
    
3. 验证 "**注册器池**" 列是否指向列出的每个用户的旧版池。 
    
     ![控制面板列出用户](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a>验证旧版边缘和联盟设置

1. 启动拓扑生成器。
    
2. 选择“从现有部署下载拓扑”****。
    
3. 选择一个文件名，并使用默认的 tbxml 文件类型保存该拓扑。
    
4. 展开 "旧版安装" 节点，以显示部署中的各种服务器角色。
    
5. 选择 "站点" 节点并验证是否设置了 "**站点联盟路由分配**" 值。 
    
     ![拓扑生成器、站点联合路由](../media/migration_lyncserver_w14_federation.jpg)
  
6. 选择 Standard Edition Server 或 Enterprise Edition 前端池。 确定是否已为低于资源的**关联**配置了边缘池。 
    
     ![显示服务器和池的拓扑生成器](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. 选择边缘池并确定下一个跃点池是否在**下一个跃点选择**下配置。
    
     ![拓扑生成器，下一个跃点选择](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a>验证旧版 XMPP 联盟伙伴配置

1. 从旧的 XMPP 服务器导航到“管理工具\服务”小程序。
    
2. 确认已启动 Office Communications Server XMPP 网关服务。 
    
     ![Office 通信服务器 XMPP 网关服务](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

