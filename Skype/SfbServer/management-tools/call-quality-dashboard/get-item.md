---
title: 获取项目
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
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 摘要：了解作为项目服务的一部分的 Get Item 操作。 项目服务是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是 Skype for Business Server 的工具。
ms.openlocfilehash: 896540c4572fb3991356ce055f01690ed702c6f2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832562"
---
# <a name="get-item"></a><span data-ttu-id="af6d1-105">获取项目</span><span class="sxs-lookup"><span data-stu-id="af6d1-105">Get Item</span></span>
 
<span data-ttu-id="af6d1-106">**摘要：** 了解作为项目服务的一部分的 Get Item 操作。</span><span class="sxs-lookup"><span data-stu-id="af6d1-106">**Summary:** Learn about the Get Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="af6d1-107">项目服务是通话质量仪表板存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="af6d1-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="af6d1-108">通话质量仪表板是 Skype for Business Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="af6d1-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="af6d1-109">Get Item 操作是呼叫质量仪表板的存储库 API 中的项目服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="af6d1-109">The Get Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item"></a><span data-ttu-id="af6d1-110">获取项目</span><span class="sxs-lookup"><span data-stu-id="af6d1-110">Get Item</span></span>

<span data-ttu-id="af6d1-111">Get Item 返回存储库中的特定项。</span><span class="sxs-lookup"><span data-stu-id="af6d1-111">Get Item returns a specific item in the repository.</span></span>
  
|<span data-ttu-id="af6d1-112">**方法**</span><span class="sxs-lookup"><span data-stu-id="af6d1-112">**Method**</span></span>|<span data-ttu-id="af6d1-113">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="af6d1-113">**Request URI**</span></span>|<span data-ttu-id="af6d1-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="af6d1-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="af6d1-115">GET</span><span class="sxs-lookup"><span data-stu-id="af6d1-115">GET</span></span>  <br/> |<span data-ttu-id="af6d1-116">https:// \<portal\> /QoERepositoryService/repository/item/{itemId}</span><span class="sxs-lookup"><span data-stu-id="af6d1-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="af6d1-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="af6d1-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="af6d1-118">**URI 参数** - 无。</span><span class="sxs-lookup"><span data-stu-id="af6d1-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="af6d1-119">**请求标头** - 无其他标头。</span><span class="sxs-lookup"><span data-stu-id="af6d1-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="af6d1-120">**请求正文** - 无。</span><span class="sxs-lookup"><span data-stu-id="af6d1-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="af6d1-121">**响应** - 响应包括 HTTP 状态代码和一组响应标头。</span><span class="sxs-lookup"><span data-stu-id="af6d1-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="af6d1-122">**状态代码** - 成功操作返回状态代码 200 (确定) 。</span><span class="sxs-lookup"><span data-stu-id="af6d1-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="af6d1-123">如果找不到指定的项目 ID，则返回状态代码 404 (未找到) 。</span><span class="sxs-lookup"><span data-stu-id="af6d1-123">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="af6d1-124">**响应标头** - 无其他标头。</span><span class="sxs-lookup"><span data-stu-id="af6d1-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="af6d1-125">**响应正文** - 下面是 JSON 中的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="af6d1-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 <span data-ttu-id="af6d1-126">*itemId*  - 项目的 ID。</span><span class="sxs-lookup"><span data-stu-id="af6d1-126">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="af6d1-127">*userId*  - 拥有此项目的用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="af6d1-127">*userId*  - ID of the user who owns this item.</span></span>
  
 <span data-ttu-id="af6d1-128">*content*  - 特定于应用程序的内容。</span><span class="sxs-lookup"><span data-stu-id="af6d1-128">*content*  - The application-specific content.</span></span>
  
 <span data-ttu-id="af6d1-129">*type*  - 内容的类型。</span><span class="sxs-lookup"><span data-stu-id="af6d1-129">*type*  - The type of the content.</span></span> <span data-ttu-id="af6d1-130">此字段由应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="af6d1-130">This field is set by the applications.</span></span>
  
 <span data-ttu-id="af6d1-131">*subItemIds*  - 子项的 ID（如果有）。</span><span class="sxs-lookup"><span data-stu-id="af6d1-131">*subItemIds*  - The IDs of sub-Items, if any.</span></span> <span data-ttu-id="af6d1-132">这是 Get Sub-Items 操作以保存呼叫的短电路。</span><span class="sxs-lookup"><span data-stu-id="af6d1-132">This is a short-circuit of Get Sub-Items operation to save a call.</span></span> <span data-ttu-id="af6d1-133">此外，应用程序可以使用 Get Sub-Items获取相同的信息。</span><span class="sxs-lookup"><span data-stu-id="af6d1-133">Applications can alternatively obtain the same information using Get Sub-Items operation.</span></span>
  

