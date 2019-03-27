---
title: 获取多维数据集
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 摘要： 了解如何获取多维数据集操作，它是用于呼叫的质量仪表板的数据 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
ms.openlocfilehash: 5c0623b92c9169a9e54f92d21358fb377c84a8f8
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897134"
---
# <a name="get-cube"></a>获取多维数据集
 
**摘要：** 了解有关获取多维数据集操作，它是用于呼叫的质量仪表板的数据 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
  
获取多维数据集操作是用于呼叫的质量仪表板的数据 API 的一部分。
  
## <a name="get-cube"></a>获取多维数据集

获取多维数据集操作返回可用维度和度量值的列表。
  

|**方法**|**请求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|获取  <br/> |https://\<门户\>/QoEDataService/CubeStructure  <br/> |HTTP/1.1  <br/> |
   
 **URI 参数**-无。
  
 **请求标头**的任何其他的标头。
  
 **请求正文**-无。
  
 **响应**-响应包括 HTTP 状态代码和一响应标头。
  
 **状态代码**-成功的操作返回状态代码 200 （确定)。
  
 **响应标头**的任何其他的标头。
  
 **响应正文**-下面是以 json 格式的示例响应负载。
  
> [!NOTE]
> 此示例仅显示多维数据集元素的每个组的前两个的元素。 
  
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

 *Kpi* -保留。 请求负载的 Kpi 部分允许运行查询操作的多维数据集中定义的 Kpi 返回值。 没有 Kpi 尚未存在 QoE 多维数据集中。
  
 *维度*-运行查询操作可能中请求负载的筛选器和维度部分中使用的维度的列表。 若要使用的维度筛选器表达式中，您需要指定维度成员，可使用获取维度成员操作获取。
  
 *度量*-可能运行查询操作的请求负载度量值部分中使用的度量值的列表。
  

