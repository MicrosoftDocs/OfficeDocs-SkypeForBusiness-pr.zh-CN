---
title: Lync Server 2013：持久聊天数据库架构
TOCTitle: 持久聊天数据库架构
ms:assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg558653(v=OCS.15)
ms:contentKeyID: 49312918
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的持久聊天数据库架构

 

_**上一次修改主题：** 2012-09-18_

它记录了 Lync Server 2013  通信软件中 持久聊天数据库的架构。

持久聊天数据库指的是与 Lync Server 2013 后端服务器角色 **PersistentChatStore** （与 mgc 数据库对应）和 **PersistentChatComplianceStore** （与 mgccomp 数据库对应）对应的数据库。发布此架构的目的是让您能够生成查询和一定程度地了解如何生成有关聊天使用、活跃的聊天室、置顶帖等内容的有用报告。

> [!IMPORTANT]
> 我们保留改进此架构的权利。Microsoft 不对保留此已发布架构的完全向后兼容性做任何保证。


请遵循以下最佳做法：

  - 不支持 SELECT\* //，因为列列表可能增大。

  - 不支持用户生成的架构修改。

  - 不支持写入操作。

  - 测试您在典型大小的数据库中生成的任何查询，以确保这些查询可以在满足您需求的级别执行。

## 本部分内容

  - [Lync Server 2013 中持久聊天服务器表的列表](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [Lync Server 2013 中持久聊天服务器合规性表的列表](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [Lync Server 2013 中的持久聊天服务器表详细信息](lync-server-2013-persistent-chat-server-table-details.md)

  - [Lync Server 2013 的示例持久聊天数据库查询](lync-server-2013-sample-persistent-chat-database-queries.md)

