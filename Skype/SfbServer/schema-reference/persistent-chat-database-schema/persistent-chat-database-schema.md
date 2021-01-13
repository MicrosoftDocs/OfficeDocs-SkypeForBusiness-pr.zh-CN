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
# <a name="persistent-chat-database-schema"></a>持久聊天数据库架构
 
这将记录 Skype for Business Server 中的持久聊天数据库的架构。
  
持久聊天数据库是指与与 mgccomp 数据库 (对应的 mgc 数据库) 和 **PersistentChatComplianceStore** (对应的 Skype for Business Server 后端服务器角色 **PersistentChatStore**) 。 发布此架构的目的是让您能够生成查询和一定程度地了解如何生成有关聊天使用、活跃的聊天室、置顶帖等内容的有用报告。
  
> [!IMPORTANT]
> 我们保留改进此架构的权利。Microsoft 不对保留此已发布架构的完全向后兼容性做任何保证。 
  
请遵循以下最佳做法：
  
- 不支持 SELECT \* //，因为列列表可能会增长。
    
- 不支持用户生成的架构修改。
    
- 不支持写入操作。
    
- 测试您在典型大小的数据库中生成的任何查询，以确保这些查询可以在满足您需求的级别执行。
    
## <a name="in-this-section"></a>本节内容

- [持久聊天服务器表列表](list-of-persistent-chat-server-tables.md)
    
- [Skype for Business Server 中的持久聊天服务器合规性表列表](list-of-persistent-chat-server-compliance-tables.md)
    
- [持久聊天服务器表详细信息](persistent-chat-server-table-details.md)
    
- [示例持久聊天数据库查询](sample-persistent-chat-database-queries.md)
    

