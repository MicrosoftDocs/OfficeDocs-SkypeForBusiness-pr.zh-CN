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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: 此文档介绍 Skype for Business 服务器中持久聊天数据库的架构。
ms.openlocfilehash: b042f4490648760f4750e45fa1e35e032a8bf8b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814740"
---
# <a name="persistent-chat-database-schema"></a>持久聊天数据库架构
 
此文档介绍 Skype for Business 服务器中持久聊天数据库的架构。
  
持久聊天数据库指对应于 Skype for Business 服务器后端服务器角色的数据库**PersistentChatStore** （对应于 mgc 数据库）和**PersistentChatComplianceStore** （对应于 mgccomp 数据库）。 发布此架构的目的是使你能够构建查询并深入了解如何构建有关聊天使用、活动会议室、热门海报等的有用报告。
  
> [!IMPORTANT]
> 我们保留发展此架构的权利。 Microsoft 不会确保保持与此已发布架构的完全向后兼容。 
  
请遵循以下最佳做法：
  
- 不支持\* SELECT//，因为列列表可以增长。
    
- 不支持用户生成的架构修改。
    
- 不支持写入操作。
    
- 测试在 representatively 大小的数据库上生成的任何查询，以确保查询可以按级别执行，以满足你的需求。
    
## <a name="in-this-section"></a>本节内容

- [持久聊天服务器表列表](list-of-persistent-chat-server-tables.md)
    
- [Skype for Business 服务器中持久聊天服务器合规性表的列表](list-of-persistent-chat-server-compliance-tables.md)
    
- [持久聊天服务器表详细信息](persistent-chat-server-table-details.md)
    
- [示例持久聊天数据库查询](sample-persistent-chat-database-queries.md)
    

