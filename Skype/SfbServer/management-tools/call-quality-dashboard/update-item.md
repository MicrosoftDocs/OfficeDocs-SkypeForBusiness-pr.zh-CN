---
title: 更新项目
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 摘要：了解 "更新项目" 操作，该操作是项目服务的一部分。 项目服务是适用于呼叫质量仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。
ms.openlocfilehash: 460e6b26375bba28887d170c9827864bfc600138
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816671"
---
# <a name="update-item"></a>更新项目
 
**摘要：** 了解 "更新项目" 操作，该操作是项目服务的一部分。 项目服务是适用于呼叫质量仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。
  
"更新项目" 操作是 "知识库 API for 通话质量" 仪表板中的项目服务的一部分。
  
## <a name="update-item"></a>更新项目

更新项目更新存储库中的特定项目。
  

|**种**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|带来  <br/> |https://\<portal\>/QoERepositoryService/repository/item/{itemId}  <br/> |HTTP/1。1  <br/> |
   
 **URI 参数**-无。
  
 **请求标头**-内容类型： application/json。
  
 **请求正文**-JSON。
  
示例请求负载：
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 *内容* 要存储为现有子项目的新内容的 JSON 格式的数据。 从技术上讲，存储库可以存储任何架构的任何内容，但在用于通话质量仪表板时，它应该是报表或查询。 *键入* 始终为 "通话质量" 仪表板指定 "application/json"。
  
 **响应**-响应包括 HTTP 状态代码和一组响应标头。
  
 **状态代码**-成功的操作返回状态代码204（无内容）。 如果找不到指定的项目 ID，则会返回状态代码404（未找到）。
  
> [!IMPORTANT]
> "无内容" 不是错误状态。 这意味着响应不会返回正文中的任何内容（相反，200 OK 返回正文中的内容）。 它表示项目已成功更新。 
  
 **响应标题**-无。
  
 **响应正文**-无。
  

