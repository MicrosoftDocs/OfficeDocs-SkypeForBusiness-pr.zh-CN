---
title: 获取维度成员
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 摘要：了解 "获取维度成员" 操作。 "获取维度成员" 操作是 "调用质量" 仪表板的数据 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。
ms.openlocfilehash: ba80e14c011d6cecb9b70f8a8faf32764b5b433d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816821"
---
# <a name="get-dimension-members"></a>获取维度成员
 
**摘要：** 了解 "获取维度成员" 操作。 "获取维度成员" 操作是 "调用质量" 仪表板的数据 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。
  
"获取维度成员" 操作是 "调用质量" 仪表板的数据 API 的一部分。
  
## <a name="get-dimension-members"></a>获取维度成员

获取维度成员操作返回特定维度的成员列表。 它还提供了筛选成员列表和获取子集的功能，以降低线路传输成本。
  

|**种**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|发布  <br/> |https://\<portal\>/QoEDataService/DimensionMembers  <br/> |HTTP/1。1  <br/> |
   
 **URI 参数**-无。
  
 **请求标题**-无其他标题。
  
 **请求正文**-此项包含我们想要成员的维度的名称。 同样，返回的最大成员数，您可以指定一些筛选来限制返回的成员。
  
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

 **响应**-响应包括 HTTP 状态代码和一组响应标头。
  
 **状态代码**-成功的操作返回状态代码200（OK）。
  
 **响应标题**-无其他标题。
  
 **响应正文**-下面是 JSON 中的一个示例响应负载，用于响应 "[开始日期]" 请求。[Month] "维度。
  
> [!NOTE]
> 列表仅显示列表的一小部分。 
  
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
