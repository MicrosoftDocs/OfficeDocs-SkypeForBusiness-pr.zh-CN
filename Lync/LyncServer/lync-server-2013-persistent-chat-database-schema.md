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
ms.openlocfilehash: a18cd17686133219ccc60d5e85fd149df190665a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="persistent-chat-database-schema-in-lync-server-2013"></a><span data-ttu-id="9a6f9-102">Lync Server 2013 中的持久聊天数据库架构</span><span class="sxs-lookup"><span data-stu-id="9a6f9-102">Persistent Chat database schema in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a6f9-103">_**上次修改的主题：** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="9a6f9-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="9a6f9-104">这篇文档介绍了 Lync Server 2013 通信软件中的持久聊天数据库的架构。</span><span class="sxs-lookup"><span data-stu-id="9a6f9-104">This documents the schema of the Persistent Chat database in Lync Server 2013 communications software.</span></span>

<span data-ttu-id="9a6f9-105">持久聊天数据库是指与 Lync Server 2013 后端服务器角色**PersistentChatStore** （对应于 mgc 数据库）和**PersistentChatComplianceStore** （对应于 mgccomp 数据库）对应的数据库。</span><span class="sxs-lookup"><span data-stu-id="9a6f9-105">The Persistent Chat database refers to the database corresponding to the Lync Server 2013 Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="9a6f9-106">发布此架构的目的是让您能够生成查询和一定程度地了解如何生成有关聊天使用、活跃的聊天室、置顶帖等内容的有用报告。</span><span class="sxs-lookup"><span data-stu-id="9a6f9-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9a6f9-p102">我们保留改进此架构的权利。Microsoft 不对保留此已发布架构的完全向后兼容性做任何保证。</span><span class="sxs-lookup"><span data-stu-id="9a6f9-p102">We reserve the right to evolve this schema. Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span>



</div>

<span data-ttu-id="9a6f9-109">请遵循以下最佳做法：</span><span class="sxs-lookup"><span data-stu-id="9a6f9-109">Follow these best practices:</span></span>

  - <span data-ttu-id="9a6f9-110">不支持\* SELECT//，因为列列表可能会增加。</span><span class="sxs-lookup"><span data-stu-id="9a6f9-110">No SELECT\* // is supported because the column list can grow.</span></span>

  - <span data-ttu-id="9a6f9-111">不支持用户生成的架构修改。</span><span class="sxs-lookup"><span data-stu-id="9a6f9-111">No user-generated schema modifications are supported.</span></span>

  - <span data-ttu-id="9a6f9-112">不支持写入操作。</span><span class="sxs-lookup"><span data-stu-id="9a6f9-112">No write operations are supported.</span></span>

  - <span data-ttu-id="9a6f9-113">测试您在典型大小的数据库中生成的任何查询，以确保这些查询可以在满足您需求的级别执行。</span><span class="sxs-lookup"><span data-stu-id="9a6f9-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9a6f9-114">本部分内容</span><span class="sxs-lookup"><span data-stu-id="9a6f9-114">In This Section</span></span>

  - [<span data-ttu-id="9a6f9-115">Lync Server 2013 中持久聊天服务器表的列表</span><span class="sxs-lookup"><span data-stu-id="9a6f9-115">List of Persistent Chat Server tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [<span data-ttu-id="9a6f9-116">Lync Server 2013 中持久聊天服务器合规性表的列表</span><span class="sxs-lookup"><span data-stu-id="9a6f9-116">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [<span data-ttu-id="9a6f9-117">Lync Server 2013 中的持久聊天服务器表详细信息</span><span class="sxs-lookup"><span data-stu-id="9a6f9-117">Persistent Chat Server table details in Lync Server 2013</span></span>](lync-server-2013-persistent-chat-server-table-details.md)

  - [<span data-ttu-id="9a6f9-118">Lync Server 2013 的示例持久聊天数据库查询</span><span class="sxs-lookup"><span data-stu-id="9a6f9-118">Sample Persistent Chat database queries for Lync Server 2013</span></span>](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

