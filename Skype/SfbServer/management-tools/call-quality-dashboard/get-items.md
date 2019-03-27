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
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: 摘要： 了解如何获取项操作，即项服务的一部分。 项服务是呼叫质量仪表板的存储库 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
ms.openlocfilehash: ad4be2c09de9d71499cd7592989334ccf4cf17c9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874981"
---
# <a name="get-items"></a><span data-ttu-id="62b1c-105">获取项目</span><span class="sxs-lookup"><span data-stu-id="62b1c-105">Get Items</span></span>
 
<span data-ttu-id="62b1c-106">**摘要：** 了解有关获取项操作，即项服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="62b1c-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="62b1c-107">项服务是呼叫质量仪表板的存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="62b1c-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="62b1c-108">呼叫质量仪表板是用于业务服务器 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="62b1c-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="62b1c-109">获取项操作是用于呼叫的质量仪表板的存储库 API 中的项服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="62b1c-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="62b1c-110">获取项目</span><span class="sxs-lookup"><span data-stu-id="62b1c-110">Get Items</span></span>

<span data-ttu-id="62b1c-111">在存储库中获取项目返回的所有项目。</span><span class="sxs-lookup"><span data-stu-id="62b1c-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="62b1c-112">**方法**</span><span class="sxs-lookup"><span data-stu-id="62b1c-112">**Method**</span></span>|<span data-ttu-id="62b1c-113">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="62b1c-113">**Request URI**</span></span>|<span data-ttu-id="62b1c-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="62b1c-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="62b1c-115">获取</span><span class="sxs-lookup"><span data-stu-id="62b1c-115">GET</span></span>  <br/> |<span data-ttu-id="62b1c-116">https://\<门户\>/QoERepositoryService/repository/item</span><span class="sxs-lookup"><span data-stu-id="62b1c-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="62b1c-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="62b1c-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="62b1c-118">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="62b1c-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="62b1c-119">**请求标头**的任何其他的标头。</span><span class="sxs-lookup"><span data-stu-id="62b1c-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="62b1c-120">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="62b1c-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="62b1c-121">**响应**-响应包括 HTTP 状态代码和一响应标头。</span><span class="sxs-lookup"><span data-stu-id="62b1c-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="62b1c-122">**状态代码**-成功的操作返回状态代码 200 （确定)。</span><span class="sxs-lookup"><span data-stu-id="62b1c-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="62b1c-123">**响应标头**的任何其他的标头。</span><span class="sxs-lookup"><span data-stu-id="62b1c-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="62b1c-124">**响应正文**-下面是以 json 格式的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="62b1c-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="62b1c-125">返回项目对象的数组。</span><span class="sxs-lookup"><span data-stu-id="62b1c-125">An array of Item objects is returned.</span></span> <span data-ttu-id="62b1c-126">有关项目对象的详细信息，请参阅获取项。</span><span class="sxs-lookup"><span data-stu-id="62b1c-126">For details about Item object, see Get Item.</span></span> 
  
```
[{
"itemId": 1652,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1654,
"userId": 0,
"type": "application/json"
}]
```
