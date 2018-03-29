---
title: 获取项的祖先
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: 摘要： 了解如何获取项上级操作，这是项服务的一部分。 此项服务是呼叫质量仪表板存储库 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: ab5cc9dd388d1192922430e2a728bb8073b3e0d7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="get-item-ancestors"></a><span data-ttu-id="bfd44-105">获取项的祖先</span><span class="sxs-lookup"><span data-stu-id="bfd44-105">Get Item Ancestors</span></span>
 
<span data-ttu-id="bfd44-106">**摘要：**了解有关获取项上级操作，这是项服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="bfd44-106">**Summary:** Learn about the Get Item Ancestors operation, which is part of the Item Service.</span></span> <span data-ttu-id="bfd44-107">此项服务是呼叫质量仪表板存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="bfd44-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="bfd44-108">通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="bfd44-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="bfd44-109">获取项上级操作是项服务存储库 API 调用质量仪表板中的一部分。</span><span class="sxs-lookup"><span data-stu-id="bfd44-109">The Get Item Ancestors operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item-ancestors"></a><span data-ttu-id="bfd44-110">获取项的祖先</span><span class="sxs-lookup"><span data-stu-id="bfd44-110">Get Item Ancestors</span></span>

<span data-ttu-id="bfd44-111">从存储库中获取项上级返回特定项目祖先。</span><span class="sxs-lookup"><span data-stu-id="bfd44-111">Get Item Ancestors returns a specific items ancestors from the repository.</span></span>
  

|<span data-ttu-id="bfd44-112">**方法**</span><span class="sxs-lookup"><span data-stu-id="bfd44-112">**Method**</span></span>|<span data-ttu-id="bfd44-113">**请求的 URI**</span><span class="sxs-lookup"><span data-stu-id="bfd44-113">**Request URI**</span></span>|<span data-ttu-id="bfd44-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="bfd44-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bfd44-115">获取</span><span class="sxs-lookup"><span data-stu-id="bfd44-115">GET</span></span>  <br/> |<span data-ttu-id="bfd44-116">https://\<门户网站\>/QoERepositoryService/存储库/itemAncestors / {itemId}</span><span class="sxs-lookup"><span data-stu-id="bfd44-116">https://\<portal\>/QoERepositoryService/repository/itemAncestors/{itemId}</span></span>  <br/> |<span data-ttu-id="bfd44-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="bfd44-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="bfd44-118">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="bfd44-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="bfd44-119">**请求标头**的任何其他标头。</span><span class="sxs-lookup"><span data-stu-id="bfd44-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="bfd44-120">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="bfd44-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="bfd44-121">**响应**-响应包括 HTTP 状态代码和一套响应标头。</span><span class="sxs-lookup"><span data-stu-id="bfd44-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="bfd44-122">**状态代码**-操作成功返回状态码 200 (OK)。</span><span class="sxs-lookup"><span data-stu-id="bfd44-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="bfd44-123">如果找不到 ID 指定的用户，它将返回状态代码 404 （未找到）。</span><span class="sxs-lookup"><span data-stu-id="bfd44-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="bfd44-124">**响应标头**的任何其他标头。</span><span class="sxs-lookup"><span data-stu-id="bfd44-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="bfd44-125">**响应正文**-下面是 json 格式的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="bfd44-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
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

 <span data-ttu-id="bfd44-126">*Item1*的项的 ID。</span><span class="sxs-lookup"><span data-stu-id="bfd44-126">*Item1*  - ID of the item.</span></span>
  
 <span data-ttu-id="bfd44-127">*Item2* -深度是从物料的距离。</span><span class="sxs-lookup"><span data-stu-id="bfd44-127">*Item2*  - Depth is the distance from the Item.</span></span> <span data-ttu-id="bfd44-128">0 是的直接父级。</span><span class="sxs-lookup"><span data-stu-id="bfd44-128">0 is the immediate parent.</span></span>
  
 <span data-ttu-id="bfd44-129">*Item3* -项目的标题。</span><span class="sxs-lookup"><span data-stu-id="bfd44-129">*Item3*  - Title of the item.</span></span>
  

