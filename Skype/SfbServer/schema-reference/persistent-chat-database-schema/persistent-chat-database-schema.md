---
title: 持久聊天数据库架构
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: 此文档介绍 Skype for Business 服务器中持久聊天数据库的架构。
ms.openlocfilehash: 9a3e09a03f764f8866865e08259cbaac12a1c554
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295613"
---
# <a name="persistent-chat-database-schema"></a><span data-ttu-id="45dbb-103">持久聊天数据库架构</span><span class="sxs-lookup"><span data-stu-id="45dbb-103">Persistent Chat database schema</span></span>
 
<span data-ttu-id="45dbb-104">此文档介绍 Skype for Business 服务器中持久聊天数据库的架构。</span><span class="sxs-lookup"><span data-stu-id="45dbb-104">This documents the schema of the Persistent Chat database in Skype for Business Server.</span></span>
  
<span data-ttu-id="45dbb-105">持久聊天数据库指的是对应于 Skype for Business 服务器后端服务器角色的数据库**PersistentChatStore** (对应于 mgc 数据库) 和**PersistentChatComplianceStore** (对应于mgccomp 数据库)。</span><span class="sxs-lookup"><span data-stu-id="45dbb-105">The Persistent Chat database refers to the database corresponding to the Skype for Business Server Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="45dbb-106">发布此架构的目的是使你能够构建查询并深入了解如何构建有关聊天使用、活动会议室、热门海报等的有用报告。</span><span class="sxs-lookup"><span data-stu-id="45dbb-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="45dbb-107">我们保留发展此架构的权利。</span><span class="sxs-lookup"><span data-stu-id="45dbb-107">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="45dbb-108">Microsoft 不会确保保持与此已发布架构的完全向后兼容。</span><span class="sxs-lookup"><span data-stu-id="45dbb-108">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span> 
  
<span data-ttu-id="45dbb-109">请遵循以下最佳做法:</span><span class="sxs-lookup"><span data-stu-id="45dbb-109">Follow these best practices:</span></span>
  
- <span data-ttu-id="45dbb-110">不支持\* SELECT//, 因为列列表可以增长。</span><span class="sxs-lookup"><span data-stu-id="45dbb-110">No SELECT\* // is supported because the column list can grow.</span></span>
    
- <span data-ttu-id="45dbb-111">不支持用户生成的架构修改。</span><span class="sxs-lookup"><span data-stu-id="45dbb-111">No user-generated schema modifications are supported.</span></span>
    
- <span data-ttu-id="45dbb-112">不支持写入操作。</span><span class="sxs-lookup"><span data-stu-id="45dbb-112">No write operations are supported.</span></span>
    
- <span data-ttu-id="45dbb-113">测试在 representatively 大小的数据库上生成的任何查询, 以确保查询可以按级别执行, 以满足你的需求。</span><span class="sxs-lookup"><span data-stu-id="45dbb-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="45dbb-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="45dbb-114">In this section</span></span>

- [<span data-ttu-id="45dbb-115">持久聊天服务器表列表</span><span class="sxs-lookup"><span data-stu-id="45dbb-115">List of Persistent Chat Server tables</span></span>](list-of-persistent-chat-server-tables.md)
    
- [<span data-ttu-id="45dbb-116">Skype for Business 服务器中持久聊天服务器合规性表的列表</span><span class="sxs-lookup"><span data-stu-id="45dbb-116">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>](list-of-persistent-chat-server-compliance-tables.md)
    
- [<span data-ttu-id="45dbb-117">持久聊天服务器表详细信息</span><span class="sxs-lookup"><span data-stu-id="45dbb-117">Persistent Chat Server table details</span></span>](persistent-chat-server-table-details.md)
    
- [<span data-ttu-id="45dbb-118">示例持久聊天数据库查询</span><span class="sxs-lookup"><span data-stu-id="45dbb-118">Sample Persistent Chat database queries</span></span>](sample-persistent-chat-database-queries.md)
    

