---
title: 获取用户的设置
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 摘要： 了解如何获取用户设置操作，它是用户设置服务的一部分。 用户设置服务被呼叫质量仪表板存储库 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: 562886196f06030aef30efbd6f583c29d7f29e59
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="get-user-setting"></a><span data-ttu-id="540e9-105">获取用户的设置</span><span class="sxs-lookup"><span data-stu-id="540e9-105">Get User Setting</span></span>
 
<span data-ttu-id="540e9-106">**摘要：**了解有关获取用户设置运算，是用户设置服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="540e9-106">**Summary:** Learn about the Get User Setting operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="540e9-107">用户设置服务被呼叫质量仪表板存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="540e9-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="540e9-108">通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="540e9-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="540e9-109">获取用户设置操作是用户设置服务存储库 API 调用质量仪表板中的一部分。</span><span class="sxs-lookup"><span data-stu-id="540e9-109">The Get User Setting operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-setting"></a><span data-ttu-id="540e9-110">获取用户的设置</span><span class="sxs-lookup"><span data-stu-id="540e9-110">Get User Setting</span></span>

<span data-ttu-id="540e9-111">获取用户设置返回的单个用户设置。</span><span class="sxs-lookup"><span data-stu-id="540e9-111">Get User Setting returns a single user setting.</span></span>
  

|<span data-ttu-id="540e9-112">**方法**</span><span class="sxs-lookup"><span data-stu-id="540e9-112">**Method**</span></span>|<span data-ttu-id="540e9-113">**请求的 URI**</span><span class="sxs-lookup"><span data-stu-id="540e9-113">**Request URI**</span></span>|<span data-ttu-id="540e9-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="540e9-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="540e9-115">获取</span><span class="sxs-lookup"><span data-stu-id="540e9-115">GET</span></span>  <br/> |<span data-ttu-id="540e9-116">https://\<门户网站\>/QoERepositoryService/存储 {库/用户/用户 Id} /setting/ {键}</span><span class="sxs-lookup"><span data-stu-id="540e9-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting/{key}</span></span>  <br/> |<span data-ttu-id="540e9-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="540e9-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="540e9-118">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="540e9-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="540e9-119">**请求标头**的任何其他标头。</span><span class="sxs-lookup"><span data-stu-id="540e9-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="540e9-120">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="540e9-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="540e9-121">**响应**-响应包括 HTTP 状态代码和一套响应标头。</span><span class="sxs-lookup"><span data-stu-id="540e9-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="540e9-122">**状态代码**-操作成功返回状态码 200 (OK)。</span><span class="sxs-lookup"><span data-stu-id="540e9-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="540e9-123">**响应标头**的任何其他标头。</span><span class="sxs-lookup"><span data-stu-id="540e9-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="540e9-124">**响应正文**-下面是 json 格式的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="540e9-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}

```

 <span data-ttu-id="540e9-125">*用户 Id*的用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="540e9-125">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="540e9-126">*键*的键设置。</span><span class="sxs-lookup"><span data-stu-id="540e9-126">*key*  - Key of the setting.</span></span>
  
 <span data-ttu-id="540e9-127">*值*的设置的值。</span><span class="sxs-lookup"><span data-stu-id="540e9-127">*value*  - Value of the setting.</span></span>
  

