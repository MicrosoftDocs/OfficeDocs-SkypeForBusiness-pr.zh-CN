---
title: 获取用户设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: '摘要: 了解 "获取用户设置" 操作, 它是 "用户设置" 服务的一部分。 "用户设置" 服务是 "呼叫质量" 仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。'
ms.openlocfilehash: 295e12405eb6a7ebbf45b87e3a06f3a745b90bad
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274651"
---
# <a name="get-user-setting"></a><span data-ttu-id="35384-105">获取用户设置</span><span class="sxs-lookup"><span data-stu-id="35384-105">Get User Setting</span></span>
 
<span data-ttu-id="35384-106">**摘要:** 了解 "获取用户设置" 操作, 该操作是 "用户设置" 服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="35384-106">**Summary:** Learn about the Get User Setting operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="35384-107">"用户设置" 服务是 "呼叫质量" 仪表板的知识库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="35384-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="35384-108">通话质量仪表板是 Skype for business 服务器的工具。</span><span class="sxs-lookup"><span data-stu-id="35384-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="35384-109">"获取用户设置" 操作是 "资源库 API for 通话质量" 仪表板中的 "用户设置" 服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="35384-109">The Get User Setting operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-setting"></a><span data-ttu-id="35384-110">获取用户设置</span><span class="sxs-lookup"><span data-stu-id="35384-110">Get User Setting</span></span>

<span data-ttu-id="35384-111">获取用户设置返回单个用户设置。</span><span class="sxs-lookup"><span data-stu-id="35384-111">Get User Setting returns a single user setting.</span></span>
  

|<span data-ttu-id="35384-112">**种**</span><span class="sxs-lookup"><span data-stu-id="35384-112">**Method**</span></span>|<span data-ttu-id="35384-113">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="35384-113">**Request URI**</span></span>|<span data-ttu-id="35384-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="35384-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="35384-115">获取</span><span class="sxs-lookup"><span data-stu-id="35384-115">GET</span></span>  <br/> |<span data-ttu-id="35384-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting/{key}</span><span class="sxs-lookup"><span data-stu-id="35384-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting/{key}</span></span>  <br/> |<span data-ttu-id="35384-117">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="35384-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="35384-118">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="35384-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="35384-119">**请求标题**-无其他标题。</span><span class="sxs-lookup"><span data-stu-id="35384-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="35384-120">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="35384-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="35384-121">**响应**-响应包括 HTTP 状态代码和一组响应标头。</span><span class="sxs-lookup"><span data-stu-id="35384-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="35384-122">**状态代码**-成功的操作返回状态代码 200 (OK)。</span><span class="sxs-lookup"><span data-stu-id="35384-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="35384-123">**响应标题**-无其他标题。</span><span class="sxs-lookup"><span data-stu-id="35384-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="35384-124">**响应正文**-下面是 JSON 中的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="35384-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 <span data-ttu-id="35384-125">*userId* -用户 ID。</span><span class="sxs-lookup"><span data-stu-id="35384-125">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="35384-126">设置的*键*。</span><span class="sxs-lookup"><span data-stu-id="35384-126">*key*  - Key of the setting.</span></span>
  
 <span data-ttu-id="35384-127">*value* -设置的值。</span><span class="sxs-lookup"><span data-stu-id="35384-127">*value*  - Value of the setting.</span></span>
  

