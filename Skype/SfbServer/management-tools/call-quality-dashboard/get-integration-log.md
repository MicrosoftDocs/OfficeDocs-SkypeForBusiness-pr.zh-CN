---
title: 获取集成日志
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: '摘要: 了解有关 "获取集成日志" 操作 (这是 "调用质量" 仪表板的数据 API 的一部分) 的信息。 通话质量仪表板是 Skype for business 服务器的工具。'
ms.openlocfilehash: 58be983ff3b282c94a4b42619a6c37c6270afcb5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274756"
---
# <a name="get-integration-log"></a>获取集成日志
 
**摘要:** 了解 "获取集成日志" 操作, 它是 "呼叫质量" 仪表板的数据 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。
  
获取集成日志操作是用于呼叫质量仪表板的数据 API 的一部分
  
## <a name="get-integration-log"></a>获取集成日志

获取集成日志操作返回日志条目的列表, 这些日志条目描述 QoE 多维数据集处理中的活动。
  
出于安全原因, 默认情况下禁用此操作。 禁用时, 它将返回一个空字符串。 若要启用此操作, 管理员需要为数据 API 的主机 web 应用程序配置 web.config。
  

|种|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|获取  <br/> |https://\<portal\>/QoEDataService/IntegrationLog  <br/> |HTTP/1。1  <br/> |
   
 **URI 参数**-无。
  
 **请求标题**-无其他标题。
  
 **请求正文**-无。
  
 **响应**-响应包括 HTTP 状态代码和一组响应标头。
  
 **状态代码**-成功的操作返回状态代码 200 (OK)。
  
 **响应标题**-无其他标题。
  
 **响应正文**-下面是日志条目的示例结构。
  
```
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


