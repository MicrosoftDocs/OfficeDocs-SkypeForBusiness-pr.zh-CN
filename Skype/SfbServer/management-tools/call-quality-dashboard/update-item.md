---
title: 更新项目
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
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 摘要：了解作为项目服务的一部分的"更新项"操作。 项目服务是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是 Skype for Business Server 的工具。
ms.openlocfilehash: 78da2fa414b4ba266f9e6aba4feac5ff73150062
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803082"
---
# <a name="update-item"></a><span data-ttu-id="51967-105">更新项目</span><span class="sxs-lookup"><span data-stu-id="51967-105">Update Item</span></span>
 
<span data-ttu-id="51967-106">**摘要：** 了解更新项操作，这是项服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="51967-106">**Summary:** Learn about the Update Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="51967-107">项目服务是通话质量仪表板存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="51967-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="51967-108">通话质量仪表板是 Skype for Business Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="51967-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="51967-109">更新项操作是呼叫质量仪表板存储库 API 中的项目服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="51967-109">The Update Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="update-item"></a><span data-ttu-id="51967-110">更新项目</span><span class="sxs-lookup"><span data-stu-id="51967-110">Update Item</span></span>

<span data-ttu-id="51967-111">更新项更新存储库中的特定项。</span><span class="sxs-lookup"><span data-stu-id="51967-111">Update Item updates a specific item in the repository.</span></span>
  

|<span data-ttu-id="51967-112">**方法**</span><span class="sxs-lookup"><span data-stu-id="51967-112">**Method**</span></span>|<span data-ttu-id="51967-113">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="51967-113">**Request URI**</span></span>|<span data-ttu-id="51967-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="51967-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="51967-115">PUT</span><span class="sxs-lookup"><span data-stu-id="51967-115">PUT</span></span>  <br/> |<span data-ttu-id="51967-116">https:// \<portal\> /QoERepositoryService/repository/item/{itemId}</span><span class="sxs-lookup"><span data-stu-id="51967-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="51967-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="51967-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="51967-118">**URI 参数** - 无。</span><span class="sxs-lookup"><span data-stu-id="51967-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="51967-119">**请求标头** -Content-Type：application/json。</span><span class="sxs-lookup"><span data-stu-id="51967-119">**Request Headers** -Content-Type: application/json.</span></span>
  
 <span data-ttu-id="51967-120">**请求正文** - JSON。</span><span class="sxs-lookup"><span data-stu-id="51967-120">**Request Body** - JSON.</span></span>
  
<span data-ttu-id="51967-121">示例请求有效负载：</span><span class="sxs-lookup"><span data-stu-id="51967-121">Sample request payload:</span></span>
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 <span data-ttu-id="51967-122">*content*  要存储为现有子项的新内容的 JSON 格式数据。</span><span class="sxs-lookup"><span data-stu-id="51967-122">*content*  JSON formatted data to be stored as the new content of an existing sub-Item.</span></span> <span data-ttu-id="51967-123">从技术上说，存储库可以存储任何架构的任何内容，但在用于呼叫质量仪表板时，它应为报表或查询。</span><span class="sxs-lookup"><span data-stu-id="51967-123">Technically, a repository can store any content of any schema, but when used for Call Quality Dashboard, it should be either a report or a query.</span></span> <span data-ttu-id="51967-124">*type*  始终为呼叫质量仪表板指定"application/json"。</span><span class="sxs-lookup"><span data-stu-id="51967-124">*type*  Always specify "application/json" for Call Quality Dashboard.</span></span>
  
 <span data-ttu-id="51967-125">**响应** - 响应包括 HTTP 状态代码和一组响应标头。</span><span class="sxs-lookup"><span data-stu-id="51967-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="51967-126">**状态代码** - 成功操作返回状态代码 204 (内容) 。</span><span class="sxs-lookup"><span data-stu-id="51967-126">**Status Code** - A successful operation returns status code 204 (No Content).</span></span> <span data-ttu-id="51967-127">如果找不到指定的项目 ID，则返回状态代码 404 (未找到) 。</span><span class="sxs-lookup"><span data-stu-id="51967-127">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="51967-128">"无内容"不是错误状态。</span><span class="sxs-lookup"><span data-stu-id="51967-128">"No Content" is not an error status.</span></span> <span data-ttu-id="51967-129">这意味着响应没有在正文中返回任何内容，相反 (200 OK 返回 Body) 。</span><span class="sxs-lookup"><span data-stu-id="51967-129">It means that a response did not return anything in the body (in contrast, 200 OK returns content in Body).</span></span> <span data-ttu-id="51967-130">它指示项目已成功更新。</span><span class="sxs-lookup"><span data-stu-id="51967-130">It indicates that the Item was successfully updated.</span></span> 
  
 <span data-ttu-id="51967-131">**响应标头** - 无。</span><span class="sxs-lookup"><span data-stu-id="51967-131">**Response Headers** - None.</span></span>
  
 <span data-ttu-id="51967-132">**响应正文** - 无。</span><span class="sxs-lookup"><span data-stu-id="51967-132">**Response Body** - None.</span></span>
  

