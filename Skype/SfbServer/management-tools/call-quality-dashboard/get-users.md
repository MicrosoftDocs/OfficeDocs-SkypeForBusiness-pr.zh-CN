---
title: 获取用户
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
ms.collection: IT_Skype16
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 摘要：了解作为用户服务的一部分的"获取用户"操作。 用户服务是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是 Skype for Business Server 的工具。
ms.openlocfilehash: a830663fc97d8fda727d1ebb008d97407796cc7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832422"
---
# <a name="get-users"></a>获取用户
 
**摘要：** 了解作为用户服务的一部分的"获取用户"操作。 用户服务是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是 Skype for Business Server 的工具。
  
Get Users 操作是呼叫质量仪表板的存储库 API 中的用户服务的一部分。
  
## <a name="get-users"></a>获取用户

Get Users returns a list of users in the repository.
  
|**方法**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/user  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数** - 无。
  
 **请求标头** - 无其他标头。
  
 **请求正文** - 无。
  
 **响应** - 响应包括 HTTP 状态代码和一组响应标头。
  
 **状态代码** - 成功操作返回状态代码 200 (确定) 。
  
 **响应标头** - 无其他标头。
  
 **响应正文** - 下面是 JSON 中的示例响应负载。
  
> [!NOTE]
> 返回 User 对象的数组。 有关 User 对象的详细信息，请参阅"获取用户"。 
  
```json
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


