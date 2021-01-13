---
title: 获取子项
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
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 摘要：了解作为项目Sub-Items一部分的 Get Sub-Items 操作。 项目服务是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是 Skype for Business Server 的工具。
ms.openlocfilehash: defb0b898c5101513cbb4f6da4382a8bb43bce6e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832502"
---
# <a name="get-sub-items"></a><span data-ttu-id="c8437-105">获取子项</span><span class="sxs-lookup"><span data-stu-id="c8437-105">Get Sub-Items</span></span>
 
<span data-ttu-id="c8437-106">**摘要：** 了解作为项目Sub-Items一部分的 Get Sub-Items 操作。</span><span class="sxs-lookup"><span data-stu-id="c8437-106">**Summary:** Learn about the Get Sub-Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="c8437-107">项目服务是通话质量仪表板存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="c8437-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="c8437-108">通话质量仪表板是 Skype for Business Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="c8437-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="c8437-109">Get Sub-Items 操作是呼叫质量仪表板存储库 API 中的项目服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="c8437-109">The Get Sub-Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-sub-items"></a><span data-ttu-id="c8437-110">获取子项</span><span class="sxs-lookup"><span data-stu-id="c8437-110">Get Sub-Items</span></span>

<span data-ttu-id="c8437-111">获取Sub-Items返回特定项目的子项。</span><span class="sxs-lookup"><span data-stu-id="c8437-111">Get Sub-Items returns a specific Item's sub-items.</span></span>
  

|<span data-ttu-id="c8437-112">**方法**</span><span class="sxs-lookup"><span data-stu-id="c8437-112">**Method**</span></span>|<span data-ttu-id="c8437-113">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="c8437-113">**Request URI**</span></span>|<span data-ttu-id="c8437-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="c8437-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c8437-115">GET</span><span class="sxs-lookup"><span data-stu-id="c8437-115">GET</span></span>  <br/> |<span data-ttu-id="c8437-116">https:// \<portal\> /QoERepositoryService/repository/item/{itemId}/subitem</span><span class="sxs-lookup"><span data-stu-id="c8437-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem</span></span>  <br/> |<span data-ttu-id="c8437-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="c8437-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="c8437-118">**URI 参数** - 无。</span><span class="sxs-lookup"><span data-stu-id="c8437-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="c8437-119">**请求标头** - 无其他标头。</span><span class="sxs-lookup"><span data-stu-id="c8437-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="c8437-120">**请求正文** - 无。</span><span class="sxs-lookup"><span data-stu-id="c8437-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="c8437-121">**响应** - 响应包括 HTTP 状态代码和一组响应标头。</span><span class="sxs-lookup"><span data-stu-id="c8437-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="c8437-122">**状态代码** - 成功操作返回状态代码 200 (确定) 。</span><span class="sxs-lookup"><span data-stu-id="c8437-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="c8437-123">如果找不到指定的用户 ID，它将返回状态代码 404 (未找到) 。</span><span class="sxs-lookup"><span data-stu-id="c8437-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="c8437-124">**响应标头** - 无其他标头。</span><span class="sxs-lookup"><span data-stu-id="c8437-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="c8437-125">**响应正文** - 下面是 JSON 中的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="c8437-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c8437-126">返回 Item 对象的数组。</span><span class="sxs-lookup"><span data-stu-id="c8437-126">An array of Item object is returned.</span></span> 
  
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

<span data-ttu-id="c8437-127">由项目操作返回Sub-Items项对象仅包含以下三个字段。</span><span class="sxs-lookup"><span data-stu-id="c8437-127">The Item object returned by Sub-Items operation only contains the following three fields.</span></span> 
  
 <span data-ttu-id="c8437-128">*itemId*  - 项目的 ID。</span><span class="sxs-lookup"><span data-stu-id="c8437-128">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="c8437-129">*userId*  - 拥有此项目的用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="c8437-129">*userId*  - ID of the User who owns this Item.</span></span>
  
 <span data-ttu-id="c8437-130">*type*  - 内容的类型。</span><span class="sxs-lookup"><span data-stu-id="c8437-130">*type*  - The type of the content.</span></span> <span data-ttu-id="c8437-131">此字段由应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="c8437-131">This field is set by the applications.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="c8437-132">`Content``subItems`和字段不包括在响应中，以减少通过网络传输的数据量。</span><span class="sxs-lookup"><span data-stu-id="c8437-132">`Content` and `subItems` fields are not included in the response to reduce the amount of data transmitted over the network.</span></span>
  

