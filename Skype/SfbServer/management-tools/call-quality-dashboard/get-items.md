---
title: 获取项目
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: '摘要: 了解有关 "获取项目" 操作 (这是项目服务的一部分) 的信息。 项目服务是适用于呼叫质量仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。'
ms.openlocfilehash: a1e7e8525df77cd5aacafb6d41316a985fbe9694
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274700"
---
# <a name="get-items"></a><span data-ttu-id="c7861-105">获取项目</span><span class="sxs-lookup"><span data-stu-id="c7861-105">Get Items</span></span>
 
<span data-ttu-id="c7861-106">**摘要:** 了解 "获取项目" 操作, 该操作是项目服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="c7861-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="c7861-107">项目服务是适用于呼叫质量仪表板的知识库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="c7861-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="c7861-108">通话质量仪表板是 Skype for business 服务器的工具。</span><span class="sxs-lookup"><span data-stu-id="c7861-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="c7861-109">获取项目操作是 "知识库 API for 通话质量" 仪表板中的项目服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="c7861-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="c7861-110">获取项目</span><span class="sxs-lookup"><span data-stu-id="c7861-110">Get Items</span></span>

<span data-ttu-id="c7861-111">获取项目将返回存储库中的所有项目。</span><span class="sxs-lookup"><span data-stu-id="c7861-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="c7861-112">**种**</span><span class="sxs-lookup"><span data-stu-id="c7861-112">**Method**</span></span>|<span data-ttu-id="c7861-113">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="c7861-113">**Request URI**</span></span>|<span data-ttu-id="c7861-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="c7861-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c7861-115">获取</span><span class="sxs-lookup"><span data-stu-id="c7861-115">GET</span></span>  <br/> |<span data-ttu-id="c7861-116">https://\<portal\>/QoERepositoryService/repository/item</span><span class="sxs-lookup"><span data-stu-id="c7861-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="c7861-117">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="c7861-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="c7861-118">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="c7861-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="c7861-119">**请求标题**-无其他标题。</span><span class="sxs-lookup"><span data-stu-id="c7861-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="c7861-120">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="c7861-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="c7861-121">**响应**-响应包括 HTTP 状态代码和一组响应标头。</span><span class="sxs-lookup"><span data-stu-id="c7861-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="c7861-122">**状态代码**-成功的操作返回状态代码 200 (OK)。</span><span class="sxs-lookup"><span data-stu-id="c7861-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="c7861-123">**响应标题**-无其他标题。</span><span class="sxs-lookup"><span data-stu-id="c7861-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="c7861-124">**响应正文**-下面是 JSON 中的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="c7861-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c7861-125">返回 Item 对象的数组。</span><span class="sxs-lookup"><span data-stu-id="c7861-125">An array of Item objects is returned.</span></span> <span data-ttu-id="c7861-126">有关项目对象的详细信息, 请参阅获取项目。</span><span class="sxs-lookup"><span data-stu-id="c7861-126">For details about Item object, see Get Item.</span></span> 
  
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
