---
title: CQD 的用户服务
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 摘要： 了解用户服务，它是用于呼叫的质量仪表板的存储库 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
ms.openlocfilehash: 4ee4594e86b14655c94472b516b9e04da674e3f0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217640"
---
# <a name="user-service-for-cqd"></a>CQD 的用户服务
 
**摘要：** 了解用户服务，它是用于呼叫的质量仪表板的存储库 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
  
用户服务是用于呼叫的质量仪表板的存储库 API 的一部分。
  
## <a name="user-service"></a>用户服务

存储库 API 提供了其中设置 （创建新的用户帐户） 的用户是自动和隐式简化的用户管理模型。 当用户发出第一次对存储库 API 请求时，存储库创建新用户记录。 
  
呼叫质量仪表板还会自动创建用户专用的新用户的项目。 新的专用用户项目是完整克隆的系统用户的项目。 这种方式，用户开始使用自己的报告和查询，他们会立即开始自定义的副本。 
  
> [!NOTE]
> 使用呼叫质量仪表板，用户可以重置其专用的项目随时随地。 
  
 **特殊的用户 Id**
  
存储库 API 包含需要整数值来指定某个特定用户的 REST API Uri。 示例： `https://<portal>/QoERepositoryService/repository/user/{userId}`。 此处，{userId} 应替换为一个整数值，如 0，1，等。
  
此外，存储库 API 将接受 {userId} 在 Uri 中的两个特殊用户 Id。
  
-  *默认*-表示当前正在使用 API 进行交互的用户。 这允许应用程序访问当前用户的内容，而跟踪的实际用户 ID 值。 示例： ` https://<portal>/QoERepositoryService/repository/user/default`。
    
-  *系统*-表示系统用户。 这使应用程序访问系统用户的内容，而无需了解的实际用户 ID 值。 示例： `https://<portal>/QoERepositoryService/repository/user/system`。
    
除非另行说明，特殊用户 Id 可在 {userId} 在 Uri 中。 
  
下表中包含的其余部分操作。
  
|**操作**|**说明**|
|:-----|:-----|
|[获取用户](get-users.md) <br/> |在存储库中返回用户的列表。  <br/> |
|[获取用户](get-user.md) <br/> |返回用户记录。  <br/> |
   

