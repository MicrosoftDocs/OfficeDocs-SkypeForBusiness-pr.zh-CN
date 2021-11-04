---
title: 获取用户设置
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 摘要：了解"获取用户设置操作，该操作是 User 设置 服务的一部分。 User 设置 Service 是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是一种用于Skype for Business Server。
ms.openlocfilehash: b7be08df46aa63287d931a566d26671bfecfc3b8
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778172"
---
# <a name="get-user-settings"></a>获取用户设置
 
**摘要：** 了解"获取用户设置操作，该操作是 User 设置 Service 的一部分。 User 设置 Service 是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是一种用于Skype for Business Server。
  
Get User 设置 操作是呼叫质量仪表板的存储库 API 设置 User 设置 Service 的一部分。
  
## <a name="get-user-settings"></a>获取用户设置

Get User 设置返回指定用户的设置列表。
  

|**方法**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数**
  
- *effective*  - 可选。 此参数仅在使用特殊的用户 ID 默认值时适用。 在其他情形下，将忽略它。 `True` 返回有效的用户设置 `false` ，并仅返回默认 (用户) 。
    
  **请求标头** - 无其他标头。
  
  **请求正文** - 无。
  
  **响应** - 响应包括 HTTP 状态代码和一组响应标头。
  
  **状态代码** - 成功操作返回状态代码 200， (确定) 。
  
  **响应标头** - 无其他标头。
  
  **响应正文** - 下面是 JSON 中的示例响应有效负载。
  
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
