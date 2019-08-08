---
title: 部署试点池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 迁移到 Skype for business Server 2019 所需的第一步是部署试验池。 试用版池用于测试 Skype for Business Server 2019 与旧部署之间的共存。 共存是指在将所有用户和池移到 Skype for Business Server 2019 之前一直持续的临时状态。
ms.openlocfilehash: dc0e5b984aaa9ed931f3937b253fbe40aef9b051
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238379"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a>部署 Skype for Business Server 2019 试用版池

迁移到 Skype for business Server 2019 所需的第一步是部署试验池。 试用版池用于测试 Skype for Business Server 2019 与旧部署之间的共存。 共存是指在将所有用户和池移到 Skype for Business Server 2019 之前一直持续的临时状态。 
  
部署试验池时, 请使用 "定义新的前端池" 向导。 你应该在旧版池中部署 Skype for business Server 2019 试验池中的相同功能和工作负荷。 如果你部署了存档服务器、监视服务器或 System Center Operations Manager 以进行存档或监视你的旧环境, 并且希望在整个迁移过程中继续存档或监视, 你还需要在你的计算机中部署这些功能试点环境。 你部署的用于存档或监视旧版环境的版本将不会在 Skype for Business Server 2019 环境中捕获数据。 
  
> [!NOTE]
> 以下过程讨论了在整个试点池部署过程中应考虑的功能和设置。 本部分仅重点介绍您在试验池部署中应考虑的要点。 <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a>部署 Skype for Business Server 2019 试验池

1. 以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。
    
2. 展开树, 直到到达 " **Skype for business 服务器 2019** > **企业版前端池**"。
    
3. 右键单击 "**企业版前端池**", 然后选择 "**新建前端池**"。
  
4. 输入池完全限定的域名 (FQDN)。 定义试验池时, 可以选择部署企业版前端池或标准版服务器。 Skype for Business Server 2019 不需要你的试点池功能与你的旧版池中部署的功能相匹配。
    
    > [!CAUTION]
    > 为试验池定义的池或服务器 FQDN 必须是唯一的。 它不能与当前部署的旧池或任何其他服务器的名称相匹配。 
  
5. 在 "**选择功能**" 页面上, 选中您希望在此前端池上的功能所对应的复选框。 例如, 如果您仅部署即时消息 (IM) 和状态功能, 则可以选择 "会议" 复选框以允许多方 IM, 但不能选择 "拨入 (PSTN) 会议"、"企业语音" 或 "呼叫许可控制" 复选框。框, 因为它们表示语音、视频和协作式会议功能。 <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. 在 "**选择 collocated 服务器角色**" 页面上, 建议您选择 collocate Skype For business server 2019 中的中介服务器。 将旧版拓扑与 Skype for Business Server 2019 合并时, 我们需要首先 collocate 传统中介服务器。 合并拓扑并配置 Skype for Business Server 2019 中介服务器之后, 你可以决定在将中介服务器角色移动到 Skype for business 服务器时是否保留 collocated 中介服务器或将其更改为独立服务器2019的部署过程。 
   
7. 在试验池部署期间, 在 "**关联服务器角色与此前端池**" 页面上,*不要*选择 "**启用要由此前端池的媒体组件使用的边缘池**" 选项。 这是你将在迁移的后续阶段启用并联机的功能。 立即清除此设置。 
  
8. 在 "**选择 Office Web Apps 服务器**" 页面上, 单击 "**新建**", 然后指定应用程序服务器的 FQDN。
  
9. 在定义 "**存档 Sql server 存储**" 页面上, 定义 "用于 skype For Business 服务器存档和监视的 sql server 存储" 页面时, 选择之前为 skype For business server 2019 创建的 sql server 实例。 
  
10. 若要发布拓扑, 请右键单击 " **Skype For Business 服务器**" 节点, 然后单击 "**发布拓扑**"。
  
11. 发布过程完成后, 单击 "**完成**"。

12. 在移动到名为 "验证试验池共存" 的下一节之前, 你需要安装刚刚在已发布拓扑中定义的 Skype for Business Server 新的前端试行池, 请按照此处所述的步骤[安装 skype。拓扑中的服务器上的业务服务器](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)

13. 完成上一步骤后, 请转到下一节以验证与旧版池共存的引导池。
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
  

