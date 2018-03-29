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
# <a name="run-query"></a><span data-ttu-id="98894-104">运行查询</span><span class="sxs-lookup"><span data-stu-id="98894-104">Run Query</span></span>
 
<span data-ttu-id="98894-105">**摘要：**了解如何运行查询操作，它是呼叫质量仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="98894-105">**Summary:** Learn about the Run Query operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="98894-106">通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="98894-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="98894-107">运行查询操作是呼叫质量仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="98894-107">The Run Query operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="run-query"></a><span data-ttu-id="98894-108">运行查询</span><span class="sxs-lookup"><span data-stu-id="98894-108">Run Query</span></span>

<span data-ttu-id="98894-109">运行的查询操作提供了基于指定的尺寸、 尺寸和筛选多维数据集上运行查询的能力，并重新返回的数据。</span><span class="sxs-lookup"><span data-stu-id="98894-109">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>
  

|<span data-ttu-id="98894-110">**方法**</span><span class="sxs-lookup"><span data-stu-id="98894-110">**Method**</span></span>|<span data-ttu-id="98894-111">**请求的 URI**</span><span class="sxs-lookup"><span data-stu-id="98894-111">**Request URI**</span></span>|<span data-ttu-id="98894-112">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="98894-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="98894-113">发布</span><span class="sxs-lookup"><span data-stu-id="98894-113">POST</span></span>  <br/> |<span data-ttu-id="98894-114">https://\<门户网站\>/QoEDataService/RunQuery</span><span class="sxs-lookup"><span data-stu-id="98894-114">https://\<portal\>/QoEDataService/RunQuery</span></span>  <br/> |<span data-ttu-id="98894-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="98894-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="98894-116">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="98894-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="98894-117">**请求标头**的任何其他标头。</span><span class="sxs-lookup"><span data-stu-id="98894-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="98894-118">**请求正文**-这里是 json 格式的示例请求负载。</span><span class="sxs-lookup"><span data-stu-id="98894-118">**Request Body** - Here is a sample request payload in JSON.</span></span> <span data-ttu-id="98894-119">它包含维度、 筛选器和测量所需的查询。</span><span class="sxs-lookup"><span data-stu-id="98894-119">It contains dimensions, filters, and measurement required for a query.</span></span>
  
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

 <span data-ttu-id="98894-120">*筛选器*的列表中的筛选器表达式，由此产生的数据集将反映只是感兴趣的数据的子集应用。</span><span class="sxs-lookup"><span data-stu-id="98894-120">*Filters*  - A list of filter expressions to be applied such that the resulting data set will reflect only the subset of the data that are of interest.</span></span>
  
 <span data-ttu-id="98894-121">*尺寸*-用于聚合数据的维度列表。</span><span class="sxs-lookup"><span data-stu-id="98894-121">*Dimensions*  - A list of dimensions that will be used for aggregating the data.</span></span> <span data-ttu-id="98894-122">至少一个维度是必需的但可以指定多个维度以获得更高层次的子聚合。</span><span class="sxs-lookup"><span data-stu-id="98894-122">At least one dimension is required but multiple dimensions may be specified to obtain additional level of sub-aggregations.</span></span>
  
 <span data-ttu-id="98894-123">*量化指标*的量化指标，也称为事实，是进行聚合所需的标准列表根据您指定的维度。</span><span class="sxs-lookup"><span data-stu-id="98894-123">*Measurements*  - A list of measurements, also known as facts, that are the desired metrics to be aggregated based on the dimensions you specified.</span></span>
  
 <span data-ttu-id="98894-124">*趋势*的更多控制指令，以自定义结果数据。</span><span class="sxs-lookup"><span data-stu-id="98894-124">*Trend*  - Additional control instructions to customize the result data.</span></span>
  
 <span data-ttu-id="98894-125">**响应**-响应包括 HTTP 状态代码和一套响应标头。</span><span class="sxs-lookup"><span data-stu-id="98894-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="98894-126">**状态代码**-操作成功返回状态码 200 (OK)。</span><span class="sxs-lookup"><span data-stu-id="98894-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="98894-127">**响应标头**的任何其他标头。</span><span class="sxs-lookup"><span data-stu-id="98894-127">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="98894-128">**响应正文**-下面是 json 格式的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="98894-128">**Response Body** - Below is a sample response payload in JSON.</span></span> <span data-ttu-id="98894-129">它包含模拟运算表，它包含的数据，它还包含元数据，其中显示了查询执行时间以及从缓存是数据。</span><span class="sxs-lookup"><span data-stu-id="98894-129">It contains a data table which contains the data, also it will contain a meta data, which shows query execution time and whether or not the data is from the cache.</span></span>
  
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

 <span data-ttu-id="98894-130">*执行时间*的服务器返回数据所花费的总时间。</span><span class="sxs-lookup"><span data-stu-id="98894-130">*Execution Time*  - The total time it took for the server to return the data.</span></span> <span data-ttu-id="98894-131">这可能会或可能不涉及缓存。</span><span class="sxs-lookup"><span data-stu-id="98894-131">This may or may not involve cache.</span></span>
  
 <span data-ttu-id="98894-132">*数据结果*的查询的结果。</span><span class="sxs-lookup"><span data-stu-id="98894-132">*Data Result*  - The result of the query.</span></span> <span data-ttu-id="98894-133">它是一个二维数组，其中包含的维度的成员的所有排列和每个元素，其中包含的维度的成员名称，以及指定度量值的聚合的值。</span><span class="sxs-lookup"><span data-stu-id="98894-133">It is a two-dimensional array containing all permutations of the dimensions' members, and each element containing the dimensions' member names as well as the aggregated values of the specified Measurements.</span></span>
  
 <span data-ttu-id="98894-134">*结果是从缓存中*的诊断程序。</span><span class="sxs-lookup"><span data-stu-id="98894-134">*Result is From Cache*  - For diagnostics.</span></span> <span data-ttu-id="98894-135">指示结果是否是从缓存或 QoE 多维数据集。</span><span class="sxs-lookup"><span data-stu-id="98894-135">Indicates whether the result came from the cache or from the QoE Cube.</span></span>
  

