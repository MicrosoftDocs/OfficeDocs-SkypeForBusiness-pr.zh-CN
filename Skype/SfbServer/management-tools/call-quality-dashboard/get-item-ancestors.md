---
title: 获取项祖先
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: 摘要： 了解如何获取项目祖先操作，即项服务的一部分。 项服务是呼叫质量仪表板的存储库 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
ms.openlocfilehash: e9e23c32aada4c609f9deb43004385b389a533bf
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532589"
---
# <a name="get-item-ancestors"></a>获取项祖先
 
**摘要：** 了解有关获取项目祖先操作，即项服务的一部分。 项服务是呼叫质量仪表板的存储库 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
  
获取项祖先操作是用于呼叫的质量仪表板的存储库 API 中的项服务的一部分。
  
## <a name="get-item-ancestors"></a>获取项祖先

从存储库中获取项目祖先返回特定项目上级。
  

|**方法**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|获取  <br/> |https://\<门户\>/QoERepositoryService/存储库/itemAncestors / {itemId}  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数**-无。
  
 **请求标头**的任何其他的标头。
  
 **请求正文**-无。
  
 **响应**-响应包括 HTTP 状态代码和一响应标头。
  
 **状态代码**-成功的操作返回状态代码 200 （确定)。 如果找不到 ID 指定的用户，则将返回状态代码的 404 （未找到）。
  
 **响应标头**的任何其他的标头。
  
 **响应正文**-下面是以 json 格式的示例响应负载。
  
```
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
  
 *Item2* -深度是从项目之间的距离。 0 是直接父。
  
 *Item3* -项目的标题。
  

