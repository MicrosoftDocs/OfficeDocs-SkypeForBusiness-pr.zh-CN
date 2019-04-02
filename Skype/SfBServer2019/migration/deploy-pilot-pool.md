---
title: 部署试点池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 一个迁移到 Skype 的业务服务器 2019年所需的第一个步骤是部署试点池。 试点池是与旧部署测试业务服务器 2019 Skype 的共存的位置。 共存一直持续到移动所有用户和池到 Skype 的业务服务器 2019年的临时状态。
ms.openlocfilehash: 26f391a485c991aa3575498b98b181f1b5ac761c
ms.sourcegitcommit: 70d3a3b162fdbca1cf2c2713d6bce54c3cbad3bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "31026047"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a>为业务服务器 2019年试点池部署 Skype

一个迁移到 Skype 的业务服务器 2019年所需的第一个步骤是部署试点池。 试点池是与旧部署测试业务服务器 2019 Skype 的共存的位置。 共存一直持续到移动所有用户和池到 Skype 的业务服务器 2019年的临时状态。 
  
部署试点池时，您可以使用定义新前端池向导。 您应在您的业务服务器 2019年试点池已在旧池中的 Skype 部署相同的功能和工作负荷。 如果您部署存档服务器、 监控服务器或 System Center Operations Manager 存档或监控旧环境，并且想要继续存档或监控在迁移过程，您需要同时部署中的这些功能您试验环境。 部署存档或监控您的旧版本环境不会捕获您 Skype 业务服务器 2019年环境中的数据。 
  
> [!NOTE]
> 功能和设置应考虑您的总体试点池部署过程的一部分，讨论了下面的过程。 本节仅突出显示试点池中部署的一部分应考虑的要点。 <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a>若要部署的业务服务器 2019年试点池 Skype

1. 以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。
    
2. 展开树，直到到达**业务服务器 2019年的 Skype** > **Enterprise Edition 前端池**。
    
3. 右键单击**Enterprise Edition 前端池**，然后选择**新前端池**。
  
4. 输入池完全限定的域名 (FQDN)。 定义您的试点池时，您可以选择部署 Enterprise Edition 前端池或 Standard Edition server。 Skype 的业务服务器 2019年不需要试点池功能匹配内容已在旧池中部署。
    
    > [!CAUTION]
    > 池或服务器为试点池定义的 FQDN 必须是唯一的。 它不能匹配当前部署的旧池或当前部署的任何其他服务器的名称。 
  
5. 在**选择功能**页上，选择您希望此前端池上的功能对应的复选框。 如果您正在部署仅即时消息 (IM) 和状态功能，例如，应选择会议复选框，以允许多方 IM，但不是应选择的电话拨入式 (PSTN) 会议，企业语音或 Call Admission Control 检查框中，因为它们代表语音、 视频和协作会议功能。 <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. 在**选择并置的服务器角色**页中，我们建议您选择要将 Skype 中的中介服务器并置的业务服务器 2019年。 合并时旧拓扑与 Skype 的业务服务器 2019年，我们需要您首先并置旧中介服务器。 合并拓扑并配置后 Skype 业务 Server 2019 中介服务器，可以决定是否保留并置的中介服务器，或将其更改为独立服务器时将中介服务器角色到 Skype 移动业务服务器2019 更高版本中的部署过程。 
   
7. 在**关联服务器角色与此前端池**页上试点池部署期间*不*选择**启用此前端池的媒体组件使用的边缘池**选项。 这是迁移的一项功能将启用，还可以联机在更高版本阶段。 保留此设置清除现在。 
  
8. 在**选择 Office Web Apps 服务器**页上，单击**新建**，并指定应用程序服务器的 FQDN。
  
9. 在**定义存档 SQL Server 存储**页上时定义的两个 Skype 业务 Server 存档和监控的 SQL Server 存储，选择为 Skype 前面创建的业务服务器 2019年的 SQL Server 实例。 
  
10. 若要发布拓扑，右键单击**Skype 业务服务器**节点，然后单击**发布拓扑**。
  
11. 完成发布过程后，单击**完成**。

12. 将移动到下一节调用"验证旧池与试点池共存"之前需要安装 Business Server 新前端试点池我们只发布的拓扑中定义的 Skype，请按照下面概括的过程安装 Skype[为在拓扑中的服务器上的业务服务器](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)

13. 上一步骤完成后，转到下一节来验证试点池与旧池的共存情况。
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
  

