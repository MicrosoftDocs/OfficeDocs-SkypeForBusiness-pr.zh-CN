---
title: 验证Skype for Business Server中的拓扑
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: 摘要：了解如何验证Skype for Business Server拓扑和 Active Directory 服务器是否按预期工作。
ms.openlocfilehash: ec63977f4c70845f39aafe3521591ec93777f7d5
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860543"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a>验证Skype for Business Server中的拓扑
 
**总结：** 了解如何验证Skype for Business Server拓扑和 Active Directory 服务器是否按预期工作。
  
发布拓扑并安装在拓扑中每个服务器上的Skype for Business Server系统组件后，即可验证拓扑是否按预期工作。 这包括验证配置是否已传播到所有 Active Directory 服务器，以便整个域知道域中Skype for Business可用。 可以按任何顺序执行步骤 1 到 5。 但是，必须按顺序执行步骤 6、7 和 8，步骤 1 到步骤 5 之后，如下图所述。 验证拓扑是否为步骤 8（共 8 步）。
  
![概述图。](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a>测试前端池部署

最后一步是测试前端池，并确认Skype for Business客户端可以相互通信。 
  
### <a name="add-users-and-verify-client-connectivity"></a>添加用户并验证客户端连接性

1. 使用 Active Directory 计算机和用户将管理员角色的 Active Directory 用户对象添加到 **CSAdministrator** 组) 安装Skype for Business Server 控制面板Skype for Business Server部署 (。
    
    > [!IMPORTANT]
    > 如果未将相应的用户和组添加到 CsAdministors 组，则打开Skype for Business Server 控制面板时将收到一个错误，该错误显示“未经授权：由于基于角色的访问控制 (RBAC) 授权失败而拒绝访问。 
  
2. 如果用户对象当前已登录，则注销后重新登录，以注册新的组分配。
    
    > [!NOTE]
    > 用户帐户不能是运行Skype for Business Server的任何服务器的本地管理员。 
  
3. 使用管理帐户登录到安装了Skype for Business Server 控制面板的计算机。
    
4. "开始"菜单 Skype for Business Server 控制面板，然后提供凭据（如果出现提示）。 Skype for Business Server 控制面板显示部署信息。
    
5. 在左侧导航栏中，单击 **“拓扑**”，然后确认服务状态是否显示一台带有绿色箭头的计算机，并且复制状态的绿色复选标记位于已部署并联机的每个Skype for Business Server角色旁边。 
    
6. 在左侧导航栏中，单击 **“用户**”，然后单击 **“启用用户**”。 
    
7. 在 **“新建Skype for Business Server用户**”页上，单击 **“添加**”。
    
8. 若要为要查找的对象定义搜索参数，可 **在“从 Active Directory 中选择** ”页上选择 **“搜索**”，然后选择单击 **“添加筛选器**”。 还可以选择 **LDAP 搜索** 并输入 LDAP 表达式来筛选或限制将返回的对象。 确定搜索选项后，单击 **“查找**”。
    
9. 在“搜索结果”窗格中，选择要添加的用户，然后单击 **“确定**”。
    
10. 在 **“新建Skype for Business Server用户**”页上，所选用户位于 **“用户**”显示屏中。 在 **“将用户分配到池** 列表”中，选择用户应驻留在其中的服务器。
    
    下面是可用于配置对象的选项列表。
    
    - **生成用户的 SIP URI**
    
    - **电话**
    
    - **行 URI**
    
    - **会议策略**
    
    - **客户端版本策略**
    
    - **PIN 策略**
    
    - **外部访问策略**
    
    - **存档策略**
    
    - **位置策略**
    
    - **客户端策略**
    
    若要测试基本功能，请选择“ **生成用户的 SIP URI** 设置”选项 (配置中的其他选项使用默认设置) ，然后单击 **“启用**”，如图所示。
    
     ![在控制面板中启用用户。](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. 将显示一个摘要页，显示 **“启用** ”列中的复选标记，以指示已设置用户。 **SIP 地址** 列显示用户登录配置所需的地址。
    
     ![添加到Skype for Business Server 控制面板的用户。](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. 将一个用户登录到已加入域的计算机，将另一个用户登录到域中的另一台计算机。
    
13. 在两台客户端计算机上安装Skype for Business客户端，然后验证两个用户是否可以登录到Skype for Business Server，并可以互相发送即时消息。
    

