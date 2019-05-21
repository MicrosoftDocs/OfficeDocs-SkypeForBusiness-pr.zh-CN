---
title: 获取用户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: '摘要: 了解 "获取用户" 操作 (这是用户服务的一部分)。 用户服务是适用于呼叫质量仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。'
ms.openlocfilehash: 22223c37dad39f171afc27eb9e0520b8b32335c5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274644"
---
# <a name="get-users"></a>获取用户
 
**摘要:** 了解 "获取用户" 操作, 这是用户服务的一部分。 用户服务是适用于呼叫质量仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。
  
"获取用户" 操作是 "资源库 API for 通话质量" 仪表板中的用户服务的一部分。
  
## <a name="get-users"></a>获取用户

获取用户返回存储库中的用户列表。
  
|**种**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|获取  <br/> |https://\<portal\>/QoERepositoryService/repository/user  <br/> |HTTP/1。1  <br/> |
   
 **URI 参数**-无。
  
 **请求标题**-无其他标题。
  
 **请求正文**-无。
  
 **响应**-响应包括 HTTP 状态代码和一组响应标头。
  
 **状态代码**-成功的操作返回状态代码 200 (OK)。
  
 **响应标题**-无其他标题。
  
 **响应正文**-下面是 JSON 中的示例响应负载。
  
> [!NOTE]
> 返回一个用户对象数组。 有关用户对象的详细信息, 请参阅获取用户。 
  
```
[{
"userId": 0,
"loginName": "system",
"defaultItemId": 1652
},
{
"userId": 1,
"loginName": "SAMPLEDOMAIN\\testuser1",
"defaultItemId": 1652
},
{
"userId": 2,
"loginName": "SAMPLEDOMAIN\\testuser2",
"defaultItemId": 1774
}]
```


