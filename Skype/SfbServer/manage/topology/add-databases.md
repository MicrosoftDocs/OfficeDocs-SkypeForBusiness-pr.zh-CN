---
title: 将数据库添加到在 Skype AlwaysOn 可用性组业务服务器 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/30/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 摘要： 了解如何可以为业务服务器 2015 Skype 中现有的 AlwaysOn 可用性组添加更多 Skype 业务服务器数据库。
ms.openlocfilehash: 31678d6cc374ecdbe40d2fdf3039905176c0178d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-databases-to-an-alwayson-availability-group-in-skype-for-business-server-2015"></a>将数据库添加到在 Skype AlwaysOn 可用性组业务服务器 2015
 
**摘要：**了解如何可以为业务服务器 2015 Skype 中现有的 AlwaysOn 可用性组添加更多 Skype 业务服务器数据库。
  
### <a name="adding-databases-to-an-alwayson-availability-group"></a>将数据库添加到 AlwaysOn 可用性组

1. 打开 SQL Server 管理 Studio，然后定位到 AlwaysOn 可用性组。 对主复制副本故障切换。
    
2. 拓扑生成器中设置到该组的主要节点的 FQDN 的 AlwaysOn 可用性组 SQL Server FQDN。
    
  - 打开拓扑生成器、 选择**下载从现有部署的拓扑结构**，并单击**确定**。
    
  - 依次展开 Skype for Business Server、你的拓扑，以及“**SQL Server 存储**”。 右键单击 SQL 存储新 AlwaysOn 可用性组，并单击**编辑属性**。
    
  - 底部的页的**SQL Server FQDN**框中，键入 AlwaysOn 可用性组的主节点的 FQDN。
    
3. 发布拓扑。从“**操作**”菜单中，单击“**拓扑**”，然后单击“**发布**”。然后在确认页中，单击“**下一步**”。
    
4. 使用 SQL Server 管理 Studio AlwaysOn 可用性组中添加新的数据库。
    

