---
title: 获取用户
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 摘要： 了解如何获取用户操作，它是用户服务的一部分。 用户服务是用于呼叫的质量仪表板的存储库 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
ms.openlocfilehash: 3508336eda934cf317f857d7ad7e903cb7298e00
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035576"
---
# <a name="get-user"></a><span data-ttu-id="1ba66-105">获取用户</span><span class="sxs-lookup"><span data-stu-id="1ba66-105">Get User</span></span>
 
<span data-ttu-id="1ba66-106">**摘要：** 了解如何获取用户操作，它是用户服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="1ba66-106">**Summary:** Learn about the Get User operation, which is part of the User Service.</span></span> <span data-ttu-id="1ba66-107">用户服务是用于呼叫的质量仪表板的存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="1ba66-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="1ba66-108">呼叫质量仪表板是用于业务服务器 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="1ba66-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="1ba66-109">获取用户操作是用于呼叫的质量仪表板的存储库 API 中的用户服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="1ba66-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user"></a><span data-ttu-id="1ba66-110">获取用户</span><span class="sxs-lookup"><span data-stu-id="1ba66-110">Get User</span></span>

<span data-ttu-id="1ba66-111">从存储库中获取用户返回用户记录。</span><span class="sxs-lookup"><span data-stu-id="1ba66-111">Get User returns a user record from the repository.</span></span>
  
|<span data-ttu-id="1ba66-112">**方法**</span><span class="sxs-lookup"><span data-stu-id="1ba66-112">**Method**</span></span>|<span data-ttu-id="1ba66-113">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="1ba66-113">**Request URI**</span></span>|<span data-ttu-id="1ba66-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="1ba66-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1ba66-115">获取</span><span class="sxs-lookup"><span data-stu-id="1ba66-115">GET</span></span>  <br/> |<span data-ttu-id="1ba66-116">https://\<门户\>/QoERepositoryService/存储库/用户 / {userId}</span><span class="sxs-lookup"><span data-stu-id="1ba66-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}</span></span>  <br/> |<span data-ttu-id="1ba66-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="1ba66-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="1ba66-118">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="1ba66-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="1ba66-119">**请求标头**的任何其他的标头。</span><span class="sxs-lookup"><span data-stu-id="1ba66-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="1ba66-120">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="1ba66-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="1ba66-121">**响应**-响应包括 HTTP 状态代码和一响应标头。</span><span class="sxs-lookup"><span data-stu-id="1ba66-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="1ba66-122">**状态代码**-成功的操作返回状态代码 200 （确定)。</span><span class="sxs-lookup"><span data-stu-id="1ba66-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="1ba66-123">如果找不到 ID 指定的用户，则将返回状态代码的 404 （未找到）。</span><span class="sxs-lookup"><span data-stu-id="1ba66-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="1ba66-124">**响应标头**的任何其他的标头。</span><span class="sxs-lookup"><span data-stu-id="1ba66-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="1ba66-125">**响应正文**-下面是以 json 格式的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="1ba66-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 <span data-ttu-id="1ba66-126">*用户 Id*的用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="1ba66-126">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="1ba66-127">*使用 loginName* -一般用户的外部用户标识。</span><span class="sxs-lookup"><span data-stu-id="1ba66-127">*loginName*  - External user identification for regular users.</span></span> <span data-ttu-id="1ba66-128">如果用户进行身份验证使用 Windows 身份验证，则这可能是用户的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1ba66-128">If Windows Authentication is used for authenticating users, then this may be a FQDN of the user.</span></span>
  
 <span data-ttu-id="1ba66-129">*defaultItemId* -此用户的默认项目的 ID。</span><span class="sxs-lookup"><span data-stu-id="1ba66-129">*defaultItemId*  - ID of the default Item for this user.</span></span> <span data-ttu-id="1ba66-130">默认项目是与用户相关联的顶层项目。</span><span class="sxs-lookup"><span data-stu-id="1ba66-130">The default Item is the top-most Item that is associated to the user.</span></span> <span data-ttu-id="1ba66-131">此用户拥有的所有其他项目的导航可以从默认的项目。</span><span class="sxs-lookup"><span data-stu-id="1ba66-131">All other Items this user owns can be navigated from the default Item.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1ba66-132">提供`defaultItemId`的值为获取项操作来检索的默认项目详细信息。</span><span class="sxs-lookup"><span data-stu-id="1ba66-132">Supply the  `defaultItemId` value to Get Item operation to retrieve the details of the default Item.</span></span>
  

