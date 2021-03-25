---
title: 部署试点池
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
description: 迁移到 Skype for Business Server 2019 所需的第一步之一是部署试点池。 试点池是测试 Skype for Business Server 2019 与旧部署共存的地方。 共存是一种临时状态，一直持续到将所有用户和池移动到 Skype for Business Server 2019。
ms.openlocfilehash: a8d9a1bbe5f629a91721ebe530e6a192e3e65b62
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113288"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a>部署 Skype for Business Server 2019 试点池

迁移到 Skype for Business Server 2019 所需的第一步之一是部署试点池。 试点池是测试 Skype for Business Server 2019 与旧部署共存的地方。 共存是一种临时状态，一直持续到将所有用户和池移动到 Skype for Business Server 2019。 
  
部署试点池时，应使用“定义新前端池”向导。 应在 Skype for Business Server 2019 试点池中部署与旧版池中相同的功能和工作负载。 如果已部署存档服务器、监控服务器或 System Center Operations Manager 以存档或监视旧环境，并且您希望在整个迁移过程中继续存档或监控，则还需要在试点环境中部署这些功能。 你部署用于存档或监视旧环境的版本不会捕获 Skype for Business Server 2019 环境中的数据。 
  
> [!NOTE]
> 随后的过程讨论应被视为试点池总体部署过程一部分的功能和设置。 本节只着重介绍在部署试点池的过程中应考虑的关键点。 <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a>部署 Skype for Business Server 2019 试点池

1. 以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。
    
2. 展开树，直到到达 **Skype for Business Server 2019**  >  **Enterprise Edition 前端池**。
    
3. 右键单击 **"Enterprise Edition 前端池"，** 然后选择 **"新建前端池"。**
  
4. 输入 FQDN 中的池完全限定 (域名) 。 定义试点池时，可以选择部署 Enterprise Edition 前端池或 Standard Edition Server。 Skype for Business Server 2019 不要求试点池功能与旧池中部署的功能相匹配。
    
    > [!CAUTION]
    > 为试点池定义的池或服务器 FQDN 必须是唯一的。 它不能匹配当前部署的旧池或当前部署任何其他服务器的名称。 
  
5. 在“选择功能”页上，选中希望此前端池具有的功能的复选框。 例如，如果您仅部署即时消息 (IM) 和状态功能，则应该选中"会议"复选框以允许多方 IM，但不选中"电话拨入式 (PSTN) 会议、企业语音 或呼叫允许控制"复选框，因为它们代表语音、视频和协作会议功能。 <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. 在" **选择并并的服务器** 角色"页上，我们建议您选择在 Skype for Business Server 2019 中并并中介服务器。 在将旧拓扑与 Skype for Business Server 2019 合并时，我们要求您首先并并旧中介服务器。 合并拓扑并配置 Skype for Business Server 2019 中介服务器后，可以在部署过程中稍后将中介服务器角色移动到 Skype for Business Server 2019 时决定是保留并并的中介服务器，还是将其更改为独立服务器。 
   
7. 在"**将服务器角色与此** 前端池关联"页上的"试点池部署期间，不要选择"启用此前端池的媒体组件使用的边缘 **池"** 选项。 这是您将启用并使其在后面的迁移阶段进入联机状态的功能。 目前请清除此设置。 
  
8. 在“选择 Office Web Apps 服务器”页上，单击“新建”并指定应用程序服务器的 FQDN。
  
9. 在"定义存档 **SQL Server** 存储"页上，为 Skype for Business Server 存档和监控定义 SQL Server 存储时，选择之前为 Skype for Business Server 2019 创建的 SQL Server 实例。 
  
10. 要发布拓扑，请右键单击 **"Skype for Business Server"** 节点，然后单击"**发布拓扑"。**
  
11. 发布过程完成后，单击“完成”。

12. 在移动到下一部分"验证试点池与旧池共存"之前，你需要安装我们刚刚在已发布拓扑中定义的 Skype for Business Server 新前端试点池，请按照此处列出的步骤在拓扑中的服务器上安装 [Skype for Business Server](../../SfbServer/deploy/install/install-skype-for-business-server.md)

13. 完成上一步后，移至下一部分以验证试点池与旧池的共存。
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
