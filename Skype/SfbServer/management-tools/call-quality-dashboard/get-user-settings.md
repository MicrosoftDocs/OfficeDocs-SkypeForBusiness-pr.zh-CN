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
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 摘要：了解作为用户设置服务的一部分的"获取用户设置"操作。 用户设置服务是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是 Skype for Business Server 的工具。
ms.openlocfilehash: e2ebf39ba5a7de5d36a8b1ea0441808b6e71f97b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832472"
---
# <a name="get-user-settings"></a><span data-ttu-id="479c5-105">获取用户设置</span><span class="sxs-lookup"><span data-stu-id="479c5-105">Get User Settings</span></span>
 
<span data-ttu-id="479c5-106">**摘要：** 了解"获取用户设置"操作，该操作是用户设置服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="479c5-106">**Summary:** Learn about the Get User Settings operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="479c5-107">用户设置服务是通话质量仪表板存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="479c5-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="479c5-108">通话质量仪表板是 Skype for Business Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="479c5-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="479c5-109">Get User Settings 操作是呼叫质量仪表板的存储库 API 中的用户设置服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="479c5-109">The Get User Settings operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-settings"></a><span data-ttu-id="479c5-110">获取用户设置</span><span class="sxs-lookup"><span data-stu-id="479c5-110">Get User Settings</span></span>

<span data-ttu-id="479c5-111">Get User Settings returns a list of settings for a specified user.</span><span class="sxs-lookup"><span data-stu-id="479c5-111">Get User Settings returns a list of settings for a specified user.</span></span>
  

|<span data-ttu-id="479c5-112">**方法**</span><span class="sxs-lookup"><span data-stu-id="479c5-112">**Method**</span></span>|<span data-ttu-id="479c5-113">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="479c5-113">**Request URI**</span></span>|<span data-ttu-id="479c5-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="479c5-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="479c5-115">GET</span><span class="sxs-lookup"><span data-stu-id="479c5-115">GET</span></span>  <br/> |<span data-ttu-id="479c5-116">https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting</span><span class="sxs-lookup"><span data-stu-id="479c5-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting</span></span>  <br/> |<span data-ttu-id="479c5-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="479c5-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="479c5-118">**URI 参数**</span><span class="sxs-lookup"><span data-stu-id="479c5-118">**URI Parameters**</span></span>
  
- <span data-ttu-id="479c5-119">*有效*  - 可选。</span><span class="sxs-lookup"><span data-stu-id="479c5-119">*effective*  - Optional.</span></span> <span data-ttu-id="479c5-120">此参数仅在使用特殊的用户 ID 默认值时适用。</span><span class="sxs-lookup"><span data-stu-id="479c5-120">This parameter applies only when the special user ID default is used.</span></span> <span data-ttu-id="479c5-121">在其他情况下，它将被忽略。</span><span class="sxs-lookup"><span data-stu-id="479c5-121">In other cases, it will be ignored.</span></span> <span data-ttu-id="479c5-122">`True` 返回有效的用户设置， `false` 并仅返回默认 (用户) 。</span><span class="sxs-lookup"><span data-stu-id="479c5-122">`True` returns effective user settings and `false` returns just user settings (default).</span></span>
    
  <span data-ttu-id="479c5-123">**请求标头** - 无其他标头。</span><span class="sxs-lookup"><span data-stu-id="479c5-123">**Request Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="479c5-124">**请求正文** - 无。</span><span class="sxs-lookup"><span data-stu-id="479c5-124">**Request Body** - None.</span></span>
  
  <span data-ttu-id="479c5-125">**响应** - 响应包括 HTTP 状态代码和一组响应标头。</span><span class="sxs-lookup"><span data-stu-id="479c5-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
  <span data-ttu-id="479c5-126">**状态代码** - 成功操作返回状态代码 200 (确定) 。</span><span class="sxs-lookup"><span data-stu-id="479c5-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
  <span data-ttu-id="479c5-127">**响应标头** - 无其他标头。</span><span class="sxs-lookup"><span data-stu-id="479c5-127">**Response Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="479c5-128">**响应正文** - 下面是 JSON 中的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="479c5-128">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
[{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
},
{
"userId": 6,
"key": "ShowTimeStamps",
"value": "true"
}]
```
