---
title: Lync Server 2013：持久聊天数据库架构
description: Lync Server 2013：持久聊天数据库架构。
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
ms.openlocfilehash: 66151201f65310cc8e6d3f2251be4f86ce2be15d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545148"
---
# <a name="persistent-chat-database-schema-in-lync-server-2013"></a>Lync Server 2013 中的持久聊天数据库架构

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-18_

这篇文档介绍了 Lync Server 2013 通信软件中的持久聊天数据库的架构。

Persistent 聊天数据库是指与 Lync Server 2013 后端服务器角色对应的数据库。 **PersistentChatStore** (对应于 mgc 数据库) 和 **PersistentChatComplianceStore** (对应于 mgccomp 数据库) 。 发布此架构的目的是让您能够生成查询和一定程度地了解如何生成有关聊天使用、活跃的聊天室、置顶帖等内容的有用报告。

<div>


> [!IMPORTANT]  
> 我们保留改进此架构的权利。Microsoft 不对保留此已发布架构的完全向后兼容性做任何保证。



</div>

请遵循以下最佳做法：

  - 不 \* 支持 SELECT//，因为列列表可能会增加。

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

