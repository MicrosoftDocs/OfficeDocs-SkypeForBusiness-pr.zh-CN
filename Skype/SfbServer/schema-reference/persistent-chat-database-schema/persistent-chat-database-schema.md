---
title: 持久聊天数据库架构
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: 本业务服务器文档持久聊天 Skype 在数据库的架构。
ms.openlocfilehash: 1c78ea53438484fb0ad573a815c10ad76f08edca
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="persistent-chat-database-schema"></a><span data-ttu-id="252c4-103">持久聊天数据库架构</span><span class="sxs-lookup"><span data-stu-id="252c4-103">Persistent Chat database schema</span></span>
 
<span data-ttu-id="252c4-104">本业务服务器文档持久聊天 Skype 在数据库的架构。</span><span class="sxs-lookup"><span data-stu-id="252c4-104">This documents the schema of the Persistent Chat database in Skype for Business Server.</span></span>
  
<span data-ttu-id="252c4-105">持续聊天数据库引用后业务服务器端服务器角色 （对应于 mgc 数据库） 的**PersistentChatStore**和**PersistentChatComplianceStore**的 Skype 与对应的数据库 (对应于mgccomp 数据库）。</span><span class="sxs-lookup"><span data-stu-id="252c4-105">The Persistent Chat database refers to the database corresponding to the Skype for Business Server Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="252c4-106">发布此架构的目标是使您能够生成查询并获得一些深入了解构建周围聊天使用率、 活动的房间、 顶海报，等有用的报告。</span><span class="sxs-lookup"><span data-stu-id="252c4-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="252c4-107">我们保留权利发展此架构。</span><span class="sxs-lookup"><span data-stu-id="252c4-107">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="252c4-108">Microsoft 不作任何保证，因此要保持与此发布架构的完全的向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="252c4-108">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span> 
  
<span data-ttu-id="252c4-109">遵循以下最佳做法：</span><span class="sxs-lookup"><span data-stu-id="252c4-109">Follow these best practices:</span></span>
  
- <span data-ttu-id="252c4-110">没有选择\*/ / 支持，因为增长的列的列表。</span><span class="sxs-lookup"><span data-stu-id="252c4-110">No SELECT\* // is supported because the column list can grow.</span></span>
    
- <span data-ttu-id="252c4-111">不支持进行任何用户生成的架构修改。</span><span class="sxs-lookup"><span data-stu-id="252c4-111">No user-generated schema modifications are supported.</span></span>
    
- <span data-ttu-id="252c4-112">不支持任何写操作。</span><span class="sxs-lookup"><span data-stu-id="252c4-112">No write operations are supported.</span></span>
    
- <span data-ttu-id="252c4-113">测试基础 representatively 大小的数据库，以确保查询可以执行以满足您需要的级别，您的任何查询。</span><span class="sxs-lookup"><span data-stu-id="252c4-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="252c4-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="252c4-114">In this section</span></span>

- [<span data-ttu-id="252c4-115">持久的聊天服务器表的列表</span><span class="sxs-lookup"><span data-stu-id="252c4-115">List of Persistent Chat Server tables</span></span>](list-of-persistent-chat-server-tables.md)
    
- [<span data-ttu-id="252c4-116">持久的聊天服务器的法规遵从性中的表列表 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="252c4-116">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>](list-of-persistent-chat-server-compliance-tables.md)
    
- [<span data-ttu-id="252c4-117">持久的聊天服务器表详细信息</span><span class="sxs-lookup"><span data-stu-id="252c4-117">Persistent Chat Server table details</span></span>](persistent-chat-server-table-details.md)
    
- [<span data-ttu-id="252c4-118">持续聊天数据库查询的示例</span><span class="sxs-lookup"><span data-stu-id="252c4-118">Sample Persistent Chat database queries</span></span>](sample-persistent-chat-database-queries.md)
    

