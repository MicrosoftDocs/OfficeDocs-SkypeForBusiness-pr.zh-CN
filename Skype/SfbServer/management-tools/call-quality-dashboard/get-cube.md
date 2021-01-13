---
title: 获取多维数据集
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
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 摘要：了解 Get Cube 操作，该操作是通话质量仪表板的数据 API 的一部分。 通话质量仪表板是 Skype for Business Server 的工具。
ms.openlocfilehash: a3527f21bc1751c23bba088ae06c3e6702cb8c8e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832622"
---
# <a name="get-cube"></a><span data-ttu-id="f42eb-104">获取多维数据集</span><span class="sxs-lookup"><span data-stu-id="f42eb-104">Get Cube</span></span>
 
<span data-ttu-id="f42eb-105">**摘要：** 了解"获取多维数据集"操作，该操作是通话质量仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="f42eb-105">**Summary:** Learn about the Get Cube operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="f42eb-106">通话质量仪表板是 Skype for Business Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="f42eb-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="f42eb-107">Get Cube 操作是通话质量仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="f42eb-107">The Get Cube operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-cube"></a><span data-ttu-id="f42eb-108">获取多维数据集</span><span class="sxs-lookup"><span data-stu-id="f42eb-108">Get Cube</span></span>

<span data-ttu-id="f42eb-109">获取多维数据集操作返回可用维度和度量的列表。</span><span class="sxs-lookup"><span data-stu-id="f42eb-109">Get Cube operation returns the list of available dimensions and measurements.</span></span>
  

|<span data-ttu-id="f42eb-110">**方法**</span><span class="sxs-lookup"><span data-stu-id="f42eb-110">**Method**</span></span>|<span data-ttu-id="f42eb-111">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="f42eb-111">**Request URI**</span></span>|<span data-ttu-id="f42eb-112">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="f42eb-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f42eb-113">GET</span><span class="sxs-lookup"><span data-stu-id="f42eb-113">GET</span></span>  <br/> |<span data-ttu-id="f42eb-114">https:// \<portal\> /QoEDataService/CubeStructure</span><span class="sxs-lookup"><span data-stu-id="f42eb-114">https://\<portal\>/QoEDataService/CubeStructure</span></span>  <br/> |<span data-ttu-id="f42eb-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="f42eb-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="f42eb-116">**URI 参数** - 无。</span><span class="sxs-lookup"><span data-stu-id="f42eb-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="f42eb-117">**请求标头** - 无其他标头。</span><span class="sxs-lookup"><span data-stu-id="f42eb-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="f42eb-118">**请求正文** - 无。</span><span class="sxs-lookup"><span data-stu-id="f42eb-118">**Request Body** - None.</span></span>
  
 <span data-ttu-id="f42eb-119">**响应** - 响应包括 HTTP 状态代码和一组响应标头。</span><span class="sxs-lookup"><span data-stu-id="f42eb-119">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="f42eb-120">**状态代码** - 成功操作返回状态代码 200 (确定) 。</span><span class="sxs-lookup"><span data-stu-id="f42eb-120">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="f42eb-121">**响应标头** - 无其他标头。</span><span class="sxs-lookup"><span data-stu-id="f42eb-121">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="f42eb-122">**响应正文** - 下面是 JSON 中的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="f42eb-122">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f42eb-123">此示例只显示每个 Cube 元素组的前两个元素。</span><span class="sxs-lookup"><span data-stu-id="f42eb-123">This sample is only showing first two elements of each groups of Cube elements.</span></span> 
  
```json
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

 <span data-ttu-id="f42eb-124">*KPI*  - 保留。</span><span class="sxs-lookup"><span data-stu-id="f42eb-124">*KPIs*  - Reserved.</span></span> <span data-ttu-id="f42eb-125">请求有效负载的 KPI 部分允许运行查询操作返回多维数据集中定义的 KPI 的值。</span><span class="sxs-lookup"><span data-stu-id="f42eb-125">The KPIs section of a request payload allows Run Query operation to return values for the KPIs defined in the cube.</span></span> <span data-ttu-id="f42eb-126">QoE 多维数据集中尚不存在 KPI。</span><span class="sxs-lookup"><span data-stu-id="f42eb-126">No KPIs exist in the QoE Cube yet.</span></span>
  
 <span data-ttu-id="f42eb-127">*Dimensions*  - 可用于运行查询操作的请求负载的"筛选器"和"维度"部分中的维度列表。</span><span class="sxs-lookup"><span data-stu-id="f42eb-127">*Dimensions*  - The list of dimensions that may be used in Filters and Dimensions sections of a request payload for Run Query operation.</span></span> <span data-ttu-id="f42eb-128">若要在筛选器表达式中使用维度，需要指定一维度成员，可以使用 Get Dimension Members 操作获取该维度。</span><span class="sxs-lookup"><span data-stu-id="f42eb-128">To use a dimension in a filter expression, you need to specify a dimension member, which can be obtained using Get Dimension Members operation.</span></span>
  
 <span data-ttu-id="f42eb-129">*度量*  - 运行查询操作的请求有效负载的"度量"部分可能使用的度量列表。</span><span class="sxs-lookup"><span data-stu-id="f42eb-129">*Measurements*  - The list of measurements that may be used in Measurements section of a request payload for Run Query operation.</span></span>
  

