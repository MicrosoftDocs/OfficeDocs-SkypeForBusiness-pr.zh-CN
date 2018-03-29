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
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 摘要： 了解有关获取用户操作，为用户服务的一部分。 用户服务是为呼叫质量仪表板存储库 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: ed26614c0fd4b443e9c5d698d1db9467291ca3d0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="get-users"></a><span data-ttu-id="76241-105">获取用户</span><span class="sxs-lookup"><span data-stu-id="76241-105">Get Users</span></span>
 
<span data-ttu-id="76241-106">**摘要：**了解有关获取用户操作，为用户服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="76241-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="76241-107">用户服务是为呼叫质量仪表板存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="76241-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="76241-108">通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="76241-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="76241-109">获取用户操作是用户服务存储库 API 调用质量仪表板中的一部分。</span><span class="sxs-lookup"><span data-stu-id="76241-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="76241-110">获取用户</span><span class="sxs-lookup"><span data-stu-id="76241-110">Get Users</span></span>

<span data-ttu-id="76241-111">在存储库中获取用户返回一个用户列表。</span><span class="sxs-lookup"><span data-stu-id="76241-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="76241-112">**方法**</span><span class="sxs-lookup"><span data-stu-id="76241-112">**Method**</span></span>|<span data-ttu-id="76241-113">**请求的 URI**</span><span class="sxs-lookup"><span data-stu-id="76241-113">**Request URI**</span></span>|<span data-ttu-id="76241-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="76241-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="76241-115">获取</span><span class="sxs-lookup"><span data-stu-id="76241-115">GET</span></span>  <br/> |<span data-ttu-id="76241-116">https://\<门户网站\>/QoERepositoryService/repository/user</span><span class="sxs-lookup"><span data-stu-id="76241-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="76241-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="76241-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="76241-118">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="76241-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="76241-119">**请求标头**的任何其他标头。</span><span class="sxs-lookup"><span data-stu-id="76241-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="76241-120">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="76241-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="76241-121">**响应**-响应包括 HTTP 状态代码和一套响应标头。</span><span class="sxs-lookup"><span data-stu-id="76241-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="76241-122">**状态代码**-操作成功返回状态码 200 (OK)。</span><span class="sxs-lookup"><span data-stu-id="76241-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="76241-123">**响应标头**的任何其他标头。</span><span class="sxs-lookup"><span data-stu-id="76241-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="76241-124">**响应正文**-下面是 json 格式的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="76241-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="76241-125">用户对象数组形式返回。</span><span class="sxs-lookup"><span data-stu-id="76241-125">An array of User objects is returned.</span></span> <span data-ttu-id="76241-126">用户对象的详细信息，请参阅获取用户。</span><span class="sxs-lookup"><span data-stu-id="76241-126">For details about the User object, see Get User.</span></span> 
  
```
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


