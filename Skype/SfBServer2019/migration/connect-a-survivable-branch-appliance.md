---
title: 连接 Survivable Branch Appliance
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 每个 Survivable Branch Appliance (SBA) 与作为备份注册器 sba 关联的前端池相关联。 Sba 关联时升级池，一旦池已迁移至 Skype 的业务服务器 2019年同时必须从前端池解除关联前端池的业务服务器 2019，SBA 迁移到 Skype，可与已升级的前端 E 重新关联和池。 此步骤需要从拓扑生成器中将旧拓扑删除 sba 关联，然后将 SBA 添加到业务服务器 2019年拓扑的 Skype。 用户驻留在 SBA 必须首先将移动到另一个前端池的拓扑删除 sba 关联之前的传统上。 一旦 SBA 添加到业务服务器 2019年拓扑的 Skype，这些用户可以然后移回 sba。 这些步骤概括如下：
ms.openlocfilehash: ff35032d9abc5c1435e44dea7aca83d841b404c6
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373747"
---
# <a name="connect-a-survivable-branch-appliance"></a>连接 Survivable Branch Appliance

每个 Survivable Branch Appliance (SBA) 与作为备份注册器 sba 关联的前端池相关联。 时的前端池迁移到 Skype 的业务服务器 2019年，SBA 必须是解除关联的前端池升级池时。 池已迁移至 Skype 的业务服务器 2019年后，SBA 可重新与已升级的前端池相关联。 此步骤需要从拓扑生成器中将旧拓扑删除 sba 关联，然后将 SBA 添加到业务服务器 2019年拓扑的 Skype。 用户驻留在 SBA 必须首先将移动到另一个前端池的拓扑删除 sba 关联之前的传统上。 SBA 添加到业务服务器 2019年拓扑的 Skype 后，这些用户可以移回 sba。 这些步骤概括如下：
  
1. 将分支用户驻留在旧 sba 关联到另一个前端池上移动。
    
2. 从要断开作为备份注册器的现有前端池将旧拓扑删除 SBA。
    
3. 将 SBA 添加到业务服务器 2019年拓扑的 Skype 并作为备份注册器配置此新前端池。 
    
4. 为业务服务器 2019 SBA 将分支用户移动到新的 Skype。
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a>将旧 SBA 分支站点添加到您的拓扑

1. 打开**拓扑生成器**。
    
2. 在左窗格中，右键单击**分支站点**，然后单击**新的分支站点**。
    
3. 在**定义新的分支站点**对话框中，单击**名称**框中，然后键入分支站点的名称。
    
4. （可选）单击**说明**，然后键入分支站点的有意义的说明。
    
5. 单击“**下一步**”。
    
6. （可选）在下的**定义新的分支站点**对话框中，请执行以下任一操作： 
    
    1. 单击**市/县**，，然后键入分支站点所在的市/县的名称。
    
    2. 单击**国家/地区**，然后键入状态或分支站点所在的地区的名称。
    
    3. 单击**国家/地区代码**，然后键入分支站点所在的国家/地区的两位数呼叫代码。
    
7. 单击**下一步**，，然后，如果在该站点上使用 Survivable Branch Appliance or Server，请确保清除**打开新建 Survivable 向导此向导关闭时**复选框。 单击“**完成**”。
    
8. 将旧 sba 关联到业务 Server 2019 前端池的 Skype 关联起来：
    
    1. 展开已创建的分支站点。 
    
    2. 在旧版本上，右键单击，然后单击**新建**。
    
    3. 单击**Survivable Branch Appliance**。
    
9. 按照在打开的向导中的说明操作。 有关向导项目的信息，请参阅    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/en-us/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > Survivable Branch Appliance 仅可与监控存储相关联。 
  
10. 如果没有在该站点上使用 Survivable Branch Appliance or Server，清除**打开新建 Survivable 向导此向导关闭时**复选框，然后单击**完成**。
    
11. 对于要向拓扑中添加每个分支站点重复上述步骤。
    

