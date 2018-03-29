---
title: 在 Skype for Business Server 2015 中验证拓扑
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: '摘要： 了解如何验证业务服务器拓扑 Skype 和 Active Directory 服务器按预期的方式工作。 有关从 Microsoft 评估中心的业务服务器 2015年下载免费试用版的 Skype: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: 983ecf8b78a12898d18f04f7ec5c26c5271cf79a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="verify-the-topology-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中验证拓扑
 
**摘要：**了解如何确定业务服务器拓扑 Skype 和 Active Directory 服务器按预期的方式工作。 有关从[Microsoft 评估中心](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)业务服务器 2015年下载 Skype 的免费试用版。
  
已发布的拓扑和 Skype 业务服务器系统组件安装在每个拓扑中的服务器后，您就可以验证拓扑按预期的方式工作。 这包括验证配置传播到所有 Active Directory 的服务器，以便整个域知道 Skype 业务可在域中。 您可以按照任意顺序完成第 1 步至第 5 步。 但是，第 6、7、8 步必须在第 1 步至第 5 步之后按图表所示顺序执行。 验证拓扑是 8 个步骤中的第 8 步。
  
![概述图表。](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a>测试前端池部署

最后一步是测试前端池并确认 Skype 业务客户端可以相互通信。 
  
### <a name="add-users-and-verify-client-connectivity"></a>添加用户并验证客户端连接

1. 使用活动目录计算机和用户添加到**CSAdministrator**组的管理员角色的 Active Directory 用户对象 （在其上安装了业务服务器控件面板的 Skype） 的业务服务器部署 Skype。
    
    > [!IMPORTANT]
    > 如果没有在 CsAdministors 组中添加适当的用户和组，您会收到错误，当您打开 Skype 业务服务器控制面板中读取，它"未经授权： 访问由于基于角色的访问控制 (RBAC) 授权失败被拒绝." 
  
2. 如果用户对象当前已登录，则注销后重新登录，以注册新的组分配。
    
    > [!NOTE]
    > 用户帐户不能为任何业务服务器运行 Skype 的服务器的本地管理员。 
  
3. 使用管理帐户登录到计算机上装有 Skype 业务服务器的控制面板。
    
4. 为业务服务器控制面板启动 Skype，然后如果系统提示您提供凭据。 Skype 业务服务器控件面板显示部署的信息。
    
5. 在左侧的导航栏中，单击**拓扑结构**，并确认服务状态显示带有一个绿色箭头的计算机和一个绿色的复选标记为复制状态是每个已部署和联机业务服务器角色的 Skype 旁边。 
    
6. 在左侧导航栏中，单击**用户**，然后单击**启用用户**。 
    
7. 在**新的 Skype 业务服务器用户的**页面上，单击**添加**。
    
8. 要为希望查找的对象定义搜索参数，可以在**从 Active Directory 中选择**页上选择**搜索**，然后选择单击**添加筛选器**。还可以选择**LDAP 搜索**，然后输入 LDAP 表达式以筛选或限制将返回的对象。确定“搜索”选项后，单击**查找**。
    
9. 在搜索结果窗格中，选择要添加的用户，然后单击 **确定**。
    
10. 在**新 Skype 业务服务器用户的**页面上，您所选的用户是在**用户**显示。 在**将用户分配给池**列表中，选择应驻留用户的服务器。
    
    您可以使用以下列表中的选项来配置对象。
    
    - **生成用户的 SIP URI**
    
    - **电话**
    
    - **线路 URI**
    
    - **会议策略**
    
    - **客户端版本策略**
    
    - **PIN 策略**
    
    - **外部访问策略**
    
    - **存档策略**
    
    - **位置策略**
    
    - **客户端策略**
    
    要测试的基本功能，请选择您想用于**生成用户的 SIP URI**设置 （其他选项中配置使用默认设置），选项然后单击**启用**，如图中所示。
    
     ![在控制面板中启用用户。](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. 此时将显示摘要页面，其中**已启用**列将显示复选标记，指示用户现已完成设置。**SIP 地址**列将显示用户登录配置所需的地址。
    
     ![已添加到 Skype for Business Server 控制面板的用户。](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. 使一个用户登录到加入域的计算机，另一个用户登录到域中的另一台计算机。
    
13. 为在每两个客户端计算机上业务客户端安装 Skype，并验证两个用户可以登录到 Skype 业务服务器并可以相互发送即时消息。
    

