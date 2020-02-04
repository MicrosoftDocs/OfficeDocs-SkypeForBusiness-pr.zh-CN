---
title: Lync Server 2013：使用 Lync Server 命令行管理程序安装数据库
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database installation using Lync Server Management Shell
ms:assetid: c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398832(v=OCS.15)
ms:contentKeyID: 48185401
ms.date: 06/16/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c617d323eb00476b53677b670c8cc6db0b8d05c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a>在 Lync Server 2013 中使用 Lync Server 命令行管理程序安装数据库

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2016-06-16_

服务器管理员和 SQL Server 管理员之间的角色和职责的分离可能导致实现延迟。 Lync Server 2013 使用基于角色的访问控制（RBAC）来缓解这些问题。 在某些情况下，SQL Server 管理员必须在基于 SQL Server 的服务器上管理在 RBAC 外的数据库安装。 Lync Server 2013 命令行管理程序为 SQL Server 管理员提供了一种运行 Windows PowerShell cmdlet 的方法，该 cmdlet 旨在使用正确的数据和日志文件配置数据库。 有关详细信息，请参阅[Lync server 2013 中的 SQL Server 部署权限](lync-server-2013-deployment-permissions-for-sql-server.md)。

<div class=" ">


> [!IMPORTANT]  
> 以下过程假定至少安装了 Lync Server 2013 OCSCore、SQL Server Native Client （sqlncli） Microsoft SQL server 2012 管理对象、安装了 Microsoft SQL Server 2012 和 Microsoft SQL Server 2012 ADOMD.NET 的 CLR 类型。 OCSCore 位于 \Setup\AMD64\Setup 目录的安装媒体中。 剩余的组件位于 \Setup\amd64. 中。 此外，已成功完成 Lync Server 2013 的 Active Directory 准备。



</div>

**Install-CsDatabase**是用于安装数据库的 Windows PowerShell cmdlet。 **CsDatabase** cmdlet 具有大量参数，这里只讨论几个参数。 有关可能的参数的详细信息，请参阅 Lync Server 2013 管理外壳文档。

<div class=" ">


> [!WARNING]  
> 若要避免性能和可能出现的超时问题，请在引用基于 SQL Server 的服务器时始终使用完全限定的域名（Fqdn）。 避免使用仅限主机名的引用。 例如，使用 sqlbe01.contoso.net，但避免使用 SQLBE01。



</div>

对于安装数据库， **CsDatabase**使用三种主要方法将数据库放在基于 SQL server 的预安装服务器上：

  - 运行**安装-CsDatabase**而不 DatabasePaths 或 UseDefaultSqlPath。 该 cmdlet 使用内置算法确定日志和数据文件的最佳位置。 该算法仅适用于独立的 SQL Server 实现。

  - 通过 DatabasePaths 参数运行**Install CsDatabase** 。 如果定义了 DatabasePaths 参数，则不会使用内置算法来优化日志和数据文件位置。 使用此参数可定义将在其中部署日志和数据文件的位置。

  - CsDatabase 与 UseDefaultSqlPaths 一起运行**安装**。 此选项不使用内置算法来优化日志和数据文件位置。 根据 SQL Server 管理员设置的默认值来部署日志和数据文件。 通常，这些路径用于自动管理 SQL Server 上的日志和数据文件的目的，并且不与 Lync Server 2013 的设置相关联。

  - DatabasePathMap 参数还可用于为每个数据库和其各自的日志文件显式指定一个位置。

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a>使用 Windows PowerShell cmdlet 配置 SQL Server 中央管理存储

1.  在任何计算机上，用管理凭据登录，以便在基于 SQL Server 的服务器上创建数据库。 有关详细信息，请参阅[Lync server 2013 中的 SQL Server 部署权限](lync-server-2013-deployment-permissions-for-sql-server.md)。

2.  打开 Lync Server 2013 命令行管理程序。 如果尚未调整 Windows PowerShell 的执行策略，则必须调整策略以允许 Windows PowerShell 脚本运行。 有关详细信息，请参阅中的 "检查执行[http://go.microsoft.com/fwlink/p/?linkId=203093](http://go.microsoft.com/fwlink/p/?linkid=203093)策略"。

3.  使用**CsDatabase** Cmdlet 安装中央管理存储。
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <fully qualified domain name of SQL Server> 
        -SqlInstanceName <named instance> -DatabasePaths <logfile path>,<database file path> 
        -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn sqlbe.contoso.net -SqlInstanceName rtc -DatabasePaths "C:\CSDB-Logs","C:\CSDB-CMS" -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > Report 参数是可选的，但如果要记录安装过程，则该参数非常有用。

    
    </div>

4.  **Install-CsDatabase-DatabasePaths**最多可以使用六条路径参数，每个参数定义了在 SQL Server Data 和日志文件放置中定义的驱动器路径。 按照 Lync Server 2013 中的数据库配置的逻辑规则，驱动器将被解析为2、4或6的存储桶。 根据你的 SQL Server 配置和存储桶的数量，你将提供两条路径、四条路径或六条路径。
    
    如果你有三个驱动器，日志将获得优先级，并且将在之后分发数据文件。 使用6个驱动器配置的基于 SQL Server 的服务器的示例：
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  数据库安装完成后，您可以关闭 Lync Server 2013 命令行管理程序，或继续安装在拓扑生成器中定义的 Lync Server 2013 配置的数据库。

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a>使用 Windows PowerShell cmdlet 配置 SQL Server 拓扑配置的数据库

