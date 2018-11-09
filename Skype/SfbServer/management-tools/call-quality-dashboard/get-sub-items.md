---
title: 获取子项
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 摘要： 了解如何获取子项操作，即项服务的一部分。 项服务是呼叫质量仪表板的存储库 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
ms.openlocfilehash: 648f514ff03361673962052445d25076437057b9
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035650"
---
# <a name="get-sub-items"></a>获取子项
 
**摘要：** 了解有关获取子项操作，即项服务的一部分。 项服务是呼叫质量仪表板的存储库 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
  
获取子项操作是用于呼叫的质量仪表板的存储库 API 中的项服务的一部分。
  
## <a name="get-sub-items"></a>获取子项

获取子项目返回的特定项目的子项目。
  

|**方法**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|获取  <br/> |https://\<门户\>/QoERepositoryService/存储库/项目 / {itemId} / subitem  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数**-无。
  
 **请求标头**的任何其他的标头。
  
 **请求正文**-无。
  
 **响应**-响应包括 HTTP 状态代码和一响应标头。
  
 **状态代码**-成功的操作返回状态代码 200 （确定)。 如果找不到 ID 指定的用户，则将返回状态代码的 404 （未找到）。
  
 **响应标头**的任何其他的标头。
  
 **响应正文**-下面是以 json 格式的示例响应负载。
  
> [!NOTE]
> 返回项目对象的数组。 
  
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

子项目操作返回的项目对象仅包含以下三个字段。 
  
 *itemId* -项目的 ID。
  
 *userId* -拥有此项的用户的 ID。
  
 *键入*的内容类型。 此字段设置应用程序。
  
> [!NOTE]
>  `Content`和`subItems`中的响应以减少通过网络传输的数据量不包含字段。
  

