---
title: Lync Server 2013：使用 Lync Server 命令行管理程序安装数据库
TOCTitle: 使用 Lync Server 命令行管理程序安装数据库
ms:assetid: c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398832(v=OCS.15)
ms:contentKeyID: 49314239
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中使用 Lync Server 命令行管理程序安装数据库
 

_**上一次修改主题：** 2016-12-08_

服务器管理员和 SQL Server 管理员之间角色和职责的分离可能会导致实现中出现延迟。 Lync Server 2013 使用基于角色的访问控制 (RBAC) 来解决这些难题。在某些实例中，SQL Server 管理员必须管理在 RBAC 之外基于 SQL Server 的服务器上安装数据库。 Lync Server 2013 命令行管理程序为 SQL Server 管理员提供了一种运行 Windows PowerShell cmdlet（旨在通过正确的数据和日志文件配置数据库）的方法。有关详细信息，请参阅 [Lync Server 2013 中 SQL Server 的部署权限](lync-server-2013-deployment-permissions-for-sql-server.md)。

> [!IMPORTANT]
> 以下过程假定至少安装了 Microsoft SQL Server 2012 和 Microsoft SQL Server 2012 ADOMD.NET 的 Lync Server 2013 OCSCore.msi、SQL Server Native Client (sqlncli.msi) Microsoft SQL Server 2012 管理对象、CLR 类型。OCSCore.msi 位于安装媒体的 \Setup\AMD64\Setup 目录中。其余组件位于 \Setup\amd64 中。此外，已成功完成 Lync Server 2013 的 Active Directory 准备工作。


**Install-CsDatabase** 是用于安装数据库的 Windows PowerShell cmdlet。 **Install-CsDatabase** cmdlet 有大量参数，此处只讨论其中的一部分。有关可能的参数的详细信息，请参阅 Lync Server 2013 命令行管理程序文档。

> [!WARNING]
> 为避免性能问题和可能出现的超时问题，引用基于 SQL Server 的服务器时请始终使用完全限定域名 (FQDN)。避免只引用主机名。例如，使用 sqlbe01.contoso.net，避免使用 SQLBE01。


对于安装数据库而言， **Install-CsDatabase** 使用三种主要的方法将数据库放入准备好的基于 SQL Server 的服务器：

  - 运行不带 DatabasePaths 或 UseDefaultSqlPath 的 **Install-CsDatabase**。该 cmdlet 使用内置算法确定日志和数据文件的最佳放置方法。此算法仅适用于单独的 SQL Server 实现。

  - 运行带有 DatabasePaths 参数的 **Install-CsDatabase**。如果定义了 DatabasePaths 参数，则不使用优化日志和数据文件位置的内置算法。您可以使用该参数来定义要部署日志和数据文件的位置。

  - 运行带有 UseDefaultSqlPaths 的 **Install-CsDatabase**。该选项不使用内置算法来优化日志和数据文件的位置。日志和数据文件是根据 SQL Server 管理员设置的默认值来部署的。设置这些路径通常是为了预先在 SQL Server 中自动管理日志和数据文件，这些路径与 Lync Server 2013 的设置没有关联。

  - DatabasePathMap 参数还可用于为每个数据库及其日志文件显式指定一个位置。

## 使用 Windows PowerShell cmdlet 配置 SQL Server 中央管理存储

1.  在任意计算机上，使用管理凭据进行登录，以便在基于 SQL Server 的服务器上创建数据库。有关详细信息，请参阅 [Lync Server 2013 中 SQL Server 的部署权限](lync-server-2013-deployment-permissions-for-sql-server.md)。

2.  打开 Lync Server 2013 命令行管理程序。如果尚未调整 Windows PowerShell 的执行策略，则必须对策略进行调整，以便使 Windows PowerShell 脚本可以运行。有关详细信息，请参阅“检查执行策略”，网址为 <http://go.microsoft.com/fwlink/?linkid=203093>。

3.  使用 **Install-CsDatabase** cmdlet 安装 中央管理存储。
    
      ```
      Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <fully qualified domain name of SQL Server> 
      -SqlInstanceName <named instance> -DatabasePaths <logfile path>,<database file path> 
       -Report <path to report file>
      ```  

        
      ```
      Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn sqlbe.contoso.net -SqlInstanceName rtc -DatabasePaths "C:\CSDB-Logs","C:\CSDB-CMS" -Report "C:\Logs\InstallDatabases.html"
      ```
    
    > [!TIP]
    > Report 参数是可选的，但是在记录安装过程时很有用。


