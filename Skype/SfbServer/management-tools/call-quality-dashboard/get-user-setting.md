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
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 摘要： 了解如何获取用户设置操作，它是用户设置服务的一部分。 用户设置服务是呼叫质量仪表板的存储库 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
ms.openlocfilehash: 286939271bdc99790f125beabb68735dd4c5f758
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2018
ms.locfileid: "26530711"
---
# <a name="get-user-setting"></a><span data-ttu-id="34386-105">获取用户设置</span><span class="sxs-lookup"><span data-stu-id="34386-105">Get User Setting</span></span>
 
<span data-ttu-id="34386-106">**摘要：** 了解如何获取用户设置操作，它是用户设置服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="34386-106">**Summary:** Learn about the Get User Setting operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="34386-107">用户设置服务是呼叫质量仪表板的存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="34386-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="34386-108">呼叫质量仪表板是用于业务服务器 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="34386-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="34386-109">获取用户设置操作是用于呼叫的质量仪表板的存储库 API 中的用户设置服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="34386-109">The Get User Setting operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-setting"></a><span data-ttu-id="34386-110">获取用户设置</span><span class="sxs-lookup"><span data-stu-id="34386-110">Get User Setting</span></span>

<span data-ttu-id="34386-111">获取用户设置返回的单个用户设置。</span><span class="sxs-lookup"><span data-stu-id="34386-111">Get User Setting returns a single user setting.</span></span>
  

|<span data-ttu-id="34386-112">**方法**</span><span class="sxs-lookup"><span data-stu-id="34386-112">**Method**</span></span>|<span data-ttu-id="34386-113">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="34386-113">**Request URI**</span></span>|<span data-ttu-id="34386-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="34386-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="34386-115">获取</span><span class="sxs-lookup"><span data-stu-id="34386-115">GET</span></span>  <br/> |<span data-ttu-id="34386-116">https://\<门户\>/QoERepositoryService/存储库/用户 / {userId} /setting/ {键}</span><span class="sxs-lookup"><span data-stu-id="34386-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting/{key}</span></span>  <br/> |<span data-ttu-id="34386-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="34386-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="34386-118">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="34386-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="34386-119">**请求标头**的任何其他的标头。</span><span class="sxs-lookup"><span data-stu-id="34386-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="34386-120">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="34386-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="34386-121">**响应**-响应包括 HTTP 状态代码和一响应标头。</span><span class="sxs-lookup"><span data-stu-id="34386-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="34386-122">**状态代码**-成功的操作返回状态代码 200 （确定)。</span><span class="sxs-lookup"><span data-stu-id="34386-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="34386-123">**响应标头**的任何其他的标头。</span><span class="sxs-lookup"><span data-stu-id="34386-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="34386-124">**响应正文**-下面是以 json 格式的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="34386-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 <span data-ttu-id="34386-125">*用户 Id*的用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="34386-125">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="34386-126">*密钥*-键的设置。</span><span class="sxs-lookup"><span data-stu-id="34386-126">*key*  - Key of the setting.</span></span>
  
 <span data-ttu-id="34386-127">*值*-设置的值。</span><span class="sxs-lookup"><span data-stu-id="34386-127">*value*  - Value of the setting.</span></span>
  

