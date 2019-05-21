---
title: 验证 Skype for Business 服务器中的拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: '摘要: 了解如何验证 Skype for business 服务器拓扑和 Active Directory 服务器是否按预期工作。 从 Microsoft 评估中心下载免费试用版 Skype for Business 服务器, 网址为: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: aad91c7bfb1e3187ace5d5caec4e3f18952a11d8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306589"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a>验证 Skype for Business 服务器中的拓扑
 
**摘要:** 了解如何验证 Skype for business 服务器拓扑和 Active Directory 服务器是否按预期工作。 从[Microsoft 评估中心](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)下载 Skype For business 服务器的免费试用版。
  
在已发布拓扑和拓扑中的每台服务器上安装了 Skype for Business 服务器系统组件后, 即可验证拓扑是否按预期方式工作。 这包括验证配置是否已传播到所有 Active Directory 服务器, 以便整个域知道 Skype for Business 在域中可用。 第 1 步至第 5 步可以按任意顺序执行。 但是，第 6、7、8 步必须在第 1 步至第 5 步之后按图表所示顺序执行。 验证拓扑是 8 个步骤中的第 8 步。
  
![概述图表。](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a>测试前端池部署

最后一步是测试前端池并确认 Skype for Business 客户端可以互相通信。 
  
### <a name="add-users-and-verify-client-connectivity"></a>添加用户并验证客户端连接

1. 使用 Active Directory 计算机和用户将 Skype for business Server 部署 (安装了 Skype for business Server 控制面板) 的管理员角色的 Active Directory 用户对象添加到**CSAdministrator**组。
    
    > [!IMPORTANT]
    > 如果不将相应的用户和组添加到 CsAdministors 组, 则打开 Skype for Business 服务器控制面板时将收到错误, "未经授权: 由于基于角色的访问控制 (RBAC) 授权失败, 访问被拒绝." 
  
2. 如果用户对象当前已登录，则注销后重新登录，以注册新的组分配。
    
    > [!NOTE]
    > 用户帐户不能是运行 Skype for Business Server 的任何服务器的本地管理员。 
  
3. 使用 "管理" 帐户登录到安装了 "Skype for Business 服务器控制面板" 的计算机。
    
4. 如果出现提示, 请启动 Skype for business 服务器控制面板, 然后提供凭据。 Skype for business 服务器 "控制面板" 显示部署信息。
    
5. 在左侧导航栏中, 单击 "**拓扑**", 然后确认 "服务状态" 显示计算机带有绿色箭头, 并且复制状态的绿色复选标记位于已部署并联机的每个 Skype For business 服务器角色旁边。 
    
6. 在左侧导航栏中，单击**用户**，然后单击**启用用户**。 
    
7. 在 "**新建 Skype for Business 服务器" 用户**页面上, 单击 "**添加**"。
    
8. 要为希望查找的对象定义搜索参数，可以在**从 Active Directory 中选择**页上选择**搜索**，然后选择单击**添加筛选器**。还可以选择**LDAP 搜索**，然后输入 LDAP 表达式以筛选或限制将返回的对象。确定“搜索”选项后，单击**查找**。
    
9. 在搜索结果窗格中，选择要添加的用户，然后单击 **确定**。
    
10. 在 "**新建 Skype For Business 服务器" 用户**页面上, 所选用户将位于 "**用户**" 显示中。 In the **Assign users to a pool** list, select the server where the users should reside.
    
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
    
    若要测试基本功能, 请为 "**生成用户的 SIP URI** " 设置选择所需的选项 (配置中的其他选项使用默认设置), 然后单击 "**启用**", 如图所示。
    
     ![在控制面板中启用用户。](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. 此时将显示摘要页面，其中**已启用**列将显示复选标记，指示用户现已完成设置。**SIP 地址**列将显示用户登录配置所需的地址。
    
     ![已添加到 Skype for Business Server 控制面板的用户。](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. 使一个用户登录到加入域的计算机，另一个用户登录到域中的另一台计算机。
    
13. 在两台客户端计算机上安装 Skype for Business 客户端, 然后验证这两个用户都可以登录到 Skype for business 服务器, 并且可以互相发送即时消息。
    

