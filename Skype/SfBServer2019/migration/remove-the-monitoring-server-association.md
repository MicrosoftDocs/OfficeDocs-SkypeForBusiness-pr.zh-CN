---
title: 删除监控服务器关联
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
description: 若要删除监视服务器，你需要更改或清除关联的前端池、前端服务器、Survivable 分支设备和 Survivable 分支服务器上的依赖关系。 编辑前端池、前端服务器、Survivable 分支装置和 Survivable 分支服务器的属性以删除相关性。 清除相关性并在拓扑生成器中删除服务器后，系统会通知你拓扑生成器中关联的数据库存储对象也将被删除。
ms.openlocfilehash: aed16d60fbdae2413cb7890e38895bf6930cd4fd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812860"
---
# <a name="remove-the-monitoring-server-association"></a>删除监控服务器关联

若要删除监视服务器，你需要更改或清除关联的前端池、前端服务器、Survivable 分支装置和 Survivable 分支服务器上的依赖关系。 编辑 "前端池"、"前端服务器"、"Survivable 分支" 装置和 "Survivable 分支服务器" 的属性以删除相关性。 清除相关性并在拓扑生成器中删除服务器后，系统会通知你拓扑生成器中关联的数据库存储对象也将被删除。
  
### <a name="to-remove-the-monitoring-server-association"></a>删除监视服务器关联

1. 在 Skype for Business 服务器2019前端服务器上，打开拓扑生成器。
    
2. 导航到 "旧版安装" 节点。
    
3. 在拓扑生成器中，展开 "**企业版前端池**"、"**标准版前端服务器**" 或 "**分支站点**"，具体取决于定义监视服务器的位置。
    
4. 如果您有关联的 Survivable 分支服务器，请展开 "**分支站点**"，展开 "分支站点名称"，然后展开 "**分支机构" Survivable**。
    
    > [!NOTE]
    > 用户界面中的**Survivable 分支装置**适用于 Survivable 分支服务器和 Survivable 分支装置。 
  
5. 右键单击与监视服务器相关联的池、服务器或设备，然后单击 "**编辑属性**"。
    
6. 在 "**编辑属性**" 下的 "**常规** > **关联**" 下，清除 "**关联监视服务器**" 复选框，然后单击 **"确定"**。
    
7. 对与监视服务器关联的任何其他池、服务器或设备重复上一步骤。
    
8. 右键单击监视服务器，然后单击 "**删除**"。 
    
9. 在 "**删除从属存储**" 中，单击 **"确定"**。
    
10. 发布拓扑，检查复制状态，并根据需要运行 Skype for Business 服务器部署向导。 
    

