---
title: 获取项目上级
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: 摘要：了解作为项目服务的一部分的"获取项目上级"操作。 项目服务是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是一种用于Skype for Business Server。
ms.openlocfilehash: 0cfc5385af1c0c821d4dc64e9ba0e0bd092fe833
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393734"
---
# <a name="get-item-ancestors"></a>获取项目上级
 
**摘要：** 了解作为项目服务的一部分的"获取项目上级"操作。 项目服务是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是一种用于Skype for Business Server。
  
"获取项目上级"操作是呼叫质量仪表板的存储库 API 中的项目服务的一部分。
  
## <a name="get-item-ancestors"></a>获取项目上级

获取项目上级从存储库中返回特定项目上级。
  

|**方法**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|GET  <br/> |\<portal\>https:///QoERepositoryService/repository/itemAncestors/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数** - 无。
  
 **请求标头** - 无其他标头。
  
 **请求正文** - 无。
  
 **响应** - 响应包括 HTTP 状态代码和一组响应标头。
  
 **状态代码** - 成功操作返回状态代码 200， (确定) 。 如果未找到指定的用户 ID，它将返回状态代码 404 (未找到) 。
  
 **响应标头** - 无其他标头。
  
 **响应正文** - 下面是 JSON 中的示例响应有效负载。
  
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

 *Item1*  - 项目的 ID。
  
 *Item2*  - 深度是项目的距离。 0 是直接父级。
  
 *Item3*  - 项目的标题。
  

