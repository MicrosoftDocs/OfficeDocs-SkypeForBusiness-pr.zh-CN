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
ms.localizationpriority: medium
description: 若要删除监控服务器，您需要更改或清除关联前端池、前端服务器、Survivable Branch Appliance 和 Survivable Branch Server 的依赖项。 编辑前端池、前端服务器、Survivable Branch Appliance 和 Survivable Branch Server 的属性以删除依赖项。 在拓扑生成器中清除依赖关系并删除服务器后，将会收到通知，拓扑生成器中的关联数据库存储对象也将被删除。
ms.openlocfilehash: 703fbfa68fe75d4e8c4a297c81eae27b0f5118c5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58590586"
---
# <a name="remove-the-monitoring-server-association"></a>删除监控服务器关联

若要删除监控服务器，您需要更改或清除关联前端池、前端服务器、Survivable Branch Appliance 和 Survivable Branch Server 的依赖项。 编辑前端池、前端服务器、Survivable Branch Appliance 和 Survivable Branch Server 的属性以删除依赖项。 在拓扑生成器中清除依赖关系并删除服务器后，将会收到通知，拓扑生成器中的关联数据库存储对象也将被删除。
  
### <a name="to-remove-the-monitoring-server-association"></a>删除监控服务器关联

1. 在 Skype for Business Server 2019 前端服务器上，打开拓扑生成器。
    
2. 导航到旧安装节点。
    
3. 在拓扑生成器中，Enterprise Edition前端池、Standard Edition **前端服务器** 或分支站点，具体取决于定义监控服务器的地方。 
    
4. 如果关联了 Survivable Branch Server，请展开"分支站点"，展开"分支站点名称"，然后展开 **"Survivable Branch 设备"。**
    
    > [!NOTE]
    > **用户界面中的 Survivable Branch Appliance** 适用于 Survivable Branch Server 和 Survivable Branch Appliance。 
  
5. 右键单击与监控服务器关联的池、服务器或设备，然后单击"编辑 **属性"。**
    
6. 在 **"编辑属性**"中的"**常规**  >  **关联"下**，清除"关联 **监控服务器**"复选框，然后单击"确定 **"。**
    
7. 对与监控服务器关联的任何其他池、服务器或设备重复上一步。
    
8. 右键单击监控服务器，然后单击"删除 **"。** 
    
9. 在“删除相关存储”上，单击“确定”。
    
10. 发布拓扑、检查复制状态，并根据需要Skype for Business Server部署向导。 
    

