---
title: 获取项目上级
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: 摘要： 了解如何获取项目祖先操作，即项服务的一部分。 项服务是呼叫质量仪表板的存储库 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
ms.openlocfilehash: 7afeecb81d1933b0a308b174e49f6d8ff45a93dd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873110"
---
# <a name="get-item-ancestors"></a><span data-ttu-id="4f91f-105">获取项目上级</span><span class="sxs-lookup"><span data-stu-id="4f91f-105">Get Item Ancestors</span></span>
 
<span data-ttu-id="4f91f-106">**摘要：** 了解有关获取项目祖先操作，即项服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="4f91f-106">**Summary:** Learn about the Get Item Ancestors operation, which is part of the Item Service.</span></span> <span data-ttu-id="4f91f-107">项服务是呼叫质量仪表板的存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="4f91f-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="4f91f-108">呼叫质量仪表板是用于业务服务器 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="4f91f-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="4f91f-109">获取项祖先操作是用于呼叫的质量仪表板的存储库 API 中的项服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="4f91f-109">The Get Item Ancestors operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item-ancestors"></a><span data-ttu-id="4f91f-110">获取项目上级</span><span class="sxs-lookup"><span data-stu-id="4f91f-110">Get Item Ancestors</span></span>

<span data-ttu-id="4f91f-111">从存储库中获取项目祖先返回特定项目上级。</span><span class="sxs-lookup"><span data-stu-id="4f91f-111">Get Item Ancestors returns a specific items ancestors from the repository.</span></span>
  

|<span data-ttu-id="4f91f-112">**方法**</span><span class="sxs-lookup"><span data-stu-id="4f91f-112">**Method**</span></span>|<span data-ttu-id="4f91f-113">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="4f91f-113">**Request URI**</span></span>|<span data-ttu-id="4f91f-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="4f91f-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4f91f-115">获取</span><span class="sxs-lookup"><span data-stu-id="4f91f-115">GET</span></span>  <br/> |<span data-ttu-id="4f91f-116">https://\<门户\>/QoERepositoryService/存储库/itemAncestors / {itemId}</span><span class="sxs-lookup"><span data-stu-id="4f91f-116">https://\<portal\>/QoERepositoryService/repository/itemAncestors/{itemId}</span></span>  <br/> |<span data-ttu-id="4f91f-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="4f91f-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="4f91f-118">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="4f91f-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="4f91f-119">**请求标头**的任何其他的标头。</span><span class="sxs-lookup"><span data-stu-id="4f91f-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="4f91f-120">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="4f91f-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="4f91f-121">**响应**-响应包括 HTTP 状态代码和一响应标头。</span><span class="sxs-lookup"><span data-stu-id="4f91f-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="4f91f-122">**状态代码**-成功的操作返回状态代码 200 （确定)。</span><span class="sxs-lookup"><span data-stu-id="4f91f-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="4f91f-123">如果找不到 ID 指定的用户，则将返回状态代码的 404 （未找到）。</span><span class="sxs-lookup"><span data-stu-id="4f91f-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="4f91f-124">**响应标头**的任何其他的标头。</span><span class="sxs-lookup"><span data-stu-id="4f91f-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="4f91f-125">**响应正文**-下面是以 json 格式的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="4f91f-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
[{
"item1": 1653,
"item2": 0,
"item3": "Audio Streams Monthly Trend"
},
{
"item1": 1652,
"item2": 1,
"item3": "All Audio Streams"
}]
```

 <span data-ttu-id="4f91f-126">*Item1* -项目的 ID。</span><span class="sxs-lookup"><span data-stu-id="4f91f-126">*Item1*  - ID of the item.</span></span>
  
 <span data-ttu-id="4f91f-127">*Item2* -深度是从项目之间的距离。</span><span class="sxs-lookup"><span data-stu-id="4f91f-127">*Item2*  - Depth is the distance from the Item.</span></span> <span data-ttu-id="4f91f-128">0 是直接父。</span><span class="sxs-lookup"><span data-stu-id="4f91f-128">0 is the immediate parent.</span></span>
  
 <span data-ttu-id="4f91f-129">*Item3* -项目的标题。</span><span class="sxs-lookup"><span data-stu-id="4f91f-129">*Item3*  - Title of the item.</span></span>
  

