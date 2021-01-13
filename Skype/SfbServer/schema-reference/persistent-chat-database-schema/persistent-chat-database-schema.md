---
title: 持久聊天数据库架构
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: 这将记录 Skype for Business Server 中的持久聊天数据库的架构。
ms.openlocfilehash: ba50f4391ce35d8a938318e96e1483bbfe0e3dfa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809872"
---
# <a name="persistent-chat-database-schema"></a><span data-ttu-id="32342-103">持久聊天数据库架构</span><span class="sxs-lookup"><span data-stu-id="32342-103">Persistent Chat database schema</span></span>
 
<span data-ttu-id="32342-104">这将记录 Skype for Business Server 中的持久聊天数据库的架构。</span><span class="sxs-lookup"><span data-stu-id="32342-104">This documents the schema of the Persistent Chat database in Skype for Business Server.</span></span>
  
<span data-ttu-id="32342-105">持久聊天数据库是指与与 mgccomp 数据库 (对应的 mgc 数据库) 和 **PersistentChatComplianceStore** (对应的 Skype for Business Server 后端服务器角色 **PersistentChatStore**) 。</span><span class="sxs-lookup"><span data-stu-id="32342-105">The Persistent Chat database refers to the database corresponding to the Skype for Business Server Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="32342-106">发布此架构的目的是让您能够生成查询和一定程度地了解如何生成有关聊天使用、活跃的聊天室、置顶帖等内容的有用报告。</span><span class="sxs-lookup"><span data-stu-id="32342-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="32342-p102">我们保留改进此架构的权利。Microsoft 不对保留此已发布架构的完全向后兼容性做任何保证。</span><span class="sxs-lookup"><span data-stu-id="32342-p102">We reserve the right to evolve this schema. Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span> 
  
<span data-ttu-id="32342-109">请遵循以下最佳做法：</span><span class="sxs-lookup"><span data-stu-id="32342-109">Follow these best practices:</span></span>
  
- <span data-ttu-id="32342-110">不支持 SELECT \* //，因为列列表可能会增长。</span><span class="sxs-lookup"><span data-stu-id="32342-110">No SELECT\* // is supported because the column list can grow.</span></span>
    
- <span data-ttu-id="32342-111">不支持用户生成的架构修改。</span><span class="sxs-lookup"><span data-stu-id="32342-111">No user-generated schema modifications are supported.</span></span>
    
- <span data-ttu-id="32342-112">不支持写入操作。</span><span class="sxs-lookup"><span data-stu-id="32342-112">No write operations are supported.</span></span>
    
- <span data-ttu-id="32342-113">测试您在典型大小的数据库中生成的任何查询，以确保这些查询可以在满足您需求的级别执行。</span><span class="sxs-lookup"><span data-stu-id="32342-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="32342-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="32342-114">In this section</span></span>

- [<span data-ttu-id="32342-115">持久聊天服务器表列表</span><span class="sxs-lookup"><span data-stu-id="32342-115">List of Persistent Chat Server tables</span></span>](list-of-persistent-chat-server-tables.md)
    
- [<span data-ttu-id="32342-116">Skype for Business Server 中的持久聊天服务器合规性表列表</span><span class="sxs-lookup"><span data-stu-id="32342-116">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>](list-of-persistent-chat-server-compliance-tables.md)
    
- [<span data-ttu-id="32342-117">持久聊天服务器表详细信息</span><span class="sxs-lookup"><span data-stu-id="32342-117">Persistent Chat Server table details</span></span>](persistent-chat-server-table-details.md)
    
- [<span data-ttu-id="32342-118">示例持久聊天数据库查询</span><span class="sxs-lookup"><span data-stu-id="32342-118">Sample Persistent Chat database queries</span></span>](sample-persistent-chat-database-queries.md)
    

