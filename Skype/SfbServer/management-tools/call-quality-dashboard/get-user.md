---
title: 获取用户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 摘要：了解 "获取用户" 操作（这是用户服务的一部分）。 用户服务是适用于呼叫质量仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。
ms.openlocfilehash: 09dcbbaeaae98ed7b01f3d710cfda23aa5fa986f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992619"
---
# <a name="get-user"></a><span data-ttu-id="46d64-105">获取用户</span><span class="sxs-lookup"><span data-stu-id="46d64-105">Get User</span></span>
 
<span data-ttu-id="46d64-106">**摘要：** 了解 "获取用户" 操作，该操作是用户服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="46d64-106">**Summary:** Learn about the Get User operation, which is part of the User Service.</span></span> <span data-ttu-id="46d64-107">用户服务是适用于呼叫质量仪表板的知识库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="46d64-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="46d64-108">通话质量仪表板是 Skype for business 服务器的工具。</span><span class="sxs-lookup"><span data-stu-id="46d64-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="46d64-109">"获取用户" 操作是 "资源库 API for 通话质量" 仪表板中的用户服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="46d64-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user"></a><span data-ttu-id="46d64-110">获取用户</span><span class="sxs-lookup"><span data-stu-id="46d64-110">Get User</span></span>

<span data-ttu-id="46d64-111">获取用户从存储库返回用户记录。</span><span class="sxs-lookup"><span data-stu-id="46d64-111">Get User returns a user record from the repository.</span></span>
  
|<span data-ttu-id="46d64-112">**种**</span><span class="sxs-lookup"><span data-stu-id="46d64-112">**Method**</span></span>|<span data-ttu-id="46d64-113">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="46d64-113">**Request URI**</span></span>|<span data-ttu-id="46d64-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="46d64-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="46d64-115">获取</span><span class="sxs-lookup"><span data-stu-id="46d64-115">GET</span></span>  <br/> |<span data-ttu-id="46d64-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}</span><span class="sxs-lookup"><span data-stu-id="46d64-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}</span></span>  <br/> |<span data-ttu-id="46d64-117">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="46d64-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="46d64-118">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="46d64-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="46d64-119">**请求标题**-无其他标题。</span><span class="sxs-lookup"><span data-stu-id="46d64-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="46d64-120">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="46d64-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="46d64-121">**响应**-响应包括 HTTP 状态代码和一组响应标头。</span><span class="sxs-lookup"><span data-stu-id="46d64-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="46d64-122">**状态代码**-成功的操作返回状态代码200（OK）。</span><span class="sxs-lookup"><span data-stu-id="46d64-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="46d64-123">如果找不到指定的用户 ID，将返回状态代码404（未找到）。</span><span class="sxs-lookup"><span data-stu-id="46d64-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="46d64-124">**响应标题**-无其他标题。</span><span class="sxs-lookup"><span data-stu-id="46d64-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="46d64-125">**响应正文**-下面是 JSON 中的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="46d64-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 <span data-ttu-id="46d64-126">*userId* -用户 ID。</span><span class="sxs-lookup"><span data-stu-id="46d64-126">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="46d64-127">*loginName* -常规用户的外部用户标识。</span><span class="sxs-lookup"><span data-stu-id="46d64-127">*loginName*  - External user identification for regular users.</span></span> <span data-ttu-id="46d64-128">如果使用 Windows 身份验证对用户进行身份验证，则这可能是用户的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="46d64-128">If Windows Authentication is used for authenticating users, then this may be a FQDN of the user.</span></span>
  
 <span data-ttu-id="46d64-129">*defaultItemId* -此用户的默认项目的 ID。</span><span class="sxs-lookup"><span data-stu-id="46d64-129">*defaultItemId*  - ID of the default Item for this user.</span></span> <span data-ttu-id="46d64-130">默认项目是与用户关联的最顶部的项目。</span><span class="sxs-lookup"><span data-stu-id="46d64-130">The default Item is the top-most Item that is associated to the user.</span></span> <span data-ttu-id="46d64-131">此用户拥有的所有其他项目都可以从 "默认" 项目中进行导航。</span><span class="sxs-lookup"><span data-stu-id="46d64-131">All other Items this user owns can be navigated from the default Item.</span></span>
  
> [!NOTE]
> <span data-ttu-id="46d64-132">提供用于`defaultItemId`获取项目操作的值以检索默认项目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="46d64-132">Supply the  `defaultItemId` value to Get Item operation to retrieve the details of the default Item.</span></span>
  

