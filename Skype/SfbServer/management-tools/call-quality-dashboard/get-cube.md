---
title: 获取多维数据集
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 摘要： 了解如何获取多维数据集操作，这是呼叫质量仪表板的数据 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: e39a88e249dc807b201b08d966285d93ae7f82a6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="get-cube"></a>获取多维数据集
 
**摘要：**了解有关获取多维数据集操作，这是呼叫质量仪表板的数据 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
  
获取多维数据集操作是呼叫质量仪表板的数据 API 的一部分。
  
## <a name="get-cube"></a>获取多维数据集

获取操作返回多维数据集中可用的维度和度量值的列表。
  

|**方法**|**请求的 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|获取  <br/> |https://\<门户网站\>/QoEDataService/CubeStructure  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数**-无。
  
 **请求标头**的任何其他标头。
  
 **请求正文**-无。
  
 **响应**-响应包括 HTTP 状态代码和一套响应标头。
  
 **状态代码**-操作成功返回状态码 200 (OK)。
  
 **响应标头**的任何其他标头。
  
 **响应正文**-下面是 json 格式的示例响应负载。
  
> [!NOTE]
> 此示例仅显示多维数据集元素的每个组的前两个元素。 
  
```
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

 *Kpi*的保留。 请求负载的 Kpi 部分允许运行查询要返回的多维数据集中定义 Kpi 值的操作。 Kpi 尚存在 QoE 多维数据集中。
  
 *尺寸*-可用于筛选器和维度部分的请求负载运行查询操作的维度的列表。 若要在筛选器表达式中使用一个维度，您需要指定维度成员，可以使用获取维度成员操作。
  
 *度量值*的度量单位可用于测量部分请求有效负载中运行查询操作的列表。
  

