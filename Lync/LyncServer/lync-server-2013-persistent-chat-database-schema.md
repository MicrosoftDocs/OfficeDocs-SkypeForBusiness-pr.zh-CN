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
ms.openlocfilehash: 51ee4506a22d866a5ba0f771db47546a8fa15e6e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006910"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-database-schema-in-lync-server-2013"></a>Lync Server 2013 中的持久聊天数据库架构

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-18_

这篇文档介绍了 Lync Server 2013 通信软件中的持久聊天数据库的架构。

持久聊天数据库是指与 Lync Server 2013 后端服务器角色**PersistentChatStore** （对应于 mgc 数据库）和**PersistentChatComplianceStore** （对应于 mgccomp 数据库）对应的数据库。 发布此架构的目的是让您能够生成查询和一定程度地了解如何生成有关聊天使用、活跃的聊天室、置顶帖等内容的有用报告。

<div>


> [!IMPORTANT]  
> 我们保留改进此架构的权利。Microsoft 不对保留此已发布架构的完全向后兼容性做任何保证。



</div>

请遵循以下最佳做法：

  - 不支持\* SELECT//，因为列列表可能会增加。

  - 不支持用户生成的架构修改。

  - 不支持写入操作。

  - 测试您在典型大小的数据库中生成的任何查询，以确保这些查询可以在满足您需求的级别执行。

<div>

## <a name="in-this-section"></a>本部分内容

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

