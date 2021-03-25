---
title: 连接 Survivable Branch Appliance
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
description: 每个 Survivable Branch Appliance (SBA) 与充当 SBA 的备份注册机构的前端池关联。 将前端池迁移到 Skype for Business Server 2019 时，必须在升级池时从前端池取消 SBA 关联，一旦将池迁移到 Skype for Business Server 2019，SBA 就可以与升级的前端池重新关联。 这包括从拓扑生成器中的旧拓扑中删除 SBA，然后将 SBA 添加到 Skype for Business Server 2019 拓扑。 在从拓扑中删除 SBA 之前，必须先将位于旧 SBA 上的用户移动到另一个前端池。 将 SBA 添加到 Skype for Business Server 2019 拓扑后，可以将这些用户移回 SBA。 这些步骤概括如下：
ms.openlocfilehash: e56bae1631a315b6f42042fb6a7bedd4f144a1b6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113338"
---
# <a name="connect-a-survivable-branch-appliance"></a>连接 Survivable Branch Appliance

每个 Survivable Branch Appliance (SBA) 与充当 SBA 备份注册机构的前端池关联。 将前端池迁移到 Skype for Business Server 2019 时，在升级池时，必须将 SBA 与前端池解除关联。 将池迁移到 Skype for Business Server 2019 后，SBA 可以与升级的前端池重新关联。 这包括从拓扑生成器中的旧拓扑中删除 SBA，然后将 SBA 添加到 Skype for Business Server 2019 拓扑。 在从拓扑中删除 SBA 之前，必须先将位于旧 SBA 上的用户移动到另一个前端池。 将 SBA 添加到 Skype for Business Server 2019 拓扑后，可以将这些用户移回 SBA。 这些步骤概括如下：
  
1. 将位于旧 SBA 上的分支用户移动到另一个前端池。
    
2. 从旧拓扑中删除 SBA 以断开现有前端池作为备份注册器。
    
3. 将 SBA 添加到 Skype for Business Server 2019 拓扑，并配置此新的前端池作为备份注册器。 
    
4. 将分支用户移动到新的 Skype for Business Server 2019 SBA。
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a>将旧 SBA 分支站点添加到拓扑

1. 打开“拓扑生成器”。
    
2. 在左窗格中，右键单击"**分支** 站点"，然后单击"**新建分支站点"。**
    
3. 在“定义新的分支站点”对话框中，单击“名称”，然后键入分支站点的名称。
    
4. （可选）单击“说明”，然后为分支站点键入有一定含义的说明。
    
5. 单击“下一步”。
    
6. （可选）在下一个“定义新的分支站点”对话框中，执行以下任一操作： 
    
    1. 单击“市/县”，然后键入分支站点所在的市/县的名称。
    
    2. 单击“国家/地区”，然后键入分支站点所在的国家或地区的名称。
    
    3. 单击“国家/地区代码”，然后键入分支站点所在的国家/地区的两位数呼叫代码。
    
7. 单击 **"** 下一步"，然后，如果在此站点上使用 Survivable Branch Appliance 或 Survivable Branch Server，请确保清除"关闭此向导时打开 **新建 Survivable 向导** "复选框。 单击“完成”。
    
8. 若要将旧 SBA 与 Skype for Business Server 2019 前端池关联：
    
    1. 展开已创建的分支站点。 
    
    2. 右键单击旧版本，然后单击 **新建。**
    
    3. 单击 **Survivable Branch Appliance**。
    
9. 按照打开的向导中的说明执行操作。 有关向导项的信息，请参阅    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](/previous-versions/office/lync-server-2013/lync-server-2013-define-a-survivable-branch-appliance-or-server). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > Survivable Branch Appliance 只能与监控存储关联。 
  
10. 如果不在该站点上使用 Survivable Branch Appliance 或 Survivable Branch Server，请清除“此向导关闭后将打开新建 Survivable 向导”复选框，然后单击“完成”。
    
11. 对要添加到拓扑的每个分支站点重复之前的步骤。
