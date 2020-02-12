---
title: 获取集成日志
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
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 摘要：了解有关 "获取集成日志" 操作（这是 "调用质量" 仪表板的数据 API 的一部分）的信息。 通话质量仪表板是 Skype for business 服务器的工具。
ms.openlocfilehash: e1d790f4723eaaf716482143f08c78624db47433
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888801"
---
# <a name="get-integration-log"></a><span data-ttu-id="1ab6e-104">获取集成日志</span><span class="sxs-lookup"><span data-stu-id="1ab6e-104">Get Integration Log</span></span>
 
<span data-ttu-id="1ab6e-105">**摘要：** 了解 "获取集成日志" 操作，它是 "呼叫质量" 仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="1ab6e-105">**Summary:** Learn about the Get Integration Log operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="1ab6e-106">通话质量仪表板是 Skype for business 服务器的工具。</span><span class="sxs-lookup"><span data-stu-id="1ab6e-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="1ab6e-107">获取集成日志操作是用于呼叫质量仪表板的数据 API 的一部分</span><span class="sxs-lookup"><span data-stu-id="1ab6e-107">The Get Integration Log operation is part of the Data API for Call Quality Dashboard</span></span>
  
## <a name="get-integration-log"></a><span data-ttu-id="1ab6e-108">获取集成日志</span><span class="sxs-lookup"><span data-stu-id="1ab6e-108">Get Integration Log</span></span>

<span data-ttu-id="1ab6e-109">获取集成日志操作返回日志条目的列表，这些日志条目描述 QoE 多维数据集处理中的活动。</span><span class="sxs-lookup"><span data-stu-id="1ab6e-109">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>
  
<span data-ttu-id="1ab6e-110">出于安全原因，默认情况下禁用此操作。</span><span class="sxs-lookup"><span data-stu-id="1ab6e-110">This operation is disabled by default for security reasons.</span></span> <span data-ttu-id="1ab6e-111">禁用时，它将返回一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="1ab6e-111">When disabled, it returns an empty string.</span></span> <span data-ttu-id="1ab6e-112">若要启用此操作，管理员需要为数据 API 的主机 web 应用程序配置 web.config。</span><span class="sxs-lookup"><span data-stu-id="1ab6e-112">To enable this operation, administrators need to configure the web.config for Data API's host web application.</span></span>
  

|<span data-ttu-id="1ab6e-113">种</span><span class="sxs-lookup"><span data-stu-id="1ab6e-113">Method</span></span>|<span data-ttu-id="1ab6e-114">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="1ab6e-114">**Request URI**</span></span>|<span data-ttu-id="1ab6e-115">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="1ab6e-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1ab6e-116">获取</span><span class="sxs-lookup"><span data-stu-id="1ab6e-116">GET</span></span>  <br/> |<span data-ttu-id="1ab6e-117">https://\<portal\>/QoEDataService/IntegrationLog</span><span class="sxs-lookup"><span data-stu-id="1ab6e-117">https://\<portal\>/QoEDataService/IntegrationLog</span></span>  <br/> |<span data-ttu-id="1ab6e-118">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="1ab6e-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="1ab6e-119">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="1ab6e-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="1ab6e-120">**请求标题**-无其他标题。</span><span class="sxs-lookup"><span data-stu-id="1ab6e-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="1ab6e-121">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="1ab6e-121">**Request Body** - None.</span></span>
  
 <span data-ttu-id="1ab6e-122">**响应**-响应包括 HTTP 状态代码和一组响应标头。</span><span class="sxs-lookup"><span data-stu-id="1ab6e-122">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="1ab6e-123">**状态代码**-成功的操作返回状态代码200（OK）。</span><span class="sxs-lookup"><span data-stu-id="1ab6e-123">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="1ab6e-124">**响应标题**-无其他标题。</span><span class="sxs-lookup"><span data-stu-id="1ab6e-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="1ab6e-125">**响应正文**-下面是日志条目的示例结构。</span><span class="sxs-lookup"><span data-stu-id="1ab6e-125">**Response Body** - Below is a sample structure of log entries.</span></span>
  
```json
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


