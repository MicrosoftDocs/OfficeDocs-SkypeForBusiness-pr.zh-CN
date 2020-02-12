---
title: 获取多维数据集
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
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 摘要：了解有关 "获取多维数据集" 操作（这是 "调用质量" 仪表板的数据 API 的一部分）的信息。 通话质量仪表板是 Skype for business 服务器的工具。
ms.openlocfilehash: 1d8327439d79e7d02182dc7195bc0052bf6c923c
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888821"
---
# <a name="get-cube"></a>获取多维数据集
 
**摘要：** 了解 "获取多维数据集" 操作，该操作是 "调用质量" 仪表板的数据 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。
  
"获取多维数据集" 操作是 "调用质量" 仪表板的数据 API 的一部分。
  
## <a name="get-cube"></a>获取多维数据集

获取多维数据集操作返回可用的维度和度量的列表。
  

|**种**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|获取  <br/> |https://\<portal\>/QoEDataService/CubeStructure  <br/> |HTTP/1。1  <br/> |
   
 **URI 参数**-无。
  
 **请求标题**-无其他标题。
  
 **请求正文**-无。
  
 **响应**-响应包括 HTTP 状态代码和一组响应标头。
  
 **状态代码**-成功的操作返回状态代码200（OK）。
  
 **响应标题**-无其他标题。
  
 **响应正文**-下面是 JSON 中的示例响应负载。
  
> [!NOTE]
> 此示例仅显示每组多维数据集元素的前两个元素。 
  
```json
{
"Kpis": [{
"FriendlyName": "Poor Trend Month",
"DataModelName": "[KPIValue].Poor Trend Month",
"Description": null
},
{
"FriendlyName": "Poor Rate Trend Month",
"DataModelName": "[KPIValue].Poor Rate Trend Month",
"Description": null
}],
"Dimensions": [{
"Category": "Access Location Pair",
"Attributes": [{
"FriendlyName": "Location Pair",
"DataModelName": "[Access Location Pair].[Location Pair]",
"Description": "Description of Location Pair"
}]
},
{
"Category": "Audio Bandwidth Est",
"Attributes": [{
"FriendlyName": "Metric",
"DataModelName": "[Audio Bandwidth Est].[Metric]",
"Description": "Description of Metric"
}]
}],
"Measurements": [{
"FriendlyName": "Audio Streams Count",
"DataModelName": "[Measures].[Audio Streams Count]",
"Description": "Description of Audio Streams Count"
},
{
"FriendlyName": "Audio Good Streams JPDR Count",
"DataModelName": "[Measures].[Audio Good Streams JPDR Count]",
"Description": "Description of Audio Good Streams JPDR Count"
}]
}
```

 *Kpi* -已保留。 请求负载的 "Kpi" 部分允许运行查询操作为多维数据集中定义的 Kpi 返回值。 QoE 多维数据集中尚无 Kpi。
  
 *维度*-可用于运行查询操作的请求负载的筛选器和维度部分中的维度列表。 若要在筛选表达式中使用维度，需要指定维度成员，该成员可使用 "获取维度成员" 操作获取。
  
 *度量*-可在运行查询操作的请求负载的度量部分中使用的度量的列表。
  