4.  **Install-CsDatabase –DatabasePaths** 最多可以使用六个路径参数，其中每个参数均定义了“SQL Server 数据和日志文件放置”中定义的驱动器的路径。依据 Lync Server 2013 中的数据库配置的逻辑规则，驱动器会解析为两个、四个或六个桶。根据您的 SQL Server 配置和桶的数目，您将提供两条、四条或六条路径。
    
    如果您有三个驱动器，则将优先分发日志文件，然后再分发数据文件。以下是配置了六个驱动器的基于 SQL Server 的服务器的示例：
    
        Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"

5.  完成数据库安装后，您可以关闭 Lync Server 2013 命令行管理程序，或继续对 拓扑生成器中定义的 Lync Server 2013 配置数据库进行安装。

## 使用 Windows PowerShell cmdlet 对配置有 SQL Server 拓扑的数据库进行配置

1.  要为 Lync Server 2013 安装配置有 拓扑生成器的数据库， Lync Server 2013 管理员必须发布拓扑。有关详细信息，请参阅部署文档中的 [在 Lync Server 2013 中发布拓扑](lync-server-2013-publish-the-topology.md)。

2.  在任意计算机上，使用管理凭据进行登录，以便在基于 SQL Server 的服务器上创建数据库。请参阅主题[Lync Server 2013 中 SQL Server 的部署权限](lync-server-2013-deployment-permissions-for-sql-server.md)。
    
    > [!IMPORTANT]
    > 为了能够配置基于 SQL Server 的数据库，请确保用于运行此处描述的步骤的 SQL Server 管理员帐户也是运行 SQL Server 并保留中央管理服务器角色的服务器上的 sysadmins 组（或等效组）的成员。这对于检查任何其他需要 SQL Server 数据库安装或配置的 Lync Server 2013 池特别重要。例如，如果您部署的是另一个池 (pool02)，而 pool01 保留了中央管理服务器角色，则 SQL Server sysadmin 组（或等效组）必须同时具有这两个基于 SQL Server 的数据库的权限。


3.  打开 Lync Server 2013 命令行管理程序（如果尚未打开）。

4.  使用 **Install-CsDatabase** cmdlet 安装通过 拓扑生成器配置的数据库。
    
	```
	Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <fully qualified domain name of SQL Server> 
	 -DatabasePaths <logfile path>,<database file path> -Report <path to report file>
	```

        
    ```
	Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe.contoso.net 
        -Report "C:\Logs\InstallDatabases.html"
	```
    
    > [!TIP]
    > Report 参数是可选的，但是在记录安装过程时很有用。


5.  完成数据库安装后，关闭 Lync Server 2013 命令行管理程序。

## 使用 Windows PowerShell cmdlet 通过 DatabasePathMap 参数配置 SQL Server 拓扑

1.  要为 Lync Server 2013 安装数据库， Lync Server 管理员必须按照预定义的规则集创建路径并部署数据库文件和日志文件。

2.  在任意计算机上，使用管理凭据进行登录，以便在基于 SQL Server 的服务器上创建数据库。请参阅主题[Lync Server 2013 中 SQL Server 的部署权限](lync-server-2013-deployment-permissions-for-sql-server.md)。
    
    > [!IMPORTANT]
    > 为了能够配置基于 SQL Server 的数据库，请确保用于运行此处描述的步骤的 SQL Server 管理员帐户也是运行 SQL Server 并保留中央管理服务器角色的服务器上的 sysadmins 组（或等效组）的成员。这对于检查任何其他需要 SQL Server 数据库安装或配置的 Lync Server 池特别重要。例如，如果您部署的是另一个池 (pool02)，而 pool01 保留了中央管理服务器角色，则 SQL Server sysadmin 组（或等效组）必须同时具有这两个基于 SQL Server 的数据库的权限。


3.  打开 Lync Server 命令行管理程序（如果尚未打开）。

4.  使用 **Install-CsDatabase** cmdlet 通过 DatabasePathMap 参数和 PowerShell 哈希表安装 拓扑生成器配置的数据库。

