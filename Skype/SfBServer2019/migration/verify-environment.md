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
ms.localizationpriority: medium
description: 在以共存Skype for Business Server部署 2019 之前，需要验证旧版服务已配置并启动。 在部署 2019 试点池之前，必须确定旧环境中Skype for Business Server和功能。 在将 Microsoft Skype for Business Server 2019 XMPP 与旧版 XMPP 部署共存状态部署之前，需要验证旧版 XMPP 服务已配置和启动，并确定旧版 XMPP 配置所支持的联盟伙伴。
ms.openlocfilehash: 208b508eb6b2b5c62da51aa6317cde6e2a95bbb7
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727741"
---
# <a name="verify-the-legacy-environment"></a>验证旧环境

在以共存Skype for Business Server部署 2019 之前，需要验证旧版服务已配置并启动。 在部署 2019 试点池之前，必须确定旧环境中Skype for Business Server和功能。 在将 Microsoft Skype for Business Server 2019 XMPP 与旧版 XMPP 部署共存状态部署之前，需要验证旧版 XMPP 服务已配置并启动，并确定旧版 XMPP 配置所支持的联盟伙伴。 验证旧部署需要执行以下操作：
  
- 验证旧服务是否已启动
    
- 查看拓扑和用户
    
- 验证联盟和边缘服务器设置
    
- 验证 XMPP 服务和联盟伙伴
    
## <a name="verify-that-legacy-services-are-started"></a>验证旧版服务是否启动

1. 从旧版前端服务器中，导航到"管理工具"\"服务"小程序。
    
2. 确认以下服务正在前端服务器上运行：
    
     ![在前端服务器上运行的服务列表。](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a>在控制面板中查看Skype for Business Server拓扑

1. 使用具有 RTCUniversalServerAdmins 组成员身份或者 CsAdministrator 或 CsUserAdministrator 管理角色成员身份的帐户登录到前端服务器。
    
2. 打开"Skype for Business Server控制面板"。
    
3. 选择“拓扑”。 验证是否列出了旧版部署中的各种服务器。
    
     !["控制面板拓扑"页。](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a>在"控制面板"中Skype for Business Server旧用户

1. 打开"Skype for Business Server控制面板"。
    
2. 选择 **"用户**"，然后单击"查找 **"。**
    
3. 验证" **注册器池"** 列是否指向列出的每个用户的旧池。 
    
     ![列出用户的控制面板。](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a>验证旧边缘和联盟设置

1. 启动拓扑生成器。
    
2. 选择“从现有部署下载拓扑”。
    
3. 选择文件名，然后使用默认的 .tbxml 文件类型保存拓扑。
    
4. 展开"旧版安装"节点以显示部署中的各种服务器角色。
    
5. 选择站点节点并验证是否设置了 **站点联盟路由** 分配值。 
    
     ![拓扑生成器、站点联盟路由。](../media/migration_lyncserver_w14_federation.jpg)
  
6. 选择Standard Edition服务器或Enterprise Edition池。 确定是否已为"关联"下方的媒体配置 **边缘池**。 
    
     ![显示服务器和池的拓扑生成器。](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. 选择边缘池，并确定是否在"下一个跃点选择"下配置"下一 **个跃点池"。**
    
     ![拓扑生成器，下一个跃点选择。](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a>验证旧版 XMPP 联盟伙伴配置

1. 从旧的 XMPP 服务器导航到“管理工具\服务”小程序。
    
2. 确认已启动 Office Communications Server XMPP 网关服务。 
    
     ![OfficeCommunications Server XMPP 网关服务。](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

