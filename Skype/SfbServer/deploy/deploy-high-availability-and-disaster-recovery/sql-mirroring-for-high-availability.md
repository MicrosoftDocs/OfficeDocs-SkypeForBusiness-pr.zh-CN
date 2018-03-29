---
title: 在 Skype for Business Server 2015 中针对后端服务器高可用性部署 SQL 镜像
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: 为了能够部署 SQL 镜像，你的服务器必须至少运行 SQL Server 2008 R2。 此版本必须在所有涉及的服务器上运行：主服务器、镜像服务器和见证服务器。 有关详细信息，请参阅更新 SQL Server 2008 Service Pack 1 包 9 累计。
ms.openlocfilehash: 8de94fc0e15b1d851b43b386b476abfa776fad2d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中针对后端服务器高可用性部署 SQL 镜像
 

为了能够部署 SQL 镜像，你的服务器必须至少运行 SQL Server 2008 R2。 此版本必须在所有涉及的服务器上运行：主服务器、镜像服务器和见证服务器。 有关详细信息，请参阅[累计更新程序包的 SQL Server 2008 Service Pack 1 9 ](http://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921)。
  
通常，在两台具有见证的后端服务器之间设置 SQL 镜像需要满足以下条件：
  
- 主服务器的 SQL Server 版本必须支持 SQL 镜像。
    
- 主、镜像和见证（如果部署）必须具有同一版本的 SQL Server。 
    
- 主和镜像必须具有同一版本的 SQL Server。见证可以具有不同版本。
    
对于 SQL 在哪些 SQL 版本方面的最佳做法支持见证服务器角色的信息，请参阅[数据库镜像见证](https://go.microsoft.com/fwlink/p/?LinkId=247345)。
  
使用拓扑生成器来部署 SQL 镜像。 拓扑生成器要镜像的数据库中选择的选项和拓扑生成器设置镜像 （如果您希望包括设置见证） 发布拓扑时。 请注意，设置或删除见证服务器会同时设置或删除镜像服务器。 没有用于仅部署或删除见证服务器的单独命令。
  
要配置服务器镜像，必须正确设置 SQL 数据库权限。 有关详细信息，请参阅[设置了登录帐户的数据库镜像或 AlwaysOn 可用性组 (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268454)。
  
对于 SQL 镜像，数据库恢复模式始终设置为“**完全**”，这意味着你必须密切监控事务日志大小并定期备份事务日志以避免后端服务器上的磁盘空间不足。事务日志备份频率取决于日志增长速率，反过来，日志增长速率又取决于前端池上的用户活动所产生的数据库事务数。建议确定你的部署工作负载预计将达到的事务日志增长幅度，以便相应地进行规划。以下文章提供了有关 SQL 备份和日志管理的其他信息：
  
- [数据库恢复模型](https://go.microsoft.com/fwlink/p/?LinkId=268446)
    
- [备份概述](https://go.microsoft.com/fwlink/p/?LinkId=268449)
    
- [备份事务日志](https://go.microsoft.com/fwlink/p/?LinkId=268452)
    
对于 SQL 镜像，可在创建池时或之后为镜像配置拓扑。
  
> [!IMPORTANT]
> 使用拓扑生成器或 cmdlet 来设置和删除 SQL 镜像仅在主服务器、 镜像和 （如果需要） 见证服务器所有属于相同的域时，才支持。 如果您需要在不同域中的服务器之间设置 SQL 镜像，请参阅 SQL Server 文档。 
  
> [!IMPORTANT]
> 只要更改了后端数据库镜像关系，就必须重新启动池中的所有前端服务器。 > 为镜像中的更改，（例如，更改镜像的位置），必须使用拓扑生成器来执行以下三个步骤： 
  
1. 从旧镜像服务器中删除镜像。
    
2. 向新镜像服务器中添加镜像。
    
3. 发布拓扑。
    
> [!NOTE]
> 必须为要写入到的镜像文件创建文件共享，SQL Server 和 SQL 代理在其下运行的服务需要读取/写入访问权限。 如果 SQL Server 服务的网络服务环境下运行，您可以添加\<域\>\\< SQLSERVERNAME\>$ 主体和镜像 SQL 服务器的共享权限。 $ 非常重要，可用于标识这是一个计算机帐户。 
  
## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a>若要配置 SQL 镜像拓扑生成器中创建池时

1. 在“**定义 SQL 存储**”页上，单击“**SQL 存储**”框旁边的“**新建**”。
    
2. 在“**定义新的 SQL 存储**”页上，指定主存储，选择“**此 SQL 实例处于镜像关系中**”，指定 SQL 镜像端口号（默认为 5022），然后单击“**确定**”。
    
3. 返回到“**定义 SQL 存储**”页，选中“**启用 SQL 存储镜像**”。 
    
4. 在“**定义新的 SQL 存储**”页中，指定要用作镜像的 SQL 存储，选择“**此 SQL 实例处于镜像关系中**”，指定端口号（默认为 5022），然后单击“**确定**”。
    
5. 如果要将见证服务器用于此镜像，请执行以下操作： 
    
    a. 选中“**使用 SQL 镜像见证启用自动故障转移**”。 
    
    b. 在“**定义 SQL 存储**”页中，选中“**使用 SQL 镜像见证启用自动故障转移**”，并指定要用作见证服务器的 SQL 存储。 
    
    c. 指定端口号（默认为 7022）并单击“**确定**”。 
    
6. 在定义您的拓扑结构，前端池和所有其他角色使用拓扑生成器来发布拓扑。 发布拓扑结构时，如果承载中央管理存储的前端池已启用 SQL 镜像，您将看到一个选项以创建两个主服务器和镜像 SQL 存储数据库。
    
    单击“**设置**”，并键入要用作镜像备份的文件共享的路径。
    
    单击“**确定**”，然后单击“**下一步**”以创建数据库并发布拓扑。这将部署镜像服务器和见证服务器（如果已指定）。
    
拓扑生成器可用于编辑现有池启用 SQL 镜像的属性。 
  
## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a>若要添加 SQL 镜像到拓扑生成器中现有前端池

1. 拓扑生成器中右键单击该池，然后单击**编辑属性**。
    
2. 选中“**启用 SQL 存储镜像**”，然后单击“**镜像 SQL 存储**”旁边的“**新建**”。 
    
3. 指定要用作镜像的 SQL 存储。 
    
4. 选择“**此 SQL 实例处于镜像关系中**”，指定 SQL 镜像端口号（默认端口为 5022），然后单击“**确定**”。
    
5. 如果要配置见证服务器，请选中“**使用 SQL 镜像见证启用自动故障转移**”，然后单击“**新建**”。 
    
6. 指定要用作见证服务器的 SQL 存储。 
    
7. 选择“**此 SQL 实例处于镜像关系中**”，指定 SQL 镜像端口号（默认端口为 7022），然后单击“**确定**”。
    
8. 单击“**确定**”。
    
9. 发布拓扑。在执行此操作时，系统会提示你安装数据库。 
    
    在拓扑发布过程中，系统将要求你定义文件共享路径。参与镜像的 SQL Server 必须对此文件共享具有读取/写入访问权限，才能建立镜像。
    
然后必须在继续下一步之前安装数据库。
  
设置 SQL 镜像时，应谨记以下几点：
  
- 如果某个镜像端点已存在，则会使用其中定义的端口重用该端点，并忽略你在拓扑中指定的端口。
    
- 已为同一服务器上的其他应用程序分配的任何端口（包括用于其他 SQL 实例的端口）均不得用于当前安装的 SQL 实例。这意味着，如果在同一服务器上安装了多个 SQL 实例，它们不能将同一端口用于镜像。有关详细信息，请参阅以下文章：
    
  - [指定服务器网络地址 （数据库镜像）](https://go.microsoft.com/fwlink/p/?LinkId=247346)
    
  - [数据库镜像端点 (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=247347)
    
## <a name="using-skype-for-business-server-management-shell-cmdlets-to-set-up-sql-mirroring"></a>使用业务服务器管理外壳 Cmdlet 的 Skype 设置 SQL 镜像

设置镜像的最简单方法是使用拓扑生成器，但是您还可以使用 cmdlet 完成。
  
1. 打开 Skype 业务服务器管理外壳窗口并运行以下 cmdlet:
    
   ```
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 

   ```

    例如：
    
   ```
   Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose 

   ```

    你将看到以下内容：
    
  ```
  Database Name:rtcxds 
        Data File:D:\CsData\BackendStore\rtc\DbPath\rtcxds.mdf 
         Log File:D:\CsData\BackendStore\rtc\LogPath\rtcxds.ldf 
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\e04-ocs$ 
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\K16-ocs$ 
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
          Account: LOS_A\AB14-lct$ 
    Database Name:rtcshared 
        Data File:D:\CsData\BackendStore\rtc\DbPath\rtcshared.mdf 
         Log File:D:\CsData\BackendStore\rtc\LogPath\rtcshared.ldf 
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\e04-ocs$ 
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\K16-ocs$ 
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
          Account: LOS_A\AB14-lct$ 
    Database Name:rtcab 
        Data File:D:\CsData\ABSStore\rtc\DbPath\rtcab.mdf 
         Log File:D:\CsData\ABSStore\rtc\LogPath\rtcab.ldf 
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\e04-ocs$ 
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\K16-ocs$ 
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
          Account: LOS_A\AB14-lct$ 
    Database Name:rgsconfig 
        Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsconfig.mdf 
         Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsconfig.ldf 
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\e04-ocs$ 
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\K16-ocs$ 
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
          Account: LOS_A\AB14-lct$ 
    Database Name:rgsdyn 
        Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsdyn.mdf 
         Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsdyn.ldf 
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\e04-ocs$ 
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\K16-ocs$ 
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
          Account: LOS_A\AB14-lct$ 
    Database Name:cpsdyn 
        Data File:D:\CsData\ApplicationStore\rtc\DbPath\cpsdyn.mdf 
         Log File:D:\CsData\ApplicationStore\rtc\LogPath\cpsdyn.ldf 
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\e04-ocs$ 
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\K16-ocs$ 
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
          Account: LOS_A\AB14-lct$ 
    Database Name:xds 
        Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\xds.mdf 
         Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\xds.ldf 
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\e04-ocs$ 
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\K16-ocs$ 
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
          Account: LOS_A\AB14-lct$ 
    Database Name:lis 
        Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\lis.mdf 
         Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\lis.ldf 
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\e04-ocs$ 
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
          Account: LOS_A\K16-ocs$ 
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
          Account: LOS_A\AB14-lct$
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): 

  ```

2. 验证以下内容：
    
    - 如果在主 SQL Server e04-ocs.los_a.lsipt.local\rtc 中启用 Windows 防火墙，则可通过防火墙访问端口 5022。 
    
    - 如果在镜像 SQL Server K16-ocs.los_a.lsipt.local\rtc 中启用 Windows 防火墙，则可通过防火墙访问端口 5022。 
    
    - 如果在见证 SQL Server AB14-lct.los_a.lsipt.local\rtc 中启用 Windows 防火墙，则可通过防火墙访问端口 7022。 
    
   - 运行所有的主计算机上的 SQL 服务器和 SQL 服务器镜像的帐户具有读/写权限的文件共享\\E04 OCS\csdatabackup 
    
   - 验证 Windows Management Instrumentation (WMI) 提供程序是否正在所有这些服务器上运行。该 cmdlet 使用此提供程序查找在所有主服务器、镜像服务器和见证服务器上运行的 SQL Server 服务的帐户信息。 
    
   - 验证运行此 cmdlet 的帐户是否有权为所有镜像服务器上的数据和日志文件创建文件夹。 
    
   - 请注意，用于运行 SQL 实例的用户帐户必须具有对文件共享的读取/写入权限。如果文件共享位于其他服务器上且 SQL 实例运行本地系统帐户，则你必须向承载 SQL 实例的服务器授予文件共享权限。
    
3. 键入 A 并按 Enter 键。
    
    将配置镜像。
    
    **安装 CsMirrorDatabase**安装镜像，并配置镜像的主 SQL 存储区上的所有数据库。 如果您想要配置为仅特定数据库镜像，您可以使用-DatabaseType 选项，或者如果您想要配置的除少数之外的所有数据库镜像，您可以使用-ExcludeDatabaseList 选项，以逗号分隔的数据库列表要排除的名称。
  
    例如，如果您将下面的选项添加到**安装 CsMirrorDatabase**，rtcab 和 rtcxds 之外的所有数据库会被都镜像。
  
    `-ExcludeDatabaseList rtcab,rtcxds`
  
   例如，如果**安装 CsMirrorDatabase**中添加下面的选项，只有 rtcab、 rtcshared 和 rtcxds 数据库会被镜像。
  
    `-DatabaseType User`
  
## <a name="removing-or-changing-sql-mirroring"></a>删除或更改 SQL 镜像

要在拓扑生成器中删除池的 SQL 镜像，你必须先使用 cmdlet 删除 SQL Server 中的镜像。随后，你可以使用拓扑生成器删除拓扑中的镜像。要删除 SQL Server 中的镜像，请使用以下 cmdlet：
  
```
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

```

例如，要删除镜像并删除针对用户数据库的数据库，请键入：
  
```
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

```

`-DropExistingDatabasesOnMirror`选项将导致受影响的数据库可以从镜像中删除。
  
然后，要从拓扑中删除镜像，请执行以下操作：
  
1. 在拓扑生成器中，右键单击该池并单击“**编辑属性**”。
    
2. 取消选中“**启用 SQL 存储镜像**”并单击“**确定**”。
    
3. 发布拓扑。
    
## <a name="removing-a-mirroring-witness"></a>删除镜像见证

如果您需要从后端服务器镜像配置中删除证人，则使用此过程。
  
1. 在拓扑生成器中，右键单击该池并单击“**编辑属性**”。 
    
2. 取消选中“**使用 SQL Server 镜像见证启用自动故障转移**”，然后单击“**确定**”。
    
3. 发布拓扑。
    
    发布拓扑结构拓扑生成器后您将看到一条消息，包含了下列
    
   ```
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    但是，请不要按照该步骤，并且没有键入`Uninstall-CsMirrorDatabase`一样，将卸载整个镜像配置。
    
4. 若要删除从 SQL Server 配置只是证人，按照[删除数据库镜像会话 (SQL Server) 从尺寸界线](https://go.microsoft.com/fwlink/p/?LinkId=268456)中的说明进行操作。
    

