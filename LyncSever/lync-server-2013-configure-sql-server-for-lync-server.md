---
title: Lync Server 2013：为 Lync Server 配置 SQL Server
TOCTitle: 为 Lync Server 2013 配置 SQL Server
ms:assetid: 375e5cc4-e436-46dc-9b02-5063f35cdcc1
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425848(v=OCS.15)
ms:contentKeyID: 49312513
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 为 Lync Server 2013 配置 SQL Server

 

_**上一次修改主题：** 2013-08-12_

本节中的主题讨论如何部署和配置 SQL Server 以便在 Lync Server 的企业部署中使用。 Standard Edition 服务器使用适合 Standard Edition Server 工作负载规模的 SQL Server 的并置 SQL Server Express 版本。

Lync Server 2013  中央管理存储可以保存池中所有 企业版 服务器的用户数据，并且设计位于基于 SQL Server 的后端服务器上。作为中央存储库， 中央管理存储不能与其他任何 Lync Server 2013 角色安装在同一台计算机上。 中央管理存储不能位于池中的 企业版 服务器上。首次发布拓扑并选择创建数据库时，会自动创建 中央管理存储。为使安装成功，指定作为后端服务器的计算机必须已在运行 SQL Server 数据库软件。

## 本部分内容

  - [Lync Server 2013 的 SQL Server 数据和日志文件放置](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [在 Lync Server 2013 中配置 SQL Server](lync-server-2013-configure-sql-server.md)

  - [Lync Server 2013 中 SQL Server 的部署权限](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [在 Lync Server 2013 中使用 Lync Server 命令行管理程序安装数据库](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [了解 SQL Server 与 Lync Server 2013 一起使用时的防火墙要求](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [在 Lync Server 2013 中配置 SQL Server 群集](lync-server-2013-configure-sql-server-clustering.md)

