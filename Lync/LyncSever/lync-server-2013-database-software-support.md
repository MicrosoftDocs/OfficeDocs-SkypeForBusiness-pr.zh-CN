---
title: Lync Server 2013 数据库软件支持
TOCTitle: 数据库软件支持
ms:assetid: e05d0032-bbea-4e61-987d-d07b1c045fd5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398990(v=OCS.15)
ms:contentKeyID: 49314497
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的数据库软件支持

 

_**上一次修改主题：** 2016-12-08_

Lync Server 2013 支持以下数据库管理系统：

  - **前端池的后端数据库、存档数据库、监控数据库、持久聊天数据库和持久聊天合规性数据库**
    
      - Microsoft SQL Server 2008 R2 Enterprise 数据库软件（64 位版本）。此外，建议运行最新的 Service Pack。
    
      - Microsoft SQL Server 2008 R2 Standard（64 位版本）。此外，建议运行最新的 Service Pack。
    
      - Microsoft SQL Server 2012 Enterprise（64 位版本）。此外，建议运行最新的 Service Pack。
    
      - Microsoft SQL Server 2012 Standard（64 位版本）。此外，建议运行最新的 Service Pack。

  - **Standard Edition 服务器数据库和前端服务器数据库**
    
      - Microsoft SQL Server 2012 Express（64 位版本）。此外，建议运行最新的 Service Pack。
        
        我们支持在前端服务器和 Standard Edition 服务器上修补和升级 Microsoft SQL Server。但是，当在前端服务器上执行任何种类的升级或修补时，您必须考虑仲裁要求。有关详细信息，请参阅[在 Lync Server 2013 中升级或更新前端服务器](lync-server-2013-upgrade-or-update-front-end-servers.md)和 [Lync Server 2013 中适用于前端服务器、即时消息和状态的拓扑和组件](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)。
    
    > [!NOTE]  
    > Lync Server 2013 会自动在每个 Standard Edition 服务器和每个前端服务器服务器上安装 Microsoft SQL Server 2012 Express（64 位版本）。
    


> [!IMPORTANT]  
> <ul>
> <li><p>Lync Server 2013 不支持 SQL Server 的 32 位版本。必须使用 64 位版本。</p></li>
> <li><p>不支持 SQL Server Web 版本和 SQL Server 工作组版本。不能将其与 Lync Server 2013 结合使用。</p></li>
> <li><p>Lync Server 2013 不支持本机数据库镜像。</p></li>
> <li><p>要使用监控服务器角色，应安装 SQL Server Reporting Services。</p></li>
> </ul>

在前端池中，后端数据库可以是单台 SQL Server 计算机。

> [!IMPORTANT]
> 如果您将 Lync Server 数据库与其他数据库并置在一起，则强烈建议您评估可能影响可用性和性能的所有因素，并请您确保在某个节点失败时剩余节点可处理负载。若要验证故障转移功能，建议您测试所有故障转移方案。


## 使用 SQL 镜像和 SQL 群集

Lync Server 2013 支持为每个 Lync Server 数据库使用 SQL 镜像或 SQL 群集。您可以使用 Lync Server 2013 中的 拓扑生成器工具轻松设置 SQL 镜像。对于 SQL 故障转移群集，您必须使用 SQL Server 进行设置。

Lync Server 2013 对于所有部署支持 SQL 镜像和 SQL 群集拓扑，包括绿场部署和已从 Lync Server 的以前版本升级的组织。

SQL 群集支持适用于主动/被动配置。出于性能原因，被动节点不应被任何其他 SQL 实例共享。

包括以下支持：

  - 针对以下各项的双节点故障转移群集：
    
      - Microsoft SQL Server 2012 Standard（64 位版本）。此外，建议运行最新的 Service Pack。
    
      - Microsoft SQL Server 2008 R2 Standard（64 位版本）。此外，建议运行最新的 Service Pack。

  - 针对以下各项的最多十六节点的故障转移群集：
    
      - Microsoft SQL Server 2012 Enterprise（64 位版本）。此外，建议运行最新的 Service Pack。
    
      - Microsoft SQL Server 2008 R2 Enterprise 数据库软件（64 位版本）。此外，建议运行最新的 Service Pack。

有关 SQL 镜像的详细信息，请参阅 [Lync Server 2013 中的后端服务器高可用性](lync-server-2013-back-end-server-high-availability.md)。有关如何部署 SQL 群集的详细信息，请参阅 [在 Lync Server 2013 中配置 SQL Server 群集](lync-server-2013-configure-sql-server-clustering.md)。

有关 SQL Server 2012 中的故障转移群集的详细信息和最佳做法，请参阅 <http://technet.microsoft.com/zh-cn/library/hh231721.aspx>。有关 SQL Server 2008 中的故障转移群集的信息，请参阅 <http://technet.microsoft.com/zh-cn/library/ms189134(v=sql.105).aspx>。

