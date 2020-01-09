---
title: 在 Skype for Business Server 中使用 "AlwaysOn 可用性" 组管理数据库
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 摘要：了解如何将更多 Skype for business 服务器数据库添加到现有 AlwaysOn 可用性组，并了解在修补或升级作为 Skype for AlwaysOn 可用性组一部分的后端服务器后所需的附加步骤企业服务器。
ms.openlocfilehash: 221964eb7d8dfcbb0303a0e1148de4fcef6cec51
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991537"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a>在 Skype for Business Server 中使用 "AlwaysOn 可用性" 组管理数据库

使用本文中的步骤将更多 Skype for business 服务器数据库添加到 Skype for Business Server 中的现有 AlwaysOn 可用性组，并在修补或升级属于 AlwaysOn 的后端服务器后了解必要的附加步骤Skype for Business 服务器中的 "可用性" 组。

## <a name="add-databases-to-an-alwayson-availability-group"></a>将数据库添加到 AlwaysOn 可用性组 

1. 打开 SQL Server Management Studio，然后导航到 "AlwaysOn 可用性" 组。 将其故障转移到主副本。
    
2. 在拓扑生成器中，将 "AlwaysOn 可用性" 组的 SQL Server FQDN 设置为该组的主节点的 FQDN。
    
   - 打开拓扑生成器，**从现有部署**中选择 "下载拓扑"，然后单击 **"确定"**。
    
   - 依次展开 Skype for Business Server、你的拓扑，以及“**SQL Server 存储**”。 右键单击新的 "AlwaysOn 可用性" 组的 SQL 应用商店，然后单击 "**编辑属性**"。
    
   - 在页面底部的 " **SQL SERVER FQDN** " 框中，键入 AlwaysOn 可用性组的主节点的 FQDN。
    
3. 发布拓扑。 从“**操作**”菜单中，单击“**拓扑**”，然后单击“**发布**”。 在确认页上，单击“**下一步**”。
    
4. 使用 SQL Server Management Studio 将新数据库添加到 "AlwaysOn 可用性" 组。
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a>修补或更新 AlwaysOn 可用性组中的 SQL Server

在修补属于 AlwaysOn 可用性组的后端服务器之后，必须重新发布拓扑。

1. 在你的一台或多台 Skype for Business 服务器上安装更新。
    
2. 在 Skype for Business 命令行管理程序中运行以下 PowerShell 命令（用被授予适当权限可向 SQL AlwaysOn 数据库应用更改的帐户登录），如下所述：
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    其中，[sqlpool.contoso.com] 被替换为 AlwaysOn 可用性组的完全限定域名 (FQDN)。
