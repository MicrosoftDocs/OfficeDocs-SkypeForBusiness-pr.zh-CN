---
title: 运行查询
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
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: 摘要：了解运行查询操作，这是通话质量仪表板的数据 API 的一部分。 通话质量仪表板是一种用于Skype for Business Server。
ms.openlocfilehash: 860760303510b792cba70fc211ac8b7f9b994996b4937aa333ed54fcffb6eb75
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340858"
---
# <a name="run-query"></a>运行查询

**摘要：** 了解运行查询操作，这是通话质量仪表板的数据 API 的一部分。 通话质量仪表板是一种用于Skype for Business Server。

运行查询操作是通话质量仪表板的数据 API 的一部分。

## <a name="run-query"></a>运行查询

通过运行查询操作，可以基于指定的维度、度量和筛选器对多维数据集运行查询，并返回数据。


|**方法**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|POST  <br/> |https:// \<portal\> /QoEDataService/RunQuery  <br/> |HTTP/1.1  <br/> |

 **URI 参数** - 无。

 **请求标头** - 无其他标头。

 **请求正文** - 下面是 JSON 中的示例请求有效负载。 它包含查询所需的维度、筛选器和度量。

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

 *Filters*  - 要应用的筛选器表达式列表，这样生成的数据集将仅反映感兴趣的数据的子集。

 *Dimensions*  - 将用于聚合数据的维度列表。 至少需要一个维度，但可以指定多个维度来获取其他级别的子聚合。

 *度量*  - 度量列表（也称为事实）是根据您指定的维度聚合的所需指标。

 *趋势*  - 用于自定义结果数据的其他控制说明。

 **响应** - 响应包括 HTTP 状态代码和一组响应标头。

 **状态代码** - 成功操作返回状态代码 200 (确定) 。

 **响应标头** - 无其他标头。

 **响应正文** - 下面是 JSON 中的示例响应有效负载。 它包含一个包含数据的数据表，它还将包含一个元数据，其中显示查询执行时间以及数据是否来自缓存。

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

 *执行时间*  - 服务器返回数据所花时间的总时间。 这可能涉及缓存，也可能不涉及缓存。

 *数据*  结果 - 查询的结果。 它是一个二维数组，包含维度成员的所有排列，每个元素包含维度的成员名称以及指定 Measurements 的聚合值。

 *结果为"来自缓存*  - 用于诊断"。 指示结果来自缓存还是来自 QoE 多维数据集。
