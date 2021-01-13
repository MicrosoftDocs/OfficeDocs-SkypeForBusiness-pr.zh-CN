---
title: 在 Skype for Business Server 中修补或更新后端服务器或 Standard Edition Server
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
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 摘要：了解如何在 Skype for Business Server 的后端服务器上安装更新或修补程序。
ms.openlocfilehash: 3e5e0cda1604f3144e853cfa3bf7bcc45e7d0c2f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826302"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a>在 Skype for Business Server 中修补或更新后端服务器或 Standard Edition Server
 
**摘要：** 了解如何在 Skype for Business Server 的后端服务器上安装更新或修补程序。
  
本主题介绍如何在 Enterprise Edition 后端服务器或 Standard Edition 服务器上安装更新。
  
如果在您升级后端服务器时它至少要停机 30 分钟，则用户可能会进入恢复能力模式。升级完成，且后端服务器又与池中的前端服务器连接后，用户会返回到全部功能。如果升级所用时间少于 30 分钟，将不会对用户造成影响。
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>更新后端服务器或 Standard Edition Server

1. 以 CsAdministrator 角色的成员身份登录到要升级的服务器。
    
2. 下载更新并将其提取到本地硬盘。
    
3. 启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，单击 **"Skype for Business"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**
    
4. 停止 Skype for Business Server 服务。 在命令行中键入：
    
    ```PowerShell
    Stop-CsWindowsService
    ```

5. 停止万维网服务。 在命令行中键入：
    
    ```PowerShell
    net stop w3svc
   ```

6. 关闭所有 Skype for Business Server 命令行管理程序窗口。
    
7. 安装该更新。
    
8. 启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，单击 **"Skype for Business"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**
    
9. 再次停止 Skype for Business Server 服务，以捕获 GAC (程序集) 全局程序集缓存。 在命令行中键入：
    
    ```PowerShell
    Stop-CsWindowsService
    ```

10. 重新启动万维网服务。 在命令行中键入：
    
    ```PowerShell
    net start w3svc
    ```

11. 通过执行以下操作之SQL Server对数据库应用所做的更改：
    
    - 如果这是 Enterprise Edition 后端服务器，并且此服务器上没有并排的数据库（如存档数据库或监控数据库），则命令行中键入以下内容：
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - 如果这是 Enterprise Edition 后端服务器，并且此服务器上存在并排的数据库，则命令行中键入以下内容：
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - 如果这是 Standard Edition Server，在命令行中键入以下内容：
    
    ```PowerShell
    Install-CsDatabase -Update -LocalDatabases

    ```
