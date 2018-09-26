---
title: 确认旧环境
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 部署以共存的业务服务器 2019 Skype 之前, 需要确认已配置并启动旧式服务。 务必来确定关键服务和在旧环境中，在部署业务服务器 2019年试点池 Skype 之前存在的功能。 在之前部署 Microsoft Skype 业务服务器 2019 XMPP 与旧的 XMPP 部署以共存，您需要验证旧版 XMPP 服务已配置并启动，并确认旧的 XMPP 配置的联盟的伙伴支持。
ms.openlocfilehash: d6e4585e127009117345d1220458196b5b461b6a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030425"
---
# <a name="verify-the-legacy-environment"></a>确认旧环境

部署以共存的业务服务器 2019 Skype 之前, 需要确认已配置并启动旧式服务。 务必来确定关键服务和部署业务服务器 2019年试点池 Skype 之前旧环境中存在的功能。 在之前部署 Microsoft Skype 业务服务器 2019 XMPP 与旧的 XMPP 部署以共存，您需要验证已将旧的 XMPP 服务配置并启动，并确定该联盟伙伴的旧的 XMPP配置为支持。 验证旧版部署涉及以下：
  
- 验证已启动旧的服务
    
- 查看拓扑和用户
    
- 验证联盟和边缘服务器设置
    
- 确认 XMPP 服务和联盟的伙伴
    
## <a name="verify-that-legacy-services-are-started"></a>确认旧服务已启动

1. 从旧前端服务器，导航到管理工具 \ 服务小程序。
    
2. 确认以下服务都在前端服务器上运行：
    
     ![前端服务器上运行的服务列表](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a>为业务 Server Control Panel 查看 Skype 中的将旧拓扑

1. 使用具有 RTCUniversalServerAdmins 组成员身份或 CsAdministrator 或 CsUserAdministrator 管理角色成员身份的帐户登录到前端服务器。
    
2. 打开 Skype 业务 Server Control Panel。
    
3. 选择**拓扑**。 确认列出旧部署中的各个服务器。
    
     ![控件控制面板拓扑页](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a>查看旧用户中的业务 Server Control Panel Skype

1. 打开 Skype 业务 Server Control Panel。
    
2. 选择**用户**，然后单击**查找**。
    
3. 确认**注册器池**列指向旧池列出的每个用户。 
    
     ![列出用户控制面板](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a>确认旧的边缘服务器和联合身份验证设置

1. 启动拓扑生成器。
    
2. 选择**从现有部署下载拓扑**。
    
3. 选择文件名并保存具有默认.tbxml 文件类型的拓扑。
    
4. 展开以显示部署中的各个服务器角色的旧式安装节点。
    
5. 选择网站节点并验证设置了**站点联盟路由分配**值。 
    
     ![拓扑生成器，站点联盟路由](../media/migration_lyncserver_w14_federation.jpg)
  
6. 选择 Standard Edition Server 或 Enterprise Edition 前端池。 确定是否已下方**关联**的媒体配置边缘池。 
    
     ![显示服务器和池的拓扑生成器](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. 选择边缘池，并确定是否下一个跃点池配置**下一个跃点选择**下方。
    
     ![拓扑生成器下, 一个跃点选择](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a>验证旧版 XMPP 联盟的伙伴配置

1. 从旧版 XMPP 服务器中，导航到管理工具 \ 服务小程序。
    
2. 确认 Office Communications Server XMPP 网关服务已启动。 
    
     ![Office Communications Server XMPP 网关服务](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

