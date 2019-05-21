---
title: CQD 用户服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: '摘要: 了解用户服务, 它是 "呼叫质量" 仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。'
ms.openlocfilehash: 3ef76d26faa27034d3f092608b52676332b254a1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274518"
---
# <a name="user-service-for-cqd"></a>CQD 用户服务
 
**摘要:** 了解用户服务, 该服务是 "呼叫质量" 仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。
  
用户服务是适用于呼叫质量仪表板的知识库 API 的一部分。
  
## <a name="user-service"></a>用户服务

知识库 API 提供了简化的用户管理模型, 在此模型中, 用户预配 (创建新用户帐户) 是自动和隐式的。 当用户首次向存储库 API 发出请求时, 存储库会创建新的用户记录。 
  
通话质量仪表板还会自动为新用户创建用户专用项目。 新的用户专用项目是系统用户项目的完整克隆。 这样, 用户就可以从自己的报表和查询副本开始自定义。 
  
> [!NOTE]
> 使用 "通话质量" 仪表板, 用户可以随时重置其专用项目。 
  
 **特殊用户 Id**
  
存储库 API 包括需要整数值以指定特定用户的 REST API Uri。 示例: `https://<portal>/QoERepositoryService/repository/user/{userId}`。 此处, {userId} 应由整数值 (如0、1等) 替换。
  
此外, 知识库 API 将在 Uri 中的 {userId} 处接受两个特殊的用户 Id。
  
-  *默认值*-表示当前与 API 交互的用户。 这允许应用程序访问当前用户的内容, 而无需跟踪实际的用户 ID 值。 示例: ` https://<portal>/QoERepositoryService/repository/user/default`。
    
-  *system* -表示系统用户。 这使应用程序无需知道实际的用户 ID 值即可访问系统用户的内容。 示例: `https://<portal>/QoERepositoryService/repository/user/system`。
    
除非另有说明, 否则可以在 Uri 中使用 {userId} 的特殊用户 Id。 
  
下表中包括其余操作。
  
|**操作**|**说明**|
|:-----|:-----|
|[获取用户](get-users.md) <br/> |返回存储库中的用户列表。  <br/> |
|[获取用户](get-user.md) <br/> |返回用户记录。  <br/> |
   

