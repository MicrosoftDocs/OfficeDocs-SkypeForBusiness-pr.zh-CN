---
title: 获取用户
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 摘要： 了解有关获取用户操作，为用户服务的一部分。 用户服务是为呼叫质量仪表板存储库 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: e3863819ea15a1039a3a02b1a35cfc7326af7e1d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="get-user"></a><span data-ttu-id="62eb9-105">获取用户</span><span class="sxs-lookup"><span data-stu-id="62eb9-105">Get User</span></span>
 
<span data-ttu-id="62eb9-106">**摘要：**了解有关获取用户操作，为用户服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="62eb9-106">**Summary:** Learn about the Get User operation, which is part of the User Service.</span></span> <span data-ttu-id="62eb9-107">用户服务是为呼叫质量仪表板存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="62eb9-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="62eb9-108">通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="62eb9-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="62eb9-109">获取用户操作是用户服务存储库 API 调用质量仪表板中的一部分。</span><span class="sxs-lookup"><span data-stu-id="62eb9-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user"></a><span data-ttu-id="62eb9-110">获取用户</span><span class="sxs-lookup"><span data-stu-id="62eb9-110">Get User</span></span>

<span data-ttu-id="62eb9-111">从存储库中获取用户返回用户记录。</span><span class="sxs-lookup"><span data-stu-id="62eb9-111">Get User returns a user record from the repository.</span></span>
  
|<span data-ttu-id="62eb9-112">**方法**</span><span class="sxs-lookup"><span data-stu-id="62eb9-112">**Method**</span></span>|<span data-ttu-id="62eb9-113">**请求的 URI**</span><span class="sxs-lookup"><span data-stu-id="62eb9-113">**Request URI**</span></span>|<span data-ttu-id="62eb9-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="62eb9-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="62eb9-115">获取</span><span class="sxs-lookup"><span data-stu-id="62eb9-115">GET</span></span>  <br/> |<span data-ttu-id="62eb9-116">https://\<门户网站\>/QoERepositoryService/存储 {库/用户/用户 Id}</span><span class="sxs-lookup"><span data-stu-id="62eb9-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}</span></span>  <br/> |<span data-ttu-id="62eb9-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="62eb9-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="62eb9-118">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="62eb9-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="62eb9-119">**请求标头**的任何其他标头。</span><span class="sxs-lookup"><span data-stu-id="62eb9-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="62eb9-120">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="62eb9-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="62eb9-121">**响应**-响应包括 HTTP 状态代码和一套响应标头。</span><span class="sxs-lookup"><span data-stu-id="62eb9-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="62eb9-122">**状态代码**-操作成功返回状态码 200 (OK)。</span><span class="sxs-lookup"><span data-stu-id="62eb9-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="62eb9-123">如果找不到 ID 指定的用户，它将返回状态代码 404 （未找到）。</span><span class="sxs-lookup"><span data-stu-id="62eb9-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="62eb9-124">**响应标头**的任何其他标头。</span><span class="sxs-lookup"><span data-stu-id="62eb9-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="62eb9-125">**响应正文**-下面是 json 格式的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="62eb9-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}

```

 <span data-ttu-id="62eb9-126">*用户 Id*的用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="62eb9-126">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="62eb9-127">*名*的普通用户的外部用户标识。</span><span class="sxs-lookup"><span data-stu-id="62eb9-127">*loginName*  - External user identification for regular users.</span></span> <span data-ttu-id="62eb9-128">如果 Windows 身份验证用于验证用户身份，这可能是用户的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="62eb9-128">If Windows Authentication is used for authenticating users, then this may be a FQDN of the user.</span></span>
  
 <span data-ttu-id="62eb9-129">*defaultItemId* -此用户的默认项的 ID。</span><span class="sxs-lookup"><span data-stu-id="62eb9-129">*defaultItemId*  - ID of the default Item for this user.</span></span> <span data-ttu-id="62eb9-130">默认值项是最上面的一项是与用户相关联。</span><span class="sxs-lookup"><span data-stu-id="62eb9-130">The default Item is the top-most Item that is associated to the user.</span></span> <span data-ttu-id="62eb9-131">此用户拥有的所有其他项目的导航可以从默认项。</span><span class="sxs-lookup"><span data-stu-id="62eb9-131">All other Items this user owns can be navigated from the default Item.</span></span>
  
> [!NOTE]
> <span data-ttu-id="62eb9-132">提供`defaultItemId`值与获取项操作来检索项的默认值的详细信息。</span><span class="sxs-lookup"><span data-stu-id="62eb9-132">Supply the  `defaultItemId` value to Get Item operation to retrieve the details of the default Item.</span></span>
  

