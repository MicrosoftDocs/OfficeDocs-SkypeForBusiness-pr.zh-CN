---
title: 验证 Skype for Business Server 中的拓扑
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: 摘要：了解如何验证 Skype for Business Server 拓扑和 Active Directory 服务器是否按预期工作。 从 Microsoft 评估中心下载 Skype for Business Server 的免费试用版， https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 位置为：
ms.openlocfilehash: 0c2307f3ad0416a7175d92a1440744dbda9b31d3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833832"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a>验证 Skype for Business Server 中的拓扑
 
**摘要：** 了解如何验证 Skype for Business Server 拓扑和 Active Directory 服务器是否正常工作。 从 Microsoft 评估中心下载 Skype for Business Server [的免费试用版](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
在拓扑中的每台服务器上发布拓扑并安装 Skype for Business Server 系统组件后，即可验证拓扑是否正常工作。 这包括验证配置是否已传播到所有 Active Directory 服务器，以便整个域知道 Skype for Business 在域中可用。 可以按任意顺序执行步骤 1 到步骤 5。 但是，您必须按顺序执行步骤 6、7 和 8，在步骤 1 到 5 之后，如图中所述。 验证拓扑是步骤 8 中的步骤 8。
  
![概述图表。](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a>测试前端池部署

最后一步是测试前端池并确认 Skype for Business 客户端可以相互通信。 
  
### <a name="add-users-and-verify-client-connectivity"></a>添加用户并验证客户端连接

1. 使用 Active Directory 计算机和用户将 Skype for Business Server 部署 (的管理员角色的 Active Directory 用户对象添加到 **CSAdministrator** 组中) Skype for Business Server 控制面板。
    
    > [!IMPORTANT]
    > 如果未将相应的用户和组添加到 CsAdministors 组，则当您打开 Skype for Business Server 控制面板时，将收到一个错误，显示"未授权：由于基于角色的访问控制 (RBAC) 授权失败，访问被拒绝"。 
  
2. 如果用户对象当前已登录，则注销后重新登录，以注册新的组分配。
    
    > [!NOTE]
    > 用户帐户不能是运行 Skype for Business Server 的任何服务器的本地管理员。 
  
3. 使用管理帐户登录到安装了 Skype for Business Server 控制面板的计算机。
    
4. 启动 Skype for Business Server 控制面板，然后提供凭据（如果系统提示）。 Skype for Business Server 控制面板显示部署信息。
    
5. 在左侧导航栏中，单击"拓扑"，然后确认服务状态显示一台使用绿色箭头的计算机，并且每个已部署并联机的 Skype for Business Server 角色旁边都有用于复制状态的绿色选中标记。 
    
6. 在左侧导航栏中，单击 **"** 用户"，然后单击"**启用用户"。** 
    
7. 在"**新建 Skype for Business Server 用户**"页上，单击"**添加"。**
    
8. 若要为要查找的对象定义搜索参数，可以在"从 Active **Directory** 中选择"页上选择"搜索"，然后选择"添加 **筛选器"。**  您还可以选择 **LDAP 搜索并** 输入 LDAP 表达式以筛选或限制将返回的对象。 决定搜索选项后，单击"查找 **"。**
    
9. 在搜索结果窗格中，选择要添加的用户，然后单击"确定 **"。**
    
10. 在 **"新建 Skype for Business Server** 用户"页上，所选用户显示在" **用户"** 中。 在 **"将用户分配到池"** 列表中，选择用户应驻留的服务器。
    
    以下是可用于配置对象的选项列表。
    
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
    
    若要测试基本功能，请选择"生成用户的 **SIP URI"** 设置所需的选项 (配置中的其他选项使用默认设置) ，然后单击"启用"，如图所示。 
    
     ![在控制面板中启用用户。](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. 将显示一个摘要页，该页在"已启用"列中显示一个选中标记，以指示用户已设置。 **SIP 地址** 列显示用户登录配置所需的地址。
    
     ![添加到 Skype for Business Server 控制面板的用户。](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. 将一个用户登录到加入域的计算机，另一个用户登录到域中的另一台计算机。
    
13. 在两台客户端计算机上的每台计算机上安装 Skype for Business 客户端，然后验证这两个用户能否登录 Skype for Business Server，并可以相互发送即时消息。
    

