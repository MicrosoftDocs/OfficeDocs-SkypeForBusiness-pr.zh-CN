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
# <a name="get-cube"></a><span data-ttu-id="ef970-104">获取多维数据集</span><span class="sxs-lookup"><span data-stu-id="ef970-104">Get Cube</span></span>
 
<span data-ttu-id="ef970-105">**摘要：**了解有关获取多维数据集操作，这是呼叫质量仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="ef970-105">**Summary:** Learn about the Get Cube operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="ef970-106">通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="ef970-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ef970-107">获取多维数据集操作是呼叫质量仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="ef970-107">The Get Cube operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-cube"></a><span data-ttu-id="ef970-108">获取多维数据集</span><span class="sxs-lookup"><span data-stu-id="ef970-108">Get Cube</span></span>

<span data-ttu-id="ef970-109">获取操作返回多维数据集中可用的维度和度量值的列表。</span><span class="sxs-lookup"><span data-stu-id="ef970-109">Get Cube operation returns the list of available dimensions and measurements.</span></span>
  

|<span data-ttu-id="ef970-110">**方法**</span><span class="sxs-lookup"><span data-stu-id="ef970-110">**Method**</span></span>|<span data-ttu-id="ef970-111">**请求的 URI**</span><span class="sxs-lookup"><span data-stu-id="ef970-111">**Request URI**</span></span>|<span data-ttu-id="ef970-112">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="ef970-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ef970-113">获取</span><span class="sxs-lookup"><span data-stu-id="ef970-113">GET</span></span>  <br/> |<span data-ttu-id="ef970-114">https://\<门户网站\>/QoEDataService/CubeStructure</span><span class="sxs-lookup"><span data-stu-id="ef970-114">https://\<portal\>/QoEDataService/CubeStructure</span></span>  <br/> |<span data-ttu-id="ef970-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="ef970-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="ef970-116">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="ef970-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="ef970-117">**请求标头**的任何其他标头。</span><span class="sxs-lookup"><span data-stu-id="ef970-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="ef970-118">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="ef970-118">**Request Body** - None.</span></span>
  
 <span data-ttu-id="ef970-119">**响应**-响应包括 HTTP 状态代码和一套响应标头。</span><span class="sxs-lookup"><span data-stu-id="ef970-119">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="ef970-120">**状态代码**-操作成功返回状态码 200 (OK)。</span><span class="sxs-lookup"><span data-stu-id="ef970-120">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="ef970-121">**响应标头**的任何其他标头。</span><span class="sxs-lookup"><span data-stu-id="ef970-121">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="ef970-122">**响应正文**-下面是 json 格式的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="ef970-122">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ef970-123">此示例仅显示多维数据集元素的每个组的前两个元素。</span><span class="sxs-lookup"><span data-stu-id="ef970-123">This sample is only showing first two elements of each groups of Cube elements.</span></span> 
  
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

 <span data-ttu-id="ef970-124">*Kpi*的保留。</span><span class="sxs-lookup"><span data-stu-id="ef970-124">*KPIs*  - Reserved.</span></span> <span data-ttu-id="ef970-125">请求负载的 Kpi 部分允许运行查询要返回的多维数据集中定义 Kpi 值的操作。</span><span class="sxs-lookup"><span data-stu-id="ef970-125">The KPIs section of a request payload allows Run Query operation to return values for the KPIs defined in the cube.</span></span> <span data-ttu-id="ef970-126">Kpi 尚存在 QoE 多维数据集中。</span><span class="sxs-lookup"><span data-stu-id="ef970-126">No KPIs exist in the QoE Cube yet.</span></span>
  
 <span data-ttu-id="ef970-127">*尺寸*-可用于筛选器和维度部分的请求负载运行查询操作的维度的列表。</span><span class="sxs-lookup"><span data-stu-id="ef970-127">*Dimensions*  - The list of dimensions that may be used in Filters and Dimensions sections of a request payload for Run Query operation.</span></span> <span data-ttu-id="ef970-128">若要在筛选器表达式中使用一个维度，您需要指定维度成员，可以使用获取维度成员操作。</span><span class="sxs-lookup"><span data-stu-id="ef970-128">To use a dimension in a filter expression, you need to specify a dimension member, which can be obtained using Get Dimension Members operation.</span></span>
  
 <span data-ttu-id="ef970-129">*度量值*的度量单位可用于测量部分请求有效负载中运行查询操作的列表。</span><span class="sxs-lookup"><span data-stu-id="ef970-129">*Measurements*  - The list of measurements that may be used in Measurements section of a request payload for Run Query operation.</span></span>
  

