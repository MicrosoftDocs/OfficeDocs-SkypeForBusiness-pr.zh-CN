---
title: 获取集成日志
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
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 摘要：了解"获取集成日志"操作，该操作是通话质量仪表板的数据 API 的一部分。 通话质量仪表板是 Skype for Business Server 的工具。
ms.openlocfilehash: 69827fa9f3fd3f56843a41867b029a071799ba66
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832592"
---
# <a name="get-integration-log"></a>获取集成日志
 
**摘要：** 了解"获取集成日志"操作，该操作是通话质量仪表板的数据 API 的一部分。 通话质量仪表板是 Skype for Business Server 的工具。
  
获取集成日志操作是通话质量仪表板的数据 API 的一部分
  
## <a name="get-integration-log"></a>获取集成日志

获取集成日志操作返回描述 QoE 多维数据集处理中的活动的日志条目列表。
  
出于安全考虑，此操作默认处于禁用状态。 禁用后，它将返回一个空字符串。 若要启用此操作，管理员需要配置web.config API 的主机 Web 应用程序的应用程序。
  

|Method|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoEDataService/IntegrationLog  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数** - 无。
  
 **请求标头** - 无其他标头。
  
 **请求正文** - 无。
  
 **响应** - 响应包括 HTTP 状态代码和一组响应标头。
  
 **状态代码** - 成功操作返回状态代码 200 (确定) 。
  
 **响应标头** - 无其他标头。
  
 **响应正文** - 下面是日志条目的示例结构。
  
```json
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


