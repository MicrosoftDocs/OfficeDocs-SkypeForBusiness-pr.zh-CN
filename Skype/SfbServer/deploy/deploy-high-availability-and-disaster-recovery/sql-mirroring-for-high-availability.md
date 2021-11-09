---
title: Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: 为了能够部署 SQL 镜像，您的服务器必须至少运行 SQL Server 2008 R2。 此版本必须在所有涉及的服务器上运行：主、镜像和见证。 有关详细信息，请参阅 cumulative update package 9 for SQL Server 2008 Service Pack 1。
ms.openlocfilehash: b27fed99cafa109da8c13e369c93985d7bc4cf64
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60849445"
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a>在 SQL Server 2015 中部署后端服务器高可用性Skype for Business镜像


为了能够部署 SQL 镜像，您的服务器必须至少运行 SQL Server 2008 R2。 此版本必须在所有涉及的服务器上运行：主、镜像和见证。 有关详细信息，请参阅[cumulative update package 9 for SQL Server 2008 Service Pack 1。](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921)

通常，在两台具有见证的后端服务器之间设置 SQL 镜像需要满足以下条件：

- 主服务器的版本必须支持SQL Server镜像SQL镜像。

- 主、镜像和见证（如果部署）必须具有同一版本的 SQL Server。

- 主和镜像必须具有同一版本的 SQL Server。见证可以具有不同版本。

有关SQL角色支持哪些版本SQL最佳实践，请参阅数据库[镜像见证](/sql/database-engine/database-mirroring/database-mirroring-witness)。

使用拓扑生成器部署SQL镜像。 在拓扑生成器中选择一个选项来镜像数据库，拓扑生成器将设置镜像 (包括设置见证（如果需要在发布拓扑时) 设置见证服务器）。 请注意，您在设置或删除镜像的同时将设置或删除见证。 没有用于仅部署或删除见证的单独命令。

若要配置服务器镜像，您必须先正确设置 SQL 数据库权限。 有关详细信息，请参阅为数据库镜像或 AlwaysOn 可用性组设置登录[ (SQL Server) 。 ](/sql/database-engine/database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability)

对于 SQL 镜像，数据库恢复模式始终设置为“完全”，这意味着您必须密切监控事务日志大小并定期备份事务日志以避免后端服务器上的磁盘空间不足。 事务日志备份频率取决于日志增长速率，反过来，日志增长速率又取决于前端池上的用户活动所触发的数据库事务数。 建议您确定部署工作负载预计的事务日志增长量，以便可以相应地进行规划。 下列文章提供了有关 SQL 备份和日志管理的其他信息：

- [数据库恢复模型](/sql/relational-databases/backup-restore/recovery-models-sql-server)

- [备份概述](/sql/relational-databases/backup-restore/backup-overview-sql-server)

- [备份事务日志](/sql/relational-databases/backup-restore/back-up-a-transaction-log-sql-server)

对于 SQL 镜像，可在创建池时或之后为镜像配置拓扑。

> [!IMPORTANT]
> 只有在主服务器、镜像服务器和见证 (（如果需要）) 服务器都属于同一个域时，才支持使用拓扑生成器或 cmdlet 设置和删除 SQL 镜像。 如果您需要在不同域中的服务器之间设置 SQL 镜像，请参阅 SQL Server 文档。

> [!IMPORTANT]
> 只要更改后端数据库镜像关系，就必须重新启动池中的所有前端服务器。 >对于镜像中的更改， (（如更改镜像服务器) ）必须使用拓扑生成器执行以下三个步骤：

1. 从旧镜像服务器中删除镜像。

2. 向新镜像服务器中添加镜像。

3. 发布拓扑。

> [!NOTE]
> 必须创建文件共享，以写入镜像文件，并且运行 SQL Server 和 SQL 代理的服务需要读/写访问权限。 如果 SQL Server 服务在网络服务上下文中运行，您可以将主体服务器和镜像 SQL 服务器的 \<Domain\> \\<SQLSERVERNAME $ 添加到 \> 共享权限。 $ 对于确定这是计算机帐户非常重要。

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a>在拓扑SQL创建池时配置镜像

