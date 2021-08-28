---
title: 移动中央管理服务器
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 迁移到 Skype for Business Server 2019 后，您需要将中央管理服务器移动到 Skype for Business Server 2019 前端服务器或池，然后才能删除旧服务器。
ms.openlocfilehash: 5c3d090f762904aa5f076033a68e46139b1e84e4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618278"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>将旧版中央管理服务器移动到 Skype for Business Server 2019

迁移到 Skype for Business Server 2019 之后，以及删除旧服务器之前，您需要将中央管理服务器移动到 Skype for Business Server 2019 前端服务器或池。 
  
中央管理服务器是单一主副本/多副本系统，其中数据库的读/写副本由包含中央管理服务器的前端服务器保留。 拓扑中的每台计算机（包括包含中央管理服务器的前端服务器）在 SQL Server 数据库 (中具有中央管理存储数据的只读副本，默认情况下) 在安装和部署过程中安装在该计算机上。 本地数据库通过作为服务在所有计算机上运行的Skype for Business Server复制程序代理接收副本更新。 中央管理服务器上实际数据库和本地副本的名称为 XDS，它由 xds.mdf 和 xds.ldf 文件决定。 主数据库位置由 Active Directory 域服务中的服务 (SCP) 引用。 使用中央管理服务器管理和配置数据库的所有工具Skype for Business Server SCP 找到中央管理存储。
  
成功移动中央管理服务器后，应从原始前端服务器中删除中央管理服务器数据库。 有关删除中央管理服务器数据库的信息，请参阅 Remove [the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md)。
  
使用 Skype for Business Server 命令行管理程序 中的 Windows PowerShell cmdlet **Move-CsManagementServer** 将数据库从旧版安装 SQL Server 数据库移动到 Skype for Business Server 2019 SQL Server 数据库，然后更新 SCP 以指向 Skype for Business Server 2019 中央管理服务器位置。 
  
使用本节中的过程在移动中央管理Skype for Business Server准备 2019 前端服务器。
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>准备前端Enterprise Edition池

1. 在要重定位中央管理服务器的 Skype for Business Server 2019 Enterprise Edition 前端池上，以 **RTCUniversalServerAdmins** 组的一个成员登录到安装了 Skype for Business Server 命令行管理程序的计算机。 还必须对要SQL Server中央管理存储的数据库拥有数据库 sysadmin 用户权限。 
    
2. 打开"Skype for Business Server命令行管理程序"。
    
3. 若要在 Skype for Business Server 2019 管理SQL Server中创建新的中央管理Skype for Business Server命令行管理程序，请键入：
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. 确认前端服务 **的状态Skype for Business Server"已****启动"。**
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>准备Standard Edition前端服务器

1. 在要重定位中央管理服务器的 Skype for Business Server 2019 Standard Edition 前端服务器上，以 **RTCUniversalServerAdmins** 组的一个成员登录到安装了 Skype for Business Server 命令行管理程序的计算机。 
    
2. 打开"Skype for Business Server部署向导"。
    
3. 在"Skype for Business Server向导"中，单击"**准备第一Standard Edition服务器"。**
    
4. 在"**正在执行命令**"页上，SQL Server Express安装为中央管理服务器。 创建必需的防火墙规则。 安装数据库和必备软件后，单击“完成”。
    
    > [!NOTE]
    > 初始安装可能要花费一些时间，这期间命令输出摘要屏幕上不显示更新。 这是由于安装 SQL Server Express。 如果需要监视数据库安装，请使用任务管理器监视安装过程。 
  
5. 若要在前端服务器的 Skype for Business Server 2019 Standard Edition中央管理存储，Skype for Business Server命令行管理程序中键入： 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. 确认前端服务 **的状态Skype for Business Server"已****启动"。**
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>若要将旧版安装中央管理服务器移至 Skype for Business Server 2019

1. 在将成为中央管理服务器的 Skype for Business Server 2019 服务器上，以 **RTCUniversalServerAdmins** 组的一个成员登录到安装了 Skype for Business Server 命令行管理程序的计算机。 您还必须具有 SQL Server 数据库管理员用户权限。 
    
2. 打开Skype for Business Server命令行管理 (以管理员角色) 。
    
3. 在"Skype for Business Server命令行管理程序"中，键入： 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > 如果未 `Enable-CsTopology` 成功，请解决阻止命令完成的问题，然后再继续。 如果 **Enable-CsTopology** 未成功，则移动将失败，并且可能会使拓扑保持没有中央管理存储的状态。 
  
4. 在 Skype for Business Server 2019 前端服务器或前端池的命令行管理程序Skype for Business Server键入： 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. Skype for Business Server命令行管理程序显示当前状态和建议状态的服务器、文件存储、数据库存储和服务连接点。 请仔细查看这些信息，确认这是预期的源和目标。 键入 **Y** 继续，或键入 **N** 停止移动。 
    
6. 查看 **Move-CsManagementServer** 命令生成的所有警告或错误，并解决它们。 
    
7. 在 Skype for Business Server 2019 服务器上，打开"Skype for Business Server部署向导"。 
    
8. 在Skype for Business Server向导"中，单击"安装或更新 **Skype for Business Server 系统**"，单击"步骤 **2： 安装或删除 Skype for Business Server 组件"，** 单击"下一步"，查看摘要，然后单击"完成 **"。** 
    
9. 在旧版安装服务器上，打开部署向导。 
    
10. 在Skype for Business Server向导"中，单击"安装或更新 **Skype for Business Server 系统**"，单击"步骤 **2： 安装或删除 Skype for Business Server 组件"，** 单击"下一步"，查看摘要，然后单击"完成 **"。** 
    
11. 重新启动 Skype for Business Server 2019 服务器。 这是必需项，因为组成员身份更改了以访问中央管理服务器数据库。
    
12. 若要确认正在使用新的中央管理存储进行复制，Skype for Business Server命令行管理程序中键入： 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > 复制可能需要一段时间来更新当前所有副本。 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>在移动后删除旧版安装中央管理存储文件

1. 在旧版安装服务器上，以 **RTCUniversalServerAdmins** 组的成员Skype for Business Server命令行管理程序安装的计算机。 您还必须具有 SQL Server 数据库管理员用户权限。 
    
2. 打开 Skype for Business Server 命令行管理程序
    
    > [!CAUTION]
    > 在复制完成和系统稳定之前，不要继续删除以前的数据库文件。 如果在完成复制之前删除文件，将会中断复制过程，使新移动的中央管理服务器保持未知状态。 可使用 cmdlet **Get-CsManagementStoreReplicationStatus** 确认复制状态。 
  
3. 若要从旧版安装中央管理服务器中删除中央管理存储数据库文件，请键入：
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    例如：
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    其中 _\<FQDN of SQL Server\>_ ， 是旧版安装后端服务器（在 Enterprise Edition 部署中）或 Standard Edition FQDN。 
    

