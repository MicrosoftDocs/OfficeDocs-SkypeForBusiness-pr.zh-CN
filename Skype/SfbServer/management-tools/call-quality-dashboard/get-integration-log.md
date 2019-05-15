---
title: 获取集成日志
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 摘要： 了解如何获取集成日志操作，它是用于呼叫的质量仪表板的数据 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
ms.openlocfilehash: 450122266caa21359b424e3abb76a13476f386c0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926098"
---
# <a name="get-integration-log"></a><span data-ttu-id="784e7-104">获取集成日志</span><span class="sxs-lookup"><span data-stu-id="784e7-104">Get Integration Log</span></span>
 
<span data-ttu-id="784e7-105">**摘要：** 了解有关获取集成日志操作，它是用于呼叫的质量仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="784e7-105">**Summary:** Learn about the Get Integration Log operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="784e7-106">呼叫质量仪表板是用于业务服务器 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="784e7-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="784e7-107">获取集成日志操作是呼叫质量仪表板的数据 API 的一部分</span><span class="sxs-lookup"><span data-stu-id="784e7-107">The Get Integration Log operation is part of the Data API for Call Quality Dashboard</span></span>
  
## <a name="get-integration-log"></a><span data-ttu-id="784e7-108">获取集成日志</span><span class="sxs-lookup"><span data-stu-id="784e7-108">Get Integration Log</span></span>

<span data-ttu-id="784e7-109">获取集成日志操作返回描述 QoE 多维数据集中活动的日志条目的列表处理。</span><span class="sxs-lookup"><span data-stu-id="784e7-109">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>
  
<span data-ttu-id="784e7-110">默认情况下，为了安全起见，此操作被禁用。</span><span class="sxs-lookup"><span data-stu-id="784e7-110">This operation is disabled by default for security reasons.</span></span> <span data-ttu-id="784e7-111">禁用时，它将返回空字符串。</span><span class="sxs-lookup"><span data-stu-id="784e7-111">When disabled, it returns an empty string.</span></span> <span data-ttu-id="784e7-112">若要启用此操作，管理员需要配置数据 API 主机 web 应用程序的 web.config。</span><span class="sxs-lookup"><span data-stu-id="784e7-112">To enable this operation, administrators need to configure the web.config for Data API's host web application.</span></span>
  

|<span data-ttu-id="784e7-113">方法</span><span class="sxs-lookup"><span data-stu-id="784e7-113">Method</span></span>|<span data-ttu-id="784e7-114">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="784e7-114">**Request URI**</span></span>|<span data-ttu-id="784e7-115">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="784e7-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="784e7-116">获取</span><span class="sxs-lookup"><span data-stu-id="784e7-116">GET</span></span>  <br/> |<span data-ttu-id="784e7-117">https://\<门户\>/QoEDataService/IntegrationLog</span><span class="sxs-lookup"><span data-stu-id="784e7-117">https://\<portal\>/QoEDataService/IntegrationLog</span></span>  <br/> |<span data-ttu-id="784e7-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="784e7-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="784e7-119">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="784e7-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="784e7-120">**请求标头**的任何其他的标头。</span><span class="sxs-lookup"><span data-stu-id="784e7-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="784e7-121">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="784e7-121">**Request Body** - None.</span></span>
  
 <span data-ttu-id="784e7-122">**响应**-响应包括 HTTP 状态代码和一响应标头。</span><span class="sxs-lookup"><span data-stu-id="784e7-122">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="784e7-123">**状态代码**-成功的操作返回状态代码 200 （确定)。</span><span class="sxs-lookup"><span data-stu-id="784e7-123">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="784e7-124">**响应标头**的任何其他的标头。</span><span class="sxs-lookup"><span data-stu-id="784e7-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="784e7-125">**响应正文**-下面是示例结构的日志条目。</span><span class="sxs-lookup"><span data-stu-id="784e7-125">**Response Body** - Below is a sample structure of log entries.</span></span>
  
```
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


