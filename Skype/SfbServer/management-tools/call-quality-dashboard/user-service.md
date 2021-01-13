---
title: 适用于 CQD 的用户服务
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
description: 摘要：了解用户服务，它是通话质量仪表板的存储库 API 的一部分。 通话质量仪表板是 Skype for Business Server 的工具。
ms.openlocfilehash: d9f4b771a1bf5efeece4f8fb87195d8567f0426e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803072"
---
# <a name="user-service-for-cqd"></a>适用于 CQD 的用户服务
 
**摘要：** 了解用户服务，它是通话质量仪表板的存储库 API 的一部分。 通话质量仪表板是 Skype for Business Server 的工具。
  
用户服务是通话质量仪表板存储库 API 的一部分。
  
## <a name="user-service"></a>用户服务

存储库 API 提供了简化的用户管理模型，其中用户预配 (自动和隐式) 用户帐户。 当用户首次对存储库 API 提出请求时，存储库将创建新的用户记录。 
  
呼叫质量仪表板还会自动为新用户创建用户专用项目。 新用户专用项目是系统用户项目的完整克隆。 这样，用户就可以从自己的报表和查询副本开始，他们可以立即开始自定义。 
  
> [!NOTE]
> 使用通话质量仪表板，用户可以随时重置其专用项目。 
  
 **特殊用户 ID**
  
存储库 API 包括需要整数值以指定特定用户的 REST API URI。 示例  `https://<portal>/QoERepositoryService/repository/user/{userId}` ：。 在这里，{userId} 应替换为整数值，如 0、1 等。
  
此外，存储库 API 将在 URI 中的 {userId} 接受两个特殊用户 ID。
  
-  *default*  - 表示当前正在与 API 交互的用户。 这允许应用程序访问当前用户的内容，而无需跟踪实际用户 ID 值。 示例：`https://<portal>/QoERepositoryService/repository/user/default`。
    
-  *system*  - 表示系统用户。 这允许应用程序在不知道实际用户 ID 值的情况下访问系统用户的内容。 示例：`https://<portal>/QoERepositoryService/repository/user/system`。
    
除非另有说明，否则特殊用户 ID 可在 URI 中的 {userId} 使用。 
  
REST 操作包含在下表中。
  
|**操作**|**说明**|
|:-----|:-----|
|[获取用户](get-users.md) <br/> |返回存储库中的用户列表。  <br/> |
|[获取用户](get-user.md) <br/> |返回用户记录。  <br/> |
   

