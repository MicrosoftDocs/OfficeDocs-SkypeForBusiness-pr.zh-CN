---
title: 更新项目
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 摘要：了解作为项目服务的一部分的"更新项"操作。 项目服务是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是一种用于Skype for Business Server。
ms.openlocfilehash: ef77a4a73cd83743b718988657dcf4f4eb9fd404
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759684"
---
# <a name="update-item"></a>更新项目
 
**摘要：** 了解"更新项目"操作，这是项服务的一部分。 项目服务是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是一种用于Skype for Business Server。
  
Update Item 操作是呼叫质量仪表板存储库 API 中的项目服务的一部分。
  
## <a name="update-item"></a>更新项目

"更新项"更新存储库中的特定项。
  

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

 *content*  要存储为现有子项的新内容的 JSON 格式数据。 从技术上说，存储库可以存储任何架构的任何内容，但在用于呼叫质量仪表板时，它应是报告或查询。 *type*  始终为呼叫质量仪表板指定"application/json"。
  
 **响应** - 响应包括 HTTP 状态代码和一组响应标头。
  
 **状态代码** - 成功操作返回状态代码 204， (内容) 。 如果未找到指定的项目 ID，它将返回状态代码 404 (未找到) 。
  
> [!IMPORTANT]
> "无内容"不是错误状态。 它表示响应未在正文中返回任何内容 (相反，200 OK 返回 Body) 。 它指示已成功更新项目。 
  
 **响应标头** - 无。
  
 **响应正文** - 无。
  

