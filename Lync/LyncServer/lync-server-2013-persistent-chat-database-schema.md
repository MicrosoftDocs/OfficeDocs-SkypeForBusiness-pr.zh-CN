---
title: Lync Server 2013：持久聊天数据库架构
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat database schema
ms:assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558653(v=OCS.15)
ms:contentKeyID: 48184228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73f3b21fe8ea7f9fc71aa5432a601e9fa3ad2425
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755232"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-database-schema-in-lync-server-2013"></a>Lync Server 2013 中的持久聊天数据库架构

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-18_

这篇文档介绍了 Lync Server 2013 通信软件中持久聊天数据库的架构。

持久聊天数据库指对应于 Lync Server 2013 后端服务器角色**PersistentChatStore** （对应于 mgc 数据库）和**PersistentChatComplianceStore** （对应于 mgccomp 数据库）的数据库。 发布此架构的目的是使你能够构建查询并深入了解如何构建有关聊天使用、活动会议室、热门海报等的有用报告。

<div>


> [!IMPORTANT]  
> 我们保留发展此架构的权利。 Microsoft 不会确保保持与此已发布架构的完全向后兼容。



</div>

请遵循以下最佳做法：

  - 不支持\* SELECT//，因为列列表可以增长。

  - 不支持用户生成的架构修改。

  - 不支持写入操作。

  - 测试在 representatively 大小的数据库上生成的任何查询，以确保查询可以按级别执行，以满足你的需求。

<div>

## <a name="in-this-section"></a>本节内容

  - [Lync Server 2013 中持久聊天服务器表的列表](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [Lync Server 2013 中持久聊天服务器合规性表的列表](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [Lync Server 2013 中的持久聊天服务器表详细信息](lync-server-2013-persistent-chat-server-table-details.md)

  - [Lync Server 2013 的示例持久聊天数据库查询](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

