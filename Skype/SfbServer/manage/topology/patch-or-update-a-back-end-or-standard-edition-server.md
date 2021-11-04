---
title: 修补或更新后端服务器或Standard Edition服务器Skype for Business Server
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
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 摘要：了解如何在 Skype for Business Server 中的后端服务器上安装更新或Skype for Business Server。
ms.openlocfilehash: 6c2a03358f5fc5f1253f65d1ff2bc202871da678
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60737778"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a>修补或更新后端服务器或Standard Edition服务器Skype for Business Server
 
**摘要：** 了解如何在 Skype for Business Server 中的后端服务器上安装更新或Skype for Business Server。
  
本主题介绍如何在后端服务器或 Enterprise Edition 服务器上安装Standard Edition更新。
  
如果在您升级后端服务器时它至少要停机 30 分钟，则用户可能会进入恢复能力模式。升级完成，且后端服务器又与池中的前端服务器连接后，用户会返回到全部功能。如果升级所用时间少于 30 分钟，将不会对用户造成影响。
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>更新后端服务器或Standard Edition服务器

1. 以 CsAdministrator 角色的成员身份登录到要升级的服务器。
    
2. 下载更新并将其提取到本地硬盘。
    
3. 启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，Skype for Business"，然后单击"Skype for Business Server **命令行管理程序**"。 
    
4. 停止Skype for Business Server服务。 在命令行中键入：
    
    ```PowerShell
    Stop-CsWindowsService
    ```

5. 停止万维网服务。在命令行中键入：
    
    ```PowerShell
    net stop w3svc
   ```

6. 关闭所有Skype for Business Server命令行管理程序窗口。
    
7. 安装该更新。
    
8. 启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，Skype for Business，然后单击"Skype for Business Server **命令行管理程序"。**
    
9. 再次Skype for Business Server服务以捕获 GAC (-d) 全局程序集缓存。 在命令行中键入：
    
    ```PowerShell
    Stop-CsWindowsService
    ```

10. 重新启动万维网服务。在命令行中键入：
    
    ```PowerShell
    net start w3svc
    ```

11. 通过执行以下操作之一SQL Server对数据库应用所做的更改：
    
    - 如果这是一Enterprise Edition后端服务器，并且此服务器上没有并排的数据库（如存档数据库或监控数据库），则命令行中键入以下内容：
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - 如果这是一Enterprise Edition后端服务器，并且此服务器上存在并排的数据库，则命令行中键入以下内容：
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - 如果这是服务器Standard Edition，在命令行中键入以下内容：
    
    ```PowerShell
    Install-CsDatabase -Update -LocalDatabases

    ```
