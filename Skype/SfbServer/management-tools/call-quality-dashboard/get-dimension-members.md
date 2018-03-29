---
title: 维度成员
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 摘要： 了解如何获取维度成员操作。 获取维度成员操作是呼叫质量仪表板的数据 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: 6da1b8f6d93dc197df320f1fb5875a6269a9b45a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="get-dimension-members"></a>维度成员
 
**摘要：**了解有关获取维度成员操作。 获取维度成员操作是呼叫质量仪表板的数据 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
  
获取维度成员操作是呼叫质量仪表板的数据 API 的一部分。
  
## <a name="get-dimension-members"></a>维度成员

获取维度成员操作返回的特定维度中的成员的列表。 它还提供筛选成员名单和获取子集，以减少网络传输成本的能力。
  

|**方法**|**请求的 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|发布  <br/> |https://\<门户网站\>/QoEDataService/DimensionMembers  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数**-无。
  
 **请求标头**的任何其他标头。
  
 **请求正文**-它包含了我们想要的成员的维度的名称。 此外返回成员的最大数目，旁边还可以指定某些筛选，用于限制返回的成员。
  
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

 **响应**-响应包括 HTTP 状态代码和一套响应标头。
  
 **状态代码**-操作成功返回状态码 200 (OK)。
  
 **响应标头**的任何其他标头。
  
 **响应正文**-下面是示例的响应负载在 JSON 响应请求的"[开始日期]。[月]"维度。
  
> [!NOTE]
> 列表仅显示列表中的一小部分。 
  
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


