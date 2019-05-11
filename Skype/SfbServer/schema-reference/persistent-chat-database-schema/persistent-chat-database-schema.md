---
title: 持久聊天数据库架构
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: 这业务服务器记录 Skype 的持久聊天数据库的架构。
ms.openlocfilehash: 5e10f47a7eeb04de08766bae2957773db35d88f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930006"
---
# <a name="persistent-chat-database-schema"></a><span data-ttu-id="51e66-103">持久聊天数据库架构</span><span class="sxs-lookup"><span data-stu-id="51e66-103">Persistent Chat database schema</span></span>
 
<span data-ttu-id="51e66-104">这业务服务器记录 Skype 的持久聊天数据库的架构。</span><span class="sxs-lookup"><span data-stu-id="51e66-104">This documents the schema of the Persistent Chat database in Skype for Business Server.</span></span>
  
<span data-ttu-id="51e66-105">持久聊天数据库是指后业务服务器端服务器角色**PersistentChatStore** （对应于 mgc 数据库） 和**PersistentChatComplianceStore** Skype 与对应的数据库 (对应于mgccomp 数据库）。</span><span class="sxs-lookup"><span data-stu-id="51e66-105">The Persistent Chat database refers to the database corresponding to the Skype for Business Server Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="51e66-106">发布此架构的目标是使您能够生成查询和深入了解一些构建周围聊天使用情况、 活动聊天室、 顶部海报、 等有用报告。</span><span class="sxs-lookup"><span data-stu-id="51e66-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="51e66-107">我们保留发展此架构的权利。</span><span class="sxs-lookup"><span data-stu-id="51e66-107">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="51e66-108">Microsoft 不作任何保证维护与此已发布架构完全的向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="51e66-108">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span> 
  
<span data-ttu-id="51e66-109">请遵循以下最佳做法：</span><span class="sxs-lookup"><span data-stu-id="51e66-109">Follow these best practices:</span></span>
  
- <span data-ttu-id="51e66-110">没有选择\*/ / 支持，因为列列表可能增大。</span><span class="sxs-lookup"><span data-stu-id="51e66-110">No SELECT\* // is supported because the column list can grow.</span></span>
    
- <span data-ttu-id="51e66-111">不支持用户生成的架构进行任何修改。</span><span class="sxs-lookup"><span data-stu-id="51e66-111">No user-generated schema modifications are supported.</span></span>
    
- <span data-ttu-id="51e66-112">支持没有写操作。</span><span class="sxs-lookup"><span data-stu-id="51e66-112">No write operations are supported.</span></span>
    
- <span data-ttu-id="51e66-113">测试在典型大小的数据库，以确保这些查询可以执行以满足您需求的级别生成的任何查询。</span><span class="sxs-lookup"><span data-stu-id="51e66-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="51e66-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="51e66-114">In this section</span></span>

- [<span data-ttu-id="51e66-115">持久聊天服务器表列表</span><span class="sxs-lookup"><span data-stu-id="51e66-115">List of Persistent Chat Server tables</span></span>](list-of-persistent-chat-server-tables.md)
    
- [<span data-ttu-id="51e66-116">持久聊天服务器合规性中的表列表 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="51e66-116">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>](list-of-persistent-chat-server-compliance-tables.md)
    
- [<span data-ttu-id="51e66-117">持久聊天服务器表详细信息</span><span class="sxs-lookup"><span data-stu-id="51e66-117">Persistent Chat Server table details</span></span>](persistent-chat-server-table-details.md)
    
- [<span data-ttu-id="51e66-118">示例持久聊天数据库查询</span><span class="sxs-lookup"><span data-stu-id="51e66-118">Sample Persistent Chat database queries</span></span>](sample-persistent-chat-database-queries.md)
    

