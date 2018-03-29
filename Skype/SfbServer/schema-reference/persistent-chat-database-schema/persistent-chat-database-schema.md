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
# <a name="persistent-chat-database-schema"></a>持久聊天数据库架构
 
本业务服务器文档持久聊天 Skype 在数据库的架构。
  
持续聊天数据库引用后业务服务器端服务器角色 （对应于 mgc 数据库） 的**PersistentChatStore**和**PersistentChatComplianceStore**的 Skype 与对应的数据库 (对应于mgccomp 数据库）。 发布此架构的目标是使您能够生成查询并获得一些深入了解构建周围聊天使用率、 活动的房间、 顶海报，等有用的报告。
  
> [!IMPORTANT]
> 我们保留权利发展此架构。 Microsoft 不作任何保证，因此要保持与此发布架构的完全的向后兼容性。 
  
遵循以下最佳做法：
  
- 没有选择\*/ / 支持，因为增长的列的列表。
    
- 不支持进行任何用户生成的架构修改。
    
- 不支持任何写操作。
    
- 测试基础 representatively 大小的数据库，以确保查询可以执行以满足您需要的级别，您的任何查询。
    
## <a name="in-this-section"></a>本节内容

- [持久的聊天服务器表的列表](list-of-persistent-chat-server-tables.md)
    
- [持久的聊天服务器的法规遵从性中的表列表 Skype 业务服务器](list-of-persistent-chat-server-compliance-tables.md)
    
- [持久的聊天服务器表详细信息](persistent-chat-server-table-details.md)
    
- [持续聊天数据库查询的示例](sample-persistent-chat-database-queries.md)
    

