---
title: 获得整合日志
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
description: 摘要： 了解获得整合日志操作，这是呼叫质量仪表板的数据 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: 8ccd4fc299cbf5310a5974d55b181aa1f42255ce
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="get-integration-log"></a>获得整合日志
 
**摘要：**了解有关获取整合日志操作，这是呼叫质量仪表板的数据 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
  
获得整合日志操作是呼叫质量仪表板数据 API 的一部分
  
## <a name="get-integration-log"></a>获得整合日志

获取操作返回描述 QoE 多维数据集中活动的日志条目的列表处理整合日志。
  
默认情况下，出于安全原因禁用此操作。 当禁用时，它会返回一个空字符串。 若要启用此操作，管理员需要配置数据 API 宿主 web 应用程序的 web.config。
  

|方法|**请求的 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|获取  <br/> |https://\<门户网站\>/QoEDataService/IntegrationLog  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数**-无。
  
 **请求标头**的任何其他标头。
  
 **请求正文**-无。
  
 **响应**-响应包括 HTTP 状态代码和一套响应标头。
  
 **状态代码**-操作成功返回状态码 200 (OK)。
  
 **响应标头**的任何其他标头。
  
 **响应正文**-以下是日志条目示例结构。
  
```
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]

```


