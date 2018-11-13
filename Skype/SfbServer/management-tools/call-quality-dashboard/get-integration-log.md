---
title: 获取集成日志
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 摘要： 了解如何获取集成日志操作，它是用于呼叫的质量仪表板的数据 API 的一部分。 呼叫质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: 1b21e078578b9e198c743f77f77e4beca94ddeaf
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294830"
---
# <a name="get-integration-log"></a>获取集成日志
 
**摘要：** 了解有关获取集成日志操作，它是用于呼叫的质量仪表板的数据 API 的一部分。 呼叫质量仪表板是用于业务服务器 2015年的 Skype 的工具。
  
获取集成日志操作是呼叫质量仪表板的数据 API 的一部分
  
## <a name="get-integration-log"></a>获取集成日志

获取集成日志操作返回描述 QoE 多维数据集中活动的日志条目的列表处理。
  
默认情况下，为了安全起见，此操作被禁用。 禁用时，它将返回空字符串。 若要启用此操作，管理员需要配置数据 API 主机 web 应用程序的 web.config。
  

|方法|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|获取  <br/> |https://\<门户\>/QoEDataService/IntegrationLog  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数**-无。
  
 **请求标头**的任何其他的标头。
  
 **请求正文**-无。
  
 **响应**-响应包括 HTTP 状态代码和一响应标头。
  
 **状态代码**-成功的操作返回状态代码 200 （确定)。
  
 **响应标头**的任何其他的标头。
  
 **响应正文**-下面是示例结构的日志条目。
  
```
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


