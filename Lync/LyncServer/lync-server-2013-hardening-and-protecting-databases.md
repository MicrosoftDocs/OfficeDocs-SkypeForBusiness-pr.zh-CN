---
title: Lync Server 2013：强化和保护数据库
TOCTitle: 强化和保护 Lync Server 2013 数据库
ms:assetid: 6953e721-3511-4235-b848-51bab093dc89
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn518330(v=OCS.15)
ms:contentKeyID: 60505966
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 强化和保护 Lync Server 2013 数据库

 

_**上一次修改主题：** 2016-12-08_

Microsoft Lync Server 2013 还依靠 SQL Server 数据库来存储用户信息、会议状态、存档数据和呼叫详细记录 (CDR)。通过以可提高容错能力和简化故障排除的方式对应用程序数据进行分区，可以最大限度地提高 Lync Server 后端数据库中 Lync Server 2013 数据的可用性。要实现这些目标，可按照以下方式对应用程序数据进行分区：

  - **使用服务器分区最佳做法**    将操作系统、应用程序和程序文件与数据文件分开。

  - **存储事务日志文件和数据库文件**    单独存储这些文件以提高容错能力和优化恢复功能，可将这些文件存储在加密磁盘或卷中。

  - **使用服务器群集**   群集后端服务器以优化 Lync Server 2013 系统可用性。

  - **确保已加密和正确处理所有数据备份**   丢失、遗弃或错放的备份媒体可能对 Lync Server 2013 部署的数据安全构成巨大威胁

在除 Standard Edition Server 以外的任何 Lync Server 2013 服务器上，SQL Server Express 实例（RTCLOCAL 实例）都不能进行远程访问，而且除 Standard Edition Server 上的 SQL Server Express 外，不会创建本地防火墙例外。在 Standard Edition Server 上，后端数据库和中央管理存储 (CMS) 均设置为可远程访问。要强化 SQL Server 数据库，可执行以下操作：

  - 在 Standard Edition Server 上自定义 SQL Server Express 防火墙，限制可远程访问数据库的服务器的范围。默认情况下，所有 IP 地址都可以远程访问数据库。

  - 使用 SQL Server 配置管理器指定 SQL Server 远程访问使用的协议、IP 地址和端口：
    
      - Lync Server 2013 使用 TCP/IP 协议。它支持 IP 版本 4 (IPv4)，但不支持 IP 版本 6 (IPv6)。
        
        > [!NOTE]  
		> Lync Server 2013 可以在启用双 IP 堆栈的网络上运行。
        
    
      - Lync Server 2013 支持多个 IP 地址（多宿主网络地址卡）。可以指定 SQL Server 只侦听特定 IP 地址（单个地址或子网），并且只使用特定协议。
    
      - Lync Server 2013 支持静态和动态 SQL Server 端口。

  - 应在静态（非默认）端口上运行 SQL Server，而不要运行 SQL Server 浏览器（这样就不会向客户端报告侦听端口）。这需要对每个 SQL Server 客户端进行自定义配置，其中包括前端服务器、监控服务器、存档服务器和管理控制台（运行 Lync Server 命令行管理程序、Lync Server 控制面板或拓扑生成器），以及运行 Lync Server 的所有其他服务器。

> [!NOTE]  
> 只能将数据库访问权限赋予受信任的数据库管理员。恶意的数据库管理员可能在数据库中插入或修改数据，以获取 Lync Server 2013 服务器的权限，或从服务中获取敏感信息，即使该数据库管理员尚未被授予直接访问或控制 Lync Server 2013 服务器的权限。



有关自定义配置和强化 SQL Server 数据库的详细信息，请参阅 NextHop 博客文章“将 Lync Server 2010 与自定义 SQL Server 网络配置一起使用”，网址为 [http://go.microsoft.com/fwlink/p/?LinkId=214008](http://go.microsoft.com/fwlink/p/?linkid=214008)。

> [!NOTE]  
> 您还可以强化操作系统和应用程序服务器，并可以使用组策略在 Lync Server 部署内实现安全锁定。有关详细信息，请参阅 <a href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">强化和保护 Lync Server 2013 的服务器和应用程序</a>。


