---
title: 获取子项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 摘要：了解 "获取子项目" 操作，该操作是项目服务的一部分。 项目服务是适用于呼叫质量仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。
ms.openlocfilehash: 75fc4fcd331925c224d8dfb72c681d25e3485eb6
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992649"
---
# <a name="get-sub-items"></a><span data-ttu-id="f4504-105">获取子项</span><span class="sxs-lookup"><span data-stu-id="f4504-105">Get Sub-Items</span></span>
 
<span data-ttu-id="f4504-106">**摘要：** 了解 "获取子项目" 操作，该操作是项目服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="f4504-106">**Summary:** Learn about the Get Sub-Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="f4504-107">项目服务是适用于呼叫质量仪表板的知识库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="f4504-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="f4504-108">通话质量仪表板是 Skype for business 服务器的工具。</span><span class="sxs-lookup"><span data-stu-id="f4504-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="f4504-109">"获取子项目" 操作是 "知识库 API for 通话质量" 仪表板中的项目服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="f4504-109">The Get Sub-Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-sub-items"></a><span data-ttu-id="f4504-110">获取子项</span><span class="sxs-lookup"><span data-stu-id="f4504-110">Get Sub-Items</span></span>

<span data-ttu-id="f4504-111">获取子项目返回特定项目的子项目。</span><span class="sxs-lookup"><span data-stu-id="f4504-111">Get Sub-Items returns a specific Item's sub-items.</span></span>
  

|<span data-ttu-id="f4504-112">**种**</span><span class="sxs-lookup"><span data-stu-id="f4504-112">**Method**</span></span>|<span data-ttu-id="f4504-113">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="f4504-113">**Request URI**</span></span>|<span data-ttu-id="f4504-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="f4504-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f4504-115">获取</span><span class="sxs-lookup"><span data-stu-id="f4504-115">GET</span></span>  <br/> |<span data-ttu-id="f4504-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem</span><span class="sxs-lookup"><span data-stu-id="f4504-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem</span></span>  <br/> |<span data-ttu-id="f4504-117">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="f4504-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="f4504-118">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="f4504-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="f4504-119">**请求标题**-无其他标题。</span><span class="sxs-lookup"><span data-stu-id="f4504-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="f4504-120">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="f4504-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="f4504-121">**响应**-响应包括 HTTP 状态代码和一组响应标头。</span><span class="sxs-lookup"><span data-stu-id="f4504-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="f4504-122">**状态代码**-成功的操作返回状态代码200（OK）。</span><span class="sxs-lookup"><span data-stu-id="f4504-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="f4504-123">如果找不到指定的用户 ID，将返回状态代码404（未找到）。</span><span class="sxs-lookup"><span data-stu-id="f4504-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="f4504-124">**响应标题**-无其他标题。</span><span class="sxs-lookup"><span data-stu-id="f4504-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="f4504-125">**响应正文**-下面是 JSON 中的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="f4504-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f4504-126">返回 Item 对象的数组。</span><span class="sxs-lookup"><span data-stu-id="f4504-126">An array of Item object is returned.</span></span> 
  
```json
[{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1710,
"userId": 0,
"type": "json"
}]
```

<span data-ttu-id="f4504-127">子项目操作返回的 Item 对象仅包含以下三个字段。</span><span class="sxs-lookup"><span data-stu-id="f4504-127">The Item object returned by Sub-Items operation only contains the following three fields.</span></span> 
  
 <span data-ttu-id="f4504-128">*itemId* -项目的 ID。</span><span class="sxs-lookup"><span data-stu-id="f4504-128">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="f4504-129">*userId* -拥有此项目的用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="f4504-129">*userId*  - ID of the User who owns this Item.</span></span>
  
 <span data-ttu-id="f4504-130">*type* -内容的类型。</span><span class="sxs-lookup"><span data-stu-id="f4504-130">*type*  - The type of the content.</span></span> <span data-ttu-id="f4504-131">此字段由应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="f4504-131">This field is set by the applications.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="f4504-132">`Content`和`subItems`字段不包含在响应中，以减少通过网络传输的数据量。</span><span class="sxs-lookup"><span data-stu-id="f4504-132">`Content` and `subItems` fields are not included in the response to reduce the amount of data transmitted over the network.</span></span>
  

