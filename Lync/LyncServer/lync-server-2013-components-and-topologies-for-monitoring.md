---
title: Lync Server 2013：用于监控的组件和拓扑
TOCTitle: 用于监控的组件和拓扑
ms:assetid: c1bb36b0-1fb8-4d8e-9cc9-9bef740fe3c6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412952(v=OCS.15)
ms:contentKeyID: 49888592
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中用于监控的组件和拓扑

 

_**上一次修改主题：** 2012-09-05_

由于在每个前端服务器上会自动安装并激活统一数据收集代理，因此无需将某个服务器配置为监控服务器；每个前端服务器均已充当监控服务器。但是，您将需要安装数据库并将其配置为针对监控数据的后端数据存储。 Microsoft Lync Server 2013 可以将以下任何数据库用作用于监控的后端存储：

  - Microsoft SQL Server 2008 R2 Enterprise Edition

  - Microsoft SQL Server 2008 R2 Standard Edition

  - Microsoft SQL Server 2012 Enterprise Edition

  - Microsoft SQL Server 2012 Standard Edition

请注意，您必须使用这些数据库的 64 位版本；SQL Server 的 32 位版本无法用作用于监控的后端存储。同样， Lync Server 2013 不支持 SQL Server 2008 Express Edition 或 SQL Server 2012 Express Edition。有关 Lync Server 2013 的数据库要求的详细信息，请参阅 Lync Server 2013 可支持性指南中的 [Lync Server 2013 中的数据库软件支持](lync-server-2013-database-software-support.md)主题。

请记住，必须先安装并配置 SQL Server，然后再部署和配置监控。不过，您仅需要部署 SQL Server 本身；无需提前设置监控数据库。当您发布 Lync Server 拓扑时，将会自动为您创建这些数据库。

监控数据可以与其他类型的数据共享 SQL Server 实例。通常，呼叫详细信息记录数据库 (LcsCdr) 和体验质量数据库 (QoEMetrics) 共享相同的 SQL 实例；这两个监控数据库与存档数据库 (LcsLog) 位于相同的 SQL 实例中也是很常见的。对 SQL Server 实例的唯一真正要求是，SQL Server 的任何一个实例仅限于以下各项：

  - Lync Server 2013 后端数据库的一个实例。（一般而言，建议不要将监控数据库与后端数据库并置在相同的 SQL 实例中，或者甚至并置在相同的计算机上。虽然从技术上而言是可能的，但是监控数据库很有可能会耗尽后端数据库所需的磁盘空间。）

  - 呼叫详细信息记录数据库的一个实例。

  - 体验质量数据库的一个实例。

  - 存档数据库的一个实例。

换句话说，您不能在同一个 SQL Server 实例中有两个 LcsCdr 数据库实例。如果您需要多个 LcsCdr 数据库实例，则需要配置多个 SQL Server 实例。

## 另请参阅

#### 其他资源

[部署监控](lync-server-2013-deploying-monitoring.md)

