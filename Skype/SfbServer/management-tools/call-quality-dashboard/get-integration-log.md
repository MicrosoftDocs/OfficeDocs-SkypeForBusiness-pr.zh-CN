---
title: 获取集成日志
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
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 摘要：了解"获取集成日志"操作，该操作是通话质量仪表板的数据 API 的一部分。 通话质量仪表板是 Skype for Business Server 的工具。
ms.openlocfilehash: 69827fa9f3fd3f56843a41867b029a071799ba66
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832592"
---
# <a name="get-integration-log"></a><span data-ttu-id="493bf-104">获取集成日志</span><span class="sxs-lookup"><span data-stu-id="493bf-104">Get Integration Log</span></span>
 
<span data-ttu-id="493bf-105">**摘要：** 了解"获取集成日志"操作，该操作是通话质量仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="493bf-105">**Summary:** Learn about the Get Integration Log operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="493bf-106">通话质量仪表板是 Skype for Business Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="493bf-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="493bf-107">获取集成日志操作是通话质量仪表板的数据 API 的一部分</span><span class="sxs-lookup"><span data-stu-id="493bf-107">The Get Integration Log operation is part of the Data API for Call Quality Dashboard</span></span>
  
## <a name="get-integration-log"></a><span data-ttu-id="493bf-108">获取集成日志</span><span class="sxs-lookup"><span data-stu-id="493bf-108">Get Integration Log</span></span>

<span data-ttu-id="493bf-109">获取集成日志操作返回描述 QoE 多维数据集处理中的活动的日志条目列表。</span><span class="sxs-lookup"><span data-stu-id="493bf-109">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>
  
<span data-ttu-id="493bf-110">出于安全考虑，此操作默认处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="493bf-110">This operation is disabled by default for security reasons.</span></span> <span data-ttu-id="493bf-111">禁用后，它将返回一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="493bf-111">When disabled, it returns an empty string.</span></span> <span data-ttu-id="493bf-112">若要启用此操作，管理员需要配置web.config API 的主机 Web 应用程序的应用程序。</span><span class="sxs-lookup"><span data-stu-id="493bf-112">To enable this operation, administrators need to configure the web.config for Data API's host web application.</span></span>
  

|<span data-ttu-id="493bf-113">Method</span><span class="sxs-lookup"><span data-stu-id="493bf-113">Method</span></span>|<span data-ttu-id="493bf-114">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="493bf-114">**Request URI**</span></span>|<span data-ttu-id="493bf-115">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="493bf-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="493bf-116">GET</span><span class="sxs-lookup"><span data-stu-id="493bf-116">GET</span></span>  <br/> |<span data-ttu-id="493bf-117">https:// \<portal\> /QoEDataService/IntegrationLog</span><span class="sxs-lookup"><span data-stu-id="493bf-117">https://\<portal\>/QoEDataService/IntegrationLog</span></span>  <br/> |<span data-ttu-id="493bf-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="493bf-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="493bf-119">**URI 参数** - 无。</span><span class="sxs-lookup"><span data-stu-id="493bf-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="493bf-120">**请求标头** - 无其他标头。</span><span class="sxs-lookup"><span data-stu-id="493bf-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="493bf-121">**请求正文** - 无。</span><span class="sxs-lookup"><span data-stu-id="493bf-121">**Request Body** - None.</span></span>
  
 <span data-ttu-id="493bf-122">**响应** - 响应包括 HTTP 状态代码和一组响应标头。</span><span class="sxs-lookup"><span data-stu-id="493bf-122">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="493bf-123">**状态代码** - 成功操作返回状态代码 200 (确定) 。</span><span class="sxs-lookup"><span data-stu-id="493bf-123">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="493bf-124">**响应标头** - 无其他标头。</span><span class="sxs-lookup"><span data-stu-id="493bf-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="493bf-125">**响应正文** - 下面是日志条目的示例结构。</span><span class="sxs-lookup"><span data-stu-id="493bf-125">**Response Body** - Below is a sample structure of log entries.</span></span>
  
```json
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


