---
title: 获取用户
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 摘要： 了解如何获取用户操作，它是用户服务的一部分。 用户服务是用于呼叫的质量仪表板的存储库 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
ms.openlocfilehash: 2d3c5febe30af2ea4d41d94aec026c25e27f21b9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32235721"
---
# <a name="get-user"></a>获取用户
 
**摘要：** 了解如何获取用户操作，它是用户服务的一部分。 用户服务是用于呼叫的质量仪表板的存储库 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
  
获取用户操作是用于呼叫的质量仪表板的存储库 API 中的用户服务的一部分。
  
## <a name="get-user"></a>获取用户

从存储库中获取用户返回用户记录。
  
|**方法**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|获取  <br/> |https://\<门户\>/QoERepositoryService/存储库/用户 / {userId}  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数**-无。
  
 **请求标头**的任何其他的标头。
  
 **请求正文**-无。
  
 **响应**-响应包括 HTTP 状态代码和一响应标头。
  
 **状态代码**-成功的操作返回状态代码 200 （确定)。 如果找不到 ID 指定的用户，则将返回状态代码的 404 （未找到）。
  
 **响应标头**的任何其他的标头。
  
 **响应正文**-下面是以 json 格式的示例响应负载。
  
```
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 *用户 Id*的用户的 ID。
  
 *使用 loginName* -一般用户的外部用户标识。 如果用户进行身份验证使用 Windows 身份验证，则这可能是用户的 FQDN。
  
 *defaultItemId* -此用户的默认项目的 ID。 默认项目是与用户相关联的顶层项目。 此用户拥有的所有其他项目的导航可以从默认的项目。
  
> [!NOTE]
> 提供`defaultItemId`的值为获取项操作来检索的默认项目详细信息。
  

