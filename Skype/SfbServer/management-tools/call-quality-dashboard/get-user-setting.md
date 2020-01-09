---
title: 获取用户设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 摘要：了解 "获取用户设置" 操作，它是 "用户设置" 服务的一部分。 "用户设置" 服务是 "呼叫质量" 仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。
ms.openlocfilehash: 168e61aaebb47cb087e77cbd18e3e6edfd987227
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992639"
---
# <a name="get-user-setting"></a>获取用户设置
 
**摘要：** 了解 "获取用户设置" 操作，该操作是 "用户设置" 服务的一部分。 "用户设置" 服务是 "呼叫质量" 仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。
  
"获取用户设置" 操作是 "资源库 API for 通话质量" 仪表板中的 "用户设置" 服务的一部分。
  
## <a name="get-user-setting"></a>获取用户设置

获取用户设置返回单个用户设置。
  

|**种**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|获取  <br/> |https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting/{key}  <br/> |HTTP/1。1  <br/> |
   
 **URI 参数**-无。
  
 **请求标题**-无其他标题。
  
 **请求正文**-无。
  
 **响应**-响应包括 HTTP 状态代码和一组响应标头。
  
 **状态代码**-成功的操作返回状态代码200（OK）。
  
 **响应标题**-无其他标题。
  
 **响应正文**-下面是 JSON 中的示例响应负载。
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 *userId* -用户 ID。
  
 设置的*键*。
  
 *value* -设置的值。
  

