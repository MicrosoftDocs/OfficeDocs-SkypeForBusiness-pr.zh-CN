---
title: 获取维度成员
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 摘要： 了解如何获取维度成员操作。 获取维度成员操作是用于呼叫的质量仪表板的数据 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
ms.openlocfilehash: 482fe92a95c6754695e983ed9ff0ec69ed7a442b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926091"
---
# <a name="get-dimension-members"></a>获取维度成员
 
**摘要：** 了解有关获取维度成员操作。 获取维度成员操作是用于呼叫的质量仪表板的数据 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
  
获取维度成员操作是用于呼叫的质量仪表板的数据 API 的一部分。
  
## <a name="get-dimension-members"></a>获取维度成员

获取维度成员操作返回的特定维度成员的列表。 它还提供的功能来筛选成员列表和获取子集，以减少线路传输成本。
  

|**方法**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|发布  <br/> |https://\<门户\>/QoEDataService/DimensionMembers  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数**-无。
  
 **请求标头**的任何其他的标头。
  
 **请求正文**-此部件包含我们希望成员的维度的名称。 此外返回成员的最大数目，旁边可以指定某些筛选，以限制返回的成员。
  
```
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}
```

 **响应**-响应包括 HTTP 状态代码和一响应标头。
  
 **状态代码**-成功的操作返回状态代码 200 （确定)。
  
 **响应标头**的任何其他的标头。
  
 **响应正文**-下面是示例的响应负载以 json 格式以响应的请求"[StartDate]。[月份]"维度。
  
> [!NOTE]
> 列表列表的一小部分仅显示。 
  
```
{
"MembersCount": 493,
"Members": [["[1990-01-01T00:00:00]",
"January 1990"],
["[1990-02-01T00:00:00]",
"February 1990"],
["[1990-03-01T00:00:00]",
"March 1990"],
 
    ...
    
["[2030-10-01T00:00:00]",
"October 2030"],
["[2030-11-01T00:00:00]",
"November 2030"],
["[2030-12-01T00:00:00]",
"December 2030"],
["[2031-01-01T00:00:00]",
"January 2031"]]
}
```
