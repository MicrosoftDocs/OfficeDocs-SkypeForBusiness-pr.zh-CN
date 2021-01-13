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
description: 摘要：了解运行查询操作，这是通话质量仪表板的数据 API 的一部分。 通话质量仪表板是 Skype for Business Server 的工具。
ms.openlocfilehash: bff24ca5a4d651ba276b4b0d795afabce3c6d0dd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803112"
---
# <a name="run-query"></a><span data-ttu-id="761e5-104">运行查询</span><span class="sxs-lookup"><span data-stu-id="761e5-104">Run Query</span></span>

<span data-ttu-id="761e5-105">**摘要：** 了解运行查询操作，这是通话质量仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="761e5-105">**Summary:** Learn about the Run Query operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="761e5-106">通话质量仪表板是 Skype for Business Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="761e5-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="761e5-107">运行查询操作是通话质量仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="761e5-107">The Run Query operation is part of the Data API for Call Quality Dashboard.</span></span>

## <a name="run-query"></a><span data-ttu-id="761e5-108">运行查询</span><span class="sxs-lookup"><span data-stu-id="761e5-108">Run Query</span></span>

<span data-ttu-id="761e5-109">运行查询操作能够基于指定的维度、度量和筛选器对多维数据集运行查询，并返回数据。</span><span class="sxs-lookup"><span data-stu-id="761e5-109">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>


|<span data-ttu-id="761e5-110">**方法**</span><span class="sxs-lookup"><span data-stu-id="761e5-110">**Method**</span></span>|<span data-ttu-id="761e5-111">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="761e5-111">**Request URI**</span></span>|<span data-ttu-id="761e5-112">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="761e5-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="761e5-113">POST</span><span class="sxs-lookup"><span data-stu-id="761e5-113">POST</span></span>  <br/> |<span data-ttu-id="761e5-114">https:// \<portal\> /QoEDataService/RunQuery</span><span class="sxs-lookup"><span data-stu-id="761e5-114">https://\<portal\>/QoEDataService/RunQuery</span></span>  <br/> |<span data-ttu-id="761e5-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="761e5-115">HTTP/1.1</span></span>  <br/> |

 <span data-ttu-id="761e5-116">**URI 参数** - 无。</span><span class="sxs-lookup"><span data-stu-id="761e5-116">**URI Parameters** - None.</span></span>

 <span data-ttu-id="761e5-117">**请求标头** - 无其他标头。</span><span class="sxs-lookup"><span data-stu-id="761e5-117">**Request Headers** - No additional headers.</span></span>

 <span data-ttu-id="761e5-118">**请求正文** - 下面是 JSON 中的示例请求负载。</span><span class="sxs-lookup"><span data-stu-id="761e5-118">**Request Body** - Here is a sample request payload in JSON.</span></span> <span data-ttu-id="761e5-119">它包含查询所需的维度、筛选器和度量。</span><span class="sxs-lookup"><span data-stu-id="761e5-119">It contains dimensions, filters, and measurement required for a query.</span></span>

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

 <span data-ttu-id="761e5-120">*筛选器*  - 要应用的筛选器表达式的列表，这样生成的数据集将仅反映感兴趣的数据的子集。</span><span class="sxs-lookup"><span data-stu-id="761e5-120">*Filters*  - A list of filter expressions to be applied such that the resulting data set will reflect only the subset of the data that are of interest.</span></span>

 <span data-ttu-id="761e5-121">*维度*  - 将用于聚合数据的维度列表。</span><span class="sxs-lookup"><span data-stu-id="761e5-121">*Dimensions*  - A list of dimensions that will be used for aggregating the data.</span></span> <span data-ttu-id="761e5-122">至少需要一个维度，但可以指定多个维度来获取其他级别的子聚合。</span><span class="sxs-lookup"><span data-stu-id="761e5-122">At least one dimension is required but multiple dimensions may be specified to obtain additional level of sub-aggregations.</span></span>

 <span data-ttu-id="761e5-123">*度量*  - 度量列表（也称为事实）是根据指定的维度聚合的所需指标。</span><span class="sxs-lookup"><span data-stu-id="761e5-123">*Measurements*  - A list of measurements, also known as facts, that are the desired metrics to be aggregated based on the dimensions you specified.</span></span>

 <span data-ttu-id="761e5-124">*趋势*  - 用于自定义结果数据的其他控制说明。</span><span class="sxs-lookup"><span data-stu-id="761e5-124">*Trend*  - Additional control instructions to customize the result data.</span></span>

 <span data-ttu-id="761e5-125">**响应** - 响应包括 HTTP 状态代码和一组响应标头。</span><span class="sxs-lookup"><span data-stu-id="761e5-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>

 <span data-ttu-id="761e5-126">**状态代码** - 成功操作返回状态代码 200 (确定) 。</span><span class="sxs-lookup"><span data-stu-id="761e5-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>

 <span data-ttu-id="761e5-127">**响应标头** - 无其他标头。</span><span class="sxs-lookup"><span data-stu-id="761e5-127">**Response Headers** - No additional headers.</span></span>

 <span data-ttu-id="761e5-128">**响应正文** - 下面是 JSON 中的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="761e5-128">**Response Body** - Below is a sample response payload in JSON.</span></span> <span data-ttu-id="761e5-129">它包含一个包含数据的数据表，还包含一个元数据，其中显示查询执行时间以及数据是否来自缓存。</span><span class="sxs-lookup"><span data-stu-id="761e5-129">It contains a data table which contains the data, also it will contain a meta data, which shows query execution time and whether or not the data is from the cache.</span></span>

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

 <span data-ttu-id="761e5-130">*执行时间*  - 服务器返回数据的总时间。</span><span class="sxs-lookup"><span data-stu-id="761e5-130">*Execution Time*  - The total time it took for the server to return the data.</span></span> <span data-ttu-id="761e5-131">这可能涉及缓存，也可能不涉及缓存。</span><span class="sxs-lookup"><span data-stu-id="761e5-131">This may or may not involve cache.</span></span>

 <span data-ttu-id="761e5-132">*数据*  结果 - 查询的结果。</span><span class="sxs-lookup"><span data-stu-id="761e5-132">*Data Result*  - The result of the query.</span></span> <span data-ttu-id="761e5-133">它是一个二维数组，包含维度成员的所有排列，以及每个包含维度的成员名称以及指定度量的聚合值的元素。</span><span class="sxs-lookup"><span data-stu-id="761e5-133">It is a two-dimensional array containing all permutations of the dimensions' members, and each element containing the dimensions' member names as well as the aggregated values of the specified Measurements.</span></span>

 <span data-ttu-id="761e5-134">*结果为"来自缓存*  - 用于诊断"。</span><span class="sxs-lookup"><span data-stu-id="761e5-134">*Result is From Cache*  - For diagnostics.</span></span> <span data-ttu-id="761e5-135">指示结果来自缓存还是来自 QoE 多维数据集。</span><span class="sxs-lookup"><span data-stu-id="761e5-135">Indicates whether the result came from the cache or from the QoE Cube.</span></span>
