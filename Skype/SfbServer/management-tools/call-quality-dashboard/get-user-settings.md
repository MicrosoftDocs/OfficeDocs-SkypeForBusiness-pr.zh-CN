---
title: 获取用户设置
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
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 摘要：了解作为用户设置服务的一部分的"获取用户设置"操作。 用户设置服务是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是 Skype for Business Server 的工具。
ms.openlocfilehash: e2ebf39ba5a7de5d36a8b1ea0441808b6e71f97b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832472"
---
# <a name="get-user-settings"></a>获取用户设置
 
**摘要：** 了解"获取用户设置"操作，该操作是用户设置服务的一部分。 用户设置服务是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是 Skype for Business Server 的工具。
  
Get User Settings 操作是呼叫质量仪表板的存储库 API 中的用户设置服务的一部分。
  
## <a name="get-user-settings"></a>获取用户设置

Get User Settings returns a list of settings for a specified user.
  

|**方法**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数**
  
- *有效*  - 可选。 此参数仅在使用特殊的用户 ID 默认值时适用。 在其他情况下，它将被忽略。 `True` 返回有效的用户设置， `false` 并仅返回默认 (用户) 。
    
  **请求标头** - 无其他标头。
  
  **请求正文** - 无。
  
  **响应** - 响应包括 HTTP 状态代码和一组响应标头。
  
  **状态代码** - 成功操作返回状态代码 200 (确定) 。
  
  **响应标头** - 无其他标头。
  
  **响应正文** - 下面是 JSON 中的示例响应负载。
  
```json
[{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
},
{
"userId": 6,
"key": "ShowTimeStamps",
"value": "true"
}]
```
