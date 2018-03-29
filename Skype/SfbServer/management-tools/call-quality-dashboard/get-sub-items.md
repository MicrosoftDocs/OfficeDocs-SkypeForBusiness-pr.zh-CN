---
title: 获取子项目
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 摘要： 了解如何获取子项操作，这是项服务的一部分。 此项服务是呼叫质量仪表板存储库 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: 8b9ec0c1c849e22f285ef1b5bbb2db806a153b76
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="get-sub-items"></a>获取子项目
 
**摘要：**了解有关获取子项操作，这是项服务的一部分。 此项服务是呼叫质量仪表板存储库 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
  
获取子项操作是项服务存储库 API 调用质量仪表板中的一部分。
  
## <a name="get-sub-items"></a>获取子项目

获取子项目返回特定项的子项。
  

|**方法**|**请求的 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|获取  <br/> |https://\<门户网站\>/QoERepositoryService/存储库/项目 / {itemId} / subitem  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数**-无。
  
 **请求标头**的任何其他标头。
  
 **请求正文**-无。
  
 **响应**-响应包括 HTTP 状态代码和一套响应标头。
  
 **状态代码**-操作成功返回状态码 200 (OK)。 如果找不到 ID 指定的用户，它将返回状态代码 404 （未找到）。
  
 **响应标头**的任何其他标头。
  
 **响应正文**-下面是 json 格式的示例响应负载。
  
> [!NOTE]
> 项目对象的数组返回。 
  
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

项目对象的子项操作返回只包含以下三个字段。 
  
 *itemId*的项的 ID。
  
 *用户 Id* -负责此项目的用户的 ID。
  
 *类型*-类型的内容。 由应用程序设置此字段。
  
> [!NOTE]
>  `Content`和`subItems`的字段不包含在响应以减少通过网络传输的数据量。
  

