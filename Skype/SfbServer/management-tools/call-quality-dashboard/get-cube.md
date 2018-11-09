---
title: 获取多维数据集
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
ms.openlocfilehash: 228ebd8f9bcb6db919f418ef9809bce1b3eb7f90
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035671"
---
# <a name="get-cube"></a><span data-ttu-id="6975b-104">获取多维数据集</span><span class="sxs-lookup"><span data-stu-id="6975b-104">Get Cube</span></span>
 
<span data-ttu-id="6975b-105">**摘要：** 了解有关获取多维数据集操作，它是用于呼叫的质量仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="6975b-105">**Summary:** Learn about the Get Cube operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="6975b-106">呼叫质量仪表板是用于业务服务器 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="6975b-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="6975b-107">获取多维数据集操作是用于呼叫的质量仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="6975b-107">The Get Cube operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-cube"></a><span data-ttu-id="6975b-108">获取多维数据集</span><span class="sxs-lookup"><span data-stu-id="6975b-108">Get Cube</span></span>

<span data-ttu-id="6975b-109">获取多维数据集操作返回可用维度和度量值的列表。</span><span class="sxs-lookup"><span data-stu-id="6975b-109">Get Cube operation returns the list of available dimensions and measurements.</span></span>
  

|<span data-ttu-id="6975b-110">**方法**</span><span class="sxs-lookup"><span data-stu-id="6975b-110">**Method**</span></span>|<span data-ttu-id="6975b-111">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="6975b-111">**Request URI**</span></span>|<span data-ttu-id="6975b-112">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="6975b-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6975b-113">获取</span><span class="sxs-lookup"><span data-stu-id="6975b-113">GET</span></span>  <br/> |<span data-ttu-id="6975b-114">https://\<门户\>/QoEDataService/CubeStructure</span><span class="sxs-lookup"><span data-stu-id="6975b-114">https://\<portal\>/QoEDataService/CubeStructure</span></span>  <br/> |<span data-ttu-id="6975b-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="6975b-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="6975b-116">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="6975b-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="6975b-117">**请求标头**的任何其他的标头。</span><span class="sxs-lookup"><span data-stu-id="6975b-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="6975b-118">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="6975b-118">**Request Body** - None.</span></span>
  
 <span data-ttu-id="6975b-119">**响应**-响应包括 HTTP 状态代码和一响应标头。</span><span class="sxs-lookup"><span data-stu-id="6975b-119">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="6975b-120">**状态代码**-成功的操作返回状态代码 200 （确定)。</span><span class="sxs-lookup"><span data-stu-id="6975b-120">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="6975b-121">**响应标头**的任何其他的标头。</span><span class="sxs-lookup"><span data-stu-id="6975b-121">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="6975b-122">**响应正文**-下面是以 json 格式的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="6975b-122">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6975b-123">此示例仅显示多维数据集元素的每个组的前两个的元素。</span><span class="sxs-lookup"><span data-stu-id="6975b-123">This sample is only showing first two elements of each groups of Cube elements.</span></span> 
  
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

 <span data-ttu-id="6975b-124">*Kpi* -保留。</span><span class="sxs-lookup"><span data-stu-id="6975b-124">*KPIs*  - Reserved.</span></span> <span data-ttu-id="6975b-125">请求负载的 Kpi 部分允许运行查询操作的多维数据集中定义的 Kpi 返回值。</span><span class="sxs-lookup"><span data-stu-id="6975b-125">The KPIs section of a request payload allows Run Query operation to return values for the KPIs defined in the cube.</span></span> <span data-ttu-id="6975b-126">没有 Kpi 尚未存在 QoE 多维数据集中。</span><span class="sxs-lookup"><span data-stu-id="6975b-126">No KPIs exist in the QoE Cube yet.</span></span>
  
 <span data-ttu-id="6975b-127">*维度*-运行查询操作可能中请求负载的筛选器和维度部分中使用的维度的列表。</span><span class="sxs-lookup"><span data-stu-id="6975b-127">*Dimensions*  - The list of dimensions that may be used in Filters and Dimensions sections of a request payload for Run Query operation.</span></span> <span data-ttu-id="6975b-128">若要使用的维度筛选器表达式中，您需要指定维度成员，可使用获取维度成员操作获取。</span><span class="sxs-lookup"><span data-stu-id="6975b-128">To use a dimension in a filter expression, you need to specify a dimension member, which can be obtained using Get Dimension Members operation.</span></span>
  
 <span data-ttu-id="6975b-129">*度量*-可能运行查询操作的请求负载度量值部分中使用的度量值的列表。</span><span class="sxs-lookup"><span data-stu-id="6975b-129">*Measurements*  - The list of measurements that may be used in Measurements section of a request payload for Run Query operation.</span></span>
  

