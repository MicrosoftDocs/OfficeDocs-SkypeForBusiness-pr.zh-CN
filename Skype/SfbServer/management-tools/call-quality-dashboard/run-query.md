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
description: 摘要： 了解如何运行查询操作，它是用于呼叫的质量仪表板的数据 API 的一部分。 呼叫质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: 720bcc16b89ed2cd2b92eababb389d6c363d734d
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2018
ms.locfileid: "26293901"
---
# <a name="run-query"></a>运行查询

**摘要：** 了解有关运行查询操作，它是用于呼叫的质量仪表板的数据 API 的一部分。 呼叫质量仪表板是用于业务服务器 2015年的 Skype 的工具。

运行查询操作是用于呼叫的质量仪表板的数据 API 的一部分。

## <a name="run-query"></a>运行查询

运行的查询操作提供能够运行基于指定的维度和度量，筛选器多维数据集上的查询并返回返回数据。


|**方法**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|发布  <br/> |https://\<门户\>/QoEDataService/RunQuery  <br/> |HTTP/1.1  <br/> |

 **URI 参数**-无。

 **请求标头**的任何其他的标头。

 **请求正文**-下面以 json 格式示例请求负载。 它包含维度、 筛选器和查询所需的度量。

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

 *筛选器*的筛选器表达式，以便生成的数据集将反映感兴趣的数据子集要应用的列表。

 *维度*-维度将用于聚合数据的列表。 需要至少一个维度，但可以指定多个维度以获取其他级别的子聚合。

 *度量值*的度量，也称为事实的聚合所需的标准列表基于您指定的尺寸。

 *趋势*-其他控件说明自定义结果数据。

 **响应**-响应包括 HTTP 状态代码和一响应标头。

 **状态代码**-成功的操作返回状态代码 200 （确定)。

 **响应标头**的任何其他的标头。

 **响应正文**-下面是以 json 格式的示例响应负载。 它包含的模拟运算表，其中包含的数据，它将在还包含元数据，其中显示查询执行时间和数据从缓存。

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

 *执行时间*-服务器返回数据所花费的总时间。 这可能也可能不涉及缓存。

 *数据结果*-查询的结果。 它是二维数组包含所有排列个维度的成员，以及每个元素包含维度的成员名称，以及指定度量值的聚合的值。

 *结果是从缓存中*的诊断。 指示结果文件缓存或 QoE 多维数据集。