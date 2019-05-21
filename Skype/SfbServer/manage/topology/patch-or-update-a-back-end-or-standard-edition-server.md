---
title: 在 Skype for Business 服务器中修补或更新后端服务器或标准版服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: '摘要: 了解如何在 Skype for Business 服务器的后端服务器上安装更新或修补程序。'
ms.openlocfilehash: b8a0280577147e37c52ab11aa3061541bae27610
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275120"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a>在 Skype for Business 服务器中修补或更新后端服务器或标准版服务器
 
**摘要:** 了解如何在 Skype for Business 服务器的后端服务器上安装更新或修补程序。
  
本主题介绍如何在企业版后端服务器或标准版服务器上安装更新。
  
如果后端服务器在升级后至少30分钟, 则用户可能会进入恢复模式。 升级完成且后端服务器再次与池中的前端服务器连接时, 用户将返回到完整功能。 如果升级所用时间少于 30 分钟，则用户不会受到影响。
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>更新后端服务器或 Standard Edition Server

1. 以 CsAdministrator 角色的成员身份登录到要升级的服务器。
    
2. 下载更新并将其提取到本地硬盘。
    
3. 启动 Skype for Business 服务器命令行管理程序: 单击 "**开始**", 单击 "**所有程序**", 单击 " **skype**for Business", 然后单击 " **skype for business 服务器管理外壳程序**"。
    
4. 停止 Skype for Business 服务器服务。 在命令行中键入：
    
    ```
    Stop-CsWindowsService
    ```

5. 停止万维网服务。 在命令行中键入：
    
    ```
    net stop w3svc
   ```

6. 关闭所有 Skype for Business 服务器管理外壳程序窗口。
    
7. 安装该更新。
    
8. 启动 Skype for Business 服务器命令行管理程序: 单击 "**开始**", 单击 "**所有程序**", 单击 " **skype**for Business", 然后单击 " **skype for business 服务器管理外壳**"。
    
9. 再次停止 Skype for Business 服务器服务以捕获全局程序集缓存 (GAC)-d 程序集。 在命令行中键入：
    
    ```
    Stop-CsWindowsService
    ```

10. 重新启动万维网服务。在命令行中键入：
    
    ```
    net start w3svc
    ```

11. 执行以下操作之一，将所做更改应用于 SQL Server 数据库：
    
    - 如果这是企业版后端服务器, 并且此服务器上没有 collocated 数据库 (如 "存档" 或 "监视数据库"), 请在命令行中键入以下内容:
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - 如果这是企业版后端服务器, 并且此服务器上有 collocated 数据库, 请在命令行中键入以下内容:
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - 如果这是标准版服务器, 请在命令行键入以下命令:
    
    ```
    Install-CsDatabase -Update -LocalDatabases

    ```
