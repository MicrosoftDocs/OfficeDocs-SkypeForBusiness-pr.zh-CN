---
title: 在 Skype for Business Server 中使用 AlwaysOn 可用性组管理数据库
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 摘要：了解如何向现有 AlwaysOn 可用性组添加更多 Skype for Business Server 数据库，并了解修补或升级作为 Skype for Business Server 中 AlwaysOn 可用性组的一部分的后端服务器后所需的附加步骤。
ms.openlocfilehash: 444194c9cda5f4c3f82e6f3f7698395dce1a5d07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826362"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a>在 Skype for Business Server 中使用 AlwaysOn 可用性组管理数据库

使用本文中的步骤将更多 Skype for Business Server 数据库添加到 Skype for Business Server 中的现有 AlwaysOn 可用性组，并查找在修补或升级作为 Skype for Business Server 中 AlwaysOn 可用性组的一部分的后端服务器后所需的附加步骤。

## <a name="add-databases-to-an-alwayson-availability-group"></a>将数据库添加到 AlwaysOn 可用性组 

1. 打开 SQL Server Management Studio，然后导航到 AlwaysOn 可用性组。 故障转移到主副本。
    
2. 在拓扑生成器中，SQL Server AlwaysOn 可用性组的 FQDN 设置为该组的主节点的 FQDN。
    
   - 打开拓扑生成器，从现有 **部署** 中选择"下载拓扑"，然后单击"**确定"。**
    
   - 展开 Skype for Business Server、扩展拓扑和SQL Server **应用商店**。 右键单击SQL AlwaysOn 可用性组的新存储，然后单击"**编辑属性"。**
    
   - 在页面底部的 **"FQDN** SQL Server框中，键入 AlwaysOn 可用性组的主节点的 FQDN。
    
3. 发布拓扑。 从" **操作"** 菜单中，单击 **"拓扑** "，然后 **发布**。 然后在确认页中单击"下一 **步"。**
    
4. 使用 SQL Server Management Studio 将新数据库添加到 AlwaysOn 可用性组。
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a>修补或更新SQL Server AlwaysOn 可用性组

修补属于 AlwaysOn 可用性组的后端服务器后，必须重新发布拓扑。

1. 在 Skype for Business 服务器或服务器上安装更新。
    
2. 使用适当权限的帐户登录的 Skype for Business 命令行管理程序 (中运行以下 PowerShell 命令，以将更改应用到 SQL AlwaysOn 数据库) 如下所示：
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    其中 ，[sqlpool.contoso.com] 替换为 AlwaysOn 可用性 (FQDN) 的完全限定域名。
