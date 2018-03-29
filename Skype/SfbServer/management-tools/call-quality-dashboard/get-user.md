---
title: 获取用户
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 摘要： 了解有关获取用户操作，为用户服务的一部分。 用户服务是为呼叫质量仪表板存储库 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: e3863819ea15a1039a3a02b1a35cfc7326af7e1d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="get-user"></a>获取用户
 
**摘要：**了解有关获取用户操作，为用户服务的一部分。 用户服务是为呼叫质量仪表板存储库 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
  
获取用户操作是用户服务存储库 API 调用质量仪表板中的一部分。
  
## <a name="get-user"></a>获取用户

从存储库中获取用户返回用户记录。
  
|**方法**|**请求的 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|获取  <br/> |https://\<门户网站\>/QoERepositoryService/存储 {库/用户/用户 Id}  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数**-无。
  
 **请求标头**的任何其他标头。
  
 **请求正文**-无。
  
 **响应**-响应包括 HTTP 状态代码和一套响应标头。
  
 **状态代码**-操作成功返回状态码 200 (OK)。 如果找不到 ID 指定的用户，它将返回状态代码 404 （未找到）。
  
 **响应标头**的任何其他标头。
  
 **响应正文**-下面是 json 格式的示例响应负载。
  
```
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}

```

 *用户 Id*的用户的 ID。
  
 *名*的普通用户的外部用户标识。 如果 Windows 身份验证用于验证用户身份，这可能是用户的 FQDN。
  
 *defaultItemId* -此用户的默认项的 ID。 默认值项是最上面的一项是与用户相关联。 此用户拥有的所有其他项目的导航可以从默认项。
  
> [!NOTE]
> 提供`defaultItemId`值与获取项操作来检索项的默认值的详细信息。
  

