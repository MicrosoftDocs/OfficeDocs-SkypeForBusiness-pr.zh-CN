---
title: 获取用户的设置
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 摘要： 了解如何获取用户设置操作，它是用户设置服务的一部分。 用户设置服务被呼叫质量仪表板存储库 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: 562886196f06030aef30efbd6f583c29d7f29e59
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="get-user-setting"></a>获取用户的设置
 
**摘要：**了解有关获取用户设置运算，是用户设置服务的一部分。 用户设置服务被呼叫质量仪表板存储库 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
  
获取用户设置操作是用户设置服务存储库 API 调用质量仪表板中的一部分。
  
## <a name="get-user-setting"></a>获取用户的设置

获取用户设置返回的单个用户设置。
  

|**方法**|**请求的 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|获取  <br/> |https://\<门户网站\>/QoERepositoryService/存储 {库/用户/用户 Id} /setting/ {键}  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数**-无。
  
 **请求标头**的任何其他标头。
  
 **请求正文**-无。
  
 **响应**-响应包括 HTTP 状态代码和一套响应标头。
  
 **状态代码**-操作成功返回状态码 200 (OK)。
  
 **响应标头**的任何其他标头。
  
 **响应正文**-下面是 json 格式的示例响应负载。
  
```
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}

```

 *用户 Id*的用户的 ID。
  
 *键*的键设置。
  
 *值*的设置的值。
  

