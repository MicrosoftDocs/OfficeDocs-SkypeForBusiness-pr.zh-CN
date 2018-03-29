---
title: 获取用户设置
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 摘要： 了解如何获取用户设置操作中，它是用户设置服务的一部分。 用户设置服务被呼叫质量仪表板存储库 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: 55c3247f0412a9ce10927496ee65255129edfd93
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="get-user-settings"></a>获取用户设置
 
**摘要：**了解有关获取用户设置运算，是用户设置服务的一部分。 用户设置服务被呼叫质量仪表板存储库 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
  
获取用户设置操作是用户设置服务存储库 API 调用质量仪表板中的一部分。
  
## <a name="get-user-settings"></a>获取用户设置

获取用户设置返回设置为指定的用户的列表。
  

|**方法**|**请求的 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|获取  <br/> |https://\<门户网站\>/QoERepositoryService/存储 {库/用户/用户 Id} / 设置  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数**
  
-  *有效*的可选。 此参数适用于只在使用特殊的用户 ID 缺省值时。 在其他情况下，它将被忽略。 `True`返回有效的用户设置和`false`返回只是用户设置 （默认值）。
    
 **请求标头**的任何其他标头。
  
 **请求正文**-无。
  
 **响应**-响应包括 HTTP 状态代码和一套响应标头。
  
 **状态代码**-操作成功返回状态码 200 (OK)。
  
 **响应标头**的任何其他标头。
  
 **响应正文**-下面是 json 格式的示例响应负载。
  
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


