---
title: 管理数据库中 Skype AlwaysOn 可用性组与企业服务器 （英文）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 摘要： 了解如何将多个 Skype Business Server 数据库添加到现有 AlwaysOn 可用性组，以及了解所需的其他步骤后您修补程序或升级后端服务器中的 Skype 的 AlwaysOn 可用性组的一部分业务服务器。
ms.openlocfilehash: 07aaadc303063204cef4a5561a83ec71b629c21b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911929"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a>管理数据库中 Skype AlwaysOn 可用性组与企业服务器 （英文）

使用本文中的步骤业务服务器添加到 Skype 中现有的 AlwaysOn 可用性组的详细 Skype 业务服务器数据库并修补程序或升级后端服务器属于 AlwaysOn 后找出有关所需的其他步骤Skype 业务服务器中的可用性组。

## <a name="add-databases-to-an-alwayson-availability-group"></a>将数据库添加到 AlwaysOn 可用性组 

1. 打开 SQL Server Management Studio，并导航到 AlwaysOn 可用性组。 其进行故障转移到主副本。
    
2. 在拓扑生成器中，AlwaysOn 可用性组的 SQL Server FQDN 设置到该组的主节点的 FQDN。
    
   - 打开拓扑生成器，选择**下载从现有部署的拓扑**，然后单击**确定**。
    
   - 依次展开 Skype for Business Server、你的拓扑，以及“**SQL Server 存储**”。 右键单击新 AlwaysOn 可用性组的 SQL 存储，然后单击**编辑属性**。
    
   - 底部的页上，在**SQL Server FQDN**框中，键入 AlwaysOn 可用性组的主节点的 FQDN。
    
3. 发布拓扑。 从“**操作**”菜单中，单击“**拓扑**”，然后单击“**发布**”。 在确认页上，单击“**下一步**”。
    
4. 使用 SQL Server Management Studio 将新数据库添加到 AlwaysOn 可用性组。
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a>修补或更新 AlwaysOn 可用性组中的 SQL Server

修补后端服务器 AlwaysOn 可用性组的一部分后, 必须重新发布拓扑。

1. 在你的一台或多台 Skype for Business 服务器上安装更新。
    
2. 在 Skype for Business 命令行管理程序中运行以下 PowerShell 命令（用被授予适当权限可向 SQL AlwaysOn 数据库应用更改的帐户登录），如下所述：
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    其中，[sqlpool.contoso.com] 被替换为 AlwaysOn 可用性组的完全限定域名 (FQDN)。
