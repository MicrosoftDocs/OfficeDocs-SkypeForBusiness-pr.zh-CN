---
title: 获取用户设置
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
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 摘要：了解 "获取用户设置" 操作，该操作是用户设置服务的一部分。 "用户设置" 服务是 "呼叫质量" 仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。
ms.openlocfilehash: 5b5ad679387866ba6562e031b6d3a42cc68851a0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816741"
---
# <a name="get-user-settings"></a><span data-ttu-id="33555-105">获取用户设置</span><span class="sxs-lookup"><span data-stu-id="33555-105">Get User Settings</span></span>
 
<span data-ttu-id="33555-106">**摘要：** 了解 "获取用户设置" 操作，该操作是 "用户设置" 服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="33555-106">**Summary:** Learn about the Get User Settings operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="33555-107">"用户设置" 服务是 "呼叫质量" 仪表板的知识库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="33555-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="33555-108">通话质量仪表板是 Skype for business 服务器的工具。</span><span class="sxs-lookup"><span data-stu-id="33555-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="33555-109">"获取用户设置" 操作是 "资源库 API for 通话质量" 仪表板中的 "用户设置" 服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="33555-109">The Get User Settings operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-settings"></a><span data-ttu-id="33555-110">获取用户设置</span><span class="sxs-lookup"><span data-stu-id="33555-110">Get User Settings</span></span>

<span data-ttu-id="33555-111">获取用户设置返回指定用户的设置列表。</span><span class="sxs-lookup"><span data-stu-id="33555-111">Get User Settings returns a list of settings for a specified user.</span></span>
  

|<span data-ttu-id="33555-112">**种**</span><span class="sxs-lookup"><span data-stu-id="33555-112">**Method**</span></span>|<span data-ttu-id="33555-113">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="33555-113">**Request URI**</span></span>|<span data-ttu-id="33555-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="33555-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="33555-115">获取</span><span class="sxs-lookup"><span data-stu-id="33555-115">GET</span></span>  <br/> |<span data-ttu-id="33555-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting</span><span class="sxs-lookup"><span data-stu-id="33555-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting</span></span>  <br/> |<span data-ttu-id="33555-117">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="33555-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="33555-118">**URI 参数**</span><span class="sxs-lookup"><span data-stu-id="33555-118">**URI Parameters**</span></span>
  
- <span data-ttu-id="33555-119">*有效*-可选。</span><span class="sxs-lookup"><span data-stu-id="33555-119">*effective*  - Optional.</span></span> <span data-ttu-id="33555-120">仅当使用特殊用户 ID 默认值时，此参数才适用。</span><span class="sxs-lookup"><span data-stu-id="33555-120">This parameter applies only when the special user ID default is used.</span></span> <span data-ttu-id="33555-121">在其他情况下，它将被忽略。</span><span class="sxs-lookup"><span data-stu-id="33555-121">In other cases, it will be ignored.</span></span> <span data-ttu-id="33555-122">`True`返回有效的用户设置`false` ，并仅返回用户设置（默认值）。</span><span class="sxs-lookup"><span data-stu-id="33555-122">`True` returns effective user settings and `false` returns just user settings (default).</span></span>
    
  <span data-ttu-id="33555-123">**请求标题**-无其他标题。</span><span class="sxs-lookup"><span data-stu-id="33555-123">**Request Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="33555-124">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="33555-124">**Request Body** - None.</span></span>
  
  <span data-ttu-id="33555-125">**响应**-响应包括 HTTP 状态代码和一组响应标头。</span><span class="sxs-lookup"><span data-stu-id="33555-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
  <span data-ttu-id="33555-126">**状态代码**-成功的操作返回状态代码200（OK）。</span><span class="sxs-lookup"><span data-stu-id="33555-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
  <span data-ttu-id="33555-127">**响应标题**-无其他标题。</span><span class="sxs-lookup"><span data-stu-id="33555-127">**Response Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="33555-128">**响应正文**-下面是 JSON 中的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="33555-128">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
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
