---
title: 获取用户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 摘要： 了解如何获取用户操作，它是用户服务的一部分。 用户服务是用于呼叫的质量仪表板的存储库 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
ms.openlocfilehash: 4f3c1a00134cb0f8276d511d80ae7bc6f82f2d72
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897329"
---
# <a name="get-users"></a><span data-ttu-id="63666-105">获取用户</span><span class="sxs-lookup"><span data-stu-id="63666-105">Get Users</span></span>
 
<span data-ttu-id="63666-106">**摘要：** 了解如何获取用户操作，它是用户服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="63666-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="63666-107">用户服务是用于呼叫的质量仪表板的存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="63666-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="63666-108">呼叫质量仪表板是用于业务服务器 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="63666-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="63666-109">获取用户操作是用于呼叫的质量仪表板的存储库 API 中的用户服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="63666-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="63666-110">获取用户</span><span class="sxs-lookup"><span data-stu-id="63666-110">Get Users</span></span>

<span data-ttu-id="63666-111">获取用户返回存储库中的用户的列表。</span><span class="sxs-lookup"><span data-stu-id="63666-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="63666-112">**方法**</span><span class="sxs-lookup"><span data-stu-id="63666-112">**Method**</span></span>|<span data-ttu-id="63666-113">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="63666-113">**Request URI**</span></span>|<span data-ttu-id="63666-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="63666-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="63666-115">获取</span><span class="sxs-lookup"><span data-stu-id="63666-115">GET</span></span>  <br/> |<span data-ttu-id="63666-116">https://\<门户\>/QoERepositoryService/repository/user</span><span class="sxs-lookup"><span data-stu-id="63666-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="63666-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="63666-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="63666-118">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="63666-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="63666-119">**请求标头**的任何其他的标头。</span><span class="sxs-lookup"><span data-stu-id="63666-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="63666-120">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="63666-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="63666-121">**响应**-响应包括 HTTP 状态代码和一响应标头。</span><span class="sxs-lookup"><span data-stu-id="63666-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="63666-122">**状态代码**-成功的操作返回状态代码 200 （确定)。</span><span class="sxs-lookup"><span data-stu-id="63666-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="63666-123">**响应标头**的任何其他的标头。</span><span class="sxs-lookup"><span data-stu-id="63666-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="63666-124">**响应正文**-下面是以 json 格式的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="63666-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="63666-125">返回用户对象的数组。</span><span class="sxs-lookup"><span data-stu-id="63666-125">An array of User objects is returned.</span></span> <span data-ttu-id="63666-126">有关用户对象的详细信息，请参阅获取用户。</span><span class="sxs-lookup"><span data-stu-id="63666-126">For details about the User object, see Get User.</span></span> 
  
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


