---
title: 获取最后一个集成数据
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: e7967dd9-0d6a-4a80-8b59-b8fc2e5615f8
description: 摘要：了解"获取最后一次集成数据"操作，这是通话质量仪表板的数据 API 的一部分。 通话质量仪表板是一种用于Skype for Business Server。
ms.openlocfilehash: 7bc9323c4a2d3933706be0a39a2ff4b86b11eb42
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851966"
---
# <a name="get-last-integration-data"></a>获取最后一个集成数据
 
**摘要：** 了解"获取最后一次集成数据"操作，该操作是通话质量仪表板的数据 API 的一部分。 通话质量仪表板是一种用于Skype for Business Server。
  
"获取最后一个集成数据"操作是通话质量仪表板的数据 API 的一部分。
  
## <a name="get-last-integration-data"></a>获取最后一个集成数据

Get Last Integration Data operation returns the list of last 5 success/failure of archiving and cube processing.
  
默认情况下禁用此功能，并且需要通过配置数据 API 来启用它。
  

|**方法**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoEDataService/IntegrationLog/Status  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数** - 无。
  
 **请求标头** - 无其他标头。
  
 **请求正文** - 无。
  
 **响应** - 响应包括 HTTP 状态代码和一组响应标头。
  
 **状态代码** - 成功操作返回状态代码 200 (确定) 。
  
 **响应标头** - 无其他标头。
  
 **响应正文** - 下面是示例日志状态。
  
```json
{
"LastSuccessIntegrations": ["01/18/2015 10:30:13",
"01/18/2015 10:28:29",
"01/17/2015 15:15:17",
"01/17/2015 15:00:17",
"01/17/2015 14:45:13"],
"LastSuccessCubeProcessings": ["01/17/2015 15:16:40",
"01/17/2015 15:01:41",
"01/17/2015 14:47:19",
"01/17/2015 14:31:40",
"01/17/2015 14:17:01"],
"LastFailedIntegrations":  ,
"LastFailedCubeProcessings": ["01/18/2015 10:30:58",
"01/18/2015 10:29:28",
"01/17/2015 10:02:20",
"01/15/2015 20:01:56",
"01/15/2015 19:45:50"],
"LastDataIntegrationStart": null,
"LastCubeProcessingStart": "01/18/2015 10:30:16"
}
```
