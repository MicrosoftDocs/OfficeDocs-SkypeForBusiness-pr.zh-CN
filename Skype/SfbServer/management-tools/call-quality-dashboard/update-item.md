---
title: 更新项
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 摘要： 了解如何更新项操作，即项服务的一部分。 项服务是呼叫质量仪表板的存储库 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
ms.openlocfilehash: 5839118dc6e907696d4ce3e9adfbc58504808fac
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532223"
---
# <a name="update-item"></a>更新项
 
**摘要：** 了解有关更新项操作，即项服务的一部分。 项服务是呼叫质量仪表板的存储库 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
  
更新项操作是用于呼叫的质量仪表板的存储库 API 中的项服务的一部分。
  
## <a name="update-item"></a>更新项

更新项更新存储库中的特定项目。
  

|**方法**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|PUT  <br/> |https://\<门户\>/QoERepositoryService/存储库/项目 / {itemId}  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数**-无。
  
 **请求标头**的内容的类型： application/json。
  
 **请求正文**的 JSON。
  
示例请求负载：
  
```
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 *内容* JSON 格式作为现有子项目的新内容存储的数据。 技术上讲，存储库可以存储的任何架构，任何内容，但当用于呼叫的质量仪表板，它应为报表或查询。 *类型* 始终为呼叫质量仪表板中指定"application/json"。
  
 **响应**-响应包括 HTTP 状态代码和一响应标头。
  
 **状态代码**-成功的操作返回状态代码 204 （无内容）。 如果找不到指定的项 ID，则返回状态代码的 404 （未找到）。
  
> [!IMPORTANT]
> "没有 Content"不是错误状态。 它表示的响应未返回任何内容 （相比之下，200 确定返回内容正文中） 在正文中。 表示该项目已成功更新。 
  
 **响应头**-无。
  
 **响应正文**-无。
  

