---
title: 在 Lync Server 2013 中配置 SQL Server 群集
TOCTitle: 在 Lync Server 2013 中配置 SQL Server 群集
ms:assetid: d7b52ef1-573c-48ed-bb94-34e37b49645c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn383982(v=OCS.15)
ms:contentKeyID: 56558980
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置 SQL Server 群集

 

_**上一次修改主题：** 2016-12-08_

Microsoft Lync Server 2013 支持 SQL Server 2012 和 SQL Server 2008 R2 的群集。有关支持的功能的详细信息，请参阅[Lync Server 2013 中的数据库软件支持](lync-server-2013-database-software-support.md)。

安装和部署 Enterprise Edition 前端服务器和后端数据库之前，您应设置和配置 SQL Server 群集。有关 SQL Server 2012 中的故障转移群集的最佳做法和设置说明，请参阅 <http://technet.microsoft.com/zh-cn/library/hh231721.aspx>。有关 SQL Server 2008 中的故障转移群集的信息，请参阅 <http://technet.microsoft.com/zh-cn/library/ms189134(v=sql.105).aspx>。

安装 SQL Server 时，应安装 SQL Server Management Studio 来管理数据库位置和日志文件位置。安装 SQL Server 时，SQL Server Management Studio 将作为可选组件安装。

> [!IMPORTANT]  
> 要在基于 SQL Server 的服务器上安装并部署数据库，您必须是在其上安装数据库文件的基于 SQL Server 的服务器上 SQL Server sysadmin 组的成员。如果不是 SQL Server sysadmin 组的成员，则您需要在部署数据库文件之前请求将您添加到该组。如果您无法成为 sysadmin 组的成员，则应为 SQL Server 数据库管理员提供配置和部署数据库的脚本。有关完成这些过程所需的相应用户权限的详细信息，请参阅<a href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync Server 2013 中 SQL Server 的部署权限</a>。


## 配置 SQL Server 群集

1.  完成 SQL Server 群集的安装和配置后，使用 SQL Server 实例虚拟群集名称（已在 SQL Server 群集设置过程中配置）和 SQL Server 数据库的实例名称在拓扑生成器中定义 SQL Server 存储。与单台基于 SQL Server 的服务器不同，群集的基于 SQL Server 的服务器将使用虚拟节点完全限定的域名 (FQDN)。
    
    > [!NOTE]  
    > 无需为拓扑生成器配置各个 Windows Server 群集节点。将只使用虚拟 SQL Server 群集名称。
    


2.  如果要使用拓扑生成器部署数据库，则您必须是 SQL Server sysadmin 组的成员。如果您是 SQL Server sysadmin 组的成员，但在域中没有权限（例如，SQL Server 数据库管理员角色），那么您将有权创建数据库，但无权读取 Lync Server 中的必要信息。有关部署 Lync Server 所需的用户权限的详细信息，请参阅[Lync Server 2013 中 SQL Server 的部署权限](lync-server-2013-deployment-permissions-for-sql-server.md)。

3.  确保已使用 SQL Server Management Studio 将数据库文件夹默认设置和日志文件文件夹默认设置正确映射到 SQL Server 群集中的共享磁盘。如果要使用拓扑生成器创建数据库，则必须执行此过程。
    
    > [!NOTE]  
    > 如果尚未安装 SQL Server Management Studio，则可通过重新运行 SQL Server 安装，然后选择该管理工具作为现有 SQL Server 部署的附加功能来进行安装。
    


4.  使用拓扑生成器或 Windows PowerShell cmdlet 为基于 SQL Server 的服务器安装数据库。若要使用拓扑生成器，请按照下列过程操作。要使用 Windows PowerShell cmdlet，请参阅[在 Lync Server 2013 中使用 Lync Server 命令行管理程序安装数据库](lync-server-2013-database-installation-using-lync-server-management-shell.md)。

## 使用拓扑生成器创建数据库

1.  启动拓扑生成器：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 拓扑生成器”。
    
    > [!WARNING]
    > 以下过程假定您已在拓扑生成器中定义和配置拓扑。有关定义拓扑的详细信息，请参阅<a href="lync-server-2013-defining-and-configuring-the-topology.md">在 Lync Server 2013 中定义和配置拓扑</a>。要使用拓扑生成器发布拓扑并配置数据库，必须以具有正确用户权限和组成员身份的用户登录。有关所需权限和组成员身份的详细信息，请参阅<a href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync Server 2013 中 SQL Server 的部署权限</a>。


2.  在拓扑生成器中发布拓扑时，在“创建数据库”页上单击“高级”。

3.  “选择数据库文件位置”页有两个选项，用于确定在 SQL Server 群集上部署数据库文件的方式。选择下列选项之一：
    
      - **自动确定数据库文件位置。** 此选项根据基于 SQL Server 的服务器上的驱动器配置，使用一种算法来确定数据库日志和数据文件的位置。将以一种尝试提供最佳性能的方式分配文件。
    
      - 使用 SQL Server 实例默认值。选择此选项将根据 SQL Server 实例设置来安装日志和数据文件。将数据库文件部署到 SQL Server 后，SQL Server 数据库管理员可能需要重新定位文件，以便针对特定的 SQL Server 配置要求来优化性能。

4.  完成发布拓扑并确认操作期间没有任何错误。

