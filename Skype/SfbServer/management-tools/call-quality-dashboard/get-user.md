---
title: 获取用户
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
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 摘要：了解作为用户服务的一部分的"获取用户"操作。 用户服务是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是 Skype for Business Server 的工具。
ms.openlocfilehash: dd2bb5e46ddbe3e65faf441a11e39cbc5429e473
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832412"
---
# <a name="get-user"></a>获取用户
 
**摘要：** 了解作为用户服务的一部分的"获取用户"操作。 用户服务是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是 Skype for Business Server 的工具。
  
Get Users 操作是呼叫质量仪表板的存储库 API 中的用户服务的一部分。
  
## <a name="get-user"></a>获取用户

Get User 从存储库返回用户记录。
  
|**方法**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数** - 无。
  
 **请求标头** - 无其他标头。
  
 **请求正文** - 无。
  
 **响应** - 响应包括 HTTP 状态代码和一组响应标头。
  
 **状态代码** - 成功操作返回状态代码 200 (确定) 。 如果找不到指定的用户 ID，它将返回状态代码 404 (未找到) 。
  
 **响应标头** - 无其他标头。
  
 **响应正文** - 下面是 JSON 中的示例响应负载。
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 *userId*  - 用户的 ID。
  
 *loginName*  - 常规用户的外部用户标识。 如果 Windows 身份验证用于验证用户，则这可能是用户的 FQDN。
  
 *defaultItemId*  - 此用户的默认项目的 ID。 默认项目是与用户关联的最顶层项目。 此用户拥有的所有其他项目都可以从默认项目导航。
  
> [!NOTE]
> 提供  `defaultItemId` 获取项目操作的值以检索默认项目的详细信息。
  