1. 在“定义 SQL 存储”页上，单击“SQL 存储”框旁边的“新建”。

2. 在“定义新的 SQL 存储”页上，指定主存储，选择“此 SQL 实例处于镜像关系中”，指定 SQL 镜像端口号（默认为 5022），然后单击“确定”。

3. 返回“定义 SQL 存储”页，选择“启用 SQL 存储镜像”。

4. 在“定义新的 SQL 存储”页中，指定要用作镜像的 SQL 存储，选择“此 SQL 实例处于镜像关系中”，指定端口号（默认为 5022），然后单击“确定”。

5. 如果要将见证用于此镜像，请执行以下操作：

    a. 选择“使用 SQL 镜像见证启用自动故障转移”。

    b. 在“定义 SQL 存储”页中，选择“使用 SQL 镜像见证启用自动故障转移”，并指定要用作见证的 SQL 存储。

    c. 指定端口号（默认为 7022）并单击“确定”。

6. 定义完拓扑中的前端池和所有其他角色后，请使用拓扑生成器发布拓扑。 发布拓扑后，如果承载中央管理存储的前端池启用了 SQL 镜像，则会看到一个选项，用于创建存储数据库中的主SQL镜像。

    单击“设置”，并键入要用作镜像备份的文件共享的路径。

    单击“确定”，然后单击“下一步”以创建数据库并发布拓扑。这将部署镜像和见证（如果已指定）。

可以使用拓扑生成器编辑现有池的属性，以启用SQL镜像。

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a>在拓扑SQL中添加到现有前端池的镜像

1. 在拓扑生成器中，右键单击该池，然后单击"编辑 **属性"。**

2. 选择“启用 SQL 存储镜像”，然后单击“镜像 SQL 存储”旁边的“新建”。

3. 指定要用作镜像的 SQL 存储。

4. 选择“此 SQL 实例处于镜像关系中”中，指定 SQL 镜像端口号（默认端口为 5022），然后单击“确定”。

5. 如果要配置见证，请选择“使用 SQL 镜像见证启用自动故障转移”，然后单击“新建”。

6. 指定要用作见证的 SQL 存储。

7. 选择“此 SQL 实例处于镜像关系中”，指定 SQL 镜像端口号（默认端口为 7022），然后单击“确定”。

8. 单击“确定”。

9. 发布拓扑。在执行此操作时，系统会提示您安装数据库。

    在拓扑发布过程中，将要求您定义文件共享路径。 参与SQL的服务器必须具有对此文件共享的读/写访问权限，镜像要建立。

然后必须在继续下一步之前安装数据库。

设置 SQL 镜像时，应记住以下几点：

- 如果某个镜像终结点已存在，则会使用其中定义的端口重用该终结点，并将忽略您在拓扑中指定的端口。

- 已为同一服务器上的其他应用程序分配的任何端口（包括用于其他 SQL 实例的端口）均不应用于当前安装的 SQL 实例。这意味着，如果在同一服务器上安装了多个 SQL 实例，它们不能将同一端口用于镜像。有关详细信息，请参阅以下文章：

  - [指定数据库镜像 (服务器网络) ](/sql/database-engine/database-mirroring/specify-a-server-network-address-database-mirroring)

  - [数据库镜像终结点 (SQL Server) ](/sql/database-engine/database-mirroring/the-database-mirroring-endpoint-sql-server)

## <a name="using-skype-for-business-server-2015-management-shell-cmdlets-to-set-up-sql-mirroring"></a>使用 Skype for Business Server 2015 命令行管理程序 Cmdlet 设置SQL镜像

设置镜像的最简单方法是使用拓扑生成器，但您也可以使用 cmdlet 来设置镜像。

