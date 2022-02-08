---
title: 获取维度成员
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 摘要：了解"获取维度成员"操作。 "获取维度成员"操作是通话质量仪表板的数据 API 的一部分。 通话质量仪表板是一种用于Skype for Business Server。
ms.openlocfilehash: a88ae16a3ccf15a60a36805f475894b657641e6e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62391034"
---
# <a name="get-dimension-members"></a>获取维度成员
 
**摘要：** 了解"获取维度成员"操作。 "获取维度成员"操作是通话质量仪表板的数据 API 的一部分。 通话质量仪表板是一种用于Skype for Business Server。
  
"获取维度成员"操作是通话质量仪表板的数据 API 的一部分。
  
## <a name="get-dimension-members"></a>获取维度成员

"获取维度成员"操作返回特定维度的成员列表。 它还提供筛选成员列表和获取子集的能力，以降低线路传输成本。
  

|**方法**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|POST  <br/> |\<portal\>https:///QoEDataService/DimensionMembers  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数** - 无。
  
 **请求标头** - 无其他标头。
  
 **请求正文** - 包含我们希望成员使用维度的名称。 此外，还可以指定一些筛选以限制返回的成员，同时返回成员的最大数目。
  
```json
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}
```

 **响应** - 响应包括 HTTP 状态代码和一组响应标头。
  
 **状态代码** - 成功操作返回状态代码 200， (确定) 。
  
 **响应标头** - 无其他标头。
  
 **响应正文** - 下面是 JSON 中响应"[StartDate] 请求的示例响应有效负载。[Month]" dimension.
  
> [!NOTE]
> 列表只显示列表的一小部分。 
  
```json
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
