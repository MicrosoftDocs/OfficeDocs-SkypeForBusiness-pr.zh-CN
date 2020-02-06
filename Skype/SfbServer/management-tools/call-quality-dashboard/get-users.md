---
title: 获取用户
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
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 摘要：了解 "获取用户" 操作（这是用户服务的一部分）。 用户服务是适用于呼叫质量仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。
ms.openlocfilehash: 81d261a49798ef49d4a1d693681b4497652cf395
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816721"
---
# <a name="get-users"></a><span data-ttu-id="27a4a-105">获取用户</span><span class="sxs-lookup"><span data-stu-id="27a4a-105">Get Users</span></span>
 
<span data-ttu-id="27a4a-106">**摘要：** 了解 "获取用户" 操作，这是用户服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="27a4a-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="27a4a-107">用户服务是适用于呼叫质量仪表板的知识库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="27a4a-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="27a4a-108">通话质量仪表板是 Skype for business 服务器的工具。</span><span class="sxs-lookup"><span data-stu-id="27a4a-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="27a4a-109">"获取用户" 操作是 "资源库 API for 通话质量" 仪表板中的用户服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="27a4a-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="27a4a-110">获取用户</span><span class="sxs-lookup"><span data-stu-id="27a4a-110">Get Users</span></span>

<span data-ttu-id="27a4a-111">获取用户返回存储库中的用户列表。</span><span class="sxs-lookup"><span data-stu-id="27a4a-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="27a4a-112">**种**</span><span class="sxs-lookup"><span data-stu-id="27a4a-112">**Method**</span></span>|<span data-ttu-id="27a4a-113">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="27a4a-113">**Request URI**</span></span>|<span data-ttu-id="27a4a-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="27a4a-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="27a4a-115">获取</span><span class="sxs-lookup"><span data-stu-id="27a4a-115">GET</span></span>  <br/> |<span data-ttu-id="27a4a-116">https://\<portal\>/QoERepositoryService/repository/user</span><span class="sxs-lookup"><span data-stu-id="27a4a-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="27a4a-117">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="27a4a-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="27a4a-118">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="27a4a-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="27a4a-119">**请求标题**-无其他标题。</span><span class="sxs-lookup"><span data-stu-id="27a4a-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="27a4a-120">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="27a4a-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="27a4a-121">**响应**-响应包括 HTTP 状态代码和一组响应标头。</span><span class="sxs-lookup"><span data-stu-id="27a4a-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="27a4a-122">**状态代码**-成功的操作返回状态代码200（OK）。</span><span class="sxs-lookup"><span data-stu-id="27a4a-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="27a4a-123">**响应标题**-无其他标题。</span><span class="sxs-lookup"><span data-stu-id="27a4a-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="27a4a-124">**响应正文**-下面是 JSON 中的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="27a4a-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="27a4a-125">返回一个用户对象数组。</span><span class="sxs-lookup"><span data-stu-id="27a4a-125">An array of User objects is returned.</span></span> <span data-ttu-id="27a4a-126">有关用户对象的详细信息，请参阅获取用户。</span><span class="sxs-lookup"><span data-stu-id="27a4a-126">For details about the User object, see Get User.</span></span> 
  
```json
[{
"userId": 0,
"loginName": "system",
"defaultItemId": 1652
},
{
"userId": 1,
"loginName": "SAMPLEDOMAIN\\testuser1",
"defaultItemId": 1652
},
{
"userId": 2,
"loginName": "SAMPLEDOMAIN\\testuser2",
"defaultItemId": 1774
}]
```


