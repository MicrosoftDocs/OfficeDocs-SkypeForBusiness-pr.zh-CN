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
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: '摘要: 了解 "获取用户" 操作 (这是用户服务的一部分)。 用户服务是适用于呼叫质量仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。'
ms.openlocfilehash: 6c38bb2db2bef1a21dfc5c4791de7a163c57ff5f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274595"
---
# <a name="get-user"></a>获取用户
 
**摘要:** 了解 "获取用户" 操作, 该操作是用户服务的一部分。 用户服务是适用于呼叫质量仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。
  
"获取用户" 操作是 "资源库 API for 通话质量" 仪表板中的用户服务的一部分。
  
## <a name="get-user"></a>获取用户

获取用户从存储库返回用户记录。
  
|**种**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|获取  <br/> |https://\<portal\>/QoERepositoryService/repository/user/{userId}  <br/> |HTTP/1。1  <br/> |
   
 **URI 参数**-无。
  
 **请求标题**-无其他标题。
  
 **请求正文**-无。
  
 **响应**-响应包括 HTTP 状态代码和一组响应标头。
  
 **状态代码**-成功的操作返回状态代码 200 (OK)。 如果找不到指定的用户 ID, 将返回状态代码 404 (未找到)。
  
 **响应标题**-无其他标题。
  
 **响应正文**-下面是 JSON 中的示例响应负载。
  
```
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 *userId* -用户 ID。
  
 *loginName* -常规用户的外部用户标识。 如果使用 Windows 身份验证对用户进行身份验证, 则这可能是用户的 FQDN。
  
 *defaultItemId* -此用户的默认项目的 ID。 默认项目是与用户关联的最顶部的项目。 此用户拥有的所有其他项目都可以从 "默认" 项目中进行导航。
  
> [!NOTE]
> 提供用于`defaultItemId`获取项目操作的值以检索默认项目的详细信息。
  

