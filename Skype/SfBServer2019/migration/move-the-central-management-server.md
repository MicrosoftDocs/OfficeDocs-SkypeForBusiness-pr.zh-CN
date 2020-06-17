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
localization_priority: Normal
description: 迁移到 Skype for business Server 2019 后，需要将中央管理服务器移动到 Skype for Business Server 2019 前端服务器或池，然后才能删除旧服务器。
ms.openlocfilehash: b5412e1b538627c50c3f2a98a5b68c64364f00a9
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752464"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>将旧版中央管理服务器移动到 Skype for business Server 2019

迁移到 Skype for business Server 2019，并且在删除旧版服务器之前，需要将中央管理服务器移动到 Skype for Business Server 2019 前端服务器或池。 
  
中央管理服务器是单个主/多副本系统，其中数据库的读/写副本由包含中央管理服务器的前端服务器保留。 拓扑中的每台计算机（包括包含中央管理服务器的前端服务器）都具有安装和部署过程中安装到计算机上的 SQL Server 数据库中的中央管理存储数据的只读副本（默认情况下名为 RTCLOCAL）。 本地数据库通过 Skype for Business Server 副本复制器代理（在所有计算机上作为服务运行）接收副本更新。 中央管理服务器和本地副本上的实际数据库的名称为 XDS，它由 XDS 和 XDS 文件组成。 主数据库位置由 Active Directory 域服务中的服务控制点（SCP）引用。 使用中央管理服务器来管理和配置 Skype for Business Server 的所有工具都使用 SCP 查找中央管理存储。
  
成功移动中央管理服务器后，应从原始前端服务器中删除中央管理服务器数据库。 有关删除中央管理服务器数据库的信息，请参阅[删除前端池的 SQL Server 数据库](remove-the-sql-server-database-for-a-front-end-pool.md)。
  
在 Skype for Business Server 命令行管理程序中使用 Windows PowerShell cmdlet **move-csmanagementserver** ，将数据库从旧版 Install sql server 数据库移动到 Skype For business SERVER 2019 SQL server 数据库，然后将 SCP 更新为指向 Skype For business Server 2019 中央管理服务器位置。 
  
使用本节中的过程准备 Skype for Business Server 2019 前端服务器，然后再移动中央管理服务器。
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>准备企业版前端池

1. 在要重新定位中央管理服务器的 Skype for Business Server 2019 Enterprise Edition 前端池上，以**RTCUniversalServerAdmins**组成员的身份登录到安装 Skype For Business Server 命令行管理程序的计算机。 此外，还必须在要安装中央管理存储的数据库上具有 SQL Server 数据库 sysadmin 用户权限和权限。 
    
2. 打开 Skype for Business Server 命令行管理程序。
    
3. 若要在 Skype for business Server 2019 SQL Server 数据库中创建新的中央管理存储，请在 Skype for Business Server 命令行管理程序中键入以下内容：
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. 确认**Skype For Business Server 前端**服务的状态为 "已**启动**"。
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>准备标准版前端服务器

1. 在要重新定位中央管理服务器的 Skype for Business Server 2019 Standard Edition 前端服务器上，以**RTCUniversalServerAdmins**组成员的身份登录到安装 Skype For Business Server 命令行管理程序的计算机。 
    
2. 打开 Skype for Business Server 部署向导。
    
3. 在 "Skype for Business Server 部署向导" 中，单击 "**准备第一个 Standard Edition server**"。
    
4. 在 "**正在执行命令**" 页上，SQL Server Express 安装为中央管理服务器。 创建必需的防火墙规则。 安装数据库和必备软件后，单击“完成”****。
    
    > [!NOTE]
    > 初始安装可能要花费一些时间，这期间命令输出摘要屏幕上不显示更新。 这是因为 SQL Server Express 的安装。 如果需要监视数据库安装，请使用任务管理器监视安装过程。 
  
5. 若要在 Skype for business Server 2019 Standard Edition 前端服务器上创建新的中央管理存储，请在 Skype for Business Server 命令行管理程序中键入以下内容： 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. 确认**Skype For Business Server 前端**服务的状态为 "已**启动**"。
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>将旧版安装中央管理服务器移动到 Skype for Business Server 2019

1. 在将成为中央管理服务器的 Skype for Business Server 2019 服务器上，登录到以**RTCUniversalServerAdmins**组成员身份安装 Skype For Business Server 命令行管理程序的计算机。 您还必须具有 SQL Server 数据库管理员用户权限。 
    
2. 打开 Skype for Business Server 命令行管理程序（以管理员身份运行）。
    
3. 在 Skype for Business Server 命令行管理程序中，键入： 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > 如果 `Enable-CsTopology` 未成功，请先解决阻止命令完成的问题，然后再继续。 如果**enable-cstopology**不成功，移动将会失败，并且可能会使拓扑处于没有中央管理存储的状态。 
  
4. 在 skype for business Server 2019 前端服务器或前端池上，在 Skype for Business Server 命令行管理程序中，键入： 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. Skype for Business Server 命令行管理程序显示服务器、文件存储、数据库存储以及当前状态和建议状态的服务连接点。 请仔细查看这些信息，确认这是预期的源和目标。 键入 **Y** 继续，或键入 **N** 停止移动。 
    
6. 查看 **Move-CsManagementServer** 命令生成的所有警告或错误，并解决它们。 
    
7. 在 Skype for business Server 2019 服务器上，打开 Skype for Business Server 部署向导。 
    
8. 在 "Skype for Business Server 部署向导" 中，单击 "**安装或更新 skype For Business Server 系统**"，单击 "**步骤2：设置" 或 "删除 Skype For business server 组件**"，单击 "**下一步**"，查看摘要，然后单击 "**完成**"。 
    
9. 在旧版安装服务器上，打开部署向导。 
    
10. 在 "Skype for Business Server 部署向导" 中，单击 "**安装或更新 skype For Business Server 系统**"，单击 "**步骤2：设置" 或 "删除 Skype For business server 组件**"，单击 "**下一步**"，查看摘要，然后单击 "**完成**"。 
    
11. 重新启动 Skype for Business Server 2019 服务器。 这是必需的，因为对 access 中央管理服务器数据库进行组成员资格更改。
    
12. 若要确认存在新的中央管理存储的复制，请在 Skype for Business Server 命令行管理程序中键入以下内容： 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > 复制可能需要一段时间来更新当前所有副本。 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>移动后删除旧版安装中央管理存储文件

1. 在旧版安装服务器上，登录到以**RTCUniversalServerAdmins**组成员身份安装 Skype For Business Server 命令行管理程序的计算机。 您还必须具有 SQL Server 数据库管理员用户权限。 
    
2. 打开 Skype for Business Server 命令行管理程序
    
    > [!CAUTION]
    > 在复制完成和系统稳定之前，不要继续删除以前的数据库文件。 如果在完成复制之前删除了文件，则会中断复制过程，并使新移动的中央管理服务器处于未知状态。 可使用 cmdlet **Get-CsManagementStoreReplicationStatus** 确认复制状态。 
  
3. 若要从旧版安装中央管理服务器中删除中央管理存储数据库文件，请键入：
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    例如：
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    其中， _\<FQDN of SQL Server\>_ 是企业版部署中的旧版安装后端服务器或 Standard edition 服务器的 FQDN。 
    

