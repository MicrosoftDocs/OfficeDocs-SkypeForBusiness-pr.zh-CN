---
title: 更新项目
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 6/8/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 摘要： 了解更新项目操作，这是项服务的一部分。 此项服务是呼叫质量仪表板存储库 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: 04a0ebf29537bbc2e62e6d5b35008fe9e329ab4f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="update-item"></a>更新项目
 
**摘要：**了解有关更新项目操作，这是项服务的一部分。 此项服务是呼叫质量仪表板存储库 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
  
更新物料操作是项服务存储库 API 调用质量仪表板中的一部分。
  
## <a name="update-item"></a>更新项目

更新项目更新资源库中的特定项。
  

|**方法**|**请求的 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|放入  <br/> |https://\<门户网站\>/QoERepositoryService/存储库/项目 / {itemId}  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数**-无。
  
 **请求标头**的内容的类型： 应用程序/json。
  
 **请求正文**的 JSON。
  
示例请求负载：
  
```
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 *内容* JSON 格式的数据存储为现有的子项目的新内容。 从技术上讲，存储库可以存储任何内容的任何架构，但是使用呼叫质量仪表板，它应该是一个报表或查询。 *类型* 始终指定呼叫质量仪表板的"应用程序/json"。
  
 **响应**-响应包括 HTTP 状态代码和一套响应标头。
  
 **状态代码**-操作成功返回状态码 204 （无内容）。 如果找不到指定的项 ID，它将返回状态代码 404 （未找到）。
  
> [!IMPORTANT]
> "没有内容"不是一个错误状态。 这意味着，响应未返回任何内容 （相比之下，在正文中 200 OK 返回内容） 体内。 它表明该项目已成功更新。 
  
 **响应标头**的无。
  
 **响应正文**-无。
  

