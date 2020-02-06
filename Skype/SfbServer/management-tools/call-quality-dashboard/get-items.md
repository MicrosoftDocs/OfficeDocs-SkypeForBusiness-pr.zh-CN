---
title: 获取项目
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: 摘要：了解有关 "获取项目" 操作（这是项目服务的一部分）的信息。 项目服务是适用于呼叫质量仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。
ms.openlocfilehash: 6345201fe3843e3fe8cf6671f01d2db30fb4e22e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816781"
---
# <a name="get-items"></a><span data-ttu-id="3f875-105">获取项目</span><span class="sxs-lookup"><span data-stu-id="3f875-105">Get Items</span></span>
 
<span data-ttu-id="3f875-106">**摘要：** 了解 "获取项目" 操作，该操作是项目服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="3f875-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="3f875-107">项目服务是适用于呼叫质量仪表板的知识库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="3f875-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="3f875-108">通话质量仪表板是 Skype for business 服务器的工具。</span><span class="sxs-lookup"><span data-stu-id="3f875-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="3f875-109">获取项目操作是 "知识库 API for 通话质量" 仪表板中的项目服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="3f875-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="3f875-110">获取项目</span><span class="sxs-lookup"><span data-stu-id="3f875-110">Get Items</span></span>

<span data-ttu-id="3f875-111">获取项目将返回存储库中的所有项目。</span><span class="sxs-lookup"><span data-stu-id="3f875-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="3f875-112">**种**</span><span class="sxs-lookup"><span data-stu-id="3f875-112">**Method**</span></span>|<span data-ttu-id="3f875-113">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="3f875-113">**Request URI**</span></span>|<span data-ttu-id="3f875-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="3f875-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3f875-115">获取</span><span class="sxs-lookup"><span data-stu-id="3f875-115">GET</span></span>  <br/> |<span data-ttu-id="3f875-116">https://\<portal\>/QoERepositoryService/repository/item</span><span class="sxs-lookup"><span data-stu-id="3f875-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="3f875-117">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="3f875-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="3f875-118">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="3f875-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="3f875-119">**请求标题**-无其他标题。</span><span class="sxs-lookup"><span data-stu-id="3f875-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="3f875-120">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="3f875-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="3f875-121">**响应**-响应包括 HTTP 状态代码和一组响应标头。</span><span class="sxs-lookup"><span data-stu-id="3f875-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="3f875-122">**状态代码**-成功的操作返回状态代码200（OK）。</span><span class="sxs-lookup"><span data-stu-id="3f875-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="3f875-123">**响应标题**-无其他标题。</span><span class="sxs-lookup"><span data-stu-id="3f875-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="3f875-124">**响应正文**-下面是 JSON 中的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="3f875-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3f875-125">返回 Item 对象的数组。</span><span class="sxs-lookup"><span data-stu-id="3f875-125">An array of Item objects is returned.</span></span> <span data-ttu-id="3f875-126">有关项目对象的详细信息，请参阅获取项目。</span><span class="sxs-lookup"><span data-stu-id="3f875-126">For details about Item object, see Get Item.</span></span> 
  
```json
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
