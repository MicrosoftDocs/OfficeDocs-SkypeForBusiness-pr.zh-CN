---
title: 获取项
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 摘要： 了解如何获取项操作，这是项服务的一部分。 此项服务是呼叫质量仪表板存储库 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: 6e4ba82c804937025b72da2d443c2a828d92d98a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="get-item"></a><span data-ttu-id="ea80c-105">获取项</span><span class="sxs-lookup"><span data-stu-id="ea80c-105">Get Item</span></span>
 
<span data-ttu-id="ea80c-106">**摘要：**了解有关获取项操作，这是项服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="ea80c-106">**Summary:** Learn about the Get Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="ea80c-107">此项服务是呼叫质量仪表板存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="ea80c-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="ea80c-108">通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="ea80c-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ea80c-109">获取项操作是项服务存储库 API 调用质量仪表板中的一部分。</span><span class="sxs-lookup"><span data-stu-id="ea80c-109">The Get Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item"></a><span data-ttu-id="ea80c-110">获取项</span><span class="sxs-lookup"><span data-stu-id="ea80c-110">Get Item</span></span>

<span data-ttu-id="ea80c-111">存储库中获取项返回的特定项。</span><span class="sxs-lookup"><span data-stu-id="ea80c-111">Get Item returns a specific item in the repository.</span></span>
  
|<span data-ttu-id="ea80c-112">**方法**</span><span class="sxs-lookup"><span data-stu-id="ea80c-112">**Method**</span></span>|<span data-ttu-id="ea80c-113">**请求的 URI**</span><span class="sxs-lookup"><span data-stu-id="ea80c-113">**Request URI**</span></span>|<span data-ttu-id="ea80c-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="ea80c-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ea80c-115">获取</span><span class="sxs-lookup"><span data-stu-id="ea80c-115">GET</span></span>  <br/> |<span data-ttu-id="ea80c-116">https://\<门户网站\>/QoERepositoryService/存储库/项目 / {itemId}</span><span class="sxs-lookup"><span data-stu-id="ea80c-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="ea80c-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="ea80c-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="ea80c-118">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="ea80c-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="ea80c-119">**请求标头**的任何其他标头。</span><span class="sxs-lookup"><span data-stu-id="ea80c-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="ea80c-120">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="ea80c-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="ea80c-121">**响应**-响应包括 HTTP 状态代码和一套响应标头。</span><span class="sxs-lookup"><span data-stu-id="ea80c-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="ea80c-122">**状态代码**-操作成功返回状态码 200 (OK)。</span><span class="sxs-lookup"><span data-stu-id="ea80c-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="ea80c-123">如果找不到指定的项 ID，它将返回状态代码 404 （未找到）。</span><span class="sxs-lookup"><span data-stu-id="ea80c-123">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="ea80c-124">**响应标头**的任何其他标头。</span><span class="sxs-lookup"><span data-stu-id="ea80c-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="ea80c-125">**响应正文**-下面是 json 格式的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="ea80c-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}

```

 <span data-ttu-id="ea80c-126">*itemId*的项的 ID。</span><span class="sxs-lookup"><span data-stu-id="ea80c-126">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="ea80c-127">*用户 Id* -负责此项目的用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="ea80c-127">*userId*  - ID of the user who owns this item.</span></span>
  
 <span data-ttu-id="ea80c-128">*内容*的应用程序特定的内容。</span><span class="sxs-lookup"><span data-stu-id="ea80c-128">*content*  - The application-specific content.</span></span>
  
 <span data-ttu-id="ea80c-129">*类型*-类型的内容。</span><span class="sxs-lookup"><span data-stu-id="ea80c-129">*type*  - The type of the content.</span></span> <span data-ttu-id="ea80c-130">由应用程序设置此字段。</span><span class="sxs-lookup"><span data-stu-id="ea80c-130">This field is set by the applications.</span></span>
  
 <span data-ttu-id="ea80c-131">*subItemIds* -Id 的子项目，如果有的话。</span><span class="sxs-lookup"><span data-stu-id="ea80c-131">*subItemIds*  - The IDs of sub-Items, if any.</span></span> <span data-ttu-id="ea80c-132">这是获取子项操作来保存调用短路。</span><span class="sxs-lookup"><span data-stu-id="ea80c-132">This is a short-circuit of Get Sub-Items operation to save a call.</span></span> <span data-ttu-id="ea80c-133">应用程序也可以获得相同的信息使用获取子项操作。</span><span class="sxs-lookup"><span data-stu-id="ea80c-133">Applications can alternatively obtain the same information using Get Sub-Items operation.</span></span>
  

