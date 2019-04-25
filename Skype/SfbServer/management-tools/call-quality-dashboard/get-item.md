---
title: 获取项目
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 摘要： 了解如何获取项操作，即项服务的一部分。 项服务是呼叫质量仪表板的存储库 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
ms.openlocfilehash: 1f86c318139d328f414bf1290c66ddd7ccb7e20a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222693"
---
# <a name="get-item"></a><span data-ttu-id="e8961-105">获取项目</span><span class="sxs-lookup"><span data-stu-id="e8961-105">Get Item</span></span>
 
<span data-ttu-id="e8961-106">**摘要：** 了解获取项目操作，即项服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="e8961-106">**Summary:** Learn about the Get Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="e8961-107">项服务是呼叫质量仪表板的存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="e8961-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="e8961-108">呼叫质量仪表板是用于业务服务器 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="e8961-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="e8961-109">获取项操作是用于呼叫的质量仪表板的存储库 API 中的项服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="e8961-109">The Get Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item"></a><span data-ttu-id="e8961-110">获取项目</span><span class="sxs-lookup"><span data-stu-id="e8961-110">Get Item</span></span>

<span data-ttu-id="e8961-111">在存储库中获取项目返回的特定项目。</span><span class="sxs-lookup"><span data-stu-id="e8961-111">Get Item returns a specific item in the repository.</span></span>
  
|<span data-ttu-id="e8961-112">**方法**</span><span class="sxs-lookup"><span data-stu-id="e8961-112">**Method**</span></span>|<span data-ttu-id="e8961-113">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="e8961-113">**Request URI**</span></span>|<span data-ttu-id="e8961-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="e8961-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e8961-115">获取</span><span class="sxs-lookup"><span data-stu-id="e8961-115">GET</span></span>  <br/> |<span data-ttu-id="e8961-116">https://\<门户\>/QoERepositoryService/存储库/项目 / {itemId}</span><span class="sxs-lookup"><span data-stu-id="e8961-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="e8961-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="e8961-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="e8961-118">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="e8961-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="e8961-119">**请求标头**的任何其他的标头。</span><span class="sxs-lookup"><span data-stu-id="e8961-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="e8961-120">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="e8961-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="e8961-121">**响应**-响应包括 HTTP 状态代码和一响应标头。</span><span class="sxs-lookup"><span data-stu-id="e8961-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="e8961-122">**状态代码**-成功的操作返回状态代码 200 （确定)。</span><span class="sxs-lookup"><span data-stu-id="e8961-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="e8961-123">如果找不到指定的项 ID，则返回状态代码的 404 （未找到）。</span><span class="sxs-lookup"><span data-stu-id="e8961-123">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="e8961-124">**响应标头**的任何其他的标头。</span><span class="sxs-lookup"><span data-stu-id="e8961-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="e8961-125">**响应正文**-下面是以 json 格式的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="e8961-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 <span data-ttu-id="e8961-126">*itemId* -项目的 ID。</span><span class="sxs-lookup"><span data-stu-id="e8961-126">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="e8961-127">*userId* -拥有此项的用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="e8961-127">*userId*  - ID of the user who owns this item.</span></span>
  
 <span data-ttu-id="e8961-128">*内容*-特定于应用程序的内容。</span><span class="sxs-lookup"><span data-stu-id="e8961-128">*content*  - The application-specific content.</span></span>
  
 <span data-ttu-id="e8961-129">*键入*的内容类型。</span><span class="sxs-lookup"><span data-stu-id="e8961-129">*type*  - The type of the content.</span></span> <span data-ttu-id="e8961-130">此字段设置应用程序。</span><span class="sxs-lookup"><span data-stu-id="e8961-130">This field is set by the applications.</span></span>
  
 <span data-ttu-id="e8961-131">*subItemIds* -的子项，如果有的 Id。</span><span class="sxs-lookup"><span data-stu-id="e8961-131">*subItemIds*  - The IDs of sub-Items, if any.</span></span> <span data-ttu-id="e8961-132">这是获取子项操作，以保存呼叫短路。</span><span class="sxs-lookup"><span data-stu-id="e8961-132">This is a short-circuit of Get Sub-Items operation to save a call.</span></span> <span data-ttu-id="e8961-133">应用程序或者可以获取相同的信息。 使用获取子项操作。</span><span class="sxs-lookup"><span data-stu-id="e8961-133">Applications can alternatively obtain the same information using Get Sub-Items operation.</span></span>
  

