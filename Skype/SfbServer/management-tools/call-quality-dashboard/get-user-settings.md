---
title: 获取用户设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: '摘要: 了解 "获取用户设置" 操作, 该操作是用户设置服务的一部分。 "用户设置" 服务是 "呼叫质量" 仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。'
ms.openlocfilehash: 8d1bb1da9e9a186cbc10f0c8ba36275348bb7267
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274616"
---
# <a name="get-user-settings"></a>获取用户设置
 
**摘要:** 了解 "获取用户设置" 操作, 该操作是 "用户设置" 服务的一部分。 "用户设置" 服务是 "呼叫质量" 仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。
  
"获取用户设置" 操作是 "资源库 API for 通话质量" 仪表板中的 "用户设置" 服务的一部分。
  
## <a name="get-user-settings"></a>获取用户设置

获取用户设置返回指定用户的设置列表。
  

|**种**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|获取  <br/> |https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting  <br/> |HTTP/1。1  <br/> |
   
 **URI 参数**
  
- *有效*-可选。 仅当使用特殊用户 ID 默认值时, 此参数才适用。 在其他情况下, 它将被忽略。 `True`返回有效的用户设置`false` , 并仅返回用户设置 (默认值)。
    
  **请求标题**-无其他标题。
  
  **请求正文**-无。
  
  **响应**-响应包括 HTTP 状态代码和一组响应标头。
  
  **状态代码**-成功的操作返回状态代码 200 (OK)。
  
  **响应标题**-无其他标题。
  
  **响应正文**-下面是 JSON 中的示例响应负载。
  
```
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
