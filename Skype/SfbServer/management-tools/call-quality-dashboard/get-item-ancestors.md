---
title: 获取项目上级
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: 摘要：了解作为项目服务的一部分的 "获取项目上级" 操作。 项目服务是适用于呼叫质量仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。
ms.openlocfilehash: c82ae699cab0bf812f281fc2f2ad54323bcf8f7f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992679"
---
# <a name="get-item-ancestors"></a><span data-ttu-id="dee1e-105">获取项目上级</span><span class="sxs-lookup"><span data-stu-id="dee1e-105">Get Item Ancestors</span></span>
 
<span data-ttu-id="dee1e-106">**摘要：** 了解 "获取项目上级" 操作，它是项目服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="dee1e-106">**Summary:** Learn about the Get Item Ancestors operation, which is part of the Item Service.</span></span> <span data-ttu-id="dee1e-107">项目服务是适用于呼叫质量仪表板的知识库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="dee1e-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="dee1e-108">通话质量仪表板是 Skype for business 服务器的工具。</span><span class="sxs-lookup"><span data-stu-id="dee1e-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="dee1e-109">"获取项目上级" 操作是 "知识库 API for 通话质量" 仪表板中的项目服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="dee1e-109">The Get Item Ancestors operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item-ancestors"></a><span data-ttu-id="dee1e-110">获取项目上级</span><span class="sxs-lookup"><span data-stu-id="dee1e-110">Get Item Ancestors</span></span>

<span data-ttu-id="dee1e-111">获取项目祖先从存储库返回特定项目上级。</span><span class="sxs-lookup"><span data-stu-id="dee1e-111">Get Item Ancestors returns a specific items ancestors from the repository.</span></span>
  

|<span data-ttu-id="dee1e-112">**种**</span><span class="sxs-lookup"><span data-stu-id="dee1e-112">**Method**</span></span>|<span data-ttu-id="dee1e-113">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="dee1e-113">**Request URI**</span></span>|<span data-ttu-id="dee1e-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="dee1e-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="dee1e-115">获取</span><span class="sxs-lookup"><span data-stu-id="dee1e-115">GET</span></span>  <br/> |<span data-ttu-id="dee1e-116">https://\<portal\>/QoERepositoryService/repository/itemAncestors/{itemId}</span><span class="sxs-lookup"><span data-stu-id="dee1e-116">https://\<portal\>/QoERepositoryService/repository/itemAncestors/{itemId}</span></span>  <br/> |<span data-ttu-id="dee1e-117">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="dee1e-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="dee1e-118">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="dee1e-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="dee1e-119">**请求标题**-无其他标题。</span><span class="sxs-lookup"><span data-stu-id="dee1e-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="dee1e-120">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="dee1e-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="dee1e-121">**响应**-响应包括 HTTP 状态代码和一组响应标头。</span><span class="sxs-lookup"><span data-stu-id="dee1e-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="dee1e-122">**状态代码**-成功的操作返回状态代码200（OK）。</span><span class="sxs-lookup"><span data-stu-id="dee1e-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="dee1e-123">如果找不到指定的用户 ID，将返回状态代码404（未找到）。</span><span class="sxs-lookup"><span data-stu-id="dee1e-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="dee1e-124">**响应标题**-无其他标题。</span><span class="sxs-lookup"><span data-stu-id="dee1e-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="dee1e-125">**响应正文**-下面是 JSON 中的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="dee1e-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
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

 <span data-ttu-id="dee1e-126">*Item1* -项目的 ID。</span><span class="sxs-lookup"><span data-stu-id="dee1e-126">*Item1*  - ID of the item.</span></span>
  
 <span data-ttu-id="dee1e-127">*Item2* -深度指项目的距离。</span><span class="sxs-lookup"><span data-stu-id="dee1e-127">*Item2*  - Depth is the distance from the Item.</span></span> <span data-ttu-id="dee1e-128">0是直接父项。</span><span class="sxs-lookup"><span data-stu-id="dee1e-128">0 is the immediate parent.</span></span>
  
 <span data-ttu-id="dee1e-129">*Item3* -项目的标题。</span><span class="sxs-lookup"><span data-stu-id="dee1e-129">*Item3*  - Title of the item.</span></span>
  

