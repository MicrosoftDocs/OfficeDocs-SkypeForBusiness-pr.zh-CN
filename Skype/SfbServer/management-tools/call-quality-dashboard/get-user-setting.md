---
title: 获取用户设置
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 摘要：了解"获取用户设置"操作，该操作是 User 设置 服务的一部分。 User 设置 Service 是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是一种用于Skype for Business Server。
ms.openlocfilehash: 1faff1a206ece2ebd0208a32988a679be9739dd7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58601457"
---
# <a name="get-user-setting"></a>获取用户设置
 
**摘要：** 了解"获取用户设置"操作，该操作是 User 设置 服务的一部分。 User 设置 Service 是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是一种用于Skype for Business Server。
  
"获取用户设置"操作是呼叫质量仪表板的存储库 API 设置 User 设置 Service 的一部分。
  
## <a name="get-user-setting"></a>获取用户设置

获取用户设置返回单个用户设置。
  

|**方法**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting/{key}  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数** - 无。
  
 **请求标头** - 无其他标头。
  
 **请求正文** - 无。
  
 **响应** - 响应包括 HTTP 状态代码和一组响应标头。
  
 **状态代码** - 成功操作返回状态代码 200， (确定) 。
  
 **响应标头** - 无其他标头。
  
 **响应正文** - 下面是 JSON 中的示例响应有效负载。
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 *userId*  - 用户的 ID。
  
 *key*  - 设置的键。
  
 *value*  - 设置的值。
  

