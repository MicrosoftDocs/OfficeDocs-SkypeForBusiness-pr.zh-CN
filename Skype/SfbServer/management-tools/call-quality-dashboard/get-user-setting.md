---
title: 获取用户设置
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
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 摘要：了解作为用户设置服务的一部分的"获取用户设置"操作。 用户设置服务是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是 Skype for Business Server 的工具。
ms.openlocfilehash: 82632f5de7ae215d6f34d9f0b39e500fb713a1be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832482"
---
# <a name="get-user-setting"></a><span data-ttu-id="1b3bc-105">获取用户设置</span><span class="sxs-lookup"><span data-stu-id="1b3bc-105">Get User Setting</span></span>
 
<span data-ttu-id="1b3bc-106">**摘要：** 了解作为用户设置服务的一部分的"获取用户设置"操作。</span><span class="sxs-lookup"><span data-stu-id="1b3bc-106">**Summary:** Learn about the Get User Setting operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="1b3bc-107">用户设置服务是通话质量仪表板存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="1b3bc-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="1b3bc-108">通话质量仪表板是 Skype for Business Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="1b3bc-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="1b3bc-109">Get User Setting 操作是呼叫质量仪表板的存储库 API 中的用户设置服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="1b3bc-109">The Get User Setting operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-setting"></a><span data-ttu-id="1b3bc-110">获取用户设置</span><span class="sxs-lookup"><span data-stu-id="1b3bc-110">Get User Setting</span></span>

<span data-ttu-id="1b3bc-111">获取用户设置返回单个用户设置。</span><span class="sxs-lookup"><span data-stu-id="1b3bc-111">Get User Setting returns a single user setting.</span></span>
  

|<span data-ttu-id="1b3bc-112">**方法**</span><span class="sxs-lookup"><span data-stu-id="1b3bc-112">**Method**</span></span>|<span data-ttu-id="1b3bc-113">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="1b3bc-113">**Request URI**</span></span>|<span data-ttu-id="1b3bc-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="1b3bc-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1b3bc-115">GET</span><span class="sxs-lookup"><span data-stu-id="1b3bc-115">GET</span></span>  <br/> |<span data-ttu-id="1b3bc-116">https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting/{key}</span><span class="sxs-lookup"><span data-stu-id="1b3bc-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting/{key}</span></span>  <br/> |<span data-ttu-id="1b3bc-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="1b3bc-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="1b3bc-118">**URI 参数** - 无。</span><span class="sxs-lookup"><span data-stu-id="1b3bc-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="1b3bc-119">**请求标头** - 无其他标头。</span><span class="sxs-lookup"><span data-stu-id="1b3bc-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="1b3bc-120">**请求正文** - 无。</span><span class="sxs-lookup"><span data-stu-id="1b3bc-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="1b3bc-121">**响应** - 响应包括 HTTP 状态代码和一组响应标头。</span><span class="sxs-lookup"><span data-stu-id="1b3bc-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="1b3bc-122">**状态代码** - 成功操作返回状态代码 200 (确定) 。</span><span class="sxs-lookup"><span data-stu-id="1b3bc-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="1b3bc-123">**响应标头** - 无其他标头。</span><span class="sxs-lookup"><span data-stu-id="1b3bc-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="1b3bc-124">**响应正文** - 下面是 JSON 中的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="1b3bc-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 <span data-ttu-id="1b3bc-125">*userId*  - 用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="1b3bc-125">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="1b3bc-126">*键*  - 设置的键。</span><span class="sxs-lookup"><span data-stu-id="1b3bc-126">*key*  - Key of the setting.</span></span>
  
 <span data-ttu-id="1b3bc-127">*value*  - 设置的值。</span><span class="sxs-lookup"><span data-stu-id="1b3bc-127">*value*  - Value of the setting.</span></span>
  

