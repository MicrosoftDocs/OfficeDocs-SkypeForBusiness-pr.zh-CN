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
description: 迁移到 Skype for business Server 2019 所需的第一步是部署试点池。 您可以使用试点池在旧部署中测试 Skype for Business Server 2019 的共存。 共存是在将所有用户和池移至 Skype for business Server 2019 之前一直持续的临时状态。
ms.openlocfilehash: 46d8b6fd6cefa2894f67a1c24732ace01ca65785
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752854"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a>部署 Skype for Business Server 2019 试点池

迁移到 Skype for business Server 2019 所需的第一步是部署试点池。 您可以使用试点池在旧部署中测试 Skype for Business Server 2019 的共存。 共存是在将所有用户和池移至 Skype for business Server 2019 之前一直持续的临时状态。 
  
部署试点池时，应使用“定义新前端池”向导。 您应在您的旧版池中部署与您的 Skype for Business Server 2019 试验池相同的功能和工作负载。 如果您部署了存档服务器、监视服务器或 System Center Operations Manager 以存档或监视您的旧环境，并且您希望在整个迁移过程中继续进行存档或监控，则还需要在您的试点环境中部署这些功能。 您部署的用于存档或监视旧环境的版本将不会在 Skype for Business Server 2019 环境中捕获数据。 
  
> [!NOTE]
> 随后的过程讨论应被视为试点池总体部署过程一部分的功能和设置。 本节只着重介绍在部署试点池的过程中应考虑的关键点。 <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a>部署 Skype for Business Server 2019 试点池

1. 以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。
    
2. 展开树，直至您进入**Skype for business Server 2019**  >  **Enterprise Edition 前端池**。
    
3. 右键单击 " **Enterprise Edition 前端池**"，然后选择 "**新建前端池**"。
  
4. 输入池完全限定的域名（FQDN）。 在定义试点池时，可以选择部署企业版前端池或 Standard Edition server。 Skype for Business Server 2019 不要求试点池功能与您的旧版池中部署的功能相匹配。
    
    > [!CAUTION]
    > 为引导池定义的池或服务器 FQDN 必须是唯一的。 它无法与当前部署的旧池或任何其他服务器的名称相匹配。 
  
5. 在“选择功能”**** 页上，选中希望此前端池具有的功能的复选框。 例如，如果仅部署即时消息（IM）和状态功能，则应选中 "会议" 复选框以允许多方 IM，但不会选择 "拨入（PSTN）会议"、"企业语音" 或 "呼叫允许控制" 复选框，因为它们代表语音、视频和协作会议功能。 <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. 在 "**选择并置服务器角色**" 页上，我们建议您选择并置 Skype For business server 2019 中的中介服务器。 将旧版拓扑与 Skype for business Server 2019 合并时，我们需要您首先并置旧版中介服务器。 在合并拓扑并配置 Skype for Business Server 2019 中介服务器后，您可以决定是否保留并置中介服务器，或在部署过程中稍后将中介服务器角色移到 Skype for business Server 2019 时，将其更改为独立服务器。 
   
7. 在引导池部署过程中，在 "**将服务器角色与此前端池关联**" 页上，*不要*选择 "**启用此前端池的媒体组件要使用的边缘池**" 选项。 这是您将启用并使其在后面的迁移阶段进入联机状态的功能。 目前请清除此设置。 
  
8. 在“选择 Office Web Apps 服务器”**** 页上，单击“新建”**** 并指定应用程序服务器的 FQDN。
  
9. 在 "**定义存档 Sql server 存储**" 页上，在定义 "skype For Business server 存档和监视的 sql server 存储" 页上，选择之前为 skype For business server 2019 创建的 sql server 实例。 
  
10. 若要发布拓扑，请右键单击 " **Skype For Business Server** " 节点，然后单击 "**发布拓扑**"。
  
11. 发布过程完成后，单击“完成”****。

12. 在转到下一节（称为 "验证试点池与旧版池共存"）之前，需要安装刚刚在已发布拓扑中定义的 Skype for Business Server 新的前端引导池，请按照此处所述的过程在[拓扑中的服务器上安装 skype For Business server](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)

13. 完成上一步后，移到下一节以验证试点池与旧版池共存。
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
  

