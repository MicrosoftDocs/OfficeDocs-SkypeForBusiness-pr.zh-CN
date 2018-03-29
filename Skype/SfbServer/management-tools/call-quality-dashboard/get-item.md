---
title: 获取项
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 摘要： 了解如何获取项操作，这是项服务的一部分。 此项服务是呼叫质量仪表板存储库 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: 6e4ba82c804937025b72da2d443c2a828d92d98a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="get-item"></a>获取项
 
**摘要：**了解有关获取项操作，这是项服务的一部分。 此项服务是呼叫质量仪表板存储库 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
  
获取项操作是项服务存储库 API 调用质量仪表板中的一部分。
  
## <a name="get-item"></a>获取项

存储库中获取项返回的特定项。
  
|**方法**|**请求的 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|获取  <br/> |https://\<门户网站\>/QoERepositoryService/存储库/项目 / {itemId}  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数**-无。
  
 **请求标头**的任何其他标头。
  
 **请求正文**-无。
  
 **响应**-响应包括 HTTP 状态代码和一套响应标头。
  
 **状态代码**-操作成功返回状态码 200 (OK)。 如果找不到指定的项 ID，它将返回状态代码 404 （未找到）。
  
 **响应标头**的任何其他标头。
  
 **响应正文**-下面是 json 格式的示例响应负载。
  
```
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}

```

 *itemId*的项的 ID。
  
 *用户 Id* -负责此项目的用户的 ID。
  
 *内容*的应用程序特定的内容。
  
 *类型*-类型的内容。 由应用程序设置此字段。
  
 *subItemIds* -Id 的子项目，如果有的话。 这是获取子项操作来保存调用短路。 应用程序也可以获得相同的信息使用获取子项操作。
  

