---
title: 修补或更新 Skype for Business Server 2015 中的后端服务器或 Standard Edition Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 摘要： 了解如何在 Skype 在后端服务器上的业务服务器安装更新程序或修补程序。
ms.openlocfilehash: 14acff1aea501bf47dff95053259187570d2f990
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server-2015"></a>修补或更新 Skype for Business Server 2015 中的后端服务器或 Standard Edition Server
 
**摘要：**了解如何在 Skype 在后端服务器上的业务服务器安装更新程序或修补程序。
  
本主题介绍如何安装企业版后端服务器或标准版服务器上的更新。
  
如果后端服务器已关闭至少 30 分钟而对其进行升级，用户可能然后进入恢复模式。 在完成升级后端服务器已重新连接与前端服务器的池中，用户返回到完整功能。 如果升级所用时间少于 30 分钟，则用户不会受到影响。
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>更新后端服务器或 Standard Edition Server

1. 以 CsAdministrator 角色的成员身份登录到要升级的服务器。
    
2. 下载更新并将其提取到本地硬盘。
    
3. 为业务服务器管理外壳程序启动 Skype： 单击**开始**，单击**所有程序**，都单击**业务 2015年的 Skype**，然后都单击**业务服务器管理外壳的 Skype**。.
    
4. 停止业务服务器服务 Skype。 在命令行中键入：
    
    ```
    Stop-CsWindowsService
    ```

5. 停止万维网服务。在命令行中键入：
    
    ```
    net stop w3svc
   ```

6. 关闭所有 Skype 业务服务器管理外壳程序窗口。
    
7. 安装该更新。
    
8. 为业务服务器管理外壳程序启动 Skype： 单击**开始**，单击**所有程序**，都单击**业务 2015年的 Skype**，然后都单击**业务服务器管理外壳的 Skype**。.
    
9. 停止业务服务器服务 Skype，再次以捕捉全局程序集缓存 (GAC)-d 程序集。 在命令行中键入：
    
    ```
    Stop-CsWindowsService
    ```

10. 重新启动万维网服务。在命令行中键入：
    
    ```
    net start w3svc
    ```

11. 执行以下操作之一，将所做更改应用于 SQL Server 数据库：
    
    - 如果这是企业版后端服务器，并且没有按顺序排列在此服务器上，如存档数据库或监视数据库，然后键入以下命令的命令行：
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - 如果这是企业版后端服务器，此服务器上没有按顺序排列的数据库，然后键入以下命令的命令行：
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - 如果这是一个标准版的服务器，请在命令行键入以下：
    
    ```
    Install-CsDatabase -Update -LocalDatabases

    ```


