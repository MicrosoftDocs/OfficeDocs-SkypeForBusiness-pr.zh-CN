---
title: 获得整合日志
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 摘要： 了解获得整合日志操作，这是呼叫质量仪表板的数据 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: 8ccd4fc299cbf5310a5974d55b181aa1f42255ce
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="get-integration-log"></a><span data-ttu-id="d5b62-104">获得整合日志</span><span class="sxs-lookup"><span data-stu-id="d5b62-104">Get Integration Log</span></span>
 
<span data-ttu-id="d5b62-105">**摘要：**了解有关获取整合日志操作，这是呼叫质量仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="d5b62-105">**Summary:** Learn about the Get Integration Log operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="d5b62-106">通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="d5b62-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="d5b62-107">获得整合日志操作是呼叫质量仪表板数据 API 的一部分</span><span class="sxs-lookup"><span data-stu-id="d5b62-107">The Get Integration Log operation is part of the Data API for Call Quality Dashboard</span></span>
  
## <a name="get-integration-log"></a><span data-ttu-id="d5b62-108">获得整合日志</span><span class="sxs-lookup"><span data-stu-id="d5b62-108">Get Integration Log</span></span>

<span data-ttu-id="d5b62-109">获取操作返回描述 QoE 多维数据集中活动的日志条目的列表处理整合日志。</span><span class="sxs-lookup"><span data-stu-id="d5b62-109">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>
  
<span data-ttu-id="d5b62-110">默认情况下，出于安全原因禁用此操作。</span><span class="sxs-lookup"><span data-stu-id="d5b62-110">This operation is disabled by default for security reasons.</span></span> <span data-ttu-id="d5b62-111">当禁用时，它会返回一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="d5b62-111">When disabled, it returns an empty string.</span></span> <span data-ttu-id="d5b62-112">若要启用此操作，管理员需要配置数据 API 宿主 web 应用程序的 web.config。</span><span class="sxs-lookup"><span data-stu-id="d5b62-112">To enable this operation, administrators need to configure the web.config for Data API's host web application.</span></span>
  

|<span data-ttu-id="d5b62-113">方法</span><span class="sxs-lookup"><span data-stu-id="d5b62-113">Method</span></span>|<span data-ttu-id="d5b62-114">**请求的 URI**</span><span class="sxs-lookup"><span data-stu-id="d5b62-114">**Request URI**</span></span>|<span data-ttu-id="d5b62-115">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="d5b62-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d5b62-116">获取</span><span class="sxs-lookup"><span data-stu-id="d5b62-116">GET</span></span>  <br/> |<span data-ttu-id="d5b62-117">https://\<门户网站\>/QoEDataService/IntegrationLog</span><span class="sxs-lookup"><span data-stu-id="d5b62-117">https://\<portal\>/QoEDataService/IntegrationLog</span></span>  <br/> |<span data-ttu-id="d5b62-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="d5b62-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="d5b62-119">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="d5b62-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="d5b62-120">**请求标头**的任何其他标头。</span><span class="sxs-lookup"><span data-stu-id="d5b62-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="d5b62-121">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="d5b62-121">**Request Body** - None.</span></span>
  
 <span data-ttu-id="d5b62-122">**响应**-响应包括 HTTP 状态代码和一套响应标头。</span><span class="sxs-lookup"><span data-stu-id="d5b62-122">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="d5b62-123">**状态代码**-操作成功返回状态码 200 (OK)。</span><span class="sxs-lookup"><span data-stu-id="d5b62-123">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="d5b62-124">**响应标头**的任何其他标头。</span><span class="sxs-lookup"><span data-stu-id="d5b62-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="d5b62-125">**响应正文**-以下是日志条目示例结构。</span><span class="sxs-lookup"><span data-stu-id="d5b62-125">**Response Body** - Below is a sample structure of log entries.</span></span>
  
```
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]

```


