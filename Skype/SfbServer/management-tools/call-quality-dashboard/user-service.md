---
title: CQD 的用户服务
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 摘要：了解用户服务，它是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是一种用于Skype for Business Server。
ms.openlocfilehash: 412f7b17e6190a35e79998d47a0d5cfa8459f6934d19761f5d0b5d65e5e91ba2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54324191"
---
# <a name="user-service-for-cqd"></a>CQD 的用户服务
 
**摘要：** 了解用户服务，它是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是一种用于Skype for Business Server。
  
用户服务是通话质量仪表板存储库 API 的一部分。
  
## <a name="user-service"></a>用户服务

存储库 API 提供了简化的用户管理模型，其中用户预配 (自动和隐式) 用户帐户。 当用户首次针对存储库 API 提出请求时，存储库会创建新的用户记录。 
  
呼叫质量仪表板还会自动为新用户创建用户专用项目。 新用户专用项是系统用户项的完整克隆。 这样，用户就可以从自己的报告和查询副本开始，他们可以立即开始自定义。 
  
> [!NOTE]
> 使用呼叫质量仪表板，用户可以随时重置其专用项目。 
  
 **特殊用户 ID**
  
存储库 API 包括需要整数值以指定特定用户的 REST API URI。 示例  `https://<portal>/QoERepositoryService/repository/user/{userId}` ：。 此处，{userId} 应替换为整数值，如 0、1 等。
  
此外，存储库 API 将在 URI 中的 {userId} 接受两个特殊用户 ID。
  
-  *default*  - 表示当前正在与 API 交互的用户。 这允许应用程序访问当前用户的内容，而无需跟踪实际用户 ID 值。 示例：`https://<portal>/QoERepositoryService/repository/user/default`。
    
-  *system*  - 表示系统用户。 这允许应用程序在不知道实际用户 ID 值的情况下访问系统用户的内容。 示例：`https://<portal>/QoERepositoryService/repository/user/system`。
    
除非另有说明，否则特殊用户 ID 可在 URI 中的 {userId} 处使用。 
  
REST 操作包含在下表中。
  
|**操作**|**说明**|
|:-----|:-----|
|[获取用户](get-users.md) <br/> |返回存储库中的用户列表。  <br/> |
|[获取用户](get-user.md) <br/> |返回用户记录。  <br/> |
   

