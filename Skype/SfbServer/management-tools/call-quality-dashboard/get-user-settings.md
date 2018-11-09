---
title: 获取用户设置
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 摘要： 了解如何获取用户设置操作，它是用户设置服务的一部分。 用户设置服务是呼叫质量仪表板的存储库 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
ms.openlocfilehash: 9547479b95a8b321a9aa2f92c7cfcb2e88edf4bb
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035601"
---
# <a name="get-user-settings"></a><span data-ttu-id="54681-105">获取用户设置</span><span class="sxs-lookup"><span data-stu-id="54681-105">Get User Settings</span></span>
 
<span data-ttu-id="54681-106">**摘要：** 了解如何获取用户设置操作，它是用户设置服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="54681-106">**Summary:** Learn about the Get User Settings operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="54681-107">用户设置服务是呼叫质量仪表板的存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="54681-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="54681-108">呼叫质量仪表板是用于业务服务器 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="54681-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="54681-109">获取用户设置操作是用于呼叫的质量仪表板的存储库 API 中的用户设置服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="54681-109">The Get User Settings operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-settings"></a><span data-ttu-id="54681-110">获取用户设置</span><span class="sxs-lookup"><span data-stu-id="54681-110">Get User Settings</span></span>

<span data-ttu-id="54681-111">获取用户设置返回指定用户的设置的列表。</span><span class="sxs-lookup"><span data-stu-id="54681-111">Get User Settings returns a list of settings for a specified user.</span></span>
  

|<span data-ttu-id="54681-112">**方法**</span><span class="sxs-lookup"><span data-stu-id="54681-112">**Method**</span></span>|<span data-ttu-id="54681-113">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="54681-113">**Request URI**</span></span>|<span data-ttu-id="54681-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="54681-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="54681-115">获取</span><span class="sxs-lookup"><span data-stu-id="54681-115">GET</span></span>  <br/> |<span data-ttu-id="54681-116">https://\<门户\>/QoERepositoryService/存储库/用户 / {userId} / 设置</span><span class="sxs-lookup"><span data-stu-id="54681-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting</span></span>  <br/> |<span data-ttu-id="54681-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="54681-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="54681-118">**URI 参数**</span><span class="sxs-lookup"><span data-stu-id="54681-118">**URI Parameters**</span></span>
  
- <span data-ttu-id="54681-119">*有效*的可选。</span><span class="sxs-lookup"><span data-stu-id="54681-119">*effective*  - Optional.</span></span> <span data-ttu-id="54681-120">仅在使用特殊的用户 ID 默认时，此参数适用。</span><span class="sxs-lookup"><span data-stu-id="54681-120">This parameter applies only when the special user ID default is used.</span></span> <span data-ttu-id="54681-121">在其他情况下，它将被忽略。</span><span class="sxs-lookup"><span data-stu-id="54681-121">In other cases, it will be ignored.</span></span> <span data-ttu-id="54681-122">`True`返回有效的用户设置和`false`返回只是用户设置 （默认值）。</span><span class="sxs-lookup"><span data-stu-id="54681-122">`True` returns effective user settings and `false` returns just user settings (default).</span></span>
    
  <span data-ttu-id="54681-123">**请求标头**的任何其他的标头。</span><span class="sxs-lookup"><span data-stu-id="54681-123">**Request Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="54681-124">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="54681-124">**Request Body** - None.</span></span>
  
  <span data-ttu-id="54681-125">**响应**-响应包括 HTTP 状态代码和一响应标头。</span><span class="sxs-lookup"><span data-stu-id="54681-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
  <span data-ttu-id="54681-126">**状态代码**-成功的操作返回状态代码 200 （确定)。</span><span class="sxs-lookup"><span data-stu-id="54681-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
  <span data-ttu-id="54681-127">**响应标头**的任何其他的标头。</span><span class="sxs-lookup"><span data-stu-id="54681-127">**Response Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="54681-128">**响应正文**-下面是以 json 格式的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="54681-128">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
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