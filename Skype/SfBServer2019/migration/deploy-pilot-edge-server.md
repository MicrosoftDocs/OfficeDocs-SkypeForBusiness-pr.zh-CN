---
title: 部署试点 Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 本主题重点介绍您应了解业务 Server 2019 边缘服务器部署您 Skype 之前的配置设置。 业务服务器 2019年的 Skype 的部署和配置过程就如同 Skype 的业务服务器 2015年。 本节仅突出显示试点池中部署的一部分应考虑的要点。 有关详细步骤，请参阅 Skype 中的部署外部用户访问业务服务器 2019年中 for 部署文档，其中介绍的部署过程，并还提供了针对外部用户访问的配置信息。
ms.openlocfilehash: 5b755d0ba8802c47a176cb3375a87b6523f35fad
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32239853"
---
# <a name="deploy-pilot-edge-server"></a>部署试点 Edge Server

本主题重点介绍应业务 Server 2019 边缘服务器部署您 Skype 之前了解您的配置设置。 业务服务器 2019年的 Skype 的部署和配置过程就如同 Skype 的业务服务器 2015年。 本节仅突出显示试点池中部署的一部分应考虑的要点。 <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
导航至**定义新边缘池**向导时，查看以下步骤中所示的密钥配置设置。 请注意，只有少数页面的**定义新边缘池**向导所示。 
  
### <a name="to-define-an-edge-pool"></a>定义边缘池

1. 以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。
    
2. 导航到业务服务器 2019年节点 Skype。 右键单击**边缘池**，然后单击**新建边缘池**。
    
     ![定义新建边缘池对话框](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. 边缘池可以是**多计算机池**或**单计算机池**。
    
     ![定义边缘池 FQDN 对话框](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. 在**选择功能**页上不要启用联盟或 XMPP 联盟。 联盟和 XMPP 联盟同时当前路由通过旧边缘服务器。 将在迁移的更高版本阶段中配置这些功能。 

  
5. 继续完成以下向导页：**外部 Fqdn**、**定义内部 IP 地址**，和**定义外部 IP 地址**。
    
6. 在**定义下一个跃点服务器**页中，选择旧的边缘池的下一个跃点的控制器。 
    
     ![定义下一跃点对话框](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. 在**关联前端或中介池**页上没有相关联池与此边缘池这一次。 当前路由通过旧边缘服务器外部媒体流量。 此设置将在更高版本阶段的迁移配置。 
    
     ![关联前端池对话框](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. 单击**完成**，然后**发布**拓扑。 
    
9. 按照部署文档中新的边缘服务器上安装文件，配置证书并启动服务中的步骤。 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
它是非常重要您按照部署文档中的主题中的准则。 本节只安装这些服务器角色时上配置设置提供的一些指导。 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
现在，您应具有与业务 Server 2019 边缘服务器部署 Skype 并行部署了旧边缘服务器。 确认同时部署都正常运行，服务已启动，您可以管理每个部署之前将移动到下一个阶段。 
  

