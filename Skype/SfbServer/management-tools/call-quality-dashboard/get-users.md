---
title: 获取用户
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 摘要：了解作为用户服务的一部分的"获取用户"操作。 用户服务是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是 Skype for Business Server 的工具。
ms.openlocfilehash: a830663fc97d8fda727d1ebb008d97407796cc7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832422"
---
# <a name="get-users"></a><span data-ttu-id="add0e-105">获取用户</span><span class="sxs-lookup"><span data-stu-id="add0e-105">Get Users</span></span>
 
<span data-ttu-id="add0e-106">**摘要：** 了解作为用户服务的一部分的"获取用户"操作。</span><span class="sxs-lookup"><span data-stu-id="add0e-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="add0e-107">用户服务是通话质量仪表板存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="add0e-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="add0e-108">通话质量仪表板是 Skype for Business Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="add0e-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="add0e-109">Get Users 操作是呼叫质量仪表板的存储库 API 中的用户服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="add0e-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="add0e-110">获取用户</span><span class="sxs-lookup"><span data-stu-id="add0e-110">Get Users</span></span>

<span data-ttu-id="add0e-111">Get Users returns a list of users in the repository.</span><span class="sxs-lookup"><span data-stu-id="add0e-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="add0e-112">**方法**</span><span class="sxs-lookup"><span data-stu-id="add0e-112">**Method**</span></span>|<span data-ttu-id="add0e-113">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="add0e-113">**Request URI**</span></span>|<span data-ttu-id="add0e-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="add0e-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="add0e-115">GET</span><span class="sxs-lookup"><span data-stu-id="add0e-115">GET</span></span>  <br/> |<span data-ttu-id="add0e-116">https:// \<portal\> /QoERepositoryService/repository/user</span><span class="sxs-lookup"><span data-stu-id="add0e-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="add0e-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="add0e-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="add0e-118">**URI 参数** - 无。</span><span class="sxs-lookup"><span data-stu-id="add0e-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="add0e-119">**请求标头** - 无其他标头。</span><span class="sxs-lookup"><span data-stu-id="add0e-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="add0e-120">**请求正文** - 无。</span><span class="sxs-lookup"><span data-stu-id="add0e-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="add0e-121">**响应** - 响应包括 HTTP 状态代码和一组响应标头。</span><span class="sxs-lookup"><span data-stu-id="add0e-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="add0e-122">**状态代码** - 成功操作返回状态代码 200 (确定) 。</span><span class="sxs-lookup"><span data-stu-id="add0e-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="add0e-123">**响应标头** - 无其他标头。</span><span class="sxs-lookup"><span data-stu-id="add0e-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="add0e-124">**响应正文** - 下面是 JSON 中的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="add0e-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="add0e-125">返回 User 对象的数组。</span><span class="sxs-lookup"><span data-stu-id="add0e-125">An array of User objects is returned.</span></span> <span data-ttu-id="add0e-126">有关 User 对象的详细信息，请参阅"获取用户"。</span><span class="sxs-lookup"><span data-stu-id="add0e-126">For details about the User object, see Get User.</span></span> 
  
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


