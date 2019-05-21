---
title: 更新项目
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: '摘要: 了解 "更新项目" 操作, 该操作是项目服务的一部分。 项目服务是适用于呼叫质量仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。'
ms.openlocfilehash: aa46be0babf5998fcf2fabea797cb7a769914f8e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274532"
---
# <a name="update-item"></a><span data-ttu-id="291ac-105">更新项目</span><span class="sxs-lookup"><span data-stu-id="291ac-105">Update Item</span></span>
 
<span data-ttu-id="291ac-106">**摘要:** 了解 "更新项目" 操作, 该操作是项目服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="291ac-106">**Summary:** Learn about the Update Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="291ac-107">项目服务是适用于呼叫质量仪表板的知识库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="291ac-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="291ac-108">通话质量仪表板是 Skype for business 服务器的工具。</span><span class="sxs-lookup"><span data-stu-id="291ac-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="291ac-109">"更新项目" 操作是 "知识库 API for 通话质量" 仪表板中的项目服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="291ac-109">The Update Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="update-item"></a><span data-ttu-id="291ac-110">更新项目</span><span class="sxs-lookup"><span data-stu-id="291ac-110">Update Item</span></span>

<span data-ttu-id="291ac-111">更新项目更新存储库中的特定项目。</span><span class="sxs-lookup"><span data-stu-id="291ac-111">Update Item updates a specific item in the repository.</span></span>
  

|<span data-ttu-id="291ac-112">**种**</span><span class="sxs-lookup"><span data-stu-id="291ac-112">**Method**</span></span>|<span data-ttu-id="291ac-113">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="291ac-113">**Request URI**</span></span>|<span data-ttu-id="291ac-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="291ac-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="291ac-115">带来</span><span class="sxs-lookup"><span data-stu-id="291ac-115">PUT</span></span>  <br/> |<span data-ttu-id="291ac-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span><span class="sxs-lookup"><span data-stu-id="291ac-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="291ac-117">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="291ac-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="291ac-118">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="291ac-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="291ac-119">**请求标头**-内容类型: application/json。</span><span class="sxs-lookup"><span data-stu-id="291ac-119">**Request Headers** -Content-Type: application/json.</span></span>
  
 <span data-ttu-id="291ac-120">**请求正文**-JSON。</span><span class="sxs-lookup"><span data-stu-id="291ac-120">**Request Body** - JSON.</span></span>
  
<span data-ttu-id="291ac-121">示例请求负载:</span><span class="sxs-lookup"><span data-stu-id="291ac-121">Sample request payload:</span></span>
  
```
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 <span data-ttu-id="291ac-122">*内容* 要存储为现有子项目的新内容的 JSON 格式的数据。</span><span class="sxs-lookup"><span data-stu-id="291ac-122">*content*  JSON formatted data to be stored as the new content of an existing sub-Item.</span></span> <span data-ttu-id="291ac-123">从技术上讲, 存储库可以存储任何架构的任何内容, 但在用于通话质量仪表板时, 它应该是报表或查询。</span><span class="sxs-lookup"><span data-stu-id="291ac-123">Technically, a repository can store any content of any schema, but when used for Call Quality Dashboard, it should be either a report or a query.</span></span> <span data-ttu-id="291ac-124">*键入* 始终为 "通话质量" 仪表板指定 "application/json"。</span><span class="sxs-lookup"><span data-stu-id="291ac-124">*type*  Always specify "application/json" for Call Quality Dashboard.</span></span>
  
 <span data-ttu-id="291ac-125">**响应**-响应包括 HTTP 状态代码和一组响应标头。</span><span class="sxs-lookup"><span data-stu-id="291ac-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="291ac-126">**状态代码**-成功的操作返回状态代码 204 (无内容)。</span><span class="sxs-lookup"><span data-stu-id="291ac-126">**Status Code** - A successful operation returns status code 204 (No Content).</span></span> <span data-ttu-id="291ac-127">如果找不到指定的项目 ID, 则会返回状态代码 404 (未找到)。</span><span class="sxs-lookup"><span data-stu-id="291ac-127">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="291ac-128">"无内容" 不是错误状态。</span><span class="sxs-lookup"><span data-stu-id="291ac-128">"No Content" is not an error status.</span></span> <span data-ttu-id="291ac-129">这意味着响应不会返回正文中的任何内容 (相反, 200 OK 返回正文中的内容)。</span><span class="sxs-lookup"><span data-stu-id="291ac-129">It means that a response did not return anything in the body (in contrast, 200 OK returns content in Body).</span></span> <span data-ttu-id="291ac-130">它表示项目已成功更新。</span><span class="sxs-lookup"><span data-stu-id="291ac-130">It indicates that the Item was successfully updated.</span></span> 
  
 <span data-ttu-id="291ac-131">**响应标题**-无。</span><span class="sxs-lookup"><span data-stu-id="291ac-131">**Response Headers** - None.</span></span>
  
 <span data-ttu-id="291ac-132">**响应正文**-无。</span><span class="sxs-lookup"><span data-stu-id="291ac-132">**Response Body** - None.</span></span>
  