1.  若要为 Lync Server 2013 安装拓扑生成器配置的数据库，Lync Server 2013 管理员必须发布拓扑。 有关详细信息，请参阅部署文档中[Lync Server 2013 中的 "发布拓扑](lync-server-2013-publish-the-topology.md)"。

2.  在任何计算机上，用管理凭据登录，以便在基于 SQL Server 的服务器上创建数据库。 请参阅[Lync server 2013 中的 SQL Server 部署权限](lync-server-2013-deployment-permissions-for-sql-server.md)主题。
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > 若要配置基于 SQL Server 的数据库，请确保用于运行此处所述步骤的 SQL Server 管理员帐户也是运行 SQL Server 并拥有集中管理的服务器上的 sysadmin 组（等同）成员服务器角色。 对于需要 SQL Server 数据库安装或配置的任何其他 Lync Server 2013 池，这一点尤其重要。 例如，如果你要部署第二个池（pool02），但中央管理服务器角色由 pool01 拥有。 SQL Server sysadmin 组（或同等身份）必须具有对基于 SQL Server 的数据库的权限。

    
    </div>

3.  打开 Lync Server 2013 命令行管理程序（如果它尚未打开）。

4.  使用**CsDatabase** Cmdlet 安装拓扑生成器配置的数据库。
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <fully qualified domain name of SQL Server> 
         -DatabasePaths <logfile path>,<database file path> -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe.contoso.net 
        -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > Report 参数是可选的，但如果要记录安装过程，则该参数非常有用。

    
    </div>

5.  数据库安装完成后，关闭 Lync Server 2013 命令行管理程序。

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a>使用 Windows PowerShell cmdlet 使用 DatabasePathMap 参数配置 SQL Server 拓扑

1.  若要为 Lync Server 2013 安装数据库，Lync Server 管理员必须创建路径并根据预定义的一组规则部署数据库文件和日志文件。

2.  在任何计算机上，用管理凭据登录，以便在基于 SQL Server 的服务器上创建数据库。 请参阅[Lync server 2013 中的 SQL Server 部署权限](lync-server-2013-deployment-permissions-for-sql-server.md)主题。
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > 若要配置基于 SQL Server 的数据库，请确保用于运行此处所述步骤的 SQL Server 管理员帐户也是运行 SQL Server 并拥有集中管理的服务器上的 sysadmin 组（等同）成员服务器角色。 这对于检查是否有需要 SQL Server 数据库安装或配置的任何其他 Lync 服务器池尤其重要。 例如，如果你要部署第二个池（pool02），但中央管理服务器角色由 pool01 拥有。 SQL Server sysadmin 组（或同等身份）必须具有对基于 SQL Server 的数据库的权限。

    
    </div>

3.  打开 Lync Server 命令行管理程序（如果尚未打开）。

4.  将**CsDatabase** Cmdlet 与 DatabasePathMap 参数和 PowerShell 哈希表配合使用，以安装拓扑生成器配置的数据库。

5.  在示例代码中，可以使用– DatabasePathMap 参数和定义的哈希表以粒度方式确定为数据库定义的路径（此示例对所有数据库（.mdf）文件使用 "C\\： CSData"，而对于所有日志（.ldf）文件使用 "c\\： CSLogFiles"。 将按安装所需创建文件夹-CsDatabase）：
    ```powershell
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
    Install-CsDatabase -ConfigureDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
6.  由于数据库和日志文件在目标数据库服务器上的位置显式命名，因此你可以为每个服务类型的实际数据库和日志位置定义特定位置。 下面的示例将每个特定服务类型的数据库放在单独的磁盘上，并将关联的日志文件放在另一个磁盘上。 例如：
    
      - 所有 RTC 数据库到 "D：\\RTCDatabase"
    
      - 所有 RTC 日志文件到 "E：\\RTCLogs"
    
      - 所有应用商店数据库到 "F：\\CPSDatabases"
    
      - 所有应用商店日志到 "G：\\CPSLogs"
    
      - 所有响应组存储数据库到 "H：\\RGSDatabases"
    
      - 所有响应组存储日志到 "I：\\RGSLogs"
    
      - 所有通讯簿将数据库存储到 "J\\： ABSDatabases"
    
      - "所有通讯簿" 将日志文件存储到\\"K： ABSLogs"
    
      - 所有存档将数据库存储到 "L\\： ArchivingDatabases"
    
      - 所有存档存储日志到 "M：\\ArchivingLogs"
    
      - 所有监视存储数据库到 "N：\\MonitoringDatabases"
    
      - 所有监视应用商店日志文件均为 "\\O： MonitoringLogfiles"
    
    <!-- end list -->
    
    ```powershell    
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
    
    使用-DatabasePathMap 参数，你可以定义任何逻辑驱动器号映射组合，为你的 SQL Server 性能和放置要求提供最佳解决方案。

如果你使用**DatabasePathMap**方法配置数据库数据文件和日志文件，你将需要在使用拓扑生成器时对你的正常过程稍作更改。 通常，你将定义拓扑选项，发布拓扑，并选择部署数据库选择。

如果您使用过**DatabasePathMap** ，则您已经完成了拓扑生成器过程的第三部分。 如果在运行拓扑生成器之前拥有完全配置的数据库服务器，您仍可以定义所有服务器角色和选项，但取消选择用于创建数据库的选项。

</div>

</div>

<span> </span>

</div>

</div>

</div>

