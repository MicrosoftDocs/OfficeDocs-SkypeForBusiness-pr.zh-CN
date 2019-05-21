---
title: 移动中央管理服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 迁移到 Skype for business Server 2019 后, 您需要将中央管理服务器移动到 Skype for business 服务器2019前端服务器或池, 然后才能删除旧服务器。
ms.openlocfilehash: 5e16145b6695a9ee7006ab7d5321af9e478d7c37
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291296"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>将旧式中央管理服务器移动到 Skype for business Server 2019

迁移到 Skype for Business Server 2019 后, 在删除旧服务器之前, 需要将中央管理服务器移动到 Skype for business 服务器2019前端服务器或池。 
  
中央管理服务器是单个主/多副本系统, 其中数据库的读/写副本由包含中央管理服务器的前端服务器保留。 拓扑中的每台计算机 (包括包含中央管理服务器的前端服务器) 在安装期间, 在计算机上安装了 SQL Server 数据库中的中央管理存储数据的只读副本 (默认情况下称为 RTCLOCAL)。部署. 本地数据库通过在所有计算机上作为服务运行的 Skype for Business Server 副本复制程序代理来接收副本更新。 中央管理服务器和本地副本上的实际数据库的名称是 XDS, 它由 XDS 和 XDS 文件组成。 Master 数据库位置由 Active Directory 域服务中的服务控制点 (SCP) 引用。 使用中心管理服务器管理和配置 Skype for Business 服务器的所有工具均使用 SCP 查找中央管理存储。
  
成功移动中央管理服务器后, 应从原始前端服务器中删除中央管理服务器数据库。 有关删除中央管理服务器数据库的信息, 请参阅[删除前端池的 SQL Server 数据库](remove-the-sql-server-database-for-a-front-end-pool.md)。
  
在 Skype for Business Server Management Shell 中使用 Windows PowerShell cmdlet **Move CsManagementServer** , 将数据库从旧版安装 SQL server 数据库移动到 Skype For business SERVER 2019 SQL server 数据库, 然后更新SCP 指向 Skype for Business Server 2019 中央管理服务器位置。 
  
在移动中央管理服务器之前, 使用本部分中的步骤准备 Skype for business Server 2019 前端服务器。
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>准备企业版前端池

1. 在要在其中重新定位中央管理服务器的 Skype for Business 服务器2019企业版前端池上, 登录到安装了 Skype for business Server Management Shell 的计算机作为 RTCUniversalServerAdmins 的成员。 **** 组。 你还必须在要安装中央管理存储的数据库上同时拥有 SQL Server 数据库 sysadmin 用户权限和权限。 
    
2. 打开 Skype for Business 服务器命令行管理程序。
    
3. 若要在 Skype for business Server 2019 SQL Server 数据库中创建新的中央管理存储, 请在 Skype for business Server Management Shell 中键入:
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. 确认**已启动** **Skype For business Server 前端**服务的状态。
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>准备标准版前端服务器

1. 在要在其中重新定位中央管理服务器的 Skype for Business Server 2019 标准版前端服务器上, 登录到安装了 Skype for business Server Management Shell 的计算机作为 RTCUniversalServerAdmins 的成员。 **** 组。 
    
2. 打开 Skype for Business 服务器部署向导。
    
3. 在 "Skype for Business 服务器部署" 向导中, 单击 "**准备第一个标准版服务器**"。
    
4. 在 "**执行命令**" 页面上, 将 SQL Server Express 作为中央管理服务器进行安装。 已创建必要的防火墙规则。 当数据库和必备软件的安装完成后, 单击 "**完成**"。
    
    > [!NOTE]
    > 初始安装可能需要一些时间, 但不显示命令输出摘要屏幕的更新。 这是由于 SQL Server Express 的安装所致。 如果需要监视数据库的安装, 请使用 "任务管理器" 监视设置。 
  
5. 若要在 Skype for business Server 2019 标准版前端服务器上创建新的中央管理存储, 请在 Skype for business Server Management Shell 中键入: 
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. 确认**已启动** **Skype For business Server 前端**服务的状态。
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>将旧式安装中央管理服务器移动到 Skype for business Server 2019

1. 在将成为中央管理服务器的 Skype for Business Server 2019 服务器上, 登录到安装了 Skype for business 服务器管理外壳的计算机作为**RTCUniversalServerAdmins**组的成员。 您还必须拥有 SQL Server 数据库管理员用户的权限。 
    
2. 打开 Skype for Business Server 命令行管理程序。
    
3. 在 Skype for Business 服务器命令行管理程序中, 键入: 
    
   ```
   Enable-CsTopology
   ```

    > [!CAUTION]
    > 如果`Enable-CsTopology`未成功, 请解决阻止命令完成的问题, 然后再继续。 如果**Enable-CsTopology**未成功, 则移动将失败, 并且可能会将拓扑置于没有中央管理存储的状态。 
  
4. 在 skype for business Server 2019 前端服务器或前端池的 Skype for business 服务器管理外壳中, 键入: 
    
   ```
   Move-CsManagementServer
   ```

5. Skype for Business 服务器管理外壳显示当前状态和建议状态的服务器、文件存储、数据库存储和服务连接点。 请仔细阅读信息, 确认这是预期的源和目标。 键入**Y**继续, 或按**N**停止移动。 
    
6. 查看由**CsManagementServer**命令生成并解决的任何警告或错误。 
    
7. 在 Skype for business Server 2019 服务器上, 打开 "Skype for Business 服务器部署" 向导。 
    
8. 在 "Skype for Business 服务器部署向导" 中, 单击 "**安装或更新 skype for Business 服务器系统**", 单击 "**步骤 2: 设置" 或 "删除 Skype for Business 服务器" 组件**, 单击 "**下一步**", 查看摘要, 然后单击 "**完成"**. 
    
9. 在旧版安装服务器上, 打开 "部署向导"。 
    
10. 在 "Skype for Business 服务器部署向导" 中, 单击 "**安装或更新 skype for Business 服务器系统**", 单击 "**步骤 2: 设置" 或 "删除 Skype for Business 服务器" 组件**, 单击 "**下一步**", 查看摘要, 然后单击 "**完成"**. 
    
11. 重新启动 Skype for Business Server 2019 服务器。 这是必需的, 因为访问中央管理服务器数据库的组成员身份发生更改。
    
12. 若要确认与新的中央管理存储进行复制, 请在 Skype for business Server Management Shell 中键入: 
    
    ```
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > 复制可能需要一些时间来更新所有当前副本。 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>移动后删除旧版安装中央管理存储文件

1. 在旧版安装服务器上, 登录到安装了 Skype for Business 服务器管理外壳的计算机作为**RTCUniversalServerAdmins**组的成员。 您还必须拥有 SQL Server 数据库管理员用户的权限。 
    
2. 打开 Skype for Business 服务器命令行管理程序
    
    > [!CAUTION]
    > 在复制完成且稳定之前, 不要继续删除以前的数据库文件。 如果在完成复制之前删除文件, 将中断复制过程, 并使新移动的中央管理服务器处于未知状态。 使用 cmdlet **CsManagementStoreReplicationStatus**确认复制状态。 
  
3. 若要从旧版安装中央管理服务器中删除中央管理存储数据库文件, 请键入:
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    例如：
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    _ \<SQL Server\>的 FQDN_是企业版部署中的旧安装后端服务器或标准版服务器的 fqdn。 
    

