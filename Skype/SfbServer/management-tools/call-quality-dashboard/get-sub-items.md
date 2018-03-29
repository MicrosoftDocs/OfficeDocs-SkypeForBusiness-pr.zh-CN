---
title: 获取子项目
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 摘要： 了解如何获取子项操作，这是项服务的一部分。 此项服务是呼叫质量仪表板存储库 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: 8b9ec0c1c849e22f285ef1b5bbb2db806a153b76
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="get-sub-items"></a><span data-ttu-id="7ea00-105">获取子项目</span><span class="sxs-lookup"><span data-stu-id="7ea00-105">Get Sub-Items</span></span>
 
<span data-ttu-id="7ea00-106">**摘要：**了解有关获取子项操作，这是项服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="7ea00-106">**Summary:** Learn about the Get Sub-Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="7ea00-107">此项服务是呼叫质量仪表板存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="7ea00-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="7ea00-108">通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="7ea00-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="7ea00-109">获取子项操作是项服务存储库 API 调用质量仪表板中的一部分。</span><span class="sxs-lookup"><span data-stu-id="7ea00-109">The Get Sub-Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-sub-items"></a><span data-ttu-id="7ea00-110">获取子项目</span><span class="sxs-lookup"><span data-stu-id="7ea00-110">Get Sub-Items</span></span>

<span data-ttu-id="7ea00-111">获取子项目返回特定项的子项。</span><span class="sxs-lookup"><span data-stu-id="7ea00-111">Get Sub-Items returns a specific Item's sub-items.</span></span>
  

|<span data-ttu-id="7ea00-112">**方法**</span><span class="sxs-lookup"><span data-stu-id="7ea00-112">**Method**</span></span>|<span data-ttu-id="7ea00-113">**请求的 URI**</span><span class="sxs-lookup"><span data-stu-id="7ea00-113">**Request URI**</span></span>|<span data-ttu-id="7ea00-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="7ea00-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7ea00-115">获取</span><span class="sxs-lookup"><span data-stu-id="7ea00-115">GET</span></span>  <br/> |<span data-ttu-id="7ea00-116">https://\<门户网站\>/QoERepositoryService/存储库/项目 / {itemId} / subitem</span><span class="sxs-lookup"><span data-stu-id="7ea00-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem</span></span>  <br/> |<span data-ttu-id="7ea00-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="7ea00-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="7ea00-118">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="7ea00-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="7ea00-119">**请求标头**的任何其他标头。</span><span class="sxs-lookup"><span data-stu-id="7ea00-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="7ea00-120">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="7ea00-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="7ea00-121">**响应**-响应包括 HTTP 状态代码和一套响应标头。</span><span class="sxs-lookup"><span data-stu-id="7ea00-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="7ea00-122">**状态代码**-操作成功返回状态码 200 (OK)。</span><span class="sxs-lookup"><span data-stu-id="7ea00-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="7ea00-123">如果找不到 ID 指定的用户，它将返回状态代码 404 （未找到）。</span><span class="sxs-lookup"><span data-stu-id="7ea00-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="7ea00-124">**响应标头**的任何其他标头。</span><span class="sxs-lookup"><span data-stu-id="7ea00-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="7ea00-125">**响应正文**-下面是 json 格式的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="7ea00-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7ea00-126">项目对象的数组返回。</span><span class="sxs-lookup"><span data-stu-id="7ea00-126">An array of Item object is returned.</span></span> 
  
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

<span data-ttu-id="7ea00-127">项目对象的子项操作返回只包含以下三个字段。</span><span class="sxs-lookup"><span data-stu-id="7ea00-127">The Item object returned by Sub-Items operation only contains the following three fields.</span></span> 
  
 <span data-ttu-id="7ea00-128">*itemId*的项的 ID。</span><span class="sxs-lookup"><span data-stu-id="7ea00-128">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="7ea00-129">*用户 Id* -负责此项目的用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="7ea00-129">*userId*  - ID of the User who owns this Item.</span></span>
  
 <span data-ttu-id="7ea00-130">*类型*-类型的内容。</span><span class="sxs-lookup"><span data-stu-id="7ea00-130">*type*  - The type of the content.</span></span> <span data-ttu-id="7ea00-131">由应用程序设置此字段。</span><span class="sxs-lookup"><span data-stu-id="7ea00-131">This field is set by the applications.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="7ea00-132">`Content`和`subItems`的字段不包含在响应以减少通过网络传输的数据量。</span><span class="sxs-lookup"><span data-stu-id="7ea00-132">`Content` and `subItems` fields are not included in the response to reduce the amount of data transmitted over the network.</span></span>
  

