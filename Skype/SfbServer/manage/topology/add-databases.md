---
title: 将数据库添加到 AlwaysOn 可用性组中 Skype，业务服务器
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 摘要： 了解如何将多个 Skype 业务服务器数据库添加到 Skype 中现有的 AlwaysOn 可用性组，业务服务器。
ms.openlocfilehash: e5217ba16234ea96f205d8ee89b6d31ac6b2df6c
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372058"
---
# <a name="add-databases-to-an-alwayson-availability-group-in-skype-for-business-server"></a>将数据库添加到 AlwaysOn 可用性组中 Skype，业务服务器
 
**摘要：** 了解如何为业务服务器到 Skype 中现有的 AlwaysOn 可用性组添加业务服务器数据库的详细 Skype。
  
### <a name="adding-databases-to-an-alwayson-availability-group"></a>将数据库添加到 AlwaysOn 可用性组

1. 打开 SQL Server Management Studio，并导航到 AlwaysOn 可用性组。 其进行故障转移到主副本。
    
2. 在拓扑生成器中，AlwaysOn 可用性组的 SQL Server FQDN 设置到该组的主节点的 FQDN。
    
   - 打开拓扑生成器，选择**下载从现有部署的拓扑**，然后单击**确定**。
    
   - 依次展开 Skype for Business Server、你的拓扑，以及“**SQL Server 存储**”。 右键单击新 AlwaysOn 可用性组的 SQL 存储，然后单击**编辑属性**。
    
   - 底部的页上，在**SQL Server FQDN**框中，键入 AlwaysOn 可用性组的主节点的 FQDN。
    
3. 发布拓扑。从“**操作**”菜单中，单击“**拓扑**”，然后单击“**发布**”。然后在确认页中，单击“**下一步**”。
    
4. 使用 SQL Server Management Studio 将新数据库添加到 AlwaysOn 可用性组。
    

