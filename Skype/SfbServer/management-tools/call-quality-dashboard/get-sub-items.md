---
title: 获取子项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: '摘要: 了解 "获取子项目" 操作, 该操作是项目服务的一部分。 项目服务是适用于呼叫质量仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。'
ms.openlocfilehash: 7be427ed4ea90cd46c6f8cea4ffe3a97be98479b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274658"
---
# <a name="get-sub-items"></a>获取子项
 
**摘要:** 了解 "获取子项目" 操作, 该操作是项目服务的一部分。 项目服务是适用于呼叫质量仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。
  
"获取子项目" 操作是 "知识库 API for 通话质量" 仪表板中的项目服务的一部分。
  
## <a name="get-sub-items"></a>获取子项

获取子项目返回特定项目的子项目。
  

|**种**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|获取  <br/> |https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem  <br/> |HTTP/1。1  <br/> |
   
 **URI 参数**-无。
  
 **请求标题**-无其他标题。
  
 **请求正文**-无。
  
 **响应**-响应包括 HTTP 状态代码和一组响应标头。
  
 **状态代码**-成功的操作返回状态代码 200 (OK)。 如果找不到指定的用户 ID, 将返回状态代码 404 (未找到)。
  
 **响应标题**-无其他标题。
  
 **响应正文**-下面是 JSON 中的示例响应负载。
  
> [!NOTE]
> 返回 Item 对象的数组。 
  
```
[{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1710,
"userId": 0,
"type": "json"
}]
```

子项目操作返回的 Item 对象仅包含以下三个字段。 
  
 *itemId* -项目的 ID。
  
 *userId* -拥有此项目的用户的 ID。
  
 *type* -内容的类型。 此字段由应用程序设置。
  
> [!NOTE]
>  `Content`和`subItems`字段不包含在响应中, 以减少通过网络传输的数据量。
  

