---
title: 获取项目
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 摘要：了解 "获取项目" 操作，该操作是项目服务的一部分。 项目服务是适用于呼叫质量仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。
ms.openlocfilehash: 208ad3d1852ab58b7fcd0d01eeb440097328f733
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992669"
---
# <a name="get-item"></a><span data-ttu-id="31bbf-105">获取项目</span><span class="sxs-lookup"><span data-stu-id="31bbf-105">Get Item</span></span>
 
<span data-ttu-id="31bbf-106">**摘要：** 了解 "获取项目" 操作，该操作是项目服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="31bbf-106">**Summary:** Learn about the Get Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="31bbf-107">项目服务是适用于呼叫质量仪表板的知识库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="31bbf-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="31bbf-108">通话质量仪表板是 Skype for business 服务器的工具。</span><span class="sxs-lookup"><span data-stu-id="31bbf-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="31bbf-109">获取项目操作是 "知识库 API for 通话质量" 仪表板中的项目服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="31bbf-109">The Get Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item"></a><span data-ttu-id="31bbf-110">获取项目</span><span class="sxs-lookup"><span data-stu-id="31bbf-110">Get Item</span></span>

<span data-ttu-id="31bbf-111">获取项目返回存储库中的特定项目。</span><span class="sxs-lookup"><span data-stu-id="31bbf-111">Get Item returns a specific item in the repository.</span></span>
  
|<span data-ttu-id="31bbf-112">**种**</span><span class="sxs-lookup"><span data-stu-id="31bbf-112">**Method**</span></span>|<span data-ttu-id="31bbf-113">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="31bbf-113">**Request URI**</span></span>|<span data-ttu-id="31bbf-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="31bbf-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="31bbf-115">获取</span><span class="sxs-lookup"><span data-stu-id="31bbf-115">GET</span></span>  <br/> |<span data-ttu-id="31bbf-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span><span class="sxs-lookup"><span data-stu-id="31bbf-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="31bbf-117">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="31bbf-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="31bbf-118">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="31bbf-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="31bbf-119">**请求标题**-无其他标题。</span><span class="sxs-lookup"><span data-stu-id="31bbf-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="31bbf-120">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="31bbf-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="31bbf-121">**响应**-响应包括 HTTP 状态代码和一组响应标头。</span><span class="sxs-lookup"><span data-stu-id="31bbf-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="31bbf-122">**状态代码**-成功的操作返回状态代码200（OK）。</span><span class="sxs-lookup"><span data-stu-id="31bbf-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="31bbf-123">如果找不到指定的项目 ID，则会返回状态代码404（未找到）。</span><span class="sxs-lookup"><span data-stu-id="31bbf-123">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="31bbf-124">**响应标题**-无其他标题。</span><span class="sxs-lookup"><span data-stu-id="31bbf-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="31bbf-125">**响应正文**-下面是 JSON 中的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="31bbf-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 <span data-ttu-id="31bbf-126">*itemId* -项目的 ID。</span><span class="sxs-lookup"><span data-stu-id="31bbf-126">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="31bbf-127">*userId* -拥有此项目的用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="31bbf-127">*userId*  - ID of the user who owns this item.</span></span>
  
 <span data-ttu-id="31bbf-128">*内容*-特定于应用程序的内容。</span><span class="sxs-lookup"><span data-stu-id="31bbf-128">*content*  - The application-specific content.</span></span>
  
 <span data-ttu-id="31bbf-129">*type* -内容的类型。</span><span class="sxs-lookup"><span data-stu-id="31bbf-129">*type*  - The type of the content.</span></span> <span data-ttu-id="31bbf-130">此字段由应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="31bbf-130">This field is set by the applications.</span></span>
  
 <span data-ttu-id="31bbf-131">*subItemIds* -子项目的 id （如果有）。</span><span class="sxs-lookup"><span data-stu-id="31bbf-131">*subItemIds*  - The IDs of sub-Items, if any.</span></span> <span data-ttu-id="31bbf-132">这是一个用于保存调用的 "获取子项目" 操作的简短电路。</span><span class="sxs-lookup"><span data-stu-id="31bbf-132">This is a short-circuit of Get Sub-Items operation to save a call.</span></span> <span data-ttu-id="31bbf-133">应用程序也可以使用 "获取子项目" 操作获取相同的信息。</span><span class="sxs-lookup"><span data-stu-id="31bbf-133">Applications can alternatively obtain the same information using Get Sub-Items operation.</span></span>
  

