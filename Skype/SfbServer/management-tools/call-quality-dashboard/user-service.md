---
title: CQD 的用户服务
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 摘要： 了解用户的服务，这是呼叫质量仪表板存储库 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: c4bb2395ea3fa4541140a7966bbfb554ef53c168
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="user-service-for-cqd"></a>CQD 的用户服务
 
**摘要：**了解用户的服务，这是呼叫质量仪表板存储库 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
  
用户服务是为呼叫质量仪表板存储库 API 的一部分。
  
## <a name="user-service"></a>用户服务

知识库 API 提供了自动和隐式资源调配 （创建新用户帐户） 的用户所在的简化的用户管理模型。 当用户第一次进行针对存储库 API 的请求时，存储库会创建新的用户记录。 
  
通话质量面板还会自动创建一个用户专门为新用户的项目。 新的用户专用项目是完全克隆的系统用户的项目。 这样一来，用户开始自己的报告和查询，他们立即可以开始自定义副本。 
  
> [!NOTE]
> 使用调用质量面板，用户可以重置其专用的项目任何时候。 
  
 **特殊用户 Id**
  
知识库 API 包括需要一个整数值，以指定特定用户的 REST API Uri。 例如： `https://<portal>/QoERepositoryService/repository/user/{userId}`。 在这里，{用户 Id} 应由一个整数值，如从 0，1，等等。
  
此外，存储库 API 将接受用户 {Id} 在 Uri 中的两个特殊的用户 Id。
  
-  *默认*的代表目前正在与 API 进行交互的用户。 这允许应用程序访问当前用户的内容，而无需跟踪的实际用户 ID 值。 例如： ` https://<portal>/QoERepositoryService/repository/user/default`。
    
-  *系统*-代表系统用户。 这允许应用程序访问系统用户的内容，而无需知道实际用户 ID 值。 例如： `https://<portal>/QoERepositoryService/repository/user/system`。
    
除非另行说明，否则这些特殊用户 Id 可在用户 {Id} Uri 中。 
  
下表中包括的其余操作。
  
|**操作**|**说明**|
|:-----|:-----|
|[获取用户](get-users.md) <br/> |返回在存储库中的用户列表。  <br/> |
|[获取用户](get-user.md) <br/> |返回用户记录。  <br/> |
   

