---
title: 备份和还原 Lync Server 2013
TOCTitle: 备份和还原 Lync Server 2013
ms:assetid: 07dc1f5e-af66-4e18-bf39-881dceff8bc3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh202160(v=OCS.15)
ms:contentKeyID: 52060955
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 备份和还原 Lync Server 2013

 

_**上一次修改主题：** 2013-02-21_

在本节，您将找到关于备份 Lync Server 2013 数据以及还原数据（如果出现故障的话）的最佳实践。这些最佳实践适用于下列情况：

  - 包含任何类型（前端服务器、边缘服务器、中介服务器、持久聊天服务器或控制器）的整个 Lync Server 池，或者其中一个池中的单个服务器。

  - 中央管理服务器 

  - 标准版 服务器

  - 企业版后端服务器 

  - 文件存储 

  - 存档数据库、监控数据库或持久聊天数据库

本节不包括还原整个站点或开发备用站点的信息。有关使用配对前端池开发灾难恢复解决方案的详细信息，请参阅[在 Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。这是用于规划灾难恢复的推荐方法。

如果您已部署配对的前端池，并且如果其中一个池出现故障而不可恢复，则可以从其配对池中还原具有新的完全限定域名 (FQDN) 的此池。有关执行此恢复的步骤的详细信息，请参阅[在 Lync Server 2013 中对池进行故障转移](lync-server-2013-failing-over-a-pool.md)。此外，如果您之后要重新创建作为前端对一部分的故障并不可恢复的池，可以使用[执行 ABC 前端池故障转移](lync-server-2013-performing-an-abc-front-end-pool-failover.md)中的步骤。

本文档介绍的方法包括规划阶段的特殊注意事项。有关详细信息，请参阅[制定备份和还原计划](lync-server-2013-establishing-a-backup-and-restoration-plan.md)。

## 本部分内容

  - [准备 Lync Server 备份和还原](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [备份数据和设置](lync-server-2013-backing-up-data-and-settings.md)

  - [还原数据和设置](lync-server-2013-restoring-data-and-settings.md)

  - [备份和还原工作表](lync-server-2013-backup-and-restoration-worksheets.md)

