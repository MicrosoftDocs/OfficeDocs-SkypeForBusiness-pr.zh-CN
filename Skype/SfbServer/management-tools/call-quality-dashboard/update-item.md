---
title: 更新项
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 6/8/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 摘要： 了解如何更新项操作，即项服务的一部分。 项服务是呼叫质量仪表板的存储库 API 的一部分。 呼叫质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: 0616f41a3ae680412bdc435716d805af77e72f3a
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295264"
---
# <a name="update-item"></a><span data-ttu-id="a1505-105">更新项</span><span class="sxs-lookup"><span data-stu-id="a1505-105">Update Item</span></span>
 
<span data-ttu-id="a1505-106">**摘要：** 了解有关更新项操作，即项服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="a1505-106">**Summary:** Learn about the Update Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="a1505-107">项服务是呼叫质量仪表板的存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="a1505-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="a1505-108">呼叫质量仪表板是用于业务服务器 2015年的 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="a1505-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="a1505-109">更新项操作是用于呼叫的质量仪表板的存储库 API 中的项服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="a1505-109">The Update Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="update-item"></a><span data-ttu-id="a1505-110">更新项</span><span class="sxs-lookup"><span data-stu-id="a1505-110">Update Item</span></span>

<span data-ttu-id="a1505-111">更新项更新存储库中的特定项目。</span><span class="sxs-lookup"><span data-stu-id="a1505-111">Update Item updates a specific item in the repository.</span></span>
  

|<span data-ttu-id="a1505-112">**方法**</span><span class="sxs-lookup"><span data-stu-id="a1505-112">**Method**</span></span>|<span data-ttu-id="a1505-113">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="a1505-113">**Request URI**</span></span>|<span data-ttu-id="a1505-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="a1505-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a1505-115">PUT</span><span class="sxs-lookup"><span data-stu-id="a1505-115">PUT</span></span>  <br/> |<span data-ttu-id="a1505-116">https://\<门户\>/QoERepositoryService/存储库/项目 / {itemId}</span><span class="sxs-lookup"><span data-stu-id="a1505-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="a1505-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="a1505-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="a1505-118">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="a1505-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="a1505-119">**请求标头**的内容的类型： application/json。</span><span class="sxs-lookup"><span data-stu-id="a1505-119">**Request Headers** -Content-Type: application/json.</span></span>
  
 <span data-ttu-id="a1505-120">**请求正文**的 JSON。</span><span class="sxs-lookup"><span data-stu-id="a1505-120">**Request Body** - JSON.</span></span>
  
<span data-ttu-id="a1505-121">示例请求负载：</span><span class="sxs-lookup"><span data-stu-id="a1505-121">Sample request payload:</span></span>
  
```
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 <span data-ttu-id="a1505-122">*内容* JSON 格式作为现有子项目的新内容存储的数据。</span><span class="sxs-lookup"><span data-stu-id="a1505-122">*content*  JSON formatted data to be stored as the new content of an existing sub-Item.</span></span> <span data-ttu-id="a1505-123">技术上讲，存储库可以存储的任何架构，任何内容，但当用于呼叫的质量仪表板，它应为报表或查询。</span><span class="sxs-lookup"><span data-stu-id="a1505-123">Technically, a repository can store any content of any schema, but when used for Call Quality Dashboard, it should be either a report or a query.</span></span> <span data-ttu-id="a1505-124">*类型* 始终为呼叫质量仪表板中指定"application/json"。</span><span class="sxs-lookup"><span data-stu-id="a1505-124">*type*  Always specify "application/json" for Call Quality Dashboard.</span></span>
  
 <span data-ttu-id="a1505-125">**响应**-响应包括 HTTP 状态代码和一响应标头。</span><span class="sxs-lookup"><span data-stu-id="a1505-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="a1505-126">**状态代码**-成功的操作返回状态代码 204 （无内容）。</span><span class="sxs-lookup"><span data-stu-id="a1505-126">**Status Code** - A successful operation returns status code 204 (No Content).</span></span> <span data-ttu-id="a1505-127">如果找不到指定的项 ID，则返回状态代码的 404 （未找到）。</span><span class="sxs-lookup"><span data-stu-id="a1505-127">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a1505-128">"没有 Content"不是错误状态。</span><span class="sxs-lookup"><span data-stu-id="a1505-128">"No Content" is not an error status.</span></span> <span data-ttu-id="a1505-129">它表示的响应未返回任何内容 （相比之下，200 确定返回内容正文中） 在正文中。</span><span class="sxs-lookup"><span data-stu-id="a1505-129">It means that a response did not return anything in the body (in contrast, 200 OK returns content in Body).</span></span> <span data-ttu-id="a1505-130">表示该项目已成功更新。</span><span class="sxs-lookup"><span data-stu-id="a1505-130">It indicates that the Item was successfully updated.</span></span> 
  
 <span data-ttu-id="a1505-131">**响应头**-无。</span><span class="sxs-lookup"><span data-stu-id="a1505-131">**Response Headers** - None.</span></span>
  
 <span data-ttu-id="a1505-132">**响应正文**-无。</span><span class="sxs-lookup"><span data-stu-id="a1505-132">**Response Body** - None.</span></span>
  

