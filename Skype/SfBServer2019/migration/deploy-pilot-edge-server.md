---
title: 部署试点 Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 本主题重点介绍部署 Skype for Business Server 2019 Edge 服务器之前应注意的配置设置。 Skype for business Server 2019 的部署和配置过程非常类似于 Skype for business Server 2015。 本部分仅重点介绍您在试验池部署中应考虑的要点。 有关详细步骤, 请参阅部署文档中的 Skype for business Server 2019 中的部署外部用户访问 (介绍部署过程), 还提供外部用户访问的配置信息。
ms.openlocfilehash: b416ba38646d05f3d10a7d2643c01924fe57020a
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238386"
---
# <a name="deploy-pilot-edge-server"></a>部署试点 Edge Server

本主题重点介绍部署 Skype for Business Server 2019 Edge 服务器之前应注意的配置设置。 Skype for business Server 2019 的部署和配置过程非常类似于 Skype for business Server 2015。 本部分仅重点介绍您在试验池部署中应考虑的要点。 <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
通过 "**定义新的边缘池**" 向导导航时, 请查看以下步骤中所示的关键配置设置。 请注意, 仅显示 "**定义新边缘池**" 向导的几个页面。 
  
### <a name="to-define-an-edge-pool"></a>定义边缘池

1. 以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。
    
2. 导航到 Skype for business 服务器2019节点。 右键单击 "**边缘池**", 然后单击 "**新建边缘池**"。
    
     ![定义 "新建边缘池" 对话框](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. 边缘池可以是**多台计算机池**或**单个计算机池**。
    
     ![定义 "边缘池 FQDN" 对话框](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. 在 "**选择功能**" 页面上, 不要启用联盟或 XMPP 联合身份验证。 联合身份验证和 XMPP 联合身份验证当前通过旧版 Edge 服务器路由。 将在迁移的后续阶段配置这些功能。 

  
5. 继续完成以下向导页:**外部 fqdn**、**定义内部 Ip 地址**以及**定义外部 IP 地址**。
    
6. 在 "**定义下一个跃点服务器**" 页面上, 选择旧版 Edge 池的下一跃点的 Director。 
    
     !["定义下一跃点" 对话框](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. 此时, 在 "**关联前端或中介池**" 页面上, 不要将池与此边界池关联。 外部媒体流量当前通过旧版 Edge 服务器路由。 将在迁移的后续阶段配置此设置。 
    
     !["关联前端池" 对话框](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. 单击 "**完成**", 然后**发布**拓扑。 
    
9. 按照部署文档中的步骤在新边缘服务器上安装文件、配置证书并启动服务。 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
请务必遵循部署文档的主题中的指南。 本部分仅提供了有关安装这些服务器角色时的配置设置指南。 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
现在, 你应该与 Skype for business Server 2019 Edge 服务器部署并行部署旧式 Edge 服务器。 验证两个部署是否正常运行, 服务是否已启动, 并且你可以在迁移到下一阶段之前管理每个部署。 
  

