---
title: 获取维度成员
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
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 摘要：了解"获取维度成员"操作。 "获取维度成员"操作是通话质量仪表板的数据 API 的一部分。 通话质量仪表板是 Skype for Business Server 的工具。
ms.openlocfilehash: ffec3b02a3c876a003adb679a28b0e8f2edb91c2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832632"
---
# <a name="get-dimension-members"></a>获取维度成员
 
**摘要：** 了解"获取维度成员"操作。 "获取维度成员"操作是通话质量仪表板的数据 API 的一部分。 通话质量仪表板是 Skype for Business Server 的工具。
  
"获取维度成员"操作是通话质量仪表板的数据 API 的一部分。
  
## <a name="get-dimension-members"></a>获取维度成员

"获取维度成员"操作返回特定维度的成员列表。 它还提供筛选成员列表和获取子集的能力，以减少线路传输成本。
  

|**方法**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|POST  <br/> |https:// \<portal\> /QoEDataService/DimensionMembers  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数** - 无。
  
 **请求标头** - 无其他标头。
  
 **请求正文** - 这包含我们希望成员使用的尺寸的名称。 此外，返回的最大成员数，旁边可以指定一些筛选以限制返回的成员。
  
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
  
 **状态代码** - 成功操作返回状态代码 200 (确定) 。
  
 **响应标头** - 无其他标头。
  
 **响应正文** - 下面是 JSON 中响应"[StartDate]请求的示例响应有效负载。[Month]" 维度。
  
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