1. 打开 Skype for Business Server 2015 命令行管理程序 窗口并运行以下 cmdlet：

   ```powershell
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose
   ```

    例如：

   ```powershell
   Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose
   ```

    您将看到以下内容：

   <pre>
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
   </pre>

2. 确认以下内容：

    - 如果在主 SQL Server e04-ocs.los_a.lsipt.local\rtc 中启用 Windows 防火墙，则可通过防火墙访问端口 5022。

    - 如果在镜像 SQL Server K16-ocs.los_a.lsipt.local\rtc 中启用 Windows 防火墙，则可通过防火墙访问端口 5022。

    - 如果在见证 SQL Server AB14-lct.los_a.lsipt.local\rtc 中启用 Windows 防火墙，则可通过防火墙访问端口 7022。

   - 在所有主服务器SQL镜像服务器上运行 SQL 的帐户对文件共享 \\ E04-OCS\csdatabackup 具有读/写权限

   - 确认 Windows Management Instrumentation (WMI) 提供程序正在所有这些服务器上运行。该 cmdlet 使用此提供程序查找在所有主、镜像和见证服务器上运行的 SQL Server 服务的帐户信息。

   - 确认运行此 cmdlet 的帐户有权为所有镜像服务器上的数据和日志文件创建文件夹。

   - 请注意，用于运行 SQL 实例的用户帐户必须具有对文件共享的读/写权限。如果文件共享位于其他服务器上且 SQL 实例运行本地系统帐户，则您必须向承载 SQL 实例的服务器授予文件共享权限。

3. 键入 A 并按 Enter。

    将配置镜像。

    **Install-CsMirrorDatabase** 可为主 SQL 存储中存在的所有数据库安装和配置镜像。 如果要仅为特定数据库配置镜像，可以使用 -DatabaseType 选项，或者如果要为除少数数据库之外的所有数据库配置镜像，可以使用 -ExcludeDatabaseList 选项以及要排除的数据库名称的逗号分隔列表。

    例如，如果将以下选项添加到 **Install-CsMirrorDatabase** 中，则除了 rtcab 和 rtcxds 之外的所有数据库都将进行镜像。

    `-ExcludeDatabaseList rtcab,rtcxds`

   例如，如果将以下选项添加到 **Install-CsMirrorDatabase**，则仅镜像 rtcab、rtcshared 和 rtcxds 数据库。

    `-DatabaseType User`

## <a name="removing-or-changing-sql-mirroring"></a>删除或更改 SQL 镜像

若要在拓扑生成器中删除池的 SQL 镜像，您必须先使用 cmdlet 删除 SQL Server 中的镜像。随后，您可使用拓扑生成器删除拓扑中的镜像。若要删除 SQL Server 中的镜像，请使用以下 cmdlet：

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]
```

例如，若要删除镜像并删除针对用户数据库的数据库，请键入：

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror
```

`-DropExistingDatabasesOnMirror`该选项会导致从镜像中删除受影响的数据库。

然后，若要从拓扑中删除镜像，请执行以下操作：

1. 在拓扑生成器中，右键单击池并单击“编辑属性”。

2. 取消选中“启用 SQL 存储镜像”并单击“确定”。

3. 发布拓扑。

## <a name="removing-a-mirroring-witness"></a>删除镜像见证

如果需要从后端服务器镜像配置中删除见证，请使用此过程。

1. 在拓扑生成器中，右键单击池并单击“编辑属性”。

2. 清除“使用 SQL Server 镜像见证启用自动故障转移”，然后单击“确定”。

3. 发布拓扑。

    发布拓扑后，拓扑生成器将看到一条消息，其中包含以下内容

   ```console
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    但是，不要执行该步骤，不要键入 ，因为这将  `Uninstall-CsMirrorDatabase` 卸载整个镜像配置。

4. 若要仅从数据库配置中删除SQL Server，请按照从数据库镜像会话中删除见证中的[ (SQL Server) 。 ](/sql/database-engine/database-mirroring/remove-the-witness-from-a-database-mirroring-session-sql-server)