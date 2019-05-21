---
title: 删除存档服务器关联
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 若要删除存档服务器, 你需要更改或清除关联的前端池、前端服务器、Survivable 分支设备和 Survivable 分支服务器上的依赖关系。 编辑前端池、前端服务器、Survivable 分支装置和 Survivable 分支服务器的属性以删除相关性。 清除相关性并在拓扑生成器中删除服务器后, 系统会通知你拓扑生成器中的相关数据库存储对象也将被删除。
ms.openlocfilehash: 52bba22f678bb4aee1ce406613ce19bb686a78c4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301109"
---
# <a name="remove-the-archiving-server-association"></a>删除存档服务器关联

若要删除存档服务器, 你需要更改或清除关联的前端池、前端服务器、Survivable 分支装置和 Survivable 分支服务器上的依赖关系。 编辑 "前端池"、"前端服务器"、"Survivable 分支" 装置和 "Survivable 分支服务器" 的属性以删除相关性。 清除相关性并在拓扑生成器中删除服务器后, 系统会通知你拓扑生成器中关联的数据库存储对象也将被删除。
  
### <a name="to-remove-the-archiving-server-association"></a>删除存档服务器关联

1. 在 Skype for Business 服务器2019前端服务器上, 打开拓扑生成器。
    
2. 导航到 "旧版安装" 节点。
    
3. 在拓扑生成器中, 展开 "**企业版前端池**"、"**标准版前端服务器**" 或 "**分支站点**", 具体取决于定义存档服务器的位置。
    
4. 如果您有关联的 Survivable 分支服务器, 请展开 "**分支站点**", 展开 "分支站点名称", 然后展开 "**分支机构" Survivable**。
    
    > [!NOTE]
    > 用户界面中的**Survivable 分支装置**适用于 Survivable 分支服务器和 Survivable 分支装置。 
  
5. 右键单击与存档服务器相关联的池、服务器或设备, 然后单击 "**编辑属性**"。
    
6. 在 "**编辑属性**" 下的 "**常规** > **关联**" 下, 清除 "**关联存档服务器**" 复选框, 然后单击 **"确定"**。
    
7. 对与要删除的存档服务器关联的任何其他池、服务器或设备重复上一步骤。
    
8. 右键单击存档服务器, 然后单击 "**删除**"。
    
9. 在 "**删除从属存储**" 中, 单击 **"确定"**。
    
10. 发布拓扑, 检查复制状态, 然后根据需要运行 Skype for Business 服务器部署向导。 
    

