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
ms.openlocfilehash: 3720ce118537963e5093741c4f05315e887bd60d
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569745"
---
# <a name="run-query"></a><span data-ttu-id="8faff-104">运行查询</span><span class="sxs-lookup"><span data-stu-id="8faff-104">Run Query</span></span>
 
<span data-ttu-id="8faff-105">**摘要：** 了解有关运行查询操作，它是用于呼叫的质量仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="8faff-105">**Summary:** Learn about the Run Query operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="8faff-106">呼叫质量仪表板是用于业务服务器 2015年的 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="8faff-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="8faff-107">运行查询操作是用于呼叫的质量仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="8faff-107">The Run Query operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="run-query"></a><span data-ttu-id="8faff-108">运行查询</span><span class="sxs-lookup"><span data-stu-id="8faff-108">Run Query</span></span>

<span data-ttu-id="8faff-109">运行的查询操作提供能够运行基于指定的维度和度量，筛选器多维数据集上的查询并返回返回数据。</span><span class="sxs-lookup"><span data-stu-id="8faff-109">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>
  

|<span data-ttu-id="8faff-110">**方法**</span><span class="sxs-lookup"><span data-stu-id="8faff-110">**Method**</span></span>|<span data-ttu-id="8faff-111">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="8faff-111">**Request URI**</span></span>|<span data-ttu-id="8faff-112">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="8faff-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8faff-113">发布</span><span class="sxs-lookup"><span data-stu-id="8faff-113">POST</span></span>  <br/> |<span data-ttu-id="8faff-114">https://\<门户\>/QoEDataService/RunQuery</span><span class="sxs-lookup"><span data-stu-id="8faff-114">https://\<portal\>/QoEDataService/RunQuery</span></span>  <br/> |<span data-ttu-id="8faff-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="8faff-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="8faff-116">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="8faff-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="8faff-117">**请求标头**的任何其他的标头。</span><span class="sxs-lookup"><span data-stu-id="8faff-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="8faff-118">**请求正文**-下面以 json 格式示例请求负载。</span><span class="sxs-lookup"><span data-stu-id="8faff-118">**Request Body** - Here is a sample request payload in JSON.</span></span> <span data-ttu-id="8faff-119">它包含维度、 筛选器和查询所需的度量。</span><span class="sxs-lookup"><span data-stu-id="8faff-119">It contains dimensions, filters, and measurement required for a query.</span></span>
  
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

 <span data-ttu-id="8faff-120">*筛选器*的筛选器表达式，以便生成的数据集将反映感兴趣的数据子集要应用的列表。</span><span class="sxs-lookup"><span data-stu-id="8faff-120">*Filters*  - A list of filter expressions to be applied such that the resulting data set will reflect only the subset of the data that are of interest.</span></span>
  
 <span data-ttu-id="8faff-121">*维度*-维度将用于聚合数据的列表。</span><span class="sxs-lookup"><span data-stu-id="8faff-121">*Dimensions*  - A list of dimensions that will be used for aggregating the data.</span></span> <span data-ttu-id="8faff-122">需要至少一个维度，但可以指定多个维度以获取其他级别的子聚合。</span><span class="sxs-lookup"><span data-stu-id="8faff-122">At least one dimension is required but multiple dimensions may be specified to obtain additional level of sub-aggregations.</span></span>
  
 <span data-ttu-id="8faff-123">*度量值*的度量，也称为事实的聚合所需的标准列表基于您指定的尺寸。</span><span class="sxs-lookup"><span data-stu-id="8faff-123">*Measurements*  - A list of measurements, also known as facts, that are the desired metrics to be aggregated based on the dimensions you specified.</span></span>
  
 <span data-ttu-id="8faff-124">*趋势*-其他控件说明自定义结果数据。</span><span class="sxs-lookup"><span data-stu-id="8faff-124">*Trend*  - Additional control instructions to customize the result data.</span></span>
  
 <span data-ttu-id="8faff-125">**响应**-响应包括 HTTP 状态代码和一响应标头。</span><span class="sxs-lookup"><span data-stu-id="8faff-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="8faff-126">**状态代码**-成功的操作返回状态代码 200 （确定)。</span><span class="sxs-lookup"><span data-stu-id="8faff-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="8faff-127">**响应标头**的任何其他的标头。</span><span class="sxs-lookup"><span data-stu-id="8faff-127">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="8faff-128">**响应正文**-下面是以 json 格式的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="8faff-128">**Response Body** - Below is a sample response payload in JSON.</span></span> <span data-ttu-id="8faff-129">它包含的模拟运算表，其中包含的数据，它将在还包含元数据，其中显示查询执行时间和数据从缓存。</span><span class="sxs-lookup"><span data-stu-id="8faff-129">It contains a data table which contains the data, also it will contain a meta data, which shows query execution time and whether or not the data is from the cache.</span></span>
  
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

 <span data-ttu-id="8faff-130">*执行时间*-服务器返回数据所花费的总时间。</span><span class="sxs-lookup"><span data-stu-id="8faff-130">*Execution Time*  - The total time it took for the server to return the data.</span></span> <span data-ttu-id="8faff-131">这可能也可能不涉及缓存。</span><span class="sxs-lookup"><span data-stu-id="8faff-131">This may or may not involve cache.</span></span>
  
 <span data-ttu-id="8faff-132">*数据结果*-查询的结果。</span><span class="sxs-lookup"><span data-stu-id="8faff-132">*Data Result*  - The result of the query.</span></span> <span data-ttu-id="8faff-133">它是二维数组包含所有排列个维度的成员，以及每个元素包含维度的成员名称，以及指定度量值的聚合的值。</span><span class="sxs-lookup"><span data-stu-id="8faff-133">It is a two-dimensional array containing all permutations of the dimensions' members, and each element containing the dimensions' member names as well as the aggregated values of the specified Measurements.</span></span>
  
 <span data-ttu-id="8faff-134">*结果是从缓存中*的诊断。</span><span class="sxs-lookup"><span data-stu-id="8faff-134">*Result is From Cache*  - For diagnostics.</span></span> <span data-ttu-id="8faff-135">指示结果文件缓存或 QoE 多维数据集。</span><span class="sxs-lookup"><span data-stu-id="8faff-135">Indicates whether the result came from the cache or from the QoE Cube.</span></span>