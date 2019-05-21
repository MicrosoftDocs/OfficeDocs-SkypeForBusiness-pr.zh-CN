---
title: 获取多维数据集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: '摘要: 了解有关 "获取多维数据集" 操作 (这是 "调用质量" 仪表板的数据 API 的一部分) 的信息。 通话质量仪表板是 Skype for business 服务器的工具。'
ms.openlocfilehash: 970187ce9f95700185ab09bd7aadf9045575b393
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274770"
---
# <a name="get-cube"></a><span data-ttu-id="1df2c-104">获取多维数据集</span><span class="sxs-lookup"><span data-stu-id="1df2c-104">Get Cube</span></span>
 
<span data-ttu-id="1df2c-105">**摘要:** 了解 "获取多维数据集" 操作, 该操作是 "调用质量" 仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="1df2c-105">**Summary:** Learn about the Get Cube operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="1df2c-106">通话质量仪表板是 Skype for business 服务器的工具。</span><span class="sxs-lookup"><span data-stu-id="1df2c-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="1df2c-107">"获取多维数据集" 操作是 "调用质量" 仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="1df2c-107">The Get Cube operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-cube"></a><span data-ttu-id="1df2c-108">获取多维数据集</span><span class="sxs-lookup"><span data-stu-id="1df2c-108">Get Cube</span></span>

<span data-ttu-id="1df2c-109">获取多维数据集操作返回可用的维度和度量的列表。</span><span class="sxs-lookup"><span data-stu-id="1df2c-109">Get Cube operation returns the list of available dimensions and measurements.</span></span>
  

|<span data-ttu-id="1df2c-110">**种**</span><span class="sxs-lookup"><span data-stu-id="1df2c-110">**Method**</span></span>|<span data-ttu-id="1df2c-111">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="1df2c-111">**Request URI**</span></span>|<span data-ttu-id="1df2c-112">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="1df2c-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1df2c-113">获取</span><span class="sxs-lookup"><span data-stu-id="1df2c-113">GET</span></span>  <br/> |<span data-ttu-id="1df2c-114">https://\<portal\>/QoEDataService/CubeStructure</span><span class="sxs-lookup"><span data-stu-id="1df2c-114">https://\<portal\>/QoEDataService/CubeStructure</span></span>  <br/> |<span data-ttu-id="1df2c-115">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="1df2c-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="1df2c-116">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="1df2c-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="1df2c-117">**请求标题**-无其他标题。</span><span class="sxs-lookup"><span data-stu-id="1df2c-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="1df2c-118">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="1df2c-118">**Request Body** - None.</span></span>
  
 <span data-ttu-id="1df2c-119">**响应**-响应包括 HTTP 状态代码和一组响应标头。</span><span class="sxs-lookup"><span data-stu-id="1df2c-119">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="1df2c-120">**状态代码**-成功的操作返回状态代码 200 (OK)。</span><span class="sxs-lookup"><span data-stu-id="1df2c-120">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="1df2c-121">**响应标题**-无其他标题。</span><span class="sxs-lookup"><span data-stu-id="1df2c-121">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="1df2c-122">**响应正文**-下面是 JSON 中的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="1df2c-122">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1df2c-123">此示例仅显示每组多维数据集元素的前两个元素。</span><span class="sxs-lookup"><span data-stu-id="1df2c-123">This sample is only showing first two elements of each groups of Cube elements.</span></span> 
  
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

 <span data-ttu-id="1df2c-124">*Kpi* -已保留。</span><span class="sxs-lookup"><span data-stu-id="1df2c-124">*KPIs*  - Reserved.</span></span> <span data-ttu-id="1df2c-125">请求负载的 "Kpi" 部分允许运行查询操作为多维数据集中定义的 Kpi 返回值。</span><span class="sxs-lookup"><span data-stu-id="1df2c-125">The KPIs section of a request payload allows Run Query operation to return values for the KPIs defined in the cube.</span></span> <span data-ttu-id="1df2c-126">QoE 多维数据集中尚无 Kpi。</span><span class="sxs-lookup"><span data-stu-id="1df2c-126">No KPIs exist in the QoE Cube yet.</span></span>
  
 <span data-ttu-id="1df2c-127">*维度*-可用于运行查询操作的请求负载的筛选器和维度部分中的维度列表。</span><span class="sxs-lookup"><span data-stu-id="1df2c-127">*Dimensions*  - The list of dimensions that may be used in Filters and Dimensions sections of a request payload for Run Query operation.</span></span> <span data-ttu-id="1df2c-128">若要在筛选表达式中使用维度, 需要指定维度成员, 该成员可使用 "获取维度成员" 操作获取。</span><span class="sxs-lookup"><span data-stu-id="1df2c-128">To use a dimension in a filter expression, you need to specify a dimension member, which can be obtained using Get Dimension Members operation.</span></span>
  
 <span data-ttu-id="1df2c-129">*度量*-可在运行查询操作的请求负载的度量部分中使用的度量的列表。</span><span class="sxs-lookup"><span data-stu-id="1df2c-129">*Measurements*  - The list of measurements that may be used in Measurements section of a request payload for Run Query operation.</span></span>
  

