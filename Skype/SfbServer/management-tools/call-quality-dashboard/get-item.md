---
title: 获取项目
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 摘要： 了解如何获取项操作，即项服务的一部分。 项服务是呼叫质量仪表板的存储库 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
ms.openlocfilehash: cd72eb583ff0e0813e4197031b119200ecf4b2fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926077"
---
# <a name="get-item"></a>获取项目
 
**摘要：** 了解获取项目操作，即项服务的一部分。 项服务是呼叫质量仪表板的存储库 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
  
获取项操作是用于呼叫的质量仪表板的存储库 API 中的项服务的一部分。
  
## <a name="get-item"></a>获取项目

在存储库中获取项目返回的特定项目。
  
|**方法**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|获取  <br/> |https://\<门户\>/QoERepositoryService/存储库/项目 / {itemId}  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数**-无。
  
 **请求标头**的任何其他的标头。
  
 **请求正文**-无。
  
 **响应**-响应包括 HTTP 状态代码和一响应标头。
  
 **状态代码**-成功的操作返回状态代码 200 （确定)。 如果找不到指定的项 ID，则返回状态代码的 404 （未找到）。
  
 **响应标头**的任何其他的标头。
  
 **响应正文**-下面是以 json 格式的示例响应负载。
  
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
  
 *userId* -拥有此项的用户的 ID。
  
 *内容*-特定于应用程序的内容。
  
 *键入*的内容类型。 此字段设置应用程序。
  
 *subItemIds* -的子项，如果有的 Id。 这是获取子项操作，以保存呼叫短路。 应用程序或者可以获取相同的信息。 使用获取子项操作。
  

