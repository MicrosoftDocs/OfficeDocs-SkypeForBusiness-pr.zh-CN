---
title: 删除后端服务器上的 SQL Server 实例和数据库
TOCTitle: 删除后端服务器上的 SQL Server 实例和数据库
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49888369
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除后端服务器上的 SQL Server 实例和数据库

 

_**上一次修改主题：** 2012-10-19_

在移除运行 Lync Server 2010 且依赖于 Microsoft SQL Server 数据库和实例的服务器后，或在将运行 Lync Server 2010 的服务器重新配置为使用其他数据库后，可移除 Microsoft SQL Server 数据库和实例。在停用当前 SQL Server 或重新配置运行 Lync Server 2010 的当前服务器，从而使这些数据库作废或不可用时，需要执行本主题中的过程。

若要移除 存档服务器或 监控服务器的数据库或实例，必须先移除此服务器角色。同样，若要移除 前端池的实例或数据库，必须先移除或重新配置依赖服务器角色。在并置的数据库或单独的服务器实例之间，这些过程没有差别，并且不受数据库并置的影响。

## 本部分内容

  - [删除前端池的 SQL Server 数据库](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [删除监控服务器的 SQL Server 数据库](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [删除存档服务器的 SQL Server 数据库](remove-the-sql-server-database-for-an-archiving-server.md)

