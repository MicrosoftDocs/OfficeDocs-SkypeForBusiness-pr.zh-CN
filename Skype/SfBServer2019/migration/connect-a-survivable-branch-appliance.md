---
title: 连接 Survivable Branch Appliance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 每个 Survivable 分支装置（SBA）都与一个前端池相关联，该池充当 SBA 的备份注册机构。 当前端池迁移到 Skype for business Server 2019 时，SBA 必须在池升级时与前端池断开关联，一旦池迁移到 Skype for business Server 2019 后，SBA 可以与升级的前 E 重新关联nd pool。 这包括从拓扑生成器中的旧版拓扑中删除 SBA，然后将 SBA 添加到 Skype for business Server 2019 拓扑。 在从拓扑结构中删除 SBA 之前，必须首先将驻留在旧 SBA 上的用户移动到另一个前端池。 将 SBA 添加到 Skype for business Server 2019 拓扑后，这些用户就可以移回 SBA。 下面总结了这些步骤：
ms.openlocfilehash: daeb061936ece02767e3299d2358d8e16ba09218
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813730"
---
# <a name="connect-a-survivable-branch-appliance"></a>连接 Survivable Branch Appliance

每个 Survivable 分支装置（SBA）都与一个前端池相关联，用作 SBA 的备份注册机构。 当前端池迁移到 Skype for business Server 2019 时，在升级池时，SBA 必须与前端池断开关联。 将池迁移到 Skype for business Server 2019 后，SBA 可以与已升级的前端池重新关联。 这包括从拓扑生成器中的旧版拓扑中删除 SBA，然后将 SBA 添加到 Skype for business Server 2019 拓扑。 在从拓扑结构中删除 SBA 之前，必须首先将驻留在旧 SBA 上的用户移动到另一个前端池。 将 SBA 添加到 Skype for business Server 2019 拓扑后，这些用户可以移回 SBA。 下面总结了这些步骤：
  
1. 将驻留在旧式 SBA 上的分支用户移动到另一个前端池。
    
2. 从旧版拓扑中删除 SBA，以将现有的前端池与备份注册机构断开连接。
    
3. 将 SBA 添加到 Skype for business Server 2019 拓扑，并将此新的前端池配置为备份注册机构。 
    
4. 将分支用户移动到新的 Skype for Business Server 2019 SBA。
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a>将旧版 SBA 分支站点添加到你的拓扑

1. 打开**拓扑生成器**。
    
2. 在左窗格中，右键单击 "**分支网站**"，然后单击 "**新建分支站点**"。
    
3. 在 "**定义新分支网站**" 对话框中，单击 "**名称**"，然后键入分支网站的名称。
    
4. 可选单击 "**说明**"，然后为分支网站键入有意义的说明。
    
5. 单击" **下一步**"。
    
6. 可选在 "下一步**定义新分支站点**" 对话框中，执行下列任一操作： 
    
    1. 单击 "**城市**"，然后键入分支站点所在城市的名称。
    
    2. 单击 "**状态/区域**"，然后键入分支站点所在的省/市/自治区或地区的名称。
    
    3. 单击 "**国家/地区代码**"，然后键入分支站点所在的国家/地区的两位数呼叫代码。
    
7. 单击 "**下一步**"，然后，如果在此网站上使用 Survivable 分支设备或服务器，请确保清除 "**关闭此向导时打开新 Survivable 向导**" 复选框。 单击“**完成**”。
    
8. 要将旧版 SBA 关联到 Skype for business Server 2019 前端池，请执行以下操作：
    
    1. 展开已创建的分支站点。 
    
    2. 右键单击旧版版本，然后单击 "**新建**"。
    
    3. 单击 " **Survivable 分支装置**"。
    
9. 按照向导中打开的说明进行操作。 有关向导项的信息，请参阅    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/en-us/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > Survivable 分支设备只能与监视应用商店相关联。 
  
10. 如果未在此网站使用 Survivable 分支装置或服务器，请清除 "**关闭此向导时打开新的 Survivable 向导**" 复选框，然后单击 "**完成**"。
    
11. 对要添加到拓扑中的每个分支网站重复上述步骤。
    

