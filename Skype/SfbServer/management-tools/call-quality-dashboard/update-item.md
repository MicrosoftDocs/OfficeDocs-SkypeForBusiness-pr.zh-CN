---
title: 更新项目
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 6/8/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 摘要： 了解更新项目操作，这是项服务的一部分。 此项服务是呼叫质量仪表板存储库 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: 04a0ebf29537bbc2e62e6d5b35008fe9e329ab4f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="update-item"></a><span data-ttu-id="89835-105">更新项目</span><span class="sxs-lookup"><span data-stu-id="89835-105">Update Item</span></span>
 
<span data-ttu-id="89835-106">**摘要：**了解有关更新项目操作，这是项服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="89835-106">**Summary:** Learn about the Update Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="89835-107">此项服务是呼叫质量仪表板存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="89835-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="89835-108">通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="89835-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="89835-109">更新物料操作是项服务存储库 API 调用质量仪表板中的一部分。</span><span class="sxs-lookup"><span data-stu-id="89835-109">The Update Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="update-item"></a><span data-ttu-id="89835-110">更新项目</span><span class="sxs-lookup"><span data-stu-id="89835-110">Update Item</span></span>

<span data-ttu-id="89835-111">更新项目更新资源库中的特定项。</span><span class="sxs-lookup"><span data-stu-id="89835-111">Update Item updates a specific item in the repository.</span></span>
  

|<span data-ttu-id="89835-112">**方法**</span><span class="sxs-lookup"><span data-stu-id="89835-112">**Method**</span></span>|<span data-ttu-id="89835-113">**请求的 URI**</span><span class="sxs-lookup"><span data-stu-id="89835-113">**Request URI**</span></span>|<span data-ttu-id="89835-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="89835-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="89835-115">放入</span><span class="sxs-lookup"><span data-stu-id="89835-115">PUT</span></span>  <br/> |<span data-ttu-id="89835-116">https://\<门户网站\>/QoERepositoryService/存储库/项目 / {itemId}</span><span class="sxs-lookup"><span data-stu-id="89835-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="89835-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="89835-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="89835-118">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="89835-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="89835-119">**请求标头**的内容的类型： 应用程序/json。</span><span class="sxs-lookup"><span data-stu-id="89835-119">**Request Headers** -Content-Type: application/json.</span></span>
  
 <span data-ttu-id="89835-120">**请求正文**的 JSON。</span><span class="sxs-lookup"><span data-stu-id="89835-120">**Request Body** - JSON.</span></span>
  
<span data-ttu-id="89835-121">示例请求负载：</span><span class="sxs-lookup"><span data-stu-id="89835-121">Sample request payload:</span></span>
  
```
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 <span data-ttu-id="89835-122">*内容* JSON 格式的数据存储为现有的子项目的新内容。</span><span class="sxs-lookup"><span data-stu-id="89835-122">*content*  JSON formatted data to be stored as the new content of an existing sub-Item.</span></span> <span data-ttu-id="89835-123">从技术上讲，存储库可以存储任何内容的任何架构，但是使用呼叫质量仪表板，它应该是一个报表或查询。</span><span class="sxs-lookup"><span data-stu-id="89835-123">Technically, a repository can store any content of any schema, but when used for Call Quality Dashboard, it should be either a report or a query.</span></span> <span data-ttu-id="89835-124">*类型* 始终指定呼叫质量仪表板的"应用程序/json"。</span><span class="sxs-lookup"><span data-stu-id="89835-124">*type*  Always specify "application/json" for Call Quality Dashboard.</span></span>
  
 <span data-ttu-id="89835-125">**响应**-响应包括 HTTP 状态代码和一套响应标头。</span><span class="sxs-lookup"><span data-stu-id="89835-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="89835-126">**状态代码**-操作成功返回状态码 204 （无内容）。</span><span class="sxs-lookup"><span data-stu-id="89835-126">**Status Code** - A successful operation returns status code 204 (No Content).</span></span> <span data-ttu-id="89835-127">如果找不到指定的项 ID，它将返回状态代码 404 （未找到）。</span><span class="sxs-lookup"><span data-stu-id="89835-127">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="89835-128">"没有内容"不是一个错误状态。</span><span class="sxs-lookup"><span data-stu-id="89835-128">"No Content" is not an error status.</span></span> <span data-ttu-id="89835-129">这意味着，响应未返回任何内容 （相比之下，在正文中 200 OK 返回内容） 体内。</span><span class="sxs-lookup"><span data-stu-id="89835-129">It means that a response did not return anything in the body (in contrast, 200 OK returns content in Body).</span></span> <span data-ttu-id="89835-130">它表明该项目已成功更新。</span><span class="sxs-lookup"><span data-stu-id="89835-130">It indicates that the Item was successfully updated.</span></span> 
  
 <span data-ttu-id="89835-131">**响应标头**的无。</span><span class="sxs-lookup"><span data-stu-id="89835-131">**Response Headers** - None.</span></span>
  
 <span data-ttu-id="89835-132">**响应正文**-无。</span><span class="sxs-lookup"><span data-stu-id="89835-132">**Response Body** - None.</span></span>
  

