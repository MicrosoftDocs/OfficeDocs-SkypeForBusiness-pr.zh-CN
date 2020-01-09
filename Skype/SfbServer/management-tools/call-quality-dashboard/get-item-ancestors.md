---
title: 获取项目上级
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: 摘要：了解作为项目服务的一部分的 "获取项目上级" 操作。 项目服务是适用于呼叫质量仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。
ms.openlocfilehash: c82ae699cab0bf812f281fc2f2ad54323bcf8f7f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992679"
---
# <a name="get-item-ancestors"></a>获取项目上级
 
**摘要：** 了解 "获取项目上级" 操作，它是项目服务的一部分。 项目服务是适用于呼叫质量仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。
  
"获取项目上级" 操作是 "知识库 API for 通话质量" 仪表板中的项目服务的一部分。
  
## <a name="get-item-ancestors"></a>获取项目上级

获取项目祖先从存储库返回特定项目上级。
  

|**种**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|获取  <br/> |https://\<portal\>/QoERepositoryService/repository/itemAncestors/{itemId}  <br/> |HTTP/1。1  <br/> |
   
 **URI 参数**-无。
  
 **请求标题**-无其他标题。
  
 **请求正文**-无。
  
 **响应**-响应包括 HTTP 状态代码和一组响应标头。
  
 **状态代码**-成功的操作返回状态代码200（OK）。 如果找不到指定的用户 ID，将返回状态代码404（未找到）。
  
 **响应标题**-无其他标题。
  
 **响应正文**-下面是 JSON 中的示例响应负载。
  
```json
[{
"item1": 1653,
"item2": 0,
"item3": "Audio Streams Monthly Trend"
},
{
"item1": 1652,
"item2": 1,
"item3": "All Audio Streams"
}]
```

 *Item1* -项目的 ID。
  
 *Item2* -深度指项目的距离。 0是直接父项。
  
 *Item3* -项目的标题。
  

