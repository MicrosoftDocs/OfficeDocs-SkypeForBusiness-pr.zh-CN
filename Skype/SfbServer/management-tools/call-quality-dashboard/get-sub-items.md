---
title: 获取子项
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 摘要：了解 Get Sub-Items 操作，这是项目服务的一部分。 项目服务是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是一种用于Skype for Business Server。
ms.openlocfilehash: 6bfa8e449610317caeeaf512e088f2b56441bd2b
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385570"
---
# <a name="get-sub-items"></a>获取子项
 
**摘要：** 了解 Get Sub-Items 操作，该操作是项服务的一部分。 项目服务是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是一种用于Skype for Business Server。
  
Get Sub-Items 操作是呼叫质量仪表板的存储库 API 中的项目服务的一部分。
  
## <a name="get-sub-items"></a>获取子项

获取Sub-Items返回特定项的子项。
  

|**方法**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|GET  <br/> |\<portal\>https:///QoERepositoryService/repository/item/{itemId}/subitem  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数** - 无。
  
 **请求标头** - 无其他标头。
  
 **请求正文** - 无。
  
 **响应** - 响应包括 HTTP 状态代码和一组响应标头。
  
 **状态代码** - 成功操作返回状态代码 200， (确定) 。 如果未找到指定的用户 ID，它将返回状态代码 404 (未找到) 。
  
 **响应标头** - 无其他标头。
  
 **响应正文** - 下面是 JSON 中的示例响应有效负载。
  
> [!NOTE]
> 返回 Item 对象的数组。 
  
```json
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

由项目操作Sub-Items Item 对象仅包含以下三个字段。 
  
 *itemId*  - 项目的 ID。
  
 *userId*  - 拥有此项目的用户的 ID。
  
 *type*  - 内容的类型。 此字段由应用程序设置。
  
> [!NOTE]
>  `Content` 响应 `subItems` 中不包含 和 字段，以减少通过网络传输的数据量。
  

