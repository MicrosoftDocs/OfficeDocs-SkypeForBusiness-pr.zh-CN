---
title: 获取项目
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: '摘要: 了解 "获取项目" 操作, 该操作是项目服务的一部分。 项目服务是适用于呼叫质量仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。'
ms.openlocfilehash: bfd5015603ac73fb48c4e30635cf8ae0fb14bf13
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274714"
---
# <a name="get-item"></a>获取项目
 
**摘要:** 了解 "获取项目" 操作, 该操作是项目服务的一部分。 项目服务是适用于呼叫质量仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。
  
获取项目操作是 "知识库 API for 通话质量" 仪表板中的项目服务的一部分。
  
## <a name="get-item"></a>获取项目

获取项目返回存储库中的特定项目。
  
|**种**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|获取  <br/> |https://\<portal\>/QoERepositoryService/repository/item/{itemId}  <br/> |HTTP/1。1  <br/> |
   
 **URI 参数**-无。
  
 **请求标题**-无其他标题。
  
 **请求正文**-无。
  
 **响应**-响应包括 HTTP 状态代码和一组响应标头。
  
 **状态代码**-成功的操作返回状态代码 200 (OK)。 如果找不到指定的项目 ID, 则会返回状态代码 404 (未找到)。
  
 **响应标题**-无其他标题。
  
 **响应正文**-下面是 JSON 中的示例响应负载。
  
```
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 *itemId* -项目的 ID。
  
 *userId* -拥有此项目的用户的 ID。
  
 *内容*-特定于应用程序的内容。
  
 *type* -内容的类型。 此字段由应用程序设置。
  
 *subItemIds* -子项目的 id (如果有)。 这是一个用于保存调用的 "获取子项目" 操作的简短电路。 应用程序也可以使用 "获取子项目" 操作获取相同的信息。
  

