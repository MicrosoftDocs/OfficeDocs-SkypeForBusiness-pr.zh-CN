---
title: 持久聊天数据库架构
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: 这将记录持久聊天数据库中持久聊天数据库的Skype for Business Server。
ms.openlocfilehash: 6f35e947f1cc0c36d6be743d57934453053f4e5c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759344"
---
# <a name="persistent-chat-database-schema"></a>持久聊天数据库架构
 
这将记录持久聊天数据库中持久聊天数据库的Skype for Business Server。
  
持久聊天数据库指与 Skype for Business Server 后端服务器角色 **PersistentChatStore** (对应的数据库，对应于 mgc 数据库) 和 **PersistentChatComplianceStore** (对应于 mgccomp 数据库) 。 发布此架构的目的是让您能够生成查询和一定程度地了解如何生成有关聊天使用、活跃的聊天室、置顶帖等内容的有用报告。
  
> [!IMPORTANT]
> 我们保留改进此架构的权利。Microsoft 不对保留此已发布架构的完全向后兼容性做任何保证。 
  
请遵循以下最佳做法：
  
- 不支持 SELECT \* // ，因为列列表可能会增大。
    
- 不支持用户生成的架构修改。
    
- 不支持写入操作。
    
- 测试您在典型大小的数据库中生成的任何查询，以确保这些查询可以在满足您需求的级别执行。
    
## <a name="in-this-section"></a>本节内容

- [持久聊天服务器表列表](list-of-persistent-chat-server-tables.md)
    
- [持久聊天服务器合规性表的列表Skype for Business Server](list-of-persistent-chat-server-compliance-tables.md)
    
- [持久聊天服务器表详细信息](persistent-chat-server-table-details.md)
    
- [示例持久聊天数据库查询](sample-persistent-chat-database-queries.md)
    

