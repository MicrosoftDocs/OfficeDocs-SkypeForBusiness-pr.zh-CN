---
title: 使用 Skype for Business Server 中的 AlwaysOn 可用性组管理Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 摘要：了解如何向现有 AlwaysOn 可用性组添加更多 Skype for Business Server 数据库，并了解修补或升级属于 Skype for Business Server 中 AlwaysOn 可用性组的一部分的后端服务器后所需的其他步骤。
ms.openlocfilehash: c47d5833b7569faa424415b1e5b7315bab4d4aae
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756989"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a>使用 Skype for Business Server 中的 AlwaysOn 可用性组管理Skype for Business Server

使用本文中的步骤向 Skype for Business Server 中的现有 AlwaysOn 可用性组添加更多 Skype for Business Server 数据库，并查找在修补或升级作为 Skype for Business Server 中 AlwaysOn 可用性组的一部分的后端服务器后所需的附加步骤。

## <a name="add-databases-to-an-alwayson-availability-group"></a>将数据库添加到 AlwaysOn 可用性组 

1. 打开SQL Server Management Studio，然后导航到 AlwaysOn 可用性组。 故障转移到主副本。
    
2. 在拓扑生成器中，SQL Server AlwaysOn 可用性组的 FQDN 设置为该组的主节点的 FQDN。
    
   - 打开拓扑生成器，选择 **"从现有部署下载拓扑"，** 然后单击"确定 **"。**
    
   - 展开Skype for Business Server，展开拓扑，然后展开SQL Server **Stores"**。 右键单击SQL AlwaysOn 可用性组的新存储，然后单击编辑 **属性**。
    
   - 在页面底部的"SQL Server **FQDN"** 框中，键入 AlwaysOn 可用性组的主节点的 FQDN。
    
3. 发布拓扑。 从"**操作"菜单中**，单击 **"拓扑"，** 然后单击"**发布"。** 然后在确认页中，单击"下一 **步"。**
    
4. 使用 SQL Server Management Studio将新数据库添加到 AlwaysOn 可用性组。
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a>修补或更新SQL Server AlwaysOn 可用性组

修补属于 AlwaysOn 可用性组的后端服务器后，必须重新发布拓扑。

1. 在服务器或服务器上Skype for Business更新。
    
2. 在 Skype for Business 命令行管理程序 (中运行以下 PowerShell 命令，该帐户使用适当权限将更改应用于 SQL AlwaysOn 数据库) 如下所示：
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    其中 ，[sqlpool.contoso.com] 替换为 AlwaysOn 可用性组的完全限定 (FQDN) FQDN。
