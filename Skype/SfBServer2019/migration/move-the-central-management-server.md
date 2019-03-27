---
title: 移动中央管理服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 迁移到 Skype for Business Server 2019 之后，您需要将移动中央管理服务器到 Skype 业务 Server 2019 前端服务器或池，然后才能删除旧服务器。
ms.openlocfilehash: dc85548a3c81e55267bc0ed3a32e53860e4bce09
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894745"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>将旧的中央管理服务器移动到 Skype 进行业务服务器 2019

迁移后到 Skype 业务服务器 2019年和可以删除旧服务器之前，您需要将中央管理服务器移动到 Skype，业务 Server 2019 前端服务器或池。 
  
中央管理服务器是单个母版/多副本系统，数据库的读/写副本由前端服务器包含中央管理服务器。 在拓扑中，包括前端服务器包含中央管理服务器，每台计算机都安装过程中的计算机上安装 SQL Server 数据库 （名为默认情况下 RTCLOCAL） 中的中央管理存储数据的只读副本和部署。 本地数据库业务服务器副本复制程序代理的所有计算机上运行作为服务接收通过 Skype 的副本更新。 在中央管理服务器和的本地副本的实际数据库的名称为 XDS，组成 xds.mdf 和 xds.ldf 文件。 服务控制点 (SCP) Active Directory 域服务中被引用的主数据库位置。 中央管理服务器用于管理和配置 Business Server Skype 的所有工具都使用 SCP 查找中央管理存储。
  
您已成功移动中央管理服务器后，您应该从原始前端服务器中删除中央管理服务器数据库。 有关删除中央管理服务器数据库的信息，请参阅[删除前端池的 SQL Server 数据库](remove-the-sql-server-database-for-a-front-end-pool.md)。
  
使用 Windows PowerShell cmdlet 中的业务 Server 命令行管理程序移动 Business Server 2019 SQL Server 数据库的 Skype 的旧安装 SQL Server 数据库的数据库，然后更新 Skype **Move-csmanagementserver**SCP 以指向业务服务器 2019年中央管理服务器位置 Skype。 
  
使用本节中的过程移动中央管理服务器之前准备 Skype 业务 Server 2019 前端服务器。
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>准备 Enterprise Edition 前端池

1. 上要重定位中央管理服务器的业务服务器 2019 Enterprise Edition 前端池的 Skype，登录到计算机的业务 Server 命令行管理程序 Skype **RTCUniversalServerAdmins 成员的安装**组。 此外必须在要安装中央管理存储的数据库具有 SQL Server 数据库的系统管理员用户权限和权限。 
    
2. 打开 Skype 业务 Server 命令行管理程序。
    
3. 若要创建新的中央管理存储中的业务服务器 2019 SQL Server 数据库中的业务 Server Management Shell，Skype Skype 键入：
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. 确认**启动** **Skype 的业务 Server 前端**服务的状态。
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>准备 Standard Edition 前端服务器

1. 上的业务 Server 2019 Standard Edition 前端服务器要重定位中央管理服务器 Skype，登录到计算机的业务 Server 命令行管理程序 Skype **RTCUniversalServerAdmins 成员的安装**组。 
    
2. 打开 Skype 业务 Server 部署向导。
    
3. 在业务 Server 部署向导的 Skype，单击**准备第一个 Standard Edition server**。
    
4. 在**正在执行命令**页上 SQL Server Express 安装为中央管理服务器。 创建必要防火墙规则。 完成数据库和必备软件的安装后，单击**完成**。
    
    > [!NOTE]
    > 在初始安装可能需要一些时间与没有可见的更新对命令输出摘要屏幕。 这是由于安装 SQL Server Express。 如果您需要监视安装数据库，请使用任务管理器监视安装程序。 
  
5. 若要业务服务器 2019 Standard Edition 前端服务器，业务 Server Management Shell，Skype Skype 上创建新的中央管理存储键入： 
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. 确认**启动** **Skype 的业务 Server 前端**服务的状态。
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>将旧的业务服务器 2019年到 Skype 安装中央管理服务器

1. 上将中央管理服务器的业务服务器 2019年服务器 Skype，登录到计算机的业务 Server 命令行管理程序 Skype 以**RTCUniversalServerAdmins**组的成员身份的安装。 您还必须具有 SQL Server 数据库管理员的用户权限和权限。 
    
2. 打开 Skype 业务 Server 命令行管理程序。
    
3. 在业务 Server Management Shell 的 Skype，键入： 
    
   ```
   Enable-CsTopology
   ```

    > [!CAUTION]
    > 如果`Enable-CsTopology`不成功，解决此问题，然后再继续完成阻止此命令。 如果**Enable-cstopology**不成功，移动将失败，它可能导致您的拓扑处于状态没有中央管理存储的位置。 
  
4. 对于业务 Server 2019 前端服务器或前端池中的业务 Server Management Shell，Skype Skype 上键入： 
    
   ```
   Move-CsManagementServer
   ```

5. 业务 Server Management Shell 的 Skype 显示服务器、 文件存储、 数据库存储和当前状态和已建议状态的服务连接点。 仔细阅读信息，并确认这是预期的源和目标。 键入**Y**以继续或**N**停止移动。 
    
6. 查看所有警告或错误**Move-csmanagementserver**命令生成并解决这些问题。 
    
7. 在业务服务器 2019年服务器 Skype，打开业务 Server 部署向导 Skype。 
    
8. Skype 的业务 Server 部署向导，在中，单击**安装或更新 Skype 业务 Server 系统**，单击**步骤 2： 安装或删除业务服务器组件的 Skype**单击**下一步**，查看摘要，然后单击**完成**. 
    
9. 在旧上安装服务器，打开部署向导。 
    
10. Skype 的业务 Server 部署向导，在中，单击**安装或更新 Skype 业务 Server 系统**，单击**步骤 2： 安装或删除业务服务器组件的 Skype**单击**下一步**，查看摘要，然后单击**完成**. 
    
11. 重新启动业务服务器 2019年服务器 Skype。 这是所需由于组成员身份更改中央管理服务器数据库的访问。
    
12. 若要确认新的中央管理存储出现，则在进行复制的业务 Server Management Shell，Skype 键入： 
    
    ```
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > 复制可能需要一些时间来更新当前所有副本。 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>移动后删除旧安装中央管理存储文件

1. 在旧安装服务器上，登录到计算机的业务 Server 命令行管理程序 Skype 以**RTCUniversalServerAdmins**组的成员身份的安装。 您还必须具有 SQL Server 数据库管理员的用户权限和权限。 
    
2. 打开 Skype 业务 Server 命令行管理程序
    
    > [!CAUTION]
    > 请不要继续删除以前的数据库文件之前复制已完成，稳定。 如果删除之前完成复制文件，您将会中断复制过程，并将新移动中央管理服务器保留未知状态。 使用**Get-csmanagementstorereplicationstatus** cmdlet 确认复制状态。 
  
3. 若要从旧安装中央管理服务器中删除中央管理存储数据库文件，请键入：
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    例如：
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    其中_\<FQDN SQL Server\>_ 是任一的传统安装在 Enterprise Edition 部署中或 Standard Edition 服务器的 FQDN 的后端服务器。 
    

