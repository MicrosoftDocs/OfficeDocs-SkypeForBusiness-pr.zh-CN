---
title: 删除监控服务器关联
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
description: 若要删除监视服务器，您需要更改或清除关联的前端池、前端服务器、Survivable 分支设备和 Survivable 分支服务器上的依赖项。 您可以编辑前端池、前端服务器、Survivable 分支设备和 Survivable 分支服务器的属性以删除依赖项。 清除依赖项并在拓扑生成器中删除服务器后，系统会通知拓扑生成器中关联的数据库存储对象也将被删除。
ms.openlocfilehash: dafbeb88773330164a5daf2144988d1afb2776a8
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753414"
---
# <a name="remove-the-monitoring-server-association"></a>删除监控服务器关联

若要删除监视服务器，您需要更改或清除关联的前端池、前端服务器、Survivable 分支设备和 Survivable 分支服务器上的依赖项。 您可以编辑前端池、前端服务器、Survivable 分支设备和 Survivable 分支服务器的属性以删除依赖项。 清除依赖项并在拓扑生成器中删除服务器后，系统会通知拓扑生成器中关联的数据库存储对象也将被删除。
  
### <a name="to-remove-the-monitoring-server-association"></a>删除监控服务器关联

1. 在 Skype for Business Server 2019 前端服务器上，打开拓扑生成器。
    
2. 导航到 "旧版安装" 节点。
    
3. 在拓扑生成器中，展开 " **Enterprise Edition 前端池**"、" **Standard edition 前端服务器**" 或 "**分支站点**"，具体取决于监视服务器的定义位置。
    
4. 如果你有与 Survivable 分支服务器相关联的，请展开 "**分支站点**"，展开分支站点名称，然后展开 " **Survivable 分支设备**"。
    
    > [!NOTE]
    > 用户界面中的**Survivable 分支设备**适用于 Survivable 分支服务器和 Survivable 分支设备。 
  
5. 右键单击与监视服务器关联的池、服务器或设备，然后单击 "**编辑属性**"。
    
6. 在 "**编辑属性**" 中的 "**常规**  >  **关联**" 下，清除 "**关联监视服务器**" 复选框，然后单击 **"确定"**。
    
7. 对与监视服务器关联的任何其他池、服务器或设备重复上一步骤。
    
8. 右键单击监视服务器，然后单击 "**删除**"。 
    
9. 在“删除相关存储”**** 上，单击“确定”****。
    
10. 根据需要发布拓扑、检查复制状态并运行 Skype for Business Server 部署向导。 
    

