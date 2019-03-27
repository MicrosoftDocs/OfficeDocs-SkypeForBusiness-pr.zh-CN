---
title: 删除存档服务器关联
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 若要删除某个存档服务器，您需要更改或清除关联前端池，前端服务器、 Survivable Branch Appliance 和 Survivable Branch Server 上的相关性。 编辑前端服务器、 Survivable Branch Appliance 和 Survivable Branch Server 中删除依赖关系前端池的属性。 清除依赖项并删除拓扑生成器中的服务器后，将通知您在拓扑生成器中的关联的数据库存储对象也将被删除。
ms.openlocfilehash: 15e6b33decb11ce7ed4550b0d84cc346a0baf073
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884398"
---
# <a name="remove-the-archiving-server-association"></a>删除存档服务器关联

若要删除某个存档服务器，您需要更改或清除关联前端池、 前端服务器、 Survivable Branch Appliance 和 Survivable Branch Server 上的相关性。 编辑前端池、 前端服务器、 Survivable Branch Appliance 和 Survivable Branch Server 中删除依赖关系的属性。 清除依赖关系和删除拓扑生成器中的服务器后，将通知您在拓扑生成器中的关联的数据库存储对象也将被删除。
  
### <a name="to-remove-the-archiving-server-association"></a>删除存档服务器关联

1. 在业务 Server 2019 前端服务器的 Skype，打开拓扑生成器。
    
2. 导航到旧的安装节点。
    
3. 在拓扑生成器中，根据定义存档服务器的位置展开**Enterprise Edition 前端池**、 **Standard Edition 前端服务器**或**分支站点**。
    
4. 如果您有关联的 Survivable Branch Server，展开**分支站点**，展开分支站点名称，，然后展开**Survivable Branch Appliance**。
    
    > [!NOTE]
    > 用户界面中的**survivable Branch Appliance**适用于 Survivable Branch Appliance 和 Survivable Branch Server。 
  
5. 右键单击池、 服务器或存档服务器，与相关联的设备，然后单击**编辑属性**。
    
6. 在**编辑属性**在**常规**下 > **关联**，清除**关联存档服务器**复选框，然后单击**确定**。
    
7. 对任何其他池、 服务器或与您要删除存档服务器相关联的设备重复上一步。
    
8. 右键单击存档服务器，，，然后单击**删除**。
    
9. 在**删除相关存储**，单击**确定**。
    
10. 发布拓扑，检查复制状态，并根据需要业务 Server 部署向导运行 Skype。 
    