5.  在示例代码中，可以使用 –DatabasePathsMap 参数和定义的哈希表精确地确定为数据库定义的路径（该示例使用“C:\\CSData”保存所有数据库 (.mdf) 文件，使用“C:\\CSLogFiles”保存所有日志 (.ldf) 文件。可根据需要通过 Install-CsDatabase 创建文件夹），如下所示：
    
        $pathmap = @{
        "BackendStore:BlobStore:DbPath"="C:\CsData";"BackendStore:BlobStore:LogPath"="C:\CsLogFiles"
        "BackendStore:RtcSharedDatabase:DbPath"="C:\CsData";"BackendStore:RtcSharedDatabase:LogPath"="C:\CsLogFiles"
        "ABSStore:AbsDatabase:DbPath"="C:\CsData";"ABSStore:AbsDatabase:LogPath"="C:\CsLogFiles"
        "ApplicationStore:RgsConfigDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsConfigDatabase:LogPath"="C:\CsLogFiles"
        "ApplicationStore:RgsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsDynDatabase:LogPath"="C:\CsLogFiles"
        "ApplicationStore:CpsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:CpsDynDatabase:LogPath"="C:\CsLogFiles"
        "ArchivingStore:ArchivingDatabase:DbPath"="C:\CsData";"ArchivingStore:ArchivingDatabase:LogPath"="C:\CsLogFiles"
        "MonitoringStore:MonitoringDatabase:DbPath"="C:\CsData";"MonitoringStore:MonitoringDatabase:LogPath"="C:\CsLogFiles"
        "MonitoringStore:QoEMetricsDatabase:DbPath"="C:\CsData";"MonitoringStore:QoEMetricsDatabase:LogPath"="C:\CsLogFiles"
        }
        Install-CsDatabase -ConfigureDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathsMap $pathmap

6.  由于数据库和日志文件使用其在目标数据库服务器上的位置显式命名，因此可以为每种服务类型的实际数据库和日志位置定义特定路径。以下示例将每种特定服务类型的数据库放在单独的磁盘上，相关的日志文件放在另一个磁盘上。例如：
    
      - 所有 RTC 数据库放在“D:\\RTCDatabase”
    
      - 所有 RTC 日志文件放在“E:\\RTCLogs”
    
      - 所有应用程序存储数据库放在“F:\\CPSDatabases”
    
      - 所有应用程序存储日志放在“G:\\CPSLogs”
    
      - 所有响应组存储数据库放在“H:\\RGSDatabases”
    
      - 所有响应组存储日志放在“I:\\RGSLogs”
    
      - 所有通讯簿存储数据库放在“J:\\ABSDatabases”
    
      - 所有通讯簿存储日志文件放在“K:\\ABSLogs”
    
      - 所有存档存储数据库放在“L:\\ArchivingDatabases”
    
      - 所有存档存储日志放在“M:\\ArchivingLogs”
    
      - 所有监控存储数据库放在“N:\\MonitoringDatabases”
    
      - 所有监控存储日志文件放在“O:\\MonitoringLogfiles”
    
    <!-- end list -->
    
    ``` 
    
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="D:\RTCDatabase";"BackendStore:BlobStore:LogPath"="E:\RTCLogs"
    "BackendStore:RtcSharedDatabase:DbPath"="D:\RTCDatabase";"BackendStore:RtcSharedDatabase:LogPath"="E:\RTCLogs"
    "ABSStore:AbsDatabase:DbPath"="J:\ABSDatabases";"ABSStore:AbsDatabase:LogPath"="K:\ABSLogs"
    "ApplicationStore:RgsConfigDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsConfigDatabase:LogPath"="G:\CPSLogs"
    "ApplicationStore:RgsDynDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsDynDatabase:LogPath"="I:\RGSLogs"
    "ApplicationStore:CpsDynDatabase:DbPath"="F:\CPSDatabases";"ApplicationStore:CpsDynDatabase:LogPath"="G:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="M:\ArchivingLogs";"ArchivingStore:ArchivingDatabase:LogPath"="N:\MonitoringDatabases"
    "MonitoringStore:MonitoringDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:MonitoringDatabase:LogPath"="O:\MonitoringLogfiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:QoEMetricsDatabase:LogPath"="O:\MonitoringLogfiles"
    }
    
    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
    
    使用 –DatabasePathMap 参数可以定义任意逻辑驱动器号组合，从而为满足 SQL Server 性能和放置要求提供最佳解决方案。

如果使用 **DatabasePathMap** 方法配置数据库数据文件和日志文件，则需要在使用 拓扑生成器时对常规过程进行轻微更改。通常，您将定义拓扑选择，发布拓扑，然后选择部署数据库选择。

如果使用了 **DatabasePathMap**，则已完成 拓扑生成器过程的第三部分。如果在运行 拓扑生成器之前已完整配置了数据库服务器，仍需要定义所有服务器角色和选项，但要取消选择选项才能创建数据库。

