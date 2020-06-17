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
description: 每个 Survivable 分支设备（SBA）都与一个前端池相关联，该前端池充当 SBA 的备份注册器。 当将前端池迁移到 Skype for business Server 2019 时，在升级池时，SBA 必须与前端池解除关联，一旦池迁移到 Skype for Business Server 2019，则 SBA 可以与升级后的前端池重新关联。 这包括从拓扑生成器中的旧版拓扑中删除 SBA，然后将 SBA 添加到 Skype for business Server 2019 拓扑。 在从拓扑中删除 SBA 之前，必须首先将驻留在旧版 SBA 上的用户移到另一个前端池。 将 SBA 添加到 Skype for business Server 2019 拓扑后，这些用户即可移回 SBA。 这些步骤概括如下：
ms.openlocfilehash: 23fea7694a754b82ecad684d2ea02b603a6c7299
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751544"
---
# <a name="connect-a-survivable-branch-appliance"></a>连接 Survivable Branch Appliance

每个 Survivable 分支设备（SBA）都与一个前端池相关联，该前端池充当 SBA 的备份注册器。 将前端池迁移到 Skype for business Server 2019 时，在升级池时，SBA 必须与前端池解除关联。 将池迁移到 Skype for business Server 2019 后，可以将 SBA 重新关联到已升级的前端池。 这包括从拓扑生成器中的旧版拓扑中删除 SBA，然后将 SBA 添加到 Skype for business Server 2019 拓扑。 在从拓扑中删除 SBA 之前，必须首先将驻留在旧版 SBA 上的用户移到另一个前端池。 将 SBA 添加到 Skype for business Server 2019 拓扑后，可以将这些用户移回 SBA。 这些步骤概括如下：
  
1. 将驻留在旧 SBA 上的分支用户移动到另一个前端池。
    
2. 从旧版拓扑中删除 SBA，以将现有的前端池作为备份注册器断开连接。
    
3. 将 SBA 添加到 Skype for business Server 2019 拓扑，并将此新的前端池配置为备份注册器。 
    
4. 将分支用户移动到新的 Skype for Business Server 2019 SBA。
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a>将旧版 SBA 分支站点添加到您的拓扑

1. 打开“拓扑生成器”****。
    
2. 在左窗格中，右键单击 "**分支站点**"，然后单击 "**新建分支站点**"。
    
3. 在“定义新的分支站点”**** 对话框中，单击“名称”****，然后键入分支站点的名称。
    
4. （可选）单击“说明”****，然后为分支站点键入有一定含义的说明。
    
5. 单击“下一步”****。
    
6. （可选）在下一个“定义新的分支站点”**** 对话框中，执行以下任一操作： 
    
    1. 单击“市/县”****，然后键入分支站点所在的市/县的名称。
    
    2. 单击“国家/地区”****，然后键入分支站点所在的国家或地区的名称。
    
    3. 单击“国家/地区代码”****，然后键入分支站点所在的国家/地区的两位数呼叫代码。
    
7. 单击 "**下一步**"，然后，如果在此站点使用的是 Survivable 分支设备或服务器，请务必清除 "**关闭此向导时打开新 Survivable 向导**" 复选框。 单击“完成”****。
    
8. 若要将旧版 SBA 与 Skype for business Server 2019 前端池相关联，请执行以下操作：
    
    1. 展开已创建的分支站点。 
    
    2. 右键单击旧版版本，然后单击 "**新建**"。
    
    3. 单击 " **Survivable 分支设备**"。
    
9. 按照打开的向导中的说明执行操作。 有关向导项的信息，请参阅    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > Survivable 分支设备仅可与监控存储关联。 
  
10. 如果不在该站点上使用 Survivable Branch Appliance 或 Survivable Branch Server，请清除“此向导关闭后将打开新建 Survivable 向导”**** 复选框，然后单击“完成”****。
    
11. 对要添加到拓扑的每个分支站点重复之前的步骤。
    

