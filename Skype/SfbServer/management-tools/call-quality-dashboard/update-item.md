---
title: 更新项目
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 摘要：了解作为项目服务的一部分的"更新项"操作。 项目服务是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是 Skype for Business Server 的工具。
ms.openlocfilehash: 78da2fa414b4ba266f9e6aba4feac5ff73150062
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803082"
---
# <a name="update-item"></a>更新项目
 
**摘要：** 了解更新项操作，这是项服务的一部分。 项目服务是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是 Skype for Business Server 的工具。
  
更新项操作是呼叫质量仪表板存储库 API 中的项目服务的一部分。
  
## <a name="update-item"></a>更新项目

更新项更新存储库中的特定项。
  

|**方法**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|PUT  <br/> |https:// \<portal\> /QoERepositoryService/repository/item/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数** - 无。
  
 **请求标头** -Content-Type：application/json。
  
 **请求正文** - JSON。
  
示例请求有效负载：
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 *content*  要存储为现有子项的新内容的 JSON 格式数据。 从技术上说，存储库可以存储任何架构的任何内容，但在用于呼叫质量仪表板时，它应为报表或查询。 *type*  始终为呼叫质量仪表板指定"application/json"。
  
 **响应** - 响应包括 HTTP 状态代码和一组响应标头。
  
 **状态代码** - 成功操作返回状态代码 204 (内容) 。 如果找不到指定的项目 ID，则返回状态代码 404 (未找到) 。
  
> [!IMPORTANT]
> "无内容"不是错误状态。 这意味着响应没有在正文中返回任何内容，相反 (200 OK 返回 Body) 。 它指示项目已成功更新。 
  
 **响应标头** - 无。
  
 **响应正文** - 无。
  

