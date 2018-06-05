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
description: 摘要： 了解如何为业务服务器中 Skype 后端服务器上安装更新或修补程序。
ms.openlocfilehash: 40437deb77fc5b212a6c579030ed77939c421050
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569377"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server-2015"></a>修补或更新 Skype for Business Server 2015 中的后端服务器或 Standard Edition Server
 
**摘要：** 了解如何为业务服务器中 Skype 后端服务器上安装更新或修补程序。
  
本主题介绍如何在 Enterprise Edition 后端服务器或 Standard Edition server 上安装更新。
  
如果后端服务器已关闭至少 30 分钟内将对其进行升级时，用户可能然后转到恢复能力模式。 当升级完成和后端服务器再次已连接具有池中前端服务器时，用户将返回完整功能。 如果升级所用时间少于 30 分钟，则用户不会受到影响。
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>更新后端服务器或 Standard Edition Server

1. 以 CsAdministrator 角色的成员身份登录到要升级的服务器。
    
2. 下载更新并将其提取到本地硬盘。
    
3. 为业务 Server 命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**、 都单击**业务 2015年的 Skype**，，然后都单击**业务 Server Management Shell 的 Skype**正在
    
4. 停止 Skype 业务服务器服务。 在命令行中键入：
    
    ```
    Stop-CsWindowsService
    ```

5. 停止万维网服务。在命令行中键入：
    
    ```
    net stop w3svc
   ```

6. 关闭所有 Skype 业务 Server Management Shell windows。
    
7. 安装该更新。
    
8. 为业务 Server 命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**、 都单击**业务 2015年的 Skype**，，然后都单击**业务 Server Management Shell 的 Skype**正在
    
9. 停止对业务 Server 服务的 Skype 再次以捕获-d 全局程序集缓存 (GAC) 的程序集。 在命令行中键入：
    
    ```
    Stop-CsWindowsService
    ```

10. 重新启动万维网服务。在命令行中键入：
    
    ```
    net start w3svc
    ```

11. 执行以下操作之一，将所做更改应用于 SQL Server 数据库：
    
    - 如果这是 Enterprise Edition 后端服务器，并且没有并置在此服务器上，如存档数据库或监控数据库，然后键入以下命令行：
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - 如果这是 Enterprise Edition 后端服务器，并且此服务器上没有并置的数据库，然后键入以下命令行：
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - 如果这是 Standard Edition 服务器，请键入以下命令行：
    
    ```
    Install-CsDatabase -Update -LocalDatabases

    ```