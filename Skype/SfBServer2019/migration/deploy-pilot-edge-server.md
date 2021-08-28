---
title: 部署试点边缘服务器
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
description: 本主题重点介绍在部署 Skype for Business Server 2019 边缘服务器之前应注意的配置设置。 Skype for Business Server 2019 的部署和配置过程与 2015 Skype for Business Server非常相似。 本节仅重点介绍了应作为试点池部署的一部分考虑的关键点。 有关详细步骤，请参阅部署文档中的 Deploying external user access in Skype for Business Server 2019，其中介绍了部署过程，并提供了外部用户访问的配置信息。
ms.openlocfilehash: c76d517bd5130c2babc41e0072ae7450b9838a64
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615006"
---
# <a name="deploy-pilot-edge-server"></a>部署试点边缘服务器

本主题重点介绍在部署 2019 边缘服务器之前应注意Skype for Business Server设置。 Skype for Business Server 2019 的部署和配置过程与 2015 Skype for Business Server非常相似。 本节仅重点介绍了应作为试点池部署的一部分考虑的关键点。 <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
在“定义新的边缘池”向导中导航时，查看以下步骤中显示的关键配置设置。请注意，仅显示了“定义新的边缘池”向导的部分页面。 
  
### <a name="to-define-an-edge-pool"></a>定义边缘池

1. 以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。
    
2. 导航到"Skype for Business Server 2019"节点。 右键单击“边缘池”，然后单击“新建边缘池”。
    
     ![定义"新建边缘池"对话框](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. 边缘池可以是 **多计算机池**，也可以是 **单计算机池**。
    
     ![定义边缘池 FQDN 对话框](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. 在“选择功能”页上，不要启用联盟或 XMPP 联盟。 联盟和 XMPP 联盟当前都通过旧边缘服务器进行路由。 将在迁移的稍后阶段中配置这些功能。 

  
5. 继续完成以下向导页面 **：External FQDNs、Define** **the internal IP address** 和 Define the external IP **address**。
    
6. 在" **定义下一个跃点服务器** "页上，为旧边缘池的下一个跃点选择控制器。 
    
     ![定义"下一个跃点"对话框](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. 在" **关联前端或中介** 池"页上，此时不要将池与此边缘池关联。 外部媒体流量当前通过旧版边缘服务器进行路由。 将在迁移的稍后阶段中配置此设置。 
    
     !["关联前端池"对话框](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. 单击 **"完成****"，然后单击**"发布拓扑"。 
    
9. 按照部署文档中的步骤在新的边缘服务器上安装文件、配置证书并启动服务。 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
遵循部署文档中的主题中的准则非常重要。 本节仅提供了一些有关安装这些服务器角色时的配置设置的指南。 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
现在，应该将旧边缘服务器与 Skype for Business Server 2019 边缘服务器部署并行部署。 在进入下一个阶段之前，确认这两个部署都正常运行，服务已启动，并且您可以管理每个部署。 
  

