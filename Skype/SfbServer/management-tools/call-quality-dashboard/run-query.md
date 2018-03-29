---
title: 运行查询
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: 摘要： 了解如何运行查询操作，它是呼叫质量仪表板的数据 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: 6e294625e173854382e39abc098a0480871586ac
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="run-query"></a>运行查询
 
**摘要：**了解如何运行查询操作，它是呼叫质量仪表板的数据 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
  
运行查询操作是呼叫质量仪表板的数据 API 的一部分。
  
## <a name="run-query"></a>运行查询

运行的查询操作提供了基于指定的尺寸、 尺寸和筛选多维数据集上运行查询的能力，并重新返回的数据。
  

|**方法**|**请求的 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|发布  <br/> |https://\<门户网站\>/QoEDataService/RunQuery  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数**-无。
  
 **请求标头**的任何其他标头。
  
 **请求正文**-这里是 json 格式的示例请求负载。 它包含维度、 筛选器和测量所需的查询。
  
```
{
"Filters": [{
"DataModelName": "[StartDate].[Month]",
"Caption": "July 2013",
"Value": "[2015-03-01T00:00:00]",
"Operand": 0,
"UnionGroup": ""
}],
"Dimensions": [{
"DataModelName": "[StartDate].[Month]"
}],
"Measurements": [{
"DataModelName": "[Measures].[Audio Good Streams Count]"
},
{
"DataModelName": "[Measures].[Audio UnClassified Streams Count]"
},
{
"DataModelName": "[Measures].[Audio Poor Streams Count]"
},
{
"DataModelName": "[Measures].[AudioPoorPercentage]"
}],
"Trend": {
"EnableTrend": true,
"SpanCount": 7,
"TrendDate": "2015-3",
"Type": 0
}
}

```

 *筛选器*的列表中的筛选器表达式，由此产生的数据集将反映只是感兴趣的数据的子集应用。
  
 *尺寸*-用于聚合数据的维度列表。 至少一个维度是必需的但可以指定多个维度以获得更高层次的子聚合。
  
 *量化指标*的量化指标，也称为事实，是进行聚合所需的标准列表根据您指定的维度。
  
 *趋势*的更多控制指令，以自定义结果数据。
  
 **响应**-响应包括 HTTP 状态代码和一套响应标头。
  
 **状态代码**-操作成功返回状态码 200 (OK)。
  
 **响应标头**的任何其他标头。
  
 **响应正文**-下面是 json 格式的示例响应负载。 它包含模拟运算表，它包含的数据，它还包含元数据，其中显示了查询执行时间以及从缓存是数据。
  
```
{
"ExecutionTime": "00:00:00.2102630",
"DataResult": [["September 2014",
        1792,
        34,
        78,
        4.171],
        ["October 2014",
        37017,
        1731,
        3305,
        8.197],
        ["November 2014",
        79184,
        3033,
        5556,
        6.557],
        ["December 2014",
        122253,
        4050,
        5444,
        4.263],
        ["January 2015",
        31246,
        1069,
        1342,
        4.118]],
"ResultIsFromCache": false,
"ErrorType": 0
}

```

 *执行时间*的服务器返回数据所花费的总时间。 这可能会或可能不涉及缓存。
  
 *数据结果*的查询的结果。 它是一个二维数组，其中包含的维度的成员的所有排列和每个元素，其中包含的维度的成员名称，以及指定度量值的聚合的值。
  
 *结果是从缓存中*的诊断程序。 指示结果是否是从缓存或 QoE 多维数据集。
  

