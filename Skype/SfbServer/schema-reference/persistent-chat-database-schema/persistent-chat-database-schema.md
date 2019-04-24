---
title: 持久聊天数据库架构
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: 这业务服务器记录 Skype 的持久聊天数据库的架构。
ms.openlocfilehash: 37b22077157def7ea25a5cf70b23a0272a58956e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212689"
---
# <a name="persistent-chat-database-schema"></a>持久聊天数据库架构
 
这业务服务器记录 Skype 的持久聊天数据库的架构。
  
持久聊天数据库是指后业务服务器端服务器角色**PersistentChatStore** （对应于 mgc 数据库） 和**PersistentChatComplianceStore** Skype 与对应的数据库 (对应于mgccomp 数据库）。 发布此架构的目标是使您能够生成查询和深入了解一些构建周围聊天使用情况、 活动聊天室、 顶部海报、 等有用报告。
  
> [!IMPORTANT]
> 我们保留发展此架构的权利。 Microsoft 不作任何保证维护与此已发布架构完全的向后兼容性。 
  
请遵循以下最佳做法：
  
- 没有选择\*/ / 支持，因为列列表可能增大。
    
- 不支持用户生成的架构进行任何修改。
    
- 支持没有写操作。
    
- 测试在典型大小的数据库，以确保这些查询可以执行以满足您需求的级别生成的任何查询。
    
## <a name="in-this-section"></a>本节内容

- [持久聊天服务器表列表](list-of-persistent-chat-server-tables.md)
    
- [持久聊天服务器合规性中的表列表 Skype 业务服务器](list-of-persistent-chat-server-compliance-tables.md)
    
- [持久聊天服务器表详细信息](persistent-chat-server-table-details.md)
    
- [示例持久聊天数据库查询](sample-persistent-chat-database-queries.md)
    

