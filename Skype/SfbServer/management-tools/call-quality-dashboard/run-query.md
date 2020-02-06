---
title: 运行查询
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
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: 摘要：了解 "运行查询" 操作，该操作是 "调用质量" 仪表板的数据 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。
ms.openlocfilehash: 4e520921496a1650af12b342fd5a0244fe9eb7a5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816681"
---
# <a name="run-query"></a>运行查询

**摘要：** 了解 "运行查询" 操作，该操作是 "调用质量" 仪表板的数据 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。

"运行查询" 操作是 "调用质量" 仪表板的数据 API 的一部分。

## <a name="run-query"></a>运行查询

"运行查询" 操作提供基于指定的维度、度量和筛选器对多维数据集运行查询并返回数据的功能。


|**种**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|发布  <br/> |https://\<portal\>/QoEDataService/RunQuery  <br/> |HTTP/1。1  <br/> |

 **URI 参数**-无。

 **请求标题**-无其他标题。

 **请求正文**-以下是 JSON 中的示例请求负载。 它包含查询所需的维度、筛选器和度量。

```json
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

 *筛选器*-要应用的筛选器表达式的列表，以便生成的数据集将仅反映感兴趣的数据子集。

 *维度*-将用于聚合数据的维度的列表。 至少需要一个维度，但可以指定多个维度以获取其他级别的子聚合。

 *度量*-根据你指定的维度聚合所需指标的度量（也称为事实）的列表。

 *趋势*线-其他控制说明，用于自定义结果数据。

 **响应**-响应包括 HTTP 状态代码和一组响应标头。

 **状态代码**-成功的操作返回状态代码200（OK）。

 **响应标题**-无其他标题。

 **响应正文**-下面是 JSON 中的示例响应负载。 它包含包含数据的数据表，还将包含元数据，其中显示查询执行时间以及数据是否来自缓存。

```json
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

 *执行时间*-服务器返回数据所花费的总时间。 这可能会也可能不会涉及缓存。

 *数据结果*-查询的结果。 它是一个二维数组，包含维度成员的所有排列，每个元素包含维度的成员名称以及指定度量值的聚合值。

 *来自缓存的结果*，用于诊断。 指示结果来自缓存还是 QoE 多维数据集。
