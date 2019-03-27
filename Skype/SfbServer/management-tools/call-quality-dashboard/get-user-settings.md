---
title: 获取用户设置
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 摘要： 了解如何获取用户设置操作，它是用户设置服务的一部分。 用户设置服务是呼叫质量仪表板的存储库 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
ms.openlocfilehash: 3c94f02f305ee2f779b6a31ef78bea875d462cbf
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889019"
---
# <a name="get-user-settings"></a>获取用户设置
 
**摘要：** 了解如何获取用户设置操作，它是用户设置服务的一部分。 用户设置服务是呼叫质量仪表板的存储库 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
  
获取用户设置操作是用于呼叫的质量仪表板的存储库 API 中的用户设置服务的一部分。
  
## <a name="get-user-settings"></a>获取用户设置

获取用户设置返回指定用户的设置的列表。
  

|**方法**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|获取  <br/> |https://\<门户\>/QoERepositoryService/存储库/用户 / {userId} / 设置  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数**
  
- *有效*的可选。 仅在使用特殊的用户 ID 默认时，此参数适用。 在其他情况下，它将被忽略。 `True`返回有效的用户设置和`false`返回只是用户设置 （默认值）。
    
  **请求标头**的任何其他的标头。
  
  **请求正文**-无。
  
  **响应**-响应包括 HTTP 状态代码和一响应标头。
  
  **状态代码**-成功的操作返回状态代码 200 （确定)。
  
  **响应标头**的任何其他的标头。
  
  **响应正文**-下面是以 json 格式的示例响应负载。
  
```
[{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
},
{
"userId": 6,
"key": "ShowTimeStamps",
"value": "true"
}]
```
