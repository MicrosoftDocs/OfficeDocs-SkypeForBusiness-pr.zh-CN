---
title: 获取子项
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 摘要： 了解如何获取子项操作，即项服务的一部分。 项服务是呼叫质量仪表板的存储库 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
ms.openlocfilehash: 41287978338bce49d8d8c30d1d6b91b9b2498acc
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889005"
---
# <a name="get-sub-items"></a><span data-ttu-id="7b794-105">获取子项</span><span class="sxs-lookup"><span data-stu-id="7b794-105">Get Sub-Items</span></span>
 
<span data-ttu-id="7b794-106">**摘要：** 了解有关获取子项操作，即项服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="7b794-106">**Summary:** Learn about the Get Sub-Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="7b794-107">项服务是呼叫质量仪表板的存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="7b794-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="7b794-108">呼叫质量仪表板是用于业务服务器 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="7b794-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="7b794-109">获取子项操作是用于呼叫的质量仪表板的存储库 API 中的项服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="7b794-109">The Get Sub-Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-sub-items"></a><span data-ttu-id="7b794-110">获取子项</span><span class="sxs-lookup"><span data-stu-id="7b794-110">Get Sub-Items</span></span>

<span data-ttu-id="7b794-111">获取子项目返回的特定项目的子项目。</span><span class="sxs-lookup"><span data-stu-id="7b794-111">Get Sub-Items returns a specific Item's sub-items.</span></span>
  

|<span data-ttu-id="7b794-112">**方法**</span><span class="sxs-lookup"><span data-stu-id="7b794-112">**Method**</span></span>|<span data-ttu-id="7b794-113">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="7b794-113">**Request URI**</span></span>|<span data-ttu-id="7b794-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="7b794-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7b794-115">获取</span><span class="sxs-lookup"><span data-stu-id="7b794-115">GET</span></span>  <br/> |<span data-ttu-id="7b794-116">https://\<门户\>/QoERepositoryService/存储库/项目 / {itemId} / subitem</span><span class="sxs-lookup"><span data-stu-id="7b794-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem</span></span>  <br/> |<span data-ttu-id="7b794-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="7b794-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="7b794-118">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="7b794-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="7b794-119">**请求标头**的任何其他的标头。</span><span class="sxs-lookup"><span data-stu-id="7b794-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="7b794-120">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="7b794-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="7b794-121">**响应**-响应包括 HTTP 状态代码和一响应标头。</span><span class="sxs-lookup"><span data-stu-id="7b794-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="7b794-122">**状态代码**-成功的操作返回状态代码 200 （确定)。</span><span class="sxs-lookup"><span data-stu-id="7b794-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="7b794-123">如果找不到 ID 指定的用户，则将返回状态代码的 404 （未找到）。</span><span class="sxs-lookup"><span data-stu-id="7b794-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="7b794-124">**响应标头**的任何其他的标头。</span><span class="sxs-lookup"><span data-stu-id="7b794-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="7b794-125">**响应正文**-下面是以 json 格式的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="7b794-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7b794-126">返回项目对象的数组。</span><span class="sxs-lookup"><span data-stu-id="7b794-126">An array of Item object is returned.</span></span> 
  
```
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

<span data-ttu-id="7b794-127">子项目操作返回的项目对象仅包含以下三个字段。</span><span class="sxs-lookup"><span data-stu-id="7b794-127">The Item object returned by Sub-Items operation only contains the following three fields.</span></span> 
  
 <span data-ttu-id="7b794-128">*itemId* -项目的 ID。</span><span class="sxs-lookup"><span data-stu-id="7b794-128">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="7b794-129">*userId* -拥有此项的用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="7b794-129">*userId*  - ID of the User who owns this Item.</span></span>
  
 <span data-ttu-id="7b794-130">*键入*的内容类型。</span><span class="sxs-lookup"><span data-stu-id="7b794-130">*type*  - The type of the content.</span></span> <span data-ttu-id="7b794-131">此字段设置应用程序。</span><span class="sxs-lookup"><span data-stu-id="7b794-131">This field is set by the applications.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="7b794-132">`Content`和`subItems`中的响应以减少通过网络传输的数据量不包含字段。</span><span class="sxs-lookup"><span data-stu-id="7b794-132">`Content` and `subItems` fields are not included in the response to reduce the amount of data transmitted over the network.</span></span>
  

